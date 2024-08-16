Status: **Editing**

Tags: [[C++]]

# call stack

The call stack is a stack data structure that follows the Last In, First Out (LIFO) principle. When a function is called, its execution context (which includes local variables, return address, and other state information) is pushed onto the stack. When the function completes, its context is popped from the stack, and control is returned to the function that called it.

 **Stack Frames:** Each function call creates a stack frame (or activation record) on the call stack. A stack frame contains:
    - The return address (where to return after the function call completes).
    - Parameters passed to the function.
    - Local variables.
    - Saved registers.
-**Stack Pointer (SP):** A register that points to the top of the stack.
    
 **Base Pointer (BP) or Frame Pointer (FP):** A register that points to the base of the current stack frame (does not change during the function execution).
# References