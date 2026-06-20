# BMT - Modern Programming Language

BMT is a modern, expressive programming language designed with clarity and performance in mind. It combines the best features of Python with a unique syntax and is available as interpreters in **Python, JavaScript, Rust, and C++**.

## Features

- **Python-like syntax** - Easy to learn and read
- **Dynamic typing** - Flexible variable handling
- **First-class functions** - Functional programming support
- **Object-oriented** - Classes and inheritance
- **Error handling** - Try/except mechanisms
- **Standard library** - Built-in functions and modules
- **Multi-platform** - Works on Windows, macOS, and Linux
- **Multiple implementations** - Choose your preferred language

## Quick Start

### Example Program

```bmt
<BMT.V.1.0.0:

# Hello World
print("Hello, World!")

# Variables
name = "Robin"
age = 25

# Control Flow
if age >= 18:
    print(f"Hello, {name}! You are an adult.")
else:
    print(f"Hello, {name}! You are a minor.")

# Loops
for i in range(5):
    print(f"Count: {i}")

# Functions
def greet(person):
    return f"Greetings, {person}!"

print(greet("Alice"))

# Lists
fruits = ["apple", "banana", "orange"]
for fruit in fruits:
    print(fruit)

# Classes
class Dog:
    def __init__(self, name):
        self.name = name
    
    def bark(self):
        print(f"{self.name} says: Woof!")

dog = Dog("Rex")
dog.bark()

<endline:50:->
```

## Installation

### Python Interpreter
```bash
python bmt_python_interpreter.py your_program.bmt
```

### JavaScript Interpreter
```bash
node bmt_javascript_interpreter.js your_program.bmt
```

### Rust Interpreter
```bash
cargo run --release -- your_program.bmt
```

### C++ Interpreter
```bash
g++ -o bmt bmt_cpp_interpreter.cpp
./bmt your_program.bmt
```

## Language Syntax

### Basic Structure
```bmt
<BMT.V.1.0.0:
# Your code here
<endline:N:->
```

### Variables
```bmt
name = "John"
age = 30
height = 5.9
is_active = True
```

### Control Flow
```bmt
if condition:
    # do something
elif other_condition:
    # do something else
else:
    # default action

while condition:
    # loop body
    break  # exit loop
    continue  # skip to next iteration

for item in sequence:
    # loop body
```

### Functions
```bmt
def function_name(param1, param2):
    """Optional docstring"""
    return param1 + param2

result = function_name(5, 3)
```

### Classes
```bmt
class MyClass:
    def __init__(self, value):
        self.value = value
    
    def method(self):
        return self.value * 2

obj = MyClass(10)
print(obj.method())
```

### Error Handling
```bmt
try:
    result = 10 / 0
except ZeroDivisionError:
    print("Cannot divide by zero!")
except Exception as e:
    print(f"Error: {e}")
finally:
    print("Cleanup code")
```

## Built-in Functions

- `print()` - Output to console
- `len()` - Get length
- `range()` - Create number sequence
- `type()` - Get type of object
- `int()`, `float()`, `str()`, `bool()` - Type conversion
- `list()`, `dict()`, `set()`, `tuple()` - Collection creation
- `sum()`, `min()`, `max()`, `abs()` - Math functions
- `sorted()`, `reversed()` - Sorting functions
- `enumerate()`, `zip()` - Iteration helpers

## Module System

```bmt
import math
import os
from collections import Counter

result = math.sqrt(16)
cwd = os.getcwd()
```

## Contributing

Contributions are welcome! Please fork the repository and submit pull requests.

## License

MIT License - see LICENSE file for details

## Author

Created with ❤️ by robblossjbl-wq

---

**Version**: 1.0.0
**Status**: Active Development
