# Chapter 21: GUI Programming 2 (Advanced) — Practice Problems

---

## 📝 Multiple Choice Questions

---

### 🟢 Beginner

**Problem 1.** What widget allows selecting multiple items simultaneously?

① `Radiobutton`
② `Checkbutton`
③ `Button`
④ `Entry`

---

**Problem 2.** What widget allows selecting only one option from multiple choices?

① `Checkbutton`
② `Listbox`
③ `Radiobutton`
④ `Scale`

---

**Problem 3.** What variable type stores checkbox selection state?

① `StringVar()`
② `IntVar()`
③ `BoolVar()`
④ `CheckVar()`

---

**Problem 4.** What widget accepts multiple lines of text input?

① `Entry`
② `Label`
③ `Text`
④ `Listbox`

---

**Problem 5.** What function displays an information message in messagebox?

① `messagebox.showinfo()`
② `messagebox.showwarning()`
③ `messagebox.showerror()`
④ `messagebox.showmessage()`

---

**Problem 6.** What option sets Scale (slider) to horizontal direction?

① `orient="horizontal"`
② `orient="vertical"`
③ `direction="horizontal"`
④ `side="horizontal"`

---

**Problem 7.** How to ensure only one radio button can be selected?

① Use different `variable` for each
② **All radio buttons share the same `variable`**
③ Set `single=True` option
④ Use `group` option

---

### 🟡 Intermediate

**Problem 8.** What is the correct code to get all content from Text widget?

① `text.get()`
② `text.get("1.0", tk.END)`
③ `text.get(0, "end")`
④ `text.read()`

---

**Problem 9.** What function in messagebox asks "Yes/No" question?

① `messagebox.askquestion()`
② `messagebox.askyesno()`
③ `messagebox.askconfirm()`
④ `messagebox.askok()`

---

**Problem 10.** What is the return value of `var.get()` when checkbox is unchecked?

```python
var = tk.IntVar()
tk.Checkbutton(window, text="Agree", variable=var)
```

① `False`
② `""`
③ `0`
④ `None`

---

**Problem 11.** What is the correct code to add menubar to window?

① `window.menu = menubar`
② `window.config(menu=menubar)`
③ `window.add(menubar)`
④ `window.setmenu(menubar)`

---

**Problem 12.** What option is needed when creating Text widget with Scrollbar?

① `scroll=scrollbar`
② `yscrollcommand=scrollbar.set`
③ `scrollbar=scrollbar.connect`
④ `yview=scrollbar`

---

### 🔴 Advanced

**Problem 13.** What is the return value of `messagebox.askyesno()`?

```python
result = messagebox.askyesno("Confirm", "Delete?")
```

① Returns `"yes"` if Yes, `"no"` if No
② Returns `1` if Yes, `0` if No
③ **Returns `True` if Yes, `False` if No**
④ Returns `"Y"` if Yes, `"N"` if No

---

**Problem 14.** What is the return value of `var.get()` when radio button is selected?

```python
var = tk.StringVar(value="Red")
tk.Radiobutton(window, text="Red", variable=var, value="Red")
tk.Radiobutton(window, text="Blue", variable=var, value="Blue")
```

① Index of selected button (0 or 1)
② `text` value of selected button
③ **`value` parameter of selected button ("Red" or "Blue")**
④ Boolean (True or False)

---

**Problem 15.** How to open a file dialog to select a file?

```python
from tkinter import filedialog

filename = filedialog.askopenfilename()
```

① Opens save dialog
② **Opens open file dialog**
③ Creates new file
④ Error - must specify filename

---

## 📝 Short Answer Questions

---

### 🟢 Beginner

**Problem 16.** Explain the difference between Checkbutton and Radiobutton.

---

**Problem 17.** What is messagebox and what types of messages can it show?

---

**Problem 18.** How to create and use tk.StringVar() and tk.IntVar()?

---

### 🟡 Intermediate

**Problem 19.** Explain how to create a menu bar with File menu.

```python
menubar = tk.Menu(window)
window.config(menu=menubar)

file_menu = tk.Menu(menubar)
menubar.add_cascade(label="File", menu=file_menu)
file_menu.add_command(label="Exit", command=window.quit)
```

---

**Problem 20.** How to connect a Scrollbar to a Text widget?

---

### 🔴 Advanced

**Problem 21.** Create a complete form with various widgets and explain functionality.

```python
import tkinter as tk
from tkinter import messagebox

def submit_form():
    name = entry_name.get()
    if check_var.get():
        messagebox.showinfo("Success", f"Name: {name}")
    else:
        messagebox.showwarning("Warning", "Check agreement")

window = tk.Tk()
window.title("Form")
window.geometry("400x300")

tk.Label(window, text="Name:").pack()
entry_name = tk.Entry(window)
entry_name.pack()

check_var = tk.BoolVar()
tk.Checkbutton(window, text="I agree", variable=check_var).pack()

tk.Button(window, text="Submit", command=submit_form).pack()

window.mainloop()
```

---

## 💻 Hands-On Problems

---

### 🟢 Beginner

**Problem 22.** Create a window with Checkbutton and Radiobutton widgets.

> Display multiple checkboxes and radio buttons with selection display.

Output example:

```
=== Widget Demo ===
Checkboxes:
☑ Python
☐ Java
☑ JavaScript

Radio Buttons:
○ Easy
● Medium
○ Hard
```

---

**Problem 23.** Create a simple messagebox demo application.

> Show different types of message boxes (info, warning, error, question).

Output example:

```
=== Messagebox Demo ===
[Info Button] → Shows information message
[Warning Button] → Shows warning message
[Error Button] → Shows error message
[Question Button] → Shows yes/no dialog
```

---

### 🟡 Intermediate

**Problem 24.** Create a notepad with Text widget and Scrollbar.

> Text editor with multiple lines and scroll functionality.

Output example:

```
=== Text Editor ===
╔════════════════════╗
║ Line 1: Hello      ║
║ Line 2: World      ║
║ Line 3: Python     ║
║                    ║ ⬆
║                    │  
╚════════════════════╝
[Save] [Clear]
```

---

**Problem 25.** Create a menu bar application with File menu.

> Application with menu bar and menu items.

Output example:

```
┌─ File ─┐
├ Open   │
├ Save   │
├ ─────  │
└ Exit   ┘

[Main Content Area]
```

---

### 🔴 Advanced

**Problem 26.** Create a comprehensive survey form application.

> Multi-widget form with various input types and validation.

Output example:

```
=== Survey Form ===
Name: [____________]
Age: [__]
Gender: ○ Male ● Female
Languages:
☑ Python  ☑ Java  ☐ C++
Experience:
[====●════════] 4 years
Comments:
[Multi-line text area]

[Submit] [Reset]
Result: Form submitted successfully!
```

---

---

# 🔑 Answer Key and Explanations

---

## 📝 Multiple Choice Answers

---

### 🟢 Beginner

**Problem 1. Answer: ② `Checkbutton`**

Checkbutton allows multiple selections.

---

**Problem 2. Answer: ③ `Radiobutton`**

Radiobutton allows only one selection.

---

**Problem 3. Answer: ③ `BoolVar()`**

BoolVar stores True/False for checkboxes. (Also IntVar with 0/1)

---

**Problem 4. Answer: ③ `Text`**

Text widget handles multiple lines.

---

**Problem 5. Answer: ① `messagebox.showinfo()`**

showinfo() displays information dialog.

---

**Problem 6. Answer: ① `orient="horizontal"`**

Horizontal slider uses `orient="horizontal"`.

---

**Problem 7. Answer: ② All radio buttons share the same `variable`**

Sharing variable ensures only one selection.

---

### 🟡 Intermediate

**Problem 8. Answer: ② `text.get("1.0", tk.END)`**

Text uses "line.column" format: "1.0" to tk.END.

---

**Problem 9. Answer: ② `messagebox.askyesno()`**

askyesno() asks yes/no question.

---

**Problem 10. Answer: ③ `0`**

IntVar: unchecked = 0, checked = 1.

---

**Problem 11. Answer: ② `window.config(menu=menubar)`**

config() method sets menu.

---

**Problem 12. Answer: ② `yscrollcommand=scrollbar.set`**

yscrollcommand connects scrollbar.

---

### 🔴 Advanced

**Problem 13. Answer: ③ Returns `True` if Yes, `False` if No**

askyesno() returns boolean.

---

**Problem 14. Answer: ③ `value` parameter**

Radio button returns its `value` parameter.

---

**Problem 15. Answer: ② Opens open file dialog**

askopenfilename() opens file selection dialog.

---

## 📝 Short Answer Key

---

### 🟢 Beginner

**Problem 16. Model Answer:**

Checkbutton = select multiple
Radiobutton = select one only

---

**Problem 17. Model Answer:**

messagebox = dialog windows for messages.

Types: showinfo, showwarning, showerror, askyesno, askquestion.

---

**Problem 18. Model Answer:**

StringVar() = stores strings, IntVar() = stores integers.

Get value with var.get(), set with var.set().

---

### 🟡 Intermediate

**Problem 19. Model Answer:**

Create menubar, add menus with cascade, add commands to menus.

---

**Problem 20. Model Answer:**

Set Text `yscrollcommand=scrollbar.set` and scrollbar `command=text.yview`.

---

### 🔴 Advanced

**Problem 21. Model Answer:**

Form collects name, validates agreement, shows result.

---

## 💻 Hands-On Solutions

---

### 🟢 Beginner

**Problem 22. Model Answer:**

```python
import tkinter as tk

window = tk.Tk()
window.title("Widget Demo")
window.geometry("400x300")

tk.Label(window, text="=== Widget Demo ===").pack()

# Checkbuttons
tk.Label(window, text="Checkboxes:").pack()
check_vars = []
for item in ["Python", "Java", "JavaScript"]:
    var = tk.BoolVar()
    check_vars.append(var)
    tk.Checkbutton(window, text=item, variable=var).pack()

# Radiobuttons
tk.Label(window, text="Radio Buttons:").pack()
radio_var = tk.StringVar(value="Medium")
for item in ["Easy", "Medium", "Hard"]:
    tk.Radiobutton(window, text=item, variable=radio_var, value=item).pack()

window.mainloop()
```

---

**Problem 23. Model Answer:**

```python
import tkinter as tk
from tkinter import messagebox

def show_info():
    messagebox.showinfo("Info", "This is information")

def show_warning():
    messagebox.showwarning("Warning", "This is warning")

def show_error():
    messagebox.showerror("Error", "This is error")

def show_question():
    result = messagebox.askyesno("Question", "Do you agree?")
    messagebox.showinfo("Result", f"You answered: {result}")

window = tk.Tk()
window.title("Messagebox Demo")
window.geometry("300x200")

tk.Button(window, text="Info", command=show_info).pack(pady=5)
tk.Button(window, text="Warning", command=show_warning).pack(pady=5)
tk.Button(window, text="Error", command=show_error).pack(pady=5)
tk.Button(window, text="Question", command=show_question).pack(pady=5)

window.mainloop()
```

---

### 🟡 Intermediate

**Problem 24. Model Answer:**

```python
import tkinter as tk

window = tk.Tk()
window.title("Text Editor")
window.geometry("500x400")

tk.Label(window, text="=== Text Editor ===").pack()

# Create frame for text and scrollbar
frame = tk.Frame(window)
frame.pack(fill=tk.BOTH, expand=True, padx=5, pady=5)

# Scrollbar
scrollbar = tk.Scrollbar(frame)
scrollbar.pack(side=tk.RIGHT, fill=tk.Y)

# Text widget
text = tk.Text(frame, yscrollcommand=scrollbar.set, height=15, width=50)
text.pack(side=tk.LEFT, fill=tk.BOTH, expand=True)

scrollbar.config(command=text.yview)

# Buttons
def save():
    content = text.get("1.0", tk.END)
    with open("note.txt", "w") as f:
        f.write(content)

def clear():
    text.delete("1.0", tk.END)

button_frame = tk.Frame(window)
button_frame.pack(pady=5)

tk.Button(button_frame, text="Save", command=save).pack(side=tk.LEFT, padx=5)
tk.Button(button_frame, text="Clear", command=clear).pack(side=tk.LEFT, padx=5)

window.mainloop()
```

---

**Problem 25. Model Answer:**

```python
import tkinter as tk

def open_file():
    tk.messagebox.showinfo("Open", "Opening file...")

def save_file():
    tk.messagebox.showinfo("Save", "Saving file...")

def exit_app():
    window.quit()

window = tk.Tk()
window.title("Menu App")
window.geometry("400x300")

# Create menubar
menubar = tk.Menu(window)
window.config(menu=menubar)

# File menu
file_menu = tk.Menu(menubar)
menubar.add_cascade(label="File", menu=file_menu)
file_menu.add_command(label="Open", command=open_file)
file_menu.add_command(label="Save", command=save_file)
file_menu.add_separator()
file_menu.add_command(label="Exit", command=exit_app)

# Main content
tk.Label(window, text="Main Content Area", font=("Arial", 20)).pack(pady=20)

window.mainloop()
```

---

### 🔴 Advanced

**Problem 26. Model Answer:**

```python
import tkinter as tk
from tkinter import messagebox

def submit_form():
    name = entry_name.get()
    age = entry_age.get()
    gender = var_gender.get()
    languages = []
    for var, lang in zip(check_vars, ["Python", "Java", "C++"]):
        if var.get():
            languages.append(lang)
    experience = scale_var.get()
    comments = text_comments.get("1.0", tk.END)
  
    result = f"Name: {name}\nAge: {age}\nGender: {gender}\nLanguages: {', '.join(languages)}\nExperience: {experience} years"
    messagebox.showinfo("Success", result)

def reset_form():
    entry_name.delete(0, tk.END)
    entry_age.delete(0, tk.END)
    var_gender.set("")
    for var in check_vars:
        var.set(False)
    scale_var.set(0)
    text_comments.delete("1.0", tk.END)

window = tk.Tk()
window.title("Survey Form")
window.geometry("500x500")

tk.Label(window, text="=== Survey Form ===", font=("Arial", 16)).pack(pady=10)

# Name
tk.Label(window, text="Name:").pack()
entry_name = tk.Entry(window, width=30)
entry_name.pack(pady=5)

# Age
tk.Label(window, text="Age:").pack()
entry_age = tk.Entry(window, width=10)
entry_age.pack(pady=5)

# Gender
tk.Label(window, text="Gender:").pack()
var_gender = tk.StringVar()
tk.Radiobutton(window, text="Male", variable=var_gender, value="Male").pack()
tk.Radiobutton(window, text="Female", variable=var_gender, value="Female").pack()

# Languages
tk.Label(window, text="Languages:").pack()
check_vars = []
for lang in ["Python", "Java", "C++"]:
    var = tk.BoolVar()
    check_vars.append(var)
    tk.Checkbutton(window, text=lang, variable=var).pack()

# Experience
tk.Label(window, text="Experience (years):").pack()
scale_var = tk.IntVar()
tk.Scale(window, from_=0, to=20, variable=scale_var, orient=tk.HORIZONTAL).pack()

# Comments
tk.Label(window, text="Comments:").pack()
text_comments = tk.Text(window, height=5, width=40)
text_comments.pack(pady=5)

# Buttons
button_frame = tk.Frame(window)
button_frame.pack(pady=10)

tk.Button(button_frame, text="Submit", command=submit_form).pack(side=tk.LEFT, padx=5)
tk.Button(button_frame, text="Reset", command=reset_form).pack(side=tk.LEFT, padx=5)

window.mainloop()
```

---


Thank you for your attention.   
Cho Jeonghyun ([peterchokr@gmail.com](mailto:peterchokr@gmail.com)). Yeungnam University College

"Produced in collaboration with Claude and Gemini."
