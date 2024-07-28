```python
def add(a, b): 
return a + b 
result = add(3, 5) 
print(result)
```

Tokenize (written in C)
	def, add, (, a, ,, b, ), :, return, a, +, b, result, =, add, (, 3, ,, 5, ), print, (, result, )

Abstract syntax tree (written in C)
	FunctionDefinition
	  └── Name: add
	  └── Parameters
	      ├── a
	      └── b
	  └── Body
	      └── Return
	          └── Addition
	              ├── a
	              └── b

Python interpreter (written in C) compiles the AST into bytecode
	LOAD_FAST 0 (a)
	LOAD_FAST 1 (b)
	BINARY_ADD
	STORE_FAST 2 (result)

Bytecode (non-interactive case is .pyc file binary format of bytecode) runs by C -> assembly code (platform dependent) -> OS (written in C)->  several layers virtualization -> machine code (binary, platform dependent) -> processor x86 microcode

[microcode](https://electronics.stackexchange.com/posts/1914/timeline)

Micro-code is another level of abstraction beyond machine code. The actual CPU is running microcode, and a translation engine converts machine code into microcode on the fly. This is done for a variety of reasons, including faster, smaller processors, easier to create a complex processor with less debugging, and for backwards compatibility. For instance, the x86 instruction set contains some string processing instructions that are rarely used. However, to remain backwards compatible, they must still be available in modern x86 processors. Rather than hardwiring an execution path for these instructions, they are converted into microcode and executed. This saves silicon, while still remaining backwards compatible.