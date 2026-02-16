# Chapter 15: Exception Handling — Practice Problems

---

## 📝 Multiple Choice Questions

---

### 🟢 Beginner

**Problem 1.** What is the correct keyword combination for exception handling in Python?

① `try-catch`  
② `try-except`  
③ `if-else`  
④ `begin-rescue`  

---

**Problem 2.** What exception is raised when executing `int("abc")`?

```python
number = int("abc")
```

① `TypeError`  
② `ValueError`  
③ `IndexError`  
④ `KeyError`  

---

**Problem 3.** What is the output of the following code?

```python
try:
    print("Start")
    x = 10 / 0
    print("End")
except ZeroDivisionError:
    print("Error")
print("Continue")
```

① Start → End → Continue  
② Start → Error → Continue  
③ Error → Continue  
④ Start → Error  

---

**Problem 4.** What exception is raised when opening a non-existent file in read mode?

① `ValueError`  
② `IOError`  
③ `FileNotFoundError`  
④ `PermissionError`  

---

**Problem 5.** What is the output of the following code? (Input: `abc`)

```python
try:
    num = int(input("Number: "))
    print(num * 2)
except ValueError:
    print("Error!")
```

① `abc2`  
② `Error!`  
③ Program terminates  
④ `abc`  

---

**Problem 6.** What is the output of the following code?

```python
try:
    fruits = ["apple", "banana"]
    print(fruits[5])
except IndexError:
    print("Index out of range")
print("Done")
```

① `Index out of range`  
② `Index out of range` → `Done`  
③ Program terminates  
④ `Done`  

---

**Problem 7.** Which is **NOT** an appropriate use of `try-except`?

① Getting number input from user  
② Opening and reading a file  
③ Calculating `1 + 2` (simple addition)  
④ Converting string to integer  

---

### 🟡 Intermediate

**Problem 8.** What is the output of the following code?

```python
try:
    x = 10 / 2
    print(x)
except ZeroDivisionError:
    print("Error")
finally:
    print("Finally")
```

① `5.0`  
② `Error` → `Finally`  
③ `5.0` → `Finally`  
④ `Finally`  

---

**Problem 9.** What is the output when executing the following code?

```python
try:
    num = int("123abc")
except ValueError:
    print("ValueError")
except TypeError:
    print("TypeError")
```

① `ValueError`  
② `TypeError`  
③ Both printed  
④ Program terminates  

---

**Problem 10.** What exception is raised in the following code?

```python
try:
    d = {"a": 1, "b": 2}
    value = d["c"]
except KeyError:
    print("KeyError")
```

① `ValueError`  
② `IndexError`  
③ `KeyError`  
④ `TypeError`  

---

**Problem 11.** What is the purpose of `raise` statement?

① **Manually raise an exception**  
② Catch an exception  
③ Exit the program  
④ Define a new exception  

---

**Problem 12.** What happens when `except Exception:` is used?

① Catches **all exceptions**  
② Catches only `ValueError`  
③ Catches only syntax errors  
④ Must specify exception type  

---

### 🔴 Advanced

**Problem 13.** What is the output of the following code?

```python
try:
    try:
        x = 1 / 0
    except ValueError:
        print("ValueError")
except ZeroDivisionError:
    print("ZeroDivisionError")
```

① `ValueError`  
② `ZeroDivisionError`  
③ Both printed  
④ Program terminates  

---

**Problem 14.** What is the correct way to handle multiple exceptions?

```python
try:
    x = int(input("Number: "))
    y = [1, 2, 3][x]
except (ValueError, IndexError):
    print("Invalid input or index")
```

① Incorrect syntax  
② Tuple of exceptions  
③ Catches multiple exceptions  
④ Error expected  

---

**Problem 15.** What is the output of the following code?

```python
try:
    print("Start")
    raise ValueError("Custom error")
except ValueError as e:
    print(f"Caught: {e}")
finally:
    print("Cleanup")
```

① `Start` → `Caught: Custom error` → `Cleanup`  
② `Start` → `Caught: Custom error`  
③ `Start` → `Cleanup`  
④ Program terminates  

---

## 📝 Short Answer Questions

---

### 🟢 Beginner

**Problem 16.** Explain the purpose of `try-except` block and give an example of when it's useful.

---

**Problem 17.** What is the difference between `except ValueError:` and `except Exception:`? Explain with examples.

```python
# Example 1
try:
    num = int("abc")
except ValueError:
    print("ValueError caught")

# Example 2
try:
    num = int("abc")
except Exception:
    print("Any exception caught")
```

---

**Problem 18.** Explain the purpose of the `finally` block and when it executes.

```python
try:
    print("Try block")
    x = 10 / 0
except ZeroDivisionError:
    print("Except block")
finally:
    print("Finally block")
```

---

### 🟡 Intermediate

**Problem 19.** What is the purpose of `raise` statement? Write code to raise a custom error.

```python
def divide(a, b):
    if b == 0:
        raise ValueError("Divisor cannot be zero")
    return a / b

try:
    result = divide(10, 0)
except ValueError as e:
    print(f"Error: {e}")
```

---

**Problem 20.** Explain nested try-except blocks and write code to handle multiple exceptions.

```python
try:
    try:
        num = int(input("Number: "))
        result = 10 / num
    except ValueError:
        print("Invalid number")
except ZeroDivisionError:
    print("Cannot divide by zero")
```

---

### 🔴 Advanced

**Problem 21.** Write code to handle file operations with proper exception handling.

```python
try:
    with open("data.txt", "r") as f:
        data = f.read()
        num = int(data)
except FileNotFoundError:
    print("File not found")
except ValueError:
    print("Invalid data in file")
except Exception as e:
    print(f"Unknown error: {e}")
finally:
    print("Operation complete")
```

---

## 💻 Hands-On Problems

---

### 🟢 Beginner

**Problem 22.** Write a program that converts user input to integer with error handling.

> Get 5 numbers from user, handle invalid input, and show sum.

Output example:

```
=== Sum Calculator ===
Enter number 1: abc
Invalid input! Please enter a number.
Enter number 1: 10
Enter number 2: 20
Enter number 3: not a number
Invalid input! Please enter a number.
Enter number 3: 30
Enter number 4: 15
Enter number 5: 25

Total: 100
```

---

**Problem 23.** Write a program that handles file operations with error messages.

> Create a file, read it, and handle FileNotFoundError.

Output example:

```
=== File Manager ===
Created file: students.txt
Added: John
Added: Jane
Added: Mike

Reading file...
1. John
2. Jane
3. Mike

Total students: 3
```

---

### 🟡 Intermediate

**Problem 24.** Write a program to validate user input and handle exceptions.

> Get student grades, validate range (0-100), and calculate statistics.

Output example:

```
=== Grade System ===
Enter 5 grades (0-100):
Grade 1: 150
Invalid! Must be 0-100.
Grade 1: 85
Grade 2: 92
Grade 3: -5
Invalid! Must be 0-100.
Grade 3: 78
Grade 4: abc
Invalid input!
Grade 4: 88
Grade 5: 95

Average: 87.6
Highest: 95
Lowest: 78
```

---

**Problem 25.** Write a program that processes CSV data with error handling.

> Read CSV, handle missing files and invalid data, calculate statistics.

Output example:

```
=== CSV Processor ===
Processing products.csv...
ProductA: $25
ProductB: $45
ProductC: $30

Total Products: 3
Total Value: $100
Average Price: $33.33

File processed successfully
```

---

### 🔴 Advanced

**Problem 26.** Write a comprehensive error handling system for a student management application.

> Manage student database with full error handling for all operations.

Output example:

```
=== Student Management System ===

1. Add Student
2. View Scores
3. Calculate GPA
4. Search Student
5. Exit

[Option 1: Add Student]
Name: John
ID: S001
Enter 3 grades: 85 92 88
Added successfully

[Option 2: View Scores]
John: 85, 92, 88 (Average: 88.3)

[Option 3: Calculate GPA]
Student ID: S002
Student not found!

[Option 4: Search]
Search name: Jane
Found: Jane (S002)

All operations with proper error handling
- FileNotFoundError
- ValueError
- KeyError
- Custom validation errors
```

---
---

# 🔑 Answer Key and Explanations

---

## 📝 Multiple Choice Answers

---

### 🟢 Beginner

**Problem 1. Answer: ② `try-except`**

Python uses `try-except` (not `try-catch` which is used in Java/JavaScript).

---

**Problem 2. Answer: ② `ValueError`**

`int("abc")` cannot convert non-numeric string, raises `ValueError`.

---

**Problem 3. Answer: ② Start → Error → Continue**

Exception occurs at `10 / 0`, caught by except block, then continues after try-except.

---

**Problem 4. Answer: ③ `FileNotFoundError`**

Python raises `FileNotFoundError` when file doesn't exist in read mode.

---

**Problem 5. Answer: ② `Error!`**

`int("abc")` raises `ValueError`, caught and prints "Error!".

---

**Problem 6. Answer: ② `Index out of range` → `Done`**

Index 5 doesn't exist, `IndexError` caught, then "Done" prints.

---

**Problem 7. Answer: ③ Calculating `1 + 2`**

Simple arithmetic doesn't need exception handling. Others do.

---

### 🟡 Intermediate

**Problem 8. Answer: ③ `5.0` → `Finally`**

No exception, so except skipped. Finally always executes.

---

**Problem 9. Answer: ① `ValueError`**

`int("123abc")` raises `ValueError` (not TypeError), first except catches it.

---

**Problem 10. Answer: ③ `KeyError`**

Accessing non-existent dictionary key raises `KeyError`.

---

**Problem 11. Answer: ① Manually raise an exception**

`raise` statement explicitly raises an exception.

---

**Problem 12. Answer: ① Catches all exceptions**

`except Exception:` is a catch-all for any exception.

---

### 🔴 Advanced

**Problem 13. Answer: ② `ZeroDivisionError`**

Inner except doesn't catch `ZeroDivisionError`, outer except does.

---

**Problem 14. Answer: ③ Catches multiple exceptions**

`except (ValueError, IndexError):` catches both exception types.

---

**Problem 15. Answer: ① `Start` → `Caught: Custom error` → `Cleanup`**

Raise caught, message printed, finally executes.

---

## 📝 Short Answer Key

---

### 🟢 Beginner

**Problem 16. Model Answer:**

**Purpose:** Prevent program crash by handling errors gracefully.

**Useful when:**
- Converting user input
- Opening files
- Accessing list/dict elements
- Mathematical operations (division)

---

**Problem 17. Model Answer:**

- **`except ValueError:`** Catches only `ValueError`
- **`except Exception:`** Catches ALL exceptions (too broad)

Better practice: catch specific exceptions.

---

**Problem 18. Model Answer:**

**Purpose:** Cleanup code that must execute (file closing, resource release).

**Output:**
```
Try block
Except block
Finally block
```

Finally executes regardless of exception.

---

### 🟡 Intermediate

**Problem 19. Model Answer:**

`raise` raises exceptions manually for validation/error conditions.

**Output:**
```
Error: Divisor cannot be zero
```

---

**Problem 20. Model Answer:**

Nested try-except handles multiple error types at different levels.

---

### 🔴 Advanced

**Problem 21. Model Answer:**

Handles:
- `FileNotFoundError` (file missing)
- `ValueError` (invalid data)
- Generic exceptions
- Cleanup in finally

---

## 💻 Hands-On Solutions

---

### 🟢 Beginner

**Problem 22. Model Answer:**

```python
total = 0
count = 0

print("=== Sum Calculator ===")
while count < 5:
    try:
        num = int(input(f"Enter number {count + 1}: "))
        total = total + num
        count = count + 1
    except ValueError:
        print("Invalid input! Please enter a number.")

print(f"\nTotal: {total}")
```

---

**Problem 23. Model Answer:**

```python
print("=== File Manager ===")

try:
    # Write file
    with open("students.txt", "w") as f:
        students = ["John", "Jane", "Mike"]
        for s in students:
            f.write(s + "\n")
    
    # Read and display
    with open("students.txt", "r") as f:
        lines = f.readlines()
    
    print("Reading file...")
    for i, line in enumerate(lines, 1):
        print(f"{i}. {line.strip()}")
    
    print(f"\nTotal students: {len(lines)}")

except FileNotFoundError:
    print("File not found!")
except Exception as e:
    print(f"Error: {e}")
```

---

### 🟡 Intermediate

**Problem 24. Model Answer:**

```python
grades = []
count = 0

print("=== Grade System ===")
print("Enter 5 grades (0-100):")

while count < 5:
    try:
        grade = int(input(f"Grade {count + 1}: "))
        if grade < 0 or grade > 100:
            print("Invalid! Must be 0-100.")
            continue
        grades.append(grade)
        count = count + 1
    except ValueError:
        print("Invalid input!")

average = sum(grades) / len(grades)
print(f"\nAverage: {average:.1f}")
print(f"Highest: {max(grades)}")
print(f"Lowest: {min(grades)}")
```

---

**Problem 25. Model Answer:**

```python
print("=== CSV Processor ===")
print("Processing products.csv...")

try:
    with open("products.csv", "w") as f:
        f.write("ProductA,25\n")
        f.write("ProductB,45\n")
        f.write("ProductC,30\n")
    
    products = []
    with open("products.csv", "r") as f:
        lines = f.readlines()
        for line in lines:
            parts = line.strip().split(",")
            name = parts[0]
            price = int(parts[1])
            products.append((name, price))
            print(f"{name}: ${price}")
    
    total = sum(p[1] for p in products)
    average = total / len(products)
    
    print(f"\nTotal Products: {len(products)}")
    print(f"Total Value: ${total}")
    print(f"Average Price: ${average:.2f}")
    print("\nFile processed successfully")

except FileNotFoundError:
    print("File not found!")
except ValueError:
    print("Invalid data in file!")
except Exception as e:
    print(f"Error: {e}")
```

---

### 🔴 Advanced

**Problem 26. Model Answer:**

```python
student_db = {}

def add_student():
    try:
        name = input("Name: ")
        sid = input("ID: ")
        grades_input = input("Enter 3 grades: ")
        grades = [int(g) for g in grades_input.split()]
        if len(grades) != 3:
            print("Please enter exactly 3 grades!")
            return
        student_db[sid] = {"name": name, "grades": grades}
        print("Added successfully")
    except ValueError:
        print("Invalid input!")

def view_scores():
    try:
        sid = input("Student ID: ")
        if sid not in student_db:
            print("Student not found!")
            return
        s = student_db[sid]
        grades = s["grades"]
        avg = sum(grades) / len(grades)
        print(f"{s['name']}: {', '.join(map(str, grades))} (Average: {avg:.1f})")
    except Exception as e:
        print(f"Error: {e}")

def calculate_gpa():
    try:
        sid = input("Student ID: ")
        if sid not in student_db:
            print("Student not found!")
            return
        grades = student_db[sid]["grades"]
        avg = sum(grades) / len(grades)
        if avg >= 90:
            gpa = 4.0
        elif avg >= 80:
            gpa = 3.0
        elif avg >= 70:
            gpa = 2.0
        else:
            gpa = 0.0
        print(f"GPA: {gpa:.2f}")
    except KeyError:
        print("Student not found!")
    except Exception as e:
        print(f"Error: {e}")

def search_student():
    try:
        name = input("Search name: ")
        for sid, data in student_db.items():
            if data["name"] == name:
                print(f"Found: {data['name']} ({sid})")
                return
        print("Not found!")
    except Exception as e:
        print(f"Error: {e}")

while True:
    print("\n=== Student Management System ===")
    print("1. Add Student")
    print("2. View Scores")
    print("3. Calculate GPA")
    print("4. Search Student")
    print("5. Exit")
    
    choice = input("Option: ")
    
    try:
        if choice == "1":
            add_student()
        elif choice == "2":
            view_scores()
        elif choice == "3":
            calculate_gpa()
        elif choice == "4":
            search_student()
        elif choice == "5":
            print("Goodbye!")
            break
        else:
            print("Invalid option!")
    except Exception as e:
        print(f"Error: {e}")
```

---

Professor Cho Jeonghyun (peterchokr@gmail.com)  
Yeungnam University College.
