# Advanced Python

## Concepts

This project aims to deepen your understanding of advanced Python features, specifically focusing on type annotations, duck typing, and code validation using mypy.

## Resources

To complete this project, refer to the following resources:
- [Python 3 typing documentation](https://docs.python.org/3/library/typing.html)
- [MyPy cheat sheet](https://mypy.readthedocs.io/en/stable/cheat_sheet_py3.html)

## Learning Objectives

By the end of this project, you should be able to explain the following concepts clearly:

### Type Annotations in Python 3
- Type annotations provide a way to specify the expected data types of variables, function parameters, and return values.
- Example:
  ```python
  def greeting(name: str) -> str:
      return 'Hello ' + name
Using Type Annotations to Specify Function Signatures and Variable Types
Type annotations can improve code readability and help catch type-related errors during development.
Example:
python
Copy code
from typing import List, Tuple

def process_data(data: List[int]) -> Tuple[int, int]:
    return (min(data), max(data))
Duck Typing
Duck typing is a concept where the type or class of an object is determined by its behavior (methods and properties) rather than its explicit type.
Example:
python
Copy code
class Duck:
    def quack(self):
        print("Quack!")

class Person:
    def quack(self):
        print("I'm quacking like a duck!")

def in_the_forest(duck):
    duck.quack()

in_the_forest(Duck())   # Outputs: Quack!
in_the_forest(Person()) # Outputs: I'm quacking like a duck!
Validating Code with mypy
mypy is a static type checker for Python. It helps catch type errors by analyzing the code before runtime.
Installation:
sh
Copy code
pip install mypy
Usage:
sh
Copy code
mypy your_script.py
Requirements
General
Editors: Allowed editors include vi, vim, and emacs.
Python Version: All code will be interpreted/compiled on Ubuntu 18.04 LTS using Python 3.7.
File Endings: All files should end with a new line.
Shebang Line: The first line of all your files should be exactly #!/usr/bin/env python3.
README.md: A README.md file at the root of the project folder is mandatory.
Code Style: Your code should follow the pycodestyle style (version 2.5).
Executable Files: All your files must be executable.
File Length: The length of your files will be tested using wc.
Documentation:
All modules should have documentation.
All classes should have documentation.
All functions (inside and outside of classes) should have documentation.
Documentation should be a complete sentence explaining the purpose of the module, class, or method.
Example Documentation
Module Documentation:

python
Copy code
"""
This module provides functions for processing data.
"""
Class Documentation:

python
Copy code
class DataProcessor:
    """
    A class used to process data.

    ...

    Methods
    -------
    process(data):
        Processes the input data.
    """
Function Documentation:

python
Copy code
def process(data: List[int]) -> Tuple[int, int]:
    """
    Processes the input data and returns a tuple containing the minimum and maximum values.

    Parameters
    ----------
    data : List[int]
        A list of integers to be processed.

    Returns
    -------
    Tuple[int, int]
        A tuple containing the minimum and maximum values.
    """
    return (min(data), max(data))
