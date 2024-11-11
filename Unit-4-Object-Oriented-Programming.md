# Unit 4: Object Oriented Programming
1. [Defining Classes, The self-parameter](#defining-classes-the-self-parameter)
2. [Adding methods to a Class](#adding-methods-to-a-class)
3. [Constructor and Types of constructor: The __init__ Method](#constructor-and-types-of-constructor-the-init-method)
4. [del__ Method (Destructor Method)](#del-method-destructor-method)
5. [Method Overloading in Python](#method-overloading-in-python)
6. [Inheritance, Types of Inheritance](#inheritance--types-of-inheritance)

## Defining Classes, The self-parameter

### Defining a Class

* Definition: In Python, a class is a blueprint for creating objects. It defines a set of attributes (variables) and methods (functions) that the objects created from the class can use.

* Syntax: Defined using the class keyword, followed by the class name and a colon.

```python
class Car:
    pass  # An empty class
```

### The self Parameter
* Self represents the instance of the class. 
* It's a way to refer to the object itself within the class, allowing you to access its attributes and methods.

* Usage: The first parameter in any method of a class is self, making it possible for the method to access the instance's variables and other methods.

```python
class Car:
    def __init__(self, brand):
        self.brand = brand  # Access instance variable using self

    def display_brand(self):
        print(f"The car brand is {self.brand}")
        
my_car = Car("Toyota")
my_car.display_brand()  # Output: The car brand is Toyota
```

## Adding methods to a Class

### Methods in a Class
* Definition: Methods are functions defined inside a class to operate on the instance data.

* Purpose: Methods perform actions or calculations using the class’s data, which allows for encapsulation (hiding details of how data is managed).

* Defining a Method: Functions within a class that include self as their first parameter. Additional parameters can follow based on the function’s requirements.

```python
class Calculator:
    def add(self, a, b):
        return a + b            # This method adds two numbers

    def subtract(self, a, b):
        return a - b            # This method subtracts two numbers

calc = Calculator()
print(calc.add(5, 3))           # Output: 8
print(calc.subtract(10, 4))     # Output: 6
```

## Constructor and Types of constructor: The __init__ Method

### Constructor
* A constructor is a special method that initializes (sets up) new objects of a class.

* The __init__ Method: In Python, the constructor is named __init__. 

* It’s automatically called when a new instance of a class is created.

```Python
class Person:
    def __init__(self, name, age):
        self.name = name        # Instance variable for name
        self.age = age          # Instance variable for age

person = Person("Alice", 25)
print(person.name, person.age)  # Output: Alice 25
```

### Types of Constructors

1. Default Constructor: A constructor that does not accept any arguments (except self).

```python
class Example:
    def __init__(self):
        self.message = "Default Constructor"
```

2. Parameterized Constructor: A constructor that accepts arguments to initialize instance variables.

```python
class Example:
    def __init__(self, message):
        self.message = message
```

## __del__ Method (Destructor Method)

### Destructor
* A destructor is a method called when an object is about to be destroyed. It allows you to release resources (like closing files or network connections) before the object is deleted.
* The __del__ Method: In Python, the destructor method is named __del__.

```python
class Resource:
    def __init__(self):
        print("Resource acquired")

    def __del__(self):
        print("Resource released")

resource = Resource()
del resource  # Output: Resource acquired \n Resource released
```

## Method Overloading in Python

### Method Overloading
* Method overloading allows a class to define multiple methods with the same name but different parameters.

* Python does not support traditional method overloading. 
* Instead, it handles different scenarios using default arguments or conditional checks within a single method.

```python
class Greeter:
    def greet(self, name=None):
        if name:
            print(f"Hello, {name}")
        else:
            print("Hello, World")

g = Greeter()
g.greet("Alice")  # Output: Hello, Alice
g.greet()         # Output: Hello, World
```
## Inheritance & Types of Inheritance

### Inheritance
* Inheritance allows a new class to derive properties and behavior from an existing class, enabling code reuse.

* The derived (child) class inherits from the base (parent) class by including the parent class name in parentheses.

``` python
class Animal:
    def speak(self):
        return "Animal makes a sound"

class Dog(Animal):  # Inheriting from Animal
    def bark(self):
        return "Dog barks"

dog = Dog()
print(dog.speak())  # Output: Animal makes a sound
print(dog.bark())   # Output: Dog barks
```

### Types of Inheritance

1. Single Inheritance: A derived class inherits from a single base class.

```python
class Base1:
    pass

class Base2:
    pass

class Derived(Base1, Base2):
    pass
```
2. Multiple Inheritance: A derived class inherits from more than one base class.

```python
class Base1:
    pass

class Base2:
    pass

class Derived(Base1, Base2):
    pass
```
3. Multilevel Inheritance: A class inherits from a derived class, forming a chain.

```python
class Grandparent:
    pass

class Parent(Grandparent):
    pass

class Child(Parent):
    pass
```
4. Hierarchical Inheritance: Multiple derived classes inherit from a single base class.

```python
class Parent:
    pass

class Child1(Parent):
    pass

class Child2(Parent):
    pass

```
5. Hybrid Inheritance: A combination of multiple inheritance types.

```python
class Base:
    pass

class Child1(Base):
    pass

class Child2(Base):
    pass

class GrandChild(Child1, Child2):
    pass
```
