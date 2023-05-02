# Dunder Methods & Statistics - Probability

### What is the purpose of dunder methods in Python? Provide an example of a commonly used dunder method.
Dunder or magic methods in Python are the methods having two prefix and suffix underscores in the method name and its allow instances of a class to interact with the built-in functions and operators of the language. Dunder here means “Double Under (Underscores)”.As it quickly became tiresome to say under-under-method-under-under Pythonistas adopted the term “dunder methods”, a short form of “double under.”
These are commonly used for operator overloading. 

Few examples for magic methods are:
__init__, __str__, __repr__, __len__ etc.

__init__: This is a special method that is called when a new object is created from a class. It is used to initialize the object's attributes and set its initial state. This method is called with the self parameter, which refers to the object being created.

__str__: This is another special method that is called when the str() function is called on an object, or when the object is used in a context where a string representation is needed (such as in a print statement). It should return a human-readable string representation of the object.

__repr__: This is a special method that is called when the repr() function is called on an object, or when the object is used in a context where a printable representation is needed (such as in a debugger). It should return a string that, when evaluated, would create an object with the same state as the original object.

__len__: This is a special method that is called when the len() function is called on an object. It should return the number of items in the object, if it is a sequence or collection.

### Example:
```python 
class MyClass:
    def __str__(self):
        # Define the string representation of the object
        # ...
        return string_representation

    def __repr__(self):
        # Define the detailed string representation of the object
        # ...
        return detailed_representation

# Create an object of the class
my_object = MyClass()

# Call the __str__ method
string_representation = str(my_object) # output: string_representation

# Call the __repr__ method
detailed_representation = repr(my_object) # output: detailed_representation

```

### *Resources:*
[Dunder Methods](https://dbader.org/blog/python-dunder-methods)

### In the video “AI Guru makes $238,800 with misleading paid course,” what was the main ethical issue raised concerning the use of developers’ work, and how might this have been avoided?

The principal ethical quandary that arises from utilizing the work of developers pertains to the unauthorized usage of their contributions and the failure to acknowledge their authorship. This situation could have been circumvented by duly accrediting the developer for their work and seeking their explicit consent before incorporating it.

### *Resources:*
[Intro to Statistics](https://www.youtube.com/watch?v=MdHtK7CWpCQ) 

[AI Guru makes $238,800 with misleading paid course. doesn’t credit developers](https://www.youtube.com/watch?v=7jmBE4yPrOs) 

### Describe the Python statistics module and give an example of a function within the module that can be used to perform a common statistical operation.

The statistics module provides functions to mathematical statistics of numeric data like (mean,median,mode) 

```python
import statistics

numbers = [1, 3, 5, 7, 9]
mean = statistics.mean(numbers)
print(mean) # output: 5.0

median = statistics.median(numbers)
print(median) # output: 5

std_dev = statistics.stdev(numbers)
print(std_dev) # output: 2.8284271247461903

variance = statistics.variance(numbers)
print(variance) # standard deviation  output: 8.0

numbers = [1, 3, 5, 3, 7, 9, 3]
mode = statistics.mode(numbers)
print(mode) # output: 3
```

### *Resources:*
[Statistics Module](https://docs.python.org/3/library/statistics.html) 
[Statistics - Probability](https://www.dataquest.io/blog/basic-statistics-in-python-probability/)
## Things I want to know more about
