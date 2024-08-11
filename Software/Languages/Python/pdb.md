Status: **Editing**

Tags: [[Python]]

# pdb

```
# Set a breakpoint
import pdb; pdb.set_trace()

# Common pdb commands
# Show the current location in the code
l

# Execute the next line of code (step over)
n

# Step into functions called at the current line
s

# Continue execution until the next breakpoint
c

# Set a breakpoint at a specified line number or function
b 42
b my_function

# Print the value of an expression or variable
p variable_name
p some_variable + 5

# Quit the debugger and terminate the program
q

# Continue execution until the current function returns
r

# Display help for pdb commands
h

```



# References