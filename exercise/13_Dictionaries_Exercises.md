# Chapter 13: Dictionaries — Practice Problems

---

## 📝 Multiple Choice Questions

---

### 🟢 Beginner

**Problem 1.** Which correctly creates a dictionary?

① `d = ["name": "John"]`  
② `d = {"name": "John"}`  
③ `d = ("name": "John")`  
④ `d = {"name" = "John"}`  

---

**Problem 2.** What is the output of the following code?

```python
person = {"name": "John Doe", "age": 25, "city": "Seoul"}
print(person["age"])
```

① John Doe  
② 25  
③ Seoul  
④ Error  

---

**Problem 3.** What is the output of the following code?

```python
menu = {"coffee": 4000, "tea": 3000}
menu["juice"] = 3500
print(len(menu))
```

① 2  
② 3  
③ 4  
④ Error  

---

**Problem 4.** Which method does NOT raise an error if a key doesn't exist?

① `dict[key]`  
② `dict.get(key)`  
③ `dict.pop(key)`  
④ `dict.remove(key)`  

---

**Problem 5.** What is the output of the following code?

```python
d = {"a": 1, "b": 2, "c": 3}
print("b" in d)
```

① True  
② False  
③ 2  
④ Error  

---

**Problem 6.** What is the `student` dictionary after executing the following code?

```python
student = {"name": "John", "age": 20}
student["age"] = 21
```

① `{"name": "John", "age": 20}`  
② `{"name": "John", "age": 21}`  
③ `{"name": "John", "age": 20, "age": 21}`  
④ Error  

---

**Problem 7.** What is the output of the following code?

```python
d = {"x": 10, "y": 20, "z": 30}
del d["y"]
print(d)
```

① `{"x": 10, "y": 20, "z": 30}`  
② `{"x": 10, "z": 30}`  
③ `{"y": 20}`  
④ Error  

---

### 🟡 Intermediate

**Problem 8.** What is the output of the following code?

```python
info = {"name": "Jane", "major": "Business"}
result = info.get("student_id", "No info")
print(result)
```

① None  
② No info  
③ student_id  
④ Error  

---

**Problem 9.** What is the output of the following code?

```python
data = {"a": 1, "b": 2, "c": 3}
total = 0
for value in data.values():
    total = total + value
print(total)
```

① 3  
② 6  
③ abc  
④ Error  

---

**Problem 10.** What is the output of the following code?

```python
fruits = {"apple": 3, "banana": 5, "orange": 2}
keys = list(fruits.keys())
print(keys)
```

① `{"apple", "banana", "orange"}`  
② `["apple", "banana", "orange"]`  
③ `("apple", "banana", "orange")`  
④ `[3, 5, 2]`  

---

**Problem 11.** What is the output of the following code?

```python
menu = {"coffee": 4500, "tea": 3000, "juice": 4000}
for item, price in menu.items():
    if price >= 4000:
        print(item, end=" ")
```

① `coffee tea juice`  
② `coffee juice`  
③ `4500 4000`  
④ `coffee`  

---

**Problem 12.** What is the output of the following code?

```python
d = {"a": 1, "b": 2}
value = d.pop("b")
print(value, d)
```

① `2 {"a": 1}`  
② `{"a": 1} 2`  
③ `2 {"a": 1, "b": 2}`  
④ Error  

---

### 🔴 Advanced

**Problem 13.** What is the result of the following dictionary comprehension?

```python
result = {i: i ** 2 for i in range(1, 6)}
print(result)
```

① `[1, 4, 9, 16, 25]`  
② `{1: 1, 2: 4, 3: 9, 4: 16, 5: 25}`  
③ `{1, 4, 9, 16, 25}`  
④ Error  

---

**Problem 14.** What is the output of the following code?

```python
students = {
    "John": {"Korean": 80, "English": 90},
    "Jane": {"Korean": 95, "English": 85}
}
print(students["Jane"]["Korean"])
```

① 80  
② 90  
③ 95  
④ 85  

---

**Problem 15.** What is the output of the following code?

```python
text = "hello"
count = {}
for ch in text:
    if ch in count:
        count[ch] = count[ch] + 1
    else:
        count[ch] = 1
print(count["l"])
```

① 1  
② 2  
③ 3  
④ Error  

---

## 📝 Short Answer Questions

---

### 🟢 Beginner

**Problem 16.** Explain at least 2 differences between dictionaries and lists. Give an example where a dictionary is more appropriate.

---

**Problem 17.** Write the output of the following code.

```python
score = {"Korean": 85, "English": 92, "Math": 78}
print(score.get("Science", 0))
print(score.get("Korean"))
print(len(score))
```

---

**Problem 18.** Explain the difference between bracket access `[]` and `get()` method. Write the output of the following code.

```python
d = {"a": 10, "b": 20}
print(d.get("c", -1))
# print(d["c"])  ← This code is commented
```

---

### 🟡 Intermediate

**Problem 19.** Explain the return values of `keys()`, `values()`, and `items()` methods. Write the output of the following code.

```python
menu = {"Americano": 4500, "Latte": 5000, "Cappuccino": 5500}
total = 0
for drink, price in menu.items():
    total = total + price
print(f"Menu items: {len(menu)}")
print(f"Total price: ${total}")
```

---

**Problem 20.** Write the output of the following code and explain the dictionary counting pattern.

```python
fruits = ["apple", "banana", "apple", "orange", "banana", "apple"]
count = {}
for fruit in fruits:
    if fruit in count:
        count[fruit] = count[fruit] + 1
    else:
        count[fruit] = 1
print(count)
```

---

### 🔴 Advanced

**Problem 21.** Write the output of the following code and explain nested dictionary access and grouping patterns.

```python
students = [
    ("John", "CS"),
    ("Jane", "Business"),
    ("Mike", "CS"),
    ("Sarah", "Business"),
    ("David", "Design")
]

by_major = {}
for name, major in students:
    if major in by_major:
        by_major[major].append(name)
    else:
        by_major[major] = [name]

for major, names in by_major.items():
    print(f"{major}: {names} ({len(names)} students)")
```

---

## 💻 Hands-On Problems

---

### 🟢 Beginner

**Problem 22.** Write a program that meets the following requirements.

> For fruit price dictionary `fruits = {"apple": 1500, "banana": 3000, "orange": 2000, "grape": 4000}`, perform the following:
> 1) Print all fruits and prices
> 2) Add "strawberry": 5000
> 3) Change "banana" price to 3500
> 4) Delete "orange"
> 5) Print final result

Output example:

```
=== Fruit Price List ===
apple: $1,500
banana: $3,000
orange: $2,000
grape: $4,000

[After Changes]
apple: $1,500
banana: $3,500
grape: $4,000
strawberry: $5,000
Total: 4 items
```

---

**Problem 23.** Write a program that meets the following requirements.

> For score dictionary `scores = {"Korean": 85, "English": 92, "Math": 78, "Science": 88, "History": 76}`,  
> find total score, average, highest subject, and lowest subject.

Output example:

```
=== Grade Report ===
Korean: 85 points
English: 92 points
Math: 78 points
Science: 88 points
History: 76 points
--------------
Total: 419 points
Average: 83.8 points
Highest: English (92 points)
Lowest: History (76 points)
```

---

### 🟡 Intermediate

**Problem 24.** Write a program that meets the following requirements.

> For text `text = "python is great and python is easy and python is fun"`,  
> count each word frequency and print sorted by frequency.

Output example:

```
=== Word Frequency Analysis ===
Original: python is great and python is easy and python is fun

Word Frequency (sorted):
python: 3 times
is: 3 times
and: 2 times
great: 1 time
easy: 1 time
fun: 1 time

Total words: 11
Unique words: 6
```

---

**Problem 25.** Write a program that meets the following requirements.

> User inputs product information (name, price, quantity). Store in dictionary and print summary.

Output example (Input: Laptop/1200/2, Phone/800/5, Tablet/600/3):

```
=== Inventory ===
1. Laptop: $1,200 × 2 = $2,400
2. Phone: $800 × 5 = $4,000
3. Tablet: $600 × 3 = $1,800

Total Items: 10
Total Value: $8,200
```

---

### 🔴 Advanced

**Problem 26.** Write a program that meets the following requirements.

> Create a student grade management system with analysis.
>
> Students: John/85/92/88, Jane/95/88/90, Mike/78/85/82, Sarah/92/94/89, David/88/87/91
>
> Analysis: total score, average, grade, group by grade level

Output example:

```
=== Student Grade System ===

1. John
   Subjects: 85, 92, 88
   Total: 265, Average: 88.3, Grade: B

2. Jane
   Subjects: 95, 88, 90
   Total: 273, Average: 91.0, Grade: A

...

=== Grade Distribution ===
A (90+): 1 student
B (80-89): 3 students
C (70-79): 1 student
```

---
---

# 🔑 Answer Key and Explanations

---

## 📝 Multiple Choice Answers

---

### 🟢 Beginner

**Problem 1. Answer: ② `d = {"name": "John"}`**

Dictionaries use **curly braces `{}`** with **colon `:` ** for key-value pairs. `[]` for lists, `()` for tuples.

---

**Problem 2. Answer: ② 25**

Dictionary access uses square brackets with the key. `person["age"]` returns `25`.

---

**Problem 3. Answer: ② 3**

`menu["juice"] = 3500` adds a new key-value pair. Dictionary grows from 2 to 3 items.

---

**Problem 4. Answer: ② `dict.get(key)`**

`get()` returns `None` (or default) if key missing. Other methods raise errors.

---

**Problem 5. Answer: ① True**

The `in` operator checks if a key exists. `"b"` is a key in the dictionary.

---

**Problem 6. Answer: ② `{"name": "John", "age": 21}`**

Assigning to existing key updates the value. The dictionary now has `age: 21`.

---

**Problem 7. Answer: ② `{"x": 10, "z": 30}`**

`del` removes the key-value pair. Dictionary is missing "y".

---

### 🟡 Intermediate

**Problem 8. Answer: ② No info**

`get()` returns the default "No info" since key "student_id" doesn't exist.

---

**Problem 9. Answer: ② 6**

`values()` returns `[1, 2, 3]`. Sum: `1 + 2 + 3 = 6`.

---

**Problem 10. Answer: ② `["apple", "banana", "orange"]`**

`keys()` returns a view, `list()` converts it to a list.

---

**Problem 11. Answer: ② `coffee juice`**

Loop checks `price >= 4000`. "coffee" (4500) and "juice" (4000) qualify, "tea" (3000) doesn't.

---

**Problem 12. Answer: ① `2 {"a": 1}`**

`pop()` removes "b" and returns its value `2`. Dictionary becomes `{"a": 1}`.

---

### 🔴 Advanced

**Problem 13. Answer: ② `{1: 1, 2: 4, 3: 9, 4: 16, 5: 25}`**

Dictionary comprehension creates `key: value` pairs. `{i: i²}` for i from 1 to 5.

---

**Problem 14. Answer: ③ 95**

Nested access: `students["Jane"]` returns inner dict, `["Korean"]` gets `95`.

---

**Problem 15. Answer: ② 2**

Character "l" appears twice in "hello". Count incremented each time.

---

## 📝 Short Answer Key

---

### 🟢 Beginner

**Problem 16. Model Answer:**

**Differences:**
- Lists use indexes (0, 1, 2...), dictionaries use **keys**
- Lists are **ordered**, dictionary order depends on insertion (Python 3.7+)
- Lists access by position, dictionaries access by meaningful key

**Example:** Storing student info with name as key is better than storing in list order.

---

**Problem 17. Model Answer:**

```
0
85
3
```

- `get("Science", 0)` → not found, returns default 0
- `get("Korean")` → found, returns 85
- `len()` → 3 key-value pairs

---

**Problem 18. Model Answer:**

- Bracket `[]` raises `KeyError` if key missing
- `get()` returns `None` or default if key missing

**Output:**
```
-1
```

---

### 🟡 Intermediate

**Problem 19. Model Answer:**

- `keys()` → returns dict_keys (all keys)
- `values()` → returns dict_values (all values)
- `items()` → returns dict_items (key-value tuples)

**Output:**
```
Menu items: 3
Total price: $14500
```

(4500 + 5000 + 5500 = 14500)

---

**Problem 20. Model Answer:**

**Output:**
```
{'apple': 3, 'banana': 2, 'orange': 1}
```

**Counting pattern:**
1. Check if item is in dict
2. If yes, increment count
3. If no, initialize count to 1
4. Result: frequency dict

---

### 🔴 Advanced

**Problem 21. Model Answer:**

**Output:**
```
CS: ['John', 'Mike'] (2 students)
Business: ['Jane', 'Sarah'] (2 students)
Design: ['David'] (1 students)
```

**Nested dictionary grouping:**
- Check if major exists in dict
- If yes, append name to list
- If no, create new list with name
- Access: `by_major[major]` gets list of names

---

## 💻 Hands-On Solutions

---

### 🟢 Beginner

**Problem 22. Model Answer:**

```python
fruits = {"apple": 1500, "banana": 3000, "orange": 2000, "grape": 4000}

print("=== Fruit Price List ===")
for fruit, price in fruits.items():
    print(f"{fruit}: ${price:,}")

# Add strawberry
fruits["strawberry"] = 5000

# Modify banana price
fruits["banana"] = 3500

# Delete orange
del fruits["orange"]

# Print final result
print("\n[After Changes]")
for fruit, price in fruits.items():
    print(f"{fruit}: ${price:,}")
print(f"Total: {len(fruits)} items")
```

---

**Problem 23. Model Answer:**

```python
scores = {"Korean": 85, "English": 92, "Math": 78, "Science": 88, "History": 76}

print("=== Grade Report ===")
for subject, score in scores.items():
    print(f"{subject}: {score} points")

total = sum(scores.values())
average = total / len(scores)
highest_subject = max(scores, key=scores.get)
lowest_subject = min(scores, key=scores.get)

print("-" * 14)
print(f"Total: {total} points")
print(f"Average: {average:.1f} points")
print(f"Highest: {highest_subject} ({scores[highest_subject]} points)")
print(f"Lowest: {lowest_subject} ({scores[lowest_subject]} points)")
```

---

### 🟡 Intermediate (Problem 24)

**Problem 24. Model Answer:**

```python
text = "python is great and python is easy and python is fun"
words = text.split()

word_count = {}
for word in words:
    if word in word_count:
        word_count[word] = word_count[word] + 1
    else:
        word_count[word] = 1

# Sort by frequency (descending)
sorted_words = sorted(word_count.items(), key=lambda x: x[1], reverse=True)

print("=== Word Frequency Analysis ===")
print(f"Original: {text}\n")
print("Word Frequency (sorted):")
for word, count in sorted_words:
    print(f"{word}: {count} time{'s' if count > 1 else ''}")

print(f"\nTotal words: {len(words)}")
print(f"Unique words: {len(word_count)}")
```

---

### 🟡 Intermediate (Problem 25)

**Problem 25. Model Answer:**

```python
inventory = {}
total_items = 0
total_value = 0

for i in range(3):
    name = input(f"Product {i+1} name: ")
    price = int(input(f"Product {i+1} price: "))
    quantity = int(input(f"Product {i+1} quantity: "))
    
    inventory[name] = {"price": price, "quantity": quantity}
    total_items = total_items + quantity
    total_value = total_value + (price * quantity)

print("\n=== Inventory ===")
for i, (name, info) in enumerate(inventory.items(), 1):
    price = info["price"]
    quantity = info["quantity"]
    value = price * quantity
    print(f"{i}. {name}: ${price} × {quantity} = ${value:,}")

print(f"\nTotal Items: {total_items}")
print(f"Total Value: ${total_value:,}")
```

---

### 🔴 Advanced (Problem 26)

**Problem 26. Model Answer:**

```python
students_data = {
    "John": [85, 92, 88],
    "Jane": [95, 88, 90],
    "Mike": [78, 85, 82],
    "Sarah": [92, 94, 89],
    "David": [88, 87, 91]
}

def get_grade(avg):
    if avg >= 90: return "A"
    elif avg >= 80: return "B"
    elif avg >= 70: return "C"
    else: return "D"

print("=== Student Grade System ===\n")
grades_count = {"A": 0, "B": 0, "C": 0, "D": 0}

for i, (name, scores) in enumerate(students_data.items(), 1):
    total = sum(scores)
    average = total / len(scores)
    grade = get_grade(average)
    grades_count[grade] = grades_count[grade] + 1
    
    print(f"{i}. {name}")
    print(f"   Subjects: {', '.join(map(str, scores))}")
    print(f"   Total: {total}, Average: {average:.1f}, Grade: {grade}\n")

print("=== Grade Distribution ===")
for grade in ["A", "B", "C", "D"]:
    count = grades_count[grade]
    if count > 0:
        min_score = 90 if grade == "A" else 80 if grade == "B" else 70 if grade == "C" else 0
        max_score = 100 if grade == "A" else 89 if grade == "B" else 79 if grade == "C" else 69
        print(f"{grade} ({min_score}-{max_score}): {count} student{'s' if count > 1 else ''}")
```

---

Professor Cho Jeonghyun (peterchokr@gmail.com)  
Yeungnam University College.
