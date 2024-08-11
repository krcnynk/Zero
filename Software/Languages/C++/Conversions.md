Status: **Editing**

Tags: [[C++]]

# Conversions

**Implicit Conversion** 
Implicitly converts from int to float, there is no guarantee this will work everytime
```cpp
float MyNumber { 5 }; // 5.0
```
happens in function returns, operators

**Narrowing Cast**
Loss of data from implicit conversion
```cpp
int Pi = 3.14;
```
Uniform initialization prevents
```cpp
int Pi { 3.14 };
float P {myDouble}; //will not cause trouble, no data loss
```
This will happen in functions as well




# References

