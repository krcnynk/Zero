Status: **Editing**

Tags: [[Python]]

# Code_to_Execution

- **Lexical Analysis**:
    - The lexer reads the source code character by character and groups them into tokens.
    - Example: The line `print("Hello, World!")` would be tokenized into `PRINT`, `LPAREN`, `STRING`, `RPAREN`.
- **Parsing**:
    - The parser takes the tokens and arranges them into a parse tree based on Python's syntax rules.
    - Example: The tokens from the previous step would be parsed into a tree structure representing a function call.
- **AST Compilation**:
    - The AST represents the program's structure and is transformed into bytecode.
    - The bytecode is a set of instructions that is easier for the PVM to execute.
- **Bytecode Interpretation**:
    - The PVM interprets the bytecode instructions and executes them.
    - The PVM includes a stack-based machine, and the bytecode instructions manipulate the stack to perform operations.

```
LOAD_FAST 0 (a)
LOAD_FAST 1 (b)
BINARY_ADD
RETURN_VALUE
```

- The PVM loads the bytecode.
- The PVM executes the bytecode instructions.
    - `LOAD_FAST 0 (a)`: Load the first argument onto the stack.
    - `LOAD_FAST 1 (b)`: Load the second argument onto the stack.
    - `BINARY_ADD`: Pop two values from the stack, add them, and push the result back onto the stack.
    - `RETURN_VALUE`: Return the value on the top of the stack.