Status: **Editing**

Tags: [[C++]]

# Cmake

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