# Chapter 20. GUI Programming 1 (tkinter Basics)

---

## 📚 Learning Objectives

After completing this chapter, you will be able to create window programs using tkinter. You can arrange buttons, text boxes, labels, and handle click events to create interactive GUI applications with users.

이번 장을 마치면 여러분은 tkinter를 사용하여 윈도우 프로그램을 만들 수 있습니다. 버튼, 텍스트 상자, 레이블 등을 배치하고, 클릭 이벤트를 처리하여 사용자와 상호작용하는 GUI 애플리케이션을 제작할 수 있습니다.

---

## 1️⃣ What is GUI? 

So far, we've created programs with only text in the terminal (black screen). But what about the programs we use daily? They are window programs with buttons, menus, and text boxes!

지금까지 우리는 터미널(검은 화면)에서 텍스트로만 프로그램을 만들었습니다. 하지만 우리가 일상적으로 사용하는 프로그램들은 어떤가요? 버튼, 메뉴, 텍스트 상자가 있는 윈도우 프로그램입니다!

### CLI vs GUI

**CLI (Command Line Interface)** - Terminal, command input (터미널, 명령어 입력)   
**GUI (Graphical User Interface)** - Window, mouse click (윈도우, 마우스 클릭)

```
CLI Example (CLI 예제)           GUI Example (GUI 예제)

$ python calc.py                 Calculator Window
Enter number 1: 10               ┌─────────────────┐
Enter number 2: 20               │ 계산기 [_][□][X]│
Result: 30                       │                 │
                                 │ Result: 30      │
                                 │                 │
                                 │ [7][8][9][+]    │
                                 │ [4][5][6][-]    │
                                 │ [1][2][3][×]    │
                                 └─────────────────┘
```

**Advantages of GUI (GUI의 장점):**

- ✅ Intuitive and easy to use (직관적이고 사용하기 쉬움)
- ✅ Just click with mouse (마우스로 클릭만 하면 됨)
- ✅ Visually appealing (시각적으로 보기 좋음)
- ✅ Accessible to general users (일반 사용자도 쉽게 사용 가능)

### What is tkinter? 

**tkinter** is a GUI library included by default in Python. You can use it right away without any additional installation!

**tkinter**는 파이썬에 기본으로 포함된 GUI 라이브러리입니다. 별도 설치 없이 바로 사용할 수 있습니다!

```python
import tkinter  # Already installed! (이미 설치되어 있음!)
```

---

## 2️⃣ Creating Your First Window 

Let's create the simplest window.

가장 간단한 윈도우부터 만들어봅시다.

### Basic Window 

```python
import tkinter as tk

# Create window (윈도우 생성)
window = tk.Tk()
window.title("My First Program")  # Set title (제목 설정)
window.geometry("400x300")        # Set size: width x height (크기 설정 - 가로x세로)

# Run window (this line is necessary for the window to appear!)
# 윈도우 실행 (이 줄이 있어야 창이 뜸!)
window.mainloop()
```

**When you run it:**

- A window of 400 pixels wide and 300 pixels tall appears (가로 400픽셀, 세로 300픽셀 크기의 윈도우가 나타남)
- "My First Program" is displayed in the title bar (제목 표시줄에 "My First Program"이 표시됨)

### Code Explanation

```python
import tkinter as tk          # Import tkinter with short name tk
                              # tkinter를 tk라는 짧은 이름으로

window = tk.Tk()              # Create window (윈도우 생성)
window.title("Title")         # Set window title (윈도우 제목)
window.geometry("width x height")  # Set window size (윈도우 크기)

window.mainloop()             # Run window (always last!) (항상 마지막!)
```

**Key Methods :**

- `tk.Tk()`: Creates a new window (새로운 윈도우 생성)
- `window.title()`: Sets the title bar text (제목 표시줄 설정)
- `window.geometry()`: Sets window size (윈도우 크기 설정)
- `window.mainloop()`: Runs the window event loop (윈도우 실행)

💡 **Important**: `mainloop()` must always be **at the end** of the code!

---

## 3️⃣ Label - Displaying Text 

To display text in a window, use Label.

윈도우에 글자를 표시하려면 Label을 사용합니다.

### Basic Label

```python
import tkinter as tk

window = tk.Tk()
window.title("Label Example")
window.geometry("400x300")

# Create Label (Label 생성)
label = tk.Label(window, text="Hello!")
label.pack()  # Place on screen (화면에 배치)

window.mainloop()
```

### Decorating Label 

```python
import tkinter as tk

window = tk.Tk()
window.title("Pretty Label")
window.geometry("400x300")

# Various options (다양한 옵션)
label1 = tk.Label(
    window,
    text="Large text",
    font=("Arial", 20),           # Font, size (폰트, 크기)
    fg="blue",                    # Text color (foreground) (글자 색)
    bg="yellow"                   # Background color (배경 색)
)
label1.pack()

label2 = tk.Label(
    window,
    text="Bold text",
    font=("Arial", 15, "bold")    # bold = bold (굵게)
)
label2.pack()

window.mainloop()
```

**Key Options :**

- `text`: Text to display (표시할 글자)
- `font`: Font (font name, size, style) (글꼴 - 이름, 크기, 스타일)
- `fg`: Text color (foreground) (글자 색)
- `bg`: Background color (배경 색)
- `width`, `height`: Size (크기)
- `padx`, `pady`: Padding (여백)

### Practical Example: Welcome Window 

```python
import tkinter as tk

window = tk.Tk()
window.title("Welcome")
window.geometry("500x300")
window.config(bg="lightblue")  # Window background (윈도우 배경)

# Title (제목)
title = tk.Label(
    window,
    text="Welcome to GUI!",
    font=("Arial", 24, "bold"),
    bg="lightblue",
    fg="darkblue"
)
title.pack(pady=20)

# Subtitle (부제목)
subtitle = tk.Label(
    window,
    text="This is your first GUI program",
    font=("Arial", 14),
    bg="lightblue"
)
subtitle.pack(pady=10)

window.mainloop()
```

---

## 4️⃣ Button - Creating Buttons

When you click a button, you can make a function run!

버튼을 클릭하면 함수가 실행되게 만들 수 있습니다!

### Basic Button

```python
import tkinter as tk

def button_click():
    """Function executed when button is clicked (버튼 클릭시 실행될 함수)"""
    print("Button was clicked!")

window = tk.Tk()
window.title("Button Example")
window.geometry("400x300")

# Create Button (버튼 생성)
button = tk.Button(
    window,
    text="Click me",
    command=button_click  # Function to execute on click (클릭시 실행할 함수)
)
button.pack()

window.mainloop()
```

When you click the button, "Button was clicked!" is printed in the terminal.

버튼을 클릭하면 터미널에 "Button was clicked!"가 출력됩니다.

### Using with Label 

```python
import tkinter as tk

def change_text():
    """Change Label content when button is clicked (버튼 클릭시 Label 내용 변경)"""
    label.config(text="You clicked the button!")

window = tk.Tk()
window.title("Interaction Example")
window.geometry("400x300")

# Create Label (Label 생성)
label = tk.Label(window, text="Hello", font=("Arial", 15))
label.pack(pady=20)  # pady = top/bottom margin (위아래 여백)

# Create Button (Button 생성)
button = tk.Button(
    window,
    text="Click",
    command=change_text,
    font=("Arial", 12),
    bg="lightblue"
)
button.pack()

window.mainloop()
```

**Button Options (Button 옵션):**

- `text`: Text to display (표시할 글자)
- `command`: Function to execute on click (클릭시 실행할 함수)
- `font`: Font (폰트)
- `bg`: Background color (배경 색)
- `fg`: Text color (글자 색)
- `width`, `height`: Size (크기)
- `padx`, `pady`: Padding (여백)

### Important Concept: command Parameter (중요: command 파라미터)

```python
# ✅ Correct (정확한 방법)
def my_function():
    print("Clicked!")

button = tk.Button(window, text="Click", command=my_function)

# ❌ Wrong (틀린 방법 - don't add () 괄호를 붙이면 안됨)
button = tk.Button(window, text="Click", command=my_function())
```

Note: Don't use `()` after the function name! It will execute immediately.

주의: 함수 이름 뒤에 `()`를 붙이면 안 됩니다! 즉시 실행됩니다.

---

## 5️⃣ Entry - Accepting Input (Entry - 입력 받기)

The Entry widget is used to receive input from users.

Entry는 사용자로부터 입력을 받을 때 사용하는 위젯입니다.

### Basic Entry (기본 Entry)

```python
import tkinter as tk

window = tk.Tk()
window.title("Entry Example")
window.geometry("400x300")

# Create Entry (Entry 생성)
label = tk.Label(window, text="Your name:")
label.pack(pady=10)

entry = tk.Entry(window, width=30)
entry.pack(pady=10)

window.mainloop()
```

### Getting Input Values (입력값 가져오기)

```python
import tkinter as tk

def show_input():
    """Get input from Entry and display (Entry에서 입력값 가져오기)"""
    value = entry.get()  # Get input value (입력값 가져오기)
    label.config(text=f"You entered: {value}")

window = tk.Tk()
window.title("Input Display")
window.geometry("400x300")

entry = tk.Entry(window, width=30)
entry.pack(pady=10)

button = tk.Button(window, text="Submit", command=show_input)
button.pack()

label = tk.Label(window, text="")
label.pack(pady=10)

window.mainloop()
```

**Entry Methods (Entry 메서드):**

- `get()`: Get the text from Entry (Entry의 텍스트 가져오기)
- `delete(start, end)`: Delete text (텍스트 삭제)
- `insert(index, text)`: Insert text (텍스트 삽입)
- `config()`: Change options (옵션 변경)

---

## 6️⃣ pack() - Layout Arrangement (pack() - 레이아웃 배치)

A method to place widgets on the screen.

위젯을 화면에 배치하는 방법입니다.

### Basic pack() (pack() 기본)

```python
import tkinter as tk

window = tk.Tk()
window.title("pack Example")
window.geometry("400x300")

# Arrange from top to bottom in order (위에서 아래로 차례대로 배치)
tk.Label(window, text="First", bg="red").pack()
tk.Label(window, text="Second", bg="green").pack()
tk.Label(window, text="Third", bg="blue").pack()

window.mainloop()
```

### pack() Options (pack() 옵션)

```python
import tkinter as tk

window = tk.Tk()
window.title("pack Options")
window.geometry("400x300")

# side: Placement direction (배치 방향)
tk.Label(window, text="Left", bg="red").pack(side="left")
tk.Label(window, text="Right", bg="green").pack(side="right")

# pady, padx: Spacing (여백)
tk.Label(window, text="With spacing", bg="yellow").pack(pady=20, padx=20)

# fill: Fill direction (채우기)
tk.Label(window, text="Fill horizontally", bg="lightblue").pack(fill="x")

window.mainloop()
```

**Key pack() Options (pack() 주요 옵션):**

- `side`: "top"(top), "bottom"(bottom), "left"(left), "right"(right)
  (위, 아래, 왼쪽, 오른쪽)
- `pady`: Top/bottom spacing (위아래 여백)
- `padx`: Left/right spacing (좌우 여백)
- `fill`: "x"(fill horizontally), "y"(fill vertically), "both"(fill both)
  (가로 채움, 세로 채움, 양쪽 채움)
- `expand`: True/False (expand to fill space)
  (남은 공간 채우기)

### Practical Example: Widget Arrangement (실전 예제: 위젯 배치)

```python
import tkinter as tk

window = tk.Tk()
window.title("Widget Arrangement")
window.geometry("500x400")
window.config(bg="lightgray")

# Top section (상단)
header = tk.Label(
    window,
    text="Header",
    bg="darkblue",
    fg="white",
    font=("Arial", 14, "bold")
)
header.pack(fill="x", padx=0, pady=0)

# Middle section (중간)
middle = tk.Frame(window, bg="lightgray")
middle.pack(fill="both", expand=True, padx=10, pady=10)

left = tk.Label(middle, text="Left", bg="red", width=20, height=10)
left.pack(side="left", padx=5, pady=5)

right = tk.Label(middle, text="Right", bg="green", width=20, height=10)
right.pack(side="right", padx=5, pady=5)

# Bottom section (하단)
footer = tk.Button(
    window,
    text="Close",
    bg="orange",
    fg="white",
    font=("Arial", 12)
)
footer.pack(fill="x", padx=10, pady=10)

window.mainloop()
```

---

## 7️⃣ Practical Example: Simple Calculator (실전 예제: 간단한 계산기)

Let's create a calculator using what we've learned so far!

지금까지 배운 것으로 계산기를 만들어봅시다!

```python
import tkinter as tk

def calculate():
    """Execute calculation (계산 실행)"""
    try:
        num1 = float(entry1.get())
        num2 = float(entry2.get())
        result = num1 + num2
        result_label.config(text=f"Result: {result}", fg="blue")
    except ValueError:
        result_label.config(text="Enter numbers!", fg="red")

def clear():
    """Clear input (입력 지우기)"""
    entry1.delete(0, tk.END)
    entry2.delete(0, tk.END)
    result_label.config(text="")

# Create window (윈도우 생성)
window = tk.Tk()
window.title("🔢 Simple Calculator")
window.geometry("400x300")
window.config(bg="lightgray")

# Title (제목)
title = tk.Label(
    window,
    text="Addition Calculator",
    font=("Arial", 20, "bold"),
    bg="lightgray"
)
title.pack(pady=20)

# First number (첫 번째 숫자)
label1 = tk.Label(window, text="First number:", bg="lightgray")
label1.pack()
entry1 = tk.Entry(window, width=20, font=("Arial", 12))
entry1.pack(pady=5)

# Second number (두 번째 숫자)
label2 = tk.Label(window, text="Second number:", bg="lightgray")
label2.pack()
entry2 = tk.Entry(window, width=20, font=("Arial", 12))
entry2.pack(pady=5)

# Buttons (버튼들)
button_frame = tk.Frame(window, bg="lightgray")
button_frame.pack(pady=15)

calc_button = tk.Button(
    button_frame,
    text="Calculate",
    command=calculate,
    width=10,
    bg="lightgreen"
)
calc_button.pack(side="left", padx=5)

clear_button = tk.Button(
    button_frame,
    text="Clear",
    command=clear,
    width=10,
    bg="lightcoral"
)
clear_button.pack(side="left", padx=5)

# Display result (결과 표시)
result_label = tk.Label(
    window,
    text="",
    font=("Arial", 15, "bold"),
    bg="lightgray"
)
result_label.pack(pady=10)

window.mainloop()
```

---

## 8️⃣ grid() - Table-like Arrangement (grid() - 표 형태 배치)

Using `grid()`, you can arrange widgets like a table.

`grid()`를 사용하면 위젯을 표처럼 배치할 수 있습니다.

### Basic grid (기본 grid)

```python
import tkinter as tk

window = tk.Tk()
window.title("grid Example")
window.geometry("300x200")

# row=row, column=column (행=row, 열=column)
tk.Label(window, text="Name:").grid(row=0, column=0, sticky="e", padx=5, pady=5)
tk.Entry(window).grid(row=0, column=1, padx=5, pady=5)  # User input (사용자 입력)

tk.Label(window, text="Age:").grid(row=1, column=0, sticky="e", padx=5, pady=5)
tk.Entry(window).grid(row=1, column=1, padx=5, pady=5)

tk.Label(window, text="Email:").grid(row=2, column=0, sticky="e", padx=5, pady=5)
tk.Entry(window).grid(row=2, column=1, padx=5, pady=5)

tk.Button(window, text="OK").grid(row=3, column=0, columnspan=2, pady=10)

window.mainloop()
```

**Key grid() Options (grid() 주요 옵션):**

- `row`: Row number (starts from 0) (행 번호 - 0부터 시작)
- `column`: Column number (starts from 0) (열 번호 - 0부터 시작)
- `sticky`: Alignment ("n"north, "s"south, "e"east, "w"west) (정렬 - 북, 남, 동, 서)
- `columnspan`: Span multiple columns (여러 열 차지)
- `rowspan`: Span multiple rows (여러 행 차지)

---

## 9️⃣ Practical Example: Login Screen (실전 예제: 로그인 화면)

A clean login screen using grid().

grid를 활용한 깔끔한 로그인 화면입니다.

```python
import tkinter as tk
from tkinter import messagebox

def login():
    """Handle login (로그인 처리)"""
    username = username_entry.get()
    password = password_entry.get()
  
    if username == "admin" and password == "1234":
        messagebox.showinfo("Success", f"Welcome, {username}!")
    else:
        messagebox.showerror("Error", "Username or password is incorrect!")

# Create window (윈도우 생성)
window = tk.Tk()
window.title("🔐 Login")
window.geometry("350x200")
window.config(bg="white")

# Title (제목)
title = tk.Label(
    window,
    text="Login",
    font=("Arial", 18, "bold"),
    bg="white"
)
title.grid(row=0, column=0, columnspan=2, pady=20)

# Username (아이디)
tk.Label(window, text="Username:", bg="white", font=("Arial", 11)).grid(
    row=1, column=0, sticky="e", padx=10, pady=10
)
username_entry = tk.Entry(window, width=20, font=("Arial", 11))
username_entry.grid(row=1, column=1, pady=10)

# Password (비밀번호)
tk.Label(window, text="Password:", bg="white", font=("Arial", 11)).grid(
    row=2, column=0, sticky="e", padx=10, pady=10
)
password_entry = tk.Entry(window, width=20, show="*", font=("Arial", 11))
password_entry.grid(row=2, column=1, pady=10)

# Login button (로그인 버튼)
login_button = tk.Button(
    window,
    text="Login",
    command=login,
    width=15,
    bg="lightblue",
    font=("Arial", 11)
)
login_button.grid(row=3, column=0, columnspan=2, pady=20)

window.mainloop()
```

---

## 📝 Key Concepts Summary (핵심 개념 정리)

### Basic Structure (기본 구조)

```python
import tkinter as tk

window = tk.Tk()           # Create window (윈도우 생성)
window.title("Title")
window.geometry("width x height")

# Add widgets (위젯 추가)

window.mainloop()          # Run (always last!) (실행 - 마지막!)
```

### Main Widgets (주요 위젯)

- `Label`: Display text (텍스트 표시)
- `Button`: Button (connect function with command) (버튼 - command로 함수 연결)
- `Entry`: Single-line input (한 줄 입력)
- `Listbox`: List (목록)
- `Text`: Multi-line text (여러 줄 텍스트)

### Layout (레이아웃)

- `pack()`: Arrange in order (순서대로 배치)
- `grid()`: Arrange in table format (표 형태로 배치)
- `place()`: Place at specific coordinates (특정 위치에 배치)

### Event Handling (이벤트 처리)

```python
def my_function():
    # Code to execute (실행할 코드)
    pass

button = tk.Button(window, text="Click", command=my_function)
```

### Common Widget Options (주요 위젯 옵션)

- `text`: Text to display (표시할 텍스트)
- `font`: Font (font name, size, style) (폰트)
- `fg`: Text color (글자 색)
- `bg`: Background color (배경 색)
- `width`, `height`: Size (크기)
- `command`: Function to execute on click (클릭시 실행 함수)

---

## 💡 Practice Assignments (실습 과제)

### Assignment 1: Greeting Program (과제 1: 인사 프로그램)

Create a program that:

1. Takes a name as input
2. Displays "Hello, [name]!" when button is clicked

프로그램을 만드세요:

1. 이름을 입력받음
2. 버튼 클릭 → "Hello, [name]!" 표시

```python
# Hint (힌트)
# Entry for name input → Button click → Display "Hello, OOO!"
# 이름 입력 → 버튼 클릭 → "안녕하세요, OOO님!" 표시
```

### Assignment 2: Simple Notepad (과제 2: 간단한 메모장)

Create a simple notepad:

1. Text widget for writing
2. Save button → save to file
3. Load button → read from file

간단한 메모장을 만드세요:

1. Text 위젯으로 작성
2. 저장 버튼 → 파일로 저장
3. 불러오기 버튼 → 파일에서 읽기

```python
# Hint (힌트)
# Use Text widget for multi-line input
# Text 위젯 사용
```

---

## ✅ Quiz (퀴즈)

### [Beginner] Question 1

How do you import tkinter?

tkinter를 import하는 방법은?

```
1. import tk
2. import tkinter
3. import gui
4. import window
```

### [Intermediate] Question 2

What method runs the window?

윈도우를 실행하는 메서드는?

```
1. run()
2. start()
3. mainloop()
4. execute()
```

### [Intermediate] Question 3

What option connects a function to a button click?

버튼 클릭 시 함수를 연결하는 옵션은?

```
1. onclick
2. command
3. function
4. event
```

### [Advanced] Question 4

What method gets the input from Entry?

Entry에서 입력값을 가져오는 메서드는?

```
1. value()
2. text()
3. get()
4. read()
```

### [Advanced] Question 5

What method arranges widgets in table format?

위젯을 표 형태로 배치하는 메서드는?

```
1. pack()
2. grid()
3. place()
4. table()
```

---

## 🔑 Quiz Answers and Explanations (퀴즈 정답 및 해설)

**Answer 1: 2**

Use `import tkinter` or `import tkinter as tk`.

`import tkinter` 또는 `import tkinter as tk`로 사용합니다.

**Answer 2: 3**

The `mainloop()` method runs the window.

`mainloop()` 메서드로 윈도우를 실행합니다.

**Answer 3: 2**

Use the `command` option to specify the function to execute on click.

`command` 옵션으로 클릭 시 실행할 함수를 지정합니다.

**Answer 4: 3**

Use the `get()` method to retrieve the input from Entry.

`get()` 메서드로 Entry의 입력값을 가져옵니다.

**Answer 5: 2**

Use the `grid()` method to arrange in table format (row, column).

`grid()` 메서드로 표 형태(행, 열)로 배치합니다.

---

## 🎯 Next Chapter Preview (다음 장 예고)

In the next chapter, you'll learn advanced GUI programming features. You'll study more diverse widgets such as checkboxes, radio buttons, menu bars, and advanced event handling methods to create high-quality GUI programs!

다음 장에서는 GUI 프로그래밍의 고급 기능을 배웁니다. 체크박스, 라디오 버튼, 메뉴 바 등 더 다양한 위젯과 이벤트 처리 방법을 학습하여 완성도 높은 GUI 프로그램을 만들 수 있게 됩니다!

---

Thank you for your attention.  
Cho Jeonghyun ([peterchokr@gmail.com](mailto:peterchokr@gmail.com)). Yeungnam University College

"Produced in collaboration with Claude and Gemini."
