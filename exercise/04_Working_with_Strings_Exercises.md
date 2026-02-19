# Chapter 4: Working with Strings — Practice Problems

---

## 📝 Multiple Choice Questions

---

### 🟢 Beginner

**Problem 1.** What is the output of the following code?

```python
text = "Hello"
print(text[0])
```

① H  
② e  
③ o  
④ Hello  

---

**Problem 2.** What is the output of the following code?

```python
text = "Python"
print(text[-1])
```

① P  
② n  
③ o  
④ Error  

---

**Problem 3.** What is used to create a multi-line string?

① Double quotes `""`  
② Single quotes `''`  
③ Triple quotes `"""`  
④ Parentheses `()`  

---

**Problem 4.** Which of the following is an escape character for newline?

① `\t`  
② `\n`  
③ `\\`  
④ `\"`  

---

**Problem 5.** What is the output of the following code?

```python
text = "Python"
print(len(text))
```

① 5  
② 6  
③ 7  
④ Error  

---

**Problem 6.** What is the output of the following code?

```python
text = "hello"
print(text.upper())
```

① hello  
② Hello  
③ HELLO  
④ hELLO  

---

**Problem 7.** Strings are immutable. Which of the following causes an error?

① `text = "Hello"; text = "World"`  
② `text = "Hello"; print(text.upper())`  
③ `text = "Hello"; text[0] = "h"`  
④ `text = "Hello"; new = text.replace("H", "h")`  

---

### 🟡 Intermediate

**Problem 8.** What is the output of the following code?

```python
text = "Hello, World!"
print(text[7:12])
```

① Hello  
② World  
③ World!  
④ , Wor  

---

**Problem 9.** What is the output of the following code?

```python
text = "   Python   "
result = text.strip()
print(f"[{result}]")
```

① `[   Python   ]`  
② `[Python   ]`  
③ `[   Python]`  
④ `[Python]`  

---

**Problem 10.** What is the output of the following code?

```python
text = "apple,banana,cherry"
result = text.split(',')
print(result[1])
```

① apple  
② banana  
③ cherry  
④ apple,banana,cherry  

---

**Problem 11.** What is the output of the following code?

```python
text = "Python is fun"
print(text.find('is'))
```

① 6  
② 7  
③ True  
④ 2  

---

**Problem 12.** What is the output of the following code?

```python
words = ['Hello', 'World']
result = ' '.join(words)
print(result)
```

① HelloWorld  
② Hello World  
③ Hello, World  
④ ['Hello', 'World']  

---

### 🔴 Advanced

**Problem 13.** What is the output of the following code?

```python
text = "Programming"
print(text[::2])
```

① Prog  
② Prga  
③ Pormig  
④ rgamn  

---

**Problem 14.** What is the output of the following code?

```python
text = "Hello, Python!"
result = text.replace("Python", "World").split(",")
print(result[1].strip())
```

① Hello  
② Python!  
③ World!  
④ , World!  

---

**Problem 15.** What is the output of the following code?

```python
name = "alice"
score = 95.678
print(f"{name.title():>10}: {score:<8.1f} points")
```

① `Alice    : 95.7     points`  
② `     Alice: 95.7     points`  
③ `Alice: 95.7 points`  
④ Error  

---

## 📝 Short Answer Questions

---

### 🟢 Beginner

**Problem 16.** Using positive and negative indices on the string `"Python"`, write code to access the first and last characters respectively.

---

**Problem 17.** Explain the meaning of each element in the slicing syntax `[start:end:step]`, and write code to extract `"ace"` from the string `"abcdefg"`.

---

**Problem 18.** Write the output of the following code.

```python
text = "Python Programming"
print(text[:6])
print(text[7:])
print(text[::-1])
```

---

### 🟡 Intermediate

**Problem 19.** Explain the functionality of `find()`, `count()`, and `replace()` methods respectively, and write the output of the following code.

```python
msg = "Hello Python Hello World"
print(msg.find("Hello"))
print(msg.count("Hello"))
print(msg.replace("Hello", "Hi", 1))
```

---

**Problem 20.** Explain why an error occurs in the following code, and write the corrected code using f-string.

```python
name = "Emily Kim"
age = 22
message = "Name: " + name + ", Age: " + age + " years old"
print(message)
```

---

### 🔴 Advanced

**Problem 21.** Write the output of the following code and explain the operation at each step.

```python
email = "student@example.com"
parts = email.lower().split('@')
user_id = parts[0]
domain = parts[1]
tld = domain.split('.')[-1]
print(f"ID: {user_id}, Domain: {domain}, TLD: {tld}")
```

---

## 💻 Hands-On Problems

---

### 🟢 Beginner

**Problem 22.** Write a program that meets the following requirements.

> From the variable `text = "Hello, Python!"`, use slicing to extract `"Hello"`, `"Python"`, and `"!nohtyP ,olleH"` (reversed) and print them.

---

**Problem 23.** Write a program that meets the following requirements.

> Store your name in a variable, then use `upper()`, `lower()`, and `len()` to print in the following format.

Output example (name is "John Smith"):

```
Original: John Smith
Uppercase: JOHN SMITH
Lowercase: john smith
Character Count: 10
```

---

**Problem 24.** Write a program that meets the following requirements.

> For variables `price = 1234567` and `rate = 3.14159`, use f-string formatting to print as follows:

Output:

```
Price: $1,234,567
Rate: 3.14%
```

---

### 🟡 Intermediate

**Problem 25.** Write a program that meets the following requirements.

> Receive a sentence from the user using `input()` and analyze it to print the following information:
> - Total character count, character count excluding spaces, word count
> - Uppercase conversion, lowercase conversion
> - First and last word

Output example (input: "Python is very fun"):

```
=== Text Analysis ===
Total Characters: 18
Characters (no spaces): 15
Word Count: 4
Uppercase: PYTHON IS VERY FUN
Lowercase: python is very fun
First Word: Python
Last Word: fun
```

---

### 🔴 Advanced

**Problem 26.** Write a program that meets the following requirements.

> Receive a phone number from the user using `input()` (example: `123-456-7890`) and convert it to three different formats and print them.  
> If the input contains hyphens, remove them first before processing.  
> (Hint: Use `replace()`, slicing, and `join()`)

Output example:

```
Enter phone number: 123-456-7890
Format 1: 123-456-7890
Format 2: (123) 456-7890
Format 3: +1-123-456-7890
```

---
---

# 🔑 Answer Key and Explanations

---

## 📝 Multiple Choice Answers

---

### 🟢 Beginner

**Problem 1. Answer: ① H**

String indices start from 0. `text[0]` returns `H`, the first character of `"Hello"`.

---

**Problem 2. Answer: ② n**

Negative indices count from the end. `text[-1]` returns `n`, the last character of `"Python"`. `-1` is the last, `-2` is the second from last, etc.

---

**Problem 3. Answer: ③ Triple quotes `"""`**

Triple quotes (`"""` or `'''`) allow you to create strings spanning multiple lines. Regular quotes are used for single-line strings only.

---

**Problem 4. Answer: ② `\n`**

`\n` represents a newline character. `\t` is a tab, `\\` is a backslash, and `\"` is a double quote.

---

**Problem 5. Answer: ② 6**

The `len()` function returns the number of characters in a string. `"Python"` consists of 6 characters: P, y, t, h, o, n.

---

**Problem 6. Answer: ③ HELLO**

The `upper()` method returns a **new string** with all characters converted to uppercase. The original `text` remains unchanged.

---

**Problem 7. Answer: ③ `text[0] = "h"`**

Strings are immutable, so you cannot directly change a character at a specific index. This causes a `TypeError`. ① Assigning a new string to a variable is possible, and ② ④ methods return new strings without issues.

---

### 🟡 Intermediate

**Problem 8. Answer: ② World**

In `"Hello, World!"`, index 7 is `W` and index 11 is `d`. `text[7:12]` returns characters at indices 7-11, which is `World`. The end index is not included in slicing.

---

**Problem 9. Answer: ④ `[Python]`**

The `strip()` method removes whitespace from both ends of a string. `"   Python   "` becomes `"Python"` after `strip()`, which is then printed within brackets.

---

**Problem 10. Answer: ② banana**

`split(',')` separates the string by commas, creating a list `['apple', 'banana', 'cherry']`. `result[1]` is the second element, `banana`.

---

**Problem 11. Answer: ② 7**

The `find()` method returns the **index** where the substring first appears. In `"Python is fun"`, `"is"` starts at index 7. Returns `-1` if not found.

---

**Problem 12. Answer: ② Hello World**

The `join()` method concatenates list elements with a separator. `' '.join(['Hello', 'World'])` joins with a space to create `"Hello World"`.

---

### 🔴 Advanced

**Problem 13. Answer: ③ Pormig**

`text[::2]` extracts every 2nd character starting from index 0. In `"Programming"`, indices 0(P), 2(o), 4(r), 6(m), 8(i), 10(g) give `"Pormig"`.

---

**Problem 14. Answer: ③ World!**

Step-by-step: ① `text.replace("Python", "World")` → `"Hello, World!"` ② `.split(",")` → `['Hello', ' World!']` ③ `result[1]` → `' World!'` ④ `.strip()` → `'World!'`. Methods are chained sequentially.

---

**Problem 15. Answer: ② `     Alice: 95.7     points`**

`name.title()` converts to `"Alice"` (5 characters). `:>10` right-aligns in 10 spaces, adding 5 leading spaces. `score` with `:<8.1f` shows one decimal (95.7) left-aligned in 8 spaces with trailing spaces.

---

## 📝 Short Answer Key

---

### 🟢 Beginner

**Problem 16. Model Answer:**

```python
text = "Python"

# First character
print(text[0])    # P (positive index)
print(text[-6])   # P (negative index)

# Last character
print(text[5])    # n (positive index)
print(text[-1])   # n (negative index)
```

Positive indices start from 0 (counting from the beginning), while negative indices start from -1 (counting from the end).

---

**Problem 17. Model Answer:**

**Slicing syntax `[start:end:step]`:**
- **start**: Index where extraction begins (omit to start from beginning)
- **end**: Index where extraction ends (up to but not including this index; omit to go to end)
- **step**: Skip interval (omit for default of 1)

```python
text = "abcdefg"
print(text[::2])    # "aceg" → to get just "ace":
print(text[0:5:2])  # "ace"
```

`text[0:5:2]` extracts indices 0(a), 2(c), 4(e) by stepping by 2.

---

**Problem 18. Model Answer:**

```
Python
Programming
gnimmargorP nohtyP
```

`text[:6]` extracts from index 0 to 5 → `"Python"`. `text[7:]` extracts from index 7 to end → `"Programming"`. `text[::-1]` reverses the string → `"gnimmargorP nohtyP"`.

---

### 🟡 Intermediate

**Problem 19. Model Answer:**

**Method Explanations:**
- `find(substring)`: Returns the **index** of the first occurrence of the substring. Returns `-1` if not found.
- `count(substring)`: Returns the **number of occurrences** of the substring.
- `replace(old, new, count)`: **Replaces** the old substring with the new one. If count is specified, only replaces that many times.

**Execution Results:**
```
0
2
Hi Python Hello World
```

`find("Hello")` returns 0 (starting position of first "Hello"). `count("Hello")` returns 2 (appears twice). `replace("Hello", "Hi", 1)` replaces only the first occurrence.

---

**Problem 20. Model Answer:**

**Error cause:** `age` is an integer type, so you cannot directly concatenate it with strings using the `+` operator. This causes a `TypeError`.

**Corrected code (using f-string):**

```python
name = "Emily Kim"
age = 22
message = f"Name: {name}, Age: {age} years old"
print(message)
```

f-strings automatically handle any variable type and convert it to a string, eliminating the need for manual type conversion.

---

### 🔴 Advanced

**Problem 21. Model Answer:**

Execution result:

```
ID: student, Domain: example.com, TLD: com
```

**Step-by-step explanation:**

1. `email.lower()` → `"student@example.com"` (convert all to lowercase)
2. `.split('@')` → `['student', 'example.com']` (split by `@`)
3. `parts[0]` → `"student"` (user ID part)
4. `parts[1]` → `"example.com"` (domain part)
5. `domain.split('.')` → `['example', 'com']` (split by `.`)
6. `[-1]` → `"com"` (last element = top-level domain)

---

## 💻 Hands-On Solutions

---

### 🟢 Beginner

**Problem 22. Model Answer:**

```python
text = "Hello, Python!"

print(text[:5])     # Hello
print(text[7:13])   # Python
print(text[::-1])   # !nohtyP ,olleH
```

Key point: `[:5]` extracts indices 0-4, `[7:13]` extracts indices 7-12, and `[::-1]` reverses the entire string.

---

**Problem 23. Model Answer:**

```python
name = "John Smith"

print(f"Original: {name}")
print(f"Uppercase: {name.upper()}")
print(f"Lowercase: {name.lower()}")
print(f"Character Count: {len(name)}")
```

Key point: `upper()` converts all characters to uppercase, `lower()` to lowercase, and `len()` counts all characters including spaces.

---

**Problem 24. Model Answer:**

```python
price = 1234567
rate = 3.14159

print(f"Price: ${price:,}")
print(f"Rate: {rate:.2f}%")
```

Key point: `:,` adds thousand separators to numbers, and `:.2f` displays numbers to 2 decimal places.

---

### 🟡 Intermediate

**Problem 25. Model Answer:**

```python
text = input("Enter a sentence: ")

# Analysis
total_length = len(text)
no_space_length = len(text.replace(' ', ''))
words = text.split()
word_count = len(words)

# Output
print("\n=== Text Analysis ===")
print(f"Total Characters: {total_length}")
print(f"Characters (no spaces): {no_space_length}")
print(f"Word Count: {word_count}")
print(f"Uppercase: {text.upper()}")
print(f"Lowercase: {text.lower()}")
print(f"First Word: {words[0]}")
print(f"Last Word: {words[-1]}")
```

Key points:
- Use `replace(' ', '')` to remove spaces before counting characters.
- `split()` divides the text by spaces to create a word list.
- `words[0]` is the first word, `words[-1]` is the last word.

---

### 🔴 Advanced

**Problem 26. Model Answer:**

```python
phone_input = input("Enter phone number: ")

# Remove hyphens to extract digits only
phone = phone_input.replace("-", "")

# Use slicing to separate parts
part1 = phone[:3]    # 123
part2 = phone[3:6]   # 456
part3 = phone[6:]    # 7890

# Output in three formats
print(f"Format 1: {part1}-{part2}-{part3}")
print(f"Format 2: ({part1}) {part2}-{part3}")
print(f"Format 3: +1-{part1}-{part2}-{part3}")
```

Key points:
- `replace("-", "")` removes hyphens from the input first.
- Slicing separates the phone number into parts: first 3 digits, next 3 digits, last 4 digits.
- International format uses country code `+1` for the US.
- f-strings flexibly combine different formats.

---

Professor Cho Jeonghyun (peterchokr@gmail.com)  
Yeungnam University College.
