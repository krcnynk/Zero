Status: **Editing**

Tags: [[Python]]

# Class

#### Basis Structure
```Python
class MyClass:
    def __init__(self, value):
        self.value = value  # Attribute

    def display_value(self):
        print(f"The value is {self.value}")  # Method
```

The reason we need `self.` is foo.meth(arg) == C.meth(foo, arg) 
#### Magic Methods
``` Python
class MyClass:
    def __init__(self, value):
        self.value = value

    def __str__(self):
        return f"MyClass with value {self.value}"

    def __repr__(self):
        return f"MyClass({self.value})"

    def __len__(self):
        return len(str(self.value))

obj = MyClass(10)
print(str(obj))  # Output: MyClass with value 10
print(repr(obj))  # Output: MyClass(10)
print(len(obj))   # Output: 2 (length of the string "10")

```

#### Inheritance
``` Python
class Base:
    def __init__(self, value):
        self.value = value

    def display_value(self):
        print(f"Value: {self.value}")

class Derived(Base):
    def __init__(self, value, extra):
        super().__init__(value)
        self.extra = extra

    def display_extra(self):
        print(f"Extra: {self.extra}")

# Create an instance of Derived
obj = Derived(10, "Extra Info")
obj.display_value()  # Output: Value: 10
obj.display_extra()  # Output: Extra: Extra Info

```

#### Encapsulation
```Python
class MyClass:
    def __init__(self):
        self._protected = "Protected"
        self.__private = "Private"

    def get_private(self):
        return self.__private

obj = MyClass()
print(obj._protected)   # Accessible
print(obj.__private)    # Raises AttributeError
print(obj.get_private())  # Output: Private

```

#### Class and Static Method
```Python
class MyClass:
    class_variable = "Class Variable"

    @classmethod
    def get_class_variable(cls):
        return cls.class_variable

	@staticmethod 
	def static_method():
		return cls.class_variable
		print("Static method called")
		
print(MyClass.get_class_variable())  # Output: Class Variable
MyClass.static_method() # Output: Static method called
```

#### **Abstraction**

Blueprint for other classes

```Python
from abc import ABC, abstractmethod

class AbstractShape(ABC):
    @abstractmethod
    def area(self):
        pass

class Circle(AbstractShape):
    def __init__(self, radius):
        self.radius = radius

    def area(self):
        return 3.14 * self.radius ** 2

circle = Circle(5)
print(circle.area())  # Output: 78.5

```
# References