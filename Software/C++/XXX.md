Preprocessor Directives
These directives are processed before compilation of the code.
```
#include <iostream>
```

Main function (entry point)

Standard output (std::cout)

Namespaces (e.g. std)

Operators
add, sub, mult, div, mod
equal, not equal, greater than, less than, goe, loe
&&, ||, ! (logical operators)
&, |, ^, ~, <<, >> (shifts are zero padded)
most can be combined with assignment operators
? :, ternary operator (a > 3) ? 10 : 20
, evaluate first op&discard, evaluate second op return value/type.
. member operator, access member of an object
** pointer dereference
& address of a variable
-> member access through a pointer
int& x = a; // x is now a reference to a

Control structures
```
if (a>5)
{}
else if (a>15)
{}
else
{}
```

```
switch (expression)
{
case constant1:
break; // other cases will not be checked
case constant2:
default:
}
```

```
for (init; cond; increment)
{}
```

```
while(condition)
```

```
do{

} while (condition); //block is executed at least once
```

```
break; // exit nearest innermost loop or switch
continue; // skip rest of current loop, move to next iteration
```


Functions
```
int add(int, int); // Function prototype, beginning of file or header

int add(float, int = 5); //Function Overloading , Default Arguments

inline int add(int a, int b) { return a + b;} // compiler inserts complete body of function whenever function is called

recursion calls itself with base case...
```

```
void modify(int a) //Pass-by-value
void modify(int& a) //Pass-by-reference
void display(const std::string& message) const parameter should not modify arguments, read only

//Templates
template <typename T> T 
add(T a, T b) 
{ return a + b; }

// Lambda example
std::vector<int> numbers = {1, 2, 3, 4, 5};
std::for_each(numbers.begin(), numbers.end(), 
[](int n) { std::cout << n << " "; }); std::cout << std::endl;
```
