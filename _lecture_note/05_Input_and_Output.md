# Chapter 5. Input and Output

---

## 📚 Learning Objectives

After completing this chapter, you will learn how to receive various forms of input from users and how to format output beautifully. Input and output are the window through which users and programs communicate, so handling them effectively is very important.

이번 장을 마치면 여러분은 사용자로부터 다양한 형태의 입력을 받고, 출력을 보기 좋게 꾸미는 방법을 익히게 됩니다. 입력과 출력은 사용자와 프로그램이 소통하는 창구이므로, 이를 효과적으로 다루는 것은 매우 중요합니다.

---

## 1️⃣ Getting Input - input() Function (입력 받기)

The `input()` function is the most basic way to receive keyboard input from users. The value entered by the user is always returned as a string (str) type.

`input()` 함수는 사용자로부터 키보드 입력을 받는 가장 기본적인 방법입니다. 사용자가 입력한 값은 항상 문자열(str) 타입으로 반환됩니다.

### Basic Usage (기본 사용법)

```python
# Basic input (기본 입력)
name = input("Enter your name: ")
print(f"Hello, {name}!")

# Input without prompt (입력 프롬프트 없이 사용)
age = input()
print(f"Your age: {age}")
```

An input prompt is a message that guides users on what to input. Providing a clear prompt allows users to use the program easily.

입력 프롬프트는 사용자에게 무엇을 입력해야 하는지 안내하는 메시지입니다. 명확한 프롬프트를 제공하면 사용자가 프로그램을 쉽게 사용할 수 있습니다.

### Converting Input Value Types (입력값 타입 변환)

As learned earlier, `input()` always returns a string, so if numeric calculations are needed, you must convert to the appropriate type.

앞에서 배웠듯이 `input()`은 항상 문자열을 반환하므로, 숫자 계산이 필요하면 적절한 타입으로 변환해야 합니다.

```python
# Get string input (문자열로 입력받기)
name = input("Name: ")

# Convert to integer (정수로 변환)
age = int(input("Age: "))
height = int(input("Height (cm): "))

# Convert to float (실수로 변환)
weight = float(input("Weight (kg): "))
temperature = float(input("Temperature: "))

# Use in calculations (계산에 활용)
bmi = weight / ((height / 100) ** 2)
print(f"BMI: {bmi:.2f}")
```



---

## 2️⃣ Getting Multiple Values Simultaneously (여러 값 동시 입력받기)

Sometimes you need to receive multiple values at once. You can use the `split()` method to separate values separated by spaces.

때로는 여러 값을 한 번에 입력받아야 할 때가 있습니다. `split()` 메서드를 활용하면 공백으로 구분된 값들을 분리할 수 있습니다.

```python
# Get multiple values separated by space (공백으로 구분된 여러 값 입력받기)
name, age, city = input("Enter name, age, city (separated by space): ").split()
age = int(age)  # Convert age to integer (나이를 정수로 변환)

print(f"Name: {name}")
print(f"Age: {age}")
print(f"City: {city}")

# Get comma-separated values (쉼표로 구분된 값 입력받기)
fruits = input("Enter fruits (separated by comma): ").split(",")
# Remove extra whitespace (공백 제거)
fruits = [fruit.strip() for fruit in fruits]

print("Fruits:")
for fruit in fruits:
    print(f"  - {fruit}")
```

---

## 3️⃣ Output and Formatting (출력과 포매팅)

The `print()` function outputs values to the screen. You can control the output format in various ways.

`print()` 함수는 값을 화면에 출력합니다. 출력 형식을 다양한 방법으로 조절할 수 있습니다.

### Basic Output Control (기본 출력 제어)

```python
# Default behavior (기본 동작)
print("Apple", "Banana", "Cherry")  # Apple Banana Cherry (space-separated)

# Change separator (구분자 변경)
print("Apple", "Banana", "Cherry", sep=",")  # Apple,Banana,Cherry

# Change end character (끝 문자 변경)
print("Hello", end="!")  # Hello! (no newline)
print("Welcome")  # Prints on same line

# Multiple lines (여러 줄)
print("Line 1\nLine 2\nLine 3")  # Separate lines with \n
```

### Formatting Numbers (숫자 포매팅)

```python
# Basic number formatting (기본 숫자 포매팅)
price = 1234.567
print(f"Price: ${price:.2f}")  # Price: $1234.57

# Alignment and padding (정렬 및 패딩)
print(f"{10:5d}")      # Right-align in 5 spaces (오른쪽 정렬)
print(f"{10:<5d}")     # Left-align in 5 spaces (왼쪽 정렬)
print(f"{10:^5d}")     # Center-align in 5 spaces (중앙 정렬)

# Comma separator (쉼표 구분)
big_number = 1000000
print(f"{big_number:,}")  # 1,000,000

# Percentage (백분율)
score = 0.85
print(f"Score: {score:.1%}")  # Score: 85.0%
```


---

## 4️⃣ Creating Nice Output Formats (보기 좋은 출력 만들기)

Creating nicely formatted output makes programs more professional and easier to use.

보기 좋게 포매팅된 출력은 프로그램을 더 전문적이고 사용하기 쉽게 만듭니다.

### Using String Repetition (문자열 반복 활용)

```python
# Create dividers (구분선 만들기)
print("=" * 40)
print("=" * 40)
print("-" * 40)

# Create borders (테두리 만들기)
print("+" + "-" * 38 + "+")
print("|" + " " * 38 + "|")
print("|" + "Welcome".center(38) + "|")
print("|" + " " * 38 + "|")
print("+" + "-" * 38 + "+")
```

## 📝 Summary of Key Concepts (핵심 개념 정리)

The `input()` function receives keyboard input and always returns a string. To perform numeric calculations, you must convert using `int()` or `float()`. Multiple values can be received at once using `split()`.

`input()` 함수는 키보드 입력을 받으며 항상 문자열을 반환합니다. 숫자 계산을 하려면 `int()` 또는 `float()`로 변환해야 합니다. `split()`을 사용하면 여러 값을 한 번에 받을 수 있습니다.

The `print()` function outputs values, and you can control output using parameters like `sep` and `end`. F-strings provide clear and concise formatting, allowing you to control decimal places, padding, and alignment. Well-formatted output makes programs more professional and user-friendly.

`print()` 함수는 값을 출력하며, `sep`과 `end` 같은 파라미터로 출력을 제어할 수 있습니다. f-문자열은 명확하고 간결한 포매팅을 제공하여 소수점, 패딩, 정렬을 조절할 수 있습니다. 보기 좋게 포매팅된 출력은 프로그램을 더욱 전문적이고 사용자 친화적으로 만듭니다.

---

## 💡 Practical Assignments (실습 과제)

### Assignment 1: Family Information Form (과제 1: 가족 정보 입력 양식)

Write a program that receives family member information and displays it nicely formatted.

가족 구성원 정보를 입력받아 보기 좋게 표시하는 프로그램을 작성하세요.

```python
# Get family information (가족 정보 입력)
family_name = input("Family name: ")
num_members = int(input("Number of family members: "))

members = []
for i in range(num_members):
    name = input(f"Member {i+1} name: ")
    age = int(input(f"Member {i+1} age: "))
    members.append((name, age))

# Display family information (가족 정보 표시)
# Format nicely and display each member
```

### Assignment 2: Sales Record System (과제 2: 판매 기록 시스템)

Write a program that records sales data and displays a summary.

판매 기록을 입력받아 요약을 표시하는 프로그램을 작성하세요.

```python
# Get number of items to record (기록할 항목 개수 입력)
num_items = int(input("How many items sold: "))

# Record each sale (각 판매 기록)
# - Product name
# - Unit price
# - Quantity sold

# Display summary (요약 표시)
# - Total revenue
# - Average price
# - Total items sold
```

---

## ✅ Quiz (퀴즈)

### [Beginner] Question 1

What is the data type of the value returned by input()?

input()으로 받은 값의 데이터 타입은?

1. int
2. float
3. str
4. bool

### [Intermediate] Question 2

What is the output?

다음의 결과는?

```python
name = "Alex"
print(f"Name: {name}")
```

1. Name: Alex
2. Name: {name}
3. f"Name: Alex"
4. Error

### [Intermediate] Question 3

What does the following code do?

다음 코드는 무엇을 하는가?

```python
values = input("Enter values: ").split()
```

1. Receives a single value
2. Receives multiple space-separated values
3. Receives comma-separated values
4. Error

### [Intermediate] Question 4

What is the output?

다음의 결과는?

```python
price = 1234.567
print(f"${price:.2f}")
```

1. $1234.567
2. $1234.57
3. $1235
4. $1234

---

## 🔑 Quiz Answers and Explanations (퀴즈 정답 및 해설)

**Question 1 Answer: 3**
The `input()` function always returns a string type, regardless of what the user enters. To use numeric values, you must convert them using `int()` or `float()`.

`input()` 함수는 사용자가 입력한 내용과 관계없이 항상 문자열 타입을 반환합니다. 숫자 값을 사용하려면 `int()` 또는 `float()`으로 변환해야 합니다.

**Question 2 Answer: 1**
F-strings substitute variable values directly. `{name}` is replaced with "Alex", resulting in "Name: Alex".

f-문자열은 변수 값을 직접 치환합니다. `{name}`이 "Alex"로 바뀌어 "Name: Alex"가 됩니다.

**Question 3 Answer: 2**
The `split()` method without arguments splits by whitespace, separating space-separated values into a list.

`split()` 메서드는 인자 없이 공백으로 분리하여 공백으로 구분된 값들을 리스트로 분리합니다.

**Question 4 Answer: 2**
The format specification `:.2f` means display as a float with 2 decimal places. $1234.567 becomes $1234.57 (rounded).

포매팅 스펙 `:.2f`는 소수점 2자리까지 표시하는 실수를 의미합니다. $1234.567은 $1234.57로 반올림됩니다.

---

## 🎯 Preview of Next Chapter (다음 장 예고)

In the next chapter, we will learn about conditional statements. Using `if`, `elif`, and `else`, we will learn how to make programs execute different code based on different conditions. Conditional statements are fundamental to programming logic and allow programs to make intelligent decisions.

다음 장에서는 조건문에 대해 배웁니다. `if`, `elif`, `else`를 사용하여 조건에 따라 다른 코드를 실행하는 방법을 학습하게 됩니다.

---

Thank you for your attention.   
Cho Jeonghyun ([peterchokr@gmail.com](mailto:peterchokr@gmail.com)). Yeungnam University College

"Produced in collaboration with Claude and Gemini."
