Tags: [[../C++/C++|C++]]
Status: **Editing**
# pointers

Assume 32 bit system (decides how big the address lengths are), 0x is hexadecimal

```
int* p1; // has garbage value
int* p2 = nullptr; // points to nothing
int* p4 = p3; // assign pointer to same memory loc

const int* pConstValue = &x;  // Pointer to a constant value (can't change *pConstValue)
int* const pConstPtr = &x;    // Constant pointer (can't change pConstPtr itself)

```


```cpp
int a = 2; //  starting from 0x00001000, store 0x0002 (2 byte int)
little-endian
0x00001000 02
0x00001001 00
int b = a; // 0x00001002 0x0002 (2 byte int and copied from a)
0x00001002 02
0x00001003 00
int* ptr = &a; // 0x00001004 0x00001000
0x00001004 00
0x00001005 10
0x00001006 00
0x00001007 00
printf("%d\n",*ptr); // printing integer
```
ptr + 1; pointer arithmetic, if pointer is an **integer pointer** jump to next integer (2 bytes)



# References
