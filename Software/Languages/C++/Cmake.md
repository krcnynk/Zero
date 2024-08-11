Status: **Editing**

Tags: [[C++]]

# cmake

The **debug configuration** is designed to help you debug your program, and is generally the one you will use when writing your programs. This configuration turns off all optimizations, and includes debugging information, which makes your programs larger and slower, but much easier to debug. The debug configuration is usually  selected as the active configuration by default. We’ll talk more about debugging techniques in a later lesson.

The **release configuration** is designed to be used when releasing your program to the public. This version is typically optimized for size and performance, and doesn’t contain the extra debugging information. Because the release configuration includes all optimizations, this mode is also useful for testing the performance of your code (which we’ll show you how to do later in the tutorial series).


**Global Flags:**

You can apply compiler flags globally to all targets in your CMake project.
```
# Add global compile options
add_compile_options(-Wall -Wextra -pedantic)
```

**Target-Specific Flags:**

To apply flags only to specific targets, use `target_compile_options()`.
```
add_executable(MyProject src/main.cpp src/utils.cpp)
# Apply flags to a specific target
target_compile_options(MyProject PRIVATE -Wall -Wextra -pedantic)

```

**Conditional Flags:**

```
set(MY_DEBUG_FLAGS "-ggdb -pedantic-errors -Wall -Weffc++ -Wextra -Wconversion -Wsign-conversion")

target_compile_options(MyProject PRIVATE
    $<$<CONFIG:Debug>${MY_DEBUG_FLAGS}>
)

```

Include paths specify directories where the compiler should look for header files during compilation.
**Global Include Paths:**
```
# Add global include directories
include_directories(include)
```
**Target-Specific Include Paths:**
```
add_executable(MyProject src/main.cpp src/utils.cpp)

# Add include directories for a specific target
target_include_directories(MyProject PRIVATE include)
```
**Conditional Include Paths:**
```
if(MY_CONDITION)
    target_include_directories(MyProject PRIVATE include/condition)
else()
    target_include_directories(MyProject PRIVATE include/default)
endif()

```

**Global Define**
`my_target` will have the preprocessor macro `MY_MACRO` defined and will include headers from the `include` directory.
```
add_definitions(-DMY_MACRO=1)
target_include_directories(my_target PRIVATE ${CMAKE_SOURCE_DIR}/include)
```
**Specific target Defines**
```
target_compile_definitions(my_target PRIVATE MY_MACRO=1)
```
# References