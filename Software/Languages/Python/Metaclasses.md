Status: **Editing**

Tags: [[Python]]

# Metaclasses

In Python, classes themselves are instances of a metaclass. By default, the metaclass for all new-style classes (i.e., classes that inherit from `object`) is `type`.
When you define a class in Python, Python uses the `type` metaclass to create that class. This process involves calling `type` with three arguments:

- The name of the class
- The tuple of base classes
- A dictionary of attributes and methods

```Python
class myMeta(type):
    def __new__(cls, name, bases, dct):
        print(f"Creating class {name}")
        return super().__new__(cls, name, bases, dct)

    def __init__(cls, name, bases, dct):
        print(f"Initializing class {name}")
        super().__init__(name, bases, dct)

# Using the metaclass to create a class
class MyClass(metaclass=myMeta):
    pass

# Output:
# Creating class MyClass
# Initializing class MyClass
#ENFORCING CLASS
class AttributeEnforcer(type):
    def __init__(cls, name, bases, dct):
        if 'required_attr' not in dct:
            raise TypeError(f"Class {name} must have 'required_attr'")
        super().__init__(name, bases, dct)

class ValidClass(metaclass=AttributeEnforcer):
    required_attr = 42

class InvalidClass(metaclass=AttributeEnforcer):
    pass  # This will raise TypeError
#AUTOREGISTERING CLASS
class RegistryMeta(type):
    registry = {}

    def __new__(cls, name, bases, dct):
        new_class = super().__new__(cls, name, bases, dct)
        cls.registry[name] = new_class
        return new_class

class BaseClass(metaclass=RegistryMeta):
    pass

class FirstClass(BaseClass):
    pass

class SecondClass(BaseClass):
    pass

print(RegistryMeta.registry)
# MODIFY METHOD DEFINIONS
class MethodAdderMeta(type):
    def __new__(cls, name, bases, dct):
        dct['added_method'] = lambda self: "This method was added by the metaclass."
        return super().__new__(cls, name, bases, dct)

class MyClass(metaclass=MethodAdderMeta):
    pass

obj = MyClass()
print(obj.added_method())
#SINGLETON CLASSES
class SingletonMeta(type):
    _instances = {}

    def __call__(cls, *args, **kwargs):
        if cls not in cls._instances:
            cls._instances[cls] = super().__call__(*args, **kwargs)
        return cls._instances[cls]

class SingletonClass(metaclass=SingletonMeta):
    pass

# Testing Singleton behavior
instance1 = SingletonClass()
instance2 = SingletonClass()

print(instance1 is instance2)  # Output: True


```
# References