# Chapter 17. Classes 1 (Basics)

---

## 📚 Learning Objectives

After completing this chapter, you will understand and use classes, the foundation of object-oriented programming. Through classes, you can bundle data and functionality together to write more systematic and reusable code.

이번 장을 마치면 여러분은 객체지향 프로그래밍의 기초인 클래스를 이해하고 사용할 수 있습니다. 클래스를 통해 데이터와 기능을 하나로 묶어 더욱 체계적이고 재사용 가능한 코드를 작성할 수 있습니다.

---

## 1️⃣ What is a Class? (클래스란 무엇인가?)

So far, we've created functions to reuse code. But as programs become more complex, functions alone are insufficient. For example, let's imagine creating characters in a game.

지금까지 우리는 함수를 만들어 코드를 재사용했습니다. 하지만 프로그램이 복잡해지면 함수만으로는 부족합니다. 예를 들어, 게임에서 캐릭터를 만든다고 생각해봅시다.

```python
# Using functions only (inconvenient!) (함수만 사용한 방식 - 불편함!)
player_name = "Warrior"
player_health = 100
player_level = 1

def attack():
    print(f"{player_name} attacks!")

def heal():
    global player_health
    player_health += 20
```

What happens as characters multiply to 2, 3, or more? The number of variables grows tremendously and becomes difficult to manage. This is when we need **classes (Class)**!

캐릭터가 2명, 3명으로 늘어나면 어떻게 될까요? 변수가 엄청나게 많아지고 관리하기 힘들어집니다. 이럴 때 **클래스(Class)**가 필요합니다!

### A Class is a Blueprint (클래스는 설계도다)

A class is like a fish-cake mold. Just as you can make multiple fish cakes with a mold, you can create multiple objects from a class.

클래스는 마치 붕어빵 틀과 같습니다. 틀로 여러 개의 붕어빵을 만들 수 있듯이, 클래스로 여러 개의 객체를 만들 수 있습니다.

### Real-World Analogy (실생활 비유)

- **Car design** = Class
  **자동차 설계도** = 클래스
  
- **My car, your car** = Objects
  **내 자동차, 네 자동차** = 객체
  
- **Smartphone model** = Class
  **스마트폰 모델** = 클래스
  
- **My iPhone, your iPhone** = Objects
  **내 아이폰, 네 아이폰** = 객체
  
- **Person** = Class
  **사람** = 클래스
  
- **Hong Gildong, Kim Chulsu** = Objects
  **홍길동, 김철수** = 객체

### Components of a Class (클래스의 구성 요소)

A class consists of two main parts:

클래스는 크게 두 가지로 구성됩니다:

**1. Attributes (속성)**: Data, characteristics
**1. 속성(Attribute)**: 데이터, 특징

- Car → color, speed, brand
  자동차 → 색상, 속도, 브랜드
  
- Person → name, age, height
  사람 → 이름, 나이, 키

**2. Methods (메서드)**: Actions, functions
**2. 메서드(Method)**: 동작, 기능

- Car → start(), stop(), accelerate()
  자동차 → 출발하다(), 정지하다(), 가속하다()
  
- Person → eat(), sleep(), walk()
  사람 → 먹다(), 자다(), 걷다()

---

## 2️⃣ Creating Your First Class (첫 번째 클래스 만들기)

Let's start with the simplest class.

가장 간단한 클래스부터 만들어봅시다.

### Basic Syntax (기본 문법)

```python
class ClassName:
    pass  # Empty for now (일단 비워둠)
```

⚠️ **Warning**: By convention, class names start with a **capital letter** (PascalCase)

⚠️ **주의**: 클래스 이름은 **대문자로 시작**하는 것이 관례입니다 (PascalCase)

### Creating a Dog Class (Dog 클래스 만들기)

```python
# Define Dog class (강아지 클래스 정의)
class Dog:
    pass

# Create objects (instances) (객체 생성 - 인스턴스 만들기)
my_dog = Dog()
your_dog = Dog()

print(type(my_dog))  # <class '__main__.Dog'>
print(my_dog)        # <__main__.Dog object at 0x...>
```

We've created our own type with no functionality yet!

아직 아무 기능도 없지만, 우리만의 타입을 만들었습니다!

### Understanding __init__ (초기화 메서드 이해하기)

When we create an object, we often want to initialize it with some data. Use the **__init__** method for this.

객체를 생성할 때 초기 데이터를 설정하고 싶을 때가 있습니다. 이때 **__init__** 메서드를 사용합니다.

```python
# Dog class with initialization (초기화가 있는 Dog 클래스)
class Dog:
    def __init__(self, name):
        """Initialize dog with name (강아지를 이름으로 초기화)"""
        self.name = name

# Create dogs with names (이름을 가진 강아지 생성)
my_dog = Dog("Buddy")
your_dog = Dog("Max")

print(my_dog.name)   # Buddy
print(your_dog.name) # Max
```

**What is self?**

`self` represents the object itself. When we say `self.name = name`, we're saving the name **in that specific object**.

**self란 무엇인가?**

`self`는 객체 자신을 나타냅니다. `self.name = name`은 그 객체에만 이름을 저장한다는 의미입니다.

### Example: Person Class (예제: 사람 클래스)

```python
# Person class (사람 클래스)
class Person:
    def __init__(self, name, age):
        """Initialize person (사람 초기화)"""
        self.name = name
        self.age = age

# Create people (사람들 생성)
alice = Person("Alice", 25)
bob = Person("Bob", 30)

print(f"{alice.name} is {alice.age} years old")  # Alice is 25 years old
print(f"{bob.name} is {bob.age} years old")      # Bob is 30 years old
```

Each object has its own data! Alice's name and age are independent of Bob's.

각 객체는 자신만의 데이터를 가집니다! Alice의 이름과 나이는 Bob의 것과 독립적입니다!

---
## 3️⃣ Adding Attributes (속성 추가하기)

Let's store data in a class.

클래스에 데이터를 저장해봅시다.

### Method 1: Adding Attributes Directly (방법 1: 직접 속성 추가)

```python
class Dog:
    pass

# Create object (객체 생성)
my_dog = Dog()

# Add attributes (속성 추가)
my_dog.name = "Buddy"
my_dog.age = 3
my_dog.breed = "Golden Retriever"

# Use (사용)
print(f"Name: {my_dog.name}")
print(f"Age: {my_dog.age} years")
print(f"Breed: {my_dog.breed}")
```

However, this method is inconvenient because you must add attributes one by one each time.

하지만 이 방법은 매번 속성을 일일이 추가해야 해서 불편합니다.

### Method 2: __init__ Constructor (Recommended) (방법 2: __init__ 생성자 - 권장)

`__init__` is a special method that automatically runs when creating an object.

`__init__`은 객체를 만들 때 자동으로 실행되는 특별한 메서드입니다.

```python
class Dog:
    def __init__(self, name, age, breed):
        """Constructor: Initialize object (생성자: 객체를 초기화)"""
        self.name = name
        self.age = age
        self.breed = breed

# Pass values when creating object (객체 생성할 때 값 전달)
my_dog = Dog("Buddy", 3, "Golden Retriever")
your_dog = Dog("Max", 5, "Shiba Inu")

# Use (사용)
print(f"{my_dog.name} is {my_dog.age} years old {my_dog.breed}")
print(f"{your_dog.name} is {your_dog.age} years old {your_dog.breed}")
```

**Execution Result (실행 결과):**

```
Buddy is 3 years old Golden Retriever
Max is 5 years old Shiba Inu
```

### What is self? (self가 뭔가요?)

`self` means "myself." It's a variable that refers to the object itself.

`self`는 "나 자신"을 의미합니다. 객체 자기 자신을 가리키는 변수입니다.

```python
class Dog:
    def __init__(self, name, age):
        self.name = name  # My (this object's) name (나 - 이 객체의 이름)
        self.age = age    # My (this object's) age (나 - 이 객체의 나이)

dog1 = Dog("Buddy", 3)
# self refers to dog1
# dog1.name = "Buddy"
# dog1.age = 3

dog2 = Dog("Max", 5)
# self refers to dog2
# dog2.name = "Max"
# dog2.age = 5
```

**Key Point (핵심)**: `self` refers to the object itself that called the method!

💡 **핵심**: `self`는 메서드를 호출한 객체 자신을 의미합니다!

---

## 4️⃣ Adding Methods (메서드 추가하기)

Now let's add functionality (methods) to the class.

이제 클래스에 기능(메서드)을 추가해봅시다.

### Basic Methods (기본 메서드)

```python
class Dog:
    def __init__(self, name, age):
        self.name = name
        self.age = age
  
    def bark(self):
        """Bark (짖기)"""
        print(f"{self.name}: Woof woof!")
  
    def info(self):
        """Print information (정보 출력)"""
        print(f"Name: {self.name}, Age: {self.age} years")

# Use (사용)
my_dog = Dog("Buddy", 3)
my_dog.bark()   # Buddy: Woof woof!
my_dog.info()   # Name: Buddy, Age: 3 years
```

### Methods with Parameters (매개변수가 있는 메서드)

```python
class Dog:
    def __init__(self, name, age):
        self.name = name
        self.age = age
        self.energy = 100
  
    def play(self, minutes):
        """Play (놀기)"""
        self.energy -= minutes
        print(f"{self.name} played for {minutes} minutes.")
        print(f"Remaining energy: {self.energy}")
  
    def sleep(self, hours):
        """Sleep (자기)"""
        recovered = hours * 10
        self.energy += recovered
        if self.energy > 100:
            self.energy = 100
        print(f"{self.name} slept for {hours} hours.")
        print(f"Current energy: {self.energy}")

# Use (사용)
dog = Dog("Buddy", 3)
dog.play(30)    # Energy decreases by 30 (에너지 30 감소)
dog.sleep(5)    # Energy recovers 50 (에너지 50 회복)
```

### Understanding Methods (메서드 이해하기)

Methods are functions inside classes. They can:
1. Access and modify object attributes using `self`
2. Take parameters to work with specific data
3. Return values

메서드는 클래스 안에 있는 함수입니다. 메서드는:
1. `self`를 사용하여 객체의 속성에 접근하고 수정할 수 있습니다
2. 매개변수를 받아 특정 데이터로 작업할 수 있습니다
3. 값을 반환할 수 있습니다

### Methods that Return Values (값을 반환하는 메서드)

```python
class Calculator:
    def __init__(self, number):
        self.number = number
  
    def double(self):
        """Return double of number (숫자를 2배로 반환)"""
        return self.number * 2
  
    def square(self):
        """Return square of number (숫자를 제곱하여 반환)"""
        return self.number ** 2

calc = Calculator(5)
print(calc.double())  # 10
print(calc.square())  # 25
```

---
## 5️⃣ Practical Example: Student Class (실전 예제: 학생 클래스)

Let's create a student management system.

학생 관리 시스템을 만들어봅시다.

```python
class Student:
    """Student class (학생 클래스)"""
  
    def __init__(self, name, student_id, grade):
        """Constructor (생성자)"""
        self.name = name
        self.student_id = student_id
        self.grade = grade
        self.scores = []  # Score list (성적 리스트)
  
    def add_score(self, subject, score):
        """Add score (성적 추가)"""
        self.scores.append({
            "subject": subject,
            "score": score
        })
        print(f"✓ {subject}: {score} points added")
  
    def get_average(self):
        """Calculate average (평균 계산)"""
        if len(self.scores) == 0:
            return 0
    
        total = sum(s["score"] for s in self.scores)
        return total / len(self.scores)
  
    def show_info(self):
        """Print information (정보 출력)"""
        print("\n" + "=" * 40)
        print(f"📚 Student Information")
        print("=" * 40)
        print(f"Name: {self.name}")
        print(f"Student ID: {self.student_id}")
        print(f"Grade: {self.grade}")
        print("\n📊 Scores:")
    
        if len(self.scores) == 0:
            print("  No registered scores.")
        else:
            for s in self.scores:
                print(f"  {s['subject']}: {s['score']} points")
        
            avg = self.get_average()
            print(f"\nAverage: {avg:.1f} points")
    
        print("=" * 40)

# Create student (학생 생성)
student = Student("Chulsu", "2024001", 1)

# Add scores (성적 추가)
student.add_score("Korean", 85)
student.add_score("English", 90)
student.add_score("Math", 78)

# Print information (정보 출력)
student.show_info()
```

**Execution Result (실행 결과):**

```
✓ Korean: 85 points added
✓ English: 90 points added
✓ Math: 78 points added

========================================
📚 Student Information
========================================
Name: Chulsu
Student ID: 2024001
Grade: 1

📊 Scores:
  Korean: 85 points
  English: 90 points
  Math: 78 points

Average: 84.3 points
========================================
```

---

## 6️⃣ Practical Example: Bank Account Class (실전 예제: 은행 계좌 클래스)

Let's create a bank account with deposit and withdrawal capabilities.

입출금이 가능한 은행 계좌를 만들어봅시다.

```python
class BankAccount:
    """Bank account class (은행 계좌 클래스)"""
  
    def __init__(self, owner, balance=0):
        """
        Constructor (생성자)
        owner: Account owner (계좌 소유자)
        balance: Initial balance, default 0 (초기 잔액 - 기본값 0)
        """
        self.owner = owner
        self.balance = balance
        self.transactions = []  # Transaction history (거래 내역)
    
        # Account opening record (계좌 개설 기록)
        self.transactions.append(f"Account opened (Initial balance: {balance:,})")
  
    def deposit(self, amount):
        """Deposit (입금)"""
        if amount <= 0:
            print("❌ Deposit amount must be greater than 0.")
            return False
    
        self.balance += amount
        self.transactions.append(f"Deposit: +{amount:,}")
        print(f"✓ {amount:,} deposited successfully")
        print(f"Balance: {self.balance:,}")
        return True
  
    def withdraw(self, amount):
        """Withdraw (출금)"""
        if amount <= 0:
            print("❌ Withdrawal amount must be greater than 0.")
            return False
    
        if amount > self.balance:
            print(f"❌ Insufficient balance. (Balance: {self.balance:,})")
            return False
    
        self.balance -= amount
        self.transactions.append(f"Withdrawal: -{amount:,}")
        print(f"✓ {amount:,} withdrawn successfully")
        print(f"Balance: {self.balance:,}")
        return True
  
    def get_balance(self):
        """Check balance (잔액 조회)"""
        return self.balance
  
    def show_transactions(self):
        """Print transaction history (거래 내역 출력)"""
        print("\n" + "=" * 40)
        print(f"💳 {self.owner}'s Transaction History")
        print("=" * 40)
    
        for i, transaction in enumerate(self.transactions, 1):
            print(f"{i}. {transaction}")
    
        print("-" * 40)
        print(f"Current Balance: {self.balance:,}")
        print("=" * 40)

# Create account (계좌 생성)
account = BankAccount("Hong", 10000)

print("\n💰 Bank Account System")
print()

# Deposit (입금)
account.deposit(50000)
print()

# Withdraw (출금)
account.withdraw(20000)
print()

# Failed withdrawal (출금 실패 - 잔액 부족)
account.withdraw(100000)
print()

# Check transaction history (거래 내역 확인)
account.show_transactions()
```

**Execution Result (실행 결과):**

```
💰 Bank Account System

✓ 50,000 deposited successfully
Balance: 60,000

✓ 20,000 withdrawn successfully
Balance: 40,000

❌ Insufficient balance. (Balance: 40,000)

========================================
💳 Hong's Transaction History
========================================
1. Account opened (Initial balance: 10,000)
2. Deposit: +50,000
3. Withdrawal: -20,000
----------------------------------------
Current Balance: 40,000
========================================
```

---

## 7️⃣ Class Variables vs Instance Variables (클래스 변수 vs 인스턴스 변수)

There are two types of variables.

변수에는 두 종류가 있습니다.

### Instance Variables: Different values for each object (인스턴스 변수: 객체마다 다른 값)

```python
class Dog:
    def __init__(self, name):
        self.name = name  # Instance variable (인스턴스 변수)

dog1 = Dog("Buddy")
dog2 = Dog("Max")

print(dog1.name)  # Buddy
print(dog2.name)  # Max
```

Each dog has its own name. Dog1's name is different from Dog2's.

각 개는 자신만의 이름을 가집니다. dog1의 이름은 dog2와 다릅니다.

### Class Variables: Values shared by all objects (클래스 변수: 모든 객체가 공유하는 값)

```python
class Dog:
    species = "Canis familiaris"  # Class variable (클래스 변수 - 모든 개가 공유)
  
    def __init__(self, name):
        self.name = name  # Instance variable (인스턴스 변수 - 개마다 다름)

dog1 = Dog("Buddy")
dog2 = Dog("Max")

print(dog1.species)  # Canis familiaris
print(dog2.species)  # Canis familiaris (same value - 같은 값)

print(dog1.name)  # Buddy
print(dog2.name)  # Max (different values - 다른 값)
```

### Practical Example: Game Character (실전 예제: 게임 캐릭터)

```python
class Character:
    # Class variable (클래스 변수)
    total_characters = 0  # Number of created characters (생성된 캐릭터 수)
  
    def __init__(self, name, job):
        # Instance variables (인스턴스 변수)
        self.name = name
        self.job = job
        self.level = 1
        self.hp = 100
    
        # Increment count when character is created (캐릭터 생성시 카운트 증가)
        Character.total_characters += 1
  
    def info(self):
        print(f"{self.name} ({self.job}) - Lv.{self.level}")
  
    @classmethod
    def get_total(cls):
        """Return total number of characters (전체 캐릭터 수 반환)"""
        return cls.total_characters

# Create characters (캐릭터 생성)
char1 = Character("Warrior", "Warrior")
char2 = Character("Mage", "Mage")
char3 = Character("Archer", "Archer")

# Print information (정보 출력)
char1.info()
char2.info()
char3.info()

print(f"\nTotal {Character.get_total()} characters created.")
```

**Execution Result (실행 결과):**

```
Warrior (Warrior) - Lv.1
Mage (Mage) - Lv.1
Archer (Archer) - Lv.1

Total 3 characters created.
```

---
## 📝 Key Concepts Summary (핵심 개념 정리)

### Classes and Objects (클래스와 객체)

- **Class**: Blueprint (설계도 - 붕어빵 틀)
- **Object**: Actual product (실제 제품 - 붕어빵)

### Creating a Class (클래스 만들기)

```python
class ClassName:
    def __init__(self, params):
        self.attribute = value
  
    def method(self):
        # Implement functionality (기능 구현)
        pass
```

### Key Terminology (핵심 용어)

- `__init__`: Constructor, initializes object (생성자, 객체 초기화)
- `self`: Refers to the object itself (객체 자신을 가리킴)
- **Attribute (속성)**: Data (데이터)
- **Method (메서드)**: Functionality (기능)

### Types of Variables (변수 종류)

- **Instance variable**: `self.name` (different for each object - 객체마다 다름)
- **Class variable**: `ClassName.count` (shared by all objects - 모든 객체가 공유)

### Best Practices (모범 사례)

- Class names should start with capital letter (PascalCase)
  클래스 이름은 대문자로 시작해야 합니다 (PascalCase)
  
- Use descriptive names for attributes and methods
  속성과 메서드에는 설명적인 이름을 사용하세요
  
- Keep __init__ simple - initialize data, not complex logic
  __init__은 간단하게 - 데이터 초기화만 하세요

---

## 💡 Practice Assignments (실습 과제)

### Assignment 1: Car Class (과제 1: 자동차 클래스)

Create a Car class with the following:
- Attributes: brand, model, speed
- Methods: accelerate(amount), brake(amount)
- Constraint: speed cannot go below 0 or above 200

다음을 포함하는 Car 클래스를 만드세요:
- 속성: brand, model, speed
- 메서드: accelerate(amount), brake(amount)
- 제약: speed는 0 이상 200 이하여야 함

```python
# Hint (힌트)
class Car:
    def __init__(self, brand, model):
        self.brand = brand
        self.model = model
        self.speed = 0
  
    def accelerate(self, amount):
        # Increase speed (가속)
        pass
  
    def brake(self, amount):
        # Decrease speed (감속)
        pass
    
    def get_speed(self):
        return self.speed
```

### Assignment 2: Shopping Cart Class (과제 2: 쇼핑 카트 클래스)

Create a ShoppingCart class with:
- Method: add_item(name, price, quantity)
- Method: remove_item(name)
- Method: get_total() - calculates total price
- Store items in a list

ShoppingCart 클래스를 만드세요:
- 메서드: add_item(name, price, quantity)
- 메서드: remove_item(name)
- 메서드: get_total() - 총 금액 계산
- 리스트에 상품 저장

```python
# Hint (힌트)
class ShoppingCart:
    def __init__(self):
        self.items = []
  
    def add_item(self, name, price, quantity):
        # Add item (상품 추가)
        pass
  
    def remove_item(self, name):
        # Remove item (상품 제거)
        pass
  
    def get_total(self):
        # Calculate total price (총 금액 계산)
        pass
```

---

## ✅ Quiz (퀴즈)

### [Beginner] Question 1

What keyword defines a class?

클래스를 정의하는 키워드는?

```
1. def
2. class
3. function
4. object
```

### [Intermediate] Question 2

What method initializes an object?

객체를 초기화하는 메서드는?

```
1. __new__
2. __start__
3. __init__
4. __create__
```

### [Intermediate] Question 3

What is the role of self?

self의 역할은?

```
1. The class itself (클래스 자체)
2. The object itself (객체 자신)
3. Method name (메서드 이름)
4. Variable type (변수 타입)
```

### [Advanced] Question 4

What is the output of this code?

다음 코드의 실행 결과는?

```python
class Dog:
    def __init__(self, name):
        self.name = name

dog = Dog("Buddy")
print(dog.name)
```

```
1. Dog
2. Buddy
3. name
4. Error 
```

### [Advanced] Question 5

What is the characteristic of a class variable?

클래스 변수의 특징은?

```
1. Different value for each object (객체마다 다른 값)
2. Shared by all objects (모든 객체가 공유)
3. Used only inside methods (메서드 안에서만 사용)
4. Cannot be changed (변경 불가능)
```

---

## 🔑 Quiz Answers and Explanations (퀴즈 정답 및 해설)

**Answer 1: 2**

The `class` keyword defines a class.

`class` 키워드로 클래스를 정의합니다.

**Answer 2: 3**

The `__init__` method is automatically called when an object is created and handles initialization.

`__init__` 메서드가 객체 생성 시 자동으로 호출되어 초기화를 담당합니다.

**Answer 3: 2**

`self` refers to the object itself that called the method.

`self`는 메서드를 호출한 객체 자신을 가리킵니다.

**Answer 4: 2**

`dog.name` prints "Buddy".

`dog.name`은 "Buddy"를 출력합니다.

**Answer 5: 2**

A class variable is a variable shared by all objects of the class.

클래스 변수는 클래스의 모든 객체가 공유하는 변수입니다.

---

## 🎯 Next Chapter Preview (다음 장 예고)

In the next chapter, we'll learn about advanced class features such as inheritance and method overriding. By extending and reusing existing classes, you'll be able to do more powerful object-oriented programming!

다음 장에서는 클래스의 고급 기능인 상속과 메서드 오버라이딩에 대해 배웁니다. 기존 클래스를 확장하고 재사용하여 더욱 강력한 객체지향 프로그래밍을 할 수 있게 됩니다!

---

Thank you for your attention.

Prof. Cho Jeonghyun (peterchokr@gmail.com)   
Yeungnam University College
