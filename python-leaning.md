
## Python

Python is a **high-level, interpreted, general-purpose programming language** created by **Guido van Rossum** in **1991**.

# Basic Concepts of Python

## 1. Variables

Variables store data values.

### Example
name = "Ram"
age = 20
* `name` stores a string.
* `age` stores an integer.


## 2. Data Types

Python has several built-in data types:

| Data Type | Example        |
| --------- | -------------- |
| int       | 10             |
| float     | 10.5           |
| str       | "Hello"        |
| bool      | True, False    |
| list      | [1, 2, 3]      |
| tuple     | (1, 2, 3)      |
| set       | {1, 2, 3}      |
| dict      | {"name":"Ram"} |

### Example
x = 10
y = 3.14
name = "Python"
status = True



## 3. Operators
Used to perform operations on values.

### Arithmetic Operators

a = 10
b = 5
print(a + b)  # 15
print(a - b)  # 5
print(a * b)  # 50
print(a / b)  # 2.0


## 4. Input and Output

### Input
name = input("Enter your name: ")

### Output
print("Hello", name)


## 5. Conditional Statements

Used for decision making.

```python
age = 18

if age >= 18:
    print("Adult")
else:
    print("Minor")
```

---

## 6. Loops

### For Loop
for i in range(5):
    print(i)
```

### While Loop

count = 1
while count <= 5:
    print(count)
    count += 1


## 7. Functions

Functions are reusable blocks of code.

def greet(name):
    return f"Hello {name}"

print(greet("Ram"))


## 8. Lists

Store multiple values in one variable.

fruits = ["Apple", "Banana", "Mango"]
print(fruits[0])
```

---

## 9. Dictionaries

Store data in key-value pairs.

student = {
    "name": "Ram",
    "age": 20
}
print(student["name"])

---

## 10. Classes and Objects (OOP)

Python supports Object-Oriented Programming.
Example:
class Student:
    def __init__(self, name):
        self.name = name

s1 = Student("Ram")
print(s1.name)


# Python Libraries and Packages

## 1. Library

A library is a collection of pre-written Python code (modules and packages) that provides reusable functionality for specific tasks.

### Examples of Python Libraries

* `math` – Mathematical functions
* `random` – Random number generation
* `datetime` – Date and time operations
* `numpy` – Numerical computing
* `pandas` – Data analysis
* `matplotlib` – Data visualization

### Example
import math
print(math.sqrt(25))
```

### Importance of Libraries

* Saves development time
* Reduces code duplication
* Provides tested and optimized code
* Adds advanced functionality easily

---

## 2. Package

A package is a way of organizing related Python modules into a directory structure.

### Package Structure

```text
mypackage/
├── __init__.py
├── module1.py
└── module2.py
```

* `mypackage` → Package
* `module1.py`, `module2.py` → Modules
* `__init__.py` → Marks the directory as a package

### Example

**calculator.py**
def add(a, b):
    return a + b
```

**main.py**
from calculator import add
print(add(5, 3))


# Module

A module is a single Python file containing functions, classes, and variables.

### Example
def add(a, b):
    return a + b


# Virtual Environment (venv)

A Virtual Environment (`venv`) is an isolated Python environment that allows you to install packages for a specific project without affecting the global Python installation.

## Why Use venv?

* Keeps project dependencies separate
* Avoids version conflicts between projects
* Makes projects easier to share and deploy
* Prevents accidental modification of global packages

---

# Common Special Methods

## 1. `__init__()`

Called automatically when an object is created.

class Student:
    def __init__(self, name):
        self.name = name

s = Student("Ram")
print(s.name)
```

**Output**
Ram

**Purpose:** Initialize object attributes.


## 2. `__str__()`

Returns a human-readable string representation of an object.

class Student:
    def __init__(self, name):
        self.name = name

    def __str__(self):
        return f"Student: {self.name}"

s = Student("Ram")
print(s)


**Output**
Student: Ram

**Purpose:** Controls what `print(object)` displays.


## 3. `__repr__()`

Returns an official string representation of an object.

class Student:
    def __repr__(self):
        return "Student()"

s = Student()
print(repr(s))

**Output**
Student()


## 4. `__len__()`

Defines behavior for `len()`.

class Team:
    def __len__(self):
        return 5
t = Team()
print(len(t))
```

**Output**
5


## 5. `__add__()`

Defines behavior for the `+` operator.

class Number:
    def __init__(self, value):
        self.value = value

    def __add__(self, other):
        return self.value + other.value

a = Number(10)
b = Number(20)

print(a + b)
```

**Output**
30


## 6. `__eq__()`

Defines behavior for `==`.

class Student:
    def __init__(self, age):
        self.age = age

    def __eq__(self, other):
        return self.age == other.age

s1 = Student(20)
s2 = Student(20)
print(s1 == s2)

**Output**
True

# Polymorphism in Python

Polymorphism means **"many forms"**.

One function, method, or operator can behave differently in different situations.

## 1. Function Polymorphism

print(len("Hello"))
print(len([1, 2, 3]))
```

**Output**
5
3


## 2. Method Polymorphism

class Dog:
    def sound(self):
        return "Bark"

class Cat:
    def sound(self):
        return "Meow"

animals = [Dog(), Cat()]

for a in animals:
    print(a.sound())


**Output**
Bark
Meow


## 3. Operator Polymorphism

print(10 + 20)
print("Hi" + " Python")

**Output**
30
Hi Python
```

# Inheritance in Python

Inheritance allows a child class to acquire properties and methods from a parent class.

## Example
class Animal:
    def eat(self):
        print("Animal is eating")

class Dog(Animal):
    def bark(self):
        print("Dog is barking")

d = Dog()

d.eat()
d.bark()
```

**Output**
Animal is eating
Dog is barking


# Types of Inheritance

## 1. Single Inheritance

class Parent:
    def show(self):
        print("Parent Class")

class Child(Parent):
    pass

c = Child()
c.show()


## 2. Multilevel Inheritance

class GrandParent:
    def gp(self):
        print("Grandparent Method")

class Parent(GrandParent):
    pass

class Child(Parent):
    pass

c = Child()
c.gp()


## 3. Multiple Inheritance

class Father:
    def drive(self):
        print("Driving")

class Mother:
    def cook(self):
        print("Cooking")

class Child(Father, Mother):
    pass

c = Child()

c.drive()
c.cook()


## 4. Hierarchical Inheritance

class Parent:
    def show(self):
        print("Parent Method")

class Child1(Parent):
    pass

class Child2(Parent):
    pass
`

## 5. Hybrid Inheritance

        A
       / \
      B   C
       \ /
        D


# Method Overriding in Python

Method Overriding occurs when a child class provides its own implementation of a method already defined in the parent class.

### Example
class Animal:
    def sound(self):
        print("Animal makes a sound")

class Dog(Animal):
    def sound(self):
        print("Dog barks")

d = Dog()
d.sound()
```

**Output**
Dog barks


# Encapsulation in Python

Encapsulation is the process of wrapping data and methods together into a single unit (class) and restricting direct access to some data.

### Real-Life Example

ATM Machine:

* You can withdraw money using buttons.
* You cannot directly access the bank's internal data.

This is encapsulation.

### Example
class Student:
    def __init__(self, name, age):
        self.name = name
        self.age = age

    def display(self):
        print(self.name, self.age)

s = Student("Ram", 20)
s.display()
```

**Output**
Ram 20
```
