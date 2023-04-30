# Ten Thousand & Python Scope

##  The concept of variable scope in Python and describe the difference between local and global scope

*Global scope* — Global scope contains all of the things defined outside of all code blocks. A code block simply consists of a piece of Python program text that can be executed as a unit. such as a module, a class definition or a function body. A global variable has global scope. A global variable is accessible from anywhere in the code.

### Example of Global Variable

```python
# global variable
a = 15
b = 10

# function to perform addition
def add():
    # code block
	c = a + b
	print(c)

# calling a function
add()
```
*Local Scope* — Local scope contains things defined inside code blocks. A local variable has local scope. A local variable is only accessible where it’s declared.

### Example of Local Variable

```python
def add():
    # code block
    # Local variable
    a = 4
    b = 5
    c = a + b
	print(c)

# calling a function
add()
```

### *Resources:*
[Python Scope](https://realpython.com/python-scope-legb-rule/)

## How do the global and nonlocal keywords work in Python, and in what situations might you use them?
Python provides two keywords that allow you to modify the content of global and nonlocal names. These two keywords are *global* and *nonlocal* 

What is the difference between nonlocal and global? The main difference is that Global is used to access and modify global variables from within a function, while nonlocal is used to access and modify variables from the nearest enclosing scope that is not global

1. global 
A global keyword is a keyword that allows a user to modify a variable outside the current scope. It is used to create global variables in Python from a non-global scope, i.e. inside a function

```python
x = 15

def change():
	# using a global keyword
	global x

	# increment value of a by 5
	x = x + 5
	print("Value of x inside a function :", x)


change()
print("Value of x outside a function :", x)
```
2. nonlocal 
The nonlocal keyword is used to work with variables inside nested functions, where the variable should not belong to the inner function.
((It is used to reference a variable in the nearest scope. ))

Example
Make a function inside a function, which uses the variable x as a non local variable:
```python
def myfunc1():
  x = "John"
  def myfunc2():
    nonlocal x
    x = "hello"
  myfunc2()
  return x

print(myfunc1())# OUTPUT hello
```

Same example as above, but without the nonlocal keyword:
```python
def myfunc1():
  x = "John"
  def myfunc2():
    x = "hello"
  myfunc2()
  return x

print(myfunc1())# OUTPUT John
```

## The purpose and importance of Big O notation in the context of algorithm analysis
Big O Notation is an essential tool in computer science that enables programmers to determine the time complexity of algorithms. By using Big O Notation, programmers can categorize algorithms based on how their time or space requirements change as the input size changes.

### *Resources:*
[Big O notation is simpler than you might think](https://www.youtube.com/watch?v=dNorFNlDbX0)

## Based on the Rolling Dice Example, explain how you would simulate a dice roll using Python. Describe how you would use code to calculate the probability of rolling a specific number (e.g., the probability of rolling a 6) over a large number of trials.

1. Define a function that rolls a six-sided die and returns the result
2. Define a function that counts how many times a 6 is rolled over a given number of iterations
3. Roll the die 'amount' times and count how many times a 6 is rolled

```python
import random

# 1
def roll():
    return random.randint(1, 6)

# 2
def count(amount):
    count_ = 0

    # 3
    for i in range(amount):
        if roll() == 6:
            count_ += 1

    return count_
```
### *Resources:*
[Rolling Dice Examples](https://artofproblemsolving.com/wiki/index.php/Basic_Programming_With_Python#Program_Example_1_3)
## Things I want to know more about
