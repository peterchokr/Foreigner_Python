# Chapter 17: Classes 1 (Basics) — Practice Problems

---

## 📝 Multiple Choice Questions

---

### 🟢 Beginner

**Problem 1.** What keyword defines a class in Python?

① `def`
② `class`
③ `function`
④ `object`

---

**Problem 2.** What is the relationship between class and object?

① Class is a copy of an object
② **Class is a blueprint, object is the actual product made from it**
③ Object is parent of class
④ Class and object are the same

---

**Problem 3.** What method is automatically called when an object is created?

① `__new__`
② `__start__`
③ `__init__`
④ `__create__`

---

**Problem 4.** What is the output of the following code?

```python
class Dog:
    def __init__(self, name):
        self.name = name

dog = Dog("Wangwang")
print(dog.name)
```

① `Dog`
② `Wangwang`
③ `name`
④ Error

---

**Problem 5.** What is the role of `self`?

① Refers to the class itself
② **Refers to the object itself**
③ Stores method name
④ Indicates variable type

---

**Problem 6.** What is the output of the following code?

```python
class Cat:
    def __init__(self, name, age):
        self.name = name
        self.age = age

cat = Cat("Navi", 2)
print(f"{cat.name} is {cat.age} years old")
```

① `Cat is 2 years old`
② `Navi is 2 years old`
③ `name is age years old`
④ Error

---

**Problem 7.** What are 2 components of a class?

① Functions and variables
② **Attributes (data) and methods (functions)**
③ Modules and packages
④ Lists and dictionaries

---

### 🟡 Intermediate

**Problem 8.** What is the output of the following code?

```python
class Counter:
    def __init__(self):
        self.count = 0
  
    def increase(self):
        self.count += 1

c = Counter()
c.increase()
c.increase()
c.increase()
print(c.count)
```

① `0`
② `1`
③ `3`
④ Error

---

**Problem 9.** How many parameters (excluding `self`) does `__init__` have?

```python
class Student:
    def __init__(self, name, student_id, grade):
        self.name = name
        self.student_id = student_id
        self.grade = grade
```

① 1
② 2
③ 3
④ 4

---

**Problem 10.** What is the difference between class variables and instance variables?

① Class variables differ for each object
② Instance variables are shared by all objects
③ **Class variables are shared by all objects, instance variables differ per object**
④ No difference

---

**Problem 11.** What is the class variable in the following code?

```python
class Dog:
    species = "Mammal"
  
    def __init__(self, name):
        self.name = name
```

① `name`
② **`species`**
③ `self`
④ `__init__`

---

**Problem 12.** What is the output?

```python
class Car:
    wheels = 4
  
    def __init__(self, color):
        self.color = color

car1 = Car("red")
car2 = Car("blue")
print(car1.wheels == car2.wheels)
```

① `True`
② `False`
③ `4`
④ Error

---

### 🔴 Advanced

**Problem 13.** What is the output of the following code?

```python
class Rectangle:
    def __init__(self, width, height):
        self.width = width
        self.height = height
  
    def area(self):
        return self.width * self.height

rect = Rectangle(5, 3)
print(rect.area())
```

① `8`
② `15`
③ `(5, 3)`
④ Error

---

**Problem 14.** What happens with class variables when shared?

```python
class Counter2:
    count = 0
  
    def __init__(self):
        Counter2.count += 1

c1 = Counter2()
c2 = Counter2()
c3 = Counter2()
print(Counter2.count)
```

① `0`
② `1`
③ **`3`**
④ Error

---

**Problem 15.** What is the correct way to call a method?

```python
class Student2:
    def __init__(self, name):
        self.name = name
  
    def introduce(self):
        return f"Hello, I am {self.name}"

student = Student2("Alice")
```

How to call the method?

① `Student2.introduce()`
② `Student2.introduce(student)`
③ **`student.introduce()`**
④ `introduce(student)`

---

## 📝 Short Answer Questions

---

### 🟢 Beginner

**Problem 16.** Explain what a class is and give a real-world example.

---

**Problem 17.** What is the purpose of `__init__` method? Explain with example code.

```python
class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age

person = Person("John", 30)
print(person.name)
print(person.age)
```

---

**Problem 18.** What is the difference between attributes and methods? Give examples.

---

### 🟡 Intermediate

**Problem 19.** Explain instance variables and class variables with code examples.

```python
class Dog3:
    species = "Canine"  # Class variable
  
    def __init__(self, name):
        self.name = name  # Instance variable
```

---

**Problem 20.** What does `self` mean in a class and why is it necessary?

---

### 🔴 Advanced

**Problem 21.** Create a class with attributes, instance methods, and explain how it works.

```python
class BankAccount:
    def __init__(self, owner, balance):
        self.owner = owner
        self.balance = balance
  
    def deposit(self, amount):
        self.balance += amount
  
    def withdraw(self, amount):
        self.balance -= amount
  
    def show_balance(self):
        return f"{self.owner}: ${self.balance}"
```

---

## 💻 Hands-On Problems

---

### 🟢 Beginner

**Problem 22.** Create a simple `Student` class with name and ID.

> Create class, make 3 students, print their information.

Output example:

```
=== Student Information ===
Student 1: John (ID: S001)
Student 2: Jane (ID: S002)
Student 3: Mike (ID: S003)
```

---

**Problem 23.** Create a `Circle` class with radius attribute.

> Calculate and display area and circumference.

Output example:

```
=== Circle Calculator ===
Radius: 5
Diameter: 10
Circumference: 31.42
Area: 78.54
```

---

### 🟡 Intermediate

**Problem 24.** Create a `BankAccount` class with deposit and withdraw methods.

> Track account balance, handle transactions.

Output example:

```
=== Bank Account ===
Owner: John
Initial Balance: $1000

Transaction: Deposit $500
Current Balance: $1500

Transaction: Withdraw $200
Current Balance: $1300

Transaction: Withdraw $500
Current Balance: $800

Final Balance: $800
```

---

**Problem 25.** Create a `Product` class with price and discount methods.

> Manage products with discount calculations.

Output example:

```
=== Product Inventory ===
Product: Laptop
Original Price: $1200
Discount: 10%
Final Price: $1080

Product: Mouse
Original Price: $25
Discount: 15%
Final Price: $21.25

Total Value: $1101.25
```

---

### 🔴 Advanced

**Problem 26.** Create a comprehensive `Person` class with multiple methods.

> Full-featured class with various operations.

Output example:

```
=== Person Information ===

Name: John Doe
Age: 30
Email: john@example.com

Birthday next year: Age will be 31

Info Summary:
John Doe (30 years old)
Email: john@example.com

Greeting: Hello, my name is John Doe!
```

---

---

# 🔑 Answer Key and Explanations

---

## 📝 Multiple Choice Answers

---

### 🟢 Beginner

**Problem 1. Answer: ② `class`**

`def` is for functions, `class` is for classes.

---

**Problem 2. Answer: ② Class is a blueprint, object is the actual product**

This is the fundamental OOP concept.

---

**Problem 3. Answer: ③ `__init__`**

Constructor method that initializes new objects.

---

**Problem 4. Answer: ② `Wangwang`**

`__init__` sets `self.name = "Wangwang"`, then prints it.

---

**Problem 5. Answer: ② Refers to the object itself**

`self` represents the current object instance.

---

**Problem 6. Answer: ② `Navi is 2 years old`**

`__init__` sets both attributes correctly.

---

**Problem 7. Answer: ② Attributes (data) and methods (functions)**

Classes have data (attributes) and operations (methods).

---

### 🟡 Intermediate

**Problem 8. Answer: ③ `3`**

`increase()` called 3 times, count becomes 3.

---

**Problem 9. Answer: ③ 3**

Parameters: name, student_id, grade (excluding self).

---

**Problem 10. Answer: ③ Class variables shared, instance variables unique**

Key difference in OOP.

---

**Problem 11. Answer: ② `species`**

Defined at class level, not in `__init__`.

---

**Problem 12. Answer: ① `True`**

Both objects share class variable `wheels = 4`.

---

### 🔴 Advanced

**Problem 13. Answer: ② `15`**

Area = width × height = 5 × 3 = 15.

---

**Problem 14. Answer: ③ `3`**

Class variable incremented 3 times (once per object).

---

**Problem 15. Answer: ③ `student.introduce()`**

Methods called on objects, not classes.

---

## 📝 Short Answer Key

---

### 🟢 Beginner

**Problem 16. Model Answer:**

Class = template for creating objects with shared attributes and methods.

Example: Car class has color, brand, drive() method.

---

**Problem 17. Model Answer:**

Initializes object when created, sets initial values for attributes.

**Output:**

```
John
30
```

---

**Problem 18. Model Answer:**

Attributes = data (properties like name, age)
Methods = functions (actions like introduce())

---

### 🟡 Intermediate

**Problem 19. Model Answer:**

Class variable shared by all instances, instance variable unique per object.

---

**Problem 20. Model Answer:**

`self` = current object. Necessary to access/modify object's attributes.

---

### 🔴 Advanced

**Problem 21. Model Answer:**

Class with deposit/withdraw/show_balance methods managing account state.

---

## 💻 Hands-On Solutions

---

### 🟢 Beginner

**Problem 22. Model Answer:**

```python
class Student:
    def __init__(self, name, student_id):
        self.name = name
        self.student_id = student_id

print("=== Student Information ===")
student1 = Student("John", "S001")
student2 = Student("Jane", "S002")
student3 = Student("Mike", "S003")

print(f"Student 1: {student1.name} (ID: {student1.student_id})")
print(f"Student 2: {student2.name} (ID: {student2.student_id})")
print(f"Student 3: {student3.name} (ID: {student3.student_id})")
```

---

**Problem 23. Model Answer:**

```python
import math

class Circle:
    def __init__(self, radius):
        self.radius = radius
  
    def diameter(self):
        return self.radius * 2
  
    def circumference(self):
        return 2 * math.pi * self.radius
  
    def area(self):
        return math.pi * self.radius ** 2

circle = Circle(5)
print("=== Circle Calculator ===")
print(f"Radius: {circle.radius}")
print(f"Diameter: {circle.diameter()}")
print(f"Circumference: {circle.circumference():.2f}")
print(f"Area: {circle.area():.2f}")
```

---

### 🟡 Intermediate

**Problem 24. Model Answer:**

```python
class BankAccount:
    def __init__(self, owner, balance):
        self.owner = owner
        self.balance = balance
  
    def deposit(self, amount):
        self.balance = self.balance + amount
  
    def withdraw(self, amount):
        self.balance = self.balance - amount
  
    def show_balance(self):
        return f"Current Balance: ${self.balance}"

account = BankAccount("John", 1000)
print("=== Bank Account ===")
print(f"Owner: {account.owner}")
print(f"Initial Balance: ${account.balance}\n")

account.deposit(500)
print("Transaction: Deposit $500")
print(account.show_balance())

account.withdraw(200)
print("\nTransaction: Withdraw $200")
print(account.show_balance())

account.withdraw(500)
print("\nTransaction: Withdraw $500")
print(account.show_balance())

print(f"\nFinal Balance: ${account.balance}")
```

---

**Problem 25. Model Answer:**

```python
class Product:
    def __init__(self, name, price):
        self.name = name
        self.price = price
  
    def apply_discount(self, discount_percent):
        discount_amount = self.price * (discount_percent / 100)
        final_price = self.price - discount_amount
        return final_price

products = [
    ("Laptop", 1200, 10),
    ("Mouse", 25, 15)
]

total_value = 0
print("=== Product Inventory ===")

for name, price, discount in products:
    product = Product(name, price)
    final = product.apply_discount(discount)
    total_value = total_value + final
    print(f"Product: {name}")
    print(f"Original Price: ${price}")
    print(f"Discount: {discount}%")
    print(f"Final Price: ${final:.2f}\n")

print(f"Total Value: ${total_value:.2f}")
```

---

### 🔴 Advanced

**Problem 26. Model Answer:**

```python
class Person:
    def __init__(self, name, age, email):
        self.name = name
        self.age = age
        self.email = email
  
    def birthday(self):
        self.age = self.age + 1
        return f"Next birthday: {self.name} will be {self.age}"
  
    def get_info(self):
        return f"{self.name} ({self.age} years old)"
  
    def greet(self):
        return f"Hello, my name is {self.name}!"

person = Person("John Doe", 30, "john@example.com")

print("=== Person Information ===\n")
print(f"Name: {person.name}")
print(f"Age: {person.age}")
print(f"Email: {person.email}\n")

print(person.birthday() + "\n")

print("Info Summary:")
print(person.get_info() + "\n")

print("Greeting:", person.greet())
```

---


Thank you for your attention.   
Cho Jeonghyun ([peterchokr@gmail.com](mailto:peterchokr@gmail.com)). Yeungnam University College

"Produced in collaboration with Claude and Gemini."
