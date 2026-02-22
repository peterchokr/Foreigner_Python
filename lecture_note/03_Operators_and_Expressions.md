# Chapter 3. Operators and Expressions

---

## 📚 Learning Objectives

After completing this chapter, you will be able to perform calculations using various operators, judge conditions, and write complex expressions. Operators are fundamental tools of programming, and using them effectively allows you to create powerful programs.

이번 장을 마치면 여러분은 다양한 연산자를 사용하여 계산을 수행하고, 조건을 판단하며, 복잡한 표현식을 작성할 수 있게 됩니다. 연산자는 프로그래밍의 기본 도구이며, 이를 잘 활용하면 강력한 프로그램을 만들 수 있습니다.

---

## 1️⃣ Arithmetic Operators (산술 연산자)

Arithmetic operators are operators that perform mathematical calculations. Just as we use a calculator in our daily lives to perform addition, subtraction, multiplication, division, and other basic operations, programming also allows us to perform these calculations.

산술 연산자는 수학 계산을 수행하는 연산자입니다. 우리가 일상생활에서 계산기를 사용할 때처럼, 프로그래밍에서도 덧셈, 뺄셈, 곱셈, 나눗셈 등의 기본 연산을 수행할 수 있습니다.

### Basic Arithmetic Operators (기본 산술 연산자)

Python provides the following arithmetic operators:

파이썬은 다음과 같은 산술 연산자를 제공합니다.

```python
# Addition (+) (덧셈)
result = 10 + 5
print(result)  # 15

# Subtraction (-) (뺄셈)
result = 10 - 5
print(result)  # 5

# Multiplication (*) (곱셈)
result = 10 * 5
print(result)  # 50

# Division (/) (나눗셈)
result = 10 / 3
print(result)  # 3.3333333333333335 (always returns float)
```

Remember that division (`/`) always returns a float. Even when dividing integers, the result is a float. For example, `10 / 2` results in `5.0`, not `5`.

나눗셈(`/`)은 항상 실수(float)를 반환한다는 점을 기억하세요. 정수끼리 나누더라도 결과는 실수입니다. 예를 들어 `10 / 2`의 결과는 `5`가 아니라 `5.0`입니다.

### Special Arithmetic Operators (특수 산술 연산자)

Python provides special operators with unique functions in addition to basic arithmetic operators.

파이썬은 일반적인 산술 연산자 외에도 특별한 기능을 가진 연산자들을 제공합니다.

```python
# Integer division or quotient (//) (정수 나눗셈 또는 몫)
result = 10 // 3
print(result)  # 3 (discards decimal portion)

# Remainder (%) (나머지)
result = 10 % 3
print(result)  # 1 (remainder of 10 divided by 3)

# Exponentiation (**) (거듭제곱)
result = 2 ** 3
print(result)  # 8 (2 to the power of 3)
```

Integer division (`//`) returns only the quotient of division and discards the decimal portion. The remainder operator (`%`) returns the remainder of division. These two operators are useful in many places such as determining even/odd numbers and checking multiples.

정수 나눗셈(`//`)은 나눗셈의 몫만 반환하며, 소수점 이하는 버립니다. 나머지 연산자(`%`)는 나눗셈의 나머지를 반환합니다. 이 두 연산자는 짝수/홀수 판별, 배수 확인 등 다양한 곳에서 유용하게 사용됩니다.

```
Arithmetic Operators Summary (산술 연산자 정리)

┌─────────────┬──────────┬─────────────┐
│ Operator    │ Symbol   │ Example     │
├─────────────┼──────────┼─────────────┤
│ Addition    │    +     │  10 + 3 = 13│
│ Subtraction │    -     │  10 - 3 = 7 │
│ Multiply    │    *     │  10 * 3 = 30│
│ Division    │    /     │  10 / 3 = 3.33│
│ Int Division│    //    │  10 // 3 = 3│
│ Remainder   │    %     │  10 % 3 = 1 │
│ Exponent    │    **    │  2 ** 3 = 8 │
└─────────────┴──────────┴─────────────┘
```

### Example 1: Online Store Discount Calculator (예제 1: 쇼핑몰 할인 계산기)

Let's create a program to calculate discounted prices when shopping online.

실생활에서 온라인 쇼핑을 할 때 할인가를 계산하는 프로그램을 만들어봅시다.

```python
# Online store discount calculator (쇼핑몰 할인 계산 프로그램)
print("=== Online Store Discount Calculator ===")

# Get product information (상품 정보 입력)
original_price = int(input("Original price: "))
discount_rate = int(input("Discount rate (example: 20): "))

# Calculate discount amount (할인 금액 계산)
discount_amount = original_price * discount_rate / 100

# Calculate final price (최종 가격 계산)
final_price = original_price - discount_amount

# Display results (결과 출력)
print(f"\nOriginal price: ${original_price:,}")
print(f"Discount rate: {discount_rate}%")
print(f"Discount amount: ${discount_amount:,.0f}")
print(f"Final price: ${final_price:,.0f}")
```

This program calculates the discount amount by multiplying the original price by the discount rate, and then calculates the final price by subtracting the discount amount from the original price. It's the same calculation method used in actual online stores.

이 프로그램은 원가에 할인율을 곱해서 할인 금액을 계산하고, 원가에서 할인 금액을 빼서 최종 가격을 구합니다. 실제 쇼핑몰 앱에서 사용하는 것과 같은 계산 방식입니다.

---

## 2️⃣ Comparison Operators (비교 연산자)

Comparison operators are operators that compare two values and return True (true) or False (false). They are very important when writing conditional statements.

비교 연산자는 두 값을 비교하여 참(True) 또는 거짓(False)을 반환하는 연산자입니다. 조건문을 작성할 때 매우 중요하게 사용됩니다.

### Basic Comparison Operators (기본 비교 연산자)

```python
# Equal (==) (같음)
print(5 == 5)   # True
print(5 == 3)   # False

# Not equal (!=) (같지 않음)
print(5 != 3)   # True
print(5 != 5)   # False

# Greater than (>) (크다)
print(5 > 3)    # True
print(3 > 5)    # False

# Less than (<) (작다)
print(3 < 5)    # True
print(5 < 3)    # False

# Greater than or equal to (>=) (크거나 같다)
print(5 >= 5)   # True
print(5 >= 3)   # True
print(3 >= 5)   # False

# Less than or equal to (<=) (작거나 같다)
print(3 <= 5)   # True
print(5 <= 5)   # True
print(5 <= 3)   # False
```

There is an important point to note when using comparison operators. Be careful not to confuse the assignment operator (`=`) with the comparison operator (`==`). The single equal sign is for assignment, while the double equal sign is for comparing whether two values are equal.

비교 연산자를 사용할 때 주의할 점이 있습니다. 등호(`=`)와 비교 연산자(`==`)를 혼동하지 말아야 합니다. 등호는 값을 할당하는 것이고, 이중 등호는 두 값이 같은지 비교하는 것입니다.

```python
# Incorrect (오류!)
x = 5
# if x = 10:  # Error! Assignment operator
#     print("x is 10")

# Correct (올바른 예)
if x == 10:  # Comparison operator
    print("x is 10")
```

### Example 2: Age Verification Program (예제 2: 나이 확인 프로그램)

This is a program that takes a user's age as input and determines whether they are an adult or minor.

사용자의 나이를 입력받아 성인인지 미성년자인지 판별하는 프로그램입니다.

```python
# Age verification system (나이 확인 프로그램)
print("=== Age Verification System ===")

age = int(input("Enter your age: "))

# Check if adult (성인 여부 확인)
is_adult = age >= 18

print(f"\nYour age: {age} years old")
print(f"Adult: {is_adult}")

if is_adult:
    print("You are an adult. You can access all content.")
else:
    print("You are a minor. Some content is restricted.")
```

---

## 3️⃣ Logical Operators (논리 연산자)

Logical operators are used to combine multiple conditions to create complex conditional statements. In everyday life, we use logic like "and", "or", and "not" to make decisions. Programming allows us to express this logic.

논리 연산자는 여러 조건을 결합하여 복잡한 조건식을 만들 때 사용합니다. 일상생활에서 "그리고", "또는", "아니다"와 같은 논리를 프로그래밍으로 표현하는 방법입니다.

### Basic Logical Operators (기본 논리 연산자)

Python provides three logical operators: `and`, `or`, `not`.

파이썬은 세 가지 논리 연산자를 제공합니다: `and`, `or`, `not`.

```python
# and operator - True only when both conditions are true (둘 다 참일 때만 True)
print(True and True)    # True
print(True and False)   # False
print(False and False)  # False

# or operator - True if either condition is true (둘 중 하나라도 참이면 True)
print(True or True)     # True
print(True or False)    # True
print(False or False)   # False

# not operator - True becomes False, False becomes True (참을 거짓으로, 거짓을 참으로)
print(not True)         # False
print(not False)        # True
```

Logical operators can be used together with comparison operators to create complex conditions.

논리 연산자는 비교 연산자와 함께 사용하여 복잡한 조건을 만들 수 있습니다.

```python
age = 25
has_license = True

# If 18 years old or older and has a license (18세 이상이고 면허가 있으면)
can_drive = age >= 18 and has_license
print(can_drive)  # True

# If less than 18 years old or doesn't have a license (18세 미만이거나 면허가 없으면)
cannot_drive = age < 18 or not has_license
print(cannot_drive)  # False
```

```
Logical Operators Truth Table (논리 연산자 진리표)

AND Operator
┌───────┬───────┬────────┐
│   A   │   B   │ A and B│
├───────┼───────┼────────┤
│ True  │ True  │  True  │
│ True  │ False │  False │
│ False │ True  │  False │
│ False │ False │  False │
└───────┴───────┴────────┘

OR Operator
┌───────┬───────┬────────┐
│   A   │   B   │ A or B │
├───────┼───────┼────────┤
│ True  │ True  │  True  │
│ True  │ False │  True  │
│ False │ True  │  True  │
│ False │ False │  False │
└───────┴───────┴────────┘

NOT Operator
┌───────┬────────┐
│   A   │ not A  │
├───────┼────────┤
│ True  │ False  │
│ False │ True   │
└───────┴────────┘
```

### Example 3: Grade Judgment System (예제 3: 학점 판정 시스템)

This is a program that evaluates a student's pass status by comprehensively considering attendance and test scores.

학생의 출석률과 시험 점수를 종합하여 합격 여부를 판정하는 프로그램입니다.

```python
# Grade judgment system (학점 판정 시스템)
print("=== Grade Judgment System ===")

# Get student information (학생 정보 입력)
attendance_rate = int(input("Attendance rate (0-100): "))
exam_score = int(input("Exam score (0-100): "))

# Pass condition: attendance >= 80% AND exam score >= 60 (합격 조건)
passed = attendance_rate >= 80 and exam_score >= 60

# Excellent student: attendance >= 95% AND exam score >= 90 (우수 학생)
excellent = attendance_rate >= 95 and exam_score >= 90

# Retake required: attendance < 80% OR exam score < 60 (재수강 대상)
retake = attendance_rate < 80 or exam_score < 60

# Display results (결과 출력)
print(f"\nAttendance rate: {attendance_rate}%")
print(f"Exam score: {exam_score}")
print(f"Passed: {passed}")
print(f"Excellent student: {excellent}")
print(f"Retake required: {retake}")

if excellent:
    print("Congratulations! You are an excellent student.")
elif passed:
    print("Congratulations! You have passed.")
else:
    print("You need to retake this course.")
```

---

## 4️⃣ Assignment Operators (대입 연산자)

Assignment operators are operators that store values in variables. In addition to the basic assignment operator (`=`), there are compound assignment operators that perform arithmetic operations and assignments simultaneously.

대입 연산자는 변수에 값을 저장하는 연산자입니다. 기본 대입 연산자(`=`) 외에도 산술 연산과 대입을 동시에 수행하는 복합 대입 연산자들이 있습니다.

### Compound Assignment Operators (복합 대입 연산자)

Compound assignment operators make code more concise when changing variable values.

복합 대입 연산자는 변수의 값을 변경할 때 코드를 간결하게 만들어줍니다.

```python
# Basic assignment (기본 대입)
x = 10

# Compound assignment operators (복합 대입 연산자)
x += 5   # Same as x = x + 5
print(x)  # 15

x -= 3   # Same as x = x - 3
print(x)  # 12

x *= 2   # Same as x = x * 2
print(x)  # 24

x /= 4   # Same as x = x / 4
print(x)  # 6.0

x //= 2  # Same as x = x // 2
print(x)  # 3.0

x %= 2   # Same as x = x % 2
print(x)  # 1.0

x **= 3  # Same as x = x ** 3
print(x)  # 1.0
```

Compound assignment operators are especially useful when incrementing counter variables or calculating cumulative sums.

복합 대입 연산자는 특히 카운터 변수를 증가시키거나 누적 합계를 계산할 때 자주 사용됩니다.

```python
# Accumulate scores (점수 누적 계산)
total_score = 0
total_score += 85  # First exam (첫 번째 시험)
total_score += 90  # Second exam (두 번째 시험)
total_score += 88  # Third exam (세 번째 시험)
print(f"Total: {total_score}")  # 263

# Increment counter (카운터 증가)
count = 0
count += 1  # Increase by 1
count += 1  # Increase by 1
count += 1  # Increase by 1
print(f"Count: {count}")  # 3
```

### Example 4: Game Score Calculation (예제 4: 게임 점수 계산)

This is a program that accumulates scores and increases level during a game.

게임에서 점수를 누적하고 레벨을 올리는 프로그램입니다.

```python
# Game score system (게임 점수 계산 프로그램)
print("=== Game Score System ===")

# Initialize (초기값 설정)
score = 0
level = 1

# Game progress (게임 진행)
print("Stage 1 Complete!")
score += 100
print(f"Current score: {score}")

print("\nBonus item obtained!")
score *= 2  # Double score (점수 2배)
print(f"Current score: {score}")

print("\nStage 2 Complete!")
score += 150
print(f"Current score: {score}")

# Check level up condition (300 points or more) (레벨업 조건 확인)
if score >= 300:
    level += 1
    print(f"\nLevel up! Current level: {level}")

print(f"\nFinal score: {score}")
print(f"Final level: {level}")
```

---

## 5️⃣ Operator Precedence (연산자 우선순위)

When there are multiple operators in one expression, there are defined rules about which operator is calculated first. This is called operator precedence. It's the same principle as in mathematics where we calculate multiplication and division before addition and subtraction.

하나의 표현식에 여러 연산자가 있을 때, 어떤 연산자를 먼저 계산할지 정해진 규칙이 있습니다. 이를 연산자 우선순위라고 합니다. 수학에서 곱셈과 나눗셈을 덧셈과 뺄셈보다 먼저 계산하는 것과 같은 원리입니다.

### Precedence Rules (우선순위 규칙)

Python's operator precedence from highest to lowest is:

파이썬의 연산자 우선순위는 다음과 같습니다 (위에서 아래로 높은 순서):

```
Operator Precedence (High → Low) (연산자 우선순위 높음 → 낮음)

1. ()          Parentheses (괄호)
2. **          Exponentiation (거듭제곱)
3. *, /, //, % Multiplication, Division, Int Division, Remainder (곱셈, 나눗셈, 정수 나눗셈, 나머지)
4. +, -        Addition, Subtraction (덧셈, 뺄셈)
5. ==, !=, >, <, >=, <=  Comparison Operators (비교 연산자)
6. not         Logical NOT (논리 부정)
7. and         Logical AND (논리 AND)
8. or          Logical OR (논리 OR)
```

```python
# Operator precedence examples (연산자 우선순위 예제)
result = 2 + 3 * 4
print(result)  # 14 (multiply first: 2 + 12)

result = (2 + 3) * 4
print(result)  # 20 (parentheses first: 5 * 4)

result = 10 - 5 - 2
print(result)  # 3 (left to right: (10 - 5) - 2)

result = 2 ** 3 ** 2
print(result)  # 512 (right to left: 2 ** (3 ** 2) = 2 ** 9)
```

When writing complex expressions, it's good to use parentheses to make it clear. Parentheses have the highest priority, so operations inside parentheses are performed first.

복잡한 표현식을 작성할 때는 괄호를 사용하여 명확하게 하는 것이 좋습니다. 괄호는 가장 높은 우선순위를 가지므로 괄호 안의 연산이 먼저 수행됩니다.

```python
# Complex calculation - Calculate average (복잡한 계산 - 평균 구하기)
english = 85
history = 90
math = 88

# Incorrect method (priority issue) (잘못된 방법 (우선순위 문제))
# average = english + history + math / 3  # Calculates math/3 first
# print(average)  # 204.33333... (incorrect result)

# Correct method (올바른 방법)
average = (english + history + math) / 3
print(average)  # 87.66666... (correct result)
```

### Example 5: Online Shopping Final Amount Calculation (예제 5: 온라인 쇼핑 최종 금액 계산)

This is a program that calculates the final payment amount considering product price, shipping fee, and discount coupon.

상품 가격, 배송비, 할인 쿠폰을 고려하여 최종 결제 금액을 계산하는 프로그램입니다.

```python
# Online shopping checkout calculator (온라인 쇼핑 최종 금액 계산)
print("=== Online Shopping Checkout Calculator ===")

# Get input (입력)
product_price = int(input("Product price: "))
quantity = int(input("Quantity: "))
shipping_fee = int(input("Shipping fee: "))
coupon_discount = int(input("Coupon discount: "))

# Calculate (mind operator precedence) (계산 (우선순위에 주의))
subtotal = product_price * quantity  # Product total (상품 금액)
total_before_discount = subtotal + shipping_fee  # Include shipping (배송비 포함)
final_price = total_before_discount - coupon_discount  # Apply coupon discount (쿠폰 할인)

# Check free shipping condition (50,000 or more) (무료 배송 조건 확인)
if subtotal >= 50000:
    final_price -= shipping_fee
    free_shipping = True
else:
    free_shipping = False

# Display results (결과 출력)
print(f"\nProduct total: ${subtotal:,}")
print(f"Shipping fee: ${shipping_fee:,}")
print(f"Coupon discount: ${coupon_discount:,}")
print(f"Free shipping: {free_shipping}")
print(f"Final payment: ${final_price:,}")
```

---

## 6️⃣ String Operations (문자열 연산)

In Python, you can use some operators not just on numbers but also on strings. You can easily concatenate or repeat strings.

파이썬에서는 숫자뿐만 아니라 문자열에도 일부 연산자를 사용할 수 있습니다. 문자열을 연결하거나 반복하는 작업을 쉽게 할 수 있습니다.

### String Concatenation (+) (문자열 연결)

Using the addition operator (`+`) on strings concatenates them together.

덧셈 연산자(`+`)를 문자열에 사용하면 두 문자열이 연결됩니다.

```python
# String concatenation (문자열 연결)
first_name = "Michael"
last_name = "Wilson"
full_name = last_name + " " + first_name
print(full_name)  # Wilson Michael

# Concatenate multiple strings (여러 문자열 연결)
greeting = "Hello, " + full_name + "!"
print(greeting)  # Hello, Wilson Michael!
```

You cannot directly concatenate strings and numbers. You must convert the number to a string first before concatenating.

문자열과 숫자를 직접 연결할 수는 없습니다. 숫자를 문자열로 변환한 후 연결해야 합니다.

```python
age = 20
# message = "My age is " + age  # Error!
message = "My age is " + str(age)  # Correct
print(message)  # My age is 20
```

### String Repetition (*) (문자열 반복)

Using the multiplication operator (`*`) with a string and an integer repeats the string.

곱셈 연산자(`*`)를 문자열과 정수에 사용하면 문자열이 반복됩니다.

```python
# String repetition (문자열 반복)
stars = "*" * 10
print(stars)  # **********

divider = "-" * 30
print(divider)  # ------------------------------

# Create pattern (패턴 만들기)
pattern = "♥" * 5
print(pattern)  # ♥♥♥♥♥
```

### Example 6: Receipt Printer Program (예제 6: 영수증 출력 프로그램)

This is a program that prints purchase receipts in a nicely formatted manner.

상품 구매 내역을 보기 좋은 형식의 영수증으로 출력하는 프로그램입니다.

```python
# Receipt generator (영수증 출력 프로그램)
print("=== Receipt Generator ===")

# Store information (상점 정보)
store_name = "Python Market"
store_address = "123 Python Street, San Francisco, CA"

# Get purchase information (구매 정보 입력)
product_name = input("Product: ")
unit_price = int(input("Unit price: "))
quantity = int(input("Quantity: "))

# Calculate (계산)
total_price = unit_price * quantity

# Print receipt (영수증 출력)
line = "=" * 40
print("\n" + line)
print(store_name.center(40))  # Center align (중앙 정렬)
print(store_address.center(40))
print(line)
print("Product".ljust(20) + "Qty".rjust(10) + "Price".rjust(10))
print(line)
print(product_name.ljust(20) + str(quantity).rjust(10) + f"${unit_price:,}".rjust(10))
print(line)
print("Total".ljust(30) + f"${total_price:,}".rjust(10))
print(line)
print("\nThank you!".center(40))
print(line)
```

---

## 📝 Summary of Key Concepts (핵심 개념 정리)

Operators are the fundamental tools for manipulating and calculating data. Arithmetic operators (+, -, *, /, //, %, **) perform mathematical calculations, while comparison operators (==, !=, >, <, >=, <=) compare two values and return Boolean values.

연산자는 데이터를 조작하고 계산하는 기본 도구입니다. 산술 연산자(+, -, *, /, //, %, **)는 수학적 계산을 수행하며, 비교 연산자(==, !=, >, <, >=, <=)는 두 값을 비교하여 불린 값을 반환합니다.

Logical operators (and, or, not) allow you to combine multiple conditions to create complex conditional statements. `and` is true when all conditions are true, `or` is true when at least one condition is true, and `not` reverses true and false.

논리 연산자(and, or, not)는 여러 조건을 결합하여 복잡한 조건식을 만들 수 있게 해줍니다. and는 모든 조건이 참일 때, or는 하나라도 참일 때, not은 참과 거짓을 반대로 바꿉니다.

Assignment operators store values in variables, and compound assignment operators (+=, -=, *=, /= etc.) perform calculations and assignments simultaneously. Operator precedence determines which operation is performed first: parentheses have the highest priority, followed by exponentiation, multiplication/division, addition/subtraction, comparison, and logical operators.

대입 연산자는 변수에 값을 저장하며, 복합 대입 연산자(+=, -=, *=, /= 등)는 계산과 대입을 동시에 수행합니다. 연산자 우선순위는 괄호가 가장 높고, 거듭제곱, 곱셈/나눗셈, 덧셈/뺄셈, 비교, 논리 연산자 순입니다.

You can also use the + operator to concatenate strings and the * operator to repeat strings. It's important to write complex expressions clearly using parentheses.

문자열에도 + 연산자로 연결하고 * 연산자로 반복할 수 있습니다. 복잡한 표현식은 괄호를 사용하여 명확하게 작성하는 것이 좋습니다.

---

## 💡 Practical Assignments (실습 과제)

### Assignment 1: Salary Calculation Program (과제 1: 급여 계산 프로그램)

Write a program that takes hourly wage, regular working hours, and night shift hours as input and calculates total salary. Night shift work is paid at 1.5 times the hourly wage.

시급, 근무 시간, 야간 근무 시간을 입력받아 총 급여를 계산하는 프로그램을 작성하세요. 야간 근무는 시급의 1.5배를 적용합니다.

```python
# Hint
hourly_wage = int(input("Hourly wage: "))
regular_hours = int(input("Regular working hours: "))
night_hours = int(input("Night shift hours: "))

# Write calculation code here
# Regular wage = hourly wage × regular hours
# Night wage = hourly wage × 1.5 × night hours
# Total wage = regular wage + night wage
```

### Assignment 2: Leap Year Determination Program (과제 2: 윤년 판별 프로그램)

Write a program that determines whether a given year is a leap year. Leap year conditions are:

연도를 입력받아 윤년인지 판별하는 프로그램을 작성하세요. 윤년 조건은 다음과 같습니다:

- Divisible by 4 and
- Not divisible by 100, or
- Divisible by 400

```python
# Hint
year = int(input("Enter year: "))

# Check leap year condition
is_leap_year = (year % 4 == 0 and year % 100 != 0) or (year % 400 == 0)

print(f"Is {year} a leap year? {is_leap_year}")
```

---

## ✅ Quiz (퀴즈)

### [Beginner] Question 1

What is the output of the following code?

다음 코드의 실행 결과는?

```python
x = 10
x += 5
print(x)
```

1. 10
2. 15
3. 5
4. Error

### [Intermediate] Question 2

Which one produces a different result?

다음 중 연산 결과가 다른 하나는?

```python
1) 10 / 2
2) float(10 // 2)
3) 5.0
4) 5
```

1. 1
2. 2
3. 3
4. 4

### [Intermediate] Question 3

What is the output of the following code?

다음 코드의 실행 결과는?

```python
result = 2 + 3 * 4
print(result)
```

1. 14
2. 20
3. 24
4. 11

### [Intermediate] Question 4

Which of the following returns True?

다음 중 True를 반환하는 것은?

```python
age = 25
has_license = True
```

1. age < 18 and has_license
2. age >= 18 or not has_license
3. not (age >= 18 and has_license)
4. age < 18 or not has_license

### [Advanced] Question 5

What is the output of the following code?

다음 코드의 실행 결과는?

```python
x = 10
y = 3
result = x % y == 1 and x // y > 2
print(result)
```

1. True
2. False
3. 1
4. Error

---

## 🔑 Quiz Answers and Explanations (퀴즈 정답 및 해설)

**Question 1 Answer: 2**
`x += 5` is the same as `x = x + 5`, so `x` becomes 10 + 5 = 15. Compound assignment operators perform calculations on the current value of the variable and store it back.

`x += 5`는 `x = x + 5`와 같으므로 `x`는 10 + 5 = 15가 됩니다. 복합 대입 연산자는 변수의 현재 값에 연산을 수행한 후 다시 저장합니다.

**Question 2 Answer: 4**

1) `10 / 2` returns 5.0 (float), 2) `10 // 2` returns 5 (int), 3) is 5.0 (float), 4) is 5 (int). Only 4 is integer type while the others are float type or float values. Regular division (`/`) always returns a float.

1번 `10 / 2`는 5.0(실수), 2번 `10 // 2`는 5(정수), 3번은 5.0(실수), 4번은 5(정수)입니다. 따라서 4번만 정수형이고 나머지는 모두 실수형이거나 실수 값입니다. 일반 나눗셈(`/`)은 항상 실수를 반환합니다.

**Question 3 Answer: 1**
According to operator precedence, multiplication is calculated first. `3 * 4 = 12`, then `2 + 12 = 14`. If it had been `(2 + 3) * 4`, the result would be 20.

연산자 우선순위에 따라 곱셈이 먼저 계산됩니다. `3 * 4 = 12`, 그 다음 `2 + 12 = 14`입니다. 만약 `(2 + 3) * 4`였다면 20이 됩니다.

**Question 4 Answer: 2**
`age >= 18` is True, `has_license` is True. (2) `True or not True` = `True or False` = True. (1) `False and True` = False, (3) `not (True and True)` = `not True` = False, (4) `False or False` = False.

`age >= 18`은 True, `has_license`는 True입니다. (2) `True or not True` = `True or False` = True입니다. (1) `False and True` = False, (3) `not (True and True)` = `not True` = False, (4) `False or False` = False입니다.

**Question 5 Answer: 1**
`x % y` is 10 % 3 = 1, `x // y` is 10 // 3 = 3. Therefore, `1 == 1 and 3 > 2` is `True and True`, which returns True. This problem includes arithmetic operations, comparison operations, and logical operations.

`x % y`는 10 % 3 = 1, `x // y`는 10 // 3 = 3입니다. 따라서 `1 == 1 and 3 > 2`는 `True and True`가 되어 True를 반환합니다. 이 문제는 산술 연산, 비교 연산, 논리 연산이 모두 포함된 복합 표현식입니다.

---

## 🎯 Preview of Next Chapter (다음 장 예고)

In the next chapter, we will learn in detail how to work with strings. We will learn string indexing, slicing, and various string methods to effectively process text data.

다음 장에서는 문자열을 다루는 방법에 대해 자세히 배웁니다. 문자열 인덱싱, 슬라이싱, 다양한 문자열 메서드를 사용하여 텍스트 데이터를 효과적으로 처리하는 방법을 학습하게 됩니다.

---

Thank you for your attention.

Cho Jeonghyun (peterchokr@gmail.com). Yeungnam University College
