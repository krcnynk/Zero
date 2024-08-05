Status: **Done**

Tags: [[Python]]
# Lambda

A lambda function in Python is a small anonymous function defined using the `lambda` keyword. Lambda functions can have any number of arguments but only one expression. The expression is evaluated and returned. Lambda functions are often used for short, simple operations that are not complex enough to require a full function definition. They are particularly useful for short operations and when used in conjunction with higher-order functions like `map`, `filter`, and `sorted`.

## Syntax

```Python
lambda arguments: expression
```

- **`arguments`**: The parameters that the function takes.
- **`expression`**: The single expression that is evaluated and returned.

### Example

```Python
add_10 = lambda x: x + 10 
print(add_10(5)) # Output: 15
```

## Uses

- **As a quick throwaway function:** If you need a simple function for a short period of time, using a lambda can make your code cleaner and more concise.

### Example

```Python
list_of_numbers = [1, 2, 3, 4, 5] 
doubled = map(lambda x: x * 2, list_of_numbers) 
print(list(doubled)) # Output: [2, 4, 6, 8, 10]
```

- **In sorting and filtering:** Lambda functions are often used as key functions in sorting and filtering operations.

### Example

```Python
points = [(1, 2), (3, 1), (5, -1)] 
points_sorted_by_y = sorted(points, key=lambda point: point[1]) print(points_sorted_by_y) # Output: [(5, -1), (3, 1), (1, 2)]
```

- **With higher-order functions:** Functions that take other functions as arguments or return them as results can benefit from lambda functions.

### Example

```Python
def make_incrementor(n): 
	return lambda x: x + n 
	
inc = make_incrementor(5) 
print(inc(10)) # Output: 15
```

## Limitations

- **Single expression**: Lambda functions are limited to a single expression. If you need more complex logic, you should define a full function using `def`.
- **Readability**: Overuse of lambda functions can sometimes make code harder to read and understand.
# References
