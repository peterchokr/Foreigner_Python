# Chapter 21. GUI Programming 2 (Advanced)

---

## 📚 Learning Objectives

After completing this chapter, you will be able to utilize tkinter's advanced widgets. You can create highly polished GUI applications using checkboxes, radio buttons, scrollbars, message boxes, and more.

이번 장을 마치면 여러분은 tkinter의 고급 위젯들을 활용할 수 있습니다. 체크박스, 라디오 버튼, 스크롤바, 메시지 박스 등을 사용하여 더욱 완성도 높은 GUI 애플리케이션을 제작할 수 있습니다.

---

## 1️⃣ Checkbutton - Checkbox (Checkbutton - 체크박스)

A checkbox that allows you to select multiple items at the same time.

여러 개를 동시에 선택할 수 있는 체크박스입니다.

### Why Use Checkbox? (왜 체크박스를 사용할까?)

Use it when you need to select multiple items at once, like in surveys or option selection.

설문조사나 옵션 선택처럼 **여러 개를 동시에 선택**할 때 사용합니다.

```
Example: Select your favorite fruits (multiple selection possible)
예시: 좋아하는 과일 선택 (여러 개 가능)
☑ Apple (사과)
☐ Banana (바나나)
☑ Strawberry (딸기)
```

### Basic Checkbox (기본 체크박스)

```python
import tkinter as tk

def show_choice():
    """Display selected items (선택한 항목 표시)"""
    choices = []
    if var1.get():
        choices.append("Apple")
    if var2.get():
        choices.append("Banana")
    if var3.get():
        choices.append("Strawberry")
  
    if choices:
        result_label.config(text=f"Selected: {', '.join(choices)}")
    else:
        result_label.config(text="No selection")

# Create window (윈도우 생성)
window = tk.Tk()
window.title("Checkbox Example")
window.geometry("300x250")

# Title (제목)
tk.Label(window, text="Select your favorite fruits", font=("Arial", 12, "bold")).pack(pady=10)

# Checkbox variables (save selection status) (체크박스 변수 - 선택 여부 저장)
var1 = tk.IntVar()
var2 = tk.IntVar()
var3 = tk.IntVar()

# Create checkboxes (체크박스 생성)
tk.Checkbutton(window, text="Apple", variable=var1, font=("Arial", 11)).pack(anchor="w", padx=50)
tk.Checkbutton(window, text="Banana", variable=var2, font=("Arial", 11)).pack(anchor="w", padx=50)
tk.Checkbutton(window, text="Strawberry", variable=var3, font=("Arial", 11)).pack(anchor="w", padx=50)

# Confirm button (확인 버튼)
tk.Button(window, text="Confirm", command=show_choice, bg="lightblue").pack(pady=10)

# Display result (결과 표시)
result_label = tk.Label(window, text="", font=("Arial", 11), fg="blue")
result_label.pack(pady=10)

window.mainloop()
```

**Key Points (핵심 포인트):**

- `IntVar()`: Variable that stores checkbox status (0=unchecked, 1=checked)
  (체크 상태를 저장하는 변수 - 0=해제, 1=선택)
- `variable`: Connects checkbox to variable (체크박스와 변수 연결)
- `get()`: Check selection status (True/False or 1/0) (선택 여부 확인)

---

## 2️⃣ Radiobutton - Radio Button (Radiobutton - 라디오 버튼)

A button that allows you to select only one from multiple options.

여러 개 중 **하나만** 선택할 수 있는 버튼입니다.

### Why Use Radio Button? (왜 라디오 버튼을 사용할까?)

Use it when you need to select only one option, like gender or grade.

성별, 학년처럼 **하나만 선택**해야 할 때 사용합니다.

```
Example: Select gender (only one possible)
예시: 성별 선택 (하나만 가능)
◉ Male (남자)
◯ Female (여자)
```

### Basic Radio Button (기본 라디오 버튼)

```python
import tkinter as tk

def show_choice():
    """Display selected item (선택한 항목 표시)"""
    choice = var.get()
    result_label.config(text=f"Selected: {choice}")

# Create window (윈도우 생성)
window = tk.Tk()
window.title("Radio Button Example")
window.geometry("300x250")

# Title (제목)
tk.Label(window, text="Select your favorite color", font=("Arial", 12, "bold")).pack(pady=10)

# Radio button variable (share one variable!) (라디오 버튼 변수 - 하나의 변수를 공유!)
var = tk.StringVar()
var.set("Red")  # Default selection (기본 선택)

# Create radio buttons (same variable) (라디오 버튼 생성 - 같은 variable 사용)
tk.Radiobutton(window, text="Red", variable=var, value="Red", font=("Arial", 11)).pack(anchor="w", padx=50)
tk.Radiobutton(window, text="Blue", variable=var, value="Blue", font=("Arial", 11)).pack(anchor="w", padx=50)
tk.Radiobutton(window, text="Green", variable=var, value="Green", font=("Arial", 11)).pack(anchor="w", padx=50)

# Confirm button (확인 버튼)
tk.Button(window, text="Confirm", command=show_choice, bg="lightgreen").pack(pady=10)

# Display result (결과 표시)
result_label = tk.Label(window, text="Selected: Red", font=("Arial", 11), fg="blue")
result_label.pack(pady=10)

window.mainloop()
```

**Key Points (핵심 포인트):**

- All radio buttons share the **same variable** (모든 라디오 버튼이 **같은 variable** 공유)
- `value`: Value of each button (각 버튼의 값)
- `set()`: Set default selection (기본 선택 설정)

### Checkbox vs Radio Button (체크박스 vs 라디오 버튼)

```
Checkbutton (multiple selection)    Radiobutton (single selection only)
☑ Apple (사과)                      ◉ Red (빨강)
☑ Banana (바나나)                   ◯ Blue (파랑)
☐ Strawberry (딸기)                 ◯ Green (초록)

Each has different variable         Share one variable
각자 다른 변수                       같은 변수 공유
var1, var2, var3                    var
```

---

## 3️⃣ Text - Multi-line Input (Text - 여러 줄 입력)

Entry can only input one line, but Text can input **multiple lines**.

Entry는 한 줄만 입력할 수 있지만, Text는 **여러 줄** 입력이 가능합니다.

### Basic Text Widget (기본 Text 위젯)

```python
import tkinter as tk

def show_text():
    """Display entered content (입력된 내용 표시)"""
    content = text.get("1.0", tk.END)  # Get all content (전체 내용 가져오기)
    print(content)

def clear_text():
    """Clear content (내용 지우기)"""
    text.delete("1.0", tk.END)

# Create window (윈도우 생성)
window = tk.Tk()
window.title("Notepad")
window.geometry("400x300")

# Title (제목)
tk.Label(window, text="Notepad", font=("Arial", 14, "bold")).pack(pady=10)

# Text widget (Text 위젯)
text = tk.Text(window, width=40, height=10, font=("Arial", 11))
text.pack(pady=10)

# Button frame (버튼 프레임)
button_frame = tk.Frame(window)
button_frame.pack()

tk.Button(button_frame, text="Print", command=show_text, width=10).pack(side="left", padx=5)
tk.Button(button_frame, text="Clear", command=clear_text, width=10).pack(side="left", padx=5)

window.mainloop()
```

**Key Text Methods (Text 주요 메서드):**

- `get("1.0", tk.END)`: Get all content (전체 내용 가져오기)
- `delete("1.0", tk.END)`: Delete all content (전체 내용 삭제)
- `insert("1.0", "text")`: Insert text at beginning (맨 앞에 텍스트 삽입)
- `insert(tk.END, "text")`: Append text at end (끝에 텍스트 추가)

💡 **Meaning of "1.0"**: Line 1, Character 0 (first position)

💡 **"1.0"의 의미**: 1번째 줄, 0번째 문자 (첫 위치)

### Practical Example: Simple Text Editor (실전 예제: 간단한 텍스트 편집기)

```python
import tkinter as tk

def clear_all():
    """Clear all text (모든 텍스트 지우기)"""
    text.delete("1.0", tk.END)

def copy_to_label():
    """Copy to label (라벨에 복사)"""
    content = text.get("1.0", tk.END)
    info_label.config(text=f"Characters: {len(content)}")

window = tk.Tk()
window.title("Text Editor")
window.geometry("400x350")

# Title (제목)
tk.Label(window, text="Text Editor", font=("Arial", 14, "bold")).pack(pady=10)

# Text widget (Text 위젯)
text = tk.Text(window, width=40, height=12, font=("Arial", 11))
text.pack(pady=10)

# Info label (정보 라벨)
info_label = tk.Label(window, text="Characters: 0", font=("Arial", 10))
info_label.pack()

# Buttons (버튼들)
button_frame = tk.Frame(window)
button_frame.pack(pady=10)

tk.Button(button_frame, text="Count", command=copy_to_label, width=10, bg="lightblue").pack(side="left", padx=5)
tk.Button(button_frame, text="Clear", command=clear_all, width=10, bg="lightcoral").pack(side="left", padx=5)

window.mainloop()
```

---

## 4️⃣ Scrollbar - Scrollbar (Scrollbar - 스크롤바)

Allows scrolling when there is a lot of content.

내용이 많을 때 스크롤할 수 있게 만듭니다.

### Connecting Text and Scrollbar (Text와 Scrollbar 연결)

```python
import tkinter as tk

window = tk.Tk()
window.title("Scrollbar Example")
window.geometry("400x300")

# Create Frame (Frame 생성)
frame = tk.Frame(window)
frame.pack(pady=10)

# Create Scrollbar (Scrollbar 생성)
scrollbar = tk.Scrollbar(frame)
scrollbar.pack(side="right", fill="y")

# Create Text (connected to Scrollbar) (Text 생성 - Scrollbar와 연결)
text = tk.Text(frame, width=40, height=15, yscrollcommand=scrollbar.set)
text.pack(side="left")

# Connect Scrollbar and Text (Scrollbar와 Text 연결)
scrollbar.config(command=text.yview)

# Add sample text (샘플 텍스트 추가)
for i in range(1, 51):
    text.insert(tk.END, f"Line {i}\n")

window.mainloop()
```

**Connection Method (연결 방법):**

1. When creating Text: `yscrollcommand=scrollbar.set` (Text 생성 시)
2. Configure Scrollbar: `scrollbar.config(command=text.yview)` (Scrollbar 설정)

**Parameters (파라미터):**

- `yscrollcommand`: Bind vertical scrollbar (수직 스크롤바 연결)
- `xscrollcommand`: Bind horizontal scrollbar (수평 스크롤바 연결)
- `fill="y"`: Fill vertical direction (수직 방향 채우기)
- `fill="x"`: Fill horizontal direction (수평 방향 채우기)

---

## 5️⃣ messagebox - Message Box (messagebox - 메시지 박스)

Display notifications, confirmations, and error messages to the user.

사용자에게 알림, 확인, 오류 메시지를 보여줍니다.

### Key Message Boxes (주요 메시지 박스)

```python
import tkinter as tk
from tkinter import messagebox

def show_info():
    """Show information message (정보 메시지)"""
    messagebox.showinfo("Notification", "Saved successfully!")

def show_warning():
    """Show warning message (경고 메시지)"""
    messagebox.showwarning("Warning", "Please be careful!")

def show_error():
    """Show error message (오류 메시지)"""
    messagebox.showerror("Error", "File not found!")

def ask_question():
    """Ask Yes/No question (질문 - 예/아니오)"""
    result = messagebox.askyesno("Confirm", "Are you sure you want to delete?")
    if result:
        messagebox.showinfo("Result", "Deleted")
    else:
        messagebox.showinfo("Result", "Cancelled")

def ask_okcancel():
    """Ask OK/Cancel (확인/취소)"""
    result = messagebox.askokcancel("Confirm", "Do you want to continue?")
    print(f"Result: {result}")

# Create window (윈도우 생성)
window = tk.Tk()
window.title("Message Box Example")
window.geometry("300x300")

tk.Label(window, text="Message Box Test", font=("Arial", 14, "bold")).pack(pady=20)

tk.Button(window, text="Info", command=show_info, width=15, bg="lightblue").pack(pady=5)
tk.Button(window, text="Warning", command=show_warning, width=15, bg="yellow").pack(pady=5)
tk.Button(window, text="Error", command=show_error, width=15, bg="lightcoral").pack(pady=5)
tk.Button(window, text="Yes/No", command=ask_question, width=15, bg="lightgreen").pack(pady=5)
tk.Button(window, text="OK/Cancel", command=ask_okcancel, width=15, bg="lightgray").pack(pady=5)

window.mainloop()
```

**Key messagebox Functions (주요 messagebox):**

- `showinfo()`: Information message (ℹ️) (정보)
- `showwarning()`: Warning message (⚠️) (경고)
- `showerror()`: Error message (❌) (오류)
- `askyesno()`: Yes/No question (returns True/False) (예/아니오 질문)
- `askokcancel()`: OK/Cancel (returns True/False) (확인/취소)
- `askretrycancel()`: Retry/Cancel (다시/취소)

---

## 6️⃣ Scale - Slider (Scale - 슬라이더)

A slider that allows you to select a value by dragging with the mouse.

마우스로 드래그하여 값을 선택하는 슬라이더입니다.

### Basic Scale (기본 Scale)

```python
import tkinter as tk

def show_value(value):
    """Display slider value (슬라이더 값 표시)"""
    label.config(text=f"Current value: {value}")

window = tk.Tk()
window.title("Slider Example")
window.geometry("400x200")

tk.Label(window, text="Volume Control", font=("Arial", 14, "bold")).pack(pady=20)

# Create Scale (Scale 생성)
scale = tk.Scale(
    window,
    from_=0,          # Minimum value (최솟값)
    to=100,           # Maximum value (최댓값)
    orient="horizontal",  # Horizontal direction (가로 방향)
    length=300,       # Length (길이)
    command=show_value  # Function to call on value change (값 변경시 호출할 함수)
)
scale.set(50)  # Set initial value (초기값)
scale.pack(pady=10)

# Display result (결과 표시)
label = tk.Label(window, text="Current value: 50", font=("Arial", 12))
label.pack(pady=10)

window.mainloop()
```

**Key Scale Options (Scale 주요 옵션):**

- `from_`: Minimum value (최솟값)
- `to`: Maximum value (최댓값)
- `orient`: "horizontal"(horizontal) or "vertical"(vertical) (가로 또는 세로)
- `command`: Function to call on value change (값 변경시 호출할 함수)
- `length`: Length of slider (슬라이더 길이)
- `label`: Display label (라벨 표시)
- `resolution`: Step value (단계 값)

---

## 7️⃣ Practical Example: Simple Calculator (Final) (실전 예제: 간단한 계산기 - 완성판)

A calculator using various widgets.

다양한 위젯을 활용한 계산기입니다.

```python
import tkinter as tk
from tkinter import messagebox

class Calculator:
    def __init__(self, window):
        self.window = window
        self.window.title("🔢 Calculator")
        self.window.geometry("350x450")
        self.window.config(bg="lightgray")
  
        self.result_var = tk.StringVar()  # Result variable (결과 변수)
        self.result_var.set("0")
  
        self.create_widgets()
  
    def create_widgets(self):
        """Create widgets (위젯 생성)"""
        # Display result (결과 표시)
        result_label = tk.Label(
            self.window,
            textvariable=self.result_var,
            font=("Arial", 24, "bold"),
            bg="white",
            anchor="e",
            padx=10,
            pady=20
        )
        result_label.pack(fill="x", padx=10, pady=10)
  
        # Button frame (버튼 프레임)
        button_frame = tk.Frame(self.window, bg="lightgray")
        button_frame.pack()
  
        # Button list (버튼 목록)
        buttons = [
            ['7', '8', '9', '/'],
            ['4', '5', '6', '*'],
            ['1', '2', '3', '-'],
            ['C', '0', '=', '+']
        ]
  
        # Create buttons (버튼 생성)
        for row_idx, row in enumerate(buttons):
            for col_idx, btn_text in enumerate(row):
                button = tk.Button(
                    button_frame,
                    text=btn_text,
                    width=6,
                    height=2,
                    font=("Arial", 14, "bold"),
                    command=lambda x=btn_text: self.on_button_click(x)
                )
          
                # Set color (색상 지정)
                if btn_text == '=':  # Equals - Calculate (계산)
                    button.config(bg="lightblue")
                elif btn_text == 'C':  # Clear (지우기)
                    button.config(bg="lightcoral")
                elif btn_text in ['+', '-', '*', '/']:  # Operators (연산자)
                    button.config(bg="lightyellow")
                else:
                    button.config(bg="white")
          
                button.grid(row=row_idx, column=col_idx, padx=2, pady=2)
  
    def on_button_click(self, btn_text):
        """Handle button click (버튼 클릭 처리)"""
        current = self.result_var.get()
  
        if btn_text == 'C':  # Clear (지우기)
            self.result_var.set("0")
  
        elif btn_text == '=':  # Calculate (계산)
            try:
                result = eval(current)
                self.result_var.set(str(result))
            except:
                messagebox.showerror("Error", "Invalid expression!")
                self.result_var.set("0")
  
        else:  # Add number or operator (숫자나 연산자 추가)
            if current == "0":
                self.result_var.set(btn_text)
            else:
                self.result_var.set(current + btn_text)

# Create window and run calculator (윈도우 생성 및 실행)
window = tk.Tk()
calculator = Calculator(window)
window.mainloop()
```

---

## 8️⃣ Menu - Menu Bar (Menu - 메뉴 바)

You can add a menu at the top of the program.

프로그램 상단에 메뉴를 추가할 수 있습니다.

### Basic Menu (기본 메뉴)

```python
import tkinter as tk
from tkinter import messagebox

def new_file():
    """Create new file (새 파일 생성)"""
    messagebox.showinfo("New File", "Create new file")

def open_file():
    """Open file (파일 열기)"""
    messagebox.showinfo("Open", "Open file")

def save_file():
    """Save file (파일 저장)"""
    messagebox.showinfo("Save", "Save file")

def exit_program():
    """Exit program (프로그램 종료)"""
    if messagebox.askyesno("Exit", "Are you sure?"):
        window.destroy()

def about():
    """Show about dialog (정보 표시)"""
    messagebox.showinfo("About", "Simple notepad v1.0")

# Create window (윈도우 생성)
window = tk.Tk()
window.title("Menu Example")
window.geometry("400x300")

# Create menu bar (메뉴 바 생성)
menubar = tk.Menu(window)
window.config(menu=menubar)

# File menu (파일 메뉴)
file_menu = tk.Menu(menubar, tearoff=0)
menubar.add_cascade(label="File", menu=file_menu)
file_menu.add_command(label="New", command=new_file)
file_menu.add_command(label="Open", command=open_file)
file_menu.add_command(label="Save", command=save_file)
file_menu.add_separator()  # Separator (구분선)
file_menu.add_command(label="Exit", command=exit_program)

# Help menu (도움말 메뉴)
help_menu = tk.Menu(menubar, tearoff=0)
menubar.add_cascade(label="Help", menu=help_menu)
help_menu.add_command(label="About", command=about)

window.mainloop()
```

---

## 📝 Key Concepts Summary (핵심 개념 정리)

### Main Widgets (주요 위젯)

- `Checkbutton`: Multiple selection (여러 개 선택)
- `Radiobutton`: Single selection (하나만 선택)
- `Text`: Multi-line input (여러 줄 입력)
- `Scale`: Slider (슬라이더)
- `Scrollbar`: Scrolling (스크롤)
- `Listbox`: List display (목록 표시)

### messagebox (메시지 박스)

```python
from tkinter import messagebox

# Information dialog (정보 대화상자)
messagebox.showinfo("Title", "Message")

# Yes/No question (예/아니오 질문)
messagebox.askyesno("Title", "Question")

# OK/Cancel question (OK/취소 질문)
messagebox.askokcancel("Title", "Question")

# Error message (오류 메시지)
messagebox.showerror("Title", "Error message")
```

### Menu (메뉴)

```python
menubar = tk.Menu(window)
window.config(menu=menubar)

file_menu = tk.Menu(menubar, tearoff=0)
menubar.add_cascade(label="File", menu=file_menu)
file_menu.add_command(label="Open")
```

### Event Handling Summary (이벤트 처리 정리)

- `command`: Execute function on click (클릭시 함수 실행)
- `variable`: Bind to variable (변수와 연결)
- `yscrollcommand`: Bind scrollbar (스크롤바 연결)

---

## 💡 Practice Assignments (실습 과제)

### Assignment 1: BMI Calculator (과제 1: BMI 계산기)

Create a program that:

1. Input height (cm) and weight (kg)
2. Calculate BMI = weight / (height/100)²
3. Display result: underweight / normal / overweight / obese

프로그램을 만드세요:

1. 키(cm), 몸무게(kg) 입력
2. BMI = 몸무게 / (키/100)²
3. 결과: 저체중/정상/과체중/비만

```python
# Hint (힌트)
# Use Entry for height and weight input (키, 몸무게 입력)
# Calculate BMI (BMI 계산)
# Display category (카테고리 표시)
```

### Assignment 2: Color Picker (과제 2: 색상 선택기)

Create a program that:

1. Use 3 Scale widgets (R, G, B)
2. Range 0-255
3. Change Label background with selected color

프로그램을 만드세요:

1. Scale 3개 (R, G, B)
2. 0-255 범위
3. 선택한 색상으로 Label 배경 변경

```python
# Hint (힌트)
# Use 3 Scale for RGB (R, G, B용 Scale 3개)
# Create color code (색상 코드 생성)
# Update background color (배경 색상 업데이트)
```

---

## ✅ Quiz (퀴즈)

### [Beginner] Question 1

What widget allows multiple selections?

여러 개를 선택할 수 있는 위젯은?

```
1. Radiobutton
2. Checkbutton
3. Button
4. Label
```

### [Intermediate] Question 2

What do radio buttons share?

라디오 버튼들이 공유하는 것은?

```
1. command
2. variable
3. window
4. text
```

### [Advanced] Question 3

How do you get all content from a Text widget?

Text 위젯에서 전체 내용을 가져오는 코드는?

```
1. text.get()
2. text.get("1.0", tk.END)
3. text.read()
4. text.content()
```

### [Advanced] Question 4

What messagebox asks Yes/No?

예/아니오를 묻는 messagebox는?

```
1. messagebox.askyesno()
2. messagebox.askquestion()
3. messagebox.showquestion()
4. messagebox.question()
```

### [Advanced] Question 5

How do you add a menu bar to a window?

메뉴 바를 윈도우에 추가하는 코드는?

```
1. window.menubar = menubar
2. window.set_menu(menubar)
3. window.config(menu=menubar)
4. window.add_menu(menubar)
```

---

## 🔑 Quiz Answers (퀴즈 정답)

**Answer 1: 2**

Checkbutton allows multiple selections.

Checkbutton은 여러 개를 선택할 수 있습니다.

**Answer 2: 2**

Radio buttons share the same variable.

라디오 버튼들은 같은 variable을 공유합니다.

**Answer 3: 2**

Use `text.get("1.0", tk.END)` to get all content.

`text.get("1.0", tk.END)`로 전체 내용을 가져옵니다.

**Answer 4: 1**

Use `messagebox.askyesno()` to ask Yes/No.

`messagebox.askyesno()`로 예/아니오를 묻습니다.

**Answer 5: 3**

Use `window.config(menu=menubar)` to add menu bar.

`window.config(menu=menubar)`로 메뉴 바를 추가합니다.

---

## 🎯 Next Chapter Preview (다음 장 예고)

In the next chapter, you'll learn about CSV files and data analysis. You'll learn how to read and write Excel files, process and analyze data!

다음 장에서는 CSV 파일과 데이터 분석을 배웁니다. 엑셀 파일을 읽고 쓰며, 데이터를 처리하고 분석하는 방법을 학습합니다!

---

Thank you for your attention.   
Cho Jeonghyun ([peterchokr@gmail.com](mailto:peterchokr@gmail.com)). Yeungnam University College

"Produced in collaboration with Claude and Gemini."
