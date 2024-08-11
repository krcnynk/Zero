Status: **Editing**

Tags: [[C++]]

# Function Prototype
**Function Prototype**
compiler reads our files top-to-bottom
```cpp
void HandlePositive(int x) {
  if (x < 0) HandleNegative(x);
}

void HandleNegative(int x){
  if (x >= 0) HandlePositive(x);
}
```
so declare function prototype (API) first!




# References