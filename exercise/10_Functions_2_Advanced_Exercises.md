# Chapter 10: Functions 2 (Advanced) — Practice Problems

---

## 📝 Multiple Choice Questions

---

### 🟢 Beginner

**Problem 1.** What is the output of the following code?

```python
def get_values():
    return 10, 20

a, b = get_values()
print(a + b)
```

① 10
② 20
③ 30
④ (10, 20)

---

**Problem 2.** What is the name of a variable created inside a function?

① Global variable
② Local variable
③ Class variable
④ Constant

---

**Problem 3.** What is the output of the following code?

```python
x = 100

def func():
    print(x)

func()
```

① Error
② None
③ 100
④ 0

---

**Problem 4.** What is the correct syntax for a lambda function?

① `lambda x: x * 2`
② `def lambda(x): return x * 2`
③ `lambda(x): x * 2`
④ `func x: x * 2`

---

**Problem 5.** What is the output of the following code?

```python
double = lambda x: x * 2
print(double(5))
```

① 5
② 10
③ x * 2
④ Error

---

**Problem 6.** What must a recursive function have?

① return statement
② global variable
③ Base case (terminating condition)
④ lambda function

---

**Problem 7.** What is the output of the following code?

```python
def factorial(n):
    if n <= 1:
        return 1
    return n * factorial(n - 1)

print(factorial(4))
```

① 4
② 10
③ 24
④ 120

---

### 🟡 Intermediate

**Problem 8.** Which keyword modifies a global variable inside a function?

① local
② global
③ nonlocal
④ static

---

**Problem 9.** What is the output of the following code?

```python
count = 0

def increment():
    global count
    count += 1

increment()
increment()
increment()
print(count)
```

① 0
② 1
③ 3
④ Error

---

**Problem 10.** What is the output of the following code?

```python
multiply = lambda a, b: a * b
result = multiply(3, 7)
print(result)
```

① 10
② 21
③ 37
④ Error

---

**Problem 11.** What is the output of the following code?

```python
def func(n):
    if n == 0:
        return 0
    return n + func(n - 1)

print(func(4))
```

① 4
② 6
③ 10
④ Infinite recursion

---

**Problem 12.** What is the output of the following code?

```python
x = 10

def func():
    x = 20
    print(x)

func()
print(x)
```

① 20 / 20
② 10 / 10
③ 20 / 10
④ 10 / 20

---

### 🔴 Advanced

**Problem 13.** What is the output of the following code?

```python
def calc_stats(a, b, c):
    total = a + b + c
    avg = total / 3
    return total, avg

t, a = calc_stats(80, 90, 70)
print(f"Total: {t}, Average: {a:.1f}")
```

① Total: 240, Average: 80.0
② Total: 80, Average: 80.0
③ (240, 80.0)
④ Error

---

**Problem 14.** What is the output of the following code?

```python
def fibonacci(n):
    if n <= 0: return 0
    elif n == 1: return 1
    else: return fibonacci(n-1) + fibonacci(n-2)

print(fibonacci(6))
```

① 5
② 8
③ 13
④ 21

---

**Problem 15.** Which is **FALSE** about recursive functions vs loops?

① Recursion code is more intuitive
② Recursion is slower than loops
③ Recursion uses less memory than loops
④ Recursion needs a base case

---

## 📝 Short Answer Questions

---

### 🟢 Beginner

**Problem 16.** Explain the difference between local and global variables and write example code for each.

---

**Problem 17.** Write the output of the following code.

```python
def swap(a, b):
    return b, a

x, y = swap(10, 20)
print(f"x={x}, y={y}")
```

---

**Problem 18.** Explain the concept of lambda functions and write a regular function equivalent to `lambda x, y: x + y`.

---

### 🟡 Intermediate

**Problem 19.** Write the output of the following code and explain why the `global` keyword is necessary.

```python
total = 0

def add_score(score):
    global total
    total += score
    return total

print(add_score(80))
print(add_score(90))
print(f"Final: {total}")
```

---

**Problem 20.** Write the output of the following code and explain the recursive call process step by step.

```python
def sum_recursive(n):
    if n <= 1:
        return n
    return n + sum_recursive(n - 1)

print(sum_recursive(5))
```

---

### 🔴 Advanced

**Problem 21.** Write the output of the following code and explain the difference between recursion and loop approaches.

```python
def power_recursive(base, exp):
    if exp == 0:
        return 1
    return base * power_recursive(base, exp - 1)

def power_loop(base, exp):
    result = 1
    for i in range(exp):
        result *= base
    return result

print(power_recursive(2, 8))
print(power_loop(2, 8))
```

---

## 💻 Hands-On Problems

---

### 🟢 Beginner

**Problem 22.** Write a program that meets the following requirements.

> Write a function `calc(a, b)` that returns **sum, difference, and product** simultaneously.

Output example:

```
calc(10, 3):
Sum: 13, Difference: 7, Product: 30
```

---

**Problem 23.** Write a program that meets the following requirements.

> Use a lambda function to convert Celsius to Fahrenheit. (Formula: `Fahrenheit = Celsius × 1.8 + 32`)

Output example:

```
0°C = 32.0°F
100°C = 212.0°F
36.5°C = 97.7°F
```

---

**Problem 24.** Write a program that meets the following requirements.

> Use a recursive function to print countdown from `n` to 1. When reaching 0, print `"Blast off!"`

Output example (n=5):

```
5
4
3
2
1
Blast off!
```

---

### 🟡 Intermediate

**Problem 25.** Write a program that meets the following requirements.

> Implement a simple bank system using global variable `balance = 10000`:
>
> - `deposit(amount)` : add funds
> - `withdraw(amount)` : remove funds (print "Insufficient balance" if not enough)
> - `check_balance()` : print balance

Output example:

```
Current Balance: 10,000
Deposit 5,000 → Balance: 15,000
Withdraw 3,000 → Balance: 12,000
Withdraw 20,000 → Insufficient balance!
Current Balance: 12,000
```

---

### 🔴 Advanced

**Problem 26.** Write a program that meets the following requirements.

> Use recursion to find the **GCD (Greatest Common Divisor)** of two numbers (Euclidean algorithm).
> Also calculate **LCM (Least Common Multiple)** (Formula: `LCM = a × b ÷ GCD`)

Output example:

```
=== GCD / LCM Calculator ===
a = 48, b = 18
GCD(48, 18) = 6
LCM(48, 18) = 144

a = 100, b = 35
GCD(100, 35) = 5
LCM(100, 35) = 700
```

---

---

# 🔑 Answer Key and Explanations

---

## 📝 Multiple Choice Answers

---

### 🟢 Beginner

**Problem 1. Answer: ③ 30**

Returning `10, 20` automatically creates a tuple `(10, 20)`. Unpacking with `a, b = get_values()` gives `a=10`, `b=20`. `10 + 20 = 30`.

---

**Problem 2. Answer: ② Local variable**

A variable created inside a function is a **local variable**, accessible only within that function. It ceases to exist when the function ends.

---

**Problem 3. Answer: ③ 100**

Reading a global variable **without modification** doesn't need `global` declaration. Since `x = 100` is global, the function reads and prints 100.

---

**Problem 4. Answer: ① `lambda x: x * 2`**

Lambda syntax is `lambda parameters: expression`. No parentheses around parameters; the colon is followed by the return expression.

---

**Problem 5. Answer: ② 10**

`double = lambda x: x * 2` with `double(5)` returns `5 * 2 = 10`.

---

**Problem 6. Answer: ③ Base case (terminating condition)**

Without a base case, recursive functions call themselves infinitely, causing `RecursionError`.

---

**Problem 7. Answer: ③ 24**

`factorial(4) = 4 × factorial(3) = 4 × 3 × factorial(2) = 4 × 3 × 2 × factorial(1) = 4 × 3 × 2 × 1 = 24`.

---

### 🟡 Intermediate

**Problem 8. Answer: ② global**

To **modify** a global variable inside a function, declare `global variable_name`. Without it, a new local variable with the same name is created.

---

**Problem 9. Answer: ③ 3**

`global count` uses the global variable, so calling `increment()` three times changes `count` from 0 → 1 → 2 → 3.

---

**Problem 10. Answer: ② 21**

`lambda a, b: a * b` with `multiply(3, 7)` returns `3 × 7 = 21`.

---

**Problem 11. Answer: ③ 10**

`func(4) = 4 + func(3) = 4 + 3 + func(2) = 4 + 3 + 2 + func(1) = 4 + 3 + 2 + 1 + func(0) = 4 + 3 + 2 + 1 + 0 = 10`.

---

**Problem 12. Answer: ③ 20 / 10**

The `x = 20` inside the function is a **local variable** (no `global` declaration). Global `x = 10` remains unchanged. Inside function: 20, outside: 10.

---

### 🔴 Advanced

**Problem 13. Answer: ① Total: 240, Average: 80.0**

`80 + 90 + 70 = 240`, `240 / 3 = 80.0`. Multiple return values unpack into `t, a`.

---

**Problem 14. Answer: ② 8**

Fibonacci sequence: F(0)=0, F(1)=1, F(2)=1, F(3)=2, F(4)=3, F(5)=5, F(6)=8. `fibonacci(6) = fibonacci(5) + fibonacci(4) = 5 + 3 = 8`.

---

**Problem 15. Answer: ③ Recursion uses less memory than loops**

This is **FALSE**. Recursion creates stack frames for each call, using **more memory** than loops.

---

## 📝 Short Answer Key

---

### 🟢 Beginner

**Problem 16. Model Answer:**

**Local variable:** Created **inside** a function. Accessible only within that function; destroyed when the function ends.

```python
def func():
    local_var = 10       # local variable
    print(local_var)     # OK: usable inside function

func()
# print(local_var)       # Error: not accessible outside
```

**Global variable:** Created **outside** (top-level of program). Accessible throughout the program.

```python
global_var = 100         # global variable

def func():
    print(global_var)    # OK: readable inside function

func()                   # 100
print(global_var)        # 100
```

---

**Problem 17. Model Answer:**

```
x=20, y=10
```

`swap(10, 20)` returns `b, a` which is `20, 10`. Unpacking into `x, y` gives `x=20`, `y=10`.

---

**Problem 18. Model Answer:**

**Lambda function:** Unnamed, one-line function using `lambda` keyword. Use for simple operations without complex logic.

```python
# lambda function
add_lambda = lambda x, y: x + y

# equivalent regular function
def add(x, y):
    return x + y

print(add_lambda(3, 5))  # 8
print(add(3, 5))          # 8
```

---

### 🟡 Intermediate

**Problem 19. Model Answer:**

Output:

```
80
170
Final: 170
```

**Process:**

- `add_score(80)`: `total = 0 + 80 = 80` → returns and prints 80
- `add_score(90)`: `total = 80 + 90 = 170` → returns and prints 170
- `total` is global, so it's 170 outside the function

**Why `global` is needed:** Without `global`, Python treats `total` as a local variable. But `+=` does read-then-write, so reading an unassigned local variable causes `UnboundLocalError`.

---

**Problem 20. Model Answer:**

Output:

```
15
```

**Recursive call process:**

```
sum_recursive(5)
= 5 + sum_recursive(4)
= 5 + 4 + sum_recursive(3)
= 5 + 4 + 3 + sum_recursive(2)
= 5 + 4 + 3 + 2 + sum_recursive(1)
= 5 + 4 + 3 + 2 + 1    ← base case (n=1 → return 1)
= 15
```

The base case `n=1` returns 1; values accumulate as recursion unwinds, giving final 15.

---

### 🔴 Advanced

**Problem 21. Model Answer:**

Output:

```
256
256
```

**Recursive approach** (`power_recursive`):

```
power_recursive(2, 8)
= 2 × power_recursive(2, 7)
= 2 × 2 × power_recursive(2, 6)
= ... (8 levels)
= 2 × 2 × 2 × 2 × 2 × 2 × 2 × 2 × 1
= 256
```

Reaches base case `exp == 0` returning 1; multiplies `base` 8 times as unwinding. Creates 9 function calls (9 stack frames).

**Loop approach** (`power_loop`):
`result` multiplies by `base` 8 times with no function calls. More memory-efficient.

Both produce 256, but loops are faster and use less memory.

---

## 💻 Hands-On Solutions

---

### 🟢 Beginner

**Problem 22. Model Answer:**

```python
def calc(a, b):
    return a + b, a - b, a * b

s, d, p = calc(10, 3)
print(f"calc(10, 3):")
print(f"Sum: {s}, Difference: {d}, Product: {p}")
```

Key point: Multiple values returned with commas; unpack into multiple variables on call.

---

**Problem 23. Model Answer:**

```python
c_to_f = lambda c: c * 1.8 + 32

print(f"0°C = {c_to_f(0)}°F")
print(f"100°C = {c_to_f(100)}°F")
print(f"36.5°C = {c_to_f(36.5)}°F")
```

Key point: One-line `lambda` converts Celsius to Fahrenheit efficiently.

---

**Problem 24. Model Answer:**

```python
def countdown(n):
    if n <= 0:
        print("Blast off!")
    else:
        print(n)
        countdown(n - 1)

countdown(5)
```

Key point: Base case (`n <= 0`) prints "Blast off!" and stops recursion. Otherwise, print `n` and recurse with `n-1`.

---

### 🟡 Intermediate

**Problem 25. Model Answer:**

```python
balance = 10000

def deposit(amount):
    global balance
    balance += amount
    print(f"Deposit {amount:,} → Balance: {balance:,}")

def withdraw(amount):
    global balance
    if amount > balance:
        print(f"Withdraw {amount:,} → Insufficient balance!")
    else:
        balance -= amount
        print(f"Withdraw {amount:,} → Balance: {balance:,}")

def check_balance():
    print(f"Current Balance: {balance:,}")

# Test
check_balance()
deposit(5000)
withdraw(3000)
withdraw(20000)
check_balance()
```

Key points:

- `global balance` modifies the global variable in each function.
- `withdraw` checks balance before deducting.

---

### 🔴 Advanced

**Problem 26. Model Answer:**

```python
def gcd(a, b):
    if b == 0:
        return a
    return gcd(b, a % b)

def lcm(a, b):
    return a * b // gcd(a, b)

# Test
print("=== GCD / LCM Calculator ===")

a, b = 48, 18
print(f"a = {a}, b = {b}")
print(f"GCD({a}, {b}) = {gcd(a, b)}")
print(f"LCM({a}, {b}) = {lcm(a, b)}")

print()

a, b = 100, 35
print(f"a = {a}, b = {b}")
print(f"GCD({a}, {b}) = {gcd(a, b)}")
print(f"LCM({a}, {b}) = {lcm(a, b)}")
```

Key points:

- **Euclidean Algorithm**: `gcd(a, b)` = `gcd(b, a%b)`, stopping when `b=0` (then `a` is GCD).
- Process: `gcd(48, 18)` → `gcd(18, 12)` → `gcd(12, 6)` → `gcd(6, 0)` → 6
- **LCM formula**: `a × b ÷ GCD`. `48 × 18 ÷ 6 = 144`.
- Use `//` for integer division.
- Verify: `gcd(100, 35)` → 5, `lcm = 100 × 35 ÷ 5 = 700`.

---


Thank you for your attention.   
Cho Jeonghyun ([peterchokr@gmail.com](mailto:peterchokr@gmail.com)). Yeungnam University College

"Produced in collaboration with Claude and Gemini."
