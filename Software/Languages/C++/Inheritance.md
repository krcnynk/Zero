Status: **Editing**

Tags:[[C++]]

# Inheritance
**Inherited Constructor**
```cpp
class Goblin : public Monster {
public:
  Goblin() : Monster{}{ // all inherited constructors are called already
  // or you could do this Monster{}
    cout << "\nDefault Constructing Goblin";
  }
};
```

```cpp
class Goblin {
public:
  void Render(){} // HERE DUPLICATE
  void Move(){}
  void Attack(){}
  void DropLoot(){}
  void Enrage(){}
};
```

```cpp
class Rock {
public:
  void Render(){} // HERE DUPLICATE
};
```
Make an Actor class (base,parent class) and create Render() there, Rock and Goblin inherits from Actor

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