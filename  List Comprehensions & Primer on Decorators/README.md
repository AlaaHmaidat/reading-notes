# List Comprehensions & Primer on Decorators

## What is the basic syntax of Python list comprehension, and how does it differ from using a for loop to create a list? Provide an example of a list comprehension that squares the elements in a given list of integers.

List comprehensions provide a more concise and faster way to create a new list by iterating over a sequence and applying an operation to each element. However, for loops are more flexible and can be used to perform more complex operations

### List comprehensions Syntax:
```python
my_new_list = [ expression for item in list ]
```
As you can see that three ingredients are necessary for a python list comprehension to work.

1. First is the expression we’d like to carry out. expression inside the square brackets.
2. Second is the object that the expression will work on. item inside the square brackets.
3. Finally, we need an iterable list of objects to build our new list from. list inside the square brackets.

### Creating a list with list comprehensions
```python
# construct a basic list using range() and list comprehensions
# syntax
# [ expression for item in list ]
digits = [x**2 for x in range(10)]

print(digits) # output: [0, 1, 4, 9, 16, 25, 36, 49, 64, 81]
```

### Comparing list creation methods in Python
```python
# create a list using a for loop
squares = []

for x in range(10):
    # raise x to the power of 2
    squares.append(x**2)

print(squares) # output: [0, 1, 4, 9, 16, 25, 36, 49, 64, 81]
```
### *Resources:*
[List Comprehensions](https://www.pythonforbeginners.com/basics/list-comprehensions-in-python)

## What is a decorator in Python?
By definition, a decorator is a function that takes another function and extends the behavior of the latter function without explicitly modifying it.


## Explain the concept of decorators in Python. How do they work, and what are some common use cases for them? Provide an example of a simple decorator function from the reading.
A decorator is a function that takes another function and extends the behavior of the latter function without explicitly modifying it. Decorators provide a way to modify the behavior of a function or class without changing the code of the function or class itself.

### Example 1:
```python
def my_decorator(func):
    def wrapper():
        print("Something is happening before the function is called.")
        func()
        print("Something is happening after the function is called.")
    return wrapper

def say_whee():
    print("Whee!")

say_whee = my_decorator(say_whee)
```
In this example: 
1. We define a decorator function my_decorator that takes a function as an argument and returns a *new function* wrapper that adds some behavior before and after the original function is called.

2. We then decorate the say_whee function with @my_decorator, which applies the my_decorator function to the say_whee function.

When we call say_whee, the my_decorator function modifies its behavior by adding some output before and after the original say_whee function is called:

```python
print(say_whee())
# output:
# Something is happening before the function is called.
# Whee!
# Something is happening after the function is called.
```
### Code tracking:
[Example 1](https://drive.google.com/file/d/1uB1tpjw9VNRBcqaTaXA4sdYWSkdrWCe3/view?usp=share_link)

### Example 2:
```python
from datetime import datetime

def not_during_the_night(func):
    def wrapper():
        if 7 <= datetime.now().hour < 22:
            func()
        else:
            pass  # Hush, the neighbors are asleep
    return wrapper

def say_whee():
    print("Whee!")

say_whee = not_during_the_night(say_whee)
print(say_whee())
```
If you try to call say_whee() after bedtime, nothing will happen.(decorator only allows the say_whee function to be called between 7am and 10pm).

### Decorators can be used for a wide range of purposes, such as logging, caching, and authentication. Some common use cases for decorators in Python include:

1. Logging: Decorators can be used to log function calls and their arguments, making it easier to debug problems in your code.
2. Caching: Decorators can be used to cache the results of expensive computations so that they can be reused later without recomputing.
3. Timing: Decorators can be used to time how long it takes for a function to execute, which can be helpful for optimizing code.
4. Authentication: Decorators can be used to authenticate users before allowing them to access certain functions or resources.

Decorators can serve to shorten code, speed up code, and completely change the way that code acts in Python

### *Resources:*
[Primer on Decorators](https://realpython.com/primer-on-python-decorators/)

## Things I want to know more about

Debugging with PySnooper

### *Resources:*
[Debugging with PySnooper](https://www.pythonpodcast.com/pysnooper-python-debugging-episode-241/)
