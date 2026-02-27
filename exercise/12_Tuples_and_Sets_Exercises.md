# Chapter 12: Tuples and Sets — Practice Problems

---

## 📝 Multiple Choice Questions

---

### 🟢 Beginner

**Problem 1.** What is the correct way to create a tuple in Python?

① `t = [1, 2, 3]`
② `t = (1, 2, 3)`
③ `t = {1, 2, 3}`
④ `t = <1, 2, 3>`

---

**Problem 2.** What is the output of the following code?

```python
t = (10, 20, 30)
print(t[1])
```

① 10
② 20
③ 30
④ Error

---

**Problem 3.** What is the output of the following code?

```python
t = (10, 20, 30)
t[0] = 100
print(t)
```

① `(100, 20, 30)`
② `(10, 20, 30)`
③ `[100, 20, 30]`
④ Error

---

**Problem 4.** Which correctly creates a tuple with one item?

① `t = (42)`
② `t = (42,)`
③ `t = [42]`
④ `t = {42}`

---

**Problem 5.** What is the output of the following code?

```python
numbers = {1, 2, 2, 3, 3, 3}
print(numbers)
```

① `{1, 2, 2, 3, 3, 3}`
② `{1, 2, 3}`
③ `[1, 2, 3]`
④ Error

---

**Problem 6.** Which correctly creates an empty set?

① `s = {}`
② `s = set()`
③ `s = ()`
④ `s = []`

---

**Problem 7.** What is the output of the following code?

```python
fruits = {"apple", "banana"}
fruits.add("orange")
fruits.add("apple")
print(len(fruits))
```

① 2
② 3
③ 4
④ Error

---

### 🟡 Intermediate

**Problem 8.** What is the output of the following code?

```python
point = (10, 20)
x, y = point
print(x + y)
```

① `(10, 20)`
② 30
③ `1020`
④ Error

---

**Problem 9.** What is the output of the following code?

```python
a = 5
b = 10
a, b = b, a
print(a, b)
```

① `5 10`
② `10 5`
③ `10 10`
④ Error

---

**Problem 10.** What is the output of the following code?

```python
a = {1, 2, 3}
b = {3, 4, 5}
print(a | b)
```

① `{3}`
② `{1, 2}`
③ `{1, 2, 3, 4, 5}`
④ `{4, 5}`

---

**Problem 11.** What is the output of the following code?

```python
a = {1, 2, 3, 4}
b = {3, 4, 5, 6}
print(a & b)
```

① `{1, 2, 3, 4, 5, 6}`
② `{3, 4}`
③ `{1, 2}`
④ `{5, 6}`

---

**Problem 12.** What is the output of the following code?

```python
a = {1, 2, 3, 4}
b = {3, 4, 5, 6}
print(a - b)
```

① `{1, 2}`
② `{5, 6}`
③ `{3, 4}`
④ `{1, 2, 5, 6}`

---

### 🔴 Advanced

**Problem 13.** What is the output of the following code?

```python
colors = {"red", "blue", "green"}
colors.discard("yellow")
colors.remove("blue")
print(len(colors))
```

① 1
② 2
③ 3
④ Error

---

**Problem 14.** What is the output of the following code?

```python
a = {1, 2}
b = {1, 2, 3, 4}
print(a.issubset(b))
print(b.issuperset(a))
```

① `True` `False`
② `False` `True`
③ `True` `True`
④ `False` `False`

---

**Problem 15.** What is the output of the following code?

```python
data = [3, 1, 4, 1, 5, 9, 2, 6, 5, 3, 5]
unique = set(data)
result = sorted(unique)
print(result)
```

① `{1, 2, 3, 4, 5, 6, 9}`
② `[1, 2, 3, 4, 5, 6, 9]`
③ `[3, 1, 4, 5, 9, 2, 6]`
④ `(1, 2, 3, 4, 5, 6, 9)`

---

## 📝 Short Answer Questions

---

### 🟢 Beginner

**Problem 16.** Compare tuples and lists and explain at least 2 similarities and 2 differences.

---

**Problem 17.** Explain 3 characteristics of sets and write the result of converting list `[1, 2, 2, 3, 3, 4]` to a set.

---

**Problem 18.** Write the output of the following code.

```python
info = ("John Smith", 20, "New York")
name, age, city = info
print(f"{name} is {age} years old and lives in {city}.")
```

---

### 🟡 Intermediate

**Problem 19.** Explain the difference between `remove()` and `discard()` in sets. Write the output of the following code.

```python
colors = {"red", "blue", "green", "yellow"}
colors.discard("purple")
colors.remove("yellow")
print(colors)
print(len(colors))
```

---

**Problem 20.** Write the output of the following code and explain the meaning of union, intersection, and difference operations.

```python
korean = {"John", "Jane", "Mike", "Sarah"}
math_class = {"Jane", "Sarah", "Tom", "Lisa"}

both = korean & math_class
only_korean = korean - math_class
all_students = korean | math_class

print(f"Both classes: {both}")
print(f"Korean only: {only_korean}")
print(f"Total students: {len(all_students)}")
```

---

### 🔴 Advanced

**Problem 21.** Write the output of the following code and explain each step.

```python
scores = [
    ("John", 85),
    ("Jane", 92),
    ("Mike", 78),
    ("Sarah", 92),
    ("David", 85)
]

# Extract unique scores
unique_scores = set()
for name, score in scores:
    unique_scores.add(score)

print(f"Unique scores: {sorted(unique_scores)}")
print(f"Number of unique scores: {len(unique_scores)}")

# Students with 90+ points
top_students = []
for name, score in scores:
    if score >= 90:
        top_students.append(name)

print(f"90+ points: {top_students}")
```

---

## 💻 Hands-On Problems

---

### 🟢 Beginner

**Problem 22.** Write a program that meets the following requirements.

> Store 3 cities' information as tuples and print them.Each tuple consists of `(city name, country, population)`.
>
> - Seoul, South Korea, 9776000
> - Tokyo, Japan, 13960000
> - New York, USA, 8336000

Output example:

```
=== World City Information ===
1. Seoul (South Korea) - Population: 9,776,000
2. Tokyo (Japan) - Population: 13,960,000
3. New York (USA) - Population: 8,336,000
```

---

**Problem 23.** Write a program that meets the following requirements.

> For the list `items = ["apple", "banana", "apple", "orange", "banana", "apple", "grape"]`,
> use sets to remove duplicates and print unique items and counts.

Output example:

```
Original: ['apple', 'banana', 'apple', 'orange', 'banana', 'apple', 'grape']
Total Count: 7
Unique Items: 4

Item Counts:
- apple: 3
- banana: 2
- orange: 1
- grape: 1
```

---

### 🟡 Intermediate

**Problem 24.** Write a program that meets the following requirements.

> Manage two club membership lists as sets and analyze them.
>
> - Coding Club: `{"John", "Jane", "Mike", "Sarah", "David"}`
> - Music Club: `{"Jane", "Sarah", "Tom", "Lisa"}`
>
> Output: members in both clubs, members in coding only, members in music only, total members

Output example:

```
=== Club Member Analysis ===

Coding Club: 5 members
Music Club: 4 members

Both clubs: Jane, Sarah
Coding only: John, Mike, David
Music only: Tom, Lisa

Total members: 7
```

---

**Problem 25.** Write a program that meets the following requirements.

> Receive 5 students' information as tuples, save them in a list, and print analysis results.
> Each student info is a tuple: `(name, age, major)`.
>
> Output: all students, average age, number of students per major

Output example (Input: John/20/CS, Jane/21/Business, Mike/22/CS, Sarah/20/Design, David/21/CS):

```
=== Student Information ===
1. John (20 years old, CS)
2. Jane (21 years old, Business)
3. Mike (22 years old, CS)
4. Sarah (20 years old, Design)
5. David (21 years old, CS)

Average Age: 20.8

Students per Major:
- CS: 3
- Business: 1
- Design: 1
```

---

### 🔴 Advanced

**Problem 26.** Write a program that meets the following requirements.

> Manage course enrollment lists as sets and perform comprehensive analysis.
>
> - Python: `{"John", "Jane", "Mike", "Sarah", "David"}`
> - Database: `{"Jane", "Mike", "Tom", "Lisa", "Sarah"}`
> - Web Dev: `{"John", "Tom", "Sarah", "Alex"}`
>
> Analysis:
>
> 1) Students taking all three courses
> 2) Students taking exactly one course
> 3) Python students but not Database students
> 4) Total students (no duplicates)
> 5) Courses per student

Output example:

```
=== Course Analysis ===

1) All three courses: Sarah
2) Exactly one course: David, Lisa, Alex
3) Python but not Database: John, David
4) Total students: 8

5) Courses per student:
- John: 2 courses
- Jane: 2 courses
- Mike: 2 courses
- Sarah: 3 courses
- David: 1 course
- Tom: 2 courses
- Lisa: 1 course
- Alex: 1 course
```

---

---

# 🔑 Answer Key and Explanations

---

## 📝 Multiple Choice Answers

---

### 🟢 Beginner

**Problem 1. Answer: ② `t = (1, 2, 3)`**

Tuples are created with **parentheses `()`**. `[]` creates lists, `{}` creates sets or dictionaries.

---

**Problem 2. Answer: ② 20**

Like lists, tuples use indexing. `t[1]` is the second item, which is `20`.

---

**Problem 3. Answer: ④ Error**

Tuples are **immutable** (unchangeable), so you cannot modify items. `t[0] = 100` raises `TypeError`.

---

**Problem 4. Answer: ② `t = (42,)`**

A single-item tuple requires a **comma**. `(42)` is just a number in parentheses (int type).

---

**Problem 5. Answer: ② `{1, 2, 3}`**

Sets **do not allow duplicates**. Duplicate values are automatically removed, leaving only `{1, 2, 3}`.

---

**Problem 6. Answer: ② `s = set()`**

`{}` creates an empty **dictionary**, not a set. Empty sets must use `set()` function.

---

**Problem 7. Answer: ② 3**

`add("orange")` makes 3 items; `add("apple")` is ignored since it already exists. Final set has 3 items.

---

### 🟡 Intermediate

**Problem 8. Answer: ② 30**

Tuple unpacking assigns `x = 10`, `y = 20`. `x + y = 30`.

---

**Problem 9. Answer: ② `10 5`**

`a, b = b, a` swaps values using tuple unpacking. Right side forms tuple `(10, 5)` first.

---

**Problem 10. Answer: ③ `{1, 2, 3, 4, 5}`**

`|` is the **union** operator. It combines all elements from both sets.

---

**Problem 11. Answer: ② `{3, 4}`**

`&` is the **intersection** operator. It returns elements **present in both** sets.

---

**Problem 12. Answer: ① `{1, 2}`**

`-` is the **difference** operator. `a - b` returns elements in `a` but **not in `b`**.

---

### 🔴 Advanced

**Problem 13. Answer: ② 2**

`discard("yellow")` doesn't error if missing. `remove("blue")` removes it. Result: `{"red", "green"}`, length 2.

---

**Problem 14. Answer: ③ `True` `True`**

`{1, 2}` is a **subset** of `{1, 2, 3, 4}`, so `issubset()` → `True`. `{1, 2, 3, 4}` is a **superset** of `{1, 2}`, so `issuperset()` → `True`.

---

**Problem 15. Answer: ② `[1, 2, 3, 4, 5, 6, 9]`**

`set(data)` removes duplicates, `sorted()` returns a **list** in sorted order.

---

## 📝 Short Answer Key

---

### 🟢 Beginner

**Problem 16. Model Answer:**

**Similarities:**

- Both store multiple values in order
- Both support indexing and slicing
- Both support `for` loops

**Differences:**

- Tuples use `()`, lists use `[]`
- Tuples are **immutable** (unchangeable), lists are **mutable** (changeable)
- Lists have modify methods (append, remove), tuples don't
- Tuples are faster and use less memory

---

**Problem 17. Model Answer:**

**3 characteristics of sets:**

1. **No duplicates** — same values stored only once
2. **No order** — no index access, output order undefined
3. **Set operations** — union (`|`), intersection (`&`), difference (`-`)

**Conversion result:**

```python
set([1, 2, 2, 3, 3, 4])  # → {1, 2, 3, 4}
```

---

**Problem 18. Model Answer:**

```
John Smith is 20 years old and lives in New York.
```

Tuple unpacking assigns name, age, city to variables. F-string formats the output.

---

### 🟡 Intermediate

**Problem 19. Model Answer:**

- `remove(value)`: Removes value. Raises **KeyError** if missing.
- `discard(value)`: Removes value. **No error** if missing.

**Output:**

```
{'red', 'blue', 'green'}
3
```

1. `discard("purple")` → no error, 4 items remain
2. `remove("yellow")` → removes it, 3 items

(Note: set order is undefined)

---

**Problem 20. Model Answer:**

**Set operations:**

- **Union (`|`)**: All elements from both sets (no duplicates)
- **Intersection (`&`)**: Elements **common to both** sets
- **Difference (`-`)**: Elements in first set but **not in second**

**Output:**

```
Both classes: {'Jane', 'Sarah'}
Korean only: {'John', 'Mike'}
Total students: 6
```

- `korean & math_class` → common: `{"Jane", "Sarah"}`
- `korean - math_class` → korean only: `{"John", "Mike"}`
- `korean | math_class` → total 6: `{"John", "Jane", "Mike", "Sarah", "Tom", "Lisa"}`

---

### 🔴 Advanced

**Problem 21. Model Answer:**

**Output:**

```
Unique scores: [78, 85, 92]
Number of unique scores: 3
90+ points: ['Jane', 'Sarah']
```

**Step-by-step:**

1. List `scores` contains 5 `(name, score)` tuples
2. Loop unpacks tuples into name and score variables
3. `unique_scores` set removes duplicates 85 and 92 → `{85, 92, 78}`
4. `sorted()` returns list `[78, 85, 92]`
5. Second loop finds students with score ≥ 90 → `['Jane', 'Sarah']`

---

## 💻 Hands-On Solutions

---

### 🟢 Beginner

**Problem 22. Model Answer:**

```python
# City information as tuples
seoul = ("Seoul", "South Korea", 9776000)
tokyo = ("Tokyo", "Japan", 13960000)
newyork = ("New York", "USA", 8336000)

cities = [seoul, tokyo, newyork]

print("=== World City Information ===")
for i in range(len(cities)):
    name, country, population = cities[i]  # tuple unpacking
    print(f"{i+1}. {name} ({country}) - Population: {population:,}")
```

Key: Store fixed data in tuples, collect in list, use unpacking in loops.

---

**Problem 23. Model Answer:**

```python
items = ["apple", "banana", "apple", "orange", "banana", "apple", "grape"]

# Remove duplicates with set
unique = set(items)

print(f"Original: {items}")
print(f"Total Count: {len(items)}")
print(f"Unique Items: {len(unique)}")

print("\nItem Counts:")
for item in unique:
    count = items.count(item)
    print(f"- {item}: {count}")
```

Key: `set()` removes duplicates, `count()` counts occurrences in original list.

---

### 🟡 Intermediate

**Problem 24. Model Answer:**

```python
coding = {"John", "Jane", "Mike", "Sarah", "David"}
music = {"Jane", "Sarah", "Tom", "Lisa"}

# Set operations
both = coding & music          # intersection
only_coding = coding - music   # difference
only_music = music - coding    # difference
all_members = coding | music   # union

print("=== Club Member Analysis ===\n")
print(f"Coding Club: {len(coding)} members")
print(f"Music Club: {len(music)} members")

print(f"\nBoth clubs: {', '.join(both)}")
print(f"Coding only: {', '.join(only_coding)}")
print(f"Music only: {', '.join(only_music)}")
print(f"\nTotal members: {len(all_members)}")
```

Key: Use `&` for common, `-` for exclusive, `|` for total. `join()` formats output.

---

### 🟡 Intermediate (Problem 25)

**Problem 25. Model Answer:**

```python
students = []

for i in range(5):
    name = input(f"Student {i+1} Name: ")
    age = int(input(f"Student {i+1} Age: "))
    major = input(f"Student {i+1} Major: ")
    students.append((name, age, major))  # store as tuple

# Print students
print("\n=== Student Information ===")
for i in range(len(students)):
    name, age, major = students[i]
    print(f"{i+1}. {name} ({age} years old, {major})")

# Average age
total_age = 0
for name, age, major in students:
    total_age = total_age + age
avg_age = total_age / len(students)
print(f"\nAverage Age: {avg_age}")

# Students per major
majors = set()
for name, age, major in students:
    majors.add(major)

print("\nStudents per Major:")
for m in majors:
    count = 0
    for name, age, major in students:
        if major == m:
            count = count + 1
    print(f"- {m}: {count}")
```

Key: Combine tuples and lists, use unpacking in loops, extract unique majors with set.

---

### 🔴 Advanced (Problem 26)

**Problem 26. Model Answer:**

```python
python_class = {"John", "Jane", "Mike", "Sarah", "David"}
db_class = {"Jane", "Mike", "Tom", "Lisa", "Sarah"}
web_class = {"John", "Tom", "Sarah", "Alex"}

# 1) All three courses
all_three = python_class & db_class & web_class
print("=== Course Analysis ===\n")
print(f"1) All three courses: {', '.join(all_three)}")

# All students
all_students = python_class | db_class | web_class

# 2) Exactly one course
one_only = set()
for student in all_students:
    count = 0
    if student in python_class:
        count = count + 1
    if student in db_class:
        count = count + 1
    if student in web_class:
        count = count + 1
    if count == 1:
        one_only.add(student)
print(f"2) Exactly one course: {', '.join(one_only)}")

# 3) Python but not Database
python_not_db = python_class - db_class
print(f"3) Python but not Database: {', '.join(python_not_db)}")

# 4) Total students
print(f"4) Total students: {len(all_students)}")

# 5) Courses per student
print(f"\n5) Courses per student:")
for student in all_students:
    count = 0
    if student in python_class:
        count = count + 1
    if student in db_class:
        count = count + 1
    if student in web_class:
        count = count + 1
    print(f"- {student}: {count} courses")
```

Key: Chain `&` for multiple intersections, use `in` to check membership, count by iterating through all sets.

---


Thank you for your attention.   
Cho Jeonghyun ([peterchokr@gmail.com](mailto:peterchokr@gmail.com)). Yeungnam University College

"Produced in collaboration with Claude and Gemini."
