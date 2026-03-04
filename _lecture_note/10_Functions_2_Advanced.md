# Chapter 10. Functions 2 (Advanced)

---

## 📚 Learning Objectives

After completing this chapter, you will understand and apply advanced function features including multiple return values, variable scope, lambda functions, and recursive functions. These concepts are essential for writing more efficient and powerful programs.

이번 장을 마치면 여러분은 다중 반환값, 변수의 스코프, 람다 함수, 재귀 함수 등 함수의 고급 기능을 이해하고 활용할 수 있습니다. 이러한 개념들은 더욱 효율적이고 강력한 프로그램을 작성하는 데 필수적입니다.

---

## 1️⃣ Multiple Return Values (여러 값 반환하기)

Python functions can return multiple values simultaneously.

파이썬 함수는 여러 개의 값을 동시에 반환할 수 있습니다.

```python
# Multiple value return (여러 값 반환)
def get_min_max(a, b, c):
    max_value = a
    if b > max_value:
        max_value = b
    if c > max_value:
        max_value = c
  
    min_value = a
    if b < min_value:
        min_value = b
    if c < min_value:
        min_value = c
  
    return min_value, max_value

# Receive multiple values (여러 값 받기)
minimum, maximum = get_min_max(10, 5, 20)
print(f"Minimum: {minimum}")  # 5
print(f"Maximum: {maximum}")  # 20
```

## 2️⃣ Variable Scope (변수의 스코프)

Variable scope refers to the range where a variable can be accessed.

변수의 스코프는 변수가 접근 가능한 범위를 의미합니다.

### Local Variables (지역 변수)

Variables created inside a function can only be used inside that function.

함수 안에서 만든 변수는 함수 안에서만 사용할 수 있습니다.

```python
def my_function():
    local_var = 10  # Local variable (지역 변수)
    print(local_var)

my_function()  # 10
# print(local_var)  # Error! Cannot access outside function (오류! 함수 밖에서 접근 불가)
```

### Global Variables (전역 변수)

Variables created outside a function can be used throughout the program.

함수 밖에서 만든 변수는 프로그램 전체에서 사용할 수 있습니다.

```python
global_var = 100  # Global variable (전역 변수)

def my_function():
    print(global_var)  # Can read global variable (전역 변수 읽기 가능)

my_function()  # 100
print(global_var)  # 100
```

### Modifying Global Variables (전역 변수 수정하기)

To modify a global variable inside a function, use the `global` keyword.

함수 안에서 전역 변수를 수정하려면 `global` 키워드를 사용해야 합니다.

```python
count = 0  # Global variable (전역 변수)

def increment():
    global count  # Declare use of global variable (전역 변수 사용 선언)
    count = count + 1

print(count)  # 0
increment()
print(count)  # 1
increment()
print(count)  # 2
```

⚠️ **Warning**: Overusing global variables makes code complex and error-prone. Use parameters and return values when possible!

⚠️ **주의**: 전역 변수를 남용하면 코드가 복잡해지고 버그가 생기기 쉽습니다. 가능하면 매개변수와 반환값을 사용하세요!


---

## 3️⃣ Lambda Functions (람다 함수)

Lambda functions are small anonymous functions useful for simple operations.

람다 함수는 간단한 작업에 유용한 작은 이름 없는 함수입니다.

### Basic Syntax (기본 문법)

```python
# Lambda function syntax (람다 함수 문법)
lambda parameters: expression

# Example (예제)
square = lambda x: x * x
print(square(5))  # 25

add = lambda x, y: x + y
print(add(3, 4))  # 7
```

### Use with Built-in Functions (내장 함수와 함께 사용)

```python
# map: Apply function to all elements (모든 요소에 함수 적용)
numbers = [1, 2, 3, 4, 5]
squared = list(map(lambda x: x ** 2, numbers))
print(squared)  # [1, 4, 9, 16, 25]

# filter: Keep elements that satisfy condition (조건을 만족하는 요소만 유지)
numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
evens = list(filter(lambda x: x % 2 == 0, numbers))
print(evens)  # [2, 4, 6, 8, 10]

# sorted: Sort with custom key (커스텀 키로 정렬)
students = [("Alice", 85), ("Bob", 75), ("Charlie", 90)]
sorted_students = sorted(students, key=lambda x: x[1], reverse=True)
print(sorted_students)  # [('Charlie', 90), ('Alice', 85), ('Bob', 75)]
```


---

## 4️⃣ Recursive Functions (재귀 함수)

A recursive function is a function that calls itself to solve problems.

재귀 함수는 자기 자신을 호출하여 문제를 해결하는 함수입니다.

### Basic Structure (기본 구조)

```python
# Recursive function structure (재귀 함수 구조)
def recursive_function(parameter):
    # Base case: when to stop (기저 사례: 언제 멈출 것인가)
    if condition:
        return result
  
    # Recursive case: call itself (재귀 사례: 자신을 호출)
    return recursive_function(modified_parameter)
```

### Example: Factorial (예제: 팩토리얼)

```python
# Factorial using recursion (재귀를 사용한 팩토리얼)
def factorial(n):
    # Base case (기저 사례)
    if n == 0 or n == 1:
        return 1
  
    # Recursive case (재귀 사례)
    return n * factorial(n - 1)

print(factorial(5))  # 120
print(factorial(10))  # 3628800
```


---

## 5️⃣ *args and **kwargs (*args와 **kwargs)

These allow functions to accept a variable number of arguments.

이들은 함수가 가변 개수의 인자를 받을 수 있게 합니다.

### *args: Variable Positional Arguments (*args: 가변 위치 인자)

```python
# *args: Variable number of positional arguments (*args: 가변 위치 인자)
def add_all(*args):
    total = 0
    for num in args:
        total = total + num
    return total

print(add_all(1, 2, 3))  # 6
print(add_all(1, 2, 3, 4, 5))  # 15
```

### **kwargs: Variable Keyword Arguments (**kwargs: 가변 키워드 인자)

```python
# **kwargs: Variable number of keyword arguments (**kwargs: 가변 키워드 인자)
def print_info(**kwargs):
    for key, value in kwargs.items():
        print(f"{key}: {value}")

print_info(name="Alice", age=25, city="New York")
# Output (출력):
# name: Alice
# age: 25
# city: New York
```



---

## 📝 Summary of Key Concepts (핵심 개념 정리)

Functions can return multiple values as tuples. Variable scope determines where variables can be accessed: local variables exist only in functions, while global variables can be accessed throughout the program.

함수는 튜플로 여러 값을 반환할 수 있습니다. 변수의 스코프는 변수가 접근 가능한 범위를 결정하며, 지역 변수는 함수 내에서만 존재하고 전역 변수는 프로그램 전체에서 접근 가능합니다.

Lambda functions are useful for simple, short operations. Recursive functions call themselves to solve problems and must have a base case to prevent infinite loops. *args and **kwargs allow flexible functions that accept variable numbers of arguments.

람다 함수는 간단한 작업에 유용하며, 재귀 함수는 자기 자신을 호출하여 문제를 해결하며 무한 루프를 방지하기 위해 기저 사례가 필요합니다. *args와 **kwargs는 가변 개수의 인자를 받을 수 있는 유연한 함수를 만듭니다.

---

## 💡 Practical Assignments (실습 과제)

### Assignment 1: Grade Calculator with Multiple Returns (과제 1: 여러 값 반환 성적 계산기)

Write a function that calculates total, average, and highest score at once.

총점, 평균, 최고점을 한 번에 계산하는 함수를 작성하세요.

```python
# Hint
def analyze_scores(scores):
    # Calculate total, average, highest
    # Return all three values
    return total, average, highest
```

### Assignment 2: Recursive Sum Calculator (과제 2: 재귀 합 계산기)

Write a recursive function that calculates the sum from 1 to n.

1부터 n까지의 합을 계산하는 재귀 함수를 작성하세요.

```python
# Hint
def sum_n(n):
    # Base case
    if n == 0:
        return 0
    # Recursive case
    return n + sum_n(n - 1)
```

---

## ✅ Quiz (퀴즈)

### [Intermediate] Question 1

What is the output?

다음 코드의 출력 결과는?

```python
def get_values():
    return 10, 20, 30

a, b, c = get_values()
print(a + b + c)
```

1. 10
2. 20
3. 60
4. Error

### [Intermediate] Question 2

What is the output?

다음 코드의 출력 결과는?

```python
count = 5

def increment():
    global count
    count = count + 10

increment()
print(count)
```

1. 5
2. 10
3. 15
4. Error

### [Intermediate] Question 3

What is the output?

다음 코드의 출력 결과는?

```python
numbers = [1, 2, 3, 4, 5]
squared = list(map(lambda x: x ** 2, numbers))
print(squared)
```

1. [1, 4, 9, 16, 25]
2. [2, 4, 6, 8, 10]
3. [1, 2, 3, 4, 5]
4. Error

### [Advanced] Question 4

What is the output?

다음 코드의 출력 결과는?

```python
def factorial(n):
    if n <= 1:
        return 1
    return n * factorial(n - 1)

print(factorial(4))
```

1. 4
2. 24
3. 12
4. Error

### [Advanced] Question 5

What is the output?

다음 코드의 출력 결과는?

```python
def sum_all(*args):
    return sum(args)

print(sum_all(1, 2, 3, 4, 5))
```

1. 5
2. 15
3. 1 2 3 4 5
4. (1, 2, 3, 4, 5)

---

## 🔑 Quiz Answers and Explanations (퀴즈 정답 및 해설)

**Question 1 Answer: 3**
The function returns a tuple (10, 20, 30). When unpacked, a=10, b=20, c=30. Sum: 10+20+30=60

함수는 (10, 20, 30) 튜플을 반환합니다. a=10, b=20, c=30이 되고, 합은 60입니다.

**Question 2 Answer: 3**
The global keyword allows the function to modify the global count variable. count starts at 5, increment() adds 10, so count becomes 15.

global 키워드로 전역 변수 count를 수정할 수 있습니다. count가 5에서 15로 변경됩니다.

**Question 3 Answer: 1**
The lambda function squares each element. [1², 2², 3², 4², 5²] = [1, 4, 9, 16, 25]

람다 함수가 각 요소를 제곱합니다. [1, 4, 9, 16, 25]

**Question 4 Answer: 2**
factorial(4) = 4 × factorial(3) = 4 × 3 × 2 × 1 = 24

factorial(4) = 4 × 3 × 2 × 1 = 24입니다.

**Question 5 Answer: 2**
*args collects all arguments into a tuple (1, 2, 3, 4, 5). sum() calculates the total: 1+2+3+4+5=15

*args는 모든 인자를 튜플로 모으고, sum()은 1+2+3+4+5=15를 계산합니다.

---

## 🎯 Preview of Next Chapter (다음 장 예고)

In the next chapter, we will learn about lists. Lists are the most commonly used data structure in Python and allow you to store multiple values efficiently. Understanding lists is crucial for data processing!

다음 장에서는 리스트에 대해 배웁니다. 리스트는 파이썬에서 가장 많이 사용되는 자료구조이며 여러 값을 효율적으로 저장할 수 있게 해줍니다.

---

Thank you for your attention.  
Cho Jeonghyun ([peterchokr@gmail.com](mailto:peterchokr@gmail.com)). Yeungnam University College

"Produced in collaboration with Claude and Gemini."
