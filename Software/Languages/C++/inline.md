Status: **Editing**

Tags:[[C++]]

# inline

The `inline` keyword is used to suggest to the compiler that the function should be expanded at the point of each call, rather than being invoked through a function call. This can potentially improve performance by eliminating function call overhead.

**Small Functions**: `inline` is typically used for small, frequently called functions where the overhead of a function call is significant relative to the function’s execution time.

**Header Files**: When defining functions in header files, especially template functions, they should be `inline` to prevent multiple definition errors during linking. This allows the function definitions to be included in multiple translation units without causing linkage issues.

**Notes**
- **Compiler Discretion**: The `inline` keyword is a suggestion to the compiler; it may ignore it and not inline the function.
- **Code Size**: Excessive use of `inline` can lead to code bloat, increasing the binary size and potentially causing cache inefficiencies.
# References