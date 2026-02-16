# Chapter 12. Tuples and Sets

---

## 📚 Learning Objectives

After completing this chapter, you will be able to use two special data structures: tuples and sets. Tuples allow you to safely store immutable data, and sets enable you to efficiently manage data without duplicates.

이번 장을 마치면 여러분은 튜플과 세트라는 두 가지 특별한 자료구조를 활용할 수 있습니다. 튜플은 변경할 수 없는 데이터를 안전하게 저장하고, 세트는 중복 없는 데이터를 효율적으로 관리할 수 있게 해줍니다.

---

## 1️⃣ What is a Tuple? (튜플이란?)

A tuple is similar to a list, but **once created, it cannot be changed** (immutable).

튜플은 리스트와 비슷하지만 **한 번 만들면 변경할 수 없습니다** (불변, immutable).

### Tuple vs List (튜플 vs 리스트)

```python
# List (mutable - changeable) (리스트 (변경 가능))
my_list = [1, 2, 3]
my_list[0] = 10  # Allowed (가능)
print(my_list)  # [10, 2, 3]

# Tuple (immutable - unchangeable) (튜플 (변경 불가능))
my_tuple = (1, 2, 3)
# my_tuple[0] = 10  # Error! (오류 발생!)
```

```
List vs Tuple (리스트 vs 튜플)

┌──────────────┬──────────────┬──────────────┐
│   Feature    │    List      │    Tuple     │
├──────────────┼──────────────┼──────────────┤
│  Bracket     │    [ ]       │    ( )       │
│  Mutable     │     Yes      │     No       │
│  Speed       │   Normal     │   Fast       │
│  When to use │  Need change │ No change    │
└──────────────┴──────────────┴──────────────┘
```

### Creating Tuples (튜플 생성하기)

```python
# Create with parentheses (소괄호로 생성)
coordinates = (37.5, 127.0)  # Coordinates (좌표)
rgb = (255, 128, 0)          # RGB color (RGB 색상)

# Without parentheses (괄호 없이도 가능)
point = 10, 20

# Single-element tuple (comma required!) (항목이 하나인 튜플 (쉼표 필수!))
single = (42,)  # Tuple
not_tuple = (42)  # Just a number

print(type(single))     # <class 'tuple'>
print(type(not_tuple))  # <class 'int'>
```

### Example 1: City Information (예제 1: 도시 정보)

A program that stores fixed city information in tuples.

도시의 고정 정보를 튜플로 저장하는 프로그램입니다.

```python
# City information program (도시 정보 프로그램)
print("🌆" + "=" * 38 + "🌆")
print("   World City Information")
print("🌆" + "=" * 38 + "🌆")

# City info (name, country, population, area) (도시 정보)
seoul = ("Seoul", "South Korea", 9776000, 605)
tokyo = ("Tokyo", "Japan", 13960000, 2194)
newyork = ("New York", "United States", 8336000, 783)

cities = [seoul, tokyo, newyork]

print("\nCity Information:")
print("=" * 40)

for city in cities:
    name, country, population, area = city  # Tuple unpacking (튜플 언패킹)
    density = population / area
  
    print(f"\n📍 {name} ({country})")
    print(f"   Population: {population:,}")
    print(f"   Area: {area}km²")
    print(f"   Density: {density:,.0f}/km²")

print("=" * 40)
```

---

## 2️⃣ Tuple Unpacking (튜플 언패킹)

You can assign tuple values to multiple variables at once.

튜플의 값을 여러 변수에 한 번에 할당할 수 있습니다.

```python
# Tuple unpacking (튜플 언패킹)
point = (10, 20)
x, y = point
print(f"x: {x}, y: {y}")  # x: 10, y: 20

# Multiple unpacking (여러 값 언패킹)
rgb = (255, 128, 0)
red, green, blue = rgb
print(f"R:{red}, G:{green}, B:{blue}")  # R:255, G:128, B:0

# Swap variables (변수 교환)
a, b = 5, 10
a, b = b, a  # Swap using unpacking (언패킹으로 교환)
print(f"a: {a}, b: {b}")  # a: 10, b: 5
```

---

## 3️⃣ What is a Set? (세트란?)

A set is an unordered collection that stores **unique values without duplicates**.

세트는 **중복 없는** 순서가 없는 자료구조입니다.

### Set Characteristics (세트의 특징)

```python
# Create set (세트 생성)
colors = {"red", "green", "blue"}
numbers = {1, 2, 3, 4, 5}

# Duplicates are removed (중복 제거)
items = {1, 2, 2, 3, 3, 3}
print(items)  # {1, 2, 3}

# Empty set (빈 세트)
empty_set = set()  # Not {} (must use set())
```

```
Set Characteristics (세트의 특징)

• Unordered (순서 없음)
• No duplicates (중복 없음)
• Mutable (변경 가능)
• Fast membership testing (멤버십 검사 빠름)
```

### Set Operations (세트 연산)

```python
# Add element (요소 추가)
colors = {"red", "blue"}
colors.add("green")
print(colors)  # {'red', 'blue', 'green'}

# Remove element (요소 제거)
colors.remove("red")
print(colors)  # {'blue', 'green'}

# Union (합집합)
set1 = {1, 2, 3}
set2 = {3, 4, 5}
union = set1 | set2  # {1, 2, 3, 4, 5}
print(union)

# Intersection (교집합)
intersection = set1 & set2  # {3}
print(intersection)

# Difference (차집합)
difference = set1 - set2  # {1, 2}
print(difference)
```

### Example 2: Unique Student IDs (예제 2: 중복 없는 학생 ID)

A program that removes duplicate student IDs using a set.

세트를 사용하여 중복된 학생 ID를 제거하는 프로그램입니다.

```python
# Student ID deduplication (학생 ID 중복 제거)
print("👥" + "=" * 38 + "👥")
print("   Unique Student ID Manager")
print("👥" + "=" * 38 + "👥")

# Student IDs with duplicates (중복된 학생 ID)
student_ids = [
    "SB001", "SB002", "SB003", "SB002",
    "SB004", "SB001", "SB005", "SB003"
]

print(f"\nOriginal count: {len(student_ids)}")
print(f"IDs: {student_ids}")

# Remove duplicates using set (세트로 중복 제거)
unique_ids = set(student_ids)
print(f"\nUnique count: {len(unique_ids)}")
print(f"Unique IDs: {sorted(unique_ids)}")

# Convert back to sorted list (정렬된 리스트로 변환)
final_ids = sorted(list(unique_ids))
print(f"\nSorted IDs:")
for id_num in final_ids:
    print(f"  {id_num}")

print("=" * 40)
```

---

## 4️⃣ Set Methods (세트 메서드)

```python
# add(): Add single element (한 개 추가)
colors = {"red", "blue"}
colors.add("green")

# update(): Add multiple elements (여러 개 추가)
colors.update({"yellow", "purple"})

# remove(): Remove element (제거 - 없으면 오류)
colors.remove("red")

# discard(): Remove element (제거 - 없어도 무방)
colors.discard("pink")

# clear(): Remove all (모두 제거)
colors.clear()

# copy(): Create copy (복사)
set1 = {1, 2, 3}
set2 = set1.copy()
```

### Example 3: Common Elements (예제 3: 공통 요소 찾기)

Finding common interests between friends.

친구들의 공통 관심사를 찾는 프로그램입니다.

```python
# Common interests finder (공통 관심사 찾기)
print("👫" + "=" * 38 + "👫")
print("   Common Interests Finder")
print("👫" + "=" * 38 + "👫")

# Friends and their interests (친구들과 관심사)
alice_interests = {"music", "sports", "coding", "gaming"}
bob_interests = {"music", "gaming", "movies", "cooking"}
charlie_interests = {"sports", "gaming", "reading"}

print("\nInterests:")
print(f"Alice: {alice_interests}")
print(f"Bob: {bob_interests}")
print(f"Charlie: {charlie_interests}")

# Common interests (공통 관심사)
common_all = alice_interests & bob_interests & charlie_interests
print(f"\nCommon (All three): {common_all}")

common_alice_bob = alice_interests & bob_interests
print(f"Common (Alice & Bob): {common_alice_bob}")

# Unique interests (고유한 관심사)
alice_unique = alice_interests - bob_interests - charlie_interests
print(f"\nAlice's unique: {alice_unique}")

print("=" * 40)
```

---

## 5️⃣ Tuple vs List vs Set (비교)

```python
# List: Ordered, mutable, allows duplicates (순서 있음, 변경 가능, 중복 허용)
my_list = [1, 2, 2, 3, 3, 3]
print(my_list)  # [1, 2, 2, 3, 3, 3]

# Tuple: Ordered, immutable, allows duplicates (순서 있음, 변경 불가, 중복 허용)
my_tuple = (1, 2, 2, 3, 3, 3)
print(my_tuple)  # (1, 2, 2, 3, 3, 3)

# Set: Unordered, mutable, no duplicates (순서 없음, 변경 가능, 중복 불허)
my_set = {1, 2, 2, 3, 3, 3}
print(my_set)  # {1, 2, 3}
```

### Example 4: Grade Tracker (예제 4: 성적 추적)

A program that tracks student grades using different data structures.

다양한 자료구조를 사용하여 학생 성적을 추적하는 프로그램입니다.

```python
# Grade tracking system (성적 추적 시스템)
print("📊" + "=" * 38 + "📊")
print("   Grade Tracking System")
print("📊" + "=" * 38 + "📊")

# Student grades (학생 성적)
# Using tuple for immutable grade records (변경 불가능한 성적 기록)
alice_grades = (95, 87, 92, 88)
bob_grades = (78, 82, 85, 80)

# Calculate average (평균 계산)
alice_avg = sum(alice_grades) / len(alice_grades)
bob_avg = sum(bob_grades) / len(bob_grades)

print(f"\nAlice's grades: {alice_grades}")
print(f"Alice's average: {alice_avg:.1f}")

print(f"\nBob's grades: {bob_grades}")
print(f"Bob's average: {bob_avg:.1f}")

# Using set to find unique grades (고유한 성적을 찾기)
all_grades_set = set(alice_grades) | set(bob_grades)
print(f"\nAll unique grades: {sorted(all_grades_set)}")

# Using list for mutable grade list (변경 가능한 성적 목록)
grades_list = [95, 87, 92, 88, 78, 82, 85, 80]
print(f"\nAll grades: {grades_list}")
print(f"Highest: {max(grades_list)}")
print(f"Lowest: {min(grades_list)}")

print("=" * 40)
```

---

## 📝 Summary of Key Concepts (핵심 개념 정리)

Tuples are immutable data structures useful for storing fixed data that shouldn't change. They can be unpacked to assign values to multiple variables at once. Sets are unordered collections that automatically remove duplicates, making them ideal for membership testing and set operations.

튜플은 변경될 수 없는 자료구조로 변하지 않아야 할 고정 데이터를 저장하기에 좋습니다. 튜플 언패킹으로 값을 여러 변수에 한 번에 할당할 수 있습니다. 세트는 순서가 없는 자료구조로 자동으로 중복을 제거하며 멤버십 검사와 집합 연산에 이상적입니다.

Understanding the differences between lists, tuples, and sets is essential for choosing the right data structure for each situation. Each has distinct advantages and use cases in Python programming.

리스트, 튜플, 세트의 차이를 이해하는 것은 각 상황에 맞는 자료구조를 선택하는 데 필수적입니다. 각각은 파이썬 프로그래밍에서 고유한 장점과 사용 사례가 있습니다.

---

## 💡 Practical Assignments (실습 과제)

### Assignment 1: Tuple Data Analysis (과제 1: 튜플 데이터 분석)

Write a program that analyzes a collection of tuples representing student data (name, score, grade).

학생 데이터(이름, 점수, 학년)를 나타내는 튜플 모음을 분석하는 프로그램을 작성하세요.

```python
# Hint
students = [
    ("Alice", 95, "A"),
    ("Bob", 87, "B"),
    ("Charlie", 92, "A")
]
# Unpack and analyze student data
```

### Assignment 2: Set Operations (과제 2: 세트 연산)

Write a program that performs set operations (union, intersection, difference) on multiple sets.

여러 세트에 대해 집합 연산(합집합, 교집합, 차집합)을 수행하는 프로그램을 작성하세요.

```python
# Hint
set1 = {1, 2, 3, 4, 5}
set2 = {4, 5, 6, 7, 8}
# Calculate union, intersection, difference
```

---

## ✅ Quiz (퀴즈)

### [Intermediate] Question 1

What is the output?

다음 코드의 출력 결과는?

```python
my_tuple = (1, 2, 3)
x, y, z = my_tuple
print(x, y, z)
```

1. (1, 2, 3)
2. 1 2 3
3. 123
4. Error

### [Intermediate] Question 2

What is the output?

다음 코드의 출력 결과는?

```python
colors = {"red", "green", "blue", "red"}
print(len(colors))
```

1. 4
2. 3
3. 1
4. Error

### [Intermediate] Question 3

What is the output?

다음 코드의 출력 결과는?

```python
set1 = {1, 2, 3}
set2 = {3, 4, 5}
result = set1 & set2
print(result)
```

1. {1, 2, 3, 4, 5}
2. {3}
3. {1, 2, 4, 5}
4. Error

### [Advanced] Question 4

Which is true about tuples?

튜플에 대해 맞는 것은?

```python
my_tuple = (1, 2, 3)
1) my_tuple[0] = 10  # Possible?
2) my_tuple.append(4)  # Possible?
3) x, y, z = my_tuple  # Possible?
4) my_tuple = ()  # Possible?
```

1. 1만 가능
2. 3, 4만 가능
3. 모두 불가능
4. 모두 가능

### [Advanced] Question 5

What is the output?

다음 코드의 출력 결과는?

```python
items = ["a", "b", "a", "c", "b", "a"]
unique = len(set(items))
print(unique)
```

1. 6
2. 3
3. 4
4. Error

---

## 🔑 Quiz Answers and Explanations (퀴즈 정답 및 해설)

**Question 1 Answer: 2**
Tuple unpacking assigns values to three variables: x=1, y=2, z=3. Output: 1 2 3

튜플 언패킹으로 세 변수에 값이 할당됩니다. 출력: 1 2 3

**Question 2 Answer: 2**
The set automatically removes duplicates. {"red", "green", "blue", "red"} becomes {"red", "green", "blue"}, length 3.

세트는 자동으로 중복을 제거합니다. 길이는 3입니다.

**Question 3 Answer: 2**
The & operator finds intersection. {1, 2, 3} & {3, 4, 5} = {3}

& 연산자는 교집합을 찾습니다. 결과는 {3}입니다.

**Question 4 Answer: 2**
Tuples are immutable, so 1 (changing) and 2 (append) are impossible. But 3 (unpacking) and 4 (reassignment) are possible.

튜플은 불변이므로 1과 2는 불가능하지만 3과 4는 가능합니다.

**Question 5 Answer: 2**
The set removes duplicates: {a, b, c}. Length = 3

세트는 "a", "b", "a", "c", "b", "a"를 {a, b, c}로 변환합니다. 길이는 3입니다.

---

## 🎯 Preview of Next Chapter (다음 장 예고)

In the next chapter, we will learn about dictionaries. Dictionaries store data as key-value pairs, making data access more intuitive and powerful. Dictionaries are one of the most important data structures in Python!

다음 장에서는 딕셔너리에 대해 배웁니다. 딕셔너리는 키-값 쌍으로 데이터를 저장하여 더욱 직관적이고 강력한 데이터 접근을 가능하게 합니다.

---

Thank you for your attention.

Cho Jeonghyun (peterchokr@gmail.com). Yeungnam University College
