Status: **Editing**

Tags:

# Compilation
**Compilation**
cxx files are compiled first then linked
The compiler reads each of our source files from top to bottom. Each file generates an intermediate output, sometimes referred to as a translation unit.
The linker then takes these translation units and links them together to create a single cohesive package
We’re telling the compiler that the linker will take care of it.
```cpp
int Add(int, int);
```
# References