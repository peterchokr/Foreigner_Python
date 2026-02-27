# Chapter 1. Python Introduction and Development Environment Setup

---

## 📚 Learning Objectives

After completing this week, you will understand what Python is, set up a Python development environment on your own computer, and be able to write and run your first program. This is an important starting point as you enter the world of programming.

이번 주차를 마치면 여러분은 파이썬이 무엇인지 이해하고, 자신의 컴퓨터에 파이썬 개발 환경을 구축하여 첫 번째 프로그램을 작성하고 실행할 수 있게 됩니다. 프로그래밍의 세계에 첫 발을 내딛는 중요한 시작점입니다.

---

## 1️⃣ What is Python?

Python is a programming language created in 1991 by Guido van Rossum, a Dutch programmer. Just as we communicate in Korean or English, Python is a language for people and computers to communicate. Compared to other programming languages, Python has a particularly easy-to-read and easy-to-learn syntax, making it the most recommended language for people who are just beginning to learn programming.

파이썬은 1991년 귀도 반 로섬(Guido van Rossum)이라는 네덜란드 프로그래머가 만든 프로그래밍 언어입니다. 마치 우리가 한국어나 영어로 의사소통하듯이, 파이썬은 사람과 컴퓨터가 소통하는 언어입니다. 다른 프로그래밍 언어들과 비교했을 때 파이썬은 특히 읽기 쉽고 배우기 쉬운 문법을 가지고 있어서, 프로그래밍을 처음 배우는 사람들에게 가장 많이 추천되는 언어입니다.

The name Python does not come from an actual snake, but from "Monty Python," a British comedy group. This reflects the creator's philosophy that programming should be fun.

파이썬의 이름은 실제 뱀(python)이 아니라 영국의 코미디 그룹 "몬티 파이썬(Monty Python)"에서 따왔습니다. 이는 프로그래밍이 재미있어야 한다는 창시자의 철학을 반영합니다.

### Key Characteristics of Python (파이썬의 주요 특징)

Python is currently one of the most popular programming languages in the world. Services that you use every day, such as Google, Netflix, Instagram, and YouTube, are built with Python. There are several reasons why Python is so widely used.

파이썬은 현재 세계에서 가장 인기 있는 프로그래밍 언어 중 하나입니다. 구글, 넷플릭스, 인스타그램, 유튜브 같은 여러분이 매일 사용하는 서비스들이 파이썬으로 만들어졌습니다. 파이썬이 이렇게 널리 사용되는 이유는 여러 가지가 있습니다.

**First, Python has easy-to-read syntax. (첫째, 파이썬은 읽기 쉬운 문법을 가지고 있습니다.)**

For example, when writing a program to print "Hello, World!", other languages require complex code, but Python requires only one line. This allows you to understand the code as naturally as reading an English sentence.

예를 들어 "Hello, World!"를 출력하는 프로그램을 작성할 때, 다른 언어들은 복잡한 코드가 필요하지만 파이썬은 단 한 줄이면 충분합니다. 이는 영어 문장을 읽는 것처럼 자연스럽게 코드를 이해할 수 있게 해줍니다.

**Second, Python is used in various fields. (둘째, 파이썬은 다양한 분야에서 활용됩니다.)**

Web development, data analysis, artificial intelligence, game development, automation programs—you can build almost anything you can imagine with Python. In particular, Python has established itself as the standard language in the fields of artificial intelligence and data science.

웹사이트 개발, 데이터 분석, 인공지능, 게임 제작, 자동화 프로그램 등 여러분이 상상하는 거의 모든 것을 파이썬으로 만들 수 있습니다. 특히 최근 인공지능과 데이터 과학 분야에서 파이썬은 표준 언어로 자리잡았습니다.

**Third, Python provides extensive libraries. (셋째, 파이썬은 방대한 라이브러리를 제공합니다.)**

A library is a collection of pre-made code that allows you to use features created by others without having to build everything from scratch. Like LEGO blocks, you can assemble the needed components to create the program you want.

라이브러리란 이미 만들어진 코드 모음으로, 여러분이 처음부터 모든 것을 만들 필요 없이 다른 사람들이 만든 기능을 가져다 쓸 수 있게 해줍니다. 마치 레고 블록처럼 필요한 부품들을 조립해서 원하는 프로그램을 만들 수 있습니다.

```
Programming Language Popularity Comparison (2024)

1. Python      ████████████████████████ (24%)
2. JavaScript  ████████████████████ (20%)
3. Java        ████████████████ (16%)
4. C++         ████████████ (12%)
5. C#          ██████████ (10%)
```

---

## 2️⃣ Setting Up Your Development Environment (개발 환경 구축하기)

To start programming, you first need to install the necessary tools on your computer. This is similar to preparing ingredients and tools before cooking.

프로그래밍을 시작하려면 먼저 컴퓨터에 필요한 도구들을 설치해야 합니다. 요리를 하기 전에 재료와 도구를 준비하는 것과 같습니다.

### Installing Python (파이썬 설치하기)

The process of installing Python is simpler than you might think. Visit the official website (python.org) and you can download the installation file for your operating system. As of 2024, Python version 3.12 is the latest, but version 3.8 or higher is sufficient for all the content in this course.

파이썬을 설치하는 과정은 생각보다 간단합니다. 공식 웹사이트(python.org)에 접속하면 여러분의 운영체제에 맞는 설치 파일을 다운로드할 수 있습니다. 2024년 현재 파이썬은 버전 3.12가 최신 버전이지만, 3.8 이상이면 이 수업의 모든 내용을 학습하는 데 문제가 없습니다.

If you are a Windows user, you must check the "Add Python to PATH" checkbox when running the downloaded installation file. This option allows Python to be executed from any location on your computer. It's similar to registering your home address so packages can be delivered anywhere.

윈도우 사용자라면 다운로드한 설치 파일을 실행할 때 반드시 "Add Python to PATH"라는 체크박스를 선택해야 합니다. 이 옵션은 컴퓨터의 어느 위치에서든 파이썬을 실행할 수 있게 해주는 중요한 설정입니다. 마치 집 주소를 등록해서 택배가 어디든 배달될 수 있게 하는 것과 비슷합니다.

Mac users may already have Python installed on the latest macOS, but it's likely an older version. It is recommended to download and install the latest version from the official website.

맥(Mac) 사용자는 최신 맥OS에 이미 파이썬이 설치되어 있을 수 있지만, 오래된 버전일 가능성이 높습니다. 공식 웹사이트에서 최신 버전을 다운로드해서 설치하는 것을 권장합니다.

To verify that the installation was successful, open the terminal (or command prompt or PowerShell on Windows) and type the following command:

설치가 완료되었는지 확인하려면 터미널(윈도우에서는 명령 프롬프트 또는 PowerShell)을 열고 다음 명령어를 입력합니다:

```bash
# Check Python version (파이썬 버전 확인)
python --version
```

If the screen displays version information like "Python 3.x.x", the installation has been completed successfully.

화면에 "Python 3.x.x"와 같은 버전 정보가 표시되면 설치가 성공적으로 완료된 것입니다.

### Choosing an Integrated Development Environment (IDE) (통합 개발 환경(IDE) 선택하기)

There are several ways to write Python code. You can use a basic text editor like Notepad, but using a professional development tool makes programming much more convenient. Such tools are called Integrated Development Environments (IDEs).

파이썬 코드를 작성하는 방법은 여러 가지가 있습니다. 메모장 같은 기본 텍스트 편집기를 사용할 수도 있지만, 전문적인 개발 도구를 사용하면 훨씬 편리하게 프로그래밍할 수 있습니다. 이런 도구를 통합 개발 환경(Integrated Development Environment, IDE)이라고 부릅니다.

In this course, we recommend two IDEs. The first is Visual Studio Code (VS Code), a free editor created by Microsoft. It is lightweight, fast, and provides various extension features. The second is PyCharm, a powerful IDE designed specifically for Python. PyCharm is available in Community Edition (free) and Professional Edition (paid), and the free version is sufficient for learning purposes.

이 수업에서는 두 가지 IDE를 추천합니다. 첫 번째는 Visual Studio Code(VS Code)로, 마이크로소프트가 만든 무료 편집기입니다. 가볍고 빠르며 다양한 확장 기능을 제공합니다. 두 번째는 PyCharm으로, 파이썬 전용으로 설계된 강력한 IDE입니다. PyCharm은 Community Edition(무료)과 Professional Edition(유료)이 있는데, 학습 목적으로는 무료 버전으로 충분합니다.

```
Development Environment Components

┌─────────────────────────────────────┐
│     Your Computer                   │
│                                     │
│  ┌──────────────────────────────┐  │
│  │   Python Interpreter          │  │  ← Engine to run Python code
│  │   (파이썬 인터프리터)           │  │
│  └──────────────────────────────┘  │
│              ↑                      │
│              │                      │
│  ┌──────────────────────────────┐  │
│  │   Code Editor (IDE)           │  │  ← Tool to write code
│  │   코드 편집기 (IDE)            │  │
│  │   - VS Code                  │  │
│  │   - PyCharm                  │  │
│  └──────────────────────────────┘  │
│              ↑                      │
│              │                      │
│         You (여러분)                 │
└─────────────────────────────────────┘
```

### Setting Up VS Code (VS Code 설정하기)

After installing VS Code, you need to install the Python extension. Run VS Code and click the extension icon (four squares grouped together) in the left sidebar, then search for "Python" and install the official Python extension provided by Microsoft. This extension provides various features such as code auto-completion, syntax error display, and debugging.

VS Code를 설치한 후에는 파이썬 확장(Extension)을 설치해야 합니다. VS Code를 실행하고 왼쪽 사이드바에서 확장 아이콘(네모 4개가 모여있는 모양)을 클릭한 다음, "Python"을 검색해서 Microsoft에서 제공하는 공식 파이썬 확장을 설치합니다. 이 확장은 코드 자동 완성, 문법 오류 표시, 디버깅 등 다양한 기능을 제공합니다.

---

## 3️⃣ Writing Your First Python Program (첫 번째 파이썬 프로그램 작성하기)

Now it's time to write actual code. The program traditionally written first when learning programming is one that prints "Hello, World!". This tradition has been followed since the 1970s and is the first step for every programmer learning a new language.

이제 드디어 실제 코드를 작성할 시간입니다. 프로그래밍을 배울 때 전통적으로 가장 먼저 작성하는 프로그램은 "Hello, World!"를 출력하는 것입니다. 이 전통은 1970년대부터 시작되었으며, 새로운 언어를 배우는 모든 프로그래머의 첫 걸음입니다.

### Example 1: Hello, World! (예제 1: Hello, World!)

Let's create a new Python file. Open VS Code and select File → New File, then save the file as `hello.py`. The file extension `.py` indicates that this file contains Python code.

새 파이썬 파일을 만들어봅시다. VS Code를 열고 File → New File을 선택한 다음, 파일 이름을 `hello.py`로 저장합니다. 파일 확장자 `.py`는 이 파일이 파이썬 코드 파일임을 나타냅니다.

```python
# Your first Python program (첫 번째 파이썬 프로그램)
# This prints "Hello, World!" to the screen (화면에 "Hello, World!"를 출력합니다)
print("Hello, World!")
```

When you run this code, the text "Hello, World!" will be displayed on the screen. Let's understand the code line by line. The first and second lines start with `#`, which is called a comment. Comments are explanations for people to read, and the computer ignores them. They serve a similar role to footnotes or notes in a book.

이 코드를 실행하면 화면에 "Hello, World!"라는 문자가 표시됩니다. 코드를 한 줄씩 이해해봅시다. 첫 번째와 두 번째 줄은 `#`으로 시작하는데, 이것을 주석(comment)이라고 합니다. 주석은 사람이 읽기 위한 설명이며, 컴퓨터는 이 부분을 무시합니다. 마치 책의 각주나 메모와 같은 역할을 합니다.

The third line contains `print()`, a built-in function in Python that outputs the content in the parentheses to the screen. Here, "Hello, World!" is called a string, which is represented by enclosing it in double quotes or single quotes.

세 번째 줄의 `print()`는 파이썬의 내장 함수로, 괄호 안의 내용을 화면에 출력합니다. 여기서 "Hello, World!"는 문자열(string)이라고 부르며, 큰따옴표나 작은따옴표로 감싸서 표현합니다.

### Example 2: Simple Greeting Program (예제 2: 간단한 인사 프로그램)

This time, let's create a more interactive program that receives the user's name and greets them.

이번에는 조금 더 상호작용하는 프로그램을 만들어봅시다. 사용자의 이름을 입력받아서 인사하는 프로그램입니다.

```python
# Program to receive a user's name and greet them
# (사용자의 이름을 입력받아 인사하는 프로그램)
name = input("Enter your name: ")
print("Hello, " + name + "!")
print("Welcome to the world of Python programming!")
```

When you run this program, the message "Enter your name: " appears and waits for input. After you type your name and press Enter, a personalized greeting message is displayed. The `input()` function receives keyboard input from the user, and the input value is stored in a variable called `name`. Think of a variable as a box that holds data.

이 프로그램을 실행하면 "Enter your name: "라는 메시지가 나타나고, 여러분이 이름을 입력하고 Enter를 누르면 개인화된 환영 메시지가 출력됩니다. `input()` 함수는 사용자로부터 키보드 입력을 받는 함수이며, 입력받은 값을 `name`이라는 변수에 저장합니다. 변수는 데이터를 담는 상자라고 생각하면 됩니다.

### Example 3: Simple Calculator (예제 3: 간단한 계산기)

Python can perform simple calculations. Let's create a program that adds two numbers.

파이썬으로 간단한 계산을 할 수 있습니다. 두 숫자를 더하는 프로그램을 만들어봅시다.

```python
# Simple addition calculator (간단한 덧셈 계산기)
print("=== Simple Addition Calculator ===")

# Get first number input (첫 번째 숫자 입력받기)
num1 = input("Enter the first number: ")
num1 = int(num1)  # Convert string to integer (문자열을 정수로 변환)

# Get second number input (두 번째 숫자 입력받기)
num2 = input("Enter the second number: ")
num2 = int(num2)  # Convert string to integer (문자열을 정수로 변환)

# Calculate and display result (계산 및 결과 출력)
result = num1 + num2
print(num1, "+", num2, "=", result)
```

This program is like using a calculator in real life. When the user enters two numbers, the program automatically adds them and shows the result. The important point here is that the `input()` function always returns a string. Therefore, to perform numeric calculations, you must use the `int()` function to convert the string to an integer.

이 프로그램은 실생활에서 계산기를 사용하는 것과 비슷합니다. 사용자가 두 개의 숫자를 입력하면 프로그램이 자동으로 더해서 결과를 보여줍니다. 여기서 중요한 점은 `input()` 함수가 항상 문자열을 반환한다는 것입니다. 따라서 숫자 계산을 하려면 `int()` 함수를 사용해서 문자열을 정수(integer)로 변환해야 합니다.

```
Program Execution Flow (프로그램 실행 흐름)

1. Program starts (프로그램 시작)
   ↓
2. Display "Enter the first number:" (첫 번째 숫자 입력 메시지 출력)
   ↓
3. Wait for user input (예: 10) (사용자 입력 대기)
   ↓
4. Convert string "10" to integer 10 (문자열 "10"을 정수 10으로 변환)
   ↓
5. Display "Enter the second number:" (두 번째 숫자 입력 메시지 출력)
   ↓
6. Wait for user input (예: 20) (사용자 입력 대기)
   ↓
7. Convert string "20" to integer 20 (문자열 "20"을 정수 20으로 변환)
   ↓
8. Calculate 10 + 20 = 30 (10 + 20 계산 = 30)
   ↓
9. Display "10 + 20 = 30" (출력)
   ↓
10. Program terminates (프로그램 종료)
```

---

## 4️⃣ How to Run a Program (프로그램 실행 방법)

There are several ways to run a written Python program. Each method has its advantages and disadvantages, so you can choose the one that fits your situation.

작성한 파이썬 프로그램을 실행하는 방법은 여러 가지가 있습니다. 각 방법마다 장단점이 있으므로 상황에 맞게 선택할 수 있습니다.

### Method 1: Run Directly from IDE (IDE에서 직접 실행)

In VS Code or PyCharm, right-click on the code editing window and select "Run Python File" or click the run button (▶️) at the top. This is the most convenient method and is recommended for beginners.

VS Code나 PyCharm에서는 코드 편집 창에서 마우스 오른쪽 버튼을 클릭하고 "Run Python File"을 선택하거나, 상단의 실행 버튼(▶️)을 클릭하면 됩니다. 이 방법이 가장 간편하며 초보자에게 권장됩니다.

### Method 2: Run from Terminal (터미널에서 실행)

Open the terminal or command prompt, navigate to the folder containing the file, and then type the following command:

터미널이나 명령 프롬프트를 열고 파일이 있는 폴더로 이동한 다음, 아래 명령어를 입력합니다:

```bash
# Run Python file (파이썬 파일 실행)
python hello.py
```

This method is useful because you can run programs without an IDE, which is useful when running programs on servers or other computers.

이 방법은 IDE 없이도 프로그램을 실행할 수 있어서 서버나 다른 컴퓨터에서 프로그램을 실행할 때 유용합니다.

### Method 3: Interactive Mode (대화형 모드)

Type just `python` at the terminal to enter interactive mode. In this mode, you can type code line by line and immediately see the results. It's very useful for simple calculations or testing.

터미널에서 `python`이라고만 입력하면 대화형 모드로 진입합니다. 이 모드에서는 코드를 한 줄씩 입력하고 즉시 결과를 확인할 수 있습니다. 간단한 계산이나 테스트를 할 때 매우 유용합니다.

```python
# Interactive mode example (대화형 모드 예제)
>>> print("Hello!")
Hello!
>>> 10 + 20
30
>>> exit()  # Exit interactive mode (대화형 모드 종료)
```

---

## 5️⃣ Understanding Errors (오류 이해하기)

As you program, you will definitely encounter errors. This is a normal process, and even experienced programmers encounter errors every day. The important thing is to learn to read and understand errors without fear.

프로그래밍을 하다 보면 반드시 오류(error)를 만나게 됩니다. 이것은 정상적인 과정이며, 심지어 경험 많은 프로그래머들도 매일 오류를 마주합니다. 중요한 것은 오류를 두려워하지 않고 읽고 이해하는 방법을 배우는 것입니다.

### Syntax Error (문법 오류)

A syntax error occurs when you violate Python's rules. It's like having grammatical errors in an English sentence.

문법 오류는 파이썬의 규칙을 어겼을 때 발생합니다. 마치 영어 문장에서 문법이 틀린 것과 같습니다.

```python
# Incorrect code - quote is not closed (잘못된 코드 - 따옴표를 닫지 않음)
print("Hello, World!)
```

When you run this code, you will see the following error message:

이 코드를 실행하면 다음과 같은 오류 메시지가 나타납니다:

```
SyntaxError: unterminated string literal
```

Although the error message is in English, if you read it slowly, you can identify the problem. "unterminated string literal" means an unclosed string, which indicates that you didn't properly close the quote.

오류 메시지는 영어로 되어 있지만 천천히 읽으면 문제를 파악할 수 있습니다. "unterminated string literal"은 "끝나지 않은 문자열"이라는 뜻으로, 따옴표를 제대로 닫지 않았다는 의미입니다.

### Name Error (이름 오류)

This occurs when you try to use a variable or function that hasn't been defined.

정의하지 않은 변수나 함수를 사용하려고 할 때 발생합니다.

```python
# Incorrect code - using a variable without defining it
# (잘못된 코드 - 변수를 정의하지 않고 사용)
print(message)
```

```
NameError: name 'message' is not defined
```

This error tells you that the name `message` has not been defined. You must first assign a value to a variable before using it.

이 오류는 `message`라는 이름이 정의되지 않았다고 알려줍니다. 변수를 사용하기 전에 먼저 값을 할당해야 합니다.

---

## 6️⃣ Good Coding Habits (좋은 코드 작성 습관)

Developing good habits from the beginning will be a great help later. Just as it's important to learn the correct posture when first learning to drive, in programming it's important to learn the right way from the beginning.

처음부터 좋은 습관을 들이면 나중에 큰 도움이 됩니다. 마치 처음 운전을 배울 때 올바른 자세를 익히는 것처럼, 프로그래밍도 처음부터 바른 방법을 익히는 것이 중요합니다.

### Using Meaningful Variable Names (의미 있는 변수명 사용하기)

Variable names should clearly indicate what that variable stores.

변수 이름은 그 변수가 무엇을 저장하는지 명확하게 알려주어야 합니다.

```python
# Bad example (나쁜 예)
a = 20
b = 5

# Good example (좋은 예)
student_age = 20
class_size = 5
```

Anyone can see that `student_age` refers to a student's age and `class_size` refers to the number of students in the class.

누가 봐도 `student_age`는 학생의 나이를, `class_size`는 반 인원수를 의미한다는 것을 알 수 있습니다.

### Writing Comments (주석 작성하기)

For complex code or important parts, add comments to make it easier to understand when you review the code later.

복잡한 코드나 중요한 부분에는 주석을 달아서 나중에 코드를 다시 볼 때 이해하기 쉽게 만듭니다.

```python
# Program to calculate student's average score
# (학생의 평균 점수를 계산하는 프로그램)
english_score = 85  # English test score (영어 시험 점수)
history_score = 90  # History test score (역사 시험 점수)
math_score = 88  # Math test score (수학 시험 점수)

# Calculate average of three subjects (세 과목의 평균 계산)
average = (english_score + history_score + math_score) / 3
print("Average score:", average)
```

### Using Consistent Indentation (일관된 들여쓰기 사용하기)

Unlike other languages, indentation is part of Python's syntax. Typically, 4 spaces are used, and you should not mix tabs and spaces.

파이썬은 다른 언어와 달리 들여쓰기(indentation)가 문법의 일부입니다. 일반적으로 스페이스 4칸을 사용하며, 탭과 스페이스를 섞어 쓰지 않아야 합니다.

---

## 📝 Summary of Key Concepts (핵심 개념 정리)

This week's learning can be summarized as follows. Python is an easy-to-read and easy-to-learn programming language used in various fields from web development to artificial intelligence. To write a Python program, you first need to install the Python interpreter, and then install development tools like VS Code or PyCharm.

이번 주차에서 배운 내용을 정리하면 다음과 같습니다. 파이썬은 읽기 쉽고 배우기 쉬운 프로그래밍 언어로, 웹 개발부터 인공지능까지 다양한 분야에서 사용됩니다. 파이썬 프로그램을 작성하려면 먼저 파이썬 인터프리터를 설치하고, VS Code나 PyCharm 같은 개발 도구를 설치해야 합니다.

The most basic Python command is `print()`, which is used to output text to the screen. To receive input from the user, use the `input()` function, which always returns a string type, so if you want to do numeric calculations, you must convert using `int()` or `float()` functions.

가장 기본적인 파이썬 명령어는 `print()`로, 화면에 텍스트를 출력할 때 사용합니다. 사용자로부터 입력을 받을 때는 `input()` 함수를 사용하며, 이 함수는 항상 문자열 타입으로 값을 반환하므로 숫자 계산을 하려면 `int()`나 `float()` 함수로 변환해야 합니다.

Comments start with `#` and are used to explain code. Being able to read and understand error messages is a very important skill, and you should develop the habit of using meaningful variable names and writing comments from the beginning.

주석은 `#`으로 시작하며 코드를 설명하는 데 사용됩니다. 오류 메시지를 읽고 이해하는 것은 매우 중요한 기술이며, 처음부터 의미 있는 변수명을 사용하고 주석을 작성하는 습관을 들여야 합니다.

---

## 💡 Practical Assignments (실습 과제)

### Assignment 1: Self-Introduction Program (과제 1: 자기소개 프로그램)

Write a program that receives the user's name, age, and favorite food, and displays them in the following format:

사용자로부터 이름, 나이, 좋아하는 음식을 입력받아서 다음과 같은 형식으로 출력하는 프로그램을 작성하세요.

```
=== Self-Introduction ===
Name: Emily Davis
Age: 20 years old
Favorite Food: Pizza
```

### Assignment 2: Temperature Conversion Calculator (과제 2: 온도 변환 계산기)

Write a program that receives Fahrenheit temperature and converts it to Celsius. The conversion formula is `Celsius = (Fahrenheit - 32) × 5/9`.

화씨 온도를 입력받아서 섭씨 온도로 변환하는 프로그램을 작성하세요. 변환 공식은 `섭씨 = (화씨 - 32) × 5/9` 입니다.

```python
# Hint
fahrenheit = input("Enter the Fahrenheit temperature: ")
fahrenheit = float(fahrenheit)  # Convert to float (실수로 변환)
# Add conversion calculation here (여기에 변환 계산을 추가하세요)
```

---

## ✅ Quiz (퀴즈)

### [Beginner] Question 1

Which of the following is the correct file extension for a Python file?

다음 중 파이썬 파일의 확장자로 올바른 것은?

1. .txt
2. .py
3. .python
4. .pyt

### [Intermediate] Question 2

What is the output of the following code?

다음 코드의 실행 결과로 올바른 것은?

```python
x = "10"
y = "20"
print(x + y)
```

1. 30
2. 1020
3. "1020"
4. Error

### [Intermediate] Question 3

Which function is used to receive keyboard input from the user?

사용자로부터 키보드 입력을 받을 때 사용하는 함수는?

1. get()
2. input()
3. read()
4. scan()

### [Intermediate] Question 4

Which line is not a comment?

다음 코드에서 주석이 아닌 줄은?

```python
# This is a comment
print("Hello")  # Display on screen
# Program end
```

1. Line 1
2. Line 2
3. Line 3
4. All are comments

---

## 🔑 Quiz Answers and Explanations (퀴즈 정답 및 해설)

**Question 1 Answer: 2**

The file extension for Python files is `.py`. This is short for Python and allows the operating system to recognize this file as Python code.

파이썬 파일의 확장자는 `.py`입니다. 이는 Python의 줄임말로, 운영체제가 이 파일을 파이썬 코드로 인식하게 합니다.

**Question 2 Answer: 3**

Both `x` and `y` are strings, so the `+` operator concatenates (combines) the strings. Therefore, "10" and "20" are concatenated to output "1020". To calculate as numbers, you should write `int(x) + int(y)`.

`x`와 `y`는 모두 문자열이므로 `+` 연산자는 문자열을 연결(concatenation)합니다. 따라서 "10"과 "20"이 연결되어 "1020"이 출력됩니다. 숫자로 계산하려면 `int(x) + int(y)`로 작성해야 합니다.

**Question 3 Answer: 2**

The function to receive keyboard input from the user is `input()`. This function always returns a string type value.

사용자로부터 키보드 입력을 받는 함수는 `input()`입니다. 이 함수는 항상 문자열 타입으로 값을 반환합니다.

**Question 4 Answer: 2**

Line 2 with `print("Hello")` is actual executable code. Only the part after it, `# Display on screen`, is a comment.

2번째 줄의 `print("Hello")`는 실제 실행되는 코드입니다. 뒤에 있는 `# Display on screen` 부분만 주석입니다.

---

## 🎯 Preview of Next Chapter (다음 장 예고)

Next week, we will learn in detail about variables and data types. You will learn about various data types such as integers, floats, strings, and booleans, and how to declare and use variables. Please review the content from this week sufficiently and complete the practical assignments!

다음 주차에는 변수와 데이터 타입에 대해 자세히 배웁니다. 정수, 실수, 문자열, 불린 같은 다양한 데이터 타입과 변수를 선언하고 사용하는 방법을 학습하게 됩니다. 이번 주에 배운 내용을 충분히 복습하고, 실습 과제를 완성해보세요!

---

Thank you for your attention.   
Cho Jeonghyun ([peterchokr@gmail.com](mailto:peterchokr@gmail.com)). Yeungnam University College

"Produced in collaboration with Claude and Gemini."
