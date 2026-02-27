# Chapter 20: GUI Programming 1 (tkinter Basics) — Practice Problems

---

## 📝 Multiple Choice Questions

---

### 🟢 Beginner

**Problem 1.** What is the correct way to import tkinter?

① `import tk`
② `import tkinter`
③ `import gui`
④ `import window`

---

**Problem 2.** What is characteristic of GUI (Graphical User Interface)?

① Use text only to operate programs
② **Use visual elements like buttons and menus to operate programs**
③ Execute programs by typing commands
④ Use keyboard only

---

**Problem 3.** What method runs a tkinter window?

① `run()`
② `start()`
③ `mainloop()`
④ `execute()`

---

**Problem 4.** What part of the code sets the window size?

```python
window = tk.Tk()
window.title("Program")
window.geometry("400x300")
window.mainloop()
```

① `tk.Tk()`
② `window.title("Program")`
③ `window.geometry("400x300")`
④ `window.mainloop()`

---

**Problem 5.** What widget displays text on the screen in tkinter?

① `Button`
② `Label`
③ `Entry`
④ `Text`

---

**Problem 6.** What option connects a function to button clicks?

① `onclick`
② `command`
③ `function`
④ `event`

---

**Problem 7.** Where should `mainloop()` be placed in code?

① At the very beginning
② Right after import statements
③ Before creating widgets
④ **At the very end of code**

---

### 🟡 Intermediate

**Problem 8.** What method retrieves input from Entry widget?

① `value()`
② `text()`
③ `get()`
④ `read()`

---

**Problem 9.** What method arranges widgets in table format (rows/columns)?

① `pack()`
② `grid()`
③ `place()`
④ `table()`

---

**Problem 10.** What is the correct way to change Label text?

```python
label = tk.Label(window, text="Default text")
label.pack()
```

① `label.text = "New text"`
② `label.config(text="New text")`
③ `label.set("New text")`
④ `label.change("New text")`

---

**Problem 11.** What option adds top/bottom margin in `pack()`?

① `margin`
② `padx`
③ `pady`
④ `spacing`

---

**Problem 12.** What is the correct code to clear Entry widget content?

① `entry.clear()`
② `entry.delete(0, tk.END)`
③ `entry.remove()`
④ `entry.reset()`

---

### 🔴 Advanced

**Problem 13.** What does `sticky="e"` mean in `grid()`?

```python
tk.Label(window, text="Name:").grid(row=0, column=0, sticky="e")
```

① Align top (north)
② Align bottom (south)
③ **Align right (east)**
④ Align left (west)

---

**Problem 14.** What does this code do?

```python
def button_clicked():
    label.config(text="Clicked!")

button = tk.Button(window, text="Click", command=button_clicked)
button.pack()
```

① Creates button that does nothing
② **Creates button that changes label text when clicked**
③ Creates button that closes window
④ Error in code

---

**Problem 15.** How to get the value from an Entry widget and display in Label?

```python
entry = tk.Entry(window)
button = tk.Button(window, command=on_button_click)
label = tk.Label(window, text="")

def on_button_click():
    value = entry.get()
    label.config(text=value)
```

① Error, cannot get Entry value
② **Get Entry value with entry.get(), display with label.config()**
③ Use entry.value directly
④ Not possible

---

## 📝 Short Answer Questions

---

### 🟢 Beginner

**Problem 16.** Explain what tkinter is and why it is useful.

---

**Problem 17.** What is the difference between `pack()` and `grid()` geometry managers?

---

**Problem 18.** Explain what `mainloop()` does and why it is necessary.

---

### 🟡 Intermediate

**Problem 19.** How to create a simple window with a label and button? Write code.

```python
import tkinter as tk

def on_click():
    label.config(text="Button clicked!")

window = tk.Tk()
window.title("Simple App")
window.geometry("300x200")

label = tk.Label(window, text="Hello World")
label.pack(pady=10)

button = tk.Button(window, text="Click Me", command=on_click)
button.pack(pady=10)

window.mainloop()
```

---

**Problem 20.** Explain the purpose of `geometry()` method and different layout managers.

---

### 🔴 Advanced

**Problem 21.** Create a complete GUI application with Entry, Button, and Label with explanation.

```python
import tkinter as tk

def greet():
    name = entry.get()
    label.config(text=f"Hello, {name}!")

window = tk.Tk()
window.title("Greeting App")
window.geometry("400x300")

label = tk.Label(window, text="Enter your name", font=("Arial", 14))
label.pack(pady=10)

entry = tk.Entry(window, font=("Arial", 12))
entry.pack(pady=10)

button = tk.Button(window, text="Greet", command=greet)
button.pack(pady=10)

window.mainloop()
```

---

## 💻 Hands-On Problems

---

### 🟢 Beginner

**Problem 22.** Create a simple window with title and size.

> Create window with 500x400 size, title "My First GUI".

Output example:

```
Window Title: My First GUI
Window Size: 500x400
```

---

**Problem 23.** Create window with Label showing text.

> Create Label widget with custom font and text.

Output example:

```
Label Text: "Welcome to tkinter!"
Font: Arial, Size: 16
Color: Blue
```

---

### 🟡 Intermediate

**Problem 24.** Create window with Entry and Button to display input.

> Get user input from Entry, display in Label when button clicked.

Output example:

```
=== User Input Display ===
Enter text: John
[Button: Submit]
Display: You entered: John
```

---

**Problem 25.** Create calculator GUI with basic operations.

> Add two numbers using Entry widgets and Button.

Output example:

```
=== Simple Calculator ===
Number 1: 10
Number 2: 5
[Button: Add]
Result: 15
[Button: Subtract]
Result: 5
```

---

### 🔴 Advanced

**Problem 26.** Create comprehensive todo list GUI application.

> Add, display, and manage todo items with buttons.

Output example:

```
=== Todo List App ===
Enter task: Buy milk
[Button: Add]

Tasks:
1. Buy milk
2. Study Python

[Button: Delete]
[Button: Clear All]
```

---

---

# 🔑 Answer Key and Explanations

---

## 📝 Multiple Choice Answers

---

### 🟢 Beginner

**Problem 1. Answer: ② `import tkinter`**

Standard tkinter import statement.

---

**Problem 2. Answer: ② Use visual elements to operate**

GUI uses buttons, menus, not text.

---

**Problem 3. Answer: ③ `mainloop()`**

`mainloop()` runs the window event loop.

---

**Problem 4. Answer: ③ `window.geometry("400x300")`**

`geometry()` sets window size.

---

**Problem 5. Answer: ② `Label`**

Label displays text on screen.

---

**Problem 6. Answer: ② `command`**

`command` option connects function to button.

---

**Problem 7. Answer: ④ At the very end**

`mainloop()` must be last to start the application.

---

### 🟡 Intermediate

**Problem 8. Answer: ③ `get()`**

`entry.get()` retrieves input value.

---

**Problem 9. Answer: ② `grid()`**

`grid()` arranges widgets in rows/columns.

---

**Problem 10. Answer: ② `label.config(text="New text")`**

`config()` modifies widget properties.

---

**Problem 11. Answer: ③ `pady`**

`pady` = padding on y-axis (top/bottom).

---

**Problem 12. Answer: ② `entry.delete(0, tk.END)`**

`delete()` removes content from Entry.

---

### 🔴 Advanced

**Problem 13. Answer: ③ Align right (east)**

`sticky="e"` aligns to east (right).

---

**Problem 14. Answer: ② Button changes label text**

`command=button_clicked` connects function to button.

---

**Problem 15. Answer: ② Get with entry.get(), display with label.config()**

Standard method to get Entry value and update Label.

---

## 📝 Short Answer Key

---

### 🟢 Beginner

**Problem 16. Model Answer:**

tkinter = Python GUI library for creating windows and buttons.

Useful for creating desktop applications easily.

---

**Problem 17. Model Answer:**

`pack()` = simpler, stacks widgets
`grid()` = table layout with rows/columns

---

**Problem 18. Model Answer:**

`mainloop()` = starts event loop to listen for user actions.

Necessary for window to stay open and respond to clicks.

---

### 🟡 Intermediate

**Problem 19. Model Answer:**

Code shown creates window with label and button.

---

**Problem 20. Model Answer:**

`geometry()` sets window size.

Layout managers: pack (simple), grid (table), place (exact position).

---

### 🔴 Advanced

**Problem 21. Model Answer:**

Greeting app gets name from Entry, displays personalized message.

---

## 💻 Hands-On Solutions

---

### 🟢 Beginner

**Problem 22. Model Answer:**

```python
import tkinter as tk

window = tk.Tk()
window.title("My First GUI")
window.geometry("500x400")

label = tk.Label(window, text="Window created!")
label.pack()

window.mainloop()
```

---

**Problem 23. Model Answer:**

```python
import tkinter as tk

window = tk.Tk()
window.title("Label Example")
window.geometry("400x200")

label = tk.Label(
    window, 
    text="Welcome to tkinter!",
    font=("Arial", 16),
    fg="blue"
)
label.pack(pady=20)

window.mainloop()
```

---

### 🟡 Intermediate

**Problem 24. Model Answer:**

```python
import tkinter as tk

def display_input():
    text = entry.get()
    label.config(text=f"You entered: {text}")

window = tk.Tk()
window.title("Input Display")
window.geometry("400x300")

label = tk.Label(window, text="Enter text below:")
label.pack(pady=10)

entry = tk.Entry(window)
entry.pack(pady=10)

button = tk.Button(window, text="Submit", command=display_input)
button.pack(pady=10)

window.mainloop()
```

---

**Problem 25. Model Answer:**

```python
import tkinter as tk

def add_numbers():
    try:
        num1 = float(entry1.get())
        num2 = float(entry2.get())
        result = num1 + num2
        result_label.config(text=f"Sum: {result}")
    except ValueError:
        result_label.config(text="Invalid input!")

def subtract_numbers():
    try:
        num1 = float(entry1.get())
        num2 = float(entry2.get())
        result = num1 - num2
        result_label.config(text=f"Difference: {result}")
    except ValueError:
        result_label.config(text="Invalid input!")

window = tk.Tk()
window.title("Simple Calculator")
window.geometry("400x300")

tk.Label(window, text="Number 1:").pack()
entry1 = tk.Entry(window)
entry1.pack(pady=5)

tk.Label(window, text="Number 2:").pack()
entry2 = tk.Entry(window)
entry2.pack(pady=5)

button_add = tk.Button(window, text="Add", command=add_numbers)
button_add.pack(pady=5)

button_sub = tk.Button(window, text="Subtract", command=subtract_numbers)
button_sub.pack(pady=5)

result_label = tk.Label(window, text="Result: ", font=("Arial", 12))
result_label.pack(pady=10)

window.mainloop()
```

---

### 🔴 Advanced

**Problem 26. Model Answer:**

```python
import tkinter as tk

tasks = []

def add_task():
    task = entry.get()
    if task:
        tasks.append(task)
        entry.delete(0, tk.END)
        update_list()

def delete_task():
    try:
        index = int(delete_entry.get())
        if 0 <= index < len(tasks):
            tasks.pop(index)
            delete_entry.delete(0, tk.END)
            update_list()
    except:
        pass

def clear_all():
    tasks.clear()
    update_list()

def update_list():
    listbox.delete(0, tk.END)
    for i, task in enumerate(tasks):
        listbox.insert(tk.END, f"{i}. {task}")

window = tk.Tk()
window.title("Todo List")
window.geometry("400x400")

tk.Label(window, text="=== Todo List App ===").pack(pady=10)

tk.Label(window, text="Add task:").pack()
entry = tk.Entry(window, width=40)
entry.pack(pady=5)

add_btn = tk.Button(window, text="Add Task", command=add_task)
add_btn.pack(pady=5)

tk.Label(window, text="Tasks:").pack()
listbox = tk.Listbox(window, height=10, width=40)
listbox.pack(pady=5)

tk.Label(window, text="Delete task (by number):").pack()
delete_entry = tk.Entry(window, width=10)
delete_entry.pack()

delete_btn = tk.Button(window, text="Delete", command=delete_task)
delete_btn.pack(pady=5)

clear_btn = tk.Button(window, text="Clear All", command=clear_all)
clear_btn.pack(pady=5)

window.mainloop()
```

---


Thank you for your attention.   
Cho Jeonghyun ([peterchokr@gmail.com](mailto:peterchokr@gmail.com)). Yeungnam University College

"Produced in collaboration with Claude and Gemini."
