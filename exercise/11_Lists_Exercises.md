# Chapter 11: Lists — Practice Problems

---

## 📝 Multiple Choice Questions

---

### 🟢 Beginner

**Problem 1.** What is the correct way to create a list in Python?

① `fruits = (1, 2, 3)`
② `fruits = [1, 2, 3]`
③ `fruits = {1, 2, 3}`
④ `fruits = <1, 2, 3>`

---

**Problem 2.** What is the output of the following code?

```python
colors = ["Red", "Green", "Blue"]
print(colors[0])
```

① Red
② Green
③ Blue
④ Error

---

**Problem 3.** What is the output of the following code?

```python
nums = [10, 20, 30, 40, 50]
print(nums[-1])
```

① 10
② 50
③ 40
④ -1

---

**Problem 4.** What is the output of the following code?

```python
fruits = ["apple", "banana", "orange"]
fruits.append("grape")
print(len(fruits))
```

① 3
② 4
③ 5
④ Error

---

**Problem 5.** What is the list `fruits` after executing the following code?

```python
fruits = ["apple", "banana", "orange"]
fruits[1] = "strawberry"
```

① `["apple", "banana", "orange"]`
② `["strawberry", "banana", "orange"]`
③ `["apple", "strawberry", "orange"]`
④ `["apple", "banana", "strawberry"]`

---

**Problem 6.** Which correctly describes the `pop()` method?

① Adds an item to the end of the list
② Removes an item from the list and returns its value
③ Sorts the list
④ Returns the length of the list

---

**Problem 7.** What is the output of the following code?

```python
nums = [3, 1, 4, 1, 5]
nums.sort()
print(nums)
```

① `[3, 1, 4, 1, 5]`
② `[1, 1, 3, 4, 5]`
③ `[5, 4, 3, 1, 1]`
④ `[1, 3, 4, 5]`

---

### 🟡 Intermediate

**Problem 8.** What is the output of the following code?

```python
nums = [0, 1, 2, 3, 4, 5]
print(nums[1:4])
```

① `[0, 1, 2, 3]`
② `[1, 2, 3]`
③ `[1, 2, 3, 4]`
④ `[0, 1, 2]`

---

**Problem 9.** What is the output of the following code?

```python
nums = [10, 20, 30, 40, 50]
print(nums[:3])
```

① `[10, 20, 30]`
② `[10, 20, 30, 40]`
③ `[30, 40, 50]`
④ `[40, 50]`

---

**Problem 10.** What is the output of the following code?

```python
items = ["A", "B", "C", "D"]
items.insert(2, "X")
print(items)
```

① `["A", "B", "X", "C", "D"]`
② `["A", "X", "B", "C", "D"]`
③ `["X", "A", "B", "C", "D"]`
④ `["A", "B", "C", "X", "D"]`

---

**Problem 11.** What is the output of the following code?

```python
fruits = ["apple", "banana", "orange", "banana"]
fruits.remove("banana")
print(fruits)
```

① `["apple", "orange"]`
② `["apple", "orange", "banana"]`
③ `["apple", "banana", "orange"]`
④ Error

---

**Problem 12.** What is the output of the following code?

```python
nums = [1, 2, 3, 4, 5]
print(nums[::2])
```

① `[1, 2]`
② `[2, 4]`
③ `[1, 3, 5]`
④ `[1, 2, 3]`

---

### 🔴 Advanced

**Problem 13.** What is the output of the following code?

```python
nums = [1, 2, 3, 4, 5]
print(nums[::-1])
```

① `[1, 2, 3, 4, 5]`
② `[5, 4, 3, 2, 1]`
③ `[2, 4]`
④ Error

---

**Problem 14.** What is the result of the following list comprehension?

```python
result = [x ** 2 for x in range(1, 6)]
print(result)
```

① `[1, 2, 3, 4, 5]`
② `[2, 4, 6, 8, 10]`
③ `[1, 4, 9, 16, 25]`
④ `[1, 8, 27, 64, 125]`

---

**Problem 15.** What is the output of the following code?

```python
result = [x for x in range(1, 11) if x % 3 == 0]
print(result)
```

① `[1, 2, 4, 5, 7, 8, 10]`
② `[3, 6, 9]`
③ `[0, 3, 6, 9]`
④ `[3, 6, 9, 12]`

---

## 📝 Short Answer Questions

---

### 🟢 Beginner

**Problem 16.** Compare lists and variables and explain why lists are useful. Write 2 ways to create an empty list.

---

**Problem 17.** Write the output of the following code.

```python
animals = ["cat", "dog", "rabbit", "hamster"]
print(animals[1])
print(animals[-2])
print(len(animals))
```

---

**Problem 18.** Explain the difference between `append()` and `insert()`. Write the output of the following code.

```python
nums = [1, 2, 3]
nums.append(4)
nums.insert(0, 0)
print(nums)
```

---

### 🟡 Intermediate

**Problem 19.** Explain the difference between `remove()` and `pop()`. Write the output of the following code.

```python
fruits = ["apple", "banana", "orange", "grape", "strawberry"]
fruits.remove("orange")
last = fruits.pop()
second = fruits.pop(1)
print(fruits)
print(f"Removed: {last}, {second}")
```

---

**Problem 20.** Write the output of the following code and explain the meaning of `[start:end:step]` in slicing.

```python
nums = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
print(nums[2:8])
print(nums[1:7:2])
print(nums[7:2:-1])
```

---

### 🔴 Advanced

**Problem 21.** Explain the concept of list comprehension and verify if the following two codes produce identical results.

**Code A:**

```python
result = []
for i in range(1, 11):
    if i % 2 == 0:
        result.append(i * 10)
print(result)
```

**Code B:**

```python
result = [i * 10 for i in range(1, 11) if i % 2 == 0]
print(result)
```

---

## 💻 Hands-On Problems

---

### 🟢 Beginner

**Problem 22.** Write a program that meets the following requirements.

> For the fruit list `fruits = ["apple", "banana", "orange"]`, perform the following operations:
>
> 1) Add "grape" to the end of the list
> 2) Insert "strawberry" at index 1
> 3) Remove "banana"
> 4) Print the final list and item count

Output example:

```
Final List: ['apple', 'strawberry', 'orange', 'grape']
Item Count: 4 items
```

---

**Problem 23.** Write a program that meets the following requirements.

> For the score list `scores = [85, 92, 78, 96, 88]`, print the following information:
>
> - All scores (list as is)
> - First and last scores
> - Total and average
> - Highest and lowest scores

Output example:

```
All Scores: [85, 92, 78, 96, 88]
First: 85 points
Last: 88 points
Total: 439 points
Average: 87.8 points
Highest: 96 points
Lowest: 78 points
```

---

### 🟡 Intermediate

**Problem 24.** Write a program that meets the following requirements.

> Receive **5 students' names and scores** using `input()`, save them in lists, then sort by score in **descending order** and print a ranking table.

Output example:

```
=== Student Score Input ===
Student 1 Name: John
Student 1 Score: 85
Student 2 Name: Jane
Student 2 Score: 92
...

=== Score Ranking ===
1st. Jane: 92 points
2nd. Mike: 90 points
3rd. Sarah: 88 points
4th. John: 85 points
5th. David: 78 points
-------------------
Average: 86.6 points
```

---

**Problem 25.** Write a program that meets the following requirements.

> For the number list `numbers = [23, 45, 12, 67, 34, 89, 21, 56, 78, 43]`, find the maximum and minimum values **without using** `max()` and `min()` functions.

Output example:

```
Original List: [23, 45, 12, 67, 34, 89, 21, 56, 78, 43]
Maximum: 89
Minimum: 12
```

---

### 🔴 Advanced

**Problem 26.** Write a program that meets the following requirements.

> Use list comprehension to perform the following tasks:
>
> Price list: `prices = [15000, 32000, 8000, 45000, 22000, 5000, 38000, 12000]`
>
> 1) Create a new list with 10% discount on all prices
> 2) Filter products $20,000 or more
> 3) Create a 15% discounted list for products $20,000 or more
> 4) Print all results

Output example:

```
=== Price Analysis ===

Original Prices:
[15000, 32000, 8000, 45000, 22000, 5000, 38000, 12000]

1) 10% Discount:
[13500, 28800, 7200, 40500, 19800, 4500, 34200, 10800]

2) Products $20,000+:
[32000, 45000, 22000, 38000]

3) $20,000+ with 15% Discount:
[27200, 38250, 18700, 32300]

Total Savings: $20,550
```

---

---

# 🔑 Answer Key and Explanations

---

## 📝 Multiple Choice Answers

---

### 🟢 Beginner

**Problem 1. Answer: ② `fruits = [1, 2, 3]`**

Lists are created with **square brackets `[]`**. `()` creates tuples, `{}` creates sets or dictionaries.

---

**Problem 2. Answer: ① Red**

List indexing starts at **0**. `colors[0]` is the first item, which is `"Red"`.

---

**Problem 3. Answer: ② 50**

Negative indexes count from the end. `-1` is the **last item**, so `50` is printed.

---

**Problem 4. Answer: ② 4**

`append("grape")` adds an item to the end, making `["apple", "banana", "orange", "grape"]`. Length is 4.

---

**Problem 5. Answer: ③ `["apple", "strawberry", "orange"]`**

`fruits[1] = "strawberry"` changes the value at index 1 from `"banana"` to `"strawberry"`. Lists allow direct value modification by index.

---

**Problem 6. Answer: ② Removes an item from the list and returns its value**

`pop()` removes an item and **returns the removed value**. Without an index, it removes the last item; with an index, it removes that position.

---

**Problem 7. Answer: ② `[1, 1, 3, 4, 5]`**

`sort()` sorts the list in **ascending order**. Duplicate values (1) are preserved.

---

### 🟡 Intermediate

**Problem 8. Answer: ② `[1, 2, 3]`**

Slicing `[1:4]` means from index 1 to index **4 (not included)**. So indices 1, 2, 3 are included.

---

**Problem 9. Answer: ① `[10, 20, 30]`**

`[:3]` means from the start (index 0) to index **3 (not included)**, so indices 0, 1, 2.

---

**Problem 10. Answer: ① `["A", "B", "X", "C", "D"]`**

`insert(2, "X")` inserts `"X"` **at index 2**. Items at index 2 and beyond shift right.

---

**Problem 11. Answer: ② `["apple", "orange", "banana"]`**

`remove("banana")` removes only the **first occurrence** of `"banana"`. The second one remains.

---

**Problem 12. Answer: ③ `[1, 3, 5]`**

`[::2]` means from start to end with **step 2** (every other item). Indices 0, 2, 4 give values 1, 3, 5.

---

### 🔴 Advanced

**Problem 13. Answer: ② `[5, 4, 3, 2, 1]`**

`[::-1]` reverses the list with step -1, creating a **reverse order**.

---

**Problem 14. Answer: ③ `[1, 4, 9, 16, 25]`**

`x ** 2` is the square of `x`. `range(1, 6)` gives 1, 2, 3, 4, 5, so squares are `[1, 4, 9, 16, 25]`.

---

**Problem 15. Answer: ② `[3, 6, 9]`**

From `range(1, 11)`, filter numbers divisible by 3 (`x % 3 == 0`). Results are 3, 6, 9.

---

## 📝 Short Answer Key

---

### 🟢 Beginner

**Problem 16. Model Answer:**

A variable stores only one value, but a list stores **multiple values under one name** in order. For example, storing 100 students' scores requires 100 variables separately, but a list can manage all 100 scores with one name. Combined with loops, lists efficiently process large datasets.

**Two ways to create an empty list:**

```python
empty1 = []        # square brackets
empty2 = list()    # list() function
```

---

**Problem 17. Model Answer:**

```
dog
rabbit
4
```

- `animals[1]` → index 1 is the second item: `"dog"`
- `animals[-2]` → second from end: `"rabbit"`
- `len(animals)` → 4 items total

---

**Problem 18. Model Answer:**

- `append(value)`: Adds item to the **end** of the list.
- `insert(position, value)`: Inserts item at **specified index**, shifting others right.

**Output:**

```
[0, 1, 2, 3, 4]
```

`append(4)` → `[1, 2, 3, 4]`, then `insert(0, 0)` → `[0, 1, 2, 3, 4]`

---

### 🟡 Intermediate

**Problem 19. Model Answer:**

- `remove(value)`: Finds **value** and removes first match. Returns nothing.
- `pop(index)`: Removes by **index position** and **returns removed value**. No index removes last item.

**Output:**

```
['apple', 'grape']
Removed: strawberry, banana
```

1. `remove("orange")` → `["apple", "banana", "grape", "strawberry"]`
2. `pop()` → removes last `"strawberry"` → `["apple", "banana", "grape"]`
3. `pop(1)` → removes index 1 `"banana"` → `["apple", "grape"]`

---

**Problem 20. Model Answer:**

**`[start:end:step]` meaning:**

- **start**: Starting index (included)
- **end**: Ending index (not included)
- **step**: Step size (negative means reverse)

**Output:**

```
[2, 3, 4, 5, 6, 7]
[1, 3, 5]
[7, 6, 5, 4, 3]
```

- `nums[2:8]` → indices 2-7: `[2, 3, 4, 5, 6, 7]`
- `nums[1:7:2]` → indices 1-6, step 2: `[1, 3, 5]`
- `nums[7:2:-1]` → index 7 to 3 in reverse: `[7, 6, 5, 4, 3]`

---

### 🔴 Advanced

**Problem 21. Model Answer:**

**List comprehension:** Concise syntax combining loops and conditions into a single line for list creation.

Basic form: `[expression for variable in iterable if condition]`

**Both codes produce identical results:**

```
[20, 40, 60, 80, 100]
```

Code A uses traditional `for` and `if` with `append()`. Code B uses list comprehension to express the same logic in one line: filter even numbers from 1-10, then multiply by 10.

---

## 💻 Hands-On Solutions

---

### 🟢 Beginner

**Problem 22. Model Answer:**

```python
fruits = ["apple", "banana", "orange"]

# 1) Add "grape" to end
fruits.append("grape")

# 2) Insert "strawberry" at index 1
fruits.insert(1, "strawberry")

# 3) Remove "banana"
fruits.remove("banana")

# 4) Print results
print(f"Final List: {fruits}")
print(f"Item Count: {len(fruits)} items")
```

Key: `append()` → `insert()` → `remove()` sequence gives `["apple", "strawberry", "orange", "grape"]` with 4 items.

---

**Problem 23. Model Answer:**

```python
scores = [85, 92, 78, 96, 88]

print(f"All Scores: {scores}")
print(f"First: {scores[0]} points")
print(f"Last: {scores[-1]} points")

total = sum(scores)
average = total / len(scores)

print(f"Total: {total} points")
print(f"Average: {average} points")
print(f"Highest: {max(scores)} points")
print(f"Lowest: {min(scores)} points")
```

Key: Use `scores[0]` for first, `scores[-1]` for last. Built-in functions `sum()`, `max()`, `min()`, `len()` work well with lists.

---

### 🟡 Intermediate

**Problem 24. Model Answer:**

```python
names = []
scores = []

print("=== Student Score Input ===")
for i in range(5):
    name = input(f"Student {i+1} Name: ")
    score = int(input(f"Student {i+1} Score: "))
    names.append(name)
    scores.append(score)

# Pair scores with names for sorting
paired = []
for i in range(len(names)):
    paired.append((scores[i], names[i]))

paired.sort(reverse=True)

# Print ranking
print("\n=== Score Ranking ===")
for i in range(len(paired)):
    score, name = paired[i]
    print(f"{i+1}{'st' if i==0 else 'nd' if i==1 else 'rd' if i==2 else 'th'}. {name}: {score} points")

print("-" * 19)
average = sum(scores) / len(scores)
print(f"Average: {average:.1f} points")
```

Key: Pair names and scores in tuples, sort by first element (score), then unpack to display rankings.

---

### 🔴 Advanced

**Problem 25. Model Answer:**

```python
numbers = [23, 45, 12, 67, 34, 89, 21, 56, 78, 43]

# Find maximum
max_value = numbers[0]
for num in numbers:
    if num > max_value:
        max_value = num

# Find minimum
min_value = numbers[0]
for num in numbers:
    if num < min_value:
        min_value = num

print(f"Original List: {numbers}")
print(f"Maximum: {max_value}")
print(f"Minimum: {min_value}")
```

Key: Initialize with first element, iterate comparing to update max/min when a larger/smaller value is found.

---

### 🔴 Advanced (Problem 26)

**Problem 26. Model Answer:**

```python
prices = [15000, 32000, 8000, 45000, 22000, 5000, 38000, 12000]

# 1) 10% discount on all
discounted_10 = [int(p * 0.9) for p in prices]

# 2) Filter prices $20,000+
expensive = [p for p in prices if p >= 20000]

# 3) 15% discount for $20,000+ items
discounted_15 = [int(p * 0.85) for p in prices if p >= 20000]

# Total savings
total_saving = sum(expensive) - sum(discounted_15)

# Output
print("=== Price Analysis ===\n")
print(f"Original Prices:\n{prices}\n")
print(f"1) 10% Discount:\n{discounted_10}\n")
print(f"2) Products $20,000+:\n{expensive}\n")
print(f"3) $20,000+ with 15% Discount:\n{discounted_15}\n")
print(f"Total Savings: ${total_saving:,}")
```

Key: Transform-only comprehension `[int(p * 0.9) for p in prices]`, filter-only `[p for p in prices if p >= 20000]`, and combined transform+filter `[int(p * 0.85) for p in prices if p >= 20000]`.

---


Thank you for your attention.   
Cho Jeonghyun ([peterchokr@gmail.com](mailto:peterchokr@gmail.com)). Yeungnam University College

"Produced in collaboration with Claude and Gemini."
