# Chapter 4. Working with Strings

---

## 📚 Learning Objectives

After completing this chapter, you will learn various ways to create, access, and manipulate strings. Since strings are one of the most frequently used data types in programming, learning how to handle them effectively is very important.

이번 장을 마치면 여러분은 문자열을 생성하고, 접근하고, 조작하는 다양한 방법을 익히게 됩니다. 문자열은 프로그래밍에서 가장 많이 다루는 데이터 타입 중 하나이므로, 이를 효과적으로 다루는 방법을 배우는 것은 매우 중요합니다.

---

## 1️⃣ String Creation and Characteristics (문자열 생성과 특징)

A string is a continuous sequence of characters. In Python, strings are created by enclosing them in double quotes (`"`) or single quotes (`'`). Both methods are functionally equivalent, but you can use them separately when you want to include quotes within the string.

문자열(String)은 문자들의 연속된 나열입니다. 파이썬에서 문자열은 큰따옴표(`"`) 또는 작은따옴표(`'`)로 감싸서 만듭니다. 두 방법은 기능적으로 동일하지만, 문자열 내부에 따옴표를 포함할 때는 구분해서 사용할 수 있습니다.

```python
# Various ways to create strings (다양한 문자열 생성 방법)
name1 = "Alex Johnson"
name2 = 'Sarah Williams'
message = "Hello, World!"
empty = ""  # Empty string (빈 문자열)

# Include quotes within strings (문자열 안에 따옴표 포함)
sentence1 = "He said, 'Hello!'"
sentence2 = 'She replied, "Goodbye!"'

print(sentence1)  # He said, 'Hello!'
print(sentence2)  # She replied, "Goodbye!"
```

### Multi-line Strings (여러 줄 문자열)

When creating long strings that span multiple lines, use triple quotes (`"""` or `'''`). This is mainly useful when storing long texts or documents.

여러 줄에 걸친 긴 문자열을 만들 때는 삼중 따옴표(`"""` 또는 `'''`)를 사용합니다. 이는 주로 긴 텍스트나 문서를 저장할 때 유용합니다.

```python
# Multi-line string (여러 줄 문자열)
poem = """
Life is a journey,
Full of challenges and opportunities,
Keep moving forward with courage!
"""

print(poem)

# Long description in code (코드 내 긴 설명문)
description = '''
This program is a student grade management system.
Features: Grade input, average calculation, grade calculation
Developer: Alex Johnson
Version: 1.0
'''
```

### Escape Characters (이스케이프 문자)

Use a backslash (`\`) to represent characters with special functions. These are called escape characters.

특수한 기능을 하는 문자를 표현할 때는 백슬래시(`\`)를 사용합니다. 이를 이스케이프 문자라고 합니다.

```python
# Main escape characters (주요 이스케이프 문자)
print("First line\nSecond line")  # \n: newline (줄바꿈)
print("Tab\tadjustment\ttest")  # \t: tab (탭)
print("Double quote: \"Hello\"")  # \": double quote (큰따옴표)
print("Single quote: \'Hi\'")  # \': single quote (작은따옴표)
print("Backslash: \\")  # \\: backslash (백슬래시)
```

```
Escape Characters Summary (이스케이프 문자 정리)

┌──────────┬────────────────────┐
│ Escape   │ Meaning            │
├──────────┼────────────────────┤
│   \n     │ Newline (줄바꿈)    │
│   \t     │ Tab (탭)            │
│   \"     │ Double quote (큰따옴표) │
│   \'     │ Single quote (작은따옴표) │
│   \\     │ Backslash (백슬래시)  │
└──────────┴────────────────────┘
```

---

## 2️⃣ String Indexing (문자열 인덱싱)

Each character in a string has a position (index). Indexing starts at 0, and you can access characters at specific positions using square brackets (`[]`).

문자열의 각 문자는 위치(인덱스)를 가지고 있습니다. 인덱스는 0부터 시작하며, 대괄호(`[]`)를 사용하여 특정 위치의 문자에 접근할 수 있습니다.

```python
# String indexing (문자열 인덱싱)
word = "Python"

# Positive index (from front) (양수 인덱스 (앞에서부터))
print(word[0])  # P (first character)
print(word[1])  # y
print(word[2])  # t
print(word[5])  # n (last character)

# Negative index (from back) (음수 인덱스 (뒤에서부터))
print(word[-1])  # n (last character)
print(word[-2])  # o (second from back)
print(word[-6])  # P (first character)
```

```
String Indexing Diagram (문자열 인덱싱 다이어그램)

        P    y    t    h    o    n
    ┌───┬───┬───┬───┬───┬───┐
    │ 0 │ 1 │ 2 │ 3 │ 4 │ 5 │  Positive index (양수 인덱스)
    ├───┼───┼───┼───┼───┼───┤
    │-6 │-5 │-4 │-3 │-2 │-1 │  Negative index (음수 인덱스)
    └───┴───┴───┴───┴───┴───┘
```

---

## 3️⃣ String Slicing (문자열 슬라이싱)

String slicing is a way to extract a substring using a range of indices. The syntax is `string[start:end:step]`. The end index is exclusive (not included in the result).

문자열 슬라이싱은 인덱스 범위를 이용하여 부분 문자열을 추출하는 방법입니다. 문법은 `string[start:end:step]`입니다. end 인덱스는 제외됩니다(결과에 포함되지 않음).

```python
# String slicing (문자열 슬라이싱)
text = "Programming"

# Basic slicing (기본 슬라이싱)
print(text[0:3])    # Pro (from index 0 to 2)
print(text[3:9])    # gramm
print(text[:4])     # Prog (from start to 3)
print(text[8:])     # ing (from 8 to end)
print(text[:])      # Programming (entire string)

# Negative slicing (음수 슬라이싱)
print(text[-3:])    # ing (last 3 characters)
print(text[:-4])    # Programm (all except last 4)

# Slicing with step (step을 사용한 슬라이싱)
print(text[::2])    # Pormig (every 2nd character)
print(text[1::2])   # rgarig (from index 1, every 2nd)
print(text[::-1])   # gnimmargorP (reverse)
```

---

## 4️⃣ String Methods (문자열 메서드)

String methods are built-in functions that operate on strings. There are many useful methods for manipulating strings.

문자열 메서드는 문자열에 대해 작동하는 내장 함수입니다. 문자열을 조작하는 많은 유용한 메서드들이 있습니다.

### Common String Methods (자주 사용하는 문자열 메서드)

```python
# Case conversion (대소문자 변환)
text = "Hello World"
print(text.upper())        # HELLO WORLD
print(text.lower())        # hello world
print(text.capitalize())   # Hello world
print(text.title())        # Hello World

# Finding and replacing (찾기 및 바꾸기)
print(text.find("World"))  # 6 (index of first occurrence)
print(text.count("l"))     # 3 (count of 'l')
print(text.replace("World", "Python"))  # Hello Python

# Stripping whitespace (공백 제거)
text2 = "  Hello  "
print(text2.strip())       # Hello (remove both sides)
print(text2.lstrip())      # Hello   (remove left side)
print(text2.rstrip())      #   Hello (remove right side)

# Splitting and joining (분리 및 연결)
text3 = "apple,banana,cherry"
fruits = text3.split(",")  # ['apple', 'banana', 'cherry']
result = "-".join(fruits)  # apple-banana-cherry

# Checking content (내용 확인)
print("hello".isdigit())        # False
print("12345".isdigit())        # True
print("Hello".startswith("He")) # True
print("Hello".endswith("lo"))   # True
```

### Example 1: Text Processing Program (예제 1: 텍스트 처리 프로그램)

```python
# Text processing program (텍스트 처리 프로그램)
print("=== Text Processing Tool ===")

# Get user input (사용자 입력 받기)
user_text = input("Enter text: ")

# Process text (텍스트 처리)
length = len(user_text)
uppercase = user_text.upper()
lowercase = user_text.lower()
reversed_text = user_text[::-1]

# Count vowels (모음 개수 세기)
vowels = "aeiouAEIOU"
vowel_count = sum(1 for char in user_text if char in vowels)

# Display results (결과 출력)
print(f"\nOriginal: {user_text}")
print(f"Length: {length}")
print(f"Uppercase: {uppercase}")
print(f"Lowercase: {lowercase}")
print(f"Reversed: {reversed_text}")
print(f"Number of vowels: {vowel_count}")
```

---

## 5️⃣ String Formatting (문자열 포매팅)

There are several ways to insert variable values into strings. The most modern and convenient way is using f-strings.

문자열에 변수 값을 삽입하는 여러 가지 방법이 있습니다. 가장 현대적이고 편리한 방법은 f-문자열(f-string)을 사용하는 것입니다.

### F-strings (f-문자열)

```python
# F-string basics (f-문자열 기본)
name = "Emily Davis"
age = 25

print(f"My name is {name}")
print(f"I am {age} years old")
print(f"Next year I will be {age + 1}")

# F-string formatting (f-문자열 포매팅)
price = 19.99
quantity = 3
total = price * quantity

print(f"Price: ${price:.2f}")  # Display 2 decimal places
print(f"Quantity: {quantity:3d}")  # Right-align in 3 spaces
print(f"Total: ${total:,.2f}")  # Display with comma separator
```

### Other Formatting Methods (다른 포매팅 방법)

```python
# format() method (format() 메서드)
text = "My name is {} and I am {} years old".format("Michael Wilson", 30)
print(text)

# % operator (% 연산자)
text2 = "My name is %s and I am %d years old" % ("Jessica Anderson", 28)
print(text2)
```

### Example 2: Invoice Generator (예제 2: 영수증 생성 프로그램)

```python
# Invoice generator program (영수증 생성 프로그램)
print("=== Invoice Generator ===")

# Get input (입력 받기)
customer_name = input("Customer name: ")
product = input("Product: ")
unit_price = float(input("Unit price: $"))
quantity = int(input("Quantity: "))

# Calculate (계산)
subtotal = unit_price * quantity
tax = subtotal * 0.08  # 8% tax
total = subtotal + tax

# Display invoice (영수증 출력)
line = "=" * 40
print(f"\n{line}")
print(f"{'INVOICE':^40}")
print(f"{line}")
print(f"Customer: {customer_name}")
print(f"Product: {product}")
print(f"{'-'*40}")
print(f"Unit Price: ${unit_price:>10.2f}")
print(f"Quantity: {quantity:>15}")
print(f"Subtotal: ${subtotal:>13.2f}")
print(f"Tax (8%): ${tax:>14.2f}")
print(f"{'-'*40}")
print(f"Total: ${total:>18.2f}")
print(f"{line}\n")
```

---

## 📝 Summary of Key Concepts (핵심 개념 정리)

A string is a sequence of characters created using double or single quotes. Each character has an index starting from 0, allowing access via `string[index]`. Slicing with `string[start:end:step]` extracts substrings.

문자열은 큰따옴표나 작은따옴표로 만든 문자들의 연속입니다. 각 문자는 0부터 시작하는 인덱스를 가지며, `string[index]`로 접근할 수 있습니다. `string[start:end:step]`을 사용한 슬라이싱으로 부분 문자열을 추출할 수 있습니다.

String methods like `upper()`, `lower()`, `find()`, `replace()`, `split()`, and `join()` are used to manipulate strings. F-strings are the most modern way to format strings with variable values, providing clear and readable code.

`upper()`, `lower()`, `find()`, `replace()`, `split()`, `join()` 등의 문자열 메서드를 사용하여 문자열을 조작할 수 있습니다. f-문자열은 변수 값을 포함하여 문자열을 포매팅하는 가장 현대적인 방법으로, 명확하고 읽기 쉬운 코드를 제공합니다.

---

## 💡 Practical Assignments (실습 과제)

### Assignment 1: Email Validation Program (과제 1: 이메일 검증 프로그램)

Write a program that checks if an email address is valid. Email validation criteria:

이메일 주소가 유효한지 확인하는 프로그램을 작성하세요. 이메일 검증 기준:

- Contains @ symbol (@ 기호 포함)
- Has text before and after @ symbol (@의 앞뒤에 텍스트 있음)
- Contains dot (.) after @ symbol (@ 이후에 점(.) 포함)

```python
# Hint: Use find(), count() methods
email = input("Enter email: ")
# Write validation code here
```

### Assignment 2: Password Strength Checker (과제 2: 비밀번호 강도 검사)

Write a program that checks password strength based on the following criteria:

다음 기준을 바탕으로 비밀번호 강도를 검사하는 프로그램을 작성하세요:

- Minimum 8 characters (최소 8글자)
- Contains uppercase letters (대문자 포함)
- Contains lowercase letters (소문자 포함)
- Contains numbers (숫자 포함)
- Contains special characters (@, #, $, etc.) (특수 문자 포함)

```python
# Hint: Use isupper(), islower(), isdigit() methods
password = input("Enter password: ")
# Write validation code here
```

---

## ✅ Quiz (퀴즈)

### [Beginner] Question 1

What is the output of the following code?

다음 코드의 실행 결과는?

```python
text = "Python"
print(text[1])
```

1. P
2. y
3. t
4. h

### [Intermediate] Question 2

What is the output?

다음의 결과는?

```python
text = "Programming"
print(text[0:4])
```

1. Program
2. Prog
3. ogra
4. gramm

### [Intermediate] Question 3

What is the output?

다음의 결과는?

```python
text = "HELLO WORLD"
print(text.lower().replace("world", "python"))
```

1. HELLO PYTHON
2. hello python
3. hello world
4. Error

### [Intermediate] Question 4

What is the output?

다음의 결과는?

```python
name = "Alex"
age = 25
print(f"{name} is {age} years old")
```

1. Alex is 25 years old
2. name is age years old
3. {name} is {age} years old
4. Error

### [Advanced] Question 5

What is the output?

다음의 결과는?

```python
text = "PYTHON"
print(text[::-1])
```

1. PYTHON
2. nohtyp
3. NOHTYP
4. python

---

## 🔑 Quiz Answers and Explanations (퀴즈 정답 및 해설)

**Question 1 Answer: 2**
`text[1]` accesses the character at index 1. In "Python", index 1 is 'y'.

`text[1]`은 인덱스 1의 문자에 접근합니다. "Python"에서 인덱스 1은 'y'입니다.

**Question 2 Answer: 2**
`text[0:4]` extracts characters from index 0 to 3 (4 is exclusive). "Programming"[0:4] is "Prog".

`text[0:4]`는 인덱스 0부터 3까지의 문자를 추출합니다 (4는 제외). "Programming"[0:4]는 "Prog"입니다.

**Question 3 Answer: 2**
`.lower()` converts to lowercase "hello world", then `.replace("world", "python")` replaces "world" with "python", resulting in "hello python".

`.lower()`는 "hello world"로 변환하고, `.replace("world", "python")`은 "world"를 "python"으로 바꿔서 "hello python"이 됩니다.

**Question 4 Answer: 1**
F-strings substitute variable values directly. `{name}` becomes "Alex" and `{age}` becomes 25, resulting in "Alex is 25 years old".

f-문자열은 변수 값을 직접 치환합니다. `{name}`은 "Alex"가 되고 `{age}`는 25가 되어 "Alex is 25 years old"가 됩니다.

**Question 5 Answer: 3**
`[::-1]` reverses the string (step -1). "PYTHON" reversed is "NOHTYP".

`[::-1]`은 문자열을 역순으로 만듭니다 (step -1). "PYTHON"을 역순으로 하면 "NOHTYP"입니다.

---

## 🎯 Preview of Next Chapter (다음 장 예고)

In the next chapter, we will learn about input and output. We will learn how to receive user input in various forms and how to format output nicely. Input and output are the window through which users and programs communicate, so handling them effectively is very important.

다음 장에서는 입력과 출력에 대해 배웁니다. 사용자로부터 다양한 형태의 입력을 받고, 출력을 보기 좋게 꾸미는 방법을 익히게 됩니다.

---

Thank you for your attention.   
Cho Jeonghyun ([peterchokr@gmail.com](mailto:peterchokr@gmail.com)). Yeungnam University College

"Produced in collaboration with Claude and Gemini."
