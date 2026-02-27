# Chapter 3: Operators and Expressions — Practice Problems

---

## 📝 Multiple Choice Questions

---

### 🟢 Beginner

**Problem 1.** What is the output of the following code?

```python
x = 10
x += 3
print(x)
```

① 10
② 13
③ 3
④ Error

---

**Problem 2.** Which of the following is the modulo operator in Python?

① `/`
② `//`
③ `%`
④ `**`

---

**Problem 3.** What is the output of the following code?

```python
print(2 ** 4)
```

① 6
② 8
③ 16
④ 24

---

**Problem 4.** Which of the following is the correct result of the comparison operation?

```python
print(10 >= 10)
```

① True
② False
③ 10
④ Error

---

**Problem 5.** Which operator is used to compare if two values are equal in Python?

① `=`
② `==`
③ `!=`
④ `>=`

---

**Problem 6.** What is the output of the following code?

```python
print("*" * 5)
```

① `* * * * *`
② `*5`
③ `*****`
④ Error

---

**Problem 7.** What is the result of `not True`?

① True
② False
③ 0
④ None

---

### 🟡 Intermediate

**Problem 8.** What is the output of the following code?

```python
result = 2 + 3 * 4 - 1
print(result)
```

① 19
② 13
③ 20
④ 14

---

**Problem 9.** What is the output of the following code?

```python
x = 10
x *= 3
x -= 5
print(x)
```

① 25
② 30
③ 35
④ 15

---

**Problem 10.** Which of the following results in `True`?

```python
age = 15
has_ticket = True
```

① `age >= 18 and has_ticket`
② `age >= 18 or not has_ticket`
③ `age < 18 and has_ticket`
④ `not has_ticket`

---

**Problem 11.** What is the output of the following code?

```python
a = 17
b = 5
print(a // b, a % b)
```

① 3.4 2
② 3 2
③ 3 3
④ 4 2

---

**Problem 12.** Which of the following causes an error?

① `"Hello" + " World"`
② `"Hello" * 3`
③ `"Hello" + 3`
④ `"Hello" * True`

---

### 🔴 Advanced

**Problem 13.** What is the output of the following code?

```python
x = 5
result = x > 3 and x < 10 or x == 1
print(result)
```

① True
② False
③ 1
④ Error

---

**Problem 14.** What is the output of the following code?

```python
result = 2 ** 3 ** 2
print(result)
```

① 64
② 512
③ 256
④ 36

---

**Problem 15.** What is the output of the following code?

```python
x = 100
x //= 3
x %= 5
print(x)
```

① 33
② 3
③ 1
④ 8

---

## 📝 Short Answer Questions

---

### 🟢 Beginner

**Problem 16.** Write all 7 arithmetic operators in Python with their symbols.

---

**Problem 17.** Explain the difference between `=` (assignment operator) and `==` (comparison operator).

---

**Problem 18.** Write the output of the following code.

```python
a = 20
b = 7
print(a / b)
print(a // b)
print(a % b)
```

---

### 🟡 Intermediate

**Problem 19.** Explain the behavior of `and`, `or`, and `not` operators respectively, and write the output of the following code.

```python
a = True
b = False
print(a and b)
print(a or b)
print(not a)
```

---

**Problem 20.** Write Python code to solve the following problem. (Use variables and write the result)

> A product costs $50. After applying a 20% discount, add 10% sales tax to calculate the final price.

---

### 🔴 Advanced

**Problem 21.** Write the output of the following code, and explain step by step the calculation process according to operator precedence.

```python
x = 10
y = 3
z = 2
result = x + y * z ** 2 > 20 and not x % y == 0
print(result)
```

---

## 💻 Hands-On Problems

---

### 🟢 Beginner

**Problem 22.** Write a program that meets the following requirements.

> Starting with `total = 0`, use the compound assignment operator (`+=`) to accumulate three test scores (85, 92, 78) sequentially, then print the total and average.

Output example:

```
Total Score: 255 points
Average: 85.0 points
```

---

**Problem 23.** Write a program that meets the following requirements.

> Store an integer in a variable, then use the modulo operator (`%`) and comparison operator (`==`) to determine if it is even or odd, and print the results.

Output example:

```
Number: 7
Is Even: False
Is Odd: True
```

---

**Problem 24.** Write a program that meets the following requirements.

> Use the string repetition operator (`*`) to print the following pattern:

Output:

```
*
**
***
****
*****
```

---

### 🟡 Intermediate

**Problem 25.** Write a program that meets the following requirements.

> Use `input()` to receive the original price ($) and discount rate (%) from the user, then calculate the discount amount and final price.
> Apply free shipping (standard shipping: $3) for purchases of $50 or more, and print the final payment amount.

Output example:

```
=== Discount Calculator ===
Original Price: 60
Discount Rate (%): 20
--------------------
Discount Amount: $12.00
Price After Discount: $48.00
Shipping: $0.00 (Free Shipping)
Final Payment: $48.00
```

---

### 🔴 Advanced

**Problem 26.** Write a program that meets the following requirements.

> Use `input()` to receive a year from the user and determine if it is a leap year.
> Leap year conditions: ① Divisible by 4 and not divisible by 100, or ② Divisible by 400
> Use logical operators (`and`, `or`) and the modulo operator (`%`) to write it as a single conditional expression.

Output example:

```
Enter the year: 2024
Is 2024 a leap year? True

Enter the year: 1900
Is 1900 a leap year? False

Enter the year: 2000
Is 2000 a leap year? True
```

---

---

# 🔑 Answer Key and Explanations

---

## 📝 Multiple Choice Answers

---

### 🟢 Beginner

**Problem 1. Answer: ② 13**

`x += 3` is equivalent to `x = x + 3`. Since the initial value of `x` is 10, `10 + 3 = 13`. The compound assignment operator performs the operation on the current value and then stores the result back.

---

**Problem 2. Answer: ③ %**

`%` is the modulo operator, which returns the remainder of division. `/` is regular division, `//` is integer division (quotient), and `**` is the exponentiation operator.

---

**Problem 3. Answer: ③ 16**

`**` is the exponentiation operator. `2 ** 4` is 2 to the power of 4, which is `2 × 2 × 2 × 2 = 16`.

---

**Problem 4. Answer: ① True**

`>=` is the "greater than or equal to" comparison operator. Since 10 equals 10, the result of `10 >= 10` is `True`.

---

**Problem 5. Answer: ② ==**

`==` is the comparison operator that checks if two values are equal, while `=` is the assignment operator that stores a value in a variable. It's important not to confuse these two operators.

---

**Problem 6. Answer: ③ `*****`**

Using the `*` operator with a string and an integer repeats the string that many times. `"*" * 5` repeats the asterisk 5 times to create `*****`.

---

**Problem 7. Answer: ② False**

The `not` operator reverses the boolean value. `not True` becomes `False`, and `not False` becomes `True`.

---

### 🟡 Intermediate

**Problem 8. Answer: ② 13**

According to operator precedence, multiplication is performed first. `3 * 4 = 12` → `2 + 12 - 1 = 13`. If calculated left to right, it would be 19, but multiplication has higher precedence than addition and subtraction.

---

**Problem 9. Answer: ① 25**

Calculate sequentially. `x = 10` → `x *= 3` gives `x = 10 * 3 = 30` → `x -= 5` gives `x = 30 - 5 = 25`. Compound assignment operators are applied in order from top to bottom.

---

**Problem 10. Answer: ③ `age < 18 and has_ticket`**

Since `age = 15`, `age < 18` is `True`, and `has_ticket` is `True`. `True and True = True`. ① `False and True = False`, ② `False or False = False`, ④ `not True = False`.

---

**Problem 11. Answer: ② 3 2**

`17 // 5 = 3` (quotient), `17 % 5 = 2` (remainder). Verification: 5 × 3 + 2 = 17. `//` is integer division that discards decimals, while `%` finds the remainder.

---

**Problem 12. Answer: ③ `"Hello" + 3`**

You cannot directly concatenate a string and an integer using the `+` operator. This causes a `TypeError`. You must convert: `"Hello" + str(3)`. Note that ④ `"Hello" * True` works because `True` is treated as the integer 1, resulting in `"Hello"`.

---

### 🔴 Advanced

**Problem 13. Answer: ① True**

Operator precedence: Comparison → not → and → or. `x > 3` is `True`, `x < 10` is `True`, `x == 1` is `False`. → `True and True` is `True` → `True or False` is `True`.

---

**Problem 14. Answer: ② 512**

The exponentiation operator (`**`) is **right-associative** (groups from right to left). Therefore, `2 ** (3 ** 2)` = `2 ** 9` = `512`. If it were `(2 ** 3) ** 2`, the result would be `8 ** 2 = 64`.

---

**Problem 15. Answer: ② 3**

Calculate sequentially. `x = 100` → `x //= 3` gives `x = 100 // 3 = 33` → `x %= 5` gives `x = 33 % 5 = 3`. Verification: 33 ÷ 5 = 6 remainder 3.

---

## 📝 Short Answer Key

---

### 🟢 Beginner

**Problem 16. Model Answer:**

| Operator                    | Symbol |
| --------------------------- | ------ |
| Addition                    | `+`  |
| Subtraction                 | `-`  |
| Multiplication              | `*`  |
| Division                    | `/`  |
| Integer Division (Quotient) | `//` |
| Modulo (Remainder)          | `%`  |
| Exponentiation              | `**` |

---

**Problem 17. Model Answer:**

`=` is the **assignment operator**, which stores the right value in the left variable. Example: `x = 10` (store 10 in variable x)

`==` is the **comparison operator**, which compares whether the left and right values are equal and returns `True` or `False`. Example: `x == 10` (check if x equals 10)

---

**Problem 18. Model Answer:**

```
2.857142857142857
2
6
```

`20 / 7 = 2.857142857142857` (regular division, always returns float), `20 // 7 = 2` (integer division, returns quotient only), `20 % 7 = 6` (modulo operation). Verification: 7 × 2 + 6 = 20.

---

### 🟡 Intermediate

**Problem 19. Model Answer:**

**Operator Explanation:**

- `and`: Returns `True` only if **both conditions are True**.
- `or`: Returns `True` if **at least one condition is True**.
- `not`: **Reverses** the boolean value (True → False, False → True).

**Execution Results:**

```
False
True
False
```

`True and False = False` (one is False), `True or False = True` (one is True), `not True = False`.

---

**Problem 20. Model Answer:**

```python
original_price = 50.00        # Original price in dollars
discount_rate = 20            # Discount rate (%)
tax_rate = 10                 # Sales tax rate (%)

# Apply discount
discount_amount = original_price * discount_rate / 100    # 10.00
discounted_price = original_price - discount_amount       # 40.00

# Apply sales tax
tax_amount = discounted_price * tax_rate / 100           # 4.00
final_price = discounted_price + tax_amount              # 44.00

print(f"Original Price: ${original_price:.2f}")
print(f"Discount Amount: ${discount_amount:.2f}")
print(f"Price After Discount: ${discounted_price:.2f}")
print(f"Sales Tax: ${tax_amount:.2f}")
print(f"Final Price: ${final_price:.2f}")
```

Result: Final price is **$44.00**

---

### 🔴 Advanced

**Problem 21. Model Answer:**

Execution result:

```
True
```

**Step-by-step calculation process (in order of operator precedence):**

1. **Exponentiation** `z ** 2` = `2 ** 2` = `4`
2. **Multiplication** `y * 4` = `3 * 4` = `12`
3. **Addition** `x + 12` = `10 + 12` = `22`
4. **Modulo** `x % y` = `10 % 3` = `1`
5. **Comparison (>)** `22 > 20` = `True`
6. **Comparison (==)** `1 == 0` = `False`
7. **not** `not False` = `True`
8. **and** `True and True` = `True`

Final result: `True`

---

## 💻 Hands-On Solutions

---

### 🟢 Beginner

**Problem 22. Model Answer:**

```python
total = 0

total += 85   # First subject
total += 92   # Second subject
total += 78   # Third subject

average = total / 3

print(f"Total Score: {total} points")
print(f"Average: {average:.1f} points")
```

Key point: Use the `+=` compound assignment operator to accumulate values. `total / 3` always returns a float, so the average includes decimal places.

---

**Problem 23. Model Answer:**

```python
number = 7

is_even = number % 2 == 0   # Determine if even
is_odd = number % 2 != 0    # Determine if odd

print(f"Number: {number}")
print(f"Is Even: {is_even}")
print(f"Is Odd: {is_odd}")
```

Key point: A number is even if its remainder when divided by 2 is 0, and odd if the remainder is non-zero. Combine the `%` (modulo) and `==` (comparison) operators.

---

**Problem 24. Model Answer:**

```python
print("*" * 1)
print("*" * 2)
print("*" * 3)
print("*" * 4)
print("*" * 5)
```

Key point: Use the string repetition operator `*` to repeat `"*"` 1 to 5 times respectively.

---

### 🟡 Intermediate

**Problem 25. Model Answer:**

```python
print("=== Discount Calculator ===")

# Input
original_price = float(input("Original Price: $"))
discount_rate = int(input("Discount Rate (%): "))

# Calculate discount
discount_amount = original_price * discount_rate / 100
discounted_price = original_price - discount_amount

# Determine shipping (free for $50 or more)
shipping_fee = 3.00
free_shipping = discounted_price >= 50.00

if free_shipping:
    final_shipping = 0.00
else:
    final_shipping = shipping_fee

# Final payment amount
final_price = discounted_price + final_shipping

# Output
print("--------------------")
print(f"Discount Amount: ${discount_amount:.2f}")
print(f"Price After Discount: ${discounted_price:.2f}")
if free_shipping:
    print(f"Shipping: ${final_shipping:.2f} (Free Shipping)")
else:
    print(f"Shipping: ${final_shipping:.2f}")
print(f"Final Payment: ${final_price:.2f}")
```

Key points:

- Use arithmetic operators (`*`, `/`, `-`) to calculate the discount.
- Use the comparison operator (`>=`) to determine the free shipping condition.
- Use `{:.2f}` formatting to display currency with two decimal places.

---

### 🔴 Advanced

**Problem 26. Model Answer:**

```python
year = int(input("Enter the year: "))

# Determine leap year (single-line conditional expression)
is_leap_year = (year % 4 == 0 and year % 100 != 0) or (year % 400 == 0)

print(f"Is {year} a leap year? {is_leap_year}")
```

Key points:

- Use the `%` operator to check divisibility (remainder of 0 means divisible).
- Use `and` to check if both conditions are satisfied, and `or` to check if at least one is satisfied.
- Verification: 2024 → `2024 % 4 == 0`(True) `and` `2024 % 100 != 0`(True) → True
- Verification: 1900 → `1900 % 4 == 0`(True) `and` `1900 % 100 != 0`(False) → False, `1900 % 400 == 0`(False) → Final False
- Verification: 2000 → First condition False, `2000 % 400 == 0`(True) → Final True

---


Thank you for your attention.   
Cho Jeonghyun ([peterchokr@gmail.com](mailto:peterchokr@gmail.com)). Yeungnam University College

"Produced in collaboration with Claude and Gemini."
