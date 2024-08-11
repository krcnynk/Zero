Status: **Editing**

Tags: [[C++]]

# C++

**Structs**
```cpp
struct Vector3 {
  float x;
  float y;
  float z;
}

int main()
{
	Vector3 Position {1.9,2.5,0.3}; // Aggregate initialization
}
- `structs` should be used for passive objects that carry data, but lack any functionality other than access/setting the data members.
- All fields must be public, and accessed directly rather than through getter/setter methods.
- Methods should not provide behavior but should only be used to set up the data e.g., constructor, `Initialize()`, `Reset()`.
- If more functionality is required, a `class` is more appropriate.
- If in doubt, make it a `class`.
```

**Operator Overloading**
```cpp
Vector3 operator+(Vector3 a, Vector3 b) // can pass by reference here
{
	return Vector3{a.x+b.x,a.y+b.y,a.z+b.z};
}
// Create a new object using the + operator
Vector3 CurrentPosition { 1.0, 2.0, 3.0 };
Vector3 Movement { 4.0, 5.0, 6.0 };
Vector3 NewPosition { CurrentPosition + Movement }; // to do this we need an operator


//
// As a member function this would have one parameter
Vector3 operator+(const Vector3 &b) const
{
	return Vector3{a.x+b.x,a.y+b.y,a.z+b.z};
}
//The `const` keyword at the end of the function signifies that the function does not modify the object on which it is called.
```
Unary and Binary operators can be overloaded as well

**Structured Binding**
```cpp
auto [a, b, c]{SomeVector};
auto [d, e, f](SomeVector);
auto [g, h, i] = SomeVector;
```


# References