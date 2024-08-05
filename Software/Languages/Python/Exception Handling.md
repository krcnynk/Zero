Status: **Done**

Tags: [[Python]]
# Exception Handling

Exception handling in Python is a mechanism to gracefully handle errors that occur during the execution of a program. It allows you to manage and respond to unexpected situations without crashing the program.

## Basic Concepts

1. **Exception:** An exception is an error that occurs during the execution of a program. When an exception occurs, the normal flow of the program is disrupted, and Python looks for a way to handle it.
2. **Try Block:** The `try` block contains the code that might throw an exception. If no exception occurs, the code within the `try` block runs smoothly.
3. **Except Block:** The `except` block contains the code that runs if an exception occurs in the `try` block. You can specify the type of exception to catch or use a general exception handler.
4. **Else Block:** The `else` block contains code that runs if no exceptions are raised in the `try` block. It's optional.
5. **Finally Block:** The `finally` block contains code that runs no matter what—whether an exception was raised or not. It’s typically used for cleanup actions like closing files or releasing resources.

## Syntax

```Python
class MyCustomError(Exception):
    def __init__(self, message):
        self.message = message
        super().__init__(message)

# Raising and catching a custom exception
try:
    raise MyCustomError("This is a custom error message.")
except MyCustomError as e:
    print(e)
except ZeroDivisionError:
except Exception as e:
    # Code that runs if the exception occurs
else:
    # Code that runs if no exception occurs
finally:
    # Code that runs no matter what
```
# References
