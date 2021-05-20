---
date: 2021-03-13T17:20
tags:
  - python/libraries/asyncio
  - python/exploration
---

# Asyncio
Asyncio offers primitives to run concurrent code using **async/await** keywords like JS/TS.

## High-level APIs
#### run
Starts a new routine passed as argument. Thought as a point of entrance for the program (*only once a time inside a thread).

```python
async def my_routine():
    await asyncio.sleep(1)
    print('Done.')
        
asyncio.run(my_routine())
```

### Task
#### create_task
Crates a task executing routine passed as argument.
```python
async def my_routine();
    ...

task = asyncio.create_task(my_routine(), name="Name of the task")
```

#### sleep
Blocks a task for a specific amount of time. Result parameter allows to returns a value after sleep ends.

```python
async def my_routine(msg):
    result = await asyncio.sleep(5, ' world')
    assert msg + result == 'hello world', 'No hello world'

asyncio.run(my_ruotine('hello'))
```

#### gather
Used to run concurrently more awaitable objects (routine for example will be scheduled as tasks).
The return_exceptions flag parameter can be used to include Exception raised during tasks directly in the resulting list containing results of the tasks.

```python
async def say_after(delay, what):
    for i in range(5):
        await asyncio.sleep(delay)
        print(what, end='')
    return "Done."


async def main():
    result = await asyncio.gather(
        say_after(3, '3-'),
        say_after(1, '1-'),
        say_after(2, '2-'),
    )

    print(result)

asyncio.run(main())
# Resulting in:
# 1-2-1-3-1-2-1-1-3-2-2-3-2-3-3-['Done.', 'Done.', 'Done.']
```

#### wait_for
Waits for an awaitable. It is possibile to specify a max wait time through timeout parameter.

```python
async def say_after(delay, what):
    await asyncio.sleep(delay)
    return "Done."


async def main():
    try:
        result = await asyncio.wait_for(say_after(5, 'hello'), timeout=2)
        print(result)
    except asyncio.TimeoutError:
        print('Timeout exceed')

asyncio.run(main())
```

#### shield
Protects a routine from cancellation.

```python
res = await shield(my_routine())
```

#### wait
Waits like wait_for but the main differnces are:

* if timeout exceed the task will not be cancelled but instead will be returned as pending
* returns two value (done, pending)

```python
done, pending = await asyncio.wait({task}, return_when=FIRST_COMPLETED, timeout=10)
done, pending = await asyncio.wait({task}, return_when=FIRST_EXCEPTION, timeout=10)
done, pending = await asyncio.wait({task}, return_when=ALL_COMPLETED, timeout=10)
```

#### current_task and all_tasks
Self explanatory.

#### Task
Task class, not thread-safe. Main methods:

* cancel() → cancel task
* cancelled() → return True if task is cancelled
* done() → return True if task is done
* result() → return result of the task (Exceptions in other cases)
* exception() → return the exception of the task 
* add_one_callback(...) → callable called when task is done
* remove_done_callback(...) → self explanatory
* get_stack()/set_stack()/print_task()
* get_name()/set_name()
* get_coro() → get routine assigned to the task

#### to_thread
Runs a routine inside another OS thread.

*Warnings:* this function does not want brackets in routine.
```python
def a_routine():
    time.sleep(1)
    print("Done.")
asyncio.to_thread(a_routine, args)
```

#### run_coroutine_threadsafe
Runs a routine inside another OS thread given a loop. Thread safe.

```python
coro = asyncio.sleep(1, result=3)
future = asyncio.run_coroutine_threadsafe(coro, loop)
print(future.result(timeout))
```

#### as_completed
Utility to run awaitable objs as iterator in a for loop.

```python
for routine in as_completed(my_routines):
    first_result = await routine
```
