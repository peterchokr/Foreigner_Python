# Chapter 18: Classes 2 (Inheritance and Methods) — Practice Problems

---

## 📝 Multiple Choice Questions

---

### 🟢 Beginner

**Problem 1.** What is the correct syntax for inheritance in Python?

① `class Child extends Parent:`  
② `class Child(Parent):`  
③ `class Child inherits Parent:`  
④ `class Child <- Parent:`  

---

**Problem 2.** Which statement about inheritance is correct?

① Child class inherits attributes from child class  
② **Child class inherits attributes and methods from parent class**  
③ Parent class is deleted after inheritance  
④ One parent class can have only one child  

---

**Problem 3.** What is the output of the following code?

```python
class Animal:
    def eat(self):
        print("Eating")

class Dog(Animal):
    def bark(self):
        print("Wangwang!")

dog = Dog()
dog.eat()
```

① Error  
② `Eating`  
③ `Wangwang!`  
④ Both `Eating` and `Wangwang!`  

---

**Problem 4.** What function calls a parent class method?

① `parent()`  
② `base()`  
③ `super()`  
④ `inherit()`  

---

**Problem 5.** What is the output of the following code?

```python
class Animal:
    def speak(self):
        print("...")

class Dog(Animal):
    def speak(self):
        print("Wangwang!")

dog = Dog()
dog.speak()
```

① `...`  
② `Wangwang!`  
③ Both printed  
④ Error  

---

**Problem 6.** What is method overriding?

① Deleting parent method  
② **Redefining parent method in child class**  
③ Adding new method  
④ Copying method  

---

**Problem 7.** What is the output of the following code?

```python
class Animal:
    def __init__(self, name):
        self.name = name

class Dog(Animal):
    def __init__(self, name, breed):
        super().__init__(name)
        self.breed = breed

dog = Dog("Wangwang", "Jindo")
print(f"{dog.name} ({dog.breed})")
```

① Error  
② `Wangwang (Jindo)`  
③ `Dog (Jindo)`  
④ `Wangwang`  

---

### 🟡 Intermediate

**Problem 8.** What is the result of `isinstance(dog, Animal)` when `dog = Dog()` and `Dog` inherits from `Animal`?

① `True`  
② `False`  
③ `None`  
④ Error  

---

**Problem 9.** What is the output of the following code?

```python
class Shape:
    def area(self):
        return 0

class Rectangle(Shape):
    def __init__(self, width, height):
        self.width = width
        self.height = height
    
    def area(self):
        return self.width * self.height

r = Rectangle(5, 3)
print(r.area())
```

① `0`  
② `15`  
③ `8`  
④ Error  

---

**Problem 10.** What is the output?

```python
class Parent:
    def greet(self):
        return "Hello"

class Child(Parent):
    def greet(self):
        return super().greet() + " from Child"

c = Child()
print(c.greet())
```

① `Hello`  
② `Hello from Child`  
③ Error  
④ `from Child`  

---

**Problem 11.** What does MRO (Method Resolution Order) refer to?

① **Order of searching for methods in inheritance hierarchy**  
② Modifying resolve options  
③ Memory resource optimization  
④ Module resolution order  

---

**Problem 12.** What is the output?

```python
class Vehicle:
    wheels = 4

class Car(Vehicle):
    pass

car = Car()
print(car.wheels)
```

① Error  
② `4`  
③ `None`  
④ `Car`  

---

### 🔴 Advanced

**Problem 13.** What is the output of the following code?

```python
class Person:
    def __init__(self, name):
        self.name = name
    
    def introduce(self):
        return f"I am {self.name}"

class Student(Person):
    def __init__(self, name, grade):
        super().__init__(name)
        self.grade = grade
    
    def introduce(self):
        return super().introduce() + f", Grade {self.grade}"

student = Student("John", "A")
print(student.introduce())
```

① `I am John`  
② `I am John, Grade A`  
③ Error  
④ `John, Grade A`  

---

**Problem 14.** Can a child class have multiple parent classes?

```python
class A:
    pass

class B:
    pass

class C(A, B):
    pass
```

① No, error  
② **Yes, multiple inheritance is supported**  
③ Only 2 parents allowed  
④ Not recommended  

---

**Problem 15.** What is abstract method?

① Method defined in parent but not implemented  
② Method with no return value  
③ **Method that must be implemented by child class**  
④ Method that cannot be inherited  

---

## 📝 Short Answer Questions

---

### 🟢 Beginner

**Problem 16.** Explain what inheritance is and give a real-world example.

---

**Problem 17.** What is the difference between inheritance and method overriding? Explain with example code.

```python
class Animal:
    def eat(self):
        print("Eating")

class Dog(Animal):
    def bark(self):
        print("Wangwang!")
```

---

**Problem 18.** What is `super()` and why is it used? Give example.

```python
class Parent:
    def __init__(self, name):
        self.name = name

class Child(Parent):
    def __init__(self, name, age):
        super().__init__(name)
        self.age = age
```

---

### 🟡 Intermediate

**Problem 19.** Explain the difference between overriding and overloading.

---

**Problem 20.** What is `isinstance()` function and how is it used in inheritance?

---

### 🔴 Advanced

**Problem 21.** Create a multi-level inheritance system and explain how it works.

```python
class Animal:
    def eat(self):
        print("Eating")

class Mammal(Animal):
    def nurse(self):
        print("Nursing")

class Dog(Mammal):
    def bark(self):
        print("Wangwang!")
```

---

## 💻 Hands-On Problems

---

### 🟢 Beginner

**Problem 22.** Create a `Vehicle` parent class and `Car` child class.

> Vehicle has color, Car adds brand, both print information.

Output example:

```
=== Vehicle Information ===
Car: Red BMW
Color: Red
Brand: BMW
```

---

**Problem 23.** Create `Shape` parent and `Circle` child with area calculation.

> Override area method in child class.

Output example:

```
=== Shape Calculation ===
Shape area: 0
Circle radius: 5
Circle area: 78.54
```

---

### 🟡 Intermediate

**Problem 24.** Create `Employee` parent and `Manager`/`Developer` child classes.

> Different wage calculations based on type.

Output example:

```
=== Employee Management ===
Manager: John
Base Salary: $3000
Bonus: $1000
Total: $4000

Developer: Jane
Base Salary: $2500
Overtime: $500
Total: $3000
```

---

**Problem 25.** Create inheritance hierarchy with `super()` usage.

> Multi-level initialization with parent data.

Output example:

```
=== School System ===
Person: John, Age: 20
Student: John, Grade: A+
Score: 95
GPA: 4.0
```

---

### 🔴 Advanced

**Problem 26.** Create a comprehensive animal classification system.

> Multiple levels of inheritance with method overriding.

Output example:

```
=== Animal Classification ===

Dog:
Eating: Dog is eating meat
Moving: Dog is running
Speaking: Wangwang!

Bird:
Eating: Bird is eating seeds
Moving: Bird is flying
Speaking: Tweet tweet!

Fish:
Eating: Fish is eating plankton
Moving: Fish is swimming
Speaking: Blub blub!
```

---
---

# 🔑 Answer Key and Explanations

---

## 📝 Multiple Choice Answers

---

### 🟢 Beginner

**Problem 1. Answer: ② `class Child(Parent):`**

Python uses parentheses for inheritance.

---

**Problem 2. Answer: ② Child class inherits from parent class**

Core concept of inheritance.

---

**Problem 3. Answer: ② `Eating`**

Dog inherits eat() method from Animal.

---

**Problem 4. Answer: ③ `super()`**

`super()` accesses parent class methods.

---

**Problem 5. Answer: ② `Wangwang!`**

Child's speak() overrides parent's.

---

**Problem 6. Answer: ② Redefining parent method in child class**

Overriding = changing inherited method.

---

**Problem 7. Answer: ② `Wangwang (Jindo)`**

`super().__init__()` initializes parent, then child.

---

### 🟡 Intermediate

**Problem 8. Answer: ① `True`**

Child instance is also instance of parent.

---

**Problem 9. Answer: ② `15`**

Rectangle's area() overrides Shape's.

---

**Problem 10. Answer: ② `Hello from Child`**

`super().greet()` calls parent's greet().

---

**Problem 11. Answer: ① Order of searching for methods**

Python searches child → parent classes in order.

---

**Problem 12. Answer: ② `4`**

Car inherits wheels class variable.

---

### 🔴 Advanced

**Problem 13. Answer: ② `I am John, Grade A`**

Multi-level inheritance with super() calls.

---

**Problem 14. Answer: ② Yes, multiple inheritance is supported**

Python supports multiple inheritance.

---

**Problem 15. Answer: ③ Method that must be implemented by child**

Abstract methods define interface.

---

## 📝 Short Answer Key

---

### 🟢 Beginner

**Problem 16. Model Answer:**

Inheritance = child class gets properties/methods from parent.

Example: Dog inherits from Animal (eat, sleep).

---

**Problem 17. Model Answer:**

Inheritance = getting methods from parent  
Overriding = redefining inherited method

---

**Problem 18. Model Answer:**

`super()` calls parent method/constructor for code reuse.

---

### 🟡 Intermediate

**Problem 19. Model Answer:**

Overriding = changing inherited method (inheritance)  
Overloading = multiple methods with same name (not in Python)

---

**Problem 20. Model Answer:**

`isinstance()` checks if object is instance of class or parent.

---

### 🔴 Advanced

**Problem 21. Model Answer:**

Dog → Mammal → Animal hierarchy allows progressive specialization.

---

## 💻 Hands-On Solutions

---

### 🟢 Beginner

**Problem 22. Model Answer:**

```python
class Vehicle:
    def __init__(self, color):
        self.color = color

class Car(Vehicle):
    def __init__(self, color, brand):
        super().__init__(color)
        self.brand = brand
    
    def info(self):
        return f"{self.brand} {self.color}"

print("=== Vehicle Information ===")
car = Car("Red", "BMW")
print(f"Car: {car.info()}")
print(f"Color: {car.color}")
print(f"Brand: {car.brand}")
```

---

**Problem 23. Model Answer:**

```python
import math

class Shape:
    def area(self):
        return 0

class Circle(Shape):
    def __init__(self, radius):
        self.radius = radius
    
    def area(self):
        return math.pi * self.radius ** 2

print("=== Shape Calculation ===")
shape = Shape()
print(f"Shape area: {shape.area()}")

circle = Circle(5)
print(f"Circle radius: {circle.radius}")
print(f"Circle area: {circle.area():.2f}")
```

---

### 🟡 Intermediate

**Problem 24. Model Answer:**

```python
class Employee:
    def __init__(self, name, base_salary):
        self.name = name
        self.base_salary = base_salary
    
    def calculate_total(self):
        return self.base_salary

class Manager(Employee):
    def __init__(self, name, base_salary, bonus):
        super().__init__(name, base_salary)
        self.bonus = bonus
    
    def calculate_total(self):
        return self.base_salary + self.bonus

class Developer(Employee):
    def __init__(self, name, base_salary, overtime):
        super().__init__(name, base_salary)
        self.overtime = overtime
    
    def calculate_total(self):
        return self.base_salary + self.overtime

print("=== Employee Management ===")
manager = Manager("John", 3000, 1000)
print(f"Manager: {manager.name}")
print(f"Base Salary: ${manager.base_salary}")
print(f"Bonus: ${manager.bonus}")
print(f"Total: ${manager.calculate_total()}\n")

developer = Developer("Jane", 2500, 500)
print(f"Developer: {developer.name}")
print(f"Base Salary: ${developer.base_salary}")
print(f"Overtime: ${developer.overtime}")
print(f"Total: ${developer.calculate_total()}")
```

---

**Problem 25. Model Answer:**

```python
class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age

class Student(Person):
    def __init__(self, name, age, grade):
        super().__init__(name, age)
        self.grade = grade
    
    def info(self):
        return f"Person: {self.name}, Age: {self.age}\nStudent: {self.name}, Grade: {self.grade}"

print("=== School System ===")
student = Student("John", 20, "A+")
print(student.info())
print(f"Score: 95")
print(f"GPA: 4.0")
```

---

### 🔴 Advanced

**Problem 26. Model Answer:**

```python
class Animal:
    def eat(self):
        return "Eating"
    
    def move(self):
        return "Moving"
    
    def speak(self):
        return "Speaking"

class Dog(Animal):
    def eat(self):
        return "Dog is eating meat"
    
    def move(self):
        return "Dog is running"
    
    def speak(self):
        return "Wangwang!"

class Bird(Animal):
    def eat(self):
        return "Bird is eating seeds"
    
    def move(self):
        return "Bird is flying"
    
    def speak(self):
        return "Tweet tweet!"

class Fish(Animal):
    def eat(self):
        return "Fish is eating plankton"
    
    def move(self):
        return "Fish is swimming"
    
    def speak(self):
        return "Blub blub!"

print("=== Animal Classification ===\n")

animals = [Dog(), Bird(), Fish()]
animal_names = ["Dog", "Bird", "Fish"]

for animal, name in zip(animals, animal_names):
    print(f"{name}:")
    print(f"Eating: {animal.eat()}")
    print(f"Moving: {animal.move()}")
    print(f"Speaking: {animal.speak()}\n")
```

---

Professor Cho Jeonghyun (peterchokr@gmail.com)  
Yeungnam University College.
