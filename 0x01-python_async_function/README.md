# Python Async Function

This project contains a series of tasks that demonstrate the basics of asynchronous programming in Python using `asyncio`.

## Task 0: The Basics of Async

**Objective:**  
Write an asynchronous coroutine that takes in an integer argument (max_delay, with a default value of 10) named `wait_random` that waits for a random delay between 0 and max_delay (inclusive) seconds and eventually returns it.


## 0-basic_async_syntax.py

import asyncio
import random

async def wait_random(max_delay: int = 10) -> float:
    delay = random.uniform(0, max_delay)
    await asyncio.sleep(delay)
    return delay
Task 1: Let's Execute Multiple Coroutines at the Same Time with async
Objective:
Write an async routine called wait_n that takes in 2 int arguments (n and max_delay). You will spawn wait_random n times with the specified max_delay.

##  1-concurrent_coroutines.py

import asyncio
from typing import List
from 0-basic_async_syntax import wait_random

async def wait_n(n: int, max_delay: int) -> List[float]:
    delays = [await wait_random(max_delay) for _ in range(n)]
    return sorted(delays)
Task 2: Measure the Runtime
Objective:
Create a measure_time function with integers n and max_delay as arguments that measures the total execution time for wait_n(n, max_delay), and returns total_time / n.

## 2-measure_runtime.py

import asyncio
import time
from 1-concurrent_coroutines import wait_n

def measure_time(n: int, max_delay: int) -> float:
    start_time = time.time()
    asyncio.run(wait_n(n, max_delay))
    end_time = time.time()
    total_time = end_time - start_time
    return total_time / n
Task 3: Tasks
Objective:
Write a function task_wait_random that takes an integer max_delay and returns an asyncio.Task.

## 3-tasks.py

import asyncio
from 0-basic_async_syntax import wait_random

def task_wait_random(max_delay: int) -> asyncio.Task:
    return asyncio.create_task(wait_random(max_delay))
Task 4: Tasks
Objective:
Alter the code from wait_n into a new function task_wait_n. The code is nearly identical to wait_n except task_wait_random is being called.

## 4-tasks.py

import asyncio
from typing import List
from 3-tasks import task_wait_random

async def task_wait_n(n: int, max_delay: int) -> List[float]:
    tasks = [task_wait_random(max_delay) for _ in range(n)]
    delays = await asyncio.gather(*tasks)
    return sorted(delays)
