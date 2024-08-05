Status: **Editing**

Tags:[[Python]]

# Variable Arguments

**Variable Positional Arguments (`*args`)**:

- This allows you to pass a variable number of positional arguments to a function. Inside the function, these arguments are accessible as a tuple.
- The `*args` syntax is used to capture any number of positional arguments.


**Variable Keyword Arguments (`**kwargs`)**:

- This allows you to pass a variable number of keyword arguments (i.e., named arguments) to a function. Inside the function, these arguments are accessible as a dictionary.
- The `**kwargs` syntax is used to capture any number of keyword arguments.

```
def process_positional_args(*args): for arg in args: print(arg) process_positional_args(1, 2, 3, 4, 5)

```
# References