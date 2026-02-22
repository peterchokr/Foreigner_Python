# Chapter 16. Modules and Packages

---

## 📚 Learning Objectives

After completing this chapter, you will be able to organize and reuse code systematically using modules and packages. You will learn how to leverage Python's powerful standard library and create your own modules to structure projects efficiently.

이번 장을 마치면 여러분은 모듈과 패키지를 사용하여 코드를 체계적으로 관리하고 재사용할 수 있습니다. 파이썬의 강력한 표준 라이브러리를 활용하고, 자신만의 모듈을 만들어 프로젝트를 효율적으로 구성할 수 있습니다.

---

## 1️⃣ What is a Module? (모듈이란 무엇인가?)

Until now, we have written all of our code inside a single Python file. But what happens as programs grow larger? Managing hundreds or thousands of lines of code in a single file becomes very difficult. Also, if you have a useful function that you want to use in another program, would you have to copy and paste it every time?

지금까지 우리는 하나의 파이썬 파일에 모든 코드를 작성했습니다. 하지만 프로그램이 점점 커지면 어떻게 될까요? 수백, 수천 줄의 코드를 하나의 파일에서 관리하는 것은 매우 어렵습니다. 또한 다른 프로그램에서도 사용하고 싶은 유용한 함수가 있다면, 그 함수를 매번 복사해서 붙여넣어야 할까요?

A **Module** is a solution to this problem. A module is a Python file (`.py`) that groups related functions, variables, and classes together. Think of it like a toolbox — a collection of tools (functions) organized by type.

이런 문제를 해결하기 위해 **모듈(Module)**이 등장했습니다. 모듈은 관련된 함수, 변수, 클래스 등을 하나의 파이썬 파일(`.py`)에 모아둔 것입니다. 마치 도구 상자처럼, 필요한 도구(함수)들을 종류별로 정리해둔 것이라고 생각하면 됩니다.

For example, math-related functions are collected in the `math` module, and date/time functions in the `datetime` module.

예를 들어, 수학과 관련된 함수들은 `math` 모듈에, 날짜와 시간 관련 함수들은 `datetime` 모듈에 모아두는 것입니다.

```
Module Concept (모듈의 개념)

┌─────────────────────┐
│   my_module.py      │  ← One Python file (하나의 파이썬 파일)
├─────────────────────┤
│ def hello():        │  ← Multiple functions (여러 함수들을)
│     print("Hi")     │     contained (담고 있음)
│                     │
│ def add(a, b):      │
│     return a + b    │
│                     │
│ PI = 3.14159        │  ← Constants included (상수도 포함)
└─────────────────────┘
        ↓ import
┌─────────────────────┐
│   main.py           │  ← Used in another file
├─────────────────────┤     (다른 파일에서 불러와서 사용)
│ import my_module    │
│                     │
│ my_module.hello()   │
│ result = my_module. │
│          add(10, 20)│
└─────────────────────┘
```

### Why Use Modules? (모듈을 사용하는 이유)

Using modules provides the following advantages:

모듈을 사용하면 다음과 같은 장점이 있습니다:

**1. Reusability (코드 재사용)**
Code you write once can be used across multiple programs. For example, if you create calculator functions, you can reuse them in homework programs, games, and shopping apps — no need to rewrite the same code every time!

한 번 작성한 코드를 여러 프로그램에서 사용할 수 있습니다. 예를 들어, 계산기 함수를 만들었다면 숙제 프로그램에서도, 게임에서도, 쇼핑몰 프로그램에서도 사용할 수 있습니다. 똑같은 코드를 매번 다시 작성할 필요가 없죠!

**2. Maintainability (코드 관리)**
Splitting a large program into multiple files by function makes it easier to manage. Organizing file-related features in `file_utils.py` and math features in `math_utils.py` makes it much easier to find and modify specific features later.

큰 프로그램을 기능별로 여러 파일로 나누면 관리가 쉬워집니다. 파일 관련 기능은 `file_utils.py`에, 계산 관련 기능은 `math_utils.py`에 넣는 식으로 정리하면, 나중에 특정 기능을 수정하거나 찾을 때 훨씬 편리합니다.

**3. Collaboration (협업)**
In team projects, each member can create separate modules for their assigned features and work simultaneously. A can write `user_module.py` while B writes `product_module.py`.

팀 프로젝트에서 각자 맡은 기능을 별도의 모듈로 만들면 동시에 작업할 수 있습니다. A는 `user_module.py`를 작성하고, B는 `product_module.py`를 작성하는 식으로 분업이 가능합니다.

**4. Namespace (이름 충돌 방지)**
Functions with the same name in different modules do not conflict. `module1.calculate()` and `module2.calculate()` are treated as different functions.

서로 다른 모듈에 같은 이름의 함수가 있어도 문제없습니다. `module1.calculate()`와 `module2.calculate()`는 다른 함수로 취급됩니다.

---

## 2️⃣ Importing Modules (모듈 import하기)

To use a module, you must first "import" it. Just like borrowing a book from a library, you bring in the module you need and use it.

모듈을 사용하려면 먼저 "불러오기(import)"를 해야 합니다. 마치 도서관에서 책을 빌려오듯이, 필요한 모듈을 가져와서 사용하는 것입니다.

### Method 1: Import the Entire Module (방법 1: 모듈 전체 가져오기)

The most basic method is to use the `import` keyword.

가장 기본적인 방법은 `import` 키워드를 사용하는 것입니다.

```python
# Import the entire math module (math 모듈 전체 가져오기)
import math

# Use as module_name.function_name() (모듈이름.함수이름() 형태로 사용)
print(math.pi)           # 3.141592653589793
print(math.sqrt(16))     # 4.0 (square root / 제곱근)
print(math.factorial(5)) # 120 (factorial / 팩토리얼)
```

This method gives access to all features in the module, but requires prefixing with `math.` every time you call a function. This makes it clear which module the function comes from, improving readability.

이 방법의 특징은 모듈 안의 모든 기능을 사용할 수 있지만, 함수를 호출할 때마다 `math.`처럼 모듈 이름을 앞에 붙여야 한다는 것입니다. 이렇게 하면 "이 함수가 어느 모듈에서 온 것인지" 명확하게 알 수 있어서 코드를 읽기 쉽습니다.

### Method 2: Import Only What You Need (방법 2: 필요한 것만 가져오기)

You can selectively import only the functions you need from a module, rather than the entire module.

모듈 전체가 아니라 필요한 함수만 골라서 가져올 수도 있습니다.

```python
# Import only pi and sqrt from math (math 모듈에서 pi와 sqrt만 가져오기)
from math import pi, sqrt

# Use directly without module name (모듈 이름 없이 바로 사용 가능)
print(pi)        # 3.141592653589793
print(sqrt(16))  # 4.0

# Items not imported cannot be used (import 하지 않은 것은 사용 불가)
# print(factorial(5))  # Error! factorial was not imported (오류!)
```

This method is convenient since you don't need to write the module name each time. However, in long programs it may be unclear where a function came from, so it is best to use this method for only a few frequently used items.

이 방법은 모듈 이름을 매번 쓰지 않아도 되어 편리합니다. 하지만 코드가 길어지면 "이 함수가 어디서 왔는지" 헷갈릴 수 있으니, 자주 사용하는 몇 가지만 이렇게 가져오는 것이 좋습니다.

⚠️ **Important**: `from math import *` imports everything, but this is not recommended. It makes it hard to know which functions were loaded, and name conflicts may occur.

⚠️ **중요**: `from math import *`처럼 모든 것을 가져오는 방법도 있지만, 권장하지 않습니다. 어떤 함수들이 들어왔는지 알기 어렵고, 이름이 겹칠 수 있기 때문입니다.

### Method 3: Using Aliases (방법 3: 별칭 사용하기)

When a module or function name is long, you can assign a shorter alias.

모듈이나 함수 이름이 길 때, 짧은 별명을 붙여서 사용할 수 있습니다.

```python
# Assign alias to module (모듈에 별칭 붙이기)
import math as m  # Use math under short name m (math를 m이라는 짧은 이름으로 사용)

print(m.pi)       # Instead of math.pi (math.pi 대신 m.pi)
print(m.sqrt(16)) # Instead of math.sqrt (math.sqrt 대신 m.sqrt)

# Assign alias to function (함수에 별칭 붙이기)
from math import factorial as fact

print(fact(5))  # 120, use fact instead of factorial (factorial 대신 fact 사용)
```

Aliases are especially useful when working with long module names. For example, the `numpy` module is almost always used with the alias `np`.

별칭은 특히 이름이 긴 모듈을 사용할 때 유용합니다. 예를 들어 `numpy` 모듈은 거의 항상 `np`라는 별칭으로 사용합니다.

### Example 1: Scientific Calculator (예제 1: 수학 계산기)

This is a scientific calculator using the math module.

math 모듈을 활용한 과학 계산기입니다.

```python
# Scientific calculator program (과학 계산기 프로그램)
import math

print("🔢" + "=" * 38 + "🔢")
print("   Scientific Calculator")
print("🔢" + "=" * 38 + "🔢")

while True:
    print("\n" + "=" * 40)
    print("1. Square Root (제곱근)")
    print("2. Power (거듭제곱)")
    print("3. Logarithm (로그)")
    print("4. Trigonometry - sin, cos, tan (삼각함수)")
    print("5. Factorial (팩토리얼)")
    print("6. Circle Area (원의 넓이)")
    print("7. Exit (종료)")
    print("=" * 40)

    choice = input("\nChoice (선택): ")

    if choice == "1":
        num = float(input("\nNumber (숫자): "))
        result = math.sqrt(num)  # Square root (제곱근)
        print(f"√{num} = {result}")

    elif choice == "2":
        base = float(input("\nBase (밑): "))
        exp = float(input("Exponent (지수): "))
        result = math.pow(base, exp)  # Power (거듭제곱)
        print(f"{base}^{exp} = {result}")

    elif choice == "3":
        num = float(input("\nNumber (숫자): "))
        result = math.log10(num)  # Log base 10 (로그)
        print(f"log₁₀({num}) = {result}")

    elif choice == "4":
        degree = float(input("\nAngle in degrees (각도 / 도): "))
        radian = math.radians(degree)  # Convert to radians (라디안으로 변환)

        print(f"\nsin({degree}°) = {math.sin(radian):.4f}")
        print(f"cos({degree}°) = {math.cos(radian):.4f}")
        print(f"tan({degree}°) = {math.tan(radian):.4f}")

    elif choice == "5":
        num = int(input("\nNumber (숫자): "))
        result = math.factorial(num)  # Factorial (팩토리얼)
        print(f"{num}! = {result}")

    elif choice == "6":
        radius = float(input("\nRadius (반지름): "))
        area = math.pi * radius ** 2  # Circle area (원의 넓이)
        print(f"Area (넓이) = {area:.2f}")

    elif choice == "7":
        print("\nExiting the calculator. (계산기를 종료합니다.)")
        break

    else:
        print("Invalid choice. (잘못된 선택입니다.)")
```

---

## 3️⃣ Useful Standard Libraries (유용한 표준 라이브러리)

When you install Python, many modules are included by default. These are called the "Standard Library." You can import and use them immediately without any separate installation — just like the default apps that come with a smartphone.

파이썬을 설치하면 이미 수많은 모듈이 함께 설치됩니다. 이를 "표준 라이브러리"라고 부릅니다. 별도로 설치할 필요 없이 바로 import해서 사용할 수 있는 것들입니다. 마치 스마트폰을 사면 기본으로 설치되어 있는 앱들과 같습니다.

### random - Generating Random Numbers (난수 생성)

When creating games, running lotteries, or generating test data, you need random values. The `random` module provides various functions for generating random numbers.

게임을 만들거나 추첨을 하거나 테스트 데이터를 만들 때 랜덤한 값이 필요합니다. `random` 모듈은 이런 난수를 생성하는 다양한 함수를 제공합니다.

```python
import random

# 1. Random float between 0.0 and 1.0 (0.0과 1.0 사이의 랜덤한 실수)
print(random.random())  # 0.523... (different each run / 실행할 때마다 다름)

# 2. Random integer in a range (특정 범위의 랜덤한 정수)
dice = random.randint(1, 6)  # Dice: 1 to 6 (주사위: 1~6 중 하나)
print(f"Dice (주사위): {dice}")

# 3. Randomly choose one item from a list (리스트에서 랜덤하게 하나 선택)
menu = ["Jjajangmyeon", "Jjamppong", "Tangsuyuk", "Bokkeumbap"]
today_lunch = random.choice(menu)
print(f"Today's lunch (오늘 점심): {today_lunch}")

# 4. Shuffle a list randomly (리스트를 무작위로 섞기)
cards = ["♠A", "♥K", "♦Q", "♣J"]
random.shuffle(cards)  # Shuffles the list in place (cards 리스트 자체가 섞임)
print(f"Shuffled cards (섞인 카드): {cards}")

# 5. Choose multiple items without repetition (리스트에서 여러 개 랜덤하게 선택, 중복 없음)
numbers = list(range(1, 46))  # 1 to 45 (1~45)
lotto = random.sample(numbers, 6)  # Choose 6 (6개 선택)
print(f"Lotto numbers (로또 번호): {sorted(lotto)}")
```

The `random` module is used in games, simulations, statistics, and many other areas.

`random` 모듈은 게임, 시뮬레이션, 통계 등 다양한 곳에서 활용됩니다.

### datetime - Working with Dates and Times (날짜와 시간 다루기)

This module is used when you need to get the current time, calculate dates, or display them in a specific format.

프로그램에서 현재 시간을 알아내거나, 날짜를 계산하거나, 특정 형식으로 표시할 때 사용합니다.

```python
from datetime import datetime, timedelta

# 1. Get current date and time (현재 날짜와 시간 가져오기)
now = datetime.now()
print(now)  # 2024-02-09 14:30:25.123456

# 2. Display in desired format (원하는 형식으로 표시하기)
print(now.strftime("%Y-%m-%d"))        # 2024-02-09
print(now.strftime("%H:%M:%S"))        # 14:30:25
print(now.strftime("%Y-%m-%d %H:%M")) # 2024-02-09 14:30

# 3. Date calculations (날짜 계산하기)
tomorrow = now + timedelta(days=1)      # Tomorrow (내일)
week_later = now + timedelta(weeks=1)   # One week later (일주일 후)
yesterday = now - timedelta(days=1)     # Yesterday (어제)

print(f"Tomorrow (내일): {tomorrow.strftime('%Y-%m-%d')}")
print(f"One week later (일주일 후): {week_later.strftime('%Y-%m-%d')}")

# 4. Create a specific date (특정 날짜 만들기)
birthday = datetime(2000, 1, 1)  # January 1, 2000 (2000년 1월 1일)
age_days = (now - birthday).days  # Days since birth (태어난 지 며칠)
print(f"Days since birth (태어난 지): {age_days} days")
```

`datetime` is very useful for schedules, log records, D-day countdowns, and more.

`datetime`은 일정 관리, 로그 기록, D-day 계산 등에 매우 유용합니다.

**Format Code Reference (형식 코드 참고):**

- `%Y`: 4-digit year (4자리 연도, e.g. 2024)
- `%m`: Month (월, 01~12)
- `%d`: Day (일, 01~31)
- `%H`: Hour (시, 00~23)
- `%M`: Minute (분, 00~59)
- `%S`: Second (초, 00~59)
- `%A`: Weekday name (요일, e.g. Monday)
- `%B`: Month name (월 이름, e.g. January)

### Example 2: Lotto Number Generator (예제 2: 로또 번호 생성기)

A lotto number generator using the random module.

random 모듈을 사용한 로또 번호 생성기입니다.

```python
# Lotto number generator (로또 번호 생성기)
import random

print("🎰" + "=" * 38 + "🎰")
print("   Lotto Number Generator (로또 번호 생성기)")
print("🎰" + "=" * 38 + "🎰")

while True:
    print("\nHow many sets to generate? (Enter 0 to exit)")
    print("생성할 번호 세트 개수 (종료: 0): ", end="")
    count = int(input())

    if count == 0:
        print("\nExiting program. (프로그램을 종료합니다.)")
        break

    print("\n" + "=" * 40)
    print("🍀 Lucky Numbers (행운의 번호)")
    print("=" * 40)

    for i in range(count):
        # Pick 6 numbers from 1 to 45 (1~45 중 6개 선택)
        numbers = random.sample(range(1, 46), 6)
        numbers.sort()  # Sort ascending (오름차순 정렬)

        print(f"Set {i+1} (번호 {i+1}): {numbers}")

    print("=" * 40)
```

---

## 4️⃣ Creating Your Own Modules (자신만의 모듈 만들기)

Now let's create our own modules. It's simpler than you think — just create a Python file (`.py`) the usual way, write functions inside it, and that file becomes a module.

이제 우리도 직접 모듈을 만들어 봅시다. 생각보다 간단합니다. 그냥 평소처럼 파이썬 파일(`.py`)을 만들고, 그 안에 함수를 작성하면 그게 바로 모듈입니다!

### Step 1: Create the Module File (단계 1: 모듈 파일 만들기)

Create a file named `mymath.py` and write the following:

먼저 `mymath.py`라는 이름의 파일을 만들고, 다음과 같이 작성합니다:

**mymath.py:**

```python
# mymath.py - Custom math functions module (나만의 수학 함수 모듈)
"""
My custom math module (나만의 수학 함수 모듈)
Provides simple arithmetic functions (간단한 사칙연산 함수들을 제공합니다)
"""

def add(a, b):
    """Add two numbers (두 수를 더합니다)"""
    return a + b

def subtract(a, b):
    """Subtract two numbers (두 수를 뺍니다)"""
    return a - b

def multiply(a, b):
    """Multiply two numbers (두 수를 곱합니다)"""
    return a * b

def divide(a, b):
    """Divide two numbers (두 수를 나눕니다)"""
    if b == 0:
        return "Cannot divide by zero (0으로 나눌 수 없습니다)"
    return a / b

# Constants can also be defined in a module (모듈에 상수도 정의할 수 있습니다)
PI = 3.14159
E = 2.71828

def circle_area(radius):
    """Calculate circle area (원의 넓이를 계산합니다)"""
    return PI * radius * radius
```

The section enclosed in triple quotes (`"""`) at the top is called a **docstring** — it documents what this module does. Each function can also have a docstring explaining its purpose.

파일 맨 위의 세 개의 따옴표(`"""`)로 둘러싸인 부분은 **독스트링(docstring)**이라고 하며, 이 모듈이 무엇을 하는지 설명하는 문서입니다. 각 함수 아래에도 독스트링을 넣어 함수의 기능을 설명할 수 있습니다.

### Step 2: Use the Module (단계 2: 모듈 사용하기)

Now create `main.py` in the same folder and use the module we created:

이제 같은 폴더에 `main.py` 파일을 만들어서 우리가 만든 모듈을 사용해봅시다:

**main.py:**

```python
# main.py - Using our custom module (우리가 만든 모듈 불러오기)
import mymath

# Using functions (함수 사용)
print(mymath.add(10, 20))      # 30
print(mymath.subtract(50, 20)) # 30
print(mymath.multiply(5, 6))   # 30
print(mymath.divide(100, 4))   # 25.0

# Using constants (상수 사용)
print(mymath.PI)  # 3.14159

# Calculate circle area (원의 넓이 계산)
radius = 5
area = mymath.circle_area(radius)
print(f"Circle area with radius {radius} (반지름 {radius}인 원의 넓이): {area}")
```

⚠️ **Important Notes (주의사항)**:

1. `mymath.py` and `main.py` must be in the **same folder** (같은 폴더에 있어야 합니다)
2. Module names cannot contain spaces or special characters (모듈 이름에 공백이나 특수문자를 넣으면 안 됩니다)
3. Module names should avoid Python reserved words like `if`, `for` (파이썬 예약어를 피해야 합니다)

### Why Create Modules? (왜 모듈로 만드는 게 좋을까요?)

Imagine building multiple projects — a calculator, a game, a statistics program — all of which need basic math. With a `mymath` module:

예를 들어, 계산기 프로그램, 게임, 통계 프로그램 등 여러 프로젝트를 만든다고 생각해봅시다. 이들 모두 기본적인 수학 계산이 필요합니다. `mymath` 모듈을 만들어두면:

```python
# calculator.py - Use add function (덧셈 함수 사용)
import mymath
result = mymath.add(user_input1, user_input2)

# game.py - Use multiply function (곱셈 함수 사용)
import mymath
damage = mymath.multiply(attack, multiplier)

# statistics.py - Use divide function (나눗셈 함수 사용)
import mymath
average = mymath.divide(total, count)
```

If you later want to improve the `add` function, just modify `mymath.py`. All programs using this module will automatically use the improved function!

만약 나중에 `add` 함수를 개선하고 싶다면, `mymath.py` 파일 하나만 수정하면 됩니다. 이 모듈을 사용하는 모든 프로그램이 자동으로 개선된 함수를 사용하게 됩니다!

## 5️⃣ Packages — Collections of Modules (패키지 - 모듈의 모음)

As a program grows, so does the number of modules. Having 10, 20, or 100 modules scattered in one folder becomes difficult to manage. That's when **Packages** become essential.

프로그램이 점점 커지면 모듈도 많아집니다. 10개, 20개, 100개의 모듈이 한 폴더에 뒤죽박죽 섞여있으면 관리하기 어렵겠죠? 이럴 때 **패키지(Package)**를 사용합니다.

A package is a **folder that contains modules**. Think of it like organizing files into folders — placing related files together in one folder.

패키지는 **모듈들을 담는 폴더**입니다. 마치 파일을 정리할 때 관련된 파일들을 폴더에 넣어 정리하는 것과 같습니다.

### Package vs Module (패키지 vs 모듈)

```
Analogy (비유로 이해하기)

📁 Document Filing (서류 정리)
├── 📄 contract.pdf          ← Single file (파일 하나 = 모듈)
├── 📄 receipt.pdf           ← Single file (파일 하나 = 모듈)
└── 📁 2024_tax_docs/        ← Folder (폴더 = 패키지)
    ├── 📄 january.pdf
    ├── 📄 february.pdf
    └── 📄 march.pdf

💻 Python Code (파이썬 코드)
├── 📄 main.py               ← Main program (메인 프로그램)
├── 📄 utils.py              ← Module (모듈)
└── 📁 mypackage/            ← Package (패키지)
    ├── 📄 __init__.py       ← Package marker file (패키지 표시 파일)
    ├── 📄 math_utils.py     ← Module (모듈)
    └── 📄 string_utils.py   ← Module (모듈)
```

### Creating a Package — Hands-on (패키지 만들기 - 실전 예제)

Let's create the following structure:

실제로 패키지를 만들어봅시다:

```
my_project/
│
├── main.py              ← Main program (메인 프로그램)
│
└── mytools/             ← Package we will create (우리가 만들 패키지)
    ├── __init__.py      ← Marks this as a package (패키지임을 알리는 파일)
    ├── calculator.py    ← Calculation module (계산 관련 모듈)
    └── texttools.py     ← Text processing module (텍스트 처리 모듈)
```

### Step 1: Create the Folder (단계 1: 폴더 만들기)

Create a folder named `mytools`.

먼저 `mytools`라는 이름의 폴더를 만듭니다.

### Step 2: Create `__init__.py` (단계 2: __init__.py 파일 만들기)

Inside the `mytools` folder, create a file called `__init__.py`. When Python sees this file, it recognizes the folder as a package.

`mytools` 폴더 안에 `__init__.py`라는 파일을 만듭니다. 이 파일이 있으면 파이썬이 "아, 이 폴더는 패키지구나!"라고 인식합니다.

**mytools/\_\_init\_\_.py:**

```python
# __init__.py - Package initialization file (패키지 초기화 파일)
"""
My custom tools package (나만의 도구 모음 패키지)
Provides calculation and text processing features (계산과 텍스트 처리 기능을 제공합니다)
"""

print("mytools package loaded (mytools 패키지가 로드되었습니다) ✓")

# Package version info (패키지 버전 정보)
__version__ = "1.0.0"
__author__ = "Hong Gil-dong"
```

`__init__.py` can be an empty file, but you can also add package metadata or initialization code like this.

`__init__.py`는 빈 파일이어도 되지만, 이렇게 패키지 정보를 넣거나 초기화 코드를 넣을 수 있습니다.

### Step 3: Create the Module Files (단계 3: 모듈 파일들 만들기)

**mytools/calculator.py:**

```python
# calculator.py - Calculation functions (계산 관련 함수들)
"""Calculation functions (계산 관련 함수들)"""

def add(a, b):
    """Addition (덧셈)"""
    return a + b

def multiply(a, b):
    """Multiplication (곱셈)"""
    return a * b

def factorial(n):
    """Calculate factorial (팩토리얼 계산)"""
    if n == 0 or n == 1:
        return 1
    result = 1
    for i in range(2, n + 1):
        result = result * i
    return result
```

**mytools/texttools.py:**

```python
# texttools.py - Text processing functions (텍스트 처리 함수들)
"""Text processing functions (텍스트 처리 함수들)"""

def reverse(text):
    """Reverse a string (문자열 뒤집기)"""
    return text[::-1]

def count_words(text):
    """Count words (단어 개수 세기)"""
    words = text.split()
    return len(words)

def remove_spaces(text):
    """Remove spaces (공백 제거)"""
    return text.replace(" ", "")
```

### Step 4: Use the Package (단계 4: 패키지 사용하기)

Now use the package in `main.py`:

이제 `main.py`에서 우리가 만든 패키지를 사용해봅시다:

**main.py:**

```python
# main.py - Using mytools package (mytools 패키지 사용)

# Method 1: Import entire module (방법 1: 모듈 전체 가져오기)
from mytools import calculator
from mytools import texttools

print("=== Calculator Test (계산기 테스트) ===")
print(f"10 + 20 = {calculator.add(10, 20)}")
print(f"5! = {calculator.factorial(5)}")

print("\n=== Text Tools Test (텍스트 도구 테스트) ===")
text = "Hello Python"
print(f"Original (원본): {text}")
print(f"Reversed (뒤집기): {texttools.reverse(text)}")
print(f"Word count (단어 수): {texttools.count_words(text)}")

# Method 2: Import only specific functions (방법 2: 필요한 함수만 가져오기)
from mytools.calculator import factorial
from mytools.texttools import reverse

print(f"\n7! = {factorial(7)}")
print(f"Python reversed (Python 뒤집기): {reverse('Python')}")
```

Output (실행 결과):

```
mytools package loaded ✓
=== Calculator Test ===
10 + 20 = 30
5! = 120

=== Text Tools Test ===
Original: Hello Python
Reversed: nohtyP olleH
Word count: 2

7! = 5040
Python reversed: nohtyP
```

### Advantages of Packages (패키지의 장점)

Using packages provides these key benefits: organized management of related modules, prevention of name conflicts between modules in different packages, reusability by copying entire packages to other projects, and easier collaboration by assigning different packages to different team members.

패키지를 사용하면 관련 모듈을 체계적으로 그룹화할 수 있고, 서로 다른 패키지 간의 이름 충돌을 방지하며, 패키지 전체를 다른 프로젝트에 복사해 재사용할 수 있고, 팀원별로 다른 패키지를 작업하여 협업이 편리해집니다.

---

## 6️⃣ Using External Packages (외부 패키지 사용하기)

The real power of Python lies in **external packages**. Hundreds of thousands of packages created by developers worldwide are freely available!

파이썬의 진정한 힘은 **외부 패키지**에 있습니다. 전 세계 개발자들이 만든 수십만 개의 패키지를 무료로 사용할 수 있습니다!

Just like installing apps on a smartphone, you can install and use any package you need — for web scraping, data analysis, AI, game development, and much more.

마치 스마트폰에 앱을 설치하듯이, 필요한 패키지를 설치해서 사용할 수 있습니다. 웹 크롤링, 데이터 분석, 인공지능, 게임 개발 등 거의 모든 분야의 패키지가 있습니다.

### pip — The Package Manager (pip - 패키지 설치 도구)

`pip` is the tool for installing and managing Python packages. It is installed automatically alongside Python.

`pip`는 파이썬 패키지를 설치하고 관리하는 프로그램입니다. 파이썬을 설치하면 자동으로 함께 설치됩니다.

**Terminal commands (터미널에서 사용하는 명령어들):**

```bash
# Install a package (패키지 설치)
pip install package_name

# Install a specific version (특정 버전 설치)
pip install package_name==1.2.3

# Uninstall a package (패키지 제거)
pip uninstall package_name

# List installed packages (설치된 패키지 목록 보기)
pip list

# Show package details (패키지 정보 확인)
pip show package_name

# Upgrade a package (패키지 업그레이드)
pip install --upgrade package_name
```

### Popular External Packages (인기 있는 외부 패키지들)

```
📦 Data Analysis (데이터 분석)
├── pandas    : Data tables, like Excel (엑셀 같은 표 다루기)
├── numpy     : Math and matrix operations (행렬, 통계)
└── matplotlib: Plotting graphs (그래프 그리기)

📦 Web Development (웹 개발)
├── flask     : Lightweight web framework (웹사이트 만들기, 가벼움)
├── django    : Full-featured web framework (웹사이트 만들기, 강력함)
└── requests  : Fetch data from the web (웹에서 데이터 가져오기)

📦 Artificial Intelligence (인공지능)
├── tensorflow: Machine learning (머신러닝)
├── pytorch   : Machine learning (머신러닝)
└── scikit-learn: ML for beginners (머신러닝 초보자용)

📦 Other (기타)
├── pillow    : Image processing (이미지 처리)
├── pygame    : Game development (게임 만들기)
└── beautifulsoup4: Web scraping (웹 크롤링)
```

### Practical Example: requests Package (실전 예제: requests 패키지)

`requests` is a very popular package for fetching data from the internet.

`requests`는 인터넷에서 데이터를 가져올 때 사용하는 매우 유명한 패키지입니다.

**Step 1: Install (1단계: 설치하기)**

```bash
pip install requests
```

**Step 2: Use (2단계: 사용하기)**

```python
# Fetch data from the web (웹에서 데이터 가져오기 예제)
import requests

# Fetch a web page (웹 페이지 가져오기)
response = requests.get("https://api.github.com")

# Check status (상태 확인)
print(f"Status code (상태 코드): {response.status_code}")  # 200 = success (성공)

# Check content (내용 확인)
if response.status_code == 200:
    print("Connected successfully! (연결 성공!)")
    data = response.json()  # Convert to JSON data (JSON 데이터로 변환)
    print(data)
else:
    print("Connection failed. (연결 실패)")
```

### Notes (주의사항)

1. **Internet required (인터넷 연결 필요)**: An internet connection is needed to install packages
2. **Admin privileges (관리자 권한)**: May sometimes be required
   - Windows: Run Command Prompt as Administrator
   - Mac/Linux: `sudo pip install package_name`
3. **Virtual environments (가상 환경)**: When different projects require different package versions, use virtual environments (covered later)
4. **Choose trusted packages (신뢰할 수 있는 패키지만)**: Since anyone can publish packages, choose well-known and widely used ones

### Finding Packages (패키지 찾기)

- **PyPI (Python Package Index)**: https://pypi.org/ — over 500,000 packages registered, with documentation, examples, and download counts
- **GitHub**: https://github.com/ — most packages publish source code here; the more stars, the more popular the package

---

## 📝 Key Concepts Summary (핵심 개념 정리)

In this chapter, you learned the core concepts of modules and packages in Python. A module is a `.py` file that groups related functions and variables, making code reusable and manageable. Python's standard library provides many built-in modules like `math`, `random`, and `datetime` that are ready to use without installation. You can also create your own modules simply by writing functions in a `.py` file and importing it. The `__name__` variable helps you run code only when a file is executed directly, not when it's imported. Packages are folders containing multiple modules, and `__init__.py` marks a folder as a package. External packages can be installed with `pip`, and well-structured projects separate code by function into clear file hierarchies.

이번 장에서는 파이썬 모듈과 패키지의 핵심 개념을 배웠습니다. 모듈은 관련 함수와 변수를 담은 `.py` 파일로, 코드 재사용과 관리를 쉽게 합니다. 파이썬 표준 라이브러리에는 `math`, `random`, `datetime` 등 바로 사용할 수 있는 모듈이 풍부합니다. `.py` 파일에 함수를 작성하고 import하면 자신만의 모듈을 만들 수 있습니다. `__name__` 변수로 파일이 직접 실행될 때만 코드를 실행할 수 있으며, 패키지는 여러 모듈을 담는 폴더로 `__init__.py`로 표시합니다. 외부 패키지는 pip로 설치하고, 좋은 프로젝트는 기능별로 파일을 명확히 분리합니다.

---

## 💡 Practice Assignments (실습 과제)

### Assignment 1: Discount Calculator Module (과제 1: 할인 계산 모듈)

Create a module that calculates various types of discounts.

다양한 할인을 계산하는 모듈을 만드세요.

```python
# discount.py - Discount calculation module (할인 계산 모듈)
def percentage_discount(price, rate):
    """Percentage discount (퍼센트 할인)"""
    return price * (100 - rate) / 100

def fixed_discount(price, amount):
    """Fixed amount discount (정액 할인)"""
    return max(0, price - amount)

def buy_n_get_m(price, n, m):
    """Buy N get M free (n개 사면 m개 무료)"""
    total_items = n + m
    return (price * n) / total_items

# Write test code here (테스트 코드 작성)
```

### Assignment 2: Text Analysis Package (과제 2: 텍스트 분석 패키지)

Create a package for analyzing text.

텍스트를 분석하는 패키지를 만드세요.

```python
# text_analysis/
#   __init__.py
#   counter.py    # Word and character count (단어, 문자 개수)
#   analyzer.py   # Longest word, average word length (가장 긴 단어, 평균 단어 길이)
#   formatter.py  # Uppercase/lowercase conversion (대문자, 소문자 변환)
```

---

## ✅ Quiz (퀴즈)

### [Beginner] Question 1

Which keyword is used to import a module?

모듈을 가져오는 키워드는?

```python
1. include
2. require
3. import
4. load
```

### [Intermediate] Question 2

Which of the following is the correct way to import?

다음 중 올바른 import 방법은?

```python
1. import math.pi
2. from math import pi
3. import pi from math
4. get pi from math
```

### [Intermediate] Question 3

What does `__name__ == "__main__"` mean?

`__name__ == "__main__"`의 의미는?

```python
1. When the module is imported (모듈이 import될 때)
2. When the module is executed directly (모듈이 직접 실행될 때)
3. When the module has an error (모듈에 오류가 있을 때)
4. When the module is first created (모듈이 처음 만들어질 때)
```

### [Advanced] Question 4

Which file marks a folder as a package?

패키지를 나타내는 파일은?

```python
1. __init__.py
2. __main__.py
3. __package__.py
4. index.py
```

### [Advanced] Question 5

What is the output of the following code?

다음 코드의 실행 결과는?

```python
from math import sqrt as s
print(s(16))
```

1. Error occurs (오류 발생)
2. s(16)
3. 4.0
4. sqrt(16)

---

## 🔑 Quiz Answers and Explanations (퀴즈 정답 및 해설)

**Answer 1: 3**

In Python, the `import` keyword is used to load a module. The other options (`include`, `require`, `load`) are not Python keywords for this purpose.

파이썬에서는 `import` 키워드로 모듈을 가져옵니다. 나머지는 파이썬에서 모듈 불러오기에 사용하지 않는 키워드입니다.

**Answer 2: 2**

`from math import pi` is the correct syntax to selectively import `pi` from the `math` module. Option 1 is invalid syntax, and options 3 and 4 are not valid Python.

`from math import pi`는 math 모듈에서 pi만 가져오는 올바른 방법입니다. 1번은 잘못된 문법이고, 3번과 4번은 유효한 파이썬 문법이 아닙니다.

**Answer 3: 2**

`__name__ == "__main__"` is `True` when the file is run directly. When the file is imported as a module, `__name__` becomes the module's name, not `"__main__"`.

`__name__ == "__main__"`은 해당 파일이 직접 실행될 때 True가 됩니다. import로 불러올 때는 `__name__`이 모듈 이름이 됩니다.

**Answer 4: 1**

A directory containing an `__init__.py` file is recognized by Python as a package.

`__init__.py` 파일이 있는 디렉토리가 패키지로 인식됩니다.

**Answer 5: 3**

Since `sqrt` was imported with the alias `s`, calling `s(16)` is equivalent to `sqrt(16)`, which returns `4.0`.

`sqrt as s`로 sqrt를 s라는 별칭으로 가져왔으므로, `s(16)`은 4.0을 출력합니다.

---

## 🎯 Next Chapter Preview (다음 장 예고)

In the next chapter, you will learn about the fundamentals of classes. You will explore object-oriented programming by using classes to bundle data and functionality together, enabling you to write more structured and powerful programs.

다음 장에서는 클래스의 기초에 대해 배웁니다. 객체지향 프로그래밍의 핵심인 클래스를 사용하여 데이터와 기능을 하나로 묶고, 더욱 체계적인 프로그램을 작성하는 방법을 학습하게 됩니다!

---

Thank you for your attention.

Prof. Cho Jeonghyun (peterchokr@gmail.com). Yeungnam University College.
