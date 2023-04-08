# FileIO & Exceptions
File IO and Exceptions are important concepts in Python programming for handling input/output operations and handling errors in the code.

File IO:
Python provides a built-in module called open() for reading and writing files. It takes two arguments, the file name and the mode in which the file is opened. The mode can be 'r' for reading, 'w' for writing, 'a' for appending, and 'x' for creating a new file. Here's an example of how to open and read a file:

```javascript
file = open('example.txt', 'r')
content = file.read()
print(content)
file.close()
```

## The purpose of the ‘with’ statement when opening a file in Python, and how does it help manage resources while reading and writing files
In Python, with statement is used in exception handling to make the code cleaner and much more readable
and its way to ensure that a file is closed properly after it has been used for input/output operations

```javascript
with open('example.txt', 'r') as file:
    content = file.read()
    print(content)
```
## The difference between the ‘read()’ and ‘readline()’ methods for file objects in Python. And examples of when to use each method

### read()

1.Returns the read bytes in the form of a string.
2.Reads n bytes; if n is not specified, then reads the entire file.

```javascript
with open('file.txt', 'r') as file:
    data = file.read()  # read the entire content of the file
    print(data)
```
### readline():

Reads a line of the file and returns it in the form of a string.
For specified n, reads at most n bytes from the current line.
readline() function does not read more than one line at a time; even if n exceeds the length of the line, it will still only read one line at a time.

```javascript
with open('file.txt', 'r') as file:
    line = file.readline()  # read the first line of the file
    print(line)
```
You can also use a loop to read all the lines of the file using readline() method:

```javascript
with open('file.txt', 'r') as file:
    line = file.readline()
    while line:
        print(line)
        line = file.readline()
```

## The concept of exception handling in Python. How can the ‘try’, ‘except’, and ‘finally’ blocks be used to handle exceptions and ensure proper execution of code? Provide a simple example

Python also provides a way to handle errors or exceptions that may occur during the execution of the code. This helps to make the code more robust and less prone to unexpected errors

```javascript
try:
    # some code that may raise an exception
except ExceptionType:
    # code to handle the exception
finally:
    # code to be executed regardless of whether an exception was raised or not
``` 
The code inside the try block is executed, and if an error occurs, it is caught by the appropriate except block. The except block can catch specific errors and handle them in a specific way.

## Things I want to know more about