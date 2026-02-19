# Chapter 18. Classes 2 (Inheritance and Methods)

---

## 📚 Learning Objectives

After completing this chapter, you will be able to extend and reuse existing classes through inheritance. By utilizing method overriding and the super() function, you can write more flexible and powerful object-oriented programs.

이번 장을 마치면 여러분은 상속을 통해 기존 클래스를 확장하고 재사용할 수 있습니다. 메서드 오버라이딩과 super() 함수를 활용하여 더욱 유연하고 강력한 객체지향 프로그램을 작성할 수 있습니다.

---

## 1️⃣ What is Inheritance? (상속이란 무엇인가?)

Last time we learned how to create classes. But what if we need to create multiple similar classes?

지난 시간에 클래스를 만드는 방법을 배웠습니다. 하지만 비슷한 클래스를 여러 개 만들어야 한다면 어떻게 해야 할까요?

```python
# Inefficient way - code duplication! (비효율적인 방법 - 코드 중복!)
class Dog:
    def __init__(self, name, age):
        self.name = name
        self.age = age
  
    def eat(self):
        print(f"{self.name} is eating.")

class Cat:
    def __init__(self, name, age):
        self.name = name
        self.age = age
  
    def eat(self):
        print(f"{self.name} is eating.")
```

Both dogs and cats are animals with common features (name, age, eating). Copying this common code every time is inefficient. This is where **inheritance (Inheritance)** comes in!

개와 고양이는 둘 다 동물이고, 공통된 특징(이름, 나이, 먹기)을 가지고 있습니다. 이런 공통 부분을 매번 복사하는 것은 비효율적입니다. 이럴 때 **상속(Inheritance)**을 사용합니다!

### Inheritance is a Parent-Child Relationship (상속은 부모-자식 관계다)

Inheritance is like parents passing down property to their children - existing classes (parents) pass their attributes and methods to new classes (children).

상속은 마치 부모가 자식에게 재산을 물려주듯이, 기존 클래스(부모)의 속성과 메서드를 새로운 클래스(자식)가 물려받는 것입니다.

### Real-World Analogy (실생활 비유)

```
Classification System (분류 체계)

Organism
 └─ Animal
     ├─ Mammal
     │   ├─ Dog
     │   ├─ Cat
     │   └─ Human
     └─ Bird
         ├─ Sparrow
         └─ Eagle
```

Characteristics of higher classifications are inherited by lower classifications:

상위 분류의 특성을 하위 분류가 물려받습니다:

- All animals eat, sleep, and move
  모든 동물은 먹고, 자고, 움직인다
  
- All mammals have fur and give birth
  모든 포유류는 털이 있고, 새끼를 낳는다
  
- Dogs bark, cats meow (each has its own characteristics)
  개는 짖고, 고양이는 야옹거린다 (각자의 특징)

### Benefits of Inheritance (상속의 장점)

**1. Code Reuse**: Write common code in one place only
1. 코드 재사용: 공통 코드를 한 곳에만 작성

**2. Easy Maintenance**: If modification is needed, only modify parent class
2. 유지보수 용이: 수정이 필요하면 부모 클래스만 수정

**3. Hierarchical Structure**: Logically organized and systematic structure
3. 계층 구조: 논리적으로 체계적인 구조

**4. Extensibility**: Add functionality without touching existing code
4. 확장성: 기존 코드를 건드리지 않고 기능 추가

---

## 2️⃣ Inheritance Basics (상속 기본 문법)

When defining a class, specify the parent class in parentheses.

상속은 클래스 정의할 때 괄호 안에 부모 클래스를 지정합니다.

### Basic Form (기본 형태)

```python
class ParentClass:
    # Parent class content (부모 클래스 내용)
    pass

class ChildClass(ParentClass):
    # Child class content (자식 클래스 내용)
    pass
```

### Simple Example (간단한 예제)

```python
# Parent class (부모 클래스)
class Animal:
    def __init__(self, name, age):
        self.name = name
        self.age = age
  
    def eat(self):
        print(f"{self.name} is eating.")
  
    def sleep(self):
        print(f"{self.name} is sleeping.")

# Child class 1 (자식 클래스 1)
class Dog(Animal):
    def bark(self):
        print(f"{self.name}: Woof woof!")

# Child class 2 (자식 클래스 2)
class Cat(Animal):
    def meow(self):
        print(f"{self.name}: Meow~")

# Use (사용)
dog = Dog("Buddy", 3)
dog.eat()    # Can use parent method! (부모 메서드 사용 가능!)
dog.sleep()  # Can use parent method! (부모 메서드 사용 가능!)
dog.bark()   # Own method (자식만의 메서드)

cat = Cat("Whiskers", 2)
cat.eat()    # Can use parent method! (부모 메서드 사용 가능!)
cat.meow()   # Own method (자식만의 메서드)
```

**Execution Result (실행 결과):**

```
Buddy is eating.
Buddy is sleeping.
Buddy: Woof woof!
Whiskers is eating.
Whiskers: Meow~
```

The child class automatically inherited the parent class methods!

자식 클래스가 부모 클래스의 메서드를 자동으로 물려받았습니다!

### How Inheritance Works (상속의 원리)

When you create a child class object:
1. The child class inherits all attributes and methods from parent
2. The child can use parent's methods directly
3. The child can add its own unique methods
4. When you call a method on the child object, Python first looks in child class, then parent class

자식 클래스 객체를 생성할 때:
1. 자식 클래스는 부모의 모든 속성과 메서드를 상속받습니다
2. 자식은 부모의 메서드를 직접 사용할 수 있습니다
3. 자식은 자신만의 고유 메서드를 추가할 수 있습니다
4. 메서드를 호출하면 Python은 먼저 자식 클래스에서, 없으면 부모 클래스에서 찾습니다

---
## 3️⃣ Adding Functionality in Child Class (자식 클래스에서 기능 추가하기)

The child class inherits everything from the parent while being able to add its own attributes and methods.

자식 클래스는 부모의 모든 것을 물려받으면서, 자신만의 속성과 메서드를 추가할 수 있습니다.

### Adding Attributes (속성 추가하기)

```python
class Animal:
    def __init__(self, name, age):
        self.name = name
        self.age = age

class Dog(Animal):
    def __init__(self, name, age, breed):
        # Must call parent's __init__! (부모의 __init__ 호출 필요!)
        Animal.__init__(self, name, age)
        # Or: super().__init__(name, age)
      
        # Add child's own attributes (자식만의 속성 추가)
        self.breed = breed
  
    def info(self):
        print(f"{self.name} ({self.breed}) - {self.age} years old")

dog = Dog("Buddy", 3, "Golden Retriever")
dog.info()  # Buddy (Golden Retriever) - 3 years old
```

### Adding Methods (메서드 추가하기)

```python
class Vehicle:
    """Vehicle (parent class) (탈것 - 부모 클래스)"""
  
    def __init__(self, brand, model):
        self.brand = brand
        self.model = model
        self.speed = 0
  
    def start(self):
        print(f"{self.brand} {self.model} starting engine")
  
    def stop(self):
        print(f"{self.brand} {self.model} stopping engine")

class Car(Vehicle):
    """Car (child class) (자동차 - 자식 클래스)"""
  
    def __init__(self, brand, model, fuel_type):
        super().__init__(brand, model)  # Initialize parent (부모 초기화)
        self.fuel_type = fuel_type
        self.trunk_open = False
  
    def open_trunk(self):
        """Open trunk (Car's unique feature) (트렁크 열기 - 자동차만의 기능)"""
        self.trunk_open = True
        print("Trunk opened.")
  
    def close_trunk(self):
        """Close trunk (트렁크 닫기)"""
        self.trunk_open = False
        print("Trunk closed.")

class Motorcycle(Vehicle):
    """Motorcycle (child class) (오토바이 - 자식 클래스)"""
  
    def __init__(self, brand, model, helmet_storage):
        super().__init__(brand, model)
        self.helmet_storage = helmet_storage
  
    def wheelie(self):
        """Front wheel lift (Motorcycle's unique feature) (앞바퀴 들기 - 오토바이만의 기능)"""
        print("Front wheel lifted!")

# Use (사용)
car = Car("Hyundai", "Sonata", "Gasoline")
car.start()        # Parent method (부모 메서드)
car.open_trunk()   # Child method (자식 메서드)
car.close_trunk()  # Child method (자식 메서드)
car.stop()         # Parent method (부모 메서드)

print()

bike = Motorcycle("Yamaha", "R1", True)
bike.start()   # Parent method (부모 메서드)
bike.wheelie() # Child method (자식 메서드)
bike.stop()    # Parent method (부모 메서드)
```

**Execution Result (실행 결과):**

```
Hyundai Sonata starting engine
Trunk opened.
Trunk closed.
Hyundai Sonata stopping engine

Yamaha R1 starting engine
Front wheel lifted!
Yamaha R1 stopping engine
```

---

## 4️⃣ Method Overriding (메서드 오버라이딩 - 재정의)

In a child class, you can **redefine** the parent's method. When creating a method with the same name, the child's version takes priority.

자식 클래스에서 부모의 메서드를 **다시 정의**할 수 있습니다. 같은 이름의 메서드를 만들면 자식 것이 우선됩니다.

### Why Overriding is Needed (왜 오버라이딩이 필요한가?)

When the parent's default behavior doesn't fit the child, you modify and use it.

부모의 기본 동작이 자식에게 맞지 않을 때 수정해서 사용합니다.

```python
class Animal:
    def __init__(self, name):
        self.name = name
  
    def speak(self):
        print(f"{self.name} makes a sound.")

class Dog(Animal):
    def speak(self):  # Overriding (오버라이딩)
        print(f"{self.name}: Woof woof!")

class Cat(Animal):
    def speak(self):  # Overriding (오버라이딩)
        print(f"{self.name}: Meow~")

class Cow(Animal):
    def speak(self):  # Overriding (오버라이딩)
        print(f"{self.name}: Moo~")

# Use (사용)
animals = [
    Dog("Buddy"),
    Cat("Whiskers"),
    Cow("Bessie")
]

for animal in animals:
    animal.speak()  # Each executes its own speak() (각자의 speak() 실행)
```

**Execution Result (실행 결과):**

```
Buddy: Woof woof!
Whiskers: Meow~
Bessie: Moo~
```

Same `speak()` method was called, but different results because each class overrode it!

같은 `speak()` 메서드를 호출했지만, 각 클래스에서 오버라이딩했기 때문에 다른 결과가 나옵니다!

### Practical Example: Employee Management (실전 예제: 직원 관리)

```python
class Employee:
    """Employee (parent class) (직원 - 부모 클래스)"""
  
    def __init__(self, name, emp_id, base_salary):
        self.name = name
        self.emp_id = emp_id
        self.base_salary = base_salary
  
    def get_salary(self):
        """Calculate salary (급여 계산)"""
        return self.base_salary
  
    def info(self):
        """Print information (정보 출력)"""
        print(f"{self.name} (ID: {self.emp_id})")
        print(f"Salary: {self.get_salary():,} won")

class Manager(Employee):
    """Manager (child class) (관리자 - 자식 클래스)"""
  
    def __init__(self, name, emp_id, base_salary, team_size):
        super().__init__(name, emp_id, base_salary)
        self.team_size = team_size
  
    def get_salary(self):  # Overriding (오버라이딩)
        """Add manager allowance (관리자 수당 추가)"""
        bonus = self.team_size * 100000
        return self.base_salary + bonus
  
    def info(self):  # Overriding (오버라이딩)
        super().info()  # Call parent method (부모 메서드 호출)
        print(f"Team size: {self.team_size} people")

class Developer(Employee):
    """Developer (child class) (개발자 - 자식 클래스)"""
  
    def __init__(self, name, emp_id, base_salary, language):
        super().__init__(name, emp_id, base_salary)
        self.language = language
  
    def get_salary(self):  # Overriding (오버라이딩)
        """Add tech allowance (기술 수당 추가)"""
        tech_bonus = 500000
        return self.base_salary + tech_bonus
  
    def info(self):  # Overriding (오버라이딩)
        super().info()
        print(f"Main language: {self.language}")

# Create employees (직원 생성)
employees = [
    Employee("Chulsu", "E001", 3000000),
    Manager("Younghee", "M001", 4000000, 5),
    Developer("Minsu", "D001", 3500000, "Python")
]

# Print information (정보 출력)
for emp in employees:
    print("\n" + "=" * 40)
    emp.info()
```

**Execution Result (실행 결과):**

```
========================================
Chulsu (ID: E001)
Salary: 3,000,000 won

========================================
Younghee (ID: M001)
Salary: 4,500,000 won
Team size: 5 people

========================================
Minsu (ID: D001)
Salary: 4,000,000 won
Main language: Python
```

---
## 5️⃣ Mastering the super() Function (super() 함수 완전 정복)

The `super()` function is used when calling parent class methods.

`super()`는 부모 클래스의 메서드를 호출할 때 사용합니다.

### Why Use super()? (왜 super()를 사용할까?)

It's useful when using parent's functionality while adding extra work.

부모의 기능을 그대로 사용하면서 추가 작업을 할 때 유용합니다.

```python
# Without super() (not recommended) (super() 없이 - 비추천)
class Animal:
    def __init__(self, name):
        self.name = name

class Dog(Animal):
    def __init__(self, name, breed):
        Animal.__init__(self, name)  # Use parent class name directly (부모 클래스 이름 직접 사용)
        self.breed = breed

# Using super() (recommended) (super() 사용 - 권장)
class Dog(Animal):
    def __init__(self, name, breed):
        super().__init__(name)  # More concise and flexible (더 간결하고 유연함)
        self.breed = breed
```

### Using super() (super()의 활용)

```python
class Shape:
    """Shape (parent) (도형 - 부모)"""
  
    def __init__(self, color):
        self.color = color
  
    def describe(self):
        print(f"Color: {self.color}")

class Rectangle(Shape):
    """Rectangle (child) (직사각형 - 자식)"""
  
    def __init__(self, color, width, height):
        super().__init__(color)  # Initialize parent (부모 초기화)
        self.width = width
        self.height = height
  
    def area(self):
        return self.width * self.height
  
    def describe(self):
        super().describe()  # Run parent method first (부모 메서드 먼저 실행)
        print(f"Width: {self.width}, Height: {self.height}")
        print(f"Area: {self.area()}")

class Circle(Shape):
    """Circle (child) (원 - 자식)"""
  
    def __init__(self, color, radius):
        super().__init__(color)
        self.radius = radius
  
    def area(self):
        return 3.14 * self.radius ** 2
  
    def describe(self):
        super().describe()
        print(f"Radius: {self.radius}")
        print(f"Area: {self.area():.2f}")

# Use (사용)
rect = Rectangle("Red", 10, 5)
rect.describe()

print()

circle = Circle("Blue", 7)
circle.describe()
```

**Execution Result (실행 결과):**

```
Color: Red
Width: 10, Height: 5
Area: 50

Color: Blue
Radius: 7
Area: 153.86
```

---

## 6️⃣ Practical Example: Restaurant Delivery System (실전 예제: 음식점 배달 시스템)

Let's create a restaurant system for a delivery app.

배달 앱의 음식점 시스템을 만들어봅시다.

```python
class Restaurant:
    """Base restaurant class (음식점 기본 클래스)"""
  
    def __init__(self, name, location, rating=0):
        self.name = name
        self.location = location
        self.rating = rating
        self.menu = {}
        self.reviews = []
  
    def add_menu(self, item, price):
        """Add menu (메뉴 추가)"""
        self.menu[item] = price
        print(f"✓ '{item}' menu added ({price:,} won)")
  
    def show_menu(self):
        """Display menu (메뉴판 표시)"""
        print(f"\n{'='*40}")
        print(f"📋 {self.name} Menu")
        print(f"📍 Location: {self.location}")
        print(f"⭐ Rating: {self.rating}/5.0")
        print("-"*40)
        if len(self.menu) == 0:
            print("No registered menus.")
        else:
            for item, price in self.menu.items():
                print(f"{item:20} {price:>8,} won")
        print("="*40)
  
    def add_review(self, rating, comment):
        """Add review (리뷰 추가)"""
        if 0 <= rating <= 5:
            self.reviews.append({
                "rating": rating,
                "comment": comment
            })
            # Calculate average rating (평균 평점 계산)
            total = sum(r["rating"] for r in self.reviews)
            self.rating = round(total / len(self.reviews), 1)
            print(f"✓ Review registered (Rating: {rating}/5)")
        else:
            print("❌ Rating must be between 0-5.")
  
    def calculate_delivery_fee(self, distance):
        """Calculate delivery fee (basic) (배달비 계산 - 기본)"""
        base_fee = 3000
        if distance > 3:
            extra_fee = (distance - 3) * 500
            return base_fee + extra_fee
        return base_fee

class KoreanRestaurant(Restaurant):
    """Korean restaurant class (한식당 클래스)"""
  
    def __init__(self, name, location):
        super().__init__(name, location)
        self.side_dishes = ["Kimchi", "Pickled radish", "Bean sprouts"]
  
    def banchan_service(self):
        """Side dish service (반찬 서비스)"""
        print(f"\n🍚 {self.name} Basic Side Dishes")
        print(f"   {', '.join(self.side_dishes)}")
        print("   Free!")
  
    def calculate_delivery_fee(self, distance):
        """Calculate delivery fee (Korean restaurant discount) (배달비 계산 - 한식당 할인)"""
        base_fee = super().calculate_delivery_fee(distance)
        discount = 500
        final_fee = base_fee - discount
        print(f"💰 Delivery Fee: {base_fee:,} won → {final_fee:,} won (Korean restaurant discount -500)")
        return final_fee
  
    def show_menu(self):
        super().show_menu()
        print(f"🎁 Basic side dishes: {', '.join(self.side_dishes)} (Free)")
        print("="*40)

class ChineseRestaurant(Restaurant):
    """Chinese restaurant class (중식당 클래스)"""
  
    def __init__(self, name, location):
        super().__init__(name, location)
        self.min_order = 15000
  
    def free_jjajang(self, order_amount):
        """Free jajangmyeon service (over 30,000 won order) (짜장면 서비스 - 3만원 이상 주문시)"""
        if order_amount >= 30000:
            print(f"\n🎉 Order over 30,000 won! Free jajangmyeon!")
            return True
        return False
  
    def calculate_delivery_fee(self, distance):
        """Calculate delivery fee (varies by distance) (배달비 계산 - 거리에 따라 다름)"""
        if distance <= 2:
            fee = 2000
        elif distance <= 4:
            fee = 3000
        else:
            fee = 4000
        print(f"💰 Delivery Fee: {fee:,} won ({distance}km)")
        return fee
  
    def show_menu(self):
        super().show_menu()
        print(f"📦 Minimum order: {self.min_order:,} won")
        print("🎁 Free jajangmyeon for orders over 30,000 won!")
        print("="*40)

class ItalianRestaurant(Restaurant):
    """Italian restaurant class (이탈리안 레스토랑 클래스)"""
  
    def __init__(self, name, location):
        super().__init__(name, location)
        self.premium = True
  
    def wine_pairing(self, dish):
        """Wine pairing recommendation (와인 페어링 추천)"""
        wine_menu = {
            "Pasta": "White wine",
            "Pizza": "Red wine",
            "Risotto": "Sparkling wine"
        }
      
        for food in wine_menu:
            if food in dish:
                print(f"\n🍷 Wine for '{dish}': {wine_menu[food]}")
                return wine_menu[food]
      
        print(f"\n🍷 Recommend red wine")
        return "Red wine"
  
    def calculate_delivery_fee(self, distance):
        """Calculate delivery fee (premium delivery) (배달비 계산 - 프리미엄 배달)"""
        base_fee = 5000  # Premium delivery (프리미엄 배달)
        if distance > 5:
            print("❌ Delivery distance exceeded. (Maximum 5km)")
            return None
        print(f"💰 Delivery Fee: {base_fee:,} won (Premium delivery service)")
        return base_fee
  
    def show_menu(self):
        super().show_menu()
        print("✨ Premium delivery service (Quality guaranteed)")
        print("📍 Delivery available distance: Max 5km")
        print("="*40)
```

---

## 7️⃣ isinstance() and issubclass() (isinstance()와 issubclass())

These functions check inheritance relationships.

상속 관계를 확인하는 함수입니다.

### isinstance() Function (isinstance() 함수)

Check if an object is an instance of a class.

객체가 특정 클래스의 인스턴스인지 확인합니다.

```python
class Animal:
    pass

class Dog(Animal):
    pass

dog = Dog()
animal = Animal()

print(isinstance(dog, Dog))     # True (Dog instance - Dog 인스턴스)
print(isinstance(dog, Animal))  # True (Dog inherits from Animal - Animal을 상속받았음)
print(isinstance(animal, Dog))  # False (Animal is not Dog - Animal은 Dog가 아님)
```

### issubclass() Function (issubclass() 함수)

Check if a class inherits from another class.

클래스가 다른 클래스를 상속받았는지 확인합니다.

```python
class Animal:
    pass

class Dog(Animal):
    pass

class Cat(Animal):
    pass

print(issubclass(Dog, Animal))  # True (Dog inherits from Animal)
print(issubclass(Cat, Animal))  # True (Cat inherits from Animal)
print(issubclass(Animal, Dog))  # False (Animal doesn't inherit from Dog)
```

### Practical Usage (실제 활용)

```python
def feed_animal(animal, food):
    """Feed animal based on type (동물 타입에 따라 먹이기)"""
    if isinstance(animal, Dog):
        print(f"{animal.name} eats {food} (dog style)")
    elif isinstance(animal, Cat):
        print(f"{animal.name} eats {food} (cat style)")
    else:
        print("Unknown animal")

class Dog(Animal):
    def __init__(self, name):
        self.name = name

class Cat(Animal):
    def __init__(self, name):
        self.name = name

dog = Dog("Buddy")
cat = Cat("Whiskers")

feed_animal(dog, "meat")    # Buddy eats meat (dog style)
feed_animal(cat, "fish")    # Whiskers eats fish (cat style)
```

---

## 8️⃣ Practical Example: Bank Account System (실전 예제: 은행 계좌 시스템)

Create an inheritance-based bank account system with different account types.

상속을 활용한 은행 계좌 시스템을 만들어봅시다.

```python
class BankAccount:
    """Base bank account class (은행 기본 계좌)"""
  
    def __init__(self, account_number, owner, balance=0):
        self.account_number = account_number
        self.owner = owner
        self.balance = balance
        self.transaction_history = []
  
    def deposit(self, amount):
        """Deposit money (입금)"""
        if amount > 0:
            self.balance += amount
            self.transaction_history.append(f"Deposit: +{amount:,}")
            print(f"✓ Deposited {amount:,} won")
            return True
        print("❌ Amount must be positive")
        return False
  
    def withdraw(self, amount):
        """Withdraw money (출금)"""
        if amount <= self.balance:
            self.balance -= amount
            self.transaction_history.append(f"Withdraw: -{amount:,}")
            print(f"✓ Withdrew {amount:,} won")
            return True
        print(f"❌ Insufficient balance")
        return False
  
    def get_balance(self):
        """Get balance (잔액 조회)"""
        return self.balance
  
    def show_info(self):
        """Show account info (계좌 정보 표시)"""
        print(f"\nAccount: {self.account_number}")
        print(f"Owner: {self.owner}")
        print(f"Balance: {self.balance:,} won")

class SavingsAccount(BankAccount):
    """Savings account (with interest) (예금 계좌 - 이자 있음)"""
  
    def __init__(self, account_number, owner, balance=0, interest_rate=0.02):
        super().__init__(account_number, owner, balance)
        self.interest_rate = interest_rate
  
    def calculate_interest(self):
        """Calculate interest (이자 계산)"""
        interest = self.balance * self.interest_rate
        self.balance += interest
        self.transaction_history.append(f"Interest: +{interest:,.0f}")
        print(f"✓ Interest added: {interest:,.0f} won")
        return interest
  
    def show_info(self):
        super().show_info()
        print(f"Interest Rate: {self.interest_rate * 100}%")

class CheckingAccount(BankAccount):
    """Checking account (with overdraft) (당좌 계좌 - 마이너스 가능)"""
  
    def __init__(self, account_number, owner, balance=0, overdraft_limit=1000000):
        super().__init__(account_number, owner, balance)
        self.overdraft_limit = overdraft_limit
  
    def withdraw(self, amount):
        """Withdraw with overdraft allowed (마이너스 허용하여 출금)"""
        if amount <= self.balance + self.overdraft_limit:
            self.balance -= amount
            self.transaction_history.append(f"Withdraw: -{amount:,}")
            print(f"✓ Withdrew {amount:,} won")
            return True
        print("❌ Overdraft limit exceeded")
        return False
  
    def show_info(self):
        super().show_info()
        print(f"Overdraft Limit: {self.overdraft_limit:,} won")
        print(f"Available Credit: {self.balance + self.overdraft_limit:,} won")
```

---
## 📝 Key Concepts Summary (핵심 개념 정리)

### Inheritance (상속)

Child class inherits attributes and methods from parent class

자식 클래스가 부모 클래스의 속성과 메서드를 물려받는 것

```python
class Parent:
    pass

class Child(Parent):  # Inherit from Parent (Parent 상속)
    pass
```

### Method Overriding (메서드 오버라이딩)

Redefine parent method in child class

자식 클래스에서 부모 메서드를 재정의

```python
class Animal:
    def speak(self):
        print("...")

class Dog(Animal):
    def speak(self):  # Overriding (오버라이딩)
        print("Woof!")
```

### super() Function (super() 함수)

Call parent class method

부모 클래스의 메서드 호출

```python
class Child(Parent):
    def __init__(self, params):
        super().__init__(params)  # Initialize parent (부모 초기화)
```

### Type Checking (타입 확인)

- `isinstance(object, class)`: Check if object is instance of class
  객체가 해당 클래스인지 확인
  
- `issubclass(child, parent)`: Check inheritance relationship
  상속 관계인지 확인

---

## 💡 Practice Assignments (실습 과제)

### Assignment 1: Shape Class (과제 1: 도형 클래스)

Create Shape classes that calculate area:
- Rectangle: Calculate area from width and height
- Circle: Calculate area from radius

넓이를 계산하는 도형 클래스를 만드세요:
- Rectangle: 가로와 세로로부터 넓이 계산
- Circle: 반지름으로부터 넓이 계산

```python
# Hint (힌트)
class Shape:
    def area(self):
        pass

class Rectangle(Shape):
    def __init__(self, width, height):
        pass
  
    def area(self):
        # Calculate area (넓이 계산)
        pass

class Circle(Shape):
    def __init__(self, radius):
        pass
  
    def area(self):
        # Calculate area (넓이 계산)
        pass
```

### Assignment 2: Student Class Inheritance (과제 2: 학생 클래스 상속)

Create different types of students with inheritance:
- Undergraduate: with major
- Graduate: with advisor

상속을 이용하여 다양한 학생 클래스를 만드세요:
- Undergraduate: 전공이 있음
- Graduate: 지도교수가 있음

```python
# Hint (힌트)
class Student:
    def __init__(self, name, student_id):
        pass

class Undergraduate(Student):
    def __init__(self, name, student_id, major):
        pass

class Graduate(Student):
    def __init__(self, name, student_id, advisor):
        pass
```

---

## ✅ Quiz (퀴즈)

### [Beginner] Question 1

What is the correct inheritance syntax?

상속 문법으로 올바른 것은?

```
1. class Child extends Parent:
2. class Child(Parent):
3. class Child inherits Parent:
4. class Child <- Parent:
```

### [Intermediate] Question 2

What function calls a parent method?

부모 메서드를 호출하는 함수는?

```
1. parent()
2. base()
3. super()
4. inherit()
```

### [Intermediate] Question 3

What is method overriding?

메서드 오버라이딩이란?

```
1. Delete method 
2. Redefine method 
3. Add method 
4. Copy method 
```

### [Advanced] Question 4

What is the output of this code?

다음 코드의 실행 결과는?

```python
class Animal:
    def speak(self):
        print("...")

class Dog(Animal):
    def speak(self):
        print("Woof!")

dog = Dog()
dog.speak()
```

```
1. ...
2. Woof!
3. Both printed 
4. Error
```

### [Advanced] Question 5

What is the result of isinstance(dog, Animal)? (when dog = Dog())

isinstance(dog, Animal)의 결과는? (dog = Dog()일 때)

```
1. True
2. False
3. None
4. Error 
```

---

## 🔑 Quiz Answers and Explanations (퀴즈 정답 및 해설)

**Answer 1: 2**

Python uses `class Child(Parent):` form for inheritance.

파이썬에서는 `class Child(Parent):` 형태로 상속합니다.

**Answer 2: 3**

The `super()` function calls the parent class method.

`super()` 함수로 부모 클래스의 메서드를 호출합니다.

**Answer 3: 2**

Method overriding is redefining the parent's method in the child class.

메서드 오버라이딩은 부모의 메서드를 자식에서 재정의하는 것입니다.

**Answer 4: 2**

The overridden method in the child class executes, printing "Woof!"

자식 클래스에서 오버라이딩한 메서드가 실행되어 "Woof!"이 출력됩니다.

**Answer 5: 1**

Dog inherits from Animal, so the result is True.

Dog는 Animal을 상속받았으므로 True입니다.

---

## 🎯 Next Chapter Preview (다음 장 예고)

In the next chapter, we'll learn advanced class concepts such as special methods, properties, and static methods. You'll be able to write more professional and Pythonic object-oriented code!

다음 장에서는 클래스의 고급 개념인 특수 메서드, 프로퍼티, 정적 메서드 등을 배웁니다. 더욱 전문적이고 파이썬다운 객체지향 프로그래밍을 할 수 있게 됩니다!

---

Thank you for your attention.

Prof. Cho Jeonghyun (peterchokr@gmail.com)   
Yeungnam University College