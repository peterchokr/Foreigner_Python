# Chapter 5: Input and Output — Practice Problems

---

## 📝 Multiple Choice Questions

---

### 🟢 Beginner

**Problem 1.** What data type does the `input()` function return?

① int
② float
③ str
④ bool

---

**Problem 2.** When a user enters `25`, what is the data type of `age` in the following code?

```python
age = input("Age: ")
```

① int
② float
③ str
④ bool

---

**Problem 3.** What is the output of the following code?

```python
print("A", "B", "C")
```

① ABC
② A B C
③ A, B, C
④ (A, B, C)

---

**Problem 4.** To prevent a newline after `print()` output, which parameter should be used?

① `sep=""`
② `end=""`
③ `line=False`
④ `newline=""`

---

**Problem 5.** What is the output of the following code?

```python
print("2024", "12", "25", sep="-")
```

① 2024 12 25
② 2024-12-25
③ 2024/12/25
④ 20241225

---

**Problem 6.** Which is the correct code to receive user input as an integer?

① `age = input("Age: ")`
② `age = int("Age: ")`
③ `age = int(input("Age: "))`
④ `age = input(int("Age: "))`

---

**Problem 7.** What is the output of the following code?

```python
print("Hello", end="!")
print("World")
```

① Hello! World
② Hello!World
③ Hello!\nWorld
④ Hello! \n World

---

### 🟡 Intermediate

**Problem 8.** When a user enters `"10 20"`, what is the output of the following code?

```python
data = input("Input: ")
a, b = data.split()
print(a + b)
```

① 30
② 1020
③ 10 20
④ Error

---

**Problem 9.** What is the output of the following code?

```python
print("A", "B", sep="***", end="!\n")
print("C")
```

① A B!\nC
② A***B!\nC
③ A***B! (newline) C
④ A B C

---

**Problem 10.** When a user enters `"3 5"`, what is the output of the following code?

```python
a, b = input("Input: ").split()
result = int(a) * int(b)
print(result)
```

① 35
② 15
③ 8
④ Error

---

**Problem 11.** What is the output of the following code?

```python
name = "John Smith"
age = 25
print(f"|{name:>15}|{age:<10}|")
```

① `|John Smith    |25        |`
② `|    John Smith|25        |`
③ `|John Smith|25|`
④ Error

---

**Problem 12.** Which is the correct explanation of the `sep` parameter in `print()`?

① Specifies the starting character of output
② Specifies the separator between output values
③ Specifies the newline character after output
④ Specifies the number of output values

---

### 🔴 Advanced

**Problem 13.** What is the correct output of the following code?

```python
print("Loading", end="")
print(".", ".", ".", sep="", end="")
print("Done!")
```

① Loading . . . Done!
② Loading...Done!
③ Loading . . .Done!
④ Loading... Done!

---

**Problem 14.** When a user enters `"John 25 175.5"`, what is the output of the following code?

```python
data = input("Input: ").split()
name = data[0]
age = int(data[1])
height = float(data[2])
print(f"{name}({age} years old) - {height}cm")
```

① John(25 years old) - 175.5cm
② John 25 175.5
③ Error
④ John(25) - 175.5

---

**Problem 15.** What is the value of the `line` variable in the following code?

```python
line = "─" * 20
print(len(line))
```

① 20
② 40
③ 10
④ 1

---

## 📝 Short Answer Questions

---

### 🟢 Beginner

**Problem 16.** Explain how the `input()` function works and what additional processing is needed for numeric calculations.

---

**Problem 17.** Write the output of the following code.

```python
print("Apple", "Banana", "Orange", sep=" | ")
print("Price", end=": ")
print("$5")
```

---

**Problem 18.** Explain the default values and roles of the `sep` and `end` parameters in the `print()` function.

---

### 🟡 Intermediate

**Problem 19.** When a user enters `"John Smith 25"`, write the output of the following code and explain the operation process.

```python
data = input("Name Age: ").split()
name = data[0] + " " + data[1]
age = int(data[2])
print(f"{name} is {age} years old, and next year they will be {age + 1}.")
```

---

**Problem 20.** Explain the meanings of the alignment options `<`, `>`, and `^` in f-string, and write the output of the following code.

```python
word = "Hi"
print(f"[{word:<8}]")
print(f"[{word:>8}]")
print(f"[{word:^8}]")
```

---

### 🔴 Advanced

**Problem 21.** Write the exact output of the following code. (Pay attention to spaces and newlines)

```python
print("=" * 20)
print("Name", "Age", sep="\t")
print("-" * 20)
print("John Smith", end="\t")
print(25)
print("=" * 20)
```

---

## 💻 Hands-On Problems

---

### 🟢 Beginner

**Problem 22.** Write a program that meets the following requirements.

> Use the `sep` parameter to output a phone number in the following format.

Output:

```
555-123-4567
```

---

**Problem 23.** Write a program that meets the following requirements.

> Use the `end` parameter to print the following on one line.

Output:

```
[■■■■■■■■■■] 100%
```

---

**Problem 24.** Write a program that meets the following requirements.

> Using the variables `name = "John Smith"`, `age = 20`, and `major = "Computer Science"`, print in the following format. (Use string repetition operator and f-string)

Output:

```
====================
    Student Info Card
====================
Name: John Smith
Age: 20 years old
Major: Computer Science
====================
```

---

### 🟡 Intermediate

**Problem 25.** Write a program that meets the following requirements.

> Receive **product name, unit price, and quantity** from the user using `input()` and print a simple receipt in the following format.
> Use thousand separators (`,`) and alignment.

Output example (product: Laptop, unit price: 1500000, quantity: 2):

```
========================================
            Simple Receipt
========================================
Product:                      Laptop
Unit Price:               $1,500,000
Quantity:                        2 units
----------------------------------------
Total:                    $3,000,000
========================================
```

---

### 🔴 Advanced

**Problem 26.** Write a program that meets the following requirements.

> Receive **name, English, Math, and Science scores** on one line from the user (space-separated) using `split()` and print a grade report in the following format.
> Display the average to one decimal place.

Input example: `John Smith 85 92 78`

Output example:

```
╔══════════════════════════════════════╗
║           Grade Report               ║
╠══════════════════════════════════════╣
║  Name: John Smith                    ║
╠══════════════════════════════════════╣
║  Subject              Score          ║
║  ─────────────────────              ║
║  English               85 points      ║
║  Math                  92 points      ║
║  Science               78 points      ║
╠══════════════════════════════════════╣
║  Total                255 points      ║
║  Average             85.0 points      ║
╚══════════════════════════════════════╝
```

---

---

# 🔑 Answer Key and Explanations

---

## 📝 Multiple Choice Answers

---

### 🟢 Beginner

**Problem 1. Answer: ③ str**

The `input()` function always returns a string (str) type, regardless of what the user enters. Even if a user enters a number, it is stored as a string.

---

**Problem 2. Answer: ③ str**

The return value of `input()` is always a string. When a user enters `25`, the value `"25"` is stored in `age` as a string. To use it as an integer, you must convert it with `int(input("Age: "))`.

---

**Problem 3. Answer: ② A B C**

When multiple values are separated by commas in `print()`, they are separated by **one space** by default. This is because the default value of the `sep` parameter is `" "` (space).

---

**Problem 4. Answer: ② end=""**

The default value of the `end` parameter is `"\n"` (newline). Setting `end=""` prevents the newline and prints without line break. The `sep` parameter specifies the separator between values.

---

**Problem 5. Answer: ② 2024-12-25**

`sep="-"` connects the output values with `-`. Therefore, `"2024"`, `"12"`, and `"25"` are connected with hyphens to produce `2024-12-25`.

---

**Problem 6. Answer: ③ `int(input("Age: "))`**

Receive a string with `input()`, then convert it to an integer with `int()`. `input()` executes first on the inside, and `int()` converts its result.

---

**Problem 7. Answer: ② Hello!World**

The first `print("Hello", end="!")` outputs `Hello!` without a newline. The second `print("World")` continues immediately on the same line. Therefore, `Hello!World` is produced.

---

### 🟡 Intermediate

**Problem 8. Answer: ② 1020**

After `split()`, `a` and `b` remain as **strings**. String `"10"` + `"20"` = `"1020"` (string concatenation). To add numbers, you must convert with `int(a) + int(b)`.

---

**Problem 9. Answer: ③ A***B! (newline) C**

`sep="***"` puts `***` between A and B, and `end="!\n"` adds `!` and a newline at the end. Therefore, the first line shows `A***B!`, and the next line shows `C`.

---

**Problem 10. Answer: ② 15**

`split()` separates `"3"` and `"5"`, and `int()` converts each to integers 3 and 5. `3 * 5 = 15` is output.

---

**Problem 11. Answer: ② `|    John Smith|25        |`**

`{name:>15}` right-aligns within 15 spaces (padding with leading spaces), and `{age:<10}` left-aligns within 10 spaces (padding with trailing spaces).

---

**Problem 12. Answer: ② Specifies the separator between output values**

`sep` is short for separator. It specifies the character inserted between multiple values in `print()`. The default value is a space (`" "`).

---

### 🔴 Advanced

**Problem 13. Answer: ② Loading...Done!**

First `print("Loading", end="")` outputs `Loading` without a newline. Second `print(".", ".", ".", sep="", end="")` outputs three dots without spaces to produce `...` and no newline. Third `print("Done!")` continues the output. Final result: `Loading...Done!`

---

**Problem 14. Answer: ① John(25 years old) - 175.5cm**

`split()` separates into `["John", "25", "175.5"]`. Convert `data[1]` to `int()` and `data[2]` to `float()`. f-string formatting produces `John(25 years old) - 175.5cm`.

---

**Problem 15. Answer: ① 20**

`"─" * 20` repeats the `─` character 20 times. `len()` returns the **number of characters** in a string, so the result is 20. The `─` special character counts as one character.

---

## 📝 Short Answer Key

---

### 🟢 Beginner

**Problem 16. Model Answer:**

The `input()` function receives keyboard input from the user and **always returns it as a string (str) type**. You can put a prompt message in the parentheses to display guidance to the user.

For numeric calculations, type conversion is necessary:

- Integer calculation: `int(input("Number: "))` → convert str to int
- Float calculation: `float(input("Number: "))` → convert str to float

---

**Problem 17. Model Answer:**

```
Apple | Banana | Orange
Price: $5
```

First line: `sep=" | "` inserts `|` between the three fruits. Second line: `end=": "` places `: ` after "Price" instead of a newline, and the third `print()` continues on the same line.

---

**Problem 18. Model Answer:**

**`sep` (separator):**

- Default value: `" "` (one space)
- Role: Specifies the character inserted **between values** when using `print()` with multiple values.
- Example: `print("A", "B", sep="-")` → `A-B`

**`end` (ending character):**

- Default value: `"\n"` (newline)
- Role: Specifies the character appended **at the end** of `print()` output.
- Example: `print("Hello", end="!")` → `Hello!` (no newline)

---

### 🟡 Intermediate

**Problem 19. Model Answer:**

Execution result:

```
John Smith is 25 years old, and next year they will be 26.
```

**Operation process:**

1. `input()` receives the string `"John Smith 25"`.
2. `.split()` separates by spaces → `["John", "Smith", "25"]` list
3. Combine `data[0]` and `data[1]` with space → `"John Smith"` (assigned to name)
4. Convert `int(data[2])` → 25 (assigned to age)
5. f-string calculates `age + 1` → `25 + 1 = 26` for output

---

**Problem 20. Model Answer:**

**Alignment options:**

- `<` : Left alignment (default, padding on right)
- `>` : Right alignment (padding on left)
- `^` : Center alignment (padding on both sides)

**Execution Results:**

```
[Hi      ]
[      Hi]
[   Hi   ]
```

Within 8-character width, `"Hi"` (2 characters) is aligned left, right, and center respectively.

---

### 🔴 Advanced

**Problem 21. Model Answer:**

```
====================
Name	Age
--------------------
John Smith	25
====================
```

**Step-by-step explanation:**

1. `"=" * 20` → `====================` printed then newline
2. `"Name"`, `"Age"` printed with `sep="\t"` (tab) separator then newline
3. `"-" * 20` → `--------------------` printed then newline
4. `"John Smith"` printed, then `end="\t"` replaces newline with tab
5. `25` printed with default newline
6. `"=" * 20` → `====================` printed

---

## 💻 Hands-On Solutions

---

### 🟢 Beginner

**Problem 22. Model Answer:**

```python
print("555", "123", "4567", sep="-")
```

Key point: `sep="-"` automatically inserts a hyphen between the three values.

---

**Problem 23. Model Answer:**

```python
print("[", end="")
print("■" * 10, end="")
print("] 100%")
```

Key point: Using `end=""` removes newlines and connects three `print()` statements into one line.

---

**Problem 24. Model Answer:**

```python
name = "John Smith"
age = 20
major = "Computer Science"

line = "=" * 20
print(line)
print("    Student Info Card")
print(line)
print(f"Name: {name}")
print(f"Age: {age} years old")
print(f"Major: {major}")
print(line)
```

Key point: Use `"=" * 20` to create divider lines and f-strings to display variables.

---

### 🟡 Intermediate

**Problem 25. Model Answer:**

```python
# Input
product = input("Product: ")
unit_price = int(input("Unit Price: "))
quantity = int(input("Quantity: "))

# Calculate
total = unit_price * quantity

# Output
w = 40
print("=" * w)
print(f"{'Simple Receipt':^{w}}")
print("=" * w)
print(f"Product: {product:>{w - 10}}")
print(f"Unit Price: ${unit_price:>{w - 12},}")
print(f"Quantity: {quantity:>{w - 10}} units")
print("-" * w)
print(f"Total: ${total:>{w - 8},}")
print("=" * w)
```

Key points:

- `{:>number,}` combines right alignment and thousand separators.
- `{:^number}` centers the title.
- `"=" * number` creates divider lines.

---

### 🔴 Advanced

**Problem 26. Model Answer:**

```python
# Receive input and separate
data = input("Name English Math Science: ").split()
name = data[0] + " " + data[1]
english = int(data[2])
math = int(data[3])
science = int(data[4])

# Calculate
total = english + math + science
average = total / 3

# Print grade report
w = 38
print("╔" + "═" * w + "╗")
print("║" + "Grade Report".center(w) + "║")
print("╠" + "═" * w + "╣")
print(f"║  Name: {name}".ljust(w + 1) + "║")
print("╠" + "═" * w + "╣")
print(f"║  {'Subject':<15}{'Score':>10}".ljust(w + 1) + "║")
print(f"║  {'─' * 20}".ljust(w + 1) + "║")
print(f"║  {'English':<15}{english:>10} points".ljust(w + 1) + "║")
print(f"║  {'Math':<15}{math:>10} points".ljust(w + 1) + "║")
print(f"║  {'Science':<15}{science:>10} points".ljust(w + 1) + "║")
print("╠" + "═" * w + "╣")
print(f"║  {'Total':<15}{total:>10} points".ljust(w + 1) + "║")
print(f"║  {'Average':<15}{average:>10.1f} points".ljust(w + 1) + "║")
print("╚" + "═" * w + "╝")
```

Key points:

- Use `split()` to separate one-line input into multiple variables.
- Use `ljust()` to align box widths and f-string options to align internal items.
- Use `:.1f` to display average to one decimal place.
- Use box characters (`╔═╗║╠╣╚╝`) to create borders.

---


Thank you for your attention.   
Cho Jeonghyun ([peterchokr@gmail.com](mailto:peterchokr@gmail.com)). Yeungnam University College

"Produced in collaboration with Claude and Gemini."
