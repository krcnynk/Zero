Status: **Editing**

Tags:[[C++]]

# inheritance


```cpp
class Goblin : public Monster, public A {
public:
  Goblin() : Monster{}{ // all inherited constructors are called already
  // or you could do this Monster{}
    cout << "\nDefault Constructing Goblin";
  }
};
```
Actor -> Rock
Actor -> Monster -> Goblin
Define render() in Actor

Non-virtual
- If Goblin defines render(), when render() is called, it will override the parents.
- If Goblin is casted to another class, corresponding class function will be called.
Virtual
- Actor render a virtual function (function can be overriden in derived)
- Monster render virtual override (override is for compiler safety, redundant)
- Goblin render virtual override
- Regardless of type of pointer Goblin render will be called for Goblin object

Public is accessible everywhere, inherited as Public
Protected is accessible in class and derived classes, inherited as Protected
Private is accessible in class, does not get inherited

Public inheritance: Derived class inherit public as public, protected as protected, not private
Protected inheritance: Derived class inherits public and protected as protected
Private: Derived class inherits public and protected as private

**Prevent Inheritance**
```cpp
class Demon : final {};

// Combining final with a base class
class Vampire final : public Character {};
```

**Extending Inherited Function**
```cpp
class Goblin : public Monster {
public:
  void Attack(){
    Monster::Attack();
    cout << "\n\nand now some Goblin things";
  }
};

# References