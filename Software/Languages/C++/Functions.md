Status: **Editing**

Tags: [[C++]]

# functions
An _**argument**_ is data we provide to a function when we call it
A _**parameter**_ is what receives that data within the function.

**Default Parameter**
```cpp
void TakeDamage(int Damage, bool isMagical = false) // isMagical is optional parameter, cannot create another parameter after this one
```
**Explicitly default parameter**
```cpp
Add({}, {}, {}); 
```

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
