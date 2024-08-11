Status: **Editing**

Tags:[[C++]]

# mutable

This keyword allows you to mark certain members of a class as modifiable while the object itself is considered immutable.

- **`mutable`** allows modification of a class member even in `const` member functions.
- **`const` member functions** guarantee that the object’s logical state does not change, but mutable members can be altered.
- **Use cases** include internal caching or updating of state that does not affect the logical state of the object.

# References