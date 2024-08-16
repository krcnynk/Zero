Status: **Editing**

Tags:[[C++]]

# inline

The `inline` keyword is used to suggest to the compiler that the function should be expanded at the point of each call, rather than being invoked through a function call. This can potentially improve performance by eliminating function call overhead.

**Small Functions**: `inline` is typically used for small, frequently called functions where the overhead of a function call is significant relative to the function’s execution time.

**Header Files**: When defining functions in header files, especially template functions, they should be `inline` to prevent multiple definition errors during linking. This allows the function definitions to be included in multiple translation units without causing linkage issues.

- Function definition in header
- Header included in multiple translational units
- Linktime it will pick one and ignore others
- Otherwise each .cpp file that includes that header will compile the function and put a symbol for it in the generated object file

function's _definition_ can appear in multiple different TUs and then the linker will just pick one of them and throw away the rest because you promised that the definition will be the same everywhere
# References