# Chapter 14. File Input and Output

---

## 📚 Learning Objectives

After completing this chapter, you will be able to read and write text files, and save and load data even after the program has ended. File input and output is an essential feature for creating practical programs.

이번 장을 마치면 여러분은 텍스트 파일을 읽고 쓸 수 있으며, 프로그램이 종료된 후에도 데이터를 저장하고 불러올 수 있습니다. 파일 입출력은 실용적인 프로그램을 만드는 데 필수적인 기능입니다.

---

## 1️⃣ What is File Input and Output? (파일 입출력이란?)

Until now, the programs you created lost all data when execution ended. By saving data to a file, you can reload the previous data even when you run the program again.

지금까지 만든 프로그램들은 실행이 끝나면 데이터가 모두 사라졌습니다. 파일에 데이터를 저장하면 프로그램을 다시 실행해도 이전 데이터를 불러올 수 있습니다.

```
Program Memory vs File Storage (프로그램 메모리 vs 파일 저장)

┌──────────────────────┐      ┌──────────────────────┐
│ Program Memory       │      │ File Storage         │
├──────────────────────┤      ├──────────────────────┤
│ Fast access          │      │ Permanent storage    │
│ Temporary            │      │ Slow access          │
│ Deleted when exit    │      │ Remains after exit   │
└──────────────────────┘      └──────────────────────┘
```

---

## 2️⃣ Writing to Text Files (텍스트 파일 쓰기)

### Opening and Closing Files (파일 열기와 닫기)

```python
# Open file (파일 열기)
file = open("test.txt", "w")  # w = write mode (쓰기 모드)
file.write("Hello!")
file.close()  # Must close! (반드시 닫아야 함!)
```

⚠️ **Important**: You must close the file with `close()`!

⚠️ **중요**: 파일을 열면 반드시 `close()`로 닫아야 합니다!

### Using the with Statement (with 문 사용)

The `with` statement automatically closes the file when you're done, so you don't have to manually close it. This is the recommended way to work with files.

`with` 문을 사용하면 파일 작업이 끝나면 자동으로 파일이 닫히므로 수동으로 닫을 필요가 없습니다. 이것이 파일 작업에 권장되는 방법입니다.

```python
# Use with statement (with 문 사용 - 자동으로 닫힘)
with open("test.txt", "w") as file:
    file.write("Hello!\n")
    file.write("I am learning Python.")
# File automatically closes here (여기서 자동으로 파일이 닫힘)
```



---

## 3️⃣ Reading Text Files (텍스트 파일 읽기)

### read() - Read Entire File (read() - 전체 읽기)

The `read()` method reads the entire file as a single string. This is useful when you want to process the entire file at once.

`read()` 메서드는 파일 전체를 하나의 문자열로 읽습니다. 파일 전체를 한 번에 처리하고 싶을 때 유용합니다.

```python
# Read entire file as string (파일 전체를 문자열로 읽기)
with open("test.txt", "r", encoding="utf-8") as file:
    content = file.read()
    print(content)
```

### readline() - Read Line by Line (readline() - 한 줄씩 읽기)

The `readline()` method reads one line at a time from the file. Each call to `readline()` reads the next line.

`readline()` 메서드는 파일에서 한 줄씩 읽습니다. `readline()`을 호출할 때마다 다음 줄을 읽습니다.

```python
# Read line by line (한 줄씩 읽기)
with open("test.txt", "r", encoding="utf-8") as file:
    line1 = file.readline()
    line2 = file.readline()
    print(line1)
    print(line2)
```

### readlines() - Read All Lines as List (readlines() - 모든 줄을 리스트로 읽기)

The `readlines()` method reads all lines of the file and returns them as a list. Each element in the list is one line of the file.

`readlines()` 메서드는 파일의 모든 줄을 읽어서 리스트로 반환합니다. 리스트의 각 원소는 파일의 한 줄입니다.

```python
# Read all lines as list (모든 줄을 리스트로 읽기)
with open("test.txt", "r", encoding="utf-8") as file:
    lines = file.readlines()
    for line in lines:
        print(line.strip())  # Remove newline (줄바꿈 제거)
```

## 4️⃣ File Modes (파일 모드)

When opening a file, you specify a mode that tells Python how you want to use the file. Different modes allow you to read, write, or append to files.

파일을 열 때 모드를 지정하여 파일을 어떤 방식으로 사용할 것인지 파이썬에 알려줍니다. 다양한 모드를 통해 파일을 읽고, 쓰고, 추가할 수 있습니다.

```
File Modes (파일 모드)

┌──────┬────────────────────────────────────────────┐
│ Mode │ Description                                │
├──────┼────────────────────────────────────────────┤
│  r   │ Read (error if file doesn't exist)         │
│  w   │ Write (deletes existing content)           │
│  a   │ Append (adds to end of file)               │
│  r+  │ Read and write                             │
│  w+  │ Write and read (deletes existing)          │
│  a+  │ Append and read                            │
└──────┴────────────────────────────────────────────┘

파일 모드

┌──────┬────────────────────────────────────────────┐
│ 모드 │ 설명                                       │
├──────┼────────────────────────────────────────────┤
│  r   │ 읽기 (파일이 없으면 오류)                  │
│  w   │ 쓰기 (기존 내용 삭제)                      │
│  a   │ 추가 (파일 끝에 추가)                      │
│  r+  │ 읽기+쓰기                                  │
│  w+  │ 쓰기+읽기 (기존 내용 삭제)                 │
│  a+  │ 추가+읽기                                  │
└──────┴────────────────────────────────────────────┘
```

### Understanding Write Mode vs Append Mode (쓰기 모드 vs 추가 모드 이해하기)

The `"w"` mode creates a new file or overwrites an existing file completely. Any data previously in the file is lost. The `"a"` mode, however, keeps the existing content and adds new data to the end of the file.

`"w"` 모드는 새 파일을 만들거나 기존 파일을 완전히 덮어씁니다. 파일에 있던 이전 데이터는 모두 손실됩니다. 그러나 `"a"` 모드는 기존 내용을 유지하고 파일의 끝에 새 데이터를 추가합니다.

```python
# w mode - deletes existing content (w 모드 - 기존 내용 삭제)
with open("test.txt", "w", encoding="utf-8") as file:
    file.write("New content")  # Existing content deleted (기존 내용이 모두 삭제됨)

# a mode - keeps existing content and appends at end (a 모드 - 기존 내용 유지하고 끝에 추가)
with open("test.txt", "a", encoding="utf-8") as file:
    file.write("Additional content")  # Added after existing content (기존 내용 뒤에 추가)
```



---

## 5️⃣ Checking File Existence (파일 존재 확인)

Before working with a file, it's often useful to check whether the file exists. The `os` module provides functions for this.

파일 작업을 하기 전에 파일이 존재하는지 확인하는 것이 유용합니다. `os` 모듈은 이를 위한 함수를 제공합니다.

```python
import os

# Check if file exists (파일 존재 확인)
if os.path.exists("test.txt"):
    print("File exists.")
else:
    print("File does not exist.")

# Delete file (파일 삭제)
if os.path.exists("test.txt"):
    os.remove("test.txt")
    print("File deleted.")
```


---



---

## 📝 Key Concepts Summary (핵심 개념 정리)

To work with files, use the `open()` function to open them and `close()` to close them. Using the `with` statement is recommended because it automatically closes the file.

파일을 다루기 위해 `open()` 함수로 파일을 열고 `close()`로 닫습니다. `with` 문을 사용하면 파일이 자동으로 닫히므로 권장됩니다.

File modes include `"r"` (read), `"w"` (write), and `"a"` (append). Specify `encoding="utf-8"` to correctly handle international characters.

파일 모드는 `"r"`(읽기), `"w"`(쓰기), `"a"`(추가)가 있으며, `encoding="utf-8"`을 지정하여 국제 문자를 올바르게 처리할 수 있습니다.

The `read()` method reads the entire content, `readline()` reads one line, and `readlines()` reads all lines as a list. Use `write()` to write content to a file.

`read()`는 전체 내용을, `readline()`은 한 줄을, `readlines()`는 모든 줄을 리스트로 읽습니다. `write()`로 파일에 내용을 씁니다.

JSON uses a dictionary-like format and is handled with `json.dump()` and `json.load()`.

JSON은 딕셔너리와 유사한 형식으로 `json.dump()`와 `json.load()`로 처리합니다.

---

## 💡 Practice Assignments (실습 과제)

### Assignment 1: Vocabulary Notebook (과제 1: 단어장)

Write a program that saves English words and definitions to a file and provides quizzes.

영어 단어와 뜻을 파일에 저장하고 퀴즈를 내는 프로그램을 작성하세요.

```python
# Hint
# words.txt file format:
# apple,apple (사과)
# banana,banana (바나나)
# cherry,cherry (체리)

# 1. Add word
# 2. Random quiz
# 3. View all
```

### Assignment 2: Budget Ledger (과제 2: 가계부)

Write a program that records income and expenses and shows statistics.

수입과 지출을 기록하고 통계를 보여주는 프로그램을 작성하세요.

```python
# Hint
# ledger.csv file format:
# Date,Type,Item,Amount
# 2024-01-01,Income,Salary,5000
# 2024-01-02,Expense,Food,50

# Statistics: Total Income, Total Expense, Balance
```

---

## ✅ Quiz (퀴즈)

### [Beginner] Question 1

Which code opens a file in write mode?

파일을 쓰기 모드로 여는 코드는?

```python
1. open("file.txt", "r")
2. open("file.txt", "w")
3. open("file.txt", "a")
4. open("file.txt", "x")
```

### [Intermediate] Question 2

What does the following code do?

다음 코드의 역할은?

```python
with open("test.txt", "a") as file:
    file.write("Hello")
```

1. Reads the file (파일을 읽는다)
2. Creates and writes to a new file (파일을 새로 만들고 쓴다)
3. Appends to the end of the file (파일 끝에 추가한다)
4. Deletes the file (파일을 삭제한다)

### [Intermediate] Question 3

Which method reads all lines of a file as a list?

파일의 모든 줄을 리스트로 읽는 메서드는?

```python
1. read()
2. readline()
3. readlines()
4. readall()
```

### [Advanced] Question 4

What is the output of the following code?

다음 코드의 실행 결과는?

```python
with open("test.txt", "w") as file:
    file.write("Line 1\n")
    file.write("Line 2\n")

with open("test.txt", "r") as file:
    content = file.read()
    print(len(content.split("\n")))
```

1. 2
2. 3
3. 4
4. Error (오류 발생)

---

## 🔑 Quiz Answers and Explanations (퀴즈 정답 및 해설)

**Answer 1: 2**

The `"w"` mode opens a file in write mode. If the file doesn't exist, it creates a new one; if it exists, it deletes the existing content.

`"w"` 모드는 파일을 쓰기 모드로 엽니다. 파일이 없으면 새로 만들고, 있으면 기존 내용을 삭제합니다.

**Answer 2: 3**

The `"a"` mode is append mode, which adds content to the end of the file. Existing content is preserved.

`"a"` 모드는 append(추가) 모드로, 파일 끝에 내용을 추가합니다. 기존 내용은 유지됩니다.

**Answer 3: 3**

The `readlines()` method returns all lines of a file as a list.

`readlines()` 메서드는 파일의 모든 줄을 리스트로 반환합니다.

**Answer 4: 2**

Splitting "Line 1\nLine 2\n" by `\n` gives ["Line 1", "Line 2", ""] with a length of 3.

"Line 1\nLine 2\n"를 `\n`으로 split하면 ["Line 1", "Line 2", ""]가 되어 길이는 3입니다.

---

## 🎯 Next Chapter Preview (다음 장 예고)

In the next chapter, we will learn about exception handling. You'll learn how to detect and handle errors that occur during program execution, allowing you to create more stable and robust programs!

다음 장에서는 예외 처리에 대해 배웁니다. 프로그램 실행 중 발생하는 오류를 감지하고 처리하는 방법을 학습하여, 더욱 안정적이고 견고한 프로그램을 만들 수 있게 됩니다!

---

Thank you for your attention.   
Cho Jeonghyun ([peterchokr@gmail.com](mailto:peterchokr@gmail.com)). Yeungnam University College

"Produced in collaboration with Claude and Gemini."
