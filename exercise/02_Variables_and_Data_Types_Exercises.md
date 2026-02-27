# Chapter 2: Variables and Data Types — Practice Problems

---

## 📝 Multiple Choice Questions

---

### 🟢 Beginner

**Problem 1.** Select **all** correct variable names in Python.

① `my_score`
② `2nd_name`
③ `_count`
④ `total-price`

---

**Problem 2.** What is the data type of the variable `name` in the following code?

```python
name = "John Smith"
```

① int
② float
③ str
④ bool

---

**Problem 3.** What is the correct meaning of the `=` symbol in Python?

① The left and right sides are equal
② Store the right value in the left variable
③ Store the left value in the right variable
④ Compare two values

---

**Problem 4.** Which of the following is a correct **boolean (bool)** value?

① true
② FALSE
③ True
④ "True"

---

**Problem 5.** Which function is used to check the data type of a variable?

① `print()`
② `type()`
③ `int()`
④ `str()`

---

**Problem 6.** What is the output of the following code?

```python
x = 10
x = 20
print(x)
```

① 10
② 20
③ 30
④ Error

---

**Problem 7.** Which of the following **cannot** be used as a variable name?

① `student_name`
② `_age`
③ `while`
④ `score1`

---

### 🟡 Intermediate

**Problem 8.** What is the output of the following code?

```python
a = "100"
b = 50
result = int(a) + b
print(result)
```

① "10050"
② 150
③ "150"
④ Error

---

**Problem 9.** What type is printed in the following code?

```python
x = 10
y = 4
result = x / y
print(type(result))
```

① `<class 'int'>`
② `<class 'float'>`
③ `<class 'str'>`
④ `<class 'bool'>`

---

**Problem 10.** What is the output of the following code?

```python
height = 175.8
height_int = int(height)
print(height_int)
```

① 176
② 175.8
③ 175
④ Error

---

**Problem 11.** Which of the following causes an error?

① `x = int("42")`
② `y = float("3.14")`
③ `z = int("hello")`
④ `w = str(100)`

---

**Problem 12.** What is the output of the following code?

```python
a, b, c = 10, 20, 30
print(b)
```

① 10
② 20
③ 30
④ (10, 20, 30)

---

### 🔴 Advanced

**Problem 13.** What is the output of the following code?

```python
x = 23
y = 7
print(x // y, x % y)
```

① 3.28 2
② 3 2
③ 3 3
④ 3.0 2.0

---

**Problem 14.** What is the final output when executing the following code in order?

```python
a = "10"
b = "20"
c = a + b
d = int(a) + int(b)
print(c, d)
```

① 30 30
② "1020" 30
③ 1020 30
④ Error

---

**Problem 15.** What are the type and value of `result` in the following code?

```python
x = 5
y = 2.0
result = x + y
```

① int, 7
② float, 7.0
③ str, "7.0"
④ int, 7.0

---

## 📝 Short Answer Questions

---

### 🟢 Beginner

**Problem 16.** Write 3 rules that must be followed when creating variable names in Python.

---

**Problem 17.** Write the output of the following code.

```python
x = 5
y = 3
print(x + y)
print(x * y)
```

---

**Problem 18.** Explain what data type the value received from the `input()` function has, and what conversion is needed for numeric calculations.

---

### 🟡 Intermediate

**Problem 19.** Explain why an error occurs in the following code, and write the corrected code.

```python
age = input("Enter your age: ")
next_year_age = age + 1
print("Next year age:", next_year_age)
```

---

**Problem 20.** Explain the differences between the three operators `/`, `//`, and `%`, and write the calculation results using `25` and `4` for each.

---

### 🔴 Advanced

**Problem 21.** Write the output of the following code, and explain step by step the type conversion process occurring in each line.

```python
a = "3"
b = 4
c = float(a) + b
d = str(int(c)) + a
print(c, type(c).__name__)
print(d, type(d).__name__)
```

---

## 💻 Hands-On Problems

---

### 🟢 Beginner

**Problem 22.** Write a program that meets the following requirements.

> Store your name, age, and height (in cm) in separate variables, and print them in the following format:

```
Name: John Smith
Age: 20 years old
Height: 175.5 cm
```

---

**Problem 23.** Write a program that meets the following requirements.

> Given variables `price = 15000` and `quantity = 3`, calculate the total amount and print it as shown below:

```
Unit Price: 15000 won
Quantity: 3 units
Total Amount: 45000 won
```

---

**Problem 24.** Write a program that meets the following requirements.

> Check the data type of the following variables using the `type()` function and print them.

```python
a = 42
b = 3.14
c = "Python"
d = True
```

Output example:

```
42 → int
3.14 → float
Python → str
True → bool
```

---

### 🟡 Intermediate

**Problem 25.** Write a program that meets the following requirements.

> Use `input()` to receive English, Math, and Science scores from the user, then calculate the total score and average.
> Print the average to one decimal place.

Output example:

```
=== Grade Calculator ===
English Score: 85
Math Score: 90
Science Score: 78
-----------------
Total Score: 253 points
Average: 84.3 points
```

---

### 🔴 Advanced

**Problem 26.** Write a program that meets the following requirements.

> Receive time in **seconds** from the user and convert it to **hours, minutes, and seconds** for output.
> (Hint: Use integer division `//` and modulo operator `%`.)

Output example:

```
Enter seconds: 3725
3725 seconds = 1 hour 2 minutes 5 seconds
```

---

---

# 🔑 Answer Key and Explanations

---

## 📝 Multiple Choice Answers

---

### 🟢 Beginner

**Problem 1. Answer: ①, ③**

`my_score` consists of letters and underscores, so it is correct. `_count` is also correct because starting with an underscore is allowed. ②`2nd_name` cannot be used because it starts with a digit, and ④`total-price` cannot be used because it contains a hyphen (`-`).

---

**Problem 2. Answer: ③ str**

A value enclosed in double quotes (`""`) is a string (str) type. `"John Smith"` is text data, so it is stored as str type.

---

**Problem 3. Answer: ②**

In Python, `=` is an assignment operator meaning "store the right value in the left variable." This is different from the equals sign (`=`) in mathematics. Comparison uses `==`.

---

**Problem 4. Answer: ③ True**

Python's boolean values must start with a capital letter: `True` and `False`. ①`true` is lowercase (error), ②`FALSE` is all caps (not a boolean). ④`"True"` is enclosed in quotes, so it is a string (str).

---

**Problem 5. Answer: ② type()**

The `type()` function returns the type of the data stored in a variable. `print()` prints values, while `int()` and `str()` are type conversion functions.

---

**Problem 6. Answer: ② 20**

Variables can be changed at any time. After storing 10 in `x = 10`, the value is changed to 20 with `x = 20`, so `print(x)` outputs 20.

---

**Problem 7. Answer: ③ while**

`while` is a Python keyword used in loops. Keywords cannot be used as variable names. The others are all valid variable names.

---

### 🟡 Intermediate

**Problem 8. Answer: ② 150**

`a` is the string `"100"`, but `int(a)` converts it to the integer 100. Therefore, `100 + 50 = 150`. If you try `a + b` without the `int()` conversion, adding a string and integer causes a `TypeError`.

---

**Problem 9. Answer: ② `<class 'float'>`**

In Python, the result of the `/` division operator is always float, even if both operands are integers. `10 / 4 = 2.5` gives a float result. Use the `//` operator if you need an integer result.

---

**Problem 10. Answer: ③ 175**

When converting a float to an integer using `int()`, the **fractional part is truncated** (not rounded). Therefore, 175.8 becomes 175. This is an important characteristic to remember.

---

**Problem 11. Answer: ③ `z = int("hello")`**

The `int()` function can only convert numeric strings to integers. `"hello"` is not numeric, so a `ValueError` is raised. The others all convert normally.

---

**Problem 12. Answer: ② 20**

`a, b, c = 10, 20, 30` declares multiple variables on one line. Left variables and right values correspond in order, so `a=10`, `b=20`, `c=30`. Therefore, `print(b)` outputs 20.

---

### 🔴 Advanced

**Problem 13. Answer: ② 3 2**

`23 // 7 = 3` is integer division (quotient), and `23 % 7 = 2` is the modulo operation. Dividing 23 by 7 gives quotient 3 and remainder 2 (7 × 3 = 21, 23 − 21 = 2). Both `//` and `%` return integers when operands are integers.

---

**Problem 14. Answer: ③ 1020 30**

In `c = a + b`, both `a` and `b` are strings, so string concatenation occurs: `c = "1020"`. In `d = int(a) + int(b)`, each is converted to an integer before addition: `d = 30`. `print(c, d)` outputs `1020 30`. (Quotes are not displayed in the output.)

---

**Problem 15. Answer: ② float, 7.0**

In Python, operating on an integer and a float results in a float type. This is called **implicit type conversion**. `5 + 2.0 = 7.0` with float type.

---

## 📝 Short Answer Key

---

### 🟢 Beginner

**Problem 16. Model Answer:**

1. Only letters (a-z, A-Z), digits (0-9), and underscores (`_`) can be used.
2. Variable names cannot start with a digit.
3. Python keywords (`if`, `for`, `while`, `True`, etc.) cannot be used.

Additional tips: Case-sensitive (`name` and `Name` are different variables), use meaningful names, and snake_case is recommended.

---

**Problem 17. Model Answer:**

```
8
15
```

`x + y = 5 + 3 = 8` is printed on the first line, and `x * y = 5 × 3 = 15` is printed on the second line.

---

**Problem 18. Model Answer:**

The `input()` function always returns a **string (str)** type. Even if the user enters a number, it is stored as a string. To perform numeric calculations, use the `int()` function (integer conversion) or `float()` function (float conversion) to convert the type.

Example: `age = int(input("Enter age: "))` → Convert the received string to integer

---

### 🟡 Intermediate

**Problem 19. Model Answer:**

**Error cause:** The `input()` function always returns a string, so `age` is string (str) type. You cannot directly add a string and integer (1) with the `+` operator, causing a `TypeError`.

**Corrected code:**

```python
age = int(input("Enter your age: "))
next_year_age = age + 1
print("Next year age:", next_year_age)
```

Converting the value received from `input()` using `int()` makes it an integer type, allowing normal addition.

---

**Problem 20. Model Answer:**

| Operator | Meaning                                  | Result with `25` and `4` |
| -------- | ---------------------------------------- | ---------------------------- |
| `/`    | Regular division (always returns float)  | `25 / 4 = 6.25`            |
| `//`   | Integer division (returns quotient only) | `25 // 4 = 6`              |
| `%`    | Modulo operation                         | `25 % 4 = 1`               |

Verification: 25 = 4 × **6** + **1** (quotient = 6, remainder = 1)

---

### 🔴 Advanced

**Problem 21. Model Answer:**

Output:

```
7.0 float
73 str
```

**Step-by-step explanation:**

1. `a = "3"` → Store string "3" (str)
2. `b = 4` → Store integer 4 (int)
3. `float(a)` → Convert string "3" to float 3.0 (str → float)
4. `3.0 + 4` → float and int operation result is float → `c = 7.0` (int 4 is implicitly converted to float 4.0)
5. `int(c)` → Convert float 7.0 to integer 7 (float → int)
6. `str(7)` → Convert integer 7 to string "7" (int → str)
7. `"7" + a` → String concatenation: `"7" + "3" = "73"` → `d = "73"` (str)

---

## 💻 Hands-On Solutions

---

### 🟢 Beginner

**Problem 22. Model Answer:**

```python
# Store personal information in variables
name = "John Smith"
age = 20
height = 175.5

# Print output
print(f"Name: {name}")
print(f"Age: {age} years old")
print(f"Height: {height} cm")
```

Key point: Use string (str) for name, integer (int) for age, and float for height. Using f-strings makes it easy to print variables.

---

**Problem 23. Model Answer:**

```python
# Declare variables
price = 15000
quantity = 3

# Calculate total amount
total = price * quantity

# Print output
print(f"Unit Price: {price} won")
print(f"Quantity: {quantity} units")
print(f"Total Amount: {total} won")
```

Key point: Use the multiplication operator (`*`) to calculate the total amount and store the result in a separate variable `total`.

---

**Problem 24. Model Answer:**

```python
a = 42
b = 3.14
c = "Python"
d = True

print(f"{a} → {type(a).__name__}")
print(f"{b} → {type(b).__name__}")
print(f"{c} → {type(c).__name__}")
print(f"{d} → {type(d).__name__}")
```

Key point: Using `type(variable).__name__` prints `int` instead of `<class 'int'>`. This practice exercises identifying the four basic data types (int, float, str, bool).

---

### 🟡 Intermediate

**Problem 25. Model Answer:**

```python
print("=== Grade Calculator ===")

# Get scores from user (string → integer conversion)
english = int(input("English Score: "))
math = int(input("Math Score: "))
science = int(input("Science Score: "))

# Calculate
total = english + math + science
average = total / 3

# Print results
print("-----------------")
print(f"Total Score: {total} points")
print(f"Average: {average:.1f} points")
```

Key points:

- The result from `input()` must be converted with `int()` for numeric calculations.
- The `/` operator automatically returns a float type for fractional averages.
- `:.1f` is a format specifier that displays one decimal place.

---

### 🔴 Advanced

**Problem 26. Model Answer:**

```python
# Get input in seconds
total_seconds = int(input("Enter seconds: "))

# Calculate hours, minutes, and seconds
hours = total_seconds // 3600        # 1 hour = 3600 seconds
remaining = total_seconds % 3600     # Remaining seconds after hours
minutes = remaining // 60            # 1 minute = 60 seconds
seconds = remaining % 60             # Remaining seconds after minutes

# Print result
print(f"{total_seconds} seconds = {hours} hour {'hours' if hours != 1 else ''} {minutes} minute{'s' if minutes != 1 else ''} {seconds} second{'s' if seconds != 1 else ''}")
```

**Simpler version (without plural handling):**

```python
# Get input in seconds
total_seconds = int(input("Enter seconds: "))

# Calculate hours, minutes, and seconds
hours = total_seconds // 3600
remaining = total_seconds % 3600
minutes = remaining // 60
seconds = remaining % 60

# Print result
print(f"{total_seconds} seconds = {hours} hours {minutes} minutes {seconds} seconds")
```

Key points:

- Use `//` (integer division) to find the quotient, and `%` (modulo) to find the remainder.
- 3725 seconds → 3725 // 3600 = **1 hour**, 3725 % 3600 = 125 seconds remaining → 125 // 60 = **2 minutes**, 125 % 60 = **5 seconds**
- Combining `//` and `%` effectively solves unit conversion problems.

---


Thank you for your attention.
Cho Jeonghyun ([peterchokr@gmail.com](mailto:peterchokr@gmail.com)). Yeungnam University College

"Produced in collaboration with Claude and Gemini."
