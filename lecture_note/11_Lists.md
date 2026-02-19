# Chapter 11. Lists

---

## 📚 Learning Objectives

After completing this chapter, you will understand how to create, access, and manipulate lists. Lists are the most commonly used data structure in Python and are essential for data processing and management.

이번 장을 마치면 여러분은 리스트를 생성하고 접근하고 조작하는 방법을 이해하게 됩니다. 리스트는 파이썬에서 가장 많이 사용되는 자료구조이며 데이터 처리와 관리에 필수적입니다.

---

## 1️⃣ What is a List? (리스트란?)

A list is an ordered collection that can store multiple values of any type. It's one of the most important data structures in Python.

리스트는 여러 개의 값을 같은 이름으로 관리할 수 있는 자료구조입니다. 여러 값을 순서대로 저장할 수 있습니다.

```python
# Create lists (리스트 생성)
numbers = [1, 2, 3, 4, 5]  # List of numbers (숫자 리스트)
fruits = ["apple", "banana", "cherry"]  # List of strings (문자열 리스트)
mixed = [1, "apple", 3.14, True]  # Mixed types (혼합 타입)
empty = []  # Empty list (빈 리스트)

# Create with range (range로 생성)
numbers = list(range(1, 6))  # [1, 2, 3, 4, 5]
```

```
List Concept (리스트의 개념)

fruits = ["apple", "banana", "cherry"]
          ↓        ↓          ↓
        Index 0  Index 1   Index 2
        또는     또는      또는
        [0]     [1]      [2]
```

### Access List Elements (리스트 요소 접근)

```python
# Access by index (인덱스로 접근)
fruits = ["apple", "banana", "cherry"]
print(fruits[0])  # apple
print(fruits[1])  # banana
print(fruits[2])  # cherry
print(fruits[-1])  # cherry (last element)
print(fruits[-2])  # banana (second from last)
```

### Example 1: Student Grade Management (예제 1: 학생 성적 관리)

A program that manages student grades using lists.

리스트를 사용한 학생 성적 관리 프로그램입니다.

```python
# Student grade management (학생 성적 관리)
print("📚" + "=" * 38 + "📚")
print("   Grade Management System")
print("📚" + "=" * 38 + "📚")

# Student names and grades (학생 이름과 성적)
names = ["Alice", "Bob", "Charlie", "David", "Emma"]
grades = [95, 87, 92, 78, 88]

print("\nStudent Grades:")
print("-" * 40)

for i in range(len(names)):
    print(f"{names[i]:10} : {grades[i]:3d} points")

print("-" * 40)

# Calculate average (평균 계산)
average = sum(grades) / len(grades)
print(f"Class Average: {average:.1f}")

# Find highest and lowest (최고점과 최저점)
highest = max(grades)
lowest = min(grades)
print(f"Highest: {highest}, Lowest: {lowest}")

print("=" * 40)
```

---

## 2️⃣ List Operations (리스트 조작)

### Add Elements (요소 추가)

```python
# append(): Add to end (끝에 추가)
fruits = ["apple", "banana"]
fruits.append("cherry")
print(fruits)  # ['apple', 'banana', 'cherry']

# insert(): Add at specific position (특정 위치에 추가)
fruits.insert(1, "orange")
print(fruits)  # ['apple', 'orange', 'banana', 'cherry']

# extend(): Add multiple elements (여러 요소 추가)
more_fruits = ["grape", "melon"]
fruits.extend(more_fruits)
print(fruits)  # ['apple', 'orange', 'banana', 'cherry', 'grape', 'melon']
```

### Remove Elements (요소 제거)

```python
# remove(): Remove first matching element (처음 일치하는 요소 제거)
fruits = ["apple", "banana", "cherry", "banana"]
fruits.remove("banana")
print(fruits)  # ['apple', 'cherry', 'banana']

# pop(): Remove by index (인덱스로 제거)
last = fruits.pop()  # Remove last (마지막 제거)
print(last)  # cherry
print(fruits)  # ['apple', 'cherry']

# pop(index): Remove at specific index (특정 위치 제거)
item = fruits.pop(0)  # Remove first (첫 번째 제거)
print(item)  # apple

# clear(): Remove all (모두 제거)
fruits.clear()
print(fruits)  # []
```

### Example 2: Shopping List (예제 2: 쇼핑 리스트)

A program to manage shopping items.

쇼핑 항목을 관리하는 프로그램입니다.

```python
# Shopping list management (쇼핑 리스트 관리)
print("🛒" + "=" * 38 + "🛒")
print("   Shopping List Manager")
print("🛒" + "=" * 38 + "🛒")

shopping_list = []

while True:
    print("\n1. Add item")
    print("2. Remove item")
    print("3. Show list")
    print("4. Exit")
    
    choice = input("\nChoose: ")
    
    if choice == "1":
        item = input("Item name: ")
        shopping_list.append(item)
        print(f"✓ {item} added!")
    
    elif choice == "2":
        if len(shopping_list) == 0:
            print("List is empty!")
            continue
        
        for i, item in enumerate(shopping_list):
            print(f"{i+1}. {item}")
        
        try:
            index = int(input("Item number to remove: ")) - 1
            removed = shopping_list.pop(index)
            print(f"✓ {removed} removed!")
        except:
            print("Invalid number!")
    
    elif choice == "3":
        if len(shopping_list) == 0:
            print("List is empty!")
        else:
            print("\nShopping List:")
            for i, item in enumerate(shopping_list, 1):
                print(f"  {i}. {item}")
    
    elif choice == "4":
        print("Goodbye!")
        break
```

---

## 3️⃣ List Slicing (리스트 슬라이싱)

Slicing extracts a portion of a list.

슬라이싱으로 리스트의 일부를 추출합니다.

```python
# List slicing (리스트 슬라이싱)
numbers = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]

print(numbers[0:3])    # [0, 1, 2] (from 0 to 2)
print(numbers[3:7])    # [3, 4, 5, 6]
print(numbers[:4])     # [0, 1, 2, 3] (from start to 3)
print(numbers[6:])     # [6, 7, 8, 9] (from 6 to end)
print(numbers[::2])    # [0, 2, 4, 6, 8] (every 2nd)
print(numbers[::-1])   # [9, 8, 7, 6, 5, 4, 3, 2, 1, 0] (reverse)
```

---

## 4️⃣ List Methods (리스트 메서드)

```python
# sort(): Sort list (정렬)
numbers = [5, 2, 8, 1, 9]
numbers.sort()
print(numbers)  # [1, 2, 5, 8, 9]

# sort(reverse=True): Reverse sort (역순 정렬)
numbers.sort(reverse=True)
print(numbers)  # [9, 8, 5, 2, 1]

# index(): Find index of element (요소의 인덱스 찾기)
fruits = ["apple", "banana", "cherry"]
print(fruits.index("banana"))  # 1

# count(): Count occurrences (요소 개수 세기)
numbers = [1, 2, 2, 3, 3, 3, 4]
print(numbers.count(3))  # 3

# copy(): Create copy (복사본 생성)
list1 = [1, 2, 3]
list2 = list1.copy()  # Independent copy (독립적인 복사본)
```

### Example 3: Grade Sorter (예제 3: 성적 정렬)

A program that sorts students by grades.

학생들을 성적순으로 정렬하는 프로그램입니다.

```python
# Grade sorting program (성적 정렬 프로그램)
print("📊" + "=" * 38 + "📊")
print("   Grade Ranking System")
print("📊" + "=" * 38 + "📊")

# Student data (학생 데이터)
students = [
    ["Alice", 95],
    ["Bob", 87],
    ["Charlie", 92],
    ["David", 78],
    ["Emma", 88]
]

print("\nOriginal order:")
for name, grade in students:
    print(f"  {name}: {grade}")

# Sort by grade (성적순 정렬)
students.sort(key=lambda x: x[1], reverse=True)

print("\nRanked by grade:")
for i, (name, grade) in enumerate(students, 1):
    print(f"  {i}. {name}: {grade}")

print("=" * 40)
```

---

## 5️⃣ List Comprehension (리스트 컴프리헨션)

List comprehension provides a concise way to create lists.

리스트 컴프리헨션은 간결한 리스트 생성 방법입니다.

```python
# Basic list comprehension (기본 리스트 컴프리헨션)
numbers = [x for x in range(1, 6)]
print(numbers)  # [1, 2, 3, 4, 5]

# With operation (연산과 함께)
squared = [x ** 2 for x in range(1, 6)]
print(squared)  # [1, 4, 9, 16, 25]

# With condition (조건과 함께)
evens = [x for x in range(1, 11) if x % 2 == 0]
print(evens)  # [2, 4, 6, 8, 10]

# Nested comprehension (중첩 컴프리헨션)
matrix = [[i*j for j in range(1, 4)] for i in range(1, 4)]
print(matrix)
# [[1, 2, 3], [2, 4, 6], [3, 6, 9]]
```

### Example 4: Data Processing (예제 4: 데이터 처리)

Processing data with list comprehension.

리스트 컴프리헨션을 사용한 데이터 처리입니다.

```python
# Data processing with list comprehension (리스트 컴프리헨션으로 데이터 처리)
print("📊" + "=" * 38 + "📊")
print("   Data Processing")
print("📊" + "=" * 38 + "📊")

# Original prices (원래 가격)
prices = [100, 250, 150, 300, 200]
print(f"\nOriginal prices: {prices}")

# Apply 20% discount (20% 할인 적용)
discounted = [p * 0.8 for p in prices]
print(f"After 20% discount: {discounted}")

# Filter items over $200 (200 이상 항목)
expensive = [p for p in prices if p >= 200]
print(f"Items over $200: {expensive}")

# Convert to dollars format ($로 변환)
formatted = [f"${p:.2f}" for p in prices]
print(f"Formatted: {formatted}")

print("=" * 40)
```

---

## 6️⃣ Nested Lists (중첩 리스트)

Lists can contain other lists, creating a 2D structure.

리스트는 다른 리스트를 포함할 수 있어 2차원 구조를 만듭니다.

```python
# 2D list (2D 리스트)
matrix = [
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]
]

# Access elements (요소 접근)
print(matrix[0])      # [1, 2, 3]
print(matrix[0][1])   # 2
print(matrix[2][2])   # 9

# Iterate through 2D list (2D 리스트 순회)
for row in matrix:
    for element in row:
        print(element, end=" ")
    print()  # Newline (줄바꿈)
```

### Example 5: Tic-Tac-Toe Game (예제 5: 틱택토 게임)

A simple tic-tac-toe game using nested lists.

중첩 리스트를 사용한 간단한 틱택토 게임입니다.

```python
# Tic-Tac-Toe display (틱택토 게임)
print("🎮" + "=" * 38 + "🎮")
print("   Tic-Tac-Toe Game")
print("🎮" + "=" * 38 + "🎮")

# Game board (게임 보드)
board = [
    [" ", " ", " "],
    [" ", " ", " "],
    [" ", " ", " "]
]

def display_board(board):
    print("\n  1 2 3")
    for i in range(3):
        print(f"{i+1} {board[i][0]}|{board[i][1]}|{board[i][2]}")
        if i < 2:
            print("  -----")

def make_move(board, row, col, player):
    if board[row][col] == " ":
        board[row][col] = player
        return True
    return False

# Play game (게임 진행)
display_board(board)

# X's turn (X의 차례)
make_move(board, 0, 0, "X")
display_board(board)

# O's turn (O의 차례)
make_move(board, 1, 1, "O")
display_board(board)

# X's turn (X의 차례)
make_move(board, 0, 2, "X")
display_board(board)

print("\n" + "=" * 40)
```

---

## 📝 Summary of Key Concepts (핵심 개념 정리)

A list is an ordered collection that stores multiple values. You can access elements by index, add or remove elements using methods like append(), insert(), remove(), and pop(). Slicing extracts portions of lists using the syntax list[start:end:step].

리스트는 순서가 있는 여러 값의 모음입니다. 인덱스로 요소에 접근하고, append(), insert(), remove(), pop() 등의 메서드로 추가하거나 제거할 수 있습니다. 슬라이싱은 list[start:end:step] 문법으로 리스트의 일부를 추출합니다.

List methods include sort() for sorting, index() for finding elements, and count() for counting occurrences. List comprehension provides a concise syntax for creating lists, especially useful for filtering and transforming data.

리스트 메서드에는 정렬을 위한 sort(), 요소 찾기를 위한 index(), 개수 세기를 위한 count() 등이 있습니다. 리스트 컴프리헨션은 간결한 리스트 생성 문법을 제공하며 특히 데이터 필터링과 변환에 유용합니다.

Nested lists create 2D structures useful for representing tables or matrices. Understanding lists is fundamental to Python programming and data manipulation.

중첩 리스트는 표나 행렬을 나타내는 데 유용한 2차원 구조를 만듭니다. 리스트를 이해하는 것은 파이썬 프로그래밍과 데이터 조작의 기본입니다.

---

## 💡 Practical Assignments (실습 과제)

### Assignment 1: List Statistics (과제 1: 리스트 통계)

Write a program that calculates statistics (sum, average, max, min, median) for a list of numbers.

숫자 리스트의 통계(합, 평균, 최대, 최소, 중앙값)를 계산하는 프로그램을 작성하세요.

```python
# Hint
def calculate_stats(numbers):
    # Calculate sum, average, max, min
    # Return all statistics
    pass
```

### Assignment 2: List Filtering (과제 2: 리스트 필터링)

Write a program that filters a list based on conditions (e.g., even numbers, numbers over 50).

조건(예: 짝수, 50 이상)을 기반으로 리스트를 필터링하는 프로그램을 작성하세요.

```python
# Hint
numbers = [10, 25, 34, 45, 56, 67, 78, 89]
# Filter even numbers using list comprehension
# Filter numbers over 50
```

---

## ✅ Quiz (퀴즈)

### [Beginner] Question 1

What is the output?

다음 코드의 출력 결과는?

```python
fruits = ["apple", "banana", "cherry"]
print(fruits[1])
```

1. apple
2. banana
3. cherry
4. Error

### [Intermediate] Question 2

What is the output?

다음 코드의 출력 결과는?

```python
numbers = [1, 2, 3, 4, 5]
print(numbers[1:4])
```

1. [1, 2, 3]
2. [2, 3, 4]
3. [2, 3, 4, 5]
4. [3, 4, 5]

### [Intermediate] Question 3

What is the output?

다음 코드의 출력 결과는?

```python
fruits = ["apple", "banana"]
fruits.append("cherry")
print(len(fruits))
```

1. 2
2. 3
3. ["apple", "banana", "cherry"]
4. Error

### [Advanced] Question 4

What is the output?

다음 코드의 출력 결과는?

```python
numbers = [5, 2, 8, 1, 9]
numbers.sort()
print(numbers)
```

1. [5, 2, 8, 1, 9]
2. [1, 2, 5, 8, 9]
3. [9, 8, 5, 2, 1]
4. Error

### [Advanced] Question 5

What is the output?

다음 코드의 출력 결과는?

```python
numbers = [x ** 2 for x in range(1, 4)]
print(numbers)
```

1. [1, 2, 3]
2. [1, 4, 9]
3. [0, 1, 4, 9]
4. Error

---

## 🔑 Quiz Answers and Explanations (퀴즈 정답 및 해설)

**Question 1 Answer: 2**
fruits[1] accesses the element at index 1, which is "banana".

fruits[1]은 인덱스 1의 요소인 "banana"에 접근합니다.

**Question 2 Answer: 2**
numbers[1:4] returns elements from index 1 to 3: [2, 3, 4]

numbers[1:4]는 인덱스 1부터 3까지의 요소를 반환합니다: [2, 3, 4]

**Question 3 Answer: 2**
append() adds one element to the list. Starting with 2 elements, after append, there are 3.

append()는 리스트에 요소 하나를 추가합니다. 2개에서 시작하여 3개가 됩니다.

**Question 4 Answer: 2**
sort() sorts the list in ascending order. [5, 2, 8, 1, 9] becomes [1, 2, 5, 8, 9]

sort()는 리스트를 오름차순으로 정렬합니다. [1, 2, 5, 8, 9]

**Question 5 Answer: 2**
List comprehension with x**2 for x in range(1, 4): 1², 2², 3² = [1, 4, 9]

리스트 컴프리헨션으로 1², 2², 3² = [1, 4, 9]

---

## 🎯 Preview of Next Chapter (다음 장 예고)

In the next chapter, we will learn about dictionaries. Dictionaries store data in key-value pairs, making data access more intuitive and efficient. Dictionaries are essential for advanced data manipulation!

다음 장에서는 딕셔너리에 대해 배웁니다. 딕셔너리는 키-값 쌍으로 데이터를 저장하여 더욱 직관적이고 효율적인 데이터 접근을 가능하게 합니다.

---

Thank you for your attention.

Cho Jeonghyun (peterchokr@gmail.com). Yeungnam University College
