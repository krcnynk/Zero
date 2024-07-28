**Introduction / Getting Started**

- Introduction to these tutorials
- Introduction to programming languages
- Introduction to C/C++
- Introduction to C++ development
- Introduction to the compiler, linker, and libraries
- Installing an Integrated Development Environment (IDE)
- Compiling your first program
- A few common C++ problems
- Configuring your compiler: Build configurations
- Configuring your compiler: Compiler extensions
- Configuring your compiler: Warning and error levels
- Configuring your compiler: Choosing a language standard
- What language standard is my compiler using?

**C++ Basics**

- Statements and the structure of a program
- Comments
- Introduction to objects and variables
- Variable assignment and initialization
- Introduction to iostream: cout, cin, and endl
- Uninitialized variables and undefined behavior
- Keywords and naming identifiers
- Whitespace and basic formatting
- Introduction to literals and operators
- Introduction to expressions
- Developing your first program
- Chapter 1 summary and quiz

**C++ Basics: Functions and Files**

- Introduction to functions
- Function return values (value-returning functions)
- Void functions (non-value returning functions)
- Introduction to function parameters and arguments
- Introduction to local scope
- Why functions are useful, and how to use them effectively
- Forward declarations and definitions
- Programs with multiple code files
- Naming collisions and an introduction to namespaces
- Introduction to the preprocessor
- Header files
- Header guards
- How to design your first programs
- Chapter 2 summary and quiz

**Debugging C++ Programs**

- Syntax and semantic errors
- The debugging process
- A strategy for debugging
- Basic debugging tactics
- More debugging tactics
- Using an integrated debugger: Stepping
- Using an integrated debugger: Running and breakpoints
- Using an integrated debugger: Watching variables
- Using an integrated debugger: The call stack
- Finding issues before they become problems
- Chapter 3 summary and quiz

**Fundamental Data Types**

- Introduction to fundamental data types
- Void
- Object sizes and the sizeof operator
- Signed integers
- Unsigned integers, and why to avoid them
- Fixed-width integers and size_t
- Introduction to scientific notation
- Floating point numbers
- Boolean values
- Introduction to if statements
- Chars
- Introduction to type conversion and static_cast
- Chapter 4 summary and quiz

**Constants and Strings**

- Constant variables (named constants)
- Literals
- Numeral systems (decimal, binary, hexadecimal, and octal)
- Constant expressions and compile-time optimization
- Constexpr variables
- The conditional operator
- Inline functions and variables
- Constexpr and consteval functions
- Introduction to std::string
- Introduction to std::string_view
- std::string_view (part 2)
- Chapter 5 summary and quiz

**Operators**

- Operator precedence and associativity
- Arithmetic operators
- Remainder and Exponentiation
- Increment/decrement operators, and side effects
- The comma operator
- Relational operators and floating point comparisons
- Logical operators
- Chapter 6 summary and quiz

**Bit Manipulation (optional chapter)**

- Bit flags and bit manipulation via std::bitset
- Bitwise operators
- Bit manipulation with bitwise operators and bit masks
- Converting integers between binary and decimal representation

**Scope, Duration, and Linkage**

- Compound statements (blocks)
- User-defined namespaces and the scope resolution operator
- Local variables
- Introduction to global variables
- Variable shadowing (name hiding)
- Internal linkage
- External linkage and variable forward declarations
- Why (non-const) global variables are evil
- Sharing global constants across multiple files (using inline variables)
- Static local variables
- Scope, duration, and linkage summary
- Using declarations and using directives
- Unnamed and inline namespaces
- Chapter 7 summary and quiz

**Control Flow**

- Control flow introduction
- If statements and blocks
- Common if statement problems
- Constexpr if statements
- Switch statement basics
- Switch fallthrough and scoping
- Goto statements
- Introduction to loops and while statements
- Do while statements
- For statements
- Break and continue
- Halts (exiting your program early)
- Introduction to random number generation
- Generating random numbers using Mersenne Twister
- Global random numbers (Random.h)
- Chapter 8 summary and quiz

**Error Detection and Handling**

- Introduction to testing your code
- Code coverage
- Common semantic errors in C++
- Detecting and handling errors
- std::cin and handling invalid input
- Assert and static_assert
- Chapter 9 summary and quiz

**Type Conversion, Type Aliases, and Type Deduction**

- Implicit type conversion
- Floating-point and integral promotion
- Numeric conversions
- Narrowing conversions, list initialization, and constexpr initializers
- Arithmetic conversions
- Explicit type conversion (casting) and static_cast
- Typedefs and type aliases
- Type deduction for objects using the auto keyword
- Type deduction for functions
- Chapter 10 summary and quiz

**Function Overloading and Function Templates**

- Introduction to function overloading
- Function overload differentiation
- Function overload resolution and ambiguous matches
- Deleting functions
- Default arguments
- Function templates
- Function template instantiation
- Using function templates in multiple files
- Function templates with multiple template types
- Non-type template parameters
- Chapter 11 summary and quiz

**Compound Types: References and Pointers**

- Introduction to compound data types
- Value categories (lvalues and rvalues)
- Lvalue references
- Lvalue references to const
- Pass by lvalue reference
- Pass by const lvalue reference
- Introduction to pointers
- Null pointers
- Pointers and const
- Pass by address
- Pass by address (part 2)
- Return by reference and return by address
- In and out parameters
- Type deduction with pointers, references, and const
- std::optional
- Chapter 12 summary and quiz

**Compound Types: Enums and Structs**

- Introduction to program-defined (user-defined) types
- Unscoped enumerations
- Unscoped enumerator integral conversions
- Converting an enumeration to and from a string
- Introduction to overloading the I/O operators
- Scoped enumerations (enum classes)
- Introduction to structs, members, and member selection
- Struct aggregate initialization
- Default member initialization
- Passing and returning structs
- Struct miscellany
- Member selection with pointers and references
- Class templates
- Class template argument deduction (CTAD) and deduction guides
- Alias templates
- Chapter 13 summary and quiz
- Using a language reference

**Introduction to Classes**

- Introduction to object-oriented programming
- Introduction to classes
- Member functions
- Const class objects and const member functions
- Public and private members and access specifiers
- Access functions
- Member functions returning references to data members
- The benefits of data hiding (encapsulation)
- Introduction to constructors
- Constructor member initializer lists
- Default constructors and default arguments
- Delegating constructors
- Temporary class objects
- Introduction to the copy constructor
- Class initialization and copy elision
- Converting constructors and the explicit keyword
- Constexpr aggregates and classes
- Chapter 14 summary and quiz

**More on Classes**

- The hidden “this” pointer and member function chaining
- Classes and header files
- Nested types (member types)
- Introduction to destructors
- Class templates with member functions
- Static member variables
- Static member functions
- Friend non-member functions
- Friend classes and friend member functions
- Ref qualifiers
- Chapter 15 summary and quiz

**Dynamic Arrays: std::vector**

- Introduction to containers and arrays
- Introduction to std::vector and list constructors
- std::vector and the unsigned length and subscript problem
- Passing std::vector
- Returning std::vector, and an introduction to move semantics
- Arrays and loops
- Arrays, loops, and sign challenge solutions
- Range-based for loops (for-each)
- Array indexing and length using enumerators
- std::vector resizing and capacity
- std::vector and stack behavior
- std::vector<bool>
- Chapter 16 summary and quiz

**Fixed-size Arrays: std::array and C-style Arrays**

- Introduction to std::array
- std::array length and indexing
- Passing and returning std::array
- std::array of class types, and brace elision
- Arrays of references via std::reference_wrapper
- std::array and enumerations
- Introduction to C-style arrays
- C-style array decay
- Pointer arithmetic and subscripting
- C-style strings
- C-style string symbolic constants
- Multidimensional C-style Arrays
- Multidimensional std::array
- Chapter 17 summary and quiz

**Iterators and Algorithms (under construction)**

- Sorting an array using selection sort
- Introduction to iterators
- Introduction to standard library algorithms
- Timing your code

**Dynamic Allocation (under construction)**

- Dynamic memory allocation with new and delete
- Dynamically allocating arrays
- Destructors
- Pointers to pointers and dynamic multidimensional arrays
- Void pointers

**Functions**

- Function Pointers
- The stack and the heap
- Recursion
- Command line arguments
- Ellipsis (and why to avoid them)
- Introduction to lambdas (anonymous functions)
- Lambda captures
- Lambda return types
- Lambdas and templates
- Chapter 18 summary and quiz

**More on Classes**

- Virtual functions
- Pure virtual functions and abstract classes
- Introduction to the dynamic type
- Inheritance
- Derived classes
- Multiple inheritance
- Virtual inheritance
- The diamond problem
- Class hierarchies
- Chapter 19 summary and quiz

**Inheritance**

- Introduction to class inheritance
- Base and derived class visibility
- Access control in inheritance
- Introduction to public, protected, and private inheritance
- Constructor and destructor inheritance
- Composition vs. inheritance
- Class interfaces and virtual functions
- Chapter 20 summary and quiz

**Advanced Topics**

- The C++ standard library
- std::vector vs. std::list
- An introduction to smart pointers
- std::unique_ptr
- std::shared_ptr
- std::weak_ptr
- Chapter 21 summary and quiz

**Final Projects**

- Working with large projects
- Working with legacy code
- Code quality and refactoring
- Unit testing
- Final project examples