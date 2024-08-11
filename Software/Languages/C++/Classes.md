Status: **Editing**

Tags:[[C++]]

# Classes
**Class Members**
```cpp
Monster Bonker;
Bonker.Health;
Boker.TakeDamage();

class Monster{
public:
	void TakeDamage(int Damage); // prototype
	
};

void Monster::TakeDamage(int Damage) { //definition
	  Health -= Damage;
	}
```


**Class Invariant**
```cpp
class Monster {
public:
  int Health { 150 }; // cannot be negative
  // if (Health < 0) { Health = 0; } inside TakeDamage()
};
```
A class itself is a form of contract that is enforced by the compiler. For example, if an object is a `Monster`, it is guaranteed to have an `int` variable called `Health`.
Class invariants are another form of contract - they’re just one we have to implement and document ourselves.

**Encapsulation**
functions (api) make it public and make class variables private, protected is like private but inherited classes can also use them

**Constructor and Destructor**
```cpp
class Monster {
public:
  Monster() = default;
  Monster(string Name, int Health = 150){ // adding this will delete default
  ~Monster() {} // automatically runs when object is deleted
  Vector3(float x = 0, float y = 0, float z = 0) : x(x), y(y), z(z) {}
```
similar to functions prototype, constructors can be declared/defined

```

# References