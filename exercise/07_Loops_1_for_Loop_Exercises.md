# Chapter 7: Loops 1 (for Loop) — Practice Problems

---

## 📝 Multiple Choice Questions

---

### 🟢 Beginner

**Problem 1.** How many times will the following code print?

```python
for i in range(5):
    print("Hello")
```

① 4 times  
② 5 times  
③ 6 times  
④ Infinite loop  

---

**Problem 2.** What numbers does `range(3)` generate?

① 1, 2, 3  
② 0, 1, 2  
③ 0, 1, 2, 3  
④ 1, 2  

---

**Problem 3.** What is the output of the following code?

```python
for i in range(1, 4):
    print(i, end=" ")
```

① 1 2 3 4  
② 0 1 2 3  
③ 1 2 3  
④ 1 2 3 4 5  

---

**Problem 4.** What is the output of the following code?

```python
for char in "Hi":
    print(char)
```

① Hi  
② H i  
③ H (newline) i  
④ Error  

---

**Problem 5.** What is the output of the following code?

```python
total = 0
for i in range(3):
    total += 1
print(total)
```

① 0  
② 1  
③ 3  
④ 6  

---

**Problem 6.** Which is the correct code to print 1 through 5?

① `for i in range(5):`  
② `for i in range(1, 5):`  
③ `for i in range(1, 6):`  
④ `for i in range(0, 5):`  

---

**Problem 7.** What is the output of the following code?

```python
print("★" * 3)
```

① ★ ★ ★  
② ★★★  
③ ★3  
④ Error  

---

### 🟡 Intermediate

**Problem 8.** What is the output of the following code?

```python
for i in range(5, 0, -1):
    print(i, end=" ")
```

① 5 4 3 2 1  
② 5 4 3 2 1 0  
③ 0 1 2 3 4 5  
④ 1 2 3 4 5  

---

**Problem 9.** What is the value of `total`?

```python
total = 0
for i in range(1, 11):
    total += i
```

① 10  
② 45  
③ 55  
④ 100  

---

**Problem 10.** How many lines does the following code print?

```python
for i in range(1, 4):
    for j in range(1, 3):
        print("*")
```

① 3 lines  
② 4 lines  
③ 6 lines  
④ 9 lines  

---

**Problem 11.** What is the output of the following code?

```python
for i in range(0, 10, 3):
    print(i, end=" ")
```

① 0 3 6 9  
② 0 3 6  
③ 3 6 9  
④ 0 1 2 3  

---

**Problem 12.** What is the output of the following code?

```python
text = "Python"
count = 0
for char in text:
    if char in "aeiou":
        count += 1
print(count)
```

① 1  
② 2  
③ 3  
④ 0  

---

### 🔴 Advanced

**Problem 13.** What is the output of the following code?

```python
for i in range(1, 5):
    print("*" * i)
```

① 4 lines, last line with 4 stars  
② 5 lines, last line with 5 stars  
③ 4 lines, last line with 5 stars  
④ 3 lines, last line with 3 stars  

---

**Problem 14.** What is the output of the following code?

```python
result = 1
for i in range(1, 5):
    result *= i
print(result)
```

① 10  
② 24  
③ 120  
④ 5  

---

**Problem 15.** What is the final value of `highest`?

```python
scores = [78, 92, 65, 88, 95, 72]
highest = 0
for score in scores:
    if score > highest:
        highest = score
print(highest)
```

① 78  
② 92  
③ 95  
④ 72  

---

## 📝 Short Answer Questions

---

### 🟢 Beginner

**Problem 16.** Write the three ways to use the `range()` function and explain the meaning of each.

---

**Problem 17.** Write the output of the following code.

```python
for i in range(1, 6):
    print(i * 10, end=" ")
```

---

**Problem 18.** Explain how to iterate through a string with a for loop, and write code to print each character of `"HELLO"` on separate lines.

---

### 🟡 Intermediate

**Problem 19.** Write the output of the following code and explain how nested for loops work.

```python
for i in range(1, 4):
    for j in range(1, 4):
        print(f"{i}×{j}={i*j}", end=" ")
    print()
```

---

**Problem 20.** Write the output of the following code and explain how the accumulator variables change.

```python
total = 0
count = 0
for i in range(1, 11):
    if i % 3 == 0:
        total += i
        count += 1
print(f"Sum: {total}, Count: {count}")
```

---

### 🔴 Advanced

**Problem 21.** Write the output of the following code and explain the number of spaces and stars in each line.

```python
n = 4
for i in range(1, n + 1):
    print(" " * (n - i) + "★" * (2 * i - 1))
```

---

## 💻 Hands-On Problems

---

### 🟢 Beginner

**Problem 22.** Write a program that meets the following requirements.

> Use a for loop and `range()` to calculate the sum of numbers 1 through 10 and print the result.

Output:

```
Sum of 1 to 10: 55
```

---

**Problem 23.** Write a program that meets the following requirements.

> Use a for loop to print the multiplication table for 5.

Output:

```
[ 5 Times Table ]
5 × 1 = 5
5 × 2 = 10
5 × 3 = 15
5 × 4 = 20
5 × 5 = 25
5 × 6 = 30
5 × 7 = 35
5 × 8 = 40
5 × 9 = 45
```

---

**Problem 24.** Write a program that meets the following requirements.

> Use a for loop to count the vowels (a, e, i, o, u) in the string `"Programming"` and print the result.

Output:

```
Number of vowels in "Programming": 3
```

---

### 🟡 Intermediate

**Problem 25.** Write a program that meets the following requirements.

> Receive the number of students using `input()`, use a for loop to input each student's score, and print **total score, average, highest score, and lowest score**.

Output example (Number of students: 3, Scores: 85, 92, 78):

```
=== Score Analysis ===
Student 1: 85
Student 2: 92
Student 3: 78
-----------------
Total Score: 255 points
Average: 85.0 points
Highest Score: 92 points
Lowest Score: 78 points
```

---

### 🔴 Advanced

**Problem 26.** Write a program that meets the following requirements.

> Receive the height (integer) using `input()` and print all three patterns below. (Use nested for loops or string operations)

Output example (Height: 5):

```
Pattern 1: Right Triangle
*
**
***
****
*****

Pattern 2: Inverted Right Triangle
*****
****
***
**
*

Pattern 3: Pyramid
    *
   ***
  *****
 *******
*********
```

---
---

# 🔑 Answer Key and Explanations

---

## 📝 Multiple Choice Answers

---

### 🟢 Beginner

**Problem 1. Answer: ② 5 times**

`range(5)` generates 0, 1, 2, 3, 4, which repeats 5 times.

---

**Problem 2. Answer: ② 0, 1, 2**

`range(3)` starts from 0 and goes up to (but not including) 3, so it generates 0, 1, 2. The end value is not included.

---

**Problem 3. Answer: ③ 1 2 3**

`range(1, 4)` generates 1, 2, 3 (up to but not including 4). With `end=" "`, they print on one line separated by spaces.

---

**Problem 4. Answer: ③ H (newline) i**

When iterating through a string with a for loop, each character is assigned to the variable one at a time. Since the default `end` is `"\n"`, each character prints on a separate line.

---

**Problem 5. Answer: ③ 3**

`range(3)` repeats 3 times (0, 1, 2). Each iteration adds 1 to `total`, so `0 + 1 + 1 + 1 = 3`.

---

**Problem 6. Answer: ③ `for i in range(1, 6):`**

`range(1, 6)` generates 1, 2, 3, 4, 5. `range(1, 5)` only goes to 4, and `range(5)` goes from 0 to 4.

---

**Problem 7. Answer: ② ★★★**

The `*` operator repeats strings without separators. `"★" * 3` produces `"★★★"`.

---

### 🟡 Intermediate

**Problem 8. Answer: ① 5 4 3 2 1**

`range(5, 0, -1)` counts from 5 down to 1 (0 is not included). Each step decreases by 1.

---

**Problem 9. Answer: ③ 55**

`range(1, 11)` generates 1 through 10. The sum is `1+2+3+4+5+6+7+8+9+10 = 55`.

---

**Problem 10. Answer: ③ 6 lines**

Outer loop 3 times (i=1,2,3) × Inner loop 2 times (j=1,2) = 6 total `print("*")` calls. Each prints one line, so 6 lines total.

---

**Problem 11. Answer: ① 0 3 6 9**

`range(0, 10, 3)` starts from 0 and increments by 3 until 10: 0, 3, 6, 9.

---

**Problem 12. Answer: ① 1**

In `"Python"`, only the lowercase vowel `o` matches the vowels in `"aeiou"`. `P`, `y`, `t`, `h`, `n` are not vowels, and `P` is uppercase.

---

### 🔴 Advanced

**Problem 13. Answer: ① 4 lines, last line with 4 stars**

`range(1, 5)` generates 1, 2, 3, 4, so 4 lines print. When `i=4`, `"*" * 4` prints 4 stars.

```
*
**
***
****
```

---

**Problem 14. Answer: ② 24**

Multiply 1 through 4: `1 × 1 = 1` → `1 × 2 = 2` → `2 × 3 = 6` → `6 × 4 = 24`. This is 4! (factorial).

---

**Problem 15. Answer: ③ 95**

Iterate through the list, updating `highest` whenever a larger value is found: 78 → 92 → 92 → 92 → 95 → 95. Final `highest = 95`.

---

## 📝 Short Answer Key

---

### 🟢 Beginner

**Problem 16. Model Answer:**

| Form | Meaning | Example |
|------|---------|---------|
| `range(end)` | 0 to (end-1) | `range(5)` → 0,1,2,3,4 |
| `range(start, end)` | start to (end-1) | `range(1, 6)` → 1,2,3,4,5 |
| `range(start, end, step)` | start to (end-1) by step | `range(0, 10, 2)` → 0,2,4,6,8 |

In all forms, **the end value is not included**.

---

**Problem 17. Model Answer:**

```
10 20 30 40 50
```

`range(1, 6)` generates 1~5, and each is multiplied by 10: 10, 20, 30, 40, 50.

---

**Problem 18. Model Answer:**

When a string is placed in a for loop, each character is assigned to the variable one at a time.

```python
text = "HELLO"
for char in text:
    print(char)
```

Output:
```
H
E
L
L
O
```

---

### 🟡 Intermediate

**Problem 19. Model Answer:**

Output:

```
1×1=1 1×2=2 1×3=3 
2×1=2 2×2=4 2×3=6 
3×1=3 3×2=6 3×3=9 
```

**How nested loops work:** The outer loop (i) runs once at a time. For each i value, the inner loop (j) runs completely from 1 to 3, printing one line. Then i increments, and the inner loop runs again. This creates a 3×3 grid of multiplication results.

---

**Problem 20. Model Answer:**

Output:

```
Sum: 18, Count: 3
```

**Accumulator process:** Multiples of 3 from 1-10 are 3, 6, 9.
- i=3: `total = 0+3 = 3`, `count = 1`
- i=6: `total = 3+6 = 9`, `count = 2`
- i=9: `total = 9+9 = 18`, `count = 3`

The condition `i % 3 == 0` filters for multiples of 3 and accumulates them.

---

### 🔴 Advanced

**Problem 21. Model Answer:**

Output:

```
   *
  ***
 *****
*******
```

**Line analysis (n=4):**

| i | Spaces (n-i) | Stars (2i-1) |
|---|------------|----------|
| 1 | 3 | 1 |
| 2 | 2 | 3 |
| 3 | 1 | 5 |
| 4 | 0 | 7 |

Spaces are added to center the pyramid. Spaces: `(n-i)`, Stars: `(2i-1)`. Stars increase by 2 each line.

---

## 💻 Hands-On Solutions

---

### 🟢 Beginner

**Problem 22. Model Answer:**

```python
total = 0
for i in range(1, 11):
    total += i
print(f"Sum of 1 to 10: {total}")
```

Key point: Use `range(1, 11)` to generate 1~10, and accumulate with `total += i`.

---

**Problem 23. Model Answer:**

```python
times = 5
print(f"[ {times} Times Table ]")
for i in range(1, 10):
    print(f"{times} × {i} = {times * i}")
```

Key point: Use `range(1, 10)` to generate 1~9 and calculate the product for the multiplication table.

---

**Problem 24. Model Answer:**

```python
text = "Programming"
count = 0
for char in text:
    if char in "aeiou":
        count += 1
print(f'Number of vowels in "{text}": {count}')
```

Key point: Iterate through the string and use the `in` operator to check if each character is a vowel. The vowels in `"Programming"` are `o`, `a`, `i` → 3 total.

---

### 🟡 Intermediate

**Problem 25. Model Answer:**

```python
num = int(input("Number of students: "))

total = 0
highest = 0
lowest = 100

print("\n=== Score Analysis ===")
for i in range(1, num + 1):
    score = int(input(f"Student {i}: "))
    total += score
    if score > highest:
        highest = score
    if score < lowest:
        lowest = score

average = total / num

print("-" * 24)
print(f"Total Score: {total} points")
print(f"Average: {average:.1f} points")
print(f"Highest Score: {highest} points")
print(f"Lowest Score: {lowest} points")
```

Key points:
- Initialize `highest` to 0 and `lowest` to 100 for comparison.
- Use `if` inside the loop to update highest/lowest scores each iteration.
- Calculate average with `total / num` and format to one decimal place with `:.1f`.

---

### 🔴 Advanced

**Problem 26. Model Answer:**

```python
height = int(input("Height: "))

# Pattern 1: Right Triangle
print("\nPattern 1: Right Triangle")
for i in range(1, height + 1):
    print("*" * i)

# Pattern 2: Inverted Right Triangle
print("\nPattern 2: Inverted Right Triangle")
for i in range(height, 0, -1):
    print("*" * i)

# Pattern 3: Pyramid
print("\nPattern 3: Pyramid")
for i in range(1, height + 1):
    spaces = " " * (height - i)
    stars = "*" * (2 * i - 1)
    print(spaces + stars)
```

Key points:
- Pattern 1: Use `range(1, height+1)` with increasing stars.
- Pattern 2: Use `range(height, 0, -1)` for reverse order with decreasing stars.
- Pattern 3: Each line has `(height-i)` spaces and `(2i-1)` stars to create pyramid shape.

---

Professor Cho Jeonghyun (peterchokr@gmail.com)  
Yeungnam University College.
