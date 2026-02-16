# Chapter 16: Modules and Packages — Practice Problems

---

## 📝 Multiple Choice Questions

---

### 🟢 Beginner

**Problem 1.** What is the keyword to import a module in Python?

① `include`  
② `require`  
③ `import`  
④ `load`  

---

**Problem 2.** Which statement about modules is correct?

① Can only be used in Python  
② **Collection of functions and variables in a `.py` file**  
③ Must contain a class  
④ Cannot be modified after import  

---

**Problem 3.** What is the output of the following code?

```python
import math
print(math.sqrt(25))
```

① `25`  
② `5`  
③ `5.0`  
④ Error  

---

**Problem 4.** After executing `from math import pi`, the correct way to use `pi` is:

① `math.pi`  
② `pi`  
③ `import.pi`  
④ `from.pi`  

---

**Problem 5.** Which is the correct import syntax?

① `import math.pi`  
② `from math import pi`  
③ `import pi from math`  
④ `get pi from math`  

---

**Problem 6.** What values can `random.randint(1, 6)` return?

① 1 to 5  
② 1 to 5  
③ **1 to 6 (inclusive)**  
④ 0 to 5  

---

**Problem 7.** What is the output of the following code?

```python
import math as m
print(m.factorial(4))
```

① `4`  
② `10`  
③ `24`  
④ Error  

---

### 🟡 Intermediate

**Problem 8.** After `from math import sqrt as s`, what is the result of `s(16)`?

① Error  
② `s(16)`  
③ `4.0`  
④ `16`  

---

**Problem 9.** When is `__name__ == "__main__"` `True`?

① When module is imported  
② **When module is run directly**  
③ When module has errors  
④ When module is created  

---

**Problem 10.** What is the output of the following code?

```python
from datetime import datetime
now = datetime.now()
print(type(now).__name__)
```

① `str`  
② `datetime`  
③ `date`  
④ `time`  

---

**Problem 11.** What file must be in a package folder?

① `__main__.py`  
② `__init__.py`  
③ `__package__.py`  
④ `index.py`  

---

**Problem 12.** What is the possible result of `random.choice(["A", "B", "C"])`?

① `["A", "B", "C"]`  
② **One of `"A"`, `"B"`, or `"C"`**  
③ Always `"A"`  
④ One of `0`, `1`, `2`  

---

### 🔴 Advanced

**Problem 13.** Why won't the test code run when importing `calculator.py`?

```python
# calculator.py
def add(a, b):
    return a + b

if __name__ == "__main__":
    print(f"Test: {add(1, 2)}")
```

① Condition is always `False`  
② **`__name__` is module name, not `"__main__"`**  
③ `add()` function doesn't work  
④ Error in the code  

---

**Problem 14.** What does `dir(math)` return?

① Deletes the module  
② **Lists all attributes and methods of math**  
③ Gets module directory path  
④ Reloads the module  

---

**Problem 15.** What is the difference between `import math` and `from math import sqrt`?

① No difference  
② **First: use `math.sqrt()`, Second: use `sqrt()` directly**  
③ First is faster  
④ Second is more secure  

---

## 📝 Short Answer Questions

---

### 🟢 Beginner

**Problem 16.** Explain what a module is and give examples of built-in modules you know.

---

**Problem 17.** Write the output of the following code and explain what each import does.

```python
import math
from math import pi
from math import sqrt as square_root

print(math.pi)
print(pi)
print(square_root(16))
```

---

**Problem 18.** Explain `__name__ == "__main__"` and why it's useful.

```python
def greet(name):
    print(f"Hello, {name}!")

if __name__ == "__main__":
    greet("John")
```

---

### 🟡 Intermediate

**Problem 19.** Explain the purpose of `__init__.py` file and package structure.

```
my_package/
    __init__.py
    module1.py
    module2.py
```

---

**Problem 20.** What is the difference between `import time` and `from time import time`? Show with code.

---

### 🔴 Advanced

**Problem 21.** Write code to create a custom module and explain how to use it.

```python
# math_utils.py
def add(a, b):
    """Add two numbers"""
    return a + b

def subtract(a, b):
    """Subtract two numbers"""
    return a - b

if __name__ == "__main__":
    print(f"Testing: {add(5, 3)}")
```

---

## 💻 Hands-On Problems

---

### 🟢 Beginner

**Problem 22.** Write a program using `random` module to simulate a dice roll game.

> Roll a dice 5 times and show results with sum.

Output example:

```
=== Dice Roll Game ===
Roll 1: 4
Roll 2: 1
Roll 3: 6
Roll 4: 3
Roll 5: 5

Total: 19
Average: 3.8
```

---

**Problem 23.** Write a program using `math` module to calculate circle properties.

> Input radius, calculate area and circumference.

Output example:

```
=== Circle Calculator ===
Enter radius: 5

Radius: 5
Diameter: 10
Circumference: 31.42
Area: 78.54
```

---

### 🟡 Intermediate

**Problem 24.** Write a program using `datetime` module to show date/time information.

> Display current date/time and calculate days until next birthday.

Output example:

```
=== Date & Time Info ===
Current date: 2026-02-14
Current time: 14:30:45
Day of week: Saturday

Birthday: 2026-06-15
Days until birthday: 121 days
```

---

**Problem 25.** Write a program that generates random passwords with requirements.

> Generate 5 random passwords (8 chars, mix of letters and numbers).

Output example:

```
=== Password Generator ===
Generated Passwords:
1. aB3dEfGh
2. 1cD5eF7g
3. Hk9lMnO2
4. pQ1rS3tU
5. vW5xY7zA

All passwords meet requirements
```

---

### 🔴 Advanced

**Problem 26.** Create a custom statistics module and use it in a program.

> Create statistics module with mean, median, std_dev functions, then use it.

Output example:

```
=== Statistics Module ===

Data: [10, 20, 30, 40, 50, 60, 70]

Mean: 40.0
Median: 40
Standard Deviation: 20.82

Data: [85, 92, 78, 88, 95]

Mean: 87.6
Median: 88
Standard Deviation: 6.55
```

---
---

# 🔑 Answer Key and Explanations

---

## 📝 Multiple Choice Answers

---

### 🟢 Beginner

**Problem 1. Answer: ③ `import`**

Python uses `import` keyword (not `include` which is C/C++).

---

**Problem 2. Answer: ② Collection of functions and variables in a `.py` file**

Module is any `.py` file with reusable code.

---

**Problem 3. Answer: ③ `5.0`**

`math.sqrt(25)` returns `5.0` (float).

---

**Problem 4. Answer: ② `pi`**

After `from math import pi`, use `pi` directly, not `math.pi`.

---

**Problem 5. Answer: ② `from math import pi`**

Correct Python syntax for importing specific items.

---

**Problem 6. Answer: ③ 1 to 6 (inclusive)**

`randint(1, 6)` includes both endpoints.

---

**Problem 7. Answer: ③ `24`**

`factorial(4) = 4 × 3 × 2 × 1 = 24`.

---

### 🟡 Intermediate

**Problem 8. Answer: ③ `4.0`**

Alias works same as function. `s(16) = 4.0`.

---

**Problem 9. Answer: ② When module is run directly**

`__name__` is `"__main__"` only when script runs directly.

---

**Problem 10. Answer: ② `datetime`**

`type()` returns datetime class.

---

**Problem 11. Answer: ② `__init__.py`**

This file marks folder as package.

---

**Problem 12. Answer: ② One of `"A"`, `"B"`, or `"C"`**

`choice()` returns random element from list.

---

### 🔴 Advanced

**Problem 13. Answer: ② `__name__` is module name, not `"__main__"`**

When imported, `__name__` is module name "calculator", not "__main__".

---

**Problem 14. Answer: ② Lists all attributes and methods of math**

`dir()` shows available items in module.

---

**Problem 15. Answer: ② First: use `math.sqrt()`, Second: use `sqrt()` directly**

`import math`: access as `math.sqrt()`  
`from math import sqrt`: access as `sqrt()`

---

## 📝 Short Answer Key

---

### 🟢 Beginner

**Problem 16. Model Answer:**

Module = `.py` file with reusable code.

Built-in modules: `math`, `random`, `datetime`, `os`, `sys`, `json`

---

**Problem 17. Model Answer:**

**Output:**
```
3.141592653589793
3.141592653589793
4.0
```

- `import math`: access as `math.pi`
- `from math import pi`: use `pi` directly
- `as square_root`: alias for shorter name

---

**Problem 18. Model Answer:**

Prevents code from running when module imported.

**Output:**
```
Hello, John!
```

(Only when run directly, not when imported)

---

### 🟡 Intermediate

**Problem 19. Model Answer:**

`__init__.py` marks folder as package. Allows importing modules from folder.

---

**Problem 20. Model Answer:**

- `import time`: use `time.time()`
- `from time import time`: use `time()` directly

---

### 🔴 Advanced

**Problem 21. Model Answer:**

Save as `math_utils.py`, import with `from math_utils import add`.

---

## 💻 Hands-On Solutions

---

### 🟢 Beginner

**Problem 22. Model Answer:**

```python
import random

print("=== Dice Roll Game ===")
rolls = []
for i in range(5):
    roll = random.randint(1, 6)
    rolls.append(roll)
    print(f"Roll {i + 1}: {roll}")

total = sum(rolls)
average = total / len(rolls)

print(f"\nTotal: {total}")
print(f"Average: {average:.1f}")
```

---

**Problem 23. Model Answer:**

```python
import math

print("=== Circle Calculator ===")
radius = int(input("Enter radius: "))

diameter = radius * 2
circumference = 2 * math.pi * radius
area = math.pi * radius ** 2

print(f"\nRadius: {radius}")
print(f"Diameter: {diameter}")
print(f"Circumference: {circumference:.2f}")
print(f"Area: {area:.2f}")
```

---

### 🟡 Intermediate

**Problem 24. Model Answer:**

```python
from datetime import datetime, date

now = datetime.now()
today = date.today()

print("=== Date & Time Info ===")
print(f"Current date: {today}")
print(f"Current time: {now.strftime('%H:%M:%S')}")
print(f"Day of week: {now.strftime('%A')}")

# Birthday example
birthday = date(2026, 6, 15)
days_left = (birthday - today).days

print(f"\nBirthday: {birthday}")
print(f"Days until birthday: {days_left} days")
```

---

**Problem 25. Model Answer:**

```python
import random
import string

print("=== Password Generator ===")
print("Generated Passwords:")

for i in range(5):
    password = ""
    for j in range(8):
        if j % 2 == 0:
            password = password + random.choice(string.ascii_letters)
        else:
            password = password + str(random.randint(0, 9))
    print(f"{i + 1}. {password}")

print("\nAll passwords meet requirements")
```

---

### 🔴 Advanced

**Problem 26. Model Answer:**

```python
# statistics_module.py
import math

def mean(data):
    return sum(data) / len(data)

def median(data):
    sorted_data = sorted(data)
    n = len(sorted_data)
    if n % 2 == 1:
        return sorted_data[n // 2]
    else:
        return (sorted_data[n // 2 - 1] + sorted_data[n // 2]) / 2

def std_dev(data):
    m = mean(data)
    variance = sum((x - m) ** 2 for x in data) / len(data)
    return math.sqrt(variance)

if __name__ == "__main__":
    print("=== Statistics Module ===")
    
    data1 = [10, 20, 30, 40, 50, 60, 70]
    print(f"\nData: {data1}")
    print(f"Mean: {mean(data1):.1f}")
    print(f"Median: {median(data1)}")
    print(f"Standard Deviation: {std_dev(data1):.2f}")
    
    data2 = [85, 92, 78, 88, 95]
    print(f"\nData: {data2}")
    print(f"Mean: {mean(data2):.1f}")
    print(f"Median: {median(data2)}")
    print(f"Standard Deviation: {std_dev(data2):.2f}")
```

---

Professor Cho Jeonghyun (peterchokr@gmail.com)  
Yeungnam University College.
