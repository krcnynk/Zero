Status: **Editing**

Tags: [[C++]]

# Compilation

- Preprocessor takes `.cpp` file
- Preprocessor processes each line with # directives (#define,#include,#pragma)
- Each complete `.cpp` file is compiled into object file `.o`
	- `.cpp` to assembly code `.as`
	- assembler converts assembly to machine code (binary) `.o`
		- `.o` has machine code, symbols (function name, variable name) that are defined and not defined (extern)
- Linker will take object files and creates a library or executable
	- using a collection of `.o` files, static `.a` or dynamic `.so` libraries are formed
		- linker takes the necessary object files from the static library and includes them directly in the executable (self contained executable)
		- the linker records that the executable depends on the dynamic library, loaded into memory (must be available on the system)

A translation unit roughly consists of a source file after it has been processed by the C preprocessor, meaning that header files listed in ```#include``` directives are literally included, sections of code within ```#ifndef``` may be included, and macros have been expanded.




The compiler reads each of our source files from top to bottom. Each file generates an intermediate output, sometimes referred to as a translation unit.
The linker then takes these translation units and links them together to create a single cohesive package
We’re telling the compiler that the linker will take care of it.
```cpp
int Add(int, int);
```
# References