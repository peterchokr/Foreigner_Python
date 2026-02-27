# Chapter 9. Functions 1 (Basics)

---

## 📚 Learning Objectives

After completing this chapter, you will be able to define and call functions, and write reusable code using parameters and return values. Functions are essential tools for organizing programs systematically.

이번 장을 마치면 여러분은 함수를 정의하고 호출할 수 있으며, 매개변수와 반환값을 활용하여 재사용 가능한 코드를 작성할 수 있습니다. 함수는 프로그램을 체계적으로 구성하는 핵심 도구입니다.

---

## 1️⃣ What is a Function? (함수란 무엇인가?)

A function is a block of code that performs a specific task. Like a recipe, once you create it, you can reuse it whenever you need it.

함수는 특정 작업을 수행하는 코드의 묶음입니다. 마치 요리 레시피처럼, 한 번 만들어두면 필요할 때마다 반복해서 사용할 수 있습니다.

```python
# Code without function (repetition) (함수 없이 반복되는 코드)
print("=" * 40)
print("Welcome!")
print("=" * 40)

# ... other code ...

print("=" * 40)
print("Welcome!")
print("=" * 40)

# ... another place ...

print("=" * 40)
print("Welcome!")
print("=" * 40)
```

```python
# With function (simple!) (함수로 만들면 간단!)
def show_welcome():
    print("=" * 40)
    print("Welcome!")
    print("=" * 40)

# Call whenever needed (필요할 때마다 호출)
show_welcome()
# ... other code ...
show_welcome()
# ... another place ...
show_welcome()
```

```
Function Concept (함수의 개념)

  Input (입력) → [ Function ] → Output (출력)
                     ↑
                 Code (코드)
```

---

## 2️⃣ Function Definition and Calling (함수 정의와 호출)

### Basic Structure (기본 구조)

```python
# Define function (함수 정의)
def function_name():
    code to execute (실행할 코드)
    code to execute (실행할 코드)

# Call function (함수 호출)
function_name()
```

### Simple Example (간단한 예제)

```python
# Greeting function (인사 함수)
def greet():
    print("Hello!")
    print("Nice to meet you!")

# Call function (함수 호출)
greet()
greet()

# Output (출력):
# Hello!
# Nice to meet you!
# Hello!
# Nice to meet you!
```

⚠️ **Important**: Just defining a function doesn't execute it. You must call it!

⚠️ **중요**: 함수는 정의만 해서는 실행되지 않습니다. 반드시 호출해야 합니다!

### Example 1: Menu Display (예제 1: 메뉴판 출력)

A function that displays a coffee shop menu.

카페 메뉴판을 출력하는 함수입니다.

```python
# Coffee shop menu display function (카페 메뉴 출력 함수)
def show_menu():
    print("☕" + "=" * 38 + "☕")
    print("   Coffee Shop Menu")
    print("☕" + "=" * 38 + "☕")
    print("\n[Hot Drinks]")
    print("  1. Americano ..................... $3")
    print("  2. Latte ....................... $4")
    print("  3. Cappuccino .................. $4")
    print("\n[Cold Drinks]")
    print("  4. Iced Americano .............. $3")
    print("  5. Iced Latte .................. $4")
    print("\n[Snacks]")
    print("  6. Croissant ................... $3")
    print("  7. Muffin ....................... $3")
    print("☕" + "=" * 38 + "☕")

# Call function (함수 호출)
show_menu()
```

---

## 3️⃣ Parameters and Arguments (매개변수와 인자)

Functions can receive input values called parameters.

함수는 매개변수라는 입력값을 받을 수 있습니다.

### Basic Structure (기본 구조)

```python
# Function with parameters (매개변수가 있는 함수)
def function_name(parameter1, parameter2):
    # Use parameters (매개변수 사용)
    code using parameters

# Call with arguments (인자를 함께 호출)
function_name(argument1, argument2)
```

### Example (예제)

```python
# Greeting function with parameter (매개변수가 있는 인사 함수)
def greet_person(name):
    print(f"Hello, {name}!")
    print(f"Nice to meet you, {name}!")

# Call with argument (인자와 함께 호출)
greet_person("Alice")
greet_person("Bob")
greet_person("Charlie")

# Output (출력):
# Hello, Alice!
# Nice to meet you, Alice!
# Hello, Bob!
# Nice to meet you, Bob!
# Hello, Charlie!
# Nice to meet you, Charlie!
```

### Example 2: Calculate Sum (예제 2: 합 계산)

A function that calculates the sum of two numbers.

두 수의 합을 계산하는 함수입니다.

```python
# Sum calculation function (합 계산 함수)
def calculate_sum(num1, num2):
    result = num1 + num2
    print(f"{num1} + {num2} = {result}")

# Call with different arguments (다른 인자로 호출)
calculate_sum(10, 5)
calculate_sum(100, 200)
calculate_sum(7, 3)

# Output (출력):
# 10 + 5 = 15
# 100 + 200 = 300
# 7 + 3 = 10
```

### Example 3: Discount Calculator (예제 3: 할인 계산)

A function that calculates discounted prices.

할인된 가격을 계산하는 함수입니다.

```python
# Discount calculator (할인 계산기)
def show_discount(product, original_price, discount_rate):
    discount_amount = original_price * (discount_rate / 100)
    final_price = original_price - discount_amount
  
    print(f"Product: {product}")
    print(f"Original price: ${original_price}")
    print(f"Discount: {discount_rate}% (-${discount_amount})")
    print(f"Final price: ${final_price}")
    print("-" * 40)

# Call with different products (다른 상품으로 호출)
show_discount("Laptop", 1000, 10)
show_discount("Monitor", 300, 20)
show_discount("Keyboard", 80, 15)
```

---

## 4️⃣ Return Values (반환값)

Functions can return a value using the `return` keyword.

함수는 `return` 키워드를 사용하여 값을 반환할 수 있습니다.

### Basic Structure (기본 구조)

```python
# Function that returns value (반환값이 있는 함수)
def function_name(parameter):
    result = # calculation (계산)
    return result  # Return value (값 반환)

# Use return value (반환값 사용)
value = function_name(argument)
```

### Example (예제)

```python
# Addition function (더하기 함수)
def add(num1, num2):
    result = num1 + num2
    return result  # Return result (결과 반환)

# Use return value (반환값 사용)
sum1 = add(10, 5)
sum2 = add(100, 200)

print(f"Sum 1: {sum1}")  # Output: Sum 1: 15
print(f"Sum 2: {sum2}")  # Output: Sum 2: 300
```

### Example 4: Grade Calculation (예제 4: 등급 계산)

A function that determines grade from a score.

점수에 따라 등급을 결정하는 함수입니다.

```python
# Grade determination function (등급 결정 함수)
def get_grade(score):
    if score >= 90:
        grade = "A"
    elif score >= 80:
        grade = "B"
    elif score >= 70:
        grade = "C"
    elif score >= 60:
        grade = "D"
    else:
        grade = "F"
  
    return grade  # Return grade (등급 반환)

# Use function (함수 사용)
score1 = 95
score2 = 75
score3 = 55

print(f"Score {score1} → Grade {get_grade(score1)}")
print(f"Score {score2} → Grade {get_grade(score2)}")
print(f"Score {score3} → Grade {get_grade(score3)}")

# Output (출력):
# Score 95 → Grade A
# Score 75 → Grade C
# Score 55 → Grade F
```

### Example 5: Rectangle Calculator (예제 5: 사각형 계산기)

A function that calculates area and perimeter of a rectangle.

사각형의 넓이와 둘레를 계산하는 함수입니다.

```python
# Rectangle area calculation (사각형 넓이 계산)
def calculate_area(width, height):
    area = width * height
    return area

# Rectangle perimeter calculation (사각형 둘레 계산)
def calculate_perimeter(width, height):
    perimeter = 2 * (width + height)
    return perimeter

# Use functions (함수 사용)
print("🔷 Rectangle Calculator")
print("=" * 40)

width = 10
height = 5

area = calculate_area(width, height)
perimeter = calculate_perimeter(width, height)

print(f"Width: {width}, Height: {height}")
print(f"Area: {area}")
print(f"Perimeter: {perimeter}")
print("=" * 40)
```

---

## 5️⃣ Multiple Return Values (여러 값 반환)

Functions can return multiple values.

함수는 여러 값을 반환할 수 있습니다.

```python
# Function returning multiple values (여러 값을 반환하는 함수)
def get_min_max(num1, num2, num3):
    minimum = min(num1, num2, num3)
    maximum = max(num1, num2, num3)
    return minimum, maximum  # Return multiple values (여러 값 반환)

# Use multiple return values (여러 값 사용)
min_value, max_value = get_min_max(10, 50, 30)

print(f"Minimum: {min_value}")
print(f"Maximum: {max_value}")

# Output (출력):
# Minimum: 10
# Maximum: 50
```

### Example 6: Age Group Classifier (예제 6: 나이 그룹 분류)

A function that classifies age groups and returns information.

나이 그룹을 분류하여 정보를 반환하는 함수입니다.

```python
# Age group classifier (나이 그룹 분류 함수)
def classify_age(age):
    if age < 13:
        group = "Child"
        category = "🧒"
    elif age < 18:
        group = "Teen"
        category = "👦"
    elif age < 65:
        group = "Adult"
        category = "👨"
    else:
        group = "Senior"
        category = "👴"
  
    return group, category  # Return multiple values (여러 값 반환)

# Use function (함수 사용)
print("👥 Age Classification System")
print("=" * 40)

ages = [10, 15, 30, 70]

for age in ages:
    group, emoji = classify_age(age)
    print(f"Age {age}: {emoji} {group}")

print("=" * 40)
```

---

## 6️⃣ Default Parameters (기본값 설정)

Parameters can have default values that are used if no argument is provided.

매개변수에 기본값을 설정하여 인자를 전달하지 않아도 되게 할 수 있습니다.

```python
# Function with default parameters (기본값이 있는 함수)
def greet_person(name, greeting="Hello"):
    print(f"{greeting}, {name}!")

# Call with both arguments (두 인자 모두 제공)
greet_person("Alice", "Hi")  # Output: Hi, Alice!

# Call with one argument (하나만 제공)
greet_person("Bob")  # Output: Hello, Bob!

# Call with one argument (하나만 제공)
greet_person("Charlie", "Good morning")  # Output: Good morning, Charlie!
```

### Example 7: Product Pricing (예제 7: 상품 가격책정)

A function for calculating product pricing with tax.

세금을 포함한 상품 가격 계산 함수입니다.

```python
# Product pricing function (상품 가격 계산 함수)
def calculate_price(product, base_price, tax_rate=0.08):
    tax = base_price * tax_rate
    total = base_price + tax
  
    print(f"Product: {product}")
    print(f"Base price: ${base_price}")
    print(f"Tax ({tax_rate*100:.0f}%): ${tax:.2f}")
    print(f"Total price: ${total:.2f}")
    print("-" * 40)

# Call with default tax rate (기본 세율로 호출)
calculate_price("Laptop", 1000)

# Call with custom tax rate (커스텀 세율로 호출)
calculate_price("Monitor", 300, 0.10)

# Call with default tax rate (기본 세율로 호출)
calculate_price("Keyboard", 80)
```

---

## 📝 Summary of Key Concepts (핵심 개념 정리)

A function is a reusable block of code that performs a specific task. Define functions using `def`, and call them by name. Functions can receive input values (parameters) and return output values (return values).

함수는 특정 작업을 수행하는 재사용 가능한 코드 블록입니다. `def`로 함수를 정의하고 이름으로 호출합니다. 함수는 입력값(매개변수)을 받고 출력값(반환값)을 반환할 수 있습니다.

Parameters are variables that receive values when a function is called. Multiple return values can be returned as a tuple. Default parameters allow functions to be called without all arguments.

매개변수는 함수가 호출될 때 값을 받는 변수입니다. 여러 반환값을 튜플로 반환할 수 있습니다. 기본값 설정으로 일부 인자 없이도 함수를 호출할 수 있습니다.

Well-designed functions make code more organized, readable, and maintainable. Functions also reduce code duplication by reusing code.

잘 설계된 함수는 코드를 더 체계적이고 읽기 쉽고 유지보수하기 편하게 만듭니다. 함수는 코드 중복을 제거하여 재사용성을 높입니다.

---

## 💡 Practical Assignments (실습 과제)

### Assignment 1: Calculator Functions (과제 1: 계산기 함수)

Write functions for addition, subtraction, multiplication, and division.

더하기, 빼기, 곱하기, 나누기 함수를 작성하세요.

```python
# Hint
def add(num1, num2):
    return num1 + num2

def subtract(num1, num2):
    return num1 - num2

# ... Create multiply and divide functions
# ... main program that uses these functions
```

### Assignment 2: Student Grade Statistics (과제 2: 학생 성적 통계)

Write a program using functions to calculate grade statistics.

함수를 사용하여 성적 통계를 계산하는 프로그램을 작성하세요.

```python
# Hint
def calculate_average(scores):
    # Calculate average (평균 계산)
    return average

def find_highest(scores):
    # Find highest score (최고점 찾기)
    return highest

# ... Main program using these functions
```

---

## ✅ Quiz (퀴즈)

### [Beginner] Question 1

How many times is "Hello" printed?

다음 코드의 출력 횟수는?

```python
def greet():
    print("Hello")

greet()
greet()
greet()
```

1. 1 time
2. 2 times
3. 3 times
4. 0 times

### [Intermediate] Question 2

What is the output?

다음 코드의 출력 결과는?

```python
def add(a, b):
    result = a + b
    return result

print(add(10, 5))
```

1. 10 5
2. 15
3. add(10, 5)
4. None

### [Intermediate] Question 3

What is the value of x?

다음 코드에서 x의 값은?

```python
def multiply(num1, num2):
    return num1 * num2

x = multiply(3, 4)
```

1. 3
2. 4
3. 12
4. 34

### [Advanced] Question 4

What is the output?

다음 코드의 출력 결과는?

```python
def get_info(name, age=20):
    print(f"{name} is {age} years old")

get_info("Alice")
get_info("Bob", 25)
```

1. Alice is 0 years old, Bob is 25 years old
2. Alice is 20 years old, Bob is 25 years old
3. Alice is 20 years old, Bob is 20 years old
4. Error

### [Advanced] Question 5

What is the output?

다음 코드의 출력 결과는?

```python
def get_values():
    return 10, 20

a, b = get_values()
print(a + b)
```

1. 10, 20
2. 1020
3. 30
4. Error

---

## 🔑 Quiz Answers and Explanations (퀴즈 정답 및 해설)

**Question 1 Answer: 3**
The function is called 3 times, so "Hello" is printed 3 times.

함수가 3번 호출되므로 "Hello"가 3번 출력됩니다.

**Question 2 Answer: 2**
The add function receives 10 and 5, adds them (15), and returns the result. print displays 15.

add 함수는 10과 5를 받아 더하고(15) 반환합니다. print는 15를 출력합니다.

**Question 3 Answer: 3**
The multiply function multiplies 3 × 4 and returns 12. x is assigned 12.

multiply 함수는 3 × 4를 계산하여 12를 반환합니다. x에는 12가 할당됩니다.

**Question 4 Answer: 2**
When get_info is called with just "Alice", the default age value 20 is used. When called with "Bob" and 25, age becomes 25.

get_info("Alice")를 호출하면 기본값 20이 사용됩니다. "Bob"과 25로 호출하면 age는 25가 됩니다.

**Question 5 Answer: 3**
get_values returns a tuple (10, 20). a gets 10 and b gets 20. a + b = 10 + 20 = 30.

get_values는 튜플(10, 20)을 반환합니다. a는 10, b는 20을 받습니다. a + b = 30입니다.

---

## 🎯 Preview of Next Chapter (다음 장 예고)

In the next chapter, we will learn advanced function concepts including variable scope, function documentation, and *args and **kwargs. We will learn how to create more flexible and powerful functions!

다음 장에서는 변수의 범위, 함수 문서화, *args와 **kwargs 등 함수의 고급 개념을 배웁니다.

---

Thank you for your attention.   
Cho Jeonghyun ([peterchokr@gmail.com](mailto:peterchokr@gmail.com)). Yeungnam University College

"Produced in collaboration with Claude and Gemini."
