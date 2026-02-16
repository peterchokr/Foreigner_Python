# Chapter 6: Conditional Statements — Practice Problems

---

## 📝 Multiple Choice Questions

---

### 🟢 Beginner

**Problem 1.** What is the output of the following code?

```python
x = 10
if x > 5:
    print("A")
print("B")
```

① A  
② B  
③ A (newline) B  
④ No output  

---

**Problem 2.** How does Python distinguish conditional statement blocks?

① Braces `{}`  
② Indentation (4 spaces)  
③ Semicolons `;`  
④ Parentheses `()`  

---

**Problem 3.** What is the output of the following code?

```python
age = 15
if age >= 18:
    print("Adult")
else:
    print("Minor")
```

① Adult  
② Minor  
③ Adult Minor  
④ Error  

---

**Problem 4.** What does `elif` stand for?

① else finally  
② else if  
③ element if  
④ equal if  

---

**Problem 5.** What is the output of the following code?

```python
score = 85
if score >= 90:
    print("A")
elif score >= 80:
    print("B")
elif score >= 70:
    print("C")
```

① A  
② B  
③ C  
④ B C  

---

**Problem 6.** What is the result of the following conditional expression?

```python
x = 7
result = "Even" if x % 2 == 0 else "Odd"
print(result)
```

① Even  
② Odd  
③ True  
④ Error  

---

**Problem 7.** For `print("Pass")` to execute in the following code, which condition must be met?

```python
if score >= 60 and attendance >= 80:
    print("Pass")
```

① score >= 60 only  
② attendance >= 80 only  
③ Either one  
④ Both conditions  

---

### 🟡 Intermediate

**Problem 8.** What is the output of the following code?

```python
x = 50
if x > 100:
    print("A")
elif x > 30:
    print("B")
elif x > 10:
    print("C")
else:
    print("D")
```

① A  
② B  
③ C  
④ B C  

---

**Problem 9.** What is the output of the following code?

```python
x = 5
y = 10
if x > 3:
    if y > 20:
        print("A")
    else:
        print("B")
else:
    print("C")
```

① A  
② B  
③ C  
④ A B  

---

**Problem 10.** What is the output of the following code?

```python
a = 10
b = 20
max_val = a if a > b else b
print(max_val)
```

① 10  
② 20  
③ True  
④ Error  

---

**Problem 11.** What is the output of the following code?

```python
age = 20
is_student = True

if age >= 18 and is_student:
    print("Adult Student")
elif age >= 18:
    print("Adult")
else:
    print("Minor")
```

① Adult Student  
② Adult  
③ Minor  
④ Adult Student Adult  

---

**Problem 12.** In which case is "Discount Applied" **not** printed?

```python
price = 50000
is_member = True

if price >= 30000 or is_member:
    print("Discount Applied")
```

① price = 50000, is_member = True  
② price = 20000, is_member = True  
③ price = 50000, is_member = False  
④ price = 20000, is_member = False  

---

### 🔴 Advanced

**Problem 13.** What is the output of the following code?

```python
x = 15
if x > 20:
    print("A")
elif x > 10:
    print("B")
    if x > 12:
        print("C")
else:
    print("D")
```

① A  
② B  
③ B C  
④ B C D  

---

**Problem 14.** What is the output of the following code?

```python
score = 75
grade = "A" if score >= 90 else "B" if score >= 80 else "C" if score >= 70 else "F"
print(grade)
```

① A  
② B  
③ C  
④ F  

---

**Problem 15.** What is the output of the following code?

```python
x = 10
y = 5
z = 8

if x > y and y < z:
    if x + y > z:
        result = "Triangle Possible"
    else:
        result = "Triangle Impossible"
else:
    result = "Condition Not Met"
print(result)
```

① Triangle Possible  
② Triangle Impossible  
③ Condition Not Met  
④ Error  

---

## 📝 Short Answer Questions

---

### 🟢 Beginner

**Problem 16.** Explain the roles of `if`, `elif`, and `else` respectively, and describe the execution order of these three keywords.

---

**Problem 17.** Write the output of the following code.

```python
temperature = 25
if temperature >= 30:
    print("Hot")
elif temperature >= 20:
    print("Comfortable")
elif temperature >= 10:
    print("Cool")
else:
    print("Cold")
```

---

**Problem 18.** Write the basic structure of a conditional expression (ternary operator) and create a conditional expression to find the absolute value of `num = -3`.

---

### 🟡 Intermediate

**Problem 19.** Explain the difference between the following two codes and write the output of each.

**Code A:**
```python
score = 85
if score >= 90:
    print("A")
if score >= 80:
    print("B")
if score >= 70:
    print("C")
```

**Code B:**
```python
score = 85
if score >= 90:
    print("A")
elif score >= 80:
    print("B")
elif score >= 70:
    print("C")
```

---

**Problem 20.** Explain the concept of nested conditional statements and write the output of the following code.

```python
age = 22
is_student = True
has_id = False

if age >= 18:
    if is_student:
        if has_id:
            print("Student Discount Applied")
        else:
            print("Please bring your student ID")
    else:
        print("Regular Price")
else:
    print("Youth Price")
```

---

### 🔴 Advanced

**Problem 21.** Write the output of the following code and explain the judgment process for each condition step by step.

```python
x = 45
y = 30

if x >= 50 or y >= 50:
    tier = "Gold"
elif x >= 30 and y >= 30:
    tier = "Silver"
elif x >= 30 or y >= 30:
    tier = "Bronze"
else:
    tier = "Regular"

bonus = "Extra Bonus" if x + y >= 70 else "No Bonus"
print(f"Tier: {tier}, {bonus}")
```

---

## 💻 Hands-On Problems

---

### 🟢 Beginner

**Problem 22.** Write a program that meets the following requirements.

> Use if-else statement to determine if the number in variable `number = 7` is even or odd, and print the result.

Output example:

```
7 is an odd number.
```

---

**Problem 23.** Write a program that meets the following requirements.

> Use if-elif-else statement to determine the letter grade for the score in variable `score = 72`.  
> (90 and above: A, 80 and above: B, 70 and above: C, 60 and above: D, otherwise: F)

Output example:

```
Score: 72 points
Grade: C
```

---

**Problem 24.** Write a program that meets the following requirements.

> For `price = 45000`, if the price is $30 or more, shipping is free (0), otherwise it costs $3. Print the final amount.

Output example:

```
Order Amount: $45,000
Shipping: $0 (Free Shipping)
Final Amount: $45,000
```

---

### 🟡 Intermediate

**Problem 25.** Write a program that meets the following requirements.

> Receive **age** and **student status (yes/no)** from the user using `input()` and calculate the movie ticket price.
>
> - Under 12: $5 (Child)
> - 12 to under 18: $8 (Youth)
> - 18 and above, student: $10 (Student Discount)
> - 18 and above, not student: $14 (Adult)
> - 65 and above: $7 (Senior, regardless of student status)

Output example (age: 20, student: yes):

```
=== Movie Ticket ===
Age: 20 years old
Student: yes
-----------------
Category: Student Discount
Ticket Price: $10
```

---

### 🔴 Advanced

**Problem 26.** Write a program that meets the following requirements.

> Receive **year and month** from the user using `input()` and print the number of days in that month.
>
> - 1, 3, 5, 7, 8, 10, 12: 31 days
> - 4, 6, 9, 11: 30 days
> - 2: 29 days if leap year, 28 otherwise
> - Leap year condition: (divisible by 4 and not divisible by 100) or (divisible by 400)

Output example:

```
Enter year: 2024
Enter month: 2
February 2024 has 29 days. (Leap Year)

Enter year: 2023
Enter month: 2
February 2023 has 28 days. (Common Year)

Enter year: 2024
Enter month: 11
November 2024 has 30 days.
```

---
---

# 🔑 Answer Key and Explanations

---

## 📝 Multiple Choice Answers

---

### 🟢 Beginner

**Problem 1. Answer: ③ A (newline) B**

Since `x > 5` is `True`, `"A"` is printed. `print("B")` is outside the if block (no indentation), so it executes regardless of the condition. Therefore, A and B are printed on separate lines.

---

**Problem 2. Answer: ② Indentation (4 spaces)**

Python distinguishes code blocks using **indentation** instead of braces like other languages. Typically 4 spaces are used, and code in the same block must have identical indentation.

---

**Problem 3. Answer: ② Minor**

Since `age = 15`, `age >= 18` is `False`. Therefore, the `else` block executes, printing `"Minor"`.

---

**Problem 4. Answer: ② else if**

`elif` is short for **else if**. It allows checking additional conditions when the `if` condition is false.

---

**Problem 5. Answer: ② B**

Since `score = 85`, the first condition `score >= 90` is `False`. The second condition `score >= 80` is `True`, so `"B"` is printed. In elif structures, **only the first true condition's block executes**, and the rest are skipped.

---

**Problem 6. Answer: ② Odd**

Since `x = 7`, `7 % 2 == 0` is `False`. The condition is false, so the `else` part assigns `"Odd"` to `result`.

---

**Problem 7. Answer: ④ Both conditions**

The `and` operator makes the entire condition `True` only if **both conditions are `True`**. Therefore, both `score >= 60` and `attendance >= 80` must be satisfied for `"Pass"` to print.

---

### 🟡 Intermediate

**Problem 8. Answer: ② B**

For `x = 50`: `x > 100` is `False`, but `x > 30` is `True`. The first true condition's block executes, printing `"B"`. Remaining elif conditions are skipped.

---

**Problem 9. Answer: ② B**

`x = 5 > 3` is `True`, entering the first if block. Inside, `y = 10 > 20` is `False`, so the `else` block executes, printing `"B"`. This is nested conditional logic.

---

**Problem 10. Answer: ② 20**

In the conditional expression, `a > b` → `10 > 20` is `False`, so the value after `else`, which is `b` (20), is assigned to `max_val`.

---

**Problem 11. Answer: ① Adult Student**

`age >= 18` is `True` and `is_student` is `True`, so `True and True = True`. The first condition is true, printing `"Adult Student"`. The remaining elif is skipped.

---

**Problem 12. Answer: ④ price = 20000, is_member = False**

The `or` operator makes the condition `True` if **at least one part is `True`**. In ④, `20000 >= 30000` is `False` and `is_member` is `False`, so `False or False = False`. This is the only case where the condition is false and nothing prints.

---

### 🔴 Advanced

**Problem 13. Answer: ③ B C**

For `x = 15`: `x > 20` is `False`, but `x > 10` is `True`, entering the elif block and printing `"B"`. Inside this block, `x > 12` (`15 > 12`) is `True`, so `"C"` is also printed. Result: B and C each print.

---

**Problem 14. Answer: ③ C**

Nested conditional expressions are interpreted right-to-left. For `score = 75`: `75 >= 90` → `False` → `75 >= 80` → `False` → `75 >= 70` → `True` → `"C"`. Chained conditional expressions enable multi-level grading.

---

**Problem 15. Answer: ① Triangle Possible**

`x > y` (`10 > 5`) = `True`, `y < z` (`5 < 8`) = `True` → `True and True = True`. Inner condition: `x + y > z` (`10 + 5 > 8` = `15 > 8`) = `True` → `"Triangle Possible"`.

---

## 📝 Short Answer Key

---

### 🟢 Beginner

**Problem 16. Model Answer:**

- **`if`**: Checks the first condition. If `True`, executes the corresponding block.
- **`elif`**: When `if` is `False`, checks an additional condition. Multiple `elif` blocks are allowed.
- **`else`**: Executes when all `if` and `elif` conditions are `False`. Used without a condition.

**Execution order:** Check if condition → if `False`, check first elif → if `False`, check next elif → ... → if all `False`, execute else. **Only the first true condition's block executes**, and the rest are skipped.

---

**Problem 17. Model Answer:**

```
Comfortable
```

Since `temperature = 25`, `>= 30` is `False` but `>= 20` is `True`. The second condition's block executes. Remaining conditions are not checked.

---

**Problem 18. Model Answer:**

**Basic structure:**

```python
variable = value_if_true if condition else value_if_false
```

**Finding absolute value:**

```python
num = -3
abs_num = num if num >= 0 else -num
print(abs_num)  # 3
```

Since `num >= 0` is `False`, `-num` = `-(-3)` = `3` is assigned to `abs_num`.

---

### 🟡 Intermediate

**Problem 19. Model Answer:**

**Code A output:**

```
B
C
```

**Code B output:**

```
B
```

**Difference:** Code A has **three independent if statements**, so all conditions are checked. `score = 85` satisfies both `>= 80` and `>= 70`, so both B and C print.

Code B uses **if-elif-elif structure**, so only the first true condition (`>= 80`) executes, and other elifs are skipped. Only B prints.

---

**Problem 20. Model Answer:**

**Nested conditional statements:** Placing one conditional statement inside another, used to check multiple levels of conditions sequentially. Inner conditions are only evaluated if the outer condition is true.

**Execution result:**

```
Please bring your student ID
```

**Judgment process:**
1. `age >= 18` → `22 >= 18` = `True` → Enter first if block
2. `is_student` → `True` → Enter second if block
3. `has_id` → `False` → Execute else block → Print `"Please bring your student ID"`

---

### 🔴 Advanced

**Problem 21. Model Answer:**

Execution result:

```
Tier: Silver, Extra Bonus
```

**Tier determination:**
1. `x >= 50 or y >= 50` → `45 >= 50`(`False`) `or` `30 >= 50`(`False`) → `False` → Skip
2. `x >= 30 and y >= 30` → `45 >= 30`(`True`) `and` `30 >= 30`(`True`) → `True` → `tier = "Silver"`

The second condition is true, so remaining elif/else are skipped.

**Bonus determination (conditional expression):**
- `x + y >= 70` → `45 + 30 = 75 >= 70` → `True` → `bonus = "Extra Bonus"`

---

## 💻 Hands-On Solutions

---

### 🟢 Beginner

**Problem 22. Model Answer:**

```python
number = 7

if number % 2 == 0:
    print(f"{number} is an even number.")
else:
    print(f"{number} is an odd number.")
```

Key point: Use the `%` operator to find remainder when divided by 2. If 0, it's even; otherwise, odd.

---

**Problem 23. Model Answer:**

```python
score = 72

if score >= 90:
    grade = "A"
elif score >= 80:
    grade = "B"
elif score >= 70:
    grade = "C"
elif score >= 60:
    grade = "D"
else:
    grade = "F"

print(f"Score: {score} points")
print(f"Grade: {grade}")
```

Key point: In elif structure, check from **highest scores first**, so conditions are checked in correct order.

---

**Problem 24. Model Answer:**

```python
price = 45000

if price >= 30000:
    shipping = 0
    msg = "$0 (Free Shipping)"
else:
    shipping = 3
    msg = f"${shipping}"

total = price + shipping

print(f"Order Amount: ${price:,}")
print(f"Shipping: {msg}")
print(f"Final Amount: ${total:,}")
```

Key point: Use if-else to branch shipping cost, and f-string `{:,}` formatting for thousand separators.

---

### 🟡 Intermediate

**Problem 25. Model Answer:**

```python
age = int(input("Age: "))
is_student = input("Student (yes/no): ")

if age >= 65:
    price = 7
    category = "Senior"
elif age >= 18:
    if is_student == "yes":
        price = 10
        category = "Student Discount"
    else:
        price = 14
        category = "Adult"
elif age >= 12:
    price = 8
    category = "Youth"
else:
    price = 5
    category = "Child"

print(f"\n=== Movie Ticket ===")
print(f"Age: {age} years old")
print(f"Student: {is_student}")
print(f"-----------------")
print(f"Category: {category}")
print(f"Ticket Price: ${price}")
```

Key points:
- Check 65+ first to apply senior price regardless of student status.
- Use nested if to add student discount check for 18+.
- Arrange elif conditions so they don't overlap.

---

### 🔴 Advanced

**Problem 26. Model Answer:**

```python
year = int(input("Enter year: "))
month = int(input("Enter month: "))

# Determine leap year
is_leap = (year % 4 == 0 and year % 100 != 0) or (year % 400 == 0)

# Determine days in month
if month in [1, 3, 5, 7, 8, 10, 12]:
    days = 31
elif month in [4, 6, 9, 11]:
    days = 30
elif month == 2:
    if is_leap:
        days = 29
    else:
        days = 28

# Output
if month == 2:
    year_type = "Leap Year" if is_leap else "Common Year"
    print(f"{month} {year} has {days} days. ({year_type})")
else:
    print(f"{month} {year} has {days} days.")
```

Key points:
- Express leap year condition in one line using logical operators.
- Use `in` operator to compare multiple values at once.
- Use nested if to check leap/common year for February.
- Use conditional expression for concise output messages.
- Verification: 2024/2→29(leap), 1900/2→28(common), 2000/2→29(leap), 2024/11→30

---

Professor Cho Jeonghyun (peterchokr@gmail.com)  
Yeungnam University College.
