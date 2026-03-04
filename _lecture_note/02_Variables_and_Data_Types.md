# Chapter 2. Variables and Data Types

---

## 📚 Learning Objectives

After completing this chapter, you will understand what variables are and be able to store and use various types of data in variables. You will also learn how to choose the appropriate type for different data and how to convert types when necessary.

이번 장을 마치면 여러분은 변수가 무엇인지 이해하고, 다양한 종류의 데이터를 변수에 저장하고 활용할 수 있게 됩니다. 또한 데이터의 종류에 따라 적절한 타입을 선택하고 필요시 타입을 변환하는 방법을 배우게 됩니다.

---

## 1️⃣ What is a Variable? (변수란 무엇인가?)

A variable is a space in programming to store data. You can think of a variable as a container with a label attached to it, just as we attach labels to boxes to store items. For example, to store a student's test score, you can create a variable named `score` and put the score value inside it.

변수(Variable)는 프로그래밍에서 데이터를 저장하는 공간입니다. 마치 우리가 물건을 보관하기 위해 상자에 라벨을 붙이듯이, 변수는 데이터를 담고 있는 상자에 이름을 붙인 것이라고 생각하면 됩니다. 예를 들어, 학생의 점수를 저장하려면 `score`라는 이름의 변수를 만들고 그 안에 점수 값을 넣을 수 있습니다.

Using variables, you no longer need to input the same value multiple times; you can use the value by simply referencing the variable name. Additionally, you can change the value stored in a variable while the program is running. This is why it's called a "variable"—because its value can change.

변수를 사용하면 같은 값을 여러 번 입력할 필요 없이 변수 이름만으로 그 값을 계속 사용할 수 있습니다. 또한 프로그램이 실행되는 동안 변수에 저장된 값을 바꿀 수도 있습니다. 이것이 바로 "변수"라고 부르는 이유입니다 - 값이 변할 수 있기 때문입니다.

```
The Concept of Variables (변수의 개념)

┌─────────────────────────┐
│ Variable Name: age      │  ← Label (The name we call it)
│ ┌───────────────────┐   │
│ │                   │   │
│ │        20         │   │  ← Stored value
│ │                   │   │
│ └───────────────────┘   │
│  Memory Space            │
└─────────────────────────┘
```

### Variable Declaration and Assignment (변수 선언과 할당)

In Python, creating a variable is very simple. You just need to assign a value to the variable using the equal sign (`=`). This equal sign does not mean equality as in mathematics, but rather "store the value on the right in the variable on the left."

파이썬에서 변수를 만드는 것은 매우 간단합니다. 등호(`=`)를 사용하여 변수에 값을 할당하기만 하면 됩니다. 이 등호는 수학에서의 같다는 의미가 아니라 "오른쪽 값을 왼쪽 변수에 저장하라"는 의미입니다.

```python
# Variable declaration and assignment (변수 선언과 값 할당)
age = 20
name = "Alex Johnson"
height = 175.5
is_student = True
```

In the above code, we stored the number 20 in a variable called `age`, and we stored the string "Alex Johnson" in a variable called `name`. You can also declare multiple variables in one line.

위 코드에서 `age`라는 변수에 숫자 20을 저장했고, `name`이라는 변수에 문자열 "Alex Johnson"을 저장했습니다. 한 번에 여러 변수를 선언할 수도 있습니다.

```python
# Declare multiple variables on one line (여러 변수를 한 줄에 선언)
x, y, z = 10, 20, 30

# Assign the same value to multiple variables (같은 값을 여러 변수에 할당)
a = b = c = 100
```

The value stored in a variable can be changed at any time. This is the core feature of variables.

변수에 저장된 값은 언제든지 바꿀 수 있습니다. 이것이 변수의 핵심 기능입니다.

```python
# Change variable value (변수 값 변경하기)
score = 85
print("Initial score:", score)

score = 95  # Change score to 95 (점수를 95로 변경)
print("Updated score:", score)
```

---

## 2️⃣ Variable Naming Rules (변수 이름 짓기 규칙)

There are rules that must be followed when naming variables. If you break these rules, your program will not run.

변수 이름을 지을 때는 반드시 따라야 하는 규칙들이 있습니다. 이 규칙을 어기면 프로그램이 실행되지 않습니다.

First, variable names can only use letters (a-z, A-Z), numbers (0-9), and underscores (_). Although Korean characters are technically possible, they are not recommended. Special characters (@, #, $ etc.) cannot be used.

첫째, 변수 이름은 영문자(a-z, A-Z), 숫자(0-9), 밑줄(_)만 사용할 수 있습니다. 한글도 기술적으로는 가능하지만 권장하지 않습니다. 특수문자(@, #, $ 등)는 사용할 수 없습니다.

Second, variable names cannot start with a number. `1st_place` is an invalid name, but `first_place` or `place_1` are valid names.

둘째, 변수 이름은 숫자로 시작할 수 없습니다. `1st_place`는 잘못된 이름이지만, `first_place`나 `place_1`은 올바른 이름입니다.

Third, Python reserved words (keywords) cannot be used as variable names. Reserved words are words that Python already uses with special meanings. For example, words like `if`, `for`, `while`, `print`, `True`, and `False`.

셋째, 파이썬의 예약어(keyword)는 변수 이름으로 사용할 수 없습니다. 예약어란 파이썬에서 이미 특별한 의미로 사용하고 있는 단어들입니다. 예를 들어 `if`, `for`, `while`, `print`, `True`, `False` 같은 단어들입니다.

Fourth, variable names are case-sensitive. `name`, `Name`, and `NAME` are all different variables.

넷째, 변수 이름은 대소문자를 구분합니다. `name`, `Name`, `NAME`은 모두 다른 변수입니다.

```python
# Valid variable names (올바른 변수 이름)
student_name = "Michael Wilson"
total_score = 100
_private_var = 42
myAge = 25

# Invalid variable names (that cause errors)
# (잘못된 변수 이름 (오류 발생))
# 2nd_student = "Sarah Williams"  # Cannot start with a number (숫자로 시작)
# my-name = "David Brown"         # Hyphens not allowed (하이픈 사용 불가)
# for = 10                        # Reserved word (예약어 사용 불가)
```

### Good Variable Naming Practices (좋은 변수 이름 짓기)

Following the rules is not enough. You should use meaningful names so that when others read your code or when you review your code later, they can easily understand what the variable represents.

규칙을 따르는 것만으로는 충분하지 않습니다. 다른 사람이 코드를 읽었을 때, 또는 나중에 자신이 다시 코드를 볼 때 쉽게 이해할 수 있도록 의미 있는 이름을 사용해야 합니다.

```python
# Bad example - Meaning is unclear (나쁜 예 - 의미를 알 수 없음)
a = 85
b = 90
c = 88

# Good example - Meaning is clear (좋은 예 - 의미가 명확함)
english_score = 85
history_score = 90
math_score = 88
```

Python generally recommends snake_case, which uses lowercase letters and underscores. This is a style where multiple words are separated by underscores.

파이썬에서는 일반적으로 소문자와 밑줄을 사용하는 스네이크 케이스(snake_case)를 권장합니다. 여러 단어를 연결할 때 밑줄로 구분하는 방식입니다.

```python
# Snake case (Python recommended) (스네이크 케이스 (Python 권장))
student_name = "Emily Davis"
total_count = 100
max_temperature = 35.5

# Camel case (mainly used in other languages) (카멜 케이스 (다른 언어에서 주로 사용))
studentName = "Emily Davis"
totalCount = 100
maxTemperature = 35.5
```

---

## 3️⃣ Data Type Varieties (데이터 타입의 종류)

In Python, there are several types of data that can be stored in variables. Each type has a different form of value it can store and different purposes. Just as we put beverages in cups and rice in rice containers, data should be stored in the type that matches its nature.

파이썬에서 변수에 저장할 수 있는 데이터는 여러 종류(타입)가 있습니다. 각 타입마다 저장할 수 있는 값의 형태와 사용 목적이 다릅니다. 마치 우리가 음료는 컵에, 쌀은 쌀통에 담듯이 데이터도 그 성격에 맞는 타입으로 저장해야 합니다.

```
Main Data Types (주요 데이터 타입)

┌──────────────────────────────────────┐
│  Integer (정수)    │  10, -5, 1000    │
├──────────────────────────────────────┤
│  Float (실수)      │  3.14, -0.5, 2.0 │
├──────────────────────────────────────┤
│  String (문자열)   │  "Hello", 'Hi'  │
├──────────────────────────────────────┤
│  Boolean (불린)    │  True, False     │
└──────────────────────────────────────┘
```

### Integer Type (int) (정수형)

Integer type is used to store numbers without decimal points. It is used to represent age, count, rank, and other whole numbers. This includes positive numbers, negative numbers, and zero.

정수형은 소수점이 없는 숫자를 저장하는 타입입니다. 나이, 개수, 순위 등을 표현할 때 사용합니다. 양수, 음수, 0 모두 정수형에 포함됩니다.

```python
# Integer type examples (정수형 변수 예제)
age = 20              # Age (나이)
student_count = 35    # Number of students (학생 수)
temperature = -5      # 5 degrees below zero (영하 5도)
year = 2024          # Year (연도)
```

Integers can store arbitrarily large numbers. Unlike other programming languages, Python has no limit on the size of integers.

정수는 아무리 큰 수도 저장할 수 있습니다. 다른 프로그래밍 언어와 달리 파이썬은 정수의 크기에 제한이 없습니다.

```python
# Store large numbers without problems (큰 숫자도 문제없이 저장)
population = 330000000           # Population (인구 3억 3천만)
national_debt = 1000000000000    # 1 trillion (1조)
```

### Float Type (Floating Point, float) (실수형)

Float type is used to store numbers with decimal points. It is used when precise values are needed, such as for height, weight, temperature, and amounts.

실수형은 소수점이 있는 숫자를 저장하는 타입입니다. 키, 몸무게, 온도, 금액 등 정확한 값이 필요할 때 사용합니다.

```python
# Float type examples (실수형 변수 예제)
height = 175.5        # Height: 175.5 cm (키 175.5cm)
weight = 68.3         # Weight: 68.3 kg (몸무게 68.3kg)
pi = 3.14159         # Pi (원주율)
temperature = 36.5    # Body temperature (체온)
```

Real numbers can also be expressed in scientific notation. This is useful for expressing very large or very small numbers.

실수는 과학적 표기법으로도 표현할 수 있습니다. 매우 크거나 작은 숫자를 표현할 때 유용합니다.

```python
# Scientific notation (과학적 표기법)
speed_of_light = 3.0e8    # 3.0 × 10^8 = 300,000,000
small_number = 1.5e-3     # 1.5 × 10^-3 = 0.0015
```

### String Type (str) (문자열)

String is the type used to store text data. It can store anything made of characters such as names, addresses, and messages. Strings are represented by enclosing them in double quotes (`"`) or single quotes (`'`).

문자열은 텍스트 데이터를 저장하는 타입입니다. 이름, 주소, 메시지 등 문자로 이루어진 모든 것을 저장할 수 있습니다. 문자열은 큰따옴표(`"`) 또는 작은따옴표(`'`)로 감싸서 표현합니다.

```python
# String type examples (문자열 변수 예제)
name = "Alex Johnson"
address = "New York, NY"
message = "Hello!"
empty_string = ""     # Empty string is also possible (빈 문자열도 가능)
```

Double quotes and single quotes have no functional difference, but they are useful when you need to include quotes within a string.

큰따옴표와 작은따옴표는 기능상 차이가 없지만, 문자열 안에 따옴표를 포함할 때 유용하게 사용할 수 있습니다.

```python
# Include quotes within strings (문자열 안에 따옴표 포함하기)
sentence1 = "He said, 'Hello!'"
sentence2 = 'She said, "Goodbye!"'
```

To store multiple lines of text, use triple quotes (`"""` or `'''`).

여러 줄의 문자열을 저장하려면 삼중 따옴표(`"""` 또는 `'''`)를 사용합니다.

```python
# Multi-line string (여러 줄 문자열)
poem = """
Life is a journey,
Full of challenges and opportunities,
Keep moving forward!
"""
```

### Boolean Type (bool) (불린형)

Boolean type can only have two values: True (true) or False (false). It is used to judge conditions or express states. Boolean values must be written with the first letter capitalized.

불린형은 참(True) 또는 거짓(False) 두 가지 값만 가질 수 있는 타입입니다. 조건을 판단하거나 상태를 표현할 때 사용합니다. 불린값은 반드시 첫 글자를 대문자로 써야 합니다.

```python
# Boolean type examples (불린형 변수 예제)
is_student = True       # Are you a student? (학생인가?)
is_adult = False        # Are you an adult? (성인인가?)
has_license = True      # Do you have a license? (면허가 있는가?)
is_raining = False      # Is it raining? (비가 오는가?)
```

Boolean type is mainly used in comparison operations and conditional statements.

불린형은 주로 비교 연산이나 조건문에서 많이 사용됩니다.

```python
# Result of comparison is boolean type (비교 연산의 결과는 불린형)
age = 20
is_adult = age >= 18    # True (20 is 18 or older)
is_teenager = age < 13  # False (20 is not less than 13)
```

---

## 4️⃣ Checking Data Type (타입 확인하기)

To check what type of data is stored in a variable, use the `type()` function. This function is very useful when writing programs.

변수에 저장된 데이터가 어떤 타입인지 확인하려면 `type()` 함수를 사용합니다. 이 함수는 프로그램을 작성할 때 매우 유용합니다.

```python
# Check various types (다양한 타입 확인하기)
age = 20
height = 175.5
name = "Emily Davis"
is_student = True

print(type(age))         # <class 'int'>
print(type(height))      # <class 'float'>
print(type(name))        # <class 'str'>
print(type(is_student))  # <class 'bool'>
```


---

## 5️⃣ Type Conversion (타입 변환하기)

Sometimes you need to convert data from one type to another. For example, you may need to convert a string received from a user to a number for calculation. This is called type conversion or type casting.

때로는 한 타입의 데이터를 다른 타입으로 변환해야 할 때가 있습니다. 예를 들어, 사용자로부터 입력받은 문자열을 숫자로 바꿔서 계산해야 하는 경우입니다. 이를 타입 변환(Type Conversion) 또는 타입 캐스팅(Type Casting)이라고 합니다.

### Convert to Integer: int() (정수로 변환: int())

Use the `int()` function to convert strings or floats to integers. When converting a float to an integer, the decimal portion is discarded (not rounded).

문자열이나 실수를 정수로 변환할 때 `int()` 함수를 사용합니다. 실수를 정수로 변환하면 소수점 이하는 버려집니다(반올림하지 않음).

```python
# Convert string to integer (문자열을 정수로 변환)
age_str = "25"
age_int = int(age_str)
print(age_int)        # 25
print(type(age_int))  # <class 'int'>

# Convert float to integer (discard decimal) (실수를 정수로 변환 (소수점 버림))
height = 175.8
height_int = int(height)
print(height_int)     # 175 (not 175.8)
```

### Convert to Float: float() (실수로 변환: float())

Use the `float()` function to convert strings or integers to floats.

문자열이나 정수를 실수로 변환할 때 `float()` 함수를 사용합니다.

```python
# Convert string to float (문자열을 실수로 변환)
price_str = "1500.50"
price_float = float(price_str)
print(price_float)    # 1500.5

# Convert integer to float (정수를 실수로 변환)
count = 10
count_float = float(count)
print(count_float)    # 10.0
```

### Convert to String: str() (문자열로 변환: str())

Use the `str()` function to convert numbers to strings. It's useful for printing and string concatenation.

숫자를 문자열로 변환할 때 `str()` 함수를 사용합니다. 출력이나 문자열 연결에 유용합니다.

```python
# Convert integer to string (정수를 문자열로 변환)
age = 20
age_str = str(age)
print(age_str)        # "20"
print(type(age_str))  # <class 'str'>

# Use for string concatenation (문자열 연결에 활용)
message = "My age is " + str(age) + " years old."
print(message)        # "My age is 20 years old."
```


---

## 6️⃣ Precautions When Using Variables (변수 사용시 주의사항)

There are several things to keep in mind when using variables. Being aware of these points helps prevent errors and write safer programs.

변수를 사용할 때 몇 가지 주의해야 할 점이 있습니다. 이러한 점들을 알아두면 오류를 예방하고 더 안전한 프로그램을 작성할 수 있습니다.

### Variable Initialization (변수 초기화)

You must assign a value to a variable before using it. Using a variable that hasn't been declared will cause an error.

변수를 사용하기 전에 반드시 값을 할당해야 합니다. 선언하지 않은 변수를 사용하면 오류가 발생합니다.

```python
# Incorrect - using uninitialized variable (잘못된 예 - 초기화하지 않은 변수 사용)
# print(score)  # NameError

# Correct - initialize variable before using (올바른 예 - 변수 초기화 후 사용)
score = 0
print(score)  # 0
```

### Type Conversion Precautions (타입 변환 주의사항)

Not all strings can be converted to numbers. If you try to convert a non-numeric string to `int()` or `float()`, an error occurs.

모든 문자열이 숫자로 변환될 수 있는 것은 아닙니다. 숫자가 아닌 문자열을 `int()`나 `float()`로 변환하려고 하면 오류가 발생합니다.

```python
# Correct conversion (올바른 변환)
num1 = int("100")      # Works normally (정상 작동)
num2 = float("3.14")   # Works normally (정상 작동)

# Incorrect conversion (causes error) (잘못된 변환 (오류 발생))
# num3 = int("hello")    # ValueError
# num4 = float("abc")    # ValueError
```

### Integer Division (정수 나눗셈)

In Python, division (`/`) always returns a float result. If you need integer division, use the `//` operator.

파이썬에서 나눗셈(`/`)은 항상 실수 결과를 반환합니다. 정수 나눗셈이 필요하면 `//` 연산자를 사용합니다.

```python
# Regular division (returns float) (일반 나눗셈 (실수 결과))
result1 = 10 / 3
print(result1)  # 3.3333333333333335

# Integer division (returns quotient only) (정수 나눗셈 (몫만 반환))
result2 = 10 // 3
print(result2)  # 3

# Modulo operation (remainder) (나머지 연산)
result3 = 10 % 3
print(result3)  # 1
```

---

## 📝 Summary of Key Concepts (핵심 개념 정리)

A variable is a space to store data, and values are assigned using the equal sign. Variable names can only use letters, numbers, and underscores, cannot start with a number, and reserved words cannot be used. Using meaningful variable names improves code readability.

변수는 데이터를 저장하는 공간으로, 등호를 사용하여 값을 할당합니다. 변수 이름은 영문자, 숫자, 밑줄만 사용할 수 있으며 숫자로 시작할 수 없고, 예약어는 사용할 수 없습니다. 의미 있는 변수 이름을 사용하면 코드의 가독성이 높아집니다.

The main data types in Python are integer (int), float (float), string (str), and boolean (bool). Each type stores different kinds of data, and you can check a variable's type using the `type()` function.

파이썬의 주요 데이터 타입에는 정수형(int), 실수형(float), 문자열(str), 불린형(bool)이 있습니다. 각 타입은 서로 다른 종류의 데이터를 저장하며, `type()` 함수로 변수의 타입을 확인할 수 있습니다.

Type conversion is performed using `int()`, `float()`, and `str()` functions. In particular, the `input()` function always returns a string, so if you want to do numeric calculations, you must convert to the appropriate type. Variables must be initialized before use, and trying to convert a non-numeric string to a number will cause an error.

타입 변환은 `int()`, `float()`, `str()` 함수를 사용하여 수행합니다. 특히 `input()` 함수는 항상 문자열을 반환하므로, 숫자 계산을 하려면 적절한 타입으로 변환해야 합니다. 변수는 사용하기 전에 반드시 초기화해야 하며, 숫자가 아닌 문자열을 숫자로 변환하려고 하면 오류가 발생합니다.

---

## 💡 Practical Assignments (실습 과제)

### Assignment 1: BMI Calculator Program (과제 1: BMI 계산 프로그램)

Write a program that takes a user's name, height (cm), and weight (kg) as input and calculates their BMI (Body Mass Index). The BMI formula is:

사용자로부터 이름, 키(cm), 몸무게(kg)를 입력받아 BMI(체질량지수)를 계산하는 프로그램을 작성하세요. BMI 공식은 다음과 같습니다:

```
BMI = Weight (kg) ÷ (Height (m))²
```

Hint: You need to convert height from cm to m (cm ÷ 100).

힌트: 키를 cm에서 m로 변환해야 합니다 (cm ÷ 100).

```python
# Write your code here
```

### Assignment 2: Currency Exchange Calculator (과제 2: 환율 계산기)

Write a program that receives an amount in USD and converts it to multiple currencies. (You can set exchange rates arbitrarily. For example: 1 USD = 1.50 CAD)

사용자로부터 USD 금액을 입력받아 여러 통화로 변환하는 프로그램을 작성하세요. (환율은 임의로 설정하세요. 예: 1달러 = 1.50 캐나다 달러)

```python
# Exchange rate settings (환율 설정)
CAD_RATE = 1.50  # 1 USD = 1.50 CAD
EUR_RATE = 0.92  # 1 USD = 0.92 EUR
GBP_RATE = 0.79  # 1 USD = 0.79 GBP

# Write your code here
```

---

## ✅ Quiz (퀴즈)

### [Beginner] Question 1

Which of the following is a valid variable name?

다음 중 올바른 변수 이름은?

1. 1st_place
2. my-name
3. student_age
4. for

### [Intermediate] Question 2

What is the output of the following code?

다음 코드의 실행 결과는?

```python
x = 10
y = 3
result = x / y
print(type(result))
```

1. `<class 'int'>`
2. `<class 'float'>`
3. `<class 'str'>`
4. `<class 'bool'>`

### [Intermediate] Question 3

What is the value of `total` in the following code?

다음 코드에서 `total`의 값은?

```python
price = "5000"
quantity = 3
total = int(price) * quantity
```

1. "500030"
2. 15000
3. "15000"
4. Error

### [Intermediate] Question 4

Which of the following is NOT a float type data?

다음 중 실수형(float) 데이터가 아닌 것은?

1. 3.14
2. 2.0
3. 1.5e2
4. 100

### [Advanced] Question 5

Choose all correct statements about the following code:

다음 코드의 실행 결과로 올바른 것을 모두 고르시오.

```python
a = 17
b = 5
print(a // b)  # Result 1
print(a % b)   # Result 2
print(a / b)   # Result 3
```

1. Result 1: 3
2. Result 2: 2
3. Result 3: 3.4
4. All correct

---

## 🔑 Quiz Answers and Explanations (퀴즈 정답 및 해설)

**Question 1 Answer: 3**
`student_age` is a valid variable name. (1) `1st_place` cannot start with a number, (2) `my-name` cannot use hyphens, (4) `for` is a Python reserved word.

`student_age`가 올바른 변수 이름입니다. (1) `1st_place`는 숫자로 시작하므로 불가능, (2) `my-name`은 하이픈을 사용할 수 없음, (4) `for`는 파이썬 예약어이므로 사용 불가능합니다.

**Question 2 Answer: 2**
In Python, the division operation (`/`) always returns a float type. `10 / 3 = 3.333...`, so the type is `<class 'float'>`. If you need an integer result, use the `//` operator.

파이썬에서 나눗셈(`/`) 연산의 결과는 항상 실수형(float)입니다. `10 / 3 = 3.333...`이므로 타입은 `<class 'float'>`입니다. 정수 결과가 필요하면 `//` 연산자를 사용해야 합니다.

**Question 3 Answer: 2**
`price` is a string "5000", but `int(price)` converts it to the integer 5000. Therefore, 5000 × 3 = 15000. If you hadn't converted with `int()`, the result would have been "500050005000" (string repetition).

`price`는 문자열 "5000"이지만 `int(price)`로 정수 5000으로 변환됩니다. 따라서 5000 × 3 = 15000이 됩니다. 만약 `int()`로 변환하지 않았다면 "500050005000"이 됩니다(문자열 반복).

**Question 4 Answer: 4**
100 is an integer type (int). (1) 3.14 is float, (2) 2.0 has a decimal point so it's float, (3) 1.5e2 is 150.0 in scientific notation, which is float.

100은 정수형(int)입니다. (1) 3.14, (2) 2.0은 소수점이 있으므로 실수형, (3) 1.5e2는 과학적 표기법으로 150.0을 의미하며 실수형입니다.

**Question 5 Answer: 4**
All are correct. (1) `17 // 5 = 3` (integer division, quotient), (2) `17 % 5 = 2` (remainder operation), (3) `17 / 5 = 3.4` (regular division, float result). Understanding the difference between these three division operators is important.

모두 맞습니다. (1) `17 // 5 = 3` (정수 나눗셈, 몫), (2) `17 % 5 = 2` (나머지 연산), (3) `17 / 5 = 3.4` (일반 나눗셈, 실수 결과). 이 세 가지 나눗셈 연산자의 차이를 정확히 이해하는 것이 중요합니다.

---

## 🎯 Preview of Next Chapter (다음 장 예고)

In the next chapter, you will learn about operators and expressions. You will learn how to use arithmetic operators, comparison operators, and logical operators to perform various calculations and make conditional judgments. Your understanding of variables and data types from this chapter will be the foundation for the next chapter, so review thoroughly!

다음 장에서는 연산자와 표현식에 대해 배웁니다. 산술 연산자, 비교 연산자, 논리 연산자를 사용하여 다양한 계산과 조건 판단을 수행하는 방법을 학습하게 됩니다. 이번 장에서 배운 변수와 데이터 타입에 대한 이해가 다음 장의 기초가 되므로 충분히 복습하세요!

---

Thank you for your attention.   
Cho Jeonghyun ([peterchokr@gmail.com](mailto:peterchokr@gmail.com)). Yeungnam University College

"Produced in collaboration with Claude and Gemini."
