# Object-oriented programming (OOP) in Python
Object-oriented programming (OOP) in Python is about creating objects from classes. Objects represent real-world entities with properties (data) and behaviors (functions). OOP helps organize code by bundling data and functions into objects.

## OOPs Concepts in Python

1. Class
2. Objects
3. Polymorphism
4. Encapsulation
5. Inheritance
6. Data Abstraction


## Python Class 
A class is a collection of objects. A class contains the blueprints or the prototype from which the objects are being created. It is a logical entity that contains some attributes and methods. 

    - Classes are created by keyword class.
    - Attributes are the variables that belong to a class.
    - Attributes are always public and can be accessed using the dot (.) operator. **Eg.: Myclass.Myattribute**


## Example 1:
```python
class ClassName:
   # Statement-1
   .
   .
   .
   # Statement-N
```

## Python Objects
Objects are entities with state and behavior. They can be real-world items like a mouse or a keyboard, or even numbers and strings. Objects store data and perform actions. They're everywhere in programming!


## Example 2:
```python
# Define a class called Person
class Person:
    def __init__(self, name, age):
        # Initialize attributes name and age
        self.name = name
        self.age = age

# Creating an instance (object) of the Person class
person1 = Person("Alice", 25)

# Accessing the attributes using the dot operator
print(person1.name)  # Output: Alice
print(person1.age)   # Output: 25
```


## Example 3:
```python
# Define a class called Person
class Person:
    def __init__(self, name, age):
        self.name = name  # state
        self.age = age    # state

    def greet(self):
        print(f"Hello, my name is {self.name}. I am {self.age} years old.")  # behavior

# Create an instance (object) of the Person class
person1 = Person("Alice", 25)

# Access the state (attributes) of the object
print(person1.name)  # Output: Alice
print(person1.age)   # Output: 25

# Invoke the behavior (method) of the object
person1.greet()      # Output: Hello, my name is Alice. I am 25 years old.
```

## The Python **self** 

When defining methods in a class, the first parameter is typically named self. This parameter represents the instance of the class itself and allows us to refer to the object's attributes and call its methods.

## Example 4:
```python 
class Person:
    # name: object's attributes
    def __init__(self, name):
        self.name = name

    def greet(self):
        print(f"Hello, my name is {self.name}.")

person1 = Person("Alice")
person1.greet()
```

- In the __init__ method, self refers to the newly created instance of the Person class. It allows us to assign the name passed as an argument to the object's attribute (self.name).

- In the greet method, self again refers to the instance of the class (person1). It enables us to access the name attribute of the object (self.name) and use it within the method to print a greeting message.

## Constructor 

A constructor is a special method in Python that is automatically called when an object of a class is created. It is used to initialize the object's attributes or perform any necessary setup operations.

In Python, the constructor method is defined with the name __init__. It takes the self parameter as the first argument, followed by any additional parameters that you want to pass when creating an object.

## Example 5:
```python
# Define a class called Person
class Person:
    def __init__(self, name, age):
        # Constructor: Initialize the attributes of the object
        self.name = name
        self.age = age

# Create an instance (object) of the Person class
person1 = Person("Alice", 25)
```

## Python Inheritance
Inheritance is the capability of one class to derive or inherit the properties from another class. The class that derives properties is called the derived class or child class and the class from which the properties are being derived is called the base class or parent class. The benefits of inheritance are:

**Inheritance benefits:**

- **Code Reusability:** Inheritance allows the derived class to reuse attributes and methods from the base class, avoiding code duplication and making the code more efficient.

- **Modularity and Organization:** Inheritance helps organize code by creating a hierarchy of classes. Common properties are defined in the base class, while specialized features are added in derived classes, improving code readability and maintainability.

- **Overriding and Polymorphism:** Derived classes can override inherited methods, providing customized behavior. Polymorphism allows objects of different classes to be used interchangeably, enhancing flexibility.

- **Extensibility:** Inheritance enables extending the functionality of existing classes without modifying them. New features can be added through derived classes, promoting scalability and adaptability of the codebase.

## Example 6:
```python
# Base class
class Shape:
    def __init__(self, color):
        self.color = color

    def display(self):
        print(f"This shape is {self.color}.")

# Derived class
class Circle(Shape):
    def display(self):
        print(f"This circle is {self.color}.")

# Create instances of the derived classes
shape = Shape("red")
circle = Circle("blue")

# Call the display method
shape.display()   # Output: This shape is red.
circle.display()  # Output: This circle is blue.
```

## Python Polymorphism
Polymorphism simply means having many forms. For example, we need to determine if the given species of birds fly or not, using polymorphism we can do this using a single function.

## Example 7:
```python
class Bird:

	def intro(self):
		print("There are many types of birds.")

	def flight(self):
		print("Most of the birds can fly but some cannot.")

class sparrow(Bird):

	def flight(self):
		print("Sparrows can fly.")

class ostrich(Bird):

	def flight(self):
		print("Ostriches cannot fly.")

obj_bird = Bird()
obj_spr = sparrow()
obj_ost = ostrich()

obj_bird.intro()
obj_bird.flight()

obj_spr.intro()
obj_spr.flight()

obj_ost.intro()
obj_ost.flight()

# Output
# There are many types of birds.
# Most of the birds can fly but some cannot.

# There are many types of birds.
# Sparrows can fly.

# There are many types of birds.
# Ostriches cannot fly.
```

## Python Encapsulation
Python encapsulation is a concept in object-oriented programming that involves bundling data (attributes) and methods (functions) together within a class. It aims to restrict access to the internal implementation details of an object and provides a controlled interface for interacting with the object.

Encapsulation is achieved by using access modifiers, such as public, private, and protected, to control the visibility of attributes and methods. Here's a brief explanation of these access modifiers:

1. Public: Public attributes and methods can be accessed from anywhere, both inside and outside the class. They are denoted by not using any access modifier.

2. Private: Private attributes and methods are intended to be accessed only within the class itself. They are denoted by prefixing an attribute or method name with double underscores (__).

3. Protected: Protected attributes and methods are intended to be accessed within the class itself and its subclasses. They are denoted by prefixing an attribute or method name with a single underscore (_).

## Example 8:
```python
class Car:
    def __init__(self, make, model, year):
        self._make = make     # Protected attribute
        self._model = model   # Protected attribute
        self.__year = year    # Private attribute

    def get_make(self):
        return self._make

    def get_model(self):
        return self._model

    def get_year(self):
        return self.__year

    def start_engine(self):
        self.__start()

    def __start(self):   # Private method
        print("Engine started.")

    def display_details(self):
        print(f"Make: {self._make}, Model: {self._model}, Year: {self.__year}")

# Create an instance of the Car class
my_car = Car("Toyota", "Camry", 2022)

# Accessing protected attributes and methods
print(my_car.get_make())      # Output: Toyota
print(my_car.get_model())     # Output: Camry

# Accessing a private attribute (Name mangling is applied)
print(my_car._Car__year)      # Output: 2022

# Calling a method that starts the engine
my_car.start_engine()         # Output: Engine started.

# Calling the public method to display details
my_car.display_details()      # Output: Make: Toyota, Model: Camry, Year: 2022
```

## Data Abstraction 
Data abstraction is a fundamental concept in object-oriented programming that involves presenting essential information while hiding the implementation details. It allows us to focus on what an object does rather than how it does it. Abstraction helps in creating complex systems by breaking them down into simpler, more manageable components.

## Example 9:
```python
from abc import ABC, abstractmethod

class Animal(ABC):
    def __init__(self, name):
        self.name = name

    @abstractmethod
    def sound(self):
        pass

    @abstractmethod
    def move(self):
        pass

class Dog(Animal):
    def sound(self):
        return "Woof!"

    def move(self):
        return "Running"

class Cat(Animal):
    def sound(self):
        return "Meow!"

    def move(self):
        return "Jumping"

# Creating objects of the derived classes
dog = Dog("Buddy")
cat = Cat("Whiskers")

# Accessing abstract methods through the objects
print(f"{dog.name} says: {dog.sound()}")
print(f"{cat.name} says: {cat.sound()}")

# Accessing abstract methods through the objects
print(f"{dog.name} is {dog.move()}")
print(f"{cat.name} is {cat.move()}")
```