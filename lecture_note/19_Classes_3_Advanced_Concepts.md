# Chapter 19. Classes 3 (Advanced Concepts)

---

## 📚 Learning Objectives

After completing this chapter, you will be able to utilize advanced features of Python classes. By using special methods, properties, and static methods, you can write more Pythonic and professional object-oriented code.

이번 장을 마치면 여러분은 파이썬 클래스의 고급 기능들을 활용할 수 있습니다. 특수 메서드, 프로퍼티, 정적 메서드 등을 사용하여 더욱 파이썬다운 전문적인 객체지향 코드를 작성할 수 있습니다.

---

## 1️⃣ What are Special Methods? (특수 메서드란?)

Python has special methods that start and end with `__` (two underscores). These are called **magic methods** or **dunder methods** (dunder methods).

파이썬에는 `__`(언더스코어 2개)로 시작하고 끝나는 특별한 메서드들이 있습니다. 이를 **매직 메서드** 또는 **던더 메서드**(dunder methods)라고 부릅니다.

### Why are Special Methods Needed? (왜 특수 메서드가 필요한가?)

They allow you to handle objects like regular functions.

일반 함수처럼 객체를 다룰 수 있게 해줍니다.

```python
# Without special methods (특수 메서드 없이)
class Book:
    def __init__(self, title, price):
        self.title = title
        self.price = price

book = Book("Python", 20000)
print(book)  # <__main__.Book object at 0x...> (meaningless!)

# Using special methods (특수 메서드 사용)
class Book:
    def __init__(self, title, price):
        self.title = title
        self.price = price
  
    def __str__(self):
        return f"{self.title} ({self.price:,} won)"

book = Book("Python", 20000)
print(book)  # Python (20,000 won) (meaningful!)
```

### Frequently Used Special Methods (자주 사용하는 특수 메서드)

**Initialization and Representation (초기화 및 표현)**

- `__init__()`: Called when object is created
  (객체 생성시 호출)
- `__str__()`: Returns string for print()
  (print() 시 문자열 반환)
- `__repr__()`: Returns string for developers
  (개발자용 문자열 반환)
- `__len__()`: Returns length for len()
  (len() 시 길이 반환)

**Comparison Operations (비교 연산)**

- `__eq__()`: == operator (== 연산자)
- `__ne__()`: != operator (!= 연산자)
- `__lt__()`: < operator (< 연산자)
- `__le__()`: <= operator (<= 연산자)
- `__gt__()`: > operator (> 연산자)
- `__ge__()`: >= operator (>= 연산자)

**Arithmetic Operations (산술 연산)**

- `__add__()`: + operator (+ 연산자)
- `__sub__()`: - operator (- 연산자)
- `__mul__()`: * operator (* 연산자)
- `__truediv__()`: / operator (/ 연산자)

---

## 2️⃣ __str__ and __repr__ (__str__과 __repr__)

Define how to represent an object as a string.

객체를 문자열로 표현하는 방법을 정의합니다.

### __str__ - Representation for Users (__str__ - 사용자용 표현)

```python
class Product:
    def __init__(self, name, price, stock):
        self.name = name
        self.price = price
        self.stock = stock
  
    def __str__(self):
        """String to show to users (사용자에게 보여줄 문자열)"""
        return f"{self.name} - {self.price:,} won (Stock: {self.stock})"

product = Product("Laptop", 1500000, 5)
print(product)  # Laptop - 1,500,000 won (Stock: 5)
```

### __repr__ - Representation for Developers (__repr__ - 개발자용 표현)

```python
class Product:
    def __init__(self, name, price, stock):
        self.name = name
        self.price = price
        self.stock = stock
  
    def __str__(self):
        """For users (사용자용)"""
        return f"{self.name} - {self.price:,} won"
  
    def __repr__(self):
        """For developers (debugging) (개발자용 - 디버깅용)"""
        return f"Product('{self.name}', {self.price}, {self.stock})"

product = Product("Mouse", 30000, 10)
print(product)       # Mouse - 30,000 won (__str__)
print(repr(product)) # Product('Mouse', 30000, 10) (__repr__)
```

### __len__ - Custom Length (길이 정의)

```python
class ShoppingCart:
    def __init__(self):
        self.items = []
  
    def add(self, item):
        self.items.append(item)
  
    def __len__(self):
        """Return number of items (상품 개수 반환)"""
        return len(self.items)
  
    def __str__(self):
        return f"Shopping cart with {len(self)} items"

cart = ShoppingCart()
cart.add("Apple")
cart.add("Banana")

print(len(cart))     # 2
print(cart)          # Shopping cart with 2 items
```

### Practice: Create a Date Class (실전: 날짜 클래스 만들기)

```python
class Date:
    def __init__(self, year, month, day):
        self.year = year
        self.month = month
        self.day = day
  
    def __str__(self):
        """User-friendly format (사용자 친화적 형식)"""
        return f"{self.year}-{self.month:02d}-{self.day:02d}"
  
    def __repr__(self):
        """Developer format (개발자 형식)"""
        return f"Date({self.year}, {self.month}, {self.day})"

date = Date(2024, 2, 13)
print(date)         # 2024-02-13
print(repr(date))   # Date(2024, 2, 13)
```

💡 **Tip**: If `__str__` is not defined, `__repr__` is used instead.

💡 **팁**: `__str__`이 없으면 `__repr__`이 사용됩니다.

---

## 3️⃣ Comparison Operator Overloading (비교 연산자 오버로딩)

Make objects comparable in size.

객체끼리 크기를 비교할 수 있게 만듭니다.

### Basic Example (기본 예제)

```python
class Student:
    def __init__(self, name, score):
        self.name = name
        self.score = score
  
    def __eq__(self, other):
        """== operator (== 연산자)"""
        return self.score == other.score
  
    def __lt__(self, other):
        """< operator (< 연산자)"""
        return self.score < other.score
  
    def __le__(self, other):
        """<= operator (<= 연산자)"""
        return self.score <= other.score
  
    def __str__(self):
        return f"{self.name}({self.score} points)"

# Create students (학생 생성)
student1 = Student("Chulsu", 85)
student2 = Student("Younghee", 90)
student3 = Student("Minsu", 85)

# Compare (비교 연산)
print(student1 == student3)  # True (same score - 점수가 같음)
print(student1 < student2)   # True (85 < 90)
print(student1 <= student3)  # True (85 <= 85)

# Sorting is also possible! (정렬도 가능!)
students = [student1, student2, student3]
students.sort()  # Sort by score (점수 순으로 정렬)
for s in students:
    print(s)
```

**Execution Result (실행 결과):**

```
True
True
True
Chulsu(85 points)
Minsu(85 points)
Younghee(90 points)
```

## 4️⃣ Arithmetic Operator Overloading (산술 연산자 오버로딩)

Define operations to add and subtract objects.

객체끼리 더하고 빼는 연산을 정의합니다.

### Basic Example: Vector Class (기본 예제: 벡터 클래스)

```python
class Vector:
    def __init__(self, x, y):
        self.x = x
        self.y = y
  
    def __add__(self, other):
        """Vector addition (벡터 덧셈)"""
        return Vector(self.x + other.x, self.y + other.y)
  
    def __sub__(self, other):
        """Vector subtraction (벡터 뺄셈)"""
        return Vector(self.x - other.x, self.y - other.y)
  
    def __mul__(self, scalar):
        """Scalar multiplication (스칼라 곱)"""
        return Vector(self.x * scalar, self.y * scalar)
  
    def __str__(self):
        return f"({self.x}, {self.y})"

# Vector operations (벡터 연산)
v1 = Vector(3, 4)
v2 = Vector(1, 2)

v3 = v1 + v2  # Calls __add__ (\_\_add\_\_ 호출)
v4 = v1 - v2  # Calls __sub__ (\_\_sub\_\_ 호출)
v5 = v1 * 2   # Calls __mul__ (\_\_mul\_\_ 호출)

print(f"v1 = {v1}")
print(f"v2 = {v2}")
print(f"v1 + v2 = {v3}")
print(f"v1 - v2 = {v4}")
print(f"v1 * 2 = {v5}")
```

**Execution Result (실행 결과):**

```
v1 = (3, 4)
v2 = (1, 2)
v1 + v2 = (4, 6)
v1 - v2 = (2, 2)
v1 * 2 = (6, 8)
```

---

## 5️⃣ Properties (Property) - Safe Attribute Management (프로퍼티 - 안전한 속성 관리)

A property is "a function that looks like a variable on the surface." Why do we need this?

프로퍼티는 "겉으로는 변수처럼 보이지만 실제로는 함수"입니다. 왜 이런 게 필요할까요?

### Problem: Wrong Values Can Be Entered (문제 상황: 잘못된 값이 들어갈 수 있다)

```python
class Person:
    def __init__(self, age):
        self.age = age

person = Person(25)
print(person.age)  # 25

# What if someone accidentally enters a weird value?
# 누군가 실수로 이상한 값을 넣으면?
person.age = -5      # Negative age?! (음수 나이?!)
person.age = 999     # 999 years old?! (999살?!)
person.age = "twenty"  # String?! (문자?!)
```

If you access variables directly like this, strange values can enter and the program can break!

이렇게 변수에 직접 접근하면 이상한 값이 들어갈 수 있습니다. 프로그램이 망가질 수 있죠!

### Solution: Use Properties (해결책: 프로퍼티 사용)

With properties, you can automatically validate when entering values.

프로퍼티를 사용하면 값을 넣을 때 자동으로 검사할 수 있습니다.

```python
class Person:
    def __init__(self, age):
        self._age = age  # _age is internal variable (숨김)
  
    @property
    def age(self):
        """Read age (나이 읽기)"""
        return self._age
  
    @age.setter
    def age(self, value):
        """Write age - validation here! (나이 쓰기 - 여기서 검사!)"""
        if value < 0:
            print("❌ Age cannot be less than 0!")
            return
        if value > 150:
            print("❌ Age is too high!")
            return
        self._age = value

# Use (사용)
person = Person(25)
print(f"Age: {person.age}")  # 25 (read - 읽기)

person.age = 30              # OK! (write - 쓰기)
print(f"Age: {person.age}")  # 30

person.age = -5              # ❌ Age cannot be less than 0!
print(f"Age: {person.age}")  # 30 (not changed - 변경 안 됨!)

person.age = 999             # ❌ Age is too high!
print(f"Age: {person.age}")  # 30 (not changed - 변경 안 됨!)
```

**Key Points (핵심 포인트):**

- `@property`: "Let me read this function like a variable" (`@property`: "이 함수를 변수처럼 읽을 수 있게 해줘")
- `@age.setter`: "Check when writing values" (`@age.setter`: "이 함수로 값을 쓸 때 검사해줘")
- Users can use it like `person.age` as if it's a variable! (사용하는 사람은 `person.age`처럼 그냥 변수처럼 사용!)

### Read-Only Properties (읽기 전용 속성 만들기)

Calculated values can be made read-only.

계산된 값은 읽기만 가능하게 만들 수 있습니다.

```python
class Rectangle:
    def __init__(self, width, height):
        self.width = width
        self.height = height
  
    @property
    def area(self):
        """Area (read-only) (넓이 - 읽기만 가능)"""
        return self.width * self.height

# Use (사용)
rect = Rectangle(10, 5)
print(f"Width: {rect.width}")
print(f"Height: {rect.height}")
print(f"Area: {rect.area}")  # 10 * 5 = 50

# Width/Height can be changed (가로/세로는 변경 가능)
rect.width = 20
print(f"New area: {rect.area}")  # 20 * 5 = 100

# rect.area = 200  # Error! No setter (오류! setter가 없어서 쓰기 불가)
```

The area is automatically calculated as width × height, so no need to change directly!

넓이는 가로 × 세로로 자동 계산되므로 직접 바꿀 필요가 없습니다!

## 6️⃣ Static Methods - Class Toolkit (정적 메서드 - 클래스의 도구함)

A static method is inside a class but is an **independent function unrelated to objects**. It's like a tool you keep in a toolbox and use when needed.

정적 메서드는 클래스 안에 있지만 **객체와 상관없는 독립적인 함수**입니다. 마치 도구 상자에 넣어둔 도구처럼, 필요할 때 꺼내 쓰는 것입니다.

### Why Use Static Methods? (왜 정적 메서드를 사용할까?)

It's convenient to organize and group related functions inside a class.

관련된 함수들을 클래스 안에 정리해서 모아두면 편리합니다.

```python
# Without static methods (functions scattered everywhere)
# 정적 메서드 없이 (함수가 여기저기 흩어짐)
def add(a, b):
    return a + b

def subtract(a, b):
    return a - b

# Using static methods (organized neatly)
# 정적 메서드 사용 (깔끔하게 정리됨)
class Calculator:
    @staticmethod
    def add(a, b):
        """Addition (덧셈)"""
        return a + b
  
    @staticmethod
    def subtract(a, b):
        """Subtraction (뺄셈)"""
        return a - b

# Use without creating an object! (객체 생성 없이 바로 사용!)
print(Calculator.add(10, 5))       # 15
print(Calculator.subtract(10, 5))  # 5
```

**Key Points (핵심 포인트):**

- `@staticmethod`: "This function doesn't need self" (`@staticmethod`: "이 함수는 self가 필요 없어요")
- No need to create objects: `ClassName.function()` (객체 생성 안 해도 됨: `클래스이름.함수이름()`)
- Good for utility function collections! (유틸리티 함수 모음에 좋음!)

### Simple Example 1: String Tools (간단한 예제 1: 문자열 도구)

```python
class StringUtil:
    """String utility (문자열 유틸리티)"""
  
    @staticmethod
    def reverse(text):
        """Reverse string (문자열 뒤집기)"""
        return text[::-1]
  
    @staticmethod
    def count_vowels(text):
        """Count vowels (모음 개수 세기)"""
        vowels = "aeiouAEIOU"
        count = 0
        for char in text:
            if char in vowels:
                count += 1
        return count
  
    @staticmethod
    def is_palindrome(text):
        """Palindrome check (palindrome) (회문 판별 - 거꾸로 읽어도 같은 단어)"""
        text = text.replace(" ", "").lower()
        return text == text[::-1]

# Use without creating an object (객체 생성 없이 바로 사용)
print(StringUtil.reverse("Hello"))           # olleH
print(StringUtil.count_vowels("Python"))     # 1
print(StringUtil.is_palindrome("level"))     # True
print(StringUtil.is_palindrome("python"))    # False
```

## 📝 Key Concepts Summary (핵심 개념 정리)

### Special Methods (특수 메서드)

Methods starting and ending with `__`, linked with operators and built-in functions

`__`로 시작하고 끝나는 메서드, 연산자나 내장 함수와 연동

```python
def __str__(self):         # print()
def __eq__(self, other):   # ==
def __add__(self, other):  # +
def __len__(self):         # len()
```

### Properties (프로퍼티)

Execute method when accessing attributes

속성 접근시 메서드 실행

```python
@property
def name(self):             # Read (읽기)
    return self._name

@name.setter
def name(self, value):      # Write (쓰기)
    self._name = value
```

### Static and Class Methods (정적/클래스 메서드)

```python
@staticmethod
def static_method():    # Independent function (독립 함수)

@classmethod
def class_method(cls):  # Access class variable (클래스 변수 접근)
```

### Quick Reference (빠른 참고)

**Special Methods (특수 메서드)**

- `__str__()`: String representation for users (사용자용)
- `__repr__()`: String representation for developers (개발자용)
- `__eq__()`, `__lt__()`, etc.: Comparison operators (비교 연산자)
- `__add__()`, `__sub__()`, etc.: Arithmetic operators (산술 연산자)
- `__len__()`: Length (길이)

**Decorators (데코레이터)**

- `@property`: Make getter (읽기 함수 만들기)
- `@name.setter`: Make setter (쓰기 함수 만들기)
- `@staticmethod`: Static method (정적 메서드)
- `@classmethod`: Class method (클래스 메서드)

---

## 💡 Practice Assignments (실습 과제)

### Assignment 1: Fraction Class (과제 1: 분수 클래스)

Create a Fraction class that:

- Stores numerator and denominator
- Supports addition with other fractions
- Has a string representation

분수 클래스를 만드세요:

- 분자와 분모 저장
- 다른 분수와 덧셈 지원
- 문자열 표현 제공

```python
# Hint (힌트)
class Fraction:
    def __init__(self, numerator, denominator):
        self.numerator = numerator
        self.denominator = denominator
  
    def __add__(self, other):
        # Fraction addition (분수 덧셈)
        pass
  
    def __str__(self):
        # String representation (문자열 표현)
        pass
```

### Assignment 2: Bank Account with Properties (과제 2: 프로퍼티를 사용한 은행 계좌)

Create a Bank Account class that:

- Uses property for balance
- Validates balance (no negative)
- Tracks transaction history

은행 계좌 클래스를 만드세요:

- 잔액에 프로퍼티 사용
- 잔액 검증 (음수 불가)
- 거래 내역 기록

```python
# Hint (힌트)
class Account:
    def __init__(self, balance):
        self._balance = balance
        self.transactions = []
  
    @property
    def balance(self):
        return self._balance
  
    @balance.setter
    def balance(self, value):
        # Balance validation (잔액 검증)
        if value >= 0:
            self._balance = value
```

---

## ✅ Quiz (퀴즈)

### [Beginner] Question 1

What method is called when using print(obj)?

print(obj) 시 호출되는 메서드는?

```
1. __print__
2. __str__
3. __show__
4. __display__
```

### [Intermediate] Question 2

What is the property decorator?

프로퍼티 데코레이터는?

```
1. @prop
2. @property
3. @getter
4. @attribute
```

### [Intermediate] Question 3

What is the static method decorator?

정적 메서드 데코레이터는?

```
1. @static
2. @staticmethod
3. @classmethod
4. @method
```

### [Advanced] Question 4

What method is called when using obj1 + obj2?

`obj1 + obj2` 시 호출되는 메서드는?

```
1. __plus__
2. __sum__
3. __add__
4. __combine__
```

### [Advanced] Question 5

What method is called when using len(obj)?

`len(obj)` 시 호출되는 메서드는?

```
1. __length__
2. __size__
3. __len__
4. __count__
```

---

## 🔑 Quiz Answers and Explanations (퀴즈 정답 및 해설)

**Answer 1: 2**

The `__str__` method is called when using print().

`__str__` 메서드가 print() 시 호출됩니다.

**Answer 2: 2**

The `@property` decorator creates a property.

`@property` 데코레이터로 프로퍼티를 만듭니다.

**Answer 3: 2**

The `@staticmethod` decorator creates a static method.

`@staticmethod` 데코레이터로 정적 메서드를 만듭니다.

**Answer 4: 3**

The `__add__` method handles the + operator.

`__add__` 메서드가 + 연산자를 처리합니다.

**Answer 5: 3**

The `__len__` method handles the len() function.

`__len__` 메서드가 len() 함수를 처리합니다.

---

## 🎯 Next Chapter Preview (다음 장 예고)

In the next chapter, we'll learn GUI programming. You'll be able to create window programs with buttons, text boxes, and more using tkinter!

다음 장에서는 GUI 프로그래밍을 배웁니다. tkinter를 사용하여 버튼, 텍스트 상자 등이 있는 윈도우 프로그램을 만들 수 있게 됩니다!

---

Thank you for your attention.

Prof. Cho Jeonghyun (peterchokr@gmail.com)
Yeungnam University College
