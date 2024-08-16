Status: **Editing**

Tags:

# function pointer

```cpp
int add(int a, int b) {
    return a + b;
}

int (*funcPtr)(int, int) = &add;
int (*funcPtr)(int, int) = add; // same decays to pointer

int arr[5] = {1, 2, 3, 4, 5};
int *ptr = arr; // arr also decays to pointer except smt like sizeof(arr) then type matters, functions dont have types
```




# References