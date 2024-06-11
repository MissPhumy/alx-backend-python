# 0x02. Python - Async Comprehension

## Resources

Read or watch:
- [PEP 530 – Asynchronous Comprehensions](https://www.python.org/dev/peps/pep-0530/)
- [What’s New in Python: Asynchronous Comprehensions / Generators](https://docs.python.org/3/whatsnew/3.6.html#whatsnew36-async-comprehensions)
- [Type-hints for generators](https://docs.python.org/3/library/typing.html#typing.Generator)

## Learning Objectives

By the end of this project, you should be able to explain to anyone, without the help of Google:
- How to write an asynchronous generator
- How to use async comprehensions
- How to type-annotate generators

## Requirements

### General
- Allowed editors: vi, vim, emacs
- All your files will be interpreted/compiled on Ubuntu 18.04 LTS using python3 (version 3.7)
- All your files should end with a new line
- Your code should use the pycodestyle style (version 2.5.x)

## Tasks

### 0. Async Generator

Write a coroutine called `async_generator` that takes no arguments.
- The coroutine will loop 10 times, each time asynchronously waiting 1 second, then yielding a random number between 0 and 10. Use the random module.

### 1. Async Comprehensions

Import `async_generator` from the previous task and then write a coroutine called `async_comprehension` that takes no arguments.
- The coroutine will collect 10 random numbers using an async comprehension over `async_generator`, then return the 10 random numbers.

### 2. Run time for four parallel comprehensions

Import `async_comprehension` from the previous file and write a `measure_runtime` coroutine that will execute `async_comprehension` four times in parallel using `asyncio.gather`.
- `measure_runtime` should measure the total runtime and return it.
- Notice that the total runtime is roughly 10 seconds, explain it to yourself.
