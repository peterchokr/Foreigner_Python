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

### Benefits of Inheritance (상속의 장점)

**1. Code Reuse**: Write common code in one place only  (코드 재사용: 공통 코드를 한 곳에만 작성)

**2. Easy Maintenance**: If modification is needed, only modify parent class (유지보수 용이: 수정이 필요하면 부모 클래스만 수정)

**3. Hierarchical Structure**: Logically organized and systematic structure  (계층 구조: 논리적으로 체계적인 구조)

**4. Extensibility**: Add functionality without touching existing code  (확장성: 기존 코드를 건드리지 않고 기능 추가)

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



---

## 5️⃣ isinstance() and issubclass() (isinstance()와 issubclass())

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
Cho Jeonghyun ([peterchokr@gmail.com](mailto:peterchokr@gmail.com)). Yeungnam University College

"Produced in collaboration with Claude and Gemini."
