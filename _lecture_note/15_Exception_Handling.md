# Chapter 15. Exception Handling

---

## 📚 Learning Objectives

After completing this chapter, you will be able to detect and handle errors that occur during program execution. Through exception handling, you can create robust programs that continue to work stably even in unexpected situations, rather than crashing.

이번 장을 마치면 여러분은 프로그램 실행 중 발생하는 오류를 감지하고 처리할 수 있습니다. 예외 처리를 통해 프로그램이 예상치 못한 상황에서도 중단되지 않고 안정적으로 동작하는 견고한 프로그램을 만들 수 있습니다.

---

## 1️⃣ What is an Exception? (예외란 무엇인가?)

When you create a program, unexpected situations occur. For example, a user might enter text when numbers are required, or try to divide by zero, or attempt to open a file that doesn't exist. In these situations, Python raises an **exception** . If you don't handle it, the program stops at that point. For users, this is a very confusing experience.

프로그램을 만들다 보면 예상치 못한 상황들이 발생합니다. 사용자가 숫자를 입력해야 하는데 문자를 입력한다거나, 0으로 나누기를 시도한다거나, 존재하지 않는 파일을 열려고 할 때 등입니다. 이런 상황에서 파이썬은 **예외(Exception)** 를 발생시키고, 아무 조치도 취하지 않으면 프로그램이 그 자리에서 멈춰버립니다. 사용자 입장에서는 매우 당황스러운 경험이죠.

### Common Exception Situations (예외가 발생하는 대표적인 상황들)

```python
# ValueError: Converting text to a number (숫자를 입력받으려고 했는데...)
age = int(input("Age: "))
# If user enters "twenty-five"? (사용자가 "스물다섯"이라고 입력하면?)
# ValueError: invalid literal for int() with base 10: 'twenty-five'
# Program stops! (프로그램 중단!) ❌
```

With exception handling you get:

- Program continues without stopping
- Friendly error messages for users
- Chance to correct and retry
- Professional and stable programs

예외 처리를 하면:

- 프로그램이 중단되지 않고 계속 실행
- 사용자에게 친절한 오류 메시지 제공
- 문제를 수정하고 다시 시도할 기회 제공
- 전문적이고 안정적인 프로그램 구현

---

## 2️⃣ try-except Basics - Catching Exceptions (try-except 기본 - 예외 잡기)

The way to safely wrap code that might cause errors is the `try-except` statement. It's like putting a safety net under dangerous code.

예외가 발생할 수 있는 코드를 안전하게 감싸는 방법이 바로 `try-except` 문입니다. 마치 안전망을 치는 것과 같습니다.

### How try-except Works (try-except의 작동 원리)

```python
try:
    # Put risky code here (위험할 수 있는 코드를 여기에)
    # "Try running this code. Problems might happen." (이 코드를 실행해봐. 문제가 생길 수 있어)
    risky_operation()
  
except:
    # Code to run if an exception occurs (예외가 발생했을 때 실행할 코드)
    # "If a problem happens, do this." (문제가 생기면 이렇게 처리해)
    safe_response()
```

### Understanding with Simple Examples (간단한 예제로 이해하기)

**Code without exception handling:**

```python
# Risky code (위험한 코드)
number = int(input("Enter a number: "))
print(f"Number entered: {number}")
print("Program continues...")

# If user enters "abc"? (사용자가 "abc"를 입력하면?)
# ValueError occurs! (ValueError 발생!)
# Program immediately stops! (프로그램 즉시 종료!)
# "Program continues..." is not printed ("Program continues..."은 출력되지 않음)
```

**Code with exception handling:**

```python
# Safe code (안전한 코드)
try:
    number = int(input("Enter a number: "))
    print(f"Number entered: {number}")
except:
    print("❌ Error! That's not a number.")
    print("💡 Please enter a number.")

print("Program continues...")

# If user enters "abc"? (사용자가 "abc"를 입력하면?)
# except block runs (except 블록이 실행됨)
# Friendly message shown (친절한 메시지 출력)
# Program keeps running! (프로그램은 계속 실행!) ✅
```

**Execution result comparison:**

```
[Normal input - 25]
Enter a number: 25
Number entered: 25
Program continues...

[Wrong input - abc]
Enter a number: abc
❌ Error! That's not a number.
💡 Please enter a number.
Program continues...
```

The program keeps running without stopping!

프로그램이 중단되지 않고 계속 실행됩니다!



### When to Use try-except? (try-except를 언제 사용하나요?)

Exception handling is used in **"places where problems can occur"**:

예외 처리는 **"문제가 생길 수 있는 곳"**에 사용합니다:

1. **User Input**: Users can enter unexpected values**사용자 입력**: 사용자는 예상 못한 값을 입력할 수 있음
2. **File Operations**: Files might be missing, have permission issues, or be corrupted
   **파일 작업**: 파일이 없거나, 권한이 없거나, 손상될 수 있음
3. **Network Communication**: Internet connection might drop, server might not respond
   **네트워크 통신**: 인터넷 연결이 끊기거나, 서버가 응답 안 할 수 있음
4. **External Data**: Data formats like JSON, CSV might be wrong
   **외부 데이터**: JSON, CSV 등 데이터 형식이 잘못될 수 있음
5. **Calculations**: Division by zero, square root of negative numbers, etc.
   **계산**: 0으로 나누기, 음수의 제곱근 등

⚠️ **Warning**: Don't wrap all code in try-except! It can hide real bugs. Use it selectively for places where problems can occur.

⚠️ **주의**: 모든 코드를 try-except로 감싸면 안 됩니다! 진짜 버그를 숨길 수 있습니다. 문제가 생길 수 있는 부분만 선택적으로 사용하세요.

### Example 1: Safe Calculator (예제 1: 안전한 계산기)

A calculator that handles division by zero errors.

0으로 나누기 오류를 처리하는 계산기입니다.

```python
# Safe division calculator (안전한 나눗셈 계산기)
print("🧮" + "=" * 38 + "🧮")
print("   Division Calculator")
print("🧮" + "=" * 38 + "🧮")

while True:
    print("\n" + "=" * 40)
  
    try:
        num1 = float(input("First number: "))
        num2 = float(input("Second number: "))
  
        result = num1 / num2
  
        print("\n" + "-" * 40)
        print(f"{num1} ÷ {num2} = {result}")
        print("-" * 40)
  
    except ZeroDivisionError:
        print("\n❌ Cannot divide by zero!")
  
    except ValueError:
        print("\n❌ Please enter a number!")
  
    except:
        print("\n❌ An unknown error occurred!")
  
    # Ask to continue (계속할지 물어보기)
    choice = input("\nContinue? (Y/N): ")
    if choice != "Y" and choice != "y":
        print("\nCalculator closed.")
        break
```

---

## 3️⃣ Multiple Exception Types - Catching Precisely (다양한 예외 유형 - 정확하게 잡기)

So far we've used `except:` to catch all exceptions at once. But what if you want to handle different types of exceptions differently?

지금까지는 `except:` 만 사용해서 모든 예외를 한꺼번에 잡았습니다. 하지만 예외 종류에 따라 다르게 처리하고 싶다면 어떻게 해야 할까요?

### Why Distinguish Exception Types? (왜 예외 유형을 구분해야 할까요?)

```python
# Handling all exceptions the same way (not recommended) (모든 예외를 똑같이 처리 - 권장 안 함)
try:
    age = int(input("Age: "))
    result = 100 / age
except:
    print("An error occurred!")  # What error? Nobody knows! (어떤 오류인지 모름!)
```

When a user enters "twenty" versus "0", the error causes are different. But if you show the same message, the user won't know what went wrong.

사용자가 "스물"을 입력했을 때와 "0"을 입력했을 때, 오류 원인이 다릅니다. 하지만 같은 메시지만 보여주면 사용자는 무엇이 잘못됐는지 알 수 없습니다.

### Common Exception Types (주요 예외 유형)

Python has many different exception types. Let's learn the ones you'll encounter frequently:

파이썬의 예외는 종류가 매우 다양합니다. 자주 만나는 것들을 알아봅시다:

```
📋 Frequently Encountered Exceptions (자주 만나는 예외들)

🔢 Numbers (숫자 관련)
├─ ValueError        : Wrong value (잘못된 값) - int("abc")
├─ ZeroDivisionError : Division by zero (0으로 나누기)
└─ OverflowError     : Number too large (숫자가 너무 큼)

📁 Files (파일 관련)
├─ FileNotFoundError : File missing (파일이 없음)
├─ PermissionError   : No permission (권한 없음)
└─ IsADirectoryError : Is a directory, not a file (파일이 아닌 폴더)

📚 Data Structures (자료구조 관련)
├─ IndexError        : Index out of range (인덱스 범위 초과)
├─ KeyError          : Dictionary key missing (딕셔너리 키 없음)
├─ KeyboardInterrupt : Ctrl+C pressed (Ctrl+C로 중단)
└─ TypeError         : Type mismatch (타입 불일치)

🌐 Others (기타)
├─ AttributeError    : Attribute/method missing (속성/메서드 없음)
├─ ImportError       : Module not found (모듈을 찾을 수 없음)
└─ NameError         : Variable not defined (변수 이름이 정의 안 됨)
```

### Handling Specific Exceptions (특정 예외만 처리하기)

By specifying the exception type, you catch only that specific exception:

예외 유형을 지정하면 그 예외만 잡을 수 있습니다:

```python
# Handle only ValueError (ValueError만 처리)
try:
    age = int(input("Age: "))
    print(f"You are {age} years old.")
  
except ValueError:
    print("❌ Please enter a number!")
    print("💡 Example: 25")
```

Now only `ValueError` is caught, and other errors stop the program. This is safer because you don't hide unexpected errors.

이제 `ValueError`만 잡고, 다른 오류는 프로그램을 중단시킵니다. 이것이 더 안전합니다. 예상하지 못한 오류를 숨기지 않기 때문입니다.

### Handling Multiple Exceptions Differently (여러 예외를 다르게 처리하기)

You can show a different message for each exception type:

각 예외마다 다른 메시지를 보여줄 수 있습니다:

```python
# Handle multiple exceptions separately (여러 예외를 구분해서 처리)
try:
    # Get user input (사용자 입력)
    numbers = [1, 2, 3, 4, 5]
    index = int(input("Index (0-4): "))
  
    # Access by index (인덱스로 접근)
    print(f"Selected number: {numbers[index]}")
  
    # Calculate (계산)
    result = 100 / index
    print(f"Calculation result: {result}")

except ValueError:
    # int() conversion failed (int() 변환 실패)
    print("❌ Please enter a number!")
  
except IndexError:
    # List is out of range (리스트 범위 벗어남)
    print("❌ Please enter 0 to 4!")
    print(f"💡 Valid indices: 0, 1, 2, 3, 4")
  
except ZeroDivisionError:
    # Division by zero (0으로 나누기)
    print("❌ Cannot use 0!")
    print("💡 Please enter 1 or greater.")
```

**Execution examples:**

```
[Case 1: Text input]
Index (0-4): abc
❌ Please enter a number!

[Case 2: Out of range]
Index (0-4): 10
❌ Please enter 0 to 4!
💡 Valid indices: 0, 1, 2, 3, 4

[Case 3: Zero input]
Index (0-4): 0
Selected number: 1
❌ Cannot use 0!
💡 Please enter 1 or greater.

[Case 4: Normal]
Index (0-4): 2
Selected number: 3
Calculation result: 50.0
```

### Handling Multiple Exceptions the Same Way (여러 예외를 같은 방식으로 처리하기)

Sometimes you want to handle multiple exceptions identically. Use parentheses to group them:

때로는 여러 예외를 똑같이 처리하고 싶을 때가 있습니다. 괄호로 묶으면 됩니다:

```python
try:
    # Try to open file (파일 열기 시도)
    with open(filename, "r") as file:
        content = file.read()
  
except (FileNotFoundError, PermissionError):
    # Handle both exceptions the same way (두 예외를 같은 방식으로 처리)
    print("❌ Cannot open file!")
    print("💡 Check filename and permissions.")
```



---

## 4️⃣ finally - Code That Always Runs (finally - 항상 실행되는 코드)

The `finally` block always executes **regardless of whether an exception occurred or not**. It's like specifying "a task that must be done no matter what happens."

`finally` 블록은 예외 발생 여부와 **관계없이 항상 실행**됩니다. 마치 "어떤 일이 있어도 반드시 해야 하는 일"을 지정하는 것입니다.

### Why finally is Needed (finally가 필요한 이유)

If you open a file, you must close it. If you connect to a database, you must disconnect. If you borrow resources, you must return them. These "cleanup tasks" must happen whether an exception occurs or not.

파일을 열었으면 닫아야 하고, 데이터베이스에 연결했으면 연결을 끊어야 하고, 자원을 빌렸으면 반납해야 합니다. 예외가 발생하든 안 하든 이런 "정리 작업"은 반드시 해야 합니다.

### Basic Example (기본 예제)

```python
try:
    print("1. Start operation (작업 시작)")
    result = 10 / 0  # Exception! (예외 발생!)
    print("2. Complete operation (작업 완료)")  # Won't run (실행 안 됨)
  
except ZeroDivisionError:
    print("3. Handle error (오류 처리)")
  
finally:
    print("4. Cleanup (항상 실행)")
  
print("5. Program continues (프로그램 계속)")
```

**Execution result:**

```
1. Start operation (작업 시작)
3. Handle error (오류 처리)
4. Cleanup (항상 실행)
5. Program continues (프로그램 계속)
```

"2. Complete operation" didn't run, but "4. Cleanup" did!

"2. Complete operation"은 실행되지 않았지만, "4. Cleanup"은 실행되었습니다!



---

## 5️⃣ Raising Exceptions (예외 직접 발생시키기 - raise)

You can create and raise your own exceptions using the `raise` keyword to enforce business rules.

`raise` 키워드를 사용하여 직접 예외를 발생시켜 비즈니스 규칙을 강제할 수 있습니다.

### Why Raise Exceptions Deliberately? (왜 일부러 예외를 발생시킬까요?)

When a user does something invalid, you can raise an exception that your program's caller can handle properly.

사용자가 유효하지 않은 작업을 할 때, 프로그램의 호출자가 적절하게 처리할 수 있는 예외를 발생시킬 수 있습니다.

### How to Use raise (raise 키워드 사용법)

```python
# Validate age (나이 검증)
def validate_age(age):
    """Check if age is valid (나이가 유효한지 확인)"""
    if age < 0:
        raise ValueError("Age cannot be negative")
    if age > 150:
        raise ValueError("Age is too high")
    return True

try:
    validate_age(-5)
except ValueError as e:
    print(f"Validation error: {e}")
```

---

## 📝 Key Concepts Summary (핵심 개념 정리)

### Exception (예외)

An error that occurs during program execution. If not handled, the program stops.

프로그램 실행 중 발생하는 오류입니다. 처리하지 않으면 프로그램이 중단됩니다.

```python
# Common exception types (주요 예외 종류)
ValueError          # Wrong value (잘못된 값)
ZeroDivisionError   # Division by zero (0으로 나누기)
FileNotFoundError   # File not found (파일 없음)
IndexError          # Index out of range (인덱스 범위 초과)
KeyError            # Dictionary key not found (딕셔너리 키 없음)
```

### try-except Basics (try-except 기본)

```python
try:
    # Code that might raise an exception (예외가 발생할 수 있는 코드)
    risky_code()
except ValueError:
    # Handle ValueError (ValueError 처리)
    handle_error()
except KeyError as e:
    # Get exception information (예외 정보 받기)
    print(f"Error: {e}")
```

### Complete Structure (완전한 구조)

```python
try:
    code()              # Try to execute (실행 시도)
except ValueError:      # On exception (예외 발생시)
    handle_error()
else:                   # If no exception (예외 없을 때만)
    success()
finally:                # Always (항상)
    cleanup()
```

### raise - Raising Exceptions (raise - 예외 발생시키기)

```python
def set_age(age):
    """Validate and set age (나이 검증 및 설정)"""
    if age < 0:
        raise ValueError("Age must be non-negative")
    return age
```

### Key Points to Remember (기억할 핵심)

- Handle exceptions safely with try-excepttry-except로 예외를 안전하게 처리하세요
- Specify exact exception types (ValueError, KeyError, etc.)구체적인 예외 타입을 지정하세요 (ValueError, KeyError 등)
- Use `as` to get exception messages `as`를 사용하여 예외 메시지를 받으세요
- `finally` always runs - use for cleanup `finally`는 항상 실행됩니다 - 정리 작업에 사용하세요
- Use `raise` to create custom exceptions
  `raise`로 직접 예외를 발생시킬 수 있습니다

---

## 💡 Practice Assignments (실습 과제)

### Assignment 1: Safe List Access (과제 1: 안전한 리스트 접근)

Get an index from user and print list item. Handle invalid inputs safely.

인덱스 입력을 받아 리스트 항목을 출력하되, 잘못된 입력을 처리하세요.

```python
# Hint (힌트)
fruits = ["apple", "banana", "orange", "grape", "strawberry"]

try:
    index = int(input("Index (0-4): "))
    print(f"Selected: {fruits[index]}")
except ValueError:
    print("❌ Please enter a number")
except IndexError:
    print("❌ Index out of range")
```

**What you'll learn:**

- Handling ValueError and IndexError
- Getting user input safely
- Using multiple except blocks

**배울 것:**

- ValueError와 IndexError 처리
- 사용자 입력을 안전하게 받기
- 여러 except 블록 사용

### Assignment 2: File Backup (과제 2: 파일 백업)

Read a file and create a backup copy. Handle all possible exceptions.

파일을 읽어서 백업 파일로 복사하되, 모든 예외를 처리하세요.

```python
# Hint (힌트)
try:
    source = input("Source filename: ")
    with open(source, "r", encoding="utf-8") as f:
        content = f.read()
  
    backup = source + ".backup"
    with open(backup, "w", encoding="utf-8") as f:
        f.write(content)
  
    print(f"✓ Backup created: {backup}")
  
except FileNotFoundError:
    print("❌ File not found")
except PermissionError:
    print("❌ Permission denied")
finally:
    print("Operation complete")
```

**What you'll learn:**

- File I/O with exception handling
- Using finally for cleanup
- Real-world error handling

**배울 것:**

- 파일 I/O와 예외 처리
- finally를 정리 작업에 사용
- 현실적인 오류 처리

---

## ✅ Quiz (퀴즈)

### [Beginner] Question 1

Which keyword combination handles exceptions in Python?

파이썬에서 예외를 처리하는 키워드 조합은?

```python
1. try-catch
2. try-except
3. if-else
4. begin-rescue
```

### [Intermediate] Question 2

What is the output when user enters "abc"?

사용자가 "abc"를 입력했을 때 실행 결과는?

```python
try:
    num = int(input("Number: "))
    print(num * 2)
except ValueError:
    print("Error!")
```

1. Error!
2. abc
3. abc2
4. Program stops (프로그램 중단)

### [Intermediate] Question 3

Which statement about finally is correct?

finally 절의 특징은?

```python
1. Only runs when exception occurs
   (예외 발생시에만 실행)
2. Only runs when no exception
   (예외 없을 때만 실행)
3. Always runs
   (항상 실행)
4. Cannot be used
   (사용 불가)
```

### [Advanced] Question 4

When is "Success" printed?

"성공"이 출력되는 경우는?

```python
try:
    x = int(input())
    y = 10 / x
except ZeroDivisionError:
    print("Zero error (0 오류)")
except ValueError:
    print("Value error (값 오류)")
else:
    print("Success (성공)")
```

1. Input 0
2. Input abc
3. Input 5
4. Never printed

### [Advanced] Question 5

Which keyword raises an exception?

예외를 발생시키는 키워드는?

```python
1. throw
2. raise
3. error
4. exception
```

---

## 🔑 Quiz Answers and Explanations (퀴즈 정답 및 해설)

**Answer 1: 2**

Python uses `try-except` to handle exceptions. Other languages like Java use `try-catch`, but Python uses `try-except`.

파이썬에서는 `try-except` 키워드로 예외를 처리합니다. 자바 등 다른 언어는 `try-catch`를 사용하지만, 파이썬은 `try-except`입니다.

**Answer 2: 1**

"abc" cannot be converted to an integer, so `ValueError` occurs and "Error!" is printed from the except block.

"abc"는 정수로 변환할 수 없어 `ValueError`가 발생하고, except 블록의 "Error!"가 출력됩니다.

**Answer 3: 3**

The `finally` block executes whether an exception occurred or not. It's commonly used for cleanup tasks like closing files.

`finally` 절은 예외 발생 여부와 관계없이 항상 실행됩니다. 파일 닫기 같은 정리 작업에 사용됩니다.

**Answer 4: 3**

Entering 5 doesn't cause any exception (no ValueError and no ZeroDivisionError), so the `else` block runs and "Success" is printed. Entering 0 or abc causes exceptions.

5를 입력하면 예외가 발생하지 않아 `else` 블록이 실행되어 "Success"가 출력됩니다. 0이나 abc를 입력하면 예외가 발생합니다.

**Answer 5: 2**

The `raise` keyword is used to raise exceptions. Java and C++ use `throw`, but Python uses `raise`.

`raise` 키워드로 예외를 발생시킵니다. 자바와 C++은 `throw`를 사용하지만, 파이썬은 `raise`입니다.

---

## 🎯 Next Chapter Preview (다음 장 예고)

In the next chapter, we'll learn about modules and packages. You'll discover how to reuse code from others and organize your code into modules for better management. We'll also explore Python's powerful standard library and how to use external packages. With modules and packages, you can build larger, more complex applications efficiently!

다음 장에서는 모듈과 패키지에 대해 배웁니다. 다른 사람이 만든 코드를 재사용하고, 자신의 코드를 모듈로 만들어 관리하는 방법을 학습합니다. 파이썬의 강력한 표준 라이브러리와 외부 패키지 활용법도 배우게 됩니다. 모듈과 패키지를 통해 더 크고 복잡한 애플리케이션을 효율적으로 만들 수 있습니다!

---

Thank you for your attention.   
Cho Jeonghyun ([peterchokr@gmail.com](mailto:peterchokr@gmail.com)). Yeungnam University College

"Produced in collaboration with Claude and Gemini."
