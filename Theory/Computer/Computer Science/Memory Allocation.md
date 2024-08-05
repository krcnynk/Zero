## User Level
Memory Allocation
 - Heap Function
```c
#include <windows.h>
#include <stdio.h>

int main() {
    HANDLE hHeap = HeapCreate(0, 0, 0);
    if (hHeap == NULL) {
        printf("Heap creation failed!\n");
        return 1;
    }

    int *pInt = (int *)HeapAlloc(hHeap, HEAP_ZERO_MEMORY, sizeof(int));
    if (pInt == NULL) {
        printf("Heap allocation failed!\n");
        HeapDestroy(hHeap);
        return 1;
    }

    *pInt = 123;
    printf("Value: %d\n", *pInt);

    HeapFree(hHeap, 0, pInt);
    HeapDestroy(hHeap);

    return 0;
}

```
- Virtual Memory
```c
#include <windows.h>
#include <stdio.h>

int main() {
    SIZE_T size = 1024 * 1024;  // 1 MB
    LPVOID pMem = VirtualAlloc(NULL, size, MEM_COMMIT | MEM_RESERVE, PAGE_READWRITE);
    if (pMem == NULL) {
        printf("VirtualAlloc failed!\n");
        return 1;
    }

    int *pInt = (int *)pMem;
    *pInt = 456;
    printf("Value: %d\n", *pInt);

    if (!VirtualFree(pMem, 0, MEM_RELEASE)) {
        printf("VirtualFree failed!\n");
        return 1;
    }

    return 0;
}

```
- C Runtime Library Functions
```c
#include <stdlib.h>
#include <stdio.h>

int main() {
    int *pInt = (int *)malloc(sizeof(int));
    if (pInt == NULL) {
        printf("malloc failed!\n");
        return 1;
    }

    *pInt = 789;
    printf("Value: %d\n", *pInt);

    free(pInt);

    return 0;
}
```

## Kernel Level
```c
#include <ntddk.h>

VOID DriverUnload(PDRIVER_OBJECT DriverObject) {
    UNREFERENCED_PARAMETER(DriverObject);
}

NTSTATUS DriverEntry(PDRIVER_OBJECT DriverObject, PUNICODE_STRING RegistryPath) {
    UNREFERENCED_PARAMETER(RegistryPath);

    DriverObject->DriverUnload = DriverUnload;

    PVOID pMem = ExAllocatePoolWithTag(NonPagedPool, 1024, 'tgaT');
    if (pMem == NULL) {
        KdPrint(("ExAllocatePoolWithTag failed!\n"));
        return STATUS_INSUFFICIENT_RESOURCES;
    }

    // Use the memory
    RtlZeroMemory(pMem, 1024);

    ExFreePoolWithTag(pMem, 'tgaT');

    return STATUS_SUCCESS;
}

```