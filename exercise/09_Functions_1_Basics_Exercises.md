# Chapter 9: Functions 1 (Basics) — Practice Problems

---

## 📝 Multiple Choice Questions

---

### 🟢 Beginner

**Problem 1.** What keyword is used to define a function in Python?

① function
② def
③ define
④ func

---

**Problem 2.** What is the output of the following code?

```python
def greet():
    print("Hello!")

greet()
greet()
```

① Hello! (1 time)
② Hello! (2 times, each on a new line)
③ greet greet
④ Error

---

**Problem 3.** What happens if a function is defined but never called?

```python
def say_hi():
    print("Hi!")
```

① "Hi!" is printed
② Nothing happens
③ Error occurs
④ None is printed

---

**Problem 4.** What is the output of the following code?

```python
def add(a, b):
    return a + b

result = add(3, 7)
print(result)
```

① 3
② 7
③ 10
④ Error

---

**Problem 5.** What does a function without `return` return?

① 0
② ""
③ None
④ False

---

**Problem 6.** What is the output of the following code?

```python
def greet(name):
    print(f"Hello, {name}!")

greet("John")
```

① Hello, name!
② Hello, John!
③ Hello, "John"!
④ Error

---

**Problem 7.** Which correctly calls the function?

```python
def multiply(a, b):
    return a * b
```

① multiply 3, 5
② multiply(3, 5)
③ call multiply(3, 5)
④ def multiply(3, 5)

---

### 🟡 Intermediate

**Problem 8.** What is the output of the following code?

```python
def make_coffee(menu="Americano"):
    print(f"{menu} is ready!")

make_coffee()
make_coffee("Latte")
```

① Americano is ready! (2 times)
② Americano is ready! / Latte is ready!
③ Error
④ None is ready! / Latte is ready!

---

**Problem 9.** What is the output of the following code?

```python
def show_sum(a, b):
    print(a + b)

result = show_sum(10, 20)
print(result)
```

① 30 (newline) 30
② 30 (newline) None
③ Only 30 prints
④ Error

---

**Problem 10.** Which is the correct function definition?

① `def func(a, b=10, c):`
② `def func(a, b, c=10):`
③ `def func(a=10, b, c):`
④ `def func(a=10, b=20, c):`

---

**Problem 11.** What is the output of the following code?

```python
def calculate(price, tax_rate=10):
    tax = price * tax_rate / 100
    return price + tax

print(calculate(1000))
print(calculate(1000, 20))
```

① 1100.0 / 1200.0
② 1010.0 / 1020.0
③ 1000 / 1000
④ Error

---

**Problem 12.** Which correctly describes keyword arguments?

```python
def info(name, age):
    print(f"{name}, {age}")

info(age=25, name="John")
```

① Must come before positional arguments
② Values are passed by parameter name
③ Only usable with default parameters
④ Order cannot be changed

---

### 🔴 Advanced

**Problem 13.** What is the output of the following code?

```python
def calculate_discount(price, rate):
    return price * (1 - rate / 100)

original = 50000
final = calculate_discount(original, 20)
print(f"{final:,.0f}")
```

① 50,000
② 40,000
③ 10,000
④ Error

---

**Problem 14.** What is the output of the following code?

```python
def get_ticket_price(age, is_morning=False):
    price = 14000
    if age <= 12:
        price = 9000
    if is_morning:
        price -= 2000
    return price

print(get_ticket_price(10, True))
```

① 14000
② 12000
③ 9000
④ 7000

---

**Problem 15.** What is the output of the following code?

```python
def outer():
    x = 10
    print(x)

x = 20
outer()
print(x)
```

① 10 / 10
② 20 / 20
③ 10 / 20
④ 20 / 10

---

## 📝 Short Answer Questions

---

### 🟢 Beginner

**Problem 16.** Explain the difference between a parameter and an argument.

---

**Problem 17.** Write the output of the following code.

```python
def repeat(text, count):
    for i in range(count):
        print(text)

repeat("Python", 3)
```

---

**Problem 18.** Explain the difference between `return` and `print()`, and when to use each.

---

### 🟡 Intermediate

**Problem 19.** Write the output of the following code and explain how default parameters work.

```python
def power(base, exponent=2):
    return base ** exponent

print(power(3))
print(power(2, 10))
print(power(5, 3))
```

---

**Problem 20.** Write the output of the following code and explain the difference between positional and keyword arguments.

```python
def order(item, quantity, unit="piece"):
    print(f"{item} {quantity}{unit}")

order("apple", 3)
order("milk", 2, "pack")
order(quantity=5, item="egg", unit="dozen")
```

---

### 🔴 Advanced

**Problem 21.** Write the output of the following code and explain the process of chained function calls.

```python
def get_grade(avg):
    if avg >= 90: return "A"
    elif avg >= 80: return "B"
    elif avg >= 70: return "C"
    else: return "F"

def get_average(kor, eng, math):
    return (kor + eng + math) / 3

def report(name, kor, eng, math):
    avg = get_average(kor, eng, math)
    grade = get_grade(avg)
    return f"{name}: Average {avg:.1f}, Grade {grade}"

print(report("John", 85, 92, 78))
```

---

## 💻 Hands-On Problems

---

### 🟢 Beginner

**Problem 22.** Write a program that meets the following requirements.

> Write a function `get_max(a, b)` that receives two numbers and returns the larger one. Test it.

Output example:

```
get_max(10, 20) = 20
get_max(7, 3) = 7
get_max(5, 5) = 5
```

---

**Problem 23.** Write a program that meets the following requirements.

> Write a function `greet(name, message="Hello")` that receives a name and a greeting message. The default greeting is `"Hello"`.

Output example:

```
John, Hello!
Jane, Nice to meet you!
```

---

**Problem 24.** Write a program that meets the following requirements.

> Write a function `circle_area(radius)` that calculates and returns the area of a circle. (π = 3.14)

Output example:

```
Area of circle with radius 5: 78.5
Area of circle with radius 10: 314.0
```

---

### 🟡 Intermediate

**Problem 25.** Write a program that meets the following requirements.

> Create a grade processing program with three functions:
>
> - `calc_total(kor, eng, math)` : returns total score
> - `calc_average(total)` : returns average (3 subjects)
> - `get_grade(avg)` : returns grade (A/B/C/D/F)
>
> Receive three subject scores using `input()` and print the results.

Output example (Korean: 85, English: 92, Math: 78):

```
=== Grade Report ===
Korean: 85 points
English: 92 points
Math: 78 points
--------------
Total: 255 points
Average: 85.0 points
Grade: B
```

---

### 🔴 Advanced

**Problem 26.** Write a program that meets the following requirements.

> Implement a product price calculation system with functions:
>
> - `apply_discount(price, rate=10)` : returns price after discount (default 10%)
> - `add_tax(price, tax_rate=10)` : returns price after tax (default 10%)
> - `calc_final_price(price, discount=10, tax=10)` : returns final price with discount applied first, then tax
>
> Print three cases for product price $50,000.

Output example:

```
=== Price Calculation ===
Original Price: $50,000

[Default 10% discount + 10% tax]
Final Price: $49,500

[20% discount + 10% tax]
Final Price: $44,000

[No discount + 5% tax]
Final Price: $52,500
```

---

---

# 🔑 Answer Key and Explanations

---

## 📝 Multiple Choice Answers

---

### 🟢 Beginner

**Problem 1. Answer: ② def**

Python uses `def` keyword to define functions: `def function_name():`. `function` is used in JavaScript.

---

**Problem 2. Answer: ② Hello! (2 times, each on a new line)**

`greet()` is called 2 times, so `"Hello!"` prints 2 times. Each function call executes the code inside.

---

**Problem 3. Answer: ② Nothing happens**

Defining a function with `def` doesn't execute the code. You must call it like `say_hi()` to execute the code inside.

---

**Problem 4. Answer: ③ 10**

`add(3, 7)` returns `3 + 7 = 10`, which is stored in `result` and printed.

---

**Problem 5. Answer: ③ None**

A function without `return` automatically returns `None`. `None` means "no value."

---

**Problem 6. Answer: ② Hello, John!**

Parameter `name` receives the argument `"John"`. The f-string substitutes `{name}` with `"John"`.

---

**Problem 7. Answer: ② multiply(3, 5)**

Function calls use the format `function_name(argument1, argument2)`. Arguments go inside parentheses.

---

### 🟡 Intermediate

**Problem 8. Answer: ② Americano is ready! / Latte is ready!**

First call without argument uses the default value `"Americano"`. Second call with `"Latte"` replaces the default.

---

**Problem 9. Answer: ② 30 (newline) None**

`show_sum` **prints** 30 but has no `return`, so it returns `None`. `result` stores `None`, which the second `print()` outputs.

---

**Problem 10. Answer: ② `def func(a, b, c=10):`**

Parameters with default values must come **after** those without. ①③④ have non-default parameters after default ones, causing error.

---

**Problem 11. Answer: ① 1100.0 / 1200.0**

First: uses default `tax_rate=10` → `1000 × 10/100 = 100` → `1000 + 100 = 1100.0`. Second: `tax_rate=20` → `1000 × 20/100 = 200` → `1000 + 200 = 1200.0`.

---

**Problem 12. Answer: ② Values are passed by parameter name**

Keyword arguments use `parameter_name=value` format and can be passed in any order. They must come after positional arguments.

---

### 🔴 Advanced

**Problem 13. Answer: ② 40,000**

`50000 × (1 - 20/100) = 50000 × 0.8 = 40000.0`. The `{:,.0f}` format produces `40,000`.

---

**Problem 14. Answer: ④ 7000**

`age=10` → 12 or under, so `price = 9000`. `is_morning=True` → `9000 - 2000 = 7000`. Discounts apply sequentially.

---

**Problem 15. Answer: ③ 10 / 20**

The `x = 10` inside `outer()` is a **local variable**, printing 10. The `x = 20` outside is a **global variable**, printing 20. They're separate despite sharing a name.

---

## 📝 Short Answer Key

---

### 🟢 Beginner

**Problem 16. Model Answer:**

**Parameter:** A variable name in the parentheses when **defining** a function. It's the "slot" for values used inside the function.

**Argument:** The actual value in parentheses when **calling** a function. It's the concrete data passed to the parameter.

```python
def greet(name):    # name is a parameter
    print(name)

greet("John")       # "John" is an argument
```

---

**Problem 17. Model Answer:**

```
Python
Python
Python
```

`repeat("Python", 3)` passes `text="Python"` and `count=3`. The loop repeats 3 times, printing `"Python"` on three lines.

---

**Problem 18. Model Answer:**

**`return`:** **Returns** a value from the function. The returned value can be stored in a variable or used in other operations. Use when you need to reuse the result later.

**`print()`:** **Outputs** a value to the screen. Doesn't return a value (returns `None`), so the result can't be reused elsewhere. Use when displaying results to users.

```python
def get_sum(a, b):
    return a + b        # returns value → reusable

result = get_sum(10, 20)
print(result * 2)       # 60 (using the return value)
```

---

### 🟡 Intermediate

**Problem 19. Model Answer:**

Output:

```
9
1024
125
```

**Default parameter behavior:**

- `power(3)` → uses default `exponent=2` → `3 ** 2 = 9`
- `power(2, 10)` → argument 10 overrides default → `2 ** 10 = 1024`
- `power(5, 3)` → argument 3 overrides default → `5 ** 3 = 125`

When you pass an argument, it replaces the default. When you don't, the default is used.

---

**Problem 20. Model Answer:**

Output:

```
apple 3piece
milk 2pack
egg 5dozen
```

**Positional arguments:** Values are passed in the **order** of parameters.

- `order("apple", 3)` → `item="apple"`, `quantity=3`, `unit="piece"`(default)

**Keyword arguments:** Values are passed as `parameter_name=value`, **regardless of order**.

- `order(quantity=5, item="egg", unit="dozen")` → order doesn't matter; names match.

Rule: Positional arguments must come before keyword arguments.

---

### 🔴 Advanced

**Problem 21. Model Answer:**

Output:

```
John: Average 85.0, Grade B
```

**Chained function call process:**

1. `report("John", 85, 92, 78)` is called
2. Inside, `get_average(85, 92, 78)` is called → `(85+92+78)/3 = 255/3 = 85.0` returned
3. `avg = 85.0`, then `get_grade(85.0)` is called → `85.0 >= 80` → `"B"` returned
4. `grade = "B"`, f-string combines → `"John: Average 85.0, Grade B"` returned
5. `print()` outputs the final result

When a function uses another function's return value, it's called **chained function calls**.

---

## 💻 Hands-On Solutions

---

### 🟢 Beginner

**Problem 22. Model Answer:**

```python
def get_max(a, b):
    if a >= b:
        return a
    else:
        return b

print(f"get_max(10, 20) = {get_max(10, 20)}")
print(f"get_max(7, 3) = {get_max(7, 3)}")
print(f"get_max(5, 5) = {get_max(5, 5)}")
```

Key point: Use `if-else` to compare and `return` the larger value.

---

**Problem 23. Model Answer:**

```python
def greet(name, message="Hello"):
    print(f"{name}, {message}!")

greet("John")
greet("Jane", "Nice to meet you")
```

Key point: Set `message="Hello"` as default. When called without the argument, the default greeting is used.

---

**Problem 24. Model Answer:**

```python
def circle_area(radius):
    return 3.14 * radius ** 2

print(f"Area of circle with radius 5: {circle_area(5)}")
print(f"Area of circle with radius 10: {circle_area(10)}")
```

Key point: Implement the circle area formula `π × r²`. `3.14 × 5² = 78.5`, `3.14 × 10² = 314.0`.

---

### 🟡 Intermediate

**Problem 25. Model Answer:**

```python
def calc_total(kor, eng, math):
    return kor + eng + math

def calc_average(total):
    return total / 3

def get_grade(avg):
    if avg >= 90: return "A"
    elif avg >= 80: return "B"
    elif avg >= 70: return "C"
    elif avg >= 60: return "D"
    else: return "F"

# Input
kor = int(input("Korean: "))
eng = int(input("English: "))
math = int(input("Math: "))

# Calculate
total = calc_total(kor, eng, math)
avg = calc_average(total)
grade = get_grade(avg)

# Output
print(f"\n=== Grade Report ===")
print(f"Korean: {kor} points")
print(f"English: {eng} points")
print(f"Math: {math} points")
print(f"--------------")
print(f"Total: {total} points")
print(f"Average: {avg:.1f} points")
print(f"Grade: {grade}")
```

Key points:

- Separate each function for reusability.
- Chain function calls by using one function's return value as another's argument.

---

### 🔴 Advanced

**Problem 26. Model Answer:**

```python
def apply_discount(price, rate=10):
    return price * (1 - rate / 100)

def add_tax(price, tax_rate=10):
    return price * (1 + tax_rate / 100)

def calc_final_price(price, discount=10, tax=10):
    discounted = apply_discount(price, discount)
    final = add_tax(discounted, tax)
    return final

# Output
original = 50000
print(f"=== Price Calculation ===")
print(f"Original Price: ${original:,}")

# Case 1: Default
price1 = calc_final_price(original)
print(f"\n[Default 10% discount + 10% tax]")
print(f"Final Price: ${price1:,.0f}")

# Case 2: 20% discount
price2 = calc_final_price(original, discount=20)
print(f"\n[20% discount + 10% tax]")
print(f"Final Price: ${price2:,.0f}")

# Case 3: No discount + 5% tax
price3 = calc_final_price(original, discount=0, tax=5)
print(f"\n[No discount + 5% tax]")
print(f"Final Price: ${price3:,.0f}")
```

Key points:

- `calc_final_price` calls `apply_discount` and `add_tax` sequentially.
- Default parameters allow flexible function calls.
- Verification: 50000 × 0.9 × 1.1 = 49500, 50000 × 0.8 × 1.1 = 44000, 50000 × 1.0 × 1.05 = 52500

---


Thank you for your attention.   
Cho Jeonghyun ([peterchokr@gmail.com](mailto:peterchokr@gmail.com)). Yeungnam University College

"Produced in collaboration with Claude and Gemini."
