# Chapter 14: File Input/Output — Practice Problems

---

## 📝 Multiple Choice Questions

---

### 🟢 Beginner

**Problem 1.** Which is the correct code to open a file in **write mode**?

① `open("file.txt", "r")`  
② `open("file.txt", "w")`  
③ `open("file.txt", "a")`  
④ `open("file.txt", "d")`  

---

**Problem 2.** Why is the `with` statement used to open files?

① Reads files faster  
② **Automatically closes the file**  
③ Encrypts the file  
④ Reduces file size  

---

**Problem 3.** What does file mode `"a"` do?

① Reads the file  
② **Overwrites** existing content with new content  
③ **Keeps** existing content and **appends** to the end  
④ Deletes the file  

---

**Problem 4.** What is in the file after this code executes?

```python
with open("test.txt", "w") as f:
    f.write("Hello")
    f.write("World")
```

① `Hello World`  
② `HelloWorld`  
③ `Hello\nWorld`  
④ Error  

---

**Problem 5.** Which method reads all lines as a **list**?

① `read()`  
② `readline()`  
③ `readlines()`  
④ `readall()`  

---

**Problem 6.** What does `encoding="utf-8"` do in this code?

```python
with open("file.txt", "w", encoding="utf-8") as f:
    f.write("Hello")
```

① Compresses the file  
② **Handles Korean correctly**  
③ Encrypts the file  
④ Reduces file size  

---

**Problem 7.** What happens when opening a non-existent file in `"r"` mode?

① A new empty file is created  
② Returns `None`  
③ **Raises `FileNotFoundError` error**  
④ Returns empty string  

---

### 🟡 Intermediate

**Problem 8.** What is in `test.txt` after executing this code?

```python
with open("test.txt", "w") as f:
    f.write("First\n")

with open("test.txt", "w") as f:
    f.write("Second\n")
```

① `First\nSecond\n`  
② `Second\n`  
③ File not found  
④ Error  

---

**Problem 9.** What is in `test.txt` after executing this code?

```python
with open("test.txt", "w") as f:
    f.write("First\n")

with open("test.txt", "a") as f:
    f.write("Second\n")
```

① `First\nSecond\n`  
② `Second\n`  
③ `First\n`  
④ Error  

---

**Problem 10.** What is the output of the following code?

```python
with open("test.txt", "w") as f:
    f.write("line1\nline2\nline3\n")

with open("test.txt", "r") as f:
    lines = f.readlines()
print(len(lines))
```

① 1  
② 3  
③ 11  
④ Error  

---

**Problem 11.** What is the output of the following code?

```python
with open("test.txt", "w") as f:
    f.write("line1\nline2\nline3\n")

with open("test.txt", "r") as f:
    first = f.readline()
    print(first.strip())
```

① `line1`  
② `line1\n`  
③ `line1 line2 line3`  
④ Error  

---

**Problem 12.** What does `os.path.exists()` do?

① Creates a new file  
② **Checks if a file/directory exists**  
③ Deletes a file  
④ Copies a file  

---

### 🔴 Advanced

**Problem 13.** What is the output of the following code?

```python
data = ["apple", "banana", "orange"]
with open("items.txt", "w") as f:
    for item in data:
        f.write(item + "\n")

with open("items.txt", "r") as f:
    content = f.read()
    count = content.count("\n")
print(count)
```

① 1  
② 2  
③ 3  
④ 4  

---

**Problem 14.** What is the difference between `read()` and `readlines()`?

① `read()` returns a string, `readlines()` returns a **list of strings**  
② Both are identical  
③ `read()` is faster  
④ `readlines()` doesn't work with `with`  

---

**Problem 15.** What is the correct way to write the sum of list elements to a file?

```python
numbers = [1, 2, 3, 4, 5]
with open("sum.txt", "w") as f:
    f.write(str(sum(numbers)))
```

Why is `str()` necessary?

① Files can only store strings  
② To make the number smaller  
③ To encrypt the file  
④ To compress data  

---

## 📝 Short Answer Questions

---

### 🟢 Beginner

**Problem 16.** Explain the three file modes `"r"`, `"w"`, and `"a"` and when to use each.

---

**Problem 17.** What is the advantage of using the `with` statement? Write the output of the following code.

```python
with open("greeting.txt", "w") as f:
    f.write("Hello\n")
    f.write("World\n")

with open("greeting.txt", "r") as f:
    text = f.read()
print(text)
```

---

**Problem 18.** Explain the difference between `write()` and `writelines()`. Show example code for each.

---

### 🟡 Intermediate

**Problem 19.** What is `encoding="utf-8"` and why is it needed? Write code to save Korean text to a file.

```python
with open("korean.txt", "w", encoding="utf-8") as f:
    f.write("안녕하세요")

with open("korean.txt", "r", encoding="utf-8") as f:
    text = f.read()
print(text)
```

---

**Problem 20.** Explain how to count lines in a file and write code to do so.

```python
with open("data.txt", "w") as f:
    f.write("line1\n")
    f.write("line2\n")
    f.write("line3\n")

with open("data.txt", "r") as f:
    lines = f.readlines()
    print(f"Total lines: {len(lines)}")
```

---

### 🔴 Advanced

**Problem 21.** Write code to read a CSV file, process data, and save results. Explain each step.

```python
# Write CSV data
with open("scores.csv", "w") as f:
    f.write("name,score\n")
    f.write("John,85\n")
    f.write("Jane,92\n")
    f.write("Mike,78\n")

# Read and process
with open("scores.csv", "r") as f:
    lines = f.readlines()
    total = 0
    count = 0
    for line in lines[1:]:  # Skip header
        parts = line.strip().split(",")
        score = int(parts[1])
        total = total + score
        count = count + 1
    
    if count > 0:
        average = total / count
        print(f"Average: {average:.1f}")
```

---

## 💻 Hands-On Problems

---

### 🟢 Beginner

**Problem 22.** Write a program that creates a file and writes data to it.

> Create a `students.txt` file and write 5 students' names, one per line. Then read and print the file contents.

Output example:

```
=== Writing data ===
Created students.txt

=== Reading data ===
1. John
2. Jane
3. Mike
4. Sarah
5. David
```

---

**Problem 23.** Write a program that appends data to an existing file.

> Create `log.txt` with initial data, then append 3 more entries. Print all contents.

Output example:

```
=== Initial log ===
[2026-02-14] Program started

=== After appending ===
[2026-02-14] Program started
[2026-02-14] Processing data
[2026-02-14] Data saved
[2026-02-14] Program ended

Total entries: 4
```

---

### 🟡 Intermediate

**Problem 24.** Write a program to process a data file and calculate statistics.

> Create a file with scores, read it, calculate average and find highest/lowest scores, save results to output file.

Output example:

```
=== Scores ===
[Input file: scores.txt]
John: 85
Jane: 92
Mike: 78
Sarah: 88
David: 95

=== Analysis ===
Total: 438
Average: 87.6
Highest: Sarah (95)
Lowest: Mike (78)

[Results saved to results.txt]
```

---

**Problem 25.** Write a program to copy file contents with modifications.

> Read source file, modify each line (add line numbers), and write to new file.

Output example (source.txt → numbered.txt):

```
Original content in source.txt:
Hello
World
Python

After adding line numbers:
1. Hello
2. World
3. Python

File saved to numbered.txt
```

---

### 🔴 Advanced

**Problem 26.** Write a comprehensive file management system.

> Manage a student database file with add/view/search/delete operations.

Output example:

```
=== Student Database ===

1. Add student
2. View all
3. Search student
4. Delete student
5. Exit

[Option 1: Add student]
Name: John
ID: S001
Major: CS
Grade: 85
Added successfully!

[Option 2: View all]
John,S001,CS,85
Jane,S002,Business,92
Mike,S003,CS,78

[Option 3: Search]
Search for: Jane
Found: Jane,S002,Business,92

[Option 4: Delete]
Delete: S001
John removed!

Updated database saved to students.db
```

---
---

# 🔑 Answer Key and Explanations

---

## 📝 Multiple Choice Answers

---

### 🟢 Beginner

**Problem 1. Answer: ② `open("file.txt", "w")`**

File modes: `"r"` = read, `"w"` = write, `"a"` = append. Mode `"w"` opens for writing.

---

**Problem 2. Answer: ② Automatically closes the file**

The `with` statement handles file closing automatically, preventing resource leaks.

---

**Problem 3. Answer: ③ Keeps existing content and appends to the end**

Mode `"a"` (append) preserves existing data and adds new content at the end.

---

**Problem 4. Answer: ② `HelloWorld`**

Both `write()` calls concatenate without newline. Result: "HelloWorld".

---

**Problem 5. Answer: ③ `readlines()`**

`readlines()` returns a list of lines; `readline()` returns single line; `read()` returns entire string.

---

**Problem 6. Answer: ② Handles Korean correctly**

UTF-8 encoding properly handles non-ASCII characters like Korean.

---

**Problem 7. Answer: ③ Raises `FileNotFoundError` error**

Reading non-existent file raises `FileNotFoundError`.

---

### 🟡 Intermediate

**Problem 8. Answer: ② `Second\n`**

Mode `"w"` overwrites. Second `open()` overwrites the first content.

---

**Problem 9. Answer: ① `First\nSecond\n`**

Mode `"a"` appends. Both writes combine.

---

**Problem 10. Answer: ② 3**

`readlines()` creates list with 3 elements (lines 1, 2, 3).

---

**Problem 11. Answer: ① `line1`**

`readline()` reads first line. `strip()` removes `\n`.

---

**Problem 12. Answer: ② Checks if a file/directory exists**

`os.path.exists()` returns `True` if path exists, `False` otherwise.

---

### 🔴 Advanced

**Problem 13. Answer: ③ 3**

Three items each end with `\n`, so 3 newlines in total.

---

**Problem 14. Answer: ① `read()` returns a string, `readlines()` returns a list of strings**

`read()` → single string; `readlines()` → list of line strings.

---

**Problem 15. Answer: ① Files can only store strings**

`write()` requires strings. `str()` converts numbers to strings.

---

## 📝 Short Answer Key

---

### 🟢 Beginner

**Problem 16. Model Answer:**

- **`"r"` (read)**: Open existing file for reading. Raises error if file doesn't exist.
- **`"w"` (write)**: Create file or overwrite existing. Deletes old content.
- **`"a"` (append)**: Open or create file. Adds content to the end without deleting existing.

---

**Problem 17. Model Answer:**

**Advantage of `with`:**
- Automatically closes file
- Prevents resource leaks
- Code is cleaner

**Output:**
```
Hello
World

```

---

**Problem 18. Model Answer:**

- **`write()`**: Writes single string
- **`writelines()`**: Writes list of strings (no automatic newlines)

```python
# write()
f.write("Hello\n")

# writelines()
f.writelines(["Hello\n", "World\n"])
```

---

### 🟡 Intermediate

**Problem 19. Model Answer:**

**`encoding="utf-8"`**: Specifies character encoding for non-ASCII text like Korean, Chinese, etc.

**Output:**
```
안녕하세요
```

---

**Problem 20. Model Answer:**

Count lines using `readlines()` length:

**Output:**
```
Total lines: 3
```

---

### 🔴 Advanced

**Problem 21. Model Answer:**

**Steps:**
1. Write CSV header and data
2. Read file and skip header
3. Parse each line by splitting on comma
4. Convert score to integer and sum
5. Calculate average

---

## 💻 Hands-On Solutions

---

### 🟢 Beginner

**Problem 22. Model Answer:**

```python
# Write data
students = ["John", "Jane", "Mike", "Sarah", "David"]

print("=== Writing data ===")
with open("students.txt", "w") as f:
    for student in students:
        f.write(student + "\n")
print("Created students.txt")

# Read and display
print("\n=== Reading data ===")
with open("students.txt", "r") as f:
    lines = f.readlines()
    for i, line in enumerate(lines, 1):
        print(f"{i}. {line.strip()}")
```

---

**Problem 23. Model Answer:**

```python
# Initial write
print("=== Initial log ===")
with open("log.txt", "w") as f:
    f.write("[2026-02-14] Program started\n")
print("[2026-02-14] Program started")

# Append entries
print("\n=== After appending ===")
entries = [
    "[2026-02-14] Processing data\n",
    "[2026-02-14] Data saved\n",
    "[2026-02-14] Program ended\n"
]

with open("log.txt", "a") as f:
    for entry in entries:
        f.write(entry)

# Read all
with open("log.txt", "r") as f:
    lines = f.readlines()
    for line in lines:
        print(line.strip())

print(f"\nTotal entries: {len(lines)}")
```

---

### 🟡 Intermediate

**Problem 24. Model Answer:**

```python
# Create score file
scores_data = [
    ("John", 85),
    ("Jane", 92),
    ("Mike", 78),
    ("Sarah", 88),
    ("David", 95)
]

with open("scores.txt", "w") as f:
    for name, score in scores_data:
        f.write(f"{name}: {score}\n")

# Read and analyze
with open("scores.txt", "r") as f:
    lines = f.readlines()

scores = []
for line in lines:
    parts = line.strip().split(": ")
    name = parts[0]
    score = int(parts[1])
    scores.append((name, score))

total = sum(s[1] for s in scores)
average = total / len(scores)
highest = max(scores, key=lambda x: x[1])
lowest = min(scores, key=lambda x: x[1])

# Save results
with open("results.txt", "w") as f:
    f.write(f"Total: {total}\n")
    f.write(f"Average: {average:.1f}\n")
    f.write(f"Highest: {highest[0]} ({highest[1]})\n")
    f.write(f"Lowest: {lowest[0]} ({lowest[1]})\n")

print(f"Total: {total}")
print(f"Average: {average:.1f}")
print(f"Highest: {highest[0]} ({highest[1]})")
print(f"Lowest: {lowest[0]} ({lowest[1]})")
print("\nResults saved to results.txt")
```

---

**Problem 25. Model Answer:**

```python
# Create source file
with open("source.txt", "w") as f:
    f.write("Hello\n")
    f.write("World\n")
    f.write("Python\n")

# Read, number, and save
with open("source.txt", "r") as f:
    lines = f.readlines()

with open("numbered.txt", "w") as f:
    for i, line in enumerate(lines, 1):
        f.write(f"{i}. {line.strip()}\n")

# Display
print("Original content:")
with open("source.txt", "r") as f:
    for line in f:
        print(line.strip())

print("\nAfter adding line numbers:")
with open("numbered.txt", "r") as f:
    for line in f:
        print(line.strip())

print("\nFile saved to numbered.txt")
```

---

### 🔴 Advanced

**Problem 26. Model Answer:**

```python
import os

db_file = "students.db"

def add_student():
    name = input("Name: ")
    student_id = input("ID: ")
    major = input("Major: ")
    grade = input("Grade: ")
    
    with open(db_file, "a") as f:
        f.write(f"{name},{student_id},{major},{grade}\n")
    print("Added successfully!")

def view_all():
    if not os.path.exists(db_file):
        print("No data found")
        return
    
    with open(db_file, "r") as f:
        lines = f.readlines()
        for line in lines:
            print(line.strip())

def search_student():
    search_term = input("Search for: ")
    
    with open(db_file, "r") as f:
        lines = f.readlines()
        found = False
        for line in lines:
            if search_term in line:
                print("Found:", line.strip())
                found = True
        
        if not found:
            print("Not found")

def delete_student():
    delete_id = input("Delete ID: ")
    
    with open(db_file, "r") as f:
        lines = f.readlines()
    
    with open(db_file, "w") as f:
        for line in lines:
            if delete_id not in line:
                f.write(line)
            else:
                name = line.split(",")[0]
                print(f"{name} removed!")

while True:
    print("\n=== Student Database ===")
    print("1. Add student")
    print("2. View all")
    print("3. Search student")
    print("4. Delete student")
    print("5. Exit")
    
    choice = input("Option: ")
    
    if choice == "1":
        add_student()
    elif choice == "2":
        view_all()
    elif choice == "3":
        search_student()
    elif choice == "4":
        delete_student()
    elif choice == "5":
        print("Saved!")
        break
```

---

Professor Cho Jeonghyun (peterchokr@gmail.com)  
Yeungnam University College.
