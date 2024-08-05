Status: **Editing**

Tags: [[Python]]
# Cython

Cython is a programming language that makes writing C extensions for Python as easy as Python itself. It is a **superset** of Python, meaning that any valid Python code is also valid Cython code. Cython is used to achieve C-like performance with code that is written mostly in Python, by allowing the inclusion of C data types and functions.

**Performance Improvement**:

- By converting Python code to C, Cython can significantly improve the performance of CPU-bound and memory-bound operations.
- Cython code is compiled into C, which is then compiled into a shared library or an executable.
- 
**C Integration**:

- Cython allows the direct calling of C functions and the use of C data types, which can result in much faster execution compared to pure Python code.
- This integration makes it easier to interface Python code with existing C libraries.

**Static Typing**:

- Cython supports optional static typing. By declaring variables with C types, you can achieve significant performance gains. ```cdef int a = 0```


```python
from setuptools import setup 
from Cython.Build import 
cythonize setup( ext_modules = cythonize("example.pyx")) # python code
```
python setup.py build_ext --inplace
*python code becomes c code
```python
from example import fibonacci
print(fibonacci(10))
```