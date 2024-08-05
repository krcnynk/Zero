Status: **Editing**

Tags: [[Python]]

# Underscore

#### Ignoring values
```Python
## ignoring a value
a, _, b = (1, 2, 3) # a = 1, b = 3
print(a, b)

## ignoring multiple values
## *(variable) used to assign multiple value to a variable as list while unpacking
## it's called "Extended Unpacking", only available in Python 3.x
a, *_, b = (7, 6, 5, 4, 3, 2, 1)
print(a, b)

for _ in range(x):
```

#### Separating Digits

```Python
## different number systems
## you can also check whether they are correct or not by coverting them into integer using "int" method
million = 1_000_000
binary = 0b_0010
octa = 0o_64
hexa = 0x_23_ab

print(million)
print(binary)
print(octa)
print(hexa)

```

#### Internal Use Only
```Python
## filename:- my_functions.py
def func():
    return "datacamp"
def _private_func():
    return 7
    
>>> _private_func() # Will cause name error
>>> my_functions._private_func()
```

#### Python Keyword Hack
```Python
>>> def function(class):
  File "<stdin>", line 1
    def function(class):
                 ^
SyntaxError: invalid syntax
>>> def function(class_):
...     pass
...
>>>

```

#### Name Mangling

``` Python
class Sample():
    def __init__(self):
        self.a = 1
        self._b = 2
        self.__c = 3
obj1 = Sample()
dir(obj1)

# Will return all attributes of class object
#'a' and _Sample__c
```

#### "magic" objects or attributes that live in user-controlled namespaces_

```
['_Animal__c',
 '__class__',
 '__delattr__',
 '__dict__',
 '__dir__',
 '__doc__',
 '__eq__',
 '__format__',
 '__ge__',
 '__getattribute__',
 '__gt__',
 '__hash__',
 '__init__',
 '__init_subclass__',
 '__le__',
 '__lt__',
 '__module__',
 '__ne__',
 '__new__',
 '__reduce__',
 '__reduce_ex__',
 '__repr__',
 '__setattr__',
 '__sizeof__',
 '__str__',
 '__subclasshook__',
 '__weakref__',
 '_b',
 'a']

```
# References