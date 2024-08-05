Status: **Editing**

Tags: [[Python]]
# Mutability vs Immutability

**Immutable data types** are those whose values cannot be changed after they are created. Any operation that alters the value of an immutable object will create a new object rather than modifying the existing one.

###### int, float, complex, str, tuple, frozenset, bytes, bool

**Mutable data types** are those whose values can be changed after they are created. These types allow for in-place modification, meaning that operations can change the original object without creating a new one.

- **Performance**:
    - **Immutable**: Operations on immutable types often involve creating new objects, which can be less efficient for large data. However, since their value cannot change, immutable objects can be optimized by Python, resulting in some performance benefits.
    - **Mutable**: Mutable objects can be modified in place, which can be more memory and time efficient when performing many updates.
- **Safety**:
    - **Immutable**: Immutable objects are inherently thread-safe because their state cannot change. This makes them useful in concurrent programming.
    - **Mutable**: Mutable objects require careful management in multi-threaded applications to avoid issues such as race conditions.
- **Hashability**:
    - **Immutable**: Immutable objects are hashable and can be used as keys in dictionaries and elements in sets.
    - **Mutable**: Mutable objects are generally not hashable and cannot be used as dictionary keys or set elements unless explicitly designed to be hashable.
- **Copying**:
    - **Immutable**: Assigning an immutable object to a new variable creates a reference to the same object. Since the object cannot change, this is usually safe.
    - **Mutable**: Assigning a mutable object to a new variable also creates a reference to the same object. Changes made through any reference will affect the original object, which can lead to unintended side effects.

###### list, dict, set, bytearray, user-defined class
