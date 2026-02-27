# Chapter 19: Classes 3 (Advanced Concepts) — Practice Problems

---

## 📝 Multiple Choice Questions

---

### 🟢 Beginner

**Problem 1.** What special method is automatically called when `print(obj)` executes?

① `__print__`
② `__str__`
③ `__show__`
④ `__display__`

---

**Problem 2.** What is the correct naming format for special methods (magic methods)?

① `_method_`
② `__method`
③ `__method__`
④ `method__`

---

**Problem 3.** What is the output of the following code?

```python
class Book:
    def __init__(self, title, price):
        self.title = title
        self.price = price
  
    def __str__(self):
        return f"{self.title} ({self.price:,})"

book = Book("Python", 20000)
print(book)
```

① `<__main__.Book object at 0x...>`
② `Python (20,000)`
③ `Book(Python, 20000)`
④ Error

---

**Problem 4.** What special method is called when executing `obj1 + obj2`?

① `__plus__`
② `__sum__`
③ `__add__`
④ `__combine__`

---

**Problem 5.** What special method is executed when calling `len(obj)`?

① `__length__`
② `__size__`
③ `__len__`
④ `__count__`

---

**Problem 6.** What decorator creates a property?

① `@prop`
② `@property`
③ `@getter`
④ `@attribute`

---

**Problem 7.** What decorator creates a static method?

① `@static`
② `@staticmethod`
③ `@classmethod`
④ `@method`

---

### 🟡 Intermediate

**Problem 8.** What is the output of the following code?

```python
class Vector:
    def __init__(self, x, y):
        self.x = x
        self.y = y
  
    def __add__(self, other):
        return Vector(self.x + other.x, self.y + other.y)
  
    def __str__(self):
        return f"({self.x}, {self.y})"

v1 = Vector(3, 4)
v2 = Vector(1, 2)
v3 = v1 + v2
print(v3)
```

① `(3, 4)`
② `(4, 6)`
③ `(1, 2)`
④ Error

---

**Problem 9.** What is the role of `@name.setter` in a property?

① Called when deleting attribute
② **Called when writing to attribute (validation possible)**
③ Called when reading attribute
④ Called when printing attribute

---

**Problem 10.** What is characteristic of static methods?

① Must have `self` parameter
② Must have `cls` parameter
③ **Can be called as `ClassName.method()` without creating object**
④ Can access instance variables

---

**Problem 11.** What is the output of the following code?

```python
class Student:
    def __init__(self, name, score):
        self.name = name
        self.score = score
  
    def __eq__(self, other):
        return self.score == other.score
  
    def __lt__(self, other):
        return self.score < other.score

s1 = Student("John", 85)
s2 = Student("Jane", 85)
s3 = Student("Mike", 90)
print(s1 == s2, s1 < s3)
```

① `False False`
② `True False`
③ `True True`
④ Error

---

**Problem 12.** What does the `__init__` method of a class do?

① Deletes object
② **Initializes object when created**
③ Prints object
④ Copies object

---

### 🔴 Advanced

**Problem 13.** What is the output of the following code?

```python
class Counter:
    count = 0
  
    @classmethod
    def increment(cls):
        cls.count += 1
  
    @staticmethod
    def get_info():
        return "Counter class"

Counter.increment()
Counter.increment()
print(Counter.count, Counter.get_info())
```

① `0 Counter class`
② `2 Counter class`
③ `1 Counter`
④ Error

---

**Problem 14.** What is the difference between `@classmethod` and `@staticmethod`?

① No difference
② `@classmethod` receives class as parameter, `@staticmethod` doesn't
③ `@classmethod` is for creating objects
④ `@staticmethod` is slower

---

**Problem 15.** What is the output?

```python
class Rectangle:
    def __init__(self, width, height):
        self._width = width
        self._height = height
  
    @property
    def width(self):
        return self._width
  
    @width.setter
    def width(self, value):
        if value > 0:
            self._width = value

rect = Rectangle(5, 3)
rect.width = 10
print(rect.width)
```

① `5`
② `10`
③ Error
④ `None`

---

## 📝 Short Answer Questions

---

### 🟢 Beginner

**Problem 16.** Explain what `__str__` method does and give an example.

---

**Problem 17.** What are special methods (magic methods)? Give 3 examples.

---

**Problem 18.** Explain the difference between `__str__` and `__repr__`.

---

### 🟡 Intermediate

**Problem 19.** Explain what properties are and why they are useful with example code.

```python
class Circle:
    def __init__(self, radius):
        self._radius = radius
  
    @property
    def radius(self):
        return self._radius
  
    @radius.setter
    def radius(self, value):
        if value > 0:
            self._radius = value
```

---

**Problem 20.** What is the difference between `@staticmethod` and `@classmethod`? Explain with examples.

---

### 🔴 Advanced

**Problem 21.** Create a comprehensive class using special methods and explain how it works.

```python
class Money:
    def __init__(self, amount):
        self.amount = amount
  
    def __add__(self, other):
        return Money(self.amount + other.amount)
  
    def __sub__(self, other):
        return Money(self.amount - other.amount)
  
    def __str__(self):
        return f"${self.amount:.2f}"
```

---

## 💻 Hands-On Problems

---

### 🟢 Beginner

**Problem 22.** Create a `Person` class with `__str__` and `__eq__` methods.

> Compare persons by age, print person info.

Output example:

```
=== Person Comparison ===
John: 30 years old
Jane: 30 years old
John == Jane (age): True
```

---

**Problem 23.** Create a `Temperature` class with temperature conversion.

> Use `__str__` to display temperature in Celsius.

Output example:

```
=== Temperature Info ===
Temperature: 25°C
Temperature: 77°F
```

---

### 🟡 Intermediate

**Problem 24.** Create a `BankAccount` class with deposit/withdraw using properties.

> Use property with validation for balance.

Output example:

```
=== Bank Account ===
Initial Balance: $1000
Deposit $500
New Balance: $1500
Withdraw $200
New Balance: $1300
```

---

**Problem 25.** Create a `Matrix` class with `__add__` for matrix addition.

> Support matrix operations with special methods.

Output example:

```
=== Matrix Operations ===
Matrix A: [[1, 2], [3, 4]]
Matrix B: [[5, 6], [7, 8]]
A + B: [[6, 8], [10, 12]]
```

---

### 🔴 Advanced

**Problem 26.** Create a comprehensive `SmartList` class with multiple special methods.

> Implement list-like behavior with validation.

Output example:

```
=== SmartList Operations ===
List: [1, 2, 3, 4, 5]
Length: 5
Index 2: 3
Contains 3: True
[1, 2, 3] + [4, 5]: [1, 2, 3, 4, 5]
```

---

---

# 🔑 Answer Key and Explanations

---

## 📝 Multiple Choice Answers

---

### 🟢 Beginner

**Problem 1. Answer: ② `__str__`**

`__str__` is called by `print()` to get string representation.

---

**Problem 2. Answer: ③ `__method__`**

Magic methods use double underscores on both sides.

---

**Problem 3. Answer: ② `Python (20,000)`**

`__str__` returns formatted string.

---

**Problem 4. Answer: ③ `__add__`**

Addition operator calls `__add__` method.

---

**Problem 5. Answer: ③ `__len__`**

`len()` function calls `__len__` method.

---

**Problem 6. Answer: ② `@property`**

`@property` decorator creates property.

---

**Problem 7. Answer: ② `@staticmethod`**

`@staticmethod` decorator for static methods.

---

### 🟡 Intermediate

**Problem 8. Answer: ② `(4, 6)`**

`__add__` returns new Vector with summed coordinates.

---

**Problem 9. Answer: ② Called when writing to attribute**

Setter allows validation when setting value.

---

**Problem 10. Answer: ③ Can be called without object**

Static methods don't need instance.

---

**Problem 11. Answer: ③ `True True`**

`s1 == s2` (same score), `s1 < s3` (85 < 90).

---

**Problem 12. Answer: ② Initializes object when created**

`__init__` is constructor.

---

### 🔴 Advanced

**Problem 13. Answer: ② `2 Counter class`**

`@classmethod` accesses class variable, `@staticmethod` returns string.

---

**Problem 14. Answer: ② `@classmethod` receives class, `@staticmethod` doesn't**

Key difference in parameter passing.

---

**Problem 15. Answer: ② `10`**

Property setter validates (10 > 0) and sets value.

---

## 📝 Short Answer Key

---

### 🟢 Beginner

**Problem 16. Model Answer:**

`__str__` returns string representation when `print()` called.

Example: Returns formatted product info.

---

**Problem 17. Model Answer:**

Special methods = automatic methods called by operators.

Examples: `__init__`, `__str__`, `__add__`, `__len__`, `__eq__`

---

**Problem 18. Model Answer:**

`__str__` = user-friendly display
`__repr__` = developer-friendly debug info

---

### 🟡 Intermediate

**Problem 19. Model Answer:**

Properties = controlled access to attributes with validation.

Allows `circle.radius = 5` with automatic checking.

---

**Problem 20. Model Answer:**

`@staticmethod` = no class/instance access
`@classmethod` = accesses class via `cls` parameter

---

### 🔴 Advanced

**Problem 21. Model Answer:**

Money class supports arithmetic with `__add__`/`__sub__` and displays with `__str__`.

---

## 💻 Hands-On Solutions

---

### 🟢 Beginner

**Problem 22. Model Answer:**

```python
class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age
  
    def __str__(self):
        return f"{self.name}: {self.age} years old"
  
    def __eq__(self, other):
        return self.age == other.age

print("=== Person Comparison ===")
john = Person("John", 30)
jane = Person("Jane", 30)
print(john)
print(jane)
print(f"John == Jane (age): {john == jane}")
```

---

**Problem 23. Model Answer:**

```python
class Temperature:
    def __init__(self, celsius):
        self.celsius = celsius
  
    def fahrenheit(self):
        return self.celsius * 9/5 + 32
  
    def __str__(self):
        return f"Temperature: {self.celsius}°C"

print("=== Temperature Info ===")
temp = Temperature(25)
print(temp)
print(f"Temperature: {temp.fahrenheit():.0f}°F")
```

---

### 🟡 Intermediate

**Problem 24. Model Answer:**

```python
class BankAccount:
    def __init__(self, initial_balance):
        self._balance = initial_balance
  
    @property
    def balance(self):
        return self._balance
  
    @balance.setter
    def balance(self, value):
        if value >= 0:
            self._balance = value
  
    def deposit(self, amount):
        self.balance = self._balance + amount
  
    def withdraw(self, amount):
        if self._balance >= amount:
            self.balance = self._balance - amount

print("=== Bank Account ===")
account = BankAccount(1000)
print(f"Initial Balance: ${account.balance}")
account.deposit(500)
print(f"Deposit $500")
print(f"New Balance: ${account.balance}")
account.withdraw(200)
print(f"Withdraw $200")
print(f"New Balance: ${account.balance}")
```

---

**Problem 25. Model Answer:**

```python
class Matrix:
    def __init__(self, data):
        self.data = data
  
    def __add__(self, other):
        result = []
        for i in range(len(self.data)):
            row = []
            for j in range(len(self.data[i])):
                row.append(self.data[i][j] + other.data[i][j])
            result.append(row)
        return Matrix(result)
  
    def __str__(self):
        return str(self.data)

print("=== Matrix Operations ===")
a = Matrix([[1, 2], [3, 4]])
b = Matrix([[5, 6], [7, 8]])
print(f"Matrix A: {a}")
print(f"Matrix B: {b}")
c = a + b
print(f"A + B: {c}")
```

---

### 🔴 Advanced

**Problem 26. Model Answer:**

```python
class SmartList:
    def __init__(self, items):
        self.items = items
  
    def __len__(self):
        return len(self.items)
  
    def __getitem__(self, index):
        return self.items[index]
  
    def __contains__(self, item):
        return item in self.items
  
    def __add__(self, other):
        return SmartList(self.items + other.items)
  
    def __str__(self):
        return str(self.items)

print("=== SmartList Operations ===")
lst = SmartList([1, 2, 3, 4, 5])
print(f"List: {lst}")
print(f"Length: {len(lst)}")
print(f"Index 2: {lst[2]}")
print(f"Contains 3: {3 in lst}")
lst2 = SmartList([4, 5])
lst3 = SmartList([1, 2, 3]) + lst2
print(f"[1, 2, 3] + [4, 5]: {lst3}")
```

---


Thank you for your attention.   
Cho Jeonghyun ([peterchokr@gmail.com](mailto:peterchokr@gmail.com)). Yeungnam University College

"Produced in collaboration with Claude and Gemini."
