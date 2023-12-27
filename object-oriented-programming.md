Sure, let's cover the fundamental concepts of Object-Oriented Programming (OOP) in Python with examples. Object-Oriented Programming is a paradigm that organizes code into reusable and structured units called objects. Python supports OOP principles, including encapsulation, inheritance, and polymorphism.

### 1. **Class and Object:**

#### Class:
A class is a blueprint for creating objects. It defines a data structure and methods that operate on the data.

```python
class Car:
    def __init__(self, make, model):
        self.make = make
        self.model = model

    def display_info(self):
        print(f"{self.make} {self.model}")

# Creating an object of the Car class
car1 = Car("Toyota", "Camry")
car1.display_info()
```

In this example, `Car` is a class with attributes `make` and `model`. The `__init__` method initializes these attributes. The `display_info` method prints information about the car.

### 2. **Encapsulation:**

Encapsulation restricts access to some of an object's components and prevents the direct modification of internal state.

```python
class BankAccount:
    def __init__(self, balance=0):
        self._balance = balance  # _balance is a convention for a protected attribute

    def deposit(self, amount):
        self._balance += amount

    def withdraw(self, amount):
        if amount <= self._balance:
            self._balance -= amount
        else:
            print("Insufficient funds")

    def get_balance(self):
        return self._balance

# Using encapsulation
account = BankAccount(1000)
account.deposit(500)
account.withdraw(200)
print("Balance:", account.get_balance())
```

Here, `_balance` is a protected attribute. It can be accessed, but the leading underscore indicates that it should be treated as internal to the class.

### 3. **Inheritance:**

Inheritance allows a class to inherit properties and methods from another class.

```python
class Animal:
    def __init__(self, species):
        self.species = species

    def speak(self):
        print("Generic animal sound")

class Dog(Animal):
    def __init__(self, breed):
        super().__init__("Dog")
        self.breed = breed

    def speak(self):
        print("Woof!")

# Using inheritance
dog = Dog("Golden Retriever")
print(dog.species)  # Inherited from Animal
dog.speak()         # Overridden method in Dog
```

Here, `Dog` is a subclass of `Animal`. It inherits the `species` attribute and `speak` method from the parent class. The `speak` method is overridden to provide a specific behavior for dogs.

### 4. **Polymorphism:**

Polymorphism allows objects of different classes to be treated as objects of a common base class.

```python
class Shape:
    def area(self):
        pass

class Circle(Shape):
    def __init__(self, radius):
        self.radius = radius

    def area(self):
        return 3.14 * self.radius ** 2

class Square(Shape):
    def __init__(self, side):
        self.side = side

    def area(self):
        return self.side ** 2

# Using polymorphism
shapes = [Circle(5), Square(4)]
for shape in shapes:
    print(f"Area: {shape.area()}")
```

Here, both `Circle` and `Square` are subclasses of `Shape`, and they provide their own implementation of the `area` method. The `shapes` list demonstrates polymorphism by iterating through objects of different types and calling a common method.

These examples cover the basic concepts of Object-Oriented Programming in Python. Understanding and practicing these concepts will provide a solid foundation for building more complex and modular software systems.
