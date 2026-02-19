# Chapter 13. Dictionaries

---

## 📚 Learning Objectives

After completing this chapter, you will be able to store and manage data using dictionaries with key-value pairs. Dictionaries are a powerful data structure that, like a phonebook where you find numbers by name, allows you to quickly find values using keys.

이번 장을 마치면 여러분은 딕셔너리를 사용하여 키-값 쌍으로 데이터를 저장하고 관리할 수 있습니다. 딕셔너리는 전화번호부처럼 이름으로 번호를 찾듯이, 키를 사용하여 값을 빠르게 찾을 수 있는 강력한 자료구조입니다.

---

## 1️⃣ What is a Dictionary? (딕셔너리란?)

A dictionary stores data as **key-value pairs**. Like looking up a word's definition in a real dictionary, you use keys to find values.

딕셔너리는 **키(key)와 값(value)의 쌍**으로 데이터를 저장합니다. 마치 실제 사전에서 단어(키)로 뜻(값)을 찾듯이 사용합니다.

```python
# List approach (inefficient) (리스트 방식 (비효율적))
names = ["Chulsu", "Younghee", "Minsu"]
phones = ["010-1111-1111", "010-2222-2222", "010-3333-3333"]
# To find Chulsu's number? (철수의 번호를 찾으려면?)
index = names.index("Chulsu")
print(phones[index])

# Dictionary approach (efficient!) (딕셔너리 방식 (효율적!))
phonebook = {
    "Chulsu": "010-1111-1111",
    "Younghee": "010-2222-2222",
    "Minsu": "010-3333-3333"
}
print(phonebook["Chulsu"])  # Find immediately! (바로 찾기!)
```

```
Dictionary Structure (딕셔너리의 구조)

   Key(키)        Value(값)
   ┌────────┐   ┌──────────────┐
   │Chulsu  │ : │010-1111-1111 │
   ├────────┤   ├──────────────┤
   │Younghee│ : │010-2222-2222 │
   ├────────┤   ├──────────────┤
   │Minsu   │ : │010-3333-3333 │
   └────────┘   └──────────────┘
```

---

## 2️⃣ Creating Dictionaries (딕셔너리 생성하기)

Dictionaries are created with braces `{}`, with keys and values separated by a colon (`:`).

딕셔너리는 중괄호 `{}`로 만들며, 키와 값은 콜론(`:`)으로 구분합니다.

```python
# Empty dictionary (빈 딕셔너리)
empty = {}

# String keys (문자열 키)
student = {
    "name": "Chulsu Kim",
    "age": 20,
    "major": "Computer Science"
}

# Number keys also possible (숫자 키도 가능)
scores = {
    1: 85,
    2: 90,
    3: 78
}

print(student)  # {'name': 'Chulsu Kim', 'age': 20, 'major': 'Computer Science'}
```

### Example 1: Coffee Shop Menu (예제 1: 커피숍 메뉴)

A program that manages a coffee shop menu using a dictionary.

커피숍 메뉴를 딕셔너리로 관리하는 프로그램입니다.

```python
# Coffee shop menu management (커피숍 메뉴 관리 프로그램)
print("☕" + "=" * 38 + "☕")
print("   Coffee Shop Menu")
print("☕" + "=" * 38 + "☕")

# Menu dictionary (menu: price) (메뉴 딕셔너리 (메뉴명: 가격))
menu = {
    "Americano": 4,
    "Latte": 5,
    "Cappuccino": 5.50,
    "Vanilla Latte": 6,
    "Caramel Macchiato": 6.50
}

print("\n📋 Menu List:")
print("=" * 40)

for drink in menu:
    print(f"{drink}: ${menu[drink]:.2f}")

print("=" * 40)

# Order (주문)
order = input("\nOrder menu: ")

if order in menu:
    price = menu[order]
    quantity = int(input("Quantity: "))
    total = price * quantity
  
    print("\n" + "-" * 40)
    print("Order Details")
    print("-" * 40)
    print(f"Menu: {order}")
    print(f"Price: ${price:.2f}")
    print(f"Quantity: {quantity}")
    print(f"Total: ${total:.2f}")
    print("-" * 40)
else:
    print(f"'{order}' is not in menu.")
```

---

## 3️⃣ Accessing Dictionary Values (딕셔너리 값 접근하기)

### Bracket Access (대괄호 접근)

```python
student = {
    "name": "Chulsu Kim",
    "age": 20,
    "major": "Computer Science"
}

print(student["name"])  # Chulsu Kim
print(student["age"])  # 20

# print(student["id"])  # Error! If key doesn't exist, raises error
```

### get() Method (Safe Access) (get() 메서드 (안전한 접근))

```python
# get(key) - Returns None if key doesn't exist
print(student.get("major"))  # Computer Science
print(student.get("id"))  # None (No error!)

# get(key, default) - Returns default if key doesn't exist
print(student.get("id", "Information unavailable"))  # Information unavailable
```

### Example 2: English Dictionary (예제 2: 영어 사전)

A simple English-Korean dictionary program.

간단한 영어 한국어 사전 프로그램입니다.

```python
# English-Korean dictionary (영어-한국어 사전)
print("📖" + "=" * 38 + "📖")
print("   English Dictionary")
print("📖" + "=" * 38 + "📖")

dictionary = {
    "hello": "안녕하세요",
    "goodbye": "안녕히 가세요",
    "thank you": "감사합니다",
    "please": "부탁합니다",
    "love": "사랑",
    "dream": "꿈"
}

while True:
    word = input("\nEnter English word (or 'exit' to quit): ").lower()
    
    if word == "exit":
        print("Thank you for using dictionary!")
        break
    
    if word in dictionary:
        meaning = dictionary[word]
        print(f"'{word}' → '{meaning}'")
    else:
        print(f"'{word}' not found in dictionary.")
```

---

## 4️⃣ Dictionary Methods (딕셔너리 메서드)

```python
# keys(): Get all keys (모든 키 얻기)
student = {"name": "Alice", "age": 25, "major": "CS"}
keys = student.keys()
print(keys)  # dict_keys(['name', 'age', 'major'])

# values(): Get all values (모든 값 얻기)
values = student.values()
print(values)  # dict_values(['Alice', 25, 'CS'])

# items(): Get key-value pairs (키-값 쌍 얻기)
items = student.items()
print(items)  # dict_items([('name', 'Alice'), ('age', 25), ('major', 'CS')])

# add/modify: Assignment (추가/수정: 할당)
student["age"] = 26  # Modify (수정)
student["city"] = "New York"  # Add (추가)

# pop(): Remove and return (제거하고 반환)
major = student.pop("major")

# clear(): Remove all (모두 제거)
student.clear()
```

### Example 3: Student Information System (예제 3: 학생 정보 시스템)

A program that manages student information.

학생 정보를 관리하는 프로그램입니다.

```python
# Student information system (학생 정보 시스템)
print("👨‍🎓" + "=" * 38 + "👨‍🎓")
print("   Student Information System")
print("👨‍🎓" + "=" * 38 + "👨‍🎓")

students = {}

while True:
    print("\n1. Add student")
    print("2. View student")
    print("3. List all students")
    print("4. Delete student")
    print("5. Exit")
    
    choice = input("\nChoose: ")
    
    if choice == "1":
        student_id = input("Student ID: ")
        name = input("Name: ")
        grade = input("Grade: ")
        
        students[student_id] = {"name": name, "grade": grade}
        print(f"✓ {name} added!")
    
    elif choice == "2":
        student_id = input("Student ID: ")
        
        if student_id in students:
            info = students[student_id]
            print(f"\nStudent ID: {student_id}")
            print(f"Name: {info['name']}")
            print(f"Grade: {info['grade']}")
        else:
            print("Student not found!")
    
    elif choice == "3":
        if len(students) == 0:
            print("No students!")
        else:
            print("\nStudent List:")
            for sid, info in students.items():
                print(f"  {sid}: {info['name']} ({info['grade']})")
    
    elif choice == "4":
        student_id = input("Student ID to delete: ")
        
        if student_id in students:
            name = students[student_id]["name"]
            del students[student_id]
            print(f"✓ {name} deleted!")
        else:
            print("Student not found!")
    
    elif choice == "5":
        print("Goodbye!")
        break
```

---

## 5️⃣ Dictionary Iteration (딕셔너리 순회)

```python
student = {
    "name": "Alice",
    "age": 25,
    "major": "Computer Science"
}

# Iterate keys (키만 순회)
for key in student:
    print(key)

# Iterate values (값만 순회)
for value in student.values():
    print(value)

# Iterate items (키-값 쌍 순회)
for key, value in student.items():
    print(f"{key}: {value}")
```

### Example 4: Grade Analysis (예제 4: 성적 분석)

A program that analyzes student grades using dictionaries.

딕셔너리를 사용한 학생 성적 분석 프로그램입니다.

```python
# Grade analysis program (성적 분석 프로그램)
print("📊" + "=" * 38 + "📊")
print("   Grade Analysis System")
print("📊" + "=" * 38 + "📊")

grades = {
    "Alice": 95,
    "Bob": 87,
    "Charlie": 92,
    "David": 78,
    "Emma": 88
}

print("\nStudent Grades:")
print("=" * 40)

# Display all grades (모든 성적 표시)
for name, grade in grades.items():
    print(f"{name:10} : {grade:3d}")

print("=" * 40)

# Calculate average (평균 계산)
average = sum(grades.values()) / len(grades)
print(f"\nClass Average: {average:.1f}")

# Find highest and lowest (최고점과 최저점)
highest = max(grades.values())
lowest = min(grades.values())

print(f"Highest: {highest}")
print(f"Lowest: {lowest}")

# Find students above average (평균 이상인 학생)
print("\nAbove Average:")
for name, grade in grades.items():
    if grade >= average:
        print(f"  {name}: {grade}")

print("=" * 40)
```

---

## 6️⃣ Nested Dictionaries (중첩 딕셔너리)

Dictionaries can contain other dictionaries for complex data structures.

딕셔너리는 다른 딕셔너리를 포함할 수 있어 복잡한 자료구조를 만듭니다.

```python
# Nested dictionary (중첩 딕셔너리)
company = {
    "name": "Tech Corp",
    "employees": {
        "Alice": {"position": "Engineer", "salary": 100000},
        "Bob": {"position": "Manager", "salary": 120000},
        "Charlie": {"position": "Designer", "salary": 90000}
    }
}

# Access nested values (중첩된 값 접근)
print(company["name"])  # Tech Corp
print(company["employees"]["Alice"]["position"])  # Engineer
```

### Example 5: School Database (예제 5: 학교 데이터베이스)

A complex database system using nested dictionaries.

중첩 딕셔너리를 사용한 복잡한 데이터베이스 시스템입니다.

```python
# School database (학교 데이터베이스)
print("🏫" + "=" * 38 + "🏫")
print("   School Database")
print("🏫" + "=" * 38 + "🏫")

school = {
    "name": "Central High School",
    "location": "New York",
    "classes": {
        "9A": {
            "teacher": "Mr. Smith",
            "students": ["Alice", "Bob", "Charlie"],
            "count": 3
        },
        "9B": {
            "teacher": "Ms. Johnson",
            "students": ["David", "Emma", "Frank"],
            "count": 3
        }
    }
}

print(f"\nSchool: {school['name']}")
print(f"Location: {school['location']}")

print("\nClass Information:")
print("=" * 40)

for class_name, info in school["classes"].items():
    print(f"\nClass: {class_name}")
    print(f"Teacher: {info['teacher']}")
    print(f"Students: {', '.join(info['students'])}")
    print(f"Count: {info['count']}")

print("\n" + "=" * 40)
```

---

## 📝 Summary of Key Concepts (핵심 개념 정리)

Dictionaries store data as key-value pairs, making data lookup fast and intuitive. Keys must be unique and immutable (strings, numbers, tuples), while values can be any type. Access values using bracket notation [] or the safer get() method.

딕셔너리는 키-값 쌍으로 데이터를 저장하여 데이터 조회가 빠르고 직관적입니다. 키는 고유하고 불변이어야 하지만(문자열, 숫자, 튜플), 값은 어떤 타입이든 가능합니다. 대괄호 []나 더 안전한 get() 메서드로 값에 접근합니다.

Dictionary methods like keys(), values(), and items() provide different ways to iterate. Nested dictionaries allow creating complex data structures for real-world applications. Dictionaries are essential for data management in Python.

keys(), values(), items() 같은 딕셔너리 메서드는 순회하는 여러 방법을 제공합니다. 중첩 딕셔너리는 실제 응용 프로그램을 위한 복잡한 자료구조를 만들 수 있습니다. 딕셔너리는 파이썬의 데이터 관리에 필수적입니다.

---

## 💡 Practical Assignments (실습 과제)

### Assignment 1: Contact Manager (과제 1: 연락처 관리자)

Write a program that manages contacts (name, phone, email) using a dictionary.

딕셔너리를 사용하여 연락처(이름, 전화, 이메일)를 관리하는 프로그램을 작성하세요.

```python
# Hint
contacts = {
    "Alice": {"phone": "010-1234-5678", "email": "alice@example.com"},
    "Bob": {"phone": "010-8765-4321", "email": "bob@example.com"}
}
# Add, view, delete contacts
```

### Assignment 2: Inventory System (과제 2: 재고 관리 시스템)

Create an inventory system that tracks product quantities and prices.

상품 수량과 가격을 추적하는 재고 관리 시스템을 만드세요.

```python
# Hint
inventory = {
    "Laptop": {"quantity": 10, "price": 1000},
    "Mouse": {"quantity": 50, "price": 25},
    "Keyboard": {"quantity": 30, "price": 75}
}
# Track stock and calculate total value
```

---

## ✅ Quiz (퀴즈)

### [Beginner] Question 1

What is the output?

다음 코드의 출력 결과는?

```python
student = {"name": "Alice", "age": 25}
print(student["name"])
```

1. {"name": "Alice", "age": 25}
2. Alice
3. name
4. Error

### [Intermediate] Question 2

What is the output?

다음 코드의 출력 결과는?

```python
grades = {"Alice": 95, "Bob": 87, "Charlie": 92}
print(len(grades))
```

1. 3
2. 2
3. 95
4. Error

### [Intermediate] Question 3

What is the output?

다음 코드의 출력 결과는?

```python
student = {"name": "Alice", "age": 25}
result = student.get("email", "No email")
print(result)
```

1. Alice
2. None
3. No email
4. Error

### [Advanced] Question 4

What is the output?

다음 코드의 출력 결과는?

```python
data = {"a": 1, "b": 2, "c": 3}
keys = list(data.keys())
print(keys[0])
```

1. a
2. 1
3. {"a": 1}
4. Error

### [Advanced] Question 5

What is the output?

다음 코드의 출력 결과는?

```python
for key, value in {"name": "Alice", "age": 25}.items():
    print(f"{key}: {value}")
```

1. {"name": "Alice", "age": 25}
2. name: age
3. name: Alice, age: 25 (on separate lines)
4. Error

---

## 🔑 Quiz Answers and Explanations (퀴즈 정답 및 해설)

**Question 1 Answer: 2**
student["name"] accesses the value associated with the "name" key, which is "Alice".

student["name"]은 "name" 키와 연결된 값인 "Alice"에 접근합니다.

**Question 2 Answer: 1**
The dictionary has 3 key-value pairs: "Alice", "Bob", "Charlie". len() returns 3.

딕셔너리는 3개의 키-값 쌍을 가지고 있으므로 len()은 3을 반환합니다.

**Question 3 Answer: 3**
The key "email" doesn't exist, so get() returns the default value "No email".

"email" 키가 없으므로 get()은 기본값 "No email"을 반환합니다.

**Question 4 Answer: 1**
data.keys() returns dict_keys(['a', 'b', 'c']). Converted to list, keys[0] is 'a'.

data.keys()는 'a', 'b', 'c'를 반환하고, 리스트로 변환하면 keys[0]은 'a'입니다.

**Question 5 Answer: 3**
items() returns key-value pairs. The loop prints "name: Alice" and "age: 25" on separate lines.

items()는 키-값 쌍을 반환하여 "name: Alice"와 "age: 25"가 각각 출력됩니다.

---

## 🎯 Preview of Next Chapter (다음 장 예고)

In the next chapters, we will learn about file input/output and modules. These will allow you to work with files and use code libraries, making your programs much more powerful and versatile!

다음 장들에서는 파일 입출력과 모듈에 대해 배웁니다. 이를 통해 파일을 다루고 코드 라이브러리를 사용할 수 있어 프로그램이 훨씬 강력해질 것입니다!

---

Thank you for your attention.

Cho Jeonghyun (peterchokr@gmail.com). Yeungnam University College
