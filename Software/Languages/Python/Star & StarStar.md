Status: **Editing**

Tags: [[Python]]

# Star & StarStar
## Star
#### Positional Argument Collection
```Python
def example_function(a, b, *args):
    print(a, b)
    print(args)
example_function(1, 2, 3, 4, 5)
# Output:
# 1 2
# (3, 4, 5)
```
#### Iterable Unpacking

```Python
a, *middle, c = [1, 2, 3, 4, 5] 
print(a) # Output: 1 
print(middle) # Output: [2, 3, 4] 
print(c) # Output: 5
```

#### Function Call Argument Unpacking
```Python
def add(a, b, c):
    return a + b + c

args = (1, 2, 3)
print(add(*args))  # Output: 6
```

#### Starred Expressions in Lists
```Python
list1 = [1, 2]
list2 = [3, 4]
combined = [*list1, *list2]
print(combined)  # Output: [1, 2, 3, 4]
```

#### Keyword-Only Arguments

```Python
def function(a, b, *, c, d):
    print(a, b, c, d)

function(1, 2, c=3, d=4)  # Output: 1 2 3 4

```
## StarStar

```Python
def print_info(name, **details):
    print(f"Name: {name}")
    for key, value in details.items():
        print(f"{key}: {value}")

print_info("Alice", age=30, city="New York", job="Engineer")

def print_info(name, age, city):
    print(f"Name: {name}")
    print(f"Age: {age}")
    print(f"City: {city}")

info = {"name": "Bob", "age": 25, "city": "Los Angeles"}
print_info(**info)


```
# References