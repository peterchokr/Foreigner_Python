# Chapter 23: Matplotlib Visualization — Practice Problems

---

## 📝 Multiple Choice Questions

---

### 🟢 Beginner

**Problem 1.** What is the most widely used Python library for drawing graphs?

① `pandas`
② `matplotlib`
③ `seaborn`
④ `tkinter`

---

**Problem 2.** What function displays a graph on screen in matplotlib?

① `plt.draw()`
② `plt.display()`
③ `plt.show()`
④ `plt.render()`

---

**Problem 3.** What function draws a line graph?

① `plt.bar()`
② `plt.line()`
③ `plt.plot()`
④ `plt.scatter()`

---

**Problem 4.** What function draws a bar chart?

① `plt.plot()`
② `plt.bar()`
③ `plt.pie()`
④ `plt.hist()`

---

**Problem 5.** What function adds a title to a graph?

① `plt.name()`
② `plt.header()`
③ `plt.title()`
④ `plt.label()`

---

**Problem 6.** What function adds grid lines to a graph?

① `plt.line()`
② `plt.grid()`
③ `plt.mesh()`
④ `plt.ruler()`

---

**Problem 7.** What is the correct way to import matplotlib?

① `import matplotlib`
② `import matplotlib.pyplot as plt`
③ `from matplotlib import graph`
④ `import plt`

---

### 🟡 Intermediate

**Problem 8.** What option displays the percentage for each item in a pie chart?

① `percent='%1.1f%%'`
② `autopct='%1.1f%%'`
③ `ratio='%1.1f%%'`
④ `label_pct='%1.1f%%'`

---

**Problem 9.** What function arranges multiple graphs on one screen?

① `plt.multi()`
② `plt.subplot()`
③ `plt.layout()`
④ `plt.grid_plot()`

---

**Problem 10.** What function draws a scatter plot?

① `plt.dot()`
② `plt.point()`
③ `plt.scatter()`
④ `plt.plot_dots()`

---

**Problem 11.** What function saves a graph as an image file?

① `plt.save()`
② `plt.savefig()`
③ `plt.export()`
④ `plt.write()`

---

**Problem 12.** What option sets the shape of data points in a line graph?

① `point='o'`
② `dot='o'`
③ `marker='o'`
④ `shape='o'`

---

### 🔴 Advanced

**Problem 13.** What does `plt.subplot(2, 3, 4)` mean?

① **4th position in 2 rows x 3 columns**
② 3rd position in 2 rows x 3 columns
③ 4 graphs arranged in 2x3
④ 2~3 columns in 4th row

---

**Problem 14.** What is the result of this code?

```python
fruits = ['Apple', 'Banana', 'Orange']
sales = [150, 120, 180]
for i, v in enumerate(sales):
    plt.text(i, v + 5, str(v), ha='center')
```

① Numbers displayed below each bar
② **Numbers displayed above each bar showing sales amount**
③ Sales amount displayed on X-axis
④ Numbers added to legend

---

**Problem 15.** What code fixes Korean font corruption?

① `plt.font('Malgun Gothic')`
② `plt.rcParams['font.family'] = 'Malgun Gothic'`
③ `plt.encoding('utf-8')`
④ `plt.set_font('korean')`

---

## 📝 Short Answer Questions

---

### 🟢 Beginner

**Problem 16.** Explain what matplotlib is and its main purpose.

---

**Problem 17.** What are the differences between `plt.plot()`, `plt.bar()`, and `plt.scatter()`?

---

**Problem 18.** What functions are needed to add labels to axes?

---

### 🟡 Intermediate

**Problem 19.** Explain how to arrange multiple graphs using subplot.

```python
plt.subplot(2, 2, 1)
plt.plot(x1, y1)

plt.subplot(2, 2, 2)
plt.bar(x2, y2)

plt.show()
```

---

**Problem 20.** How to add text or values on a graph?

---

### 🔴 Advanced

**Problem 21.** Write code to create multiple types of graphs with styling.

```python
import matplotlib.pyplot as plt

# Multiple graphs
plt.figure(figsize=(12, 4))

# Line graph
plt.subplot(1, 3, 1)
plt.plot(x, y, marker='o', color='red')
plt.title('Line Graph')
plt.grid()

# Bar chart
plt.subplot(1, 3, 2)
plt.bar(categories, values, color='blue')
plt.title('Bar Chart')

# Scatter plot
plt.subplot(1, 3, 3)
plt.scatter(x_data, y_data, color='green')
plt.title('Scatter Plot')

plt.tight_layout()
plt.show()
```

---

## 💻 Hands-On Problems

---

### 🟢 Beginner

**Problem 22.** Create a simple line graph.

> Draw a line graph showing x and y values.

Output example:

```
=== Line Graph ===
X: [1, 2, 3, 4, 5]
Y: [2, 4, 6, 8, 10]
Title: Simple Graph
Grid: Enabled
```

---

**Problem 23.** Create a bar chart with labels.

> Draw bar chart with category labels and values.

Output example:

```
=== Bar Chart ===
Categories: Apple, Banana, Orange
Values: 100, 150, 120
Title: Fruit Sales
Y-axis Label: Sales (units)
```

---

### 🟡 Intermediate

**Problem 24.** Create a pie chart with percentages.

> Draw pie chart showing proportions with percentage labels.

Output example:

```
=== Pie Chart ===
Categories: A, B, C, D
Values: 25, 35, 20, 20
Percentages: 25.0%, 35.0%, 20.0%, 20.0%
Title: Market Share
```

---

**Problem 25.** Create multiple graphs with subplot.

> Arrange 3 different graph types on one figure.

Output example:

```
=== Multiple Graphs ===
[Line Graph]  [Bar Chart]  [Scatter Plot]
with titles and labels
```

---

### 🔴 Advanced

**Problem 26.** Create comprehensive visualization with multiple data types.

> Complex visualization with styling, legends, and saved output.

Output example:

```
=== Comprehensive Visualization ===
Figure 1: Line Graph with Multiple Lines
- Line 1 (Red): Data A
- Line 2 (Blue): Data B
- Title: Sales Trends
- Legend: Enabled
- Grid: Enabled

Figure 2: Comparison Charts
- Bar Chart: Monthly Comparison
- Pie Chart: Distribution
- Scatter: Correlation

Saved as: visualization.png
```

---

---

# 🔑 Answer Key and Explanations

---

## 📝 Multiple Choice Answers

---

### 🟢 Beginner

**Problem 1. Answer: ② `matplotlib`**

Matplotlib is the primary graphing library for Python.

---

**Problem 2. Answer: ③ `plt.show()`**

`show()` displays the graph window.

---

**Problem 3. Answer: ③ `plt.plot()`**

`plot()` draws line graphs.

---

**Problem 4. Answer: ② `plt.bar()`**

`bar()` creates bar charts.

---

**Problem 5. Answer: ③ `plt.title()`**

`title()` adds graph title.

---

**Problem 6. Answer: ② `plt.grid()`**

`grid()` adds grid lines.

---

**Problem 7. Answer: ② `import matplotlib.pyplot as plt`**

Standard matplotlib import statement.

---

### 🟡 Intermediate

**Problem 8. Answer: ② `autopct='%1.1f%%'`**

autopct parameter shows percentages in pie chart.

---

**Problem 9. Answer: ② `plt.subplot()`**

subplot() arranges multiple graphs.

---

**Problem 10. Answer: ③ `plt.scatter()`**

`scatter()` creates scatter plots.

---

**Problem 11. Answer: ② `plt.savefig()`**

`savefig()` saves graph as image.

---

**Problem 12. Answer: ③ `marker='o'`**

marker parameter sets point style.

---

### 🔴 Advanced

**Problem 13. Answer: ① 4th position in 2x3 grid**

subplot(2,3,4) creates 2 rows, 3 columns, 4th position.

---

**Problem 14. Answer: ② Numbers above each bar**

`plt.text(i, v + 5, str(v))` places text above bar.

---

**Problem 15. Answer: ② `plt.rcParams['font.family'] = 'Malgun Gothic'`**

rcParams sets font for Korean characters.

---

## 📝 Short Answer Key

---

### 🟢 Beginner

**Problem 16. Model Answer:**

Matplotlib = Python library for creating graphs and charts.

Purpose: visualize data in various formats.

---

**Problem 17. Model Answer:**

`plot()` = line graph, `bar()` = bar chart, `scatter()` = scatter plot.

---

**Problem 18. Model Answer:**

`plt.xlabel()` and `plt.ylabel()` for axis labels.

---

### 🟡 Intermediate

**Problem 19. Model Answer:**

subplot(rows, cols, position) creates grid layout for graphs.

---

**Problem 20. Model Answer:**

`plt.text()` adds text at specific coordinates on graph.

---

### 🔴 Advanced

**Problem 21. Model Answer:**

Multiple graphs with different types and styling on one figure.

---

## 💻 Hands-On Solutions

---

### 🟢 Beginner

**Problem 22. Model Answer:**

```python
import matplotlib.pyplot as plt

x = [1, 2, 3, 4, 5]
y = [2, 4, 6, 8, 10]

plt.plot(x, y, marker='o')
plt.title('Simple Graph')
plt.xlabel('X-axis')
plt.ylabel('Y-axis')
plt.grid(True)
plt.show()
```

---

**Problem 23. Model Answer:**

```python
import matplotlib.pyplot as plt

categories = ['Apple', 'Banana', 'Orange']
values = [100, 150, 120]

plt.bar(categories, values, color='skyblue')
plt.title('Fruit Sales')
plt.ylabel('Sales (units)')
plt.xlabel('Fruit')
plt.show()
```

---

### 🟡 Intermediate

**Problem 24. Model Answer:**

```python
import matplotlib.pyplot as plt

categories = ['A', 'B', 'C', 'D']
values = [25, 35, 20, 20]

plt.pie(values, labels=categories, autopct='%1.1f%%')
plt.title('Market Share')
plt.show()
```

---

**Problem 25. Model Answer:**

```python
import matplotlib.pyplot as plt

x = [1, 2, 3, 4, 5]
y1 = [2, 4, 6, 8, 10]

categories = ['A', 'B', 'C']
values = [10, 20, 30]

x_scatter = [1, 2, 3, 4, 5]
y_scatter = [1, 4, 2, 5, 3]

plt.figure(figsize=(12, 4))

plt.subplot(1, 3, 1)
plt.plot(x, y1, marker='o')
plt.title('Line Graph')
plt.grid()

plt.subplot(1, 3, 2)
plt.bar(categories, values)
plt.title('Bar Chart')

plt.subplot(1, 3, 3)
plt.scatter(x_scatter, y_scatter)
plt.title('Scatter Plot')

plt.tight_layout()
plt.show()
```

---

### 🔴 Advanced

**Problem 26. Model Answer:**

```python
import matplotlib.pyplot as plt
import matplotlib
matplotlib.rcParams['font.family'] = 'DejaVu Sans'

# Create figure with multiple subplots
fig = plt.figure(figsize=(14, 8))

# 1. Line Graph with Multiple Lines
ax1 = plt.subplot(2, 2, 1)
months = [1, 2, 3, 4, 5]
data_a = [10, 12, 15, 13, 18]
data_b = [8, 10, 12, 14, 16]
ax1.plot(months, data_a, marker='o', label='Data A', color='red')
ax1.plot(months, data_b, marker='s', label='Data B', color='blue')
ax1.set_title('Sales Trends')
ax1.set_xlabel('Month')
ax1.set_ylabel('Sales')
ax1.legend()
ax1.grid(True)

# 2. Bar Chart
ax2 = plt.subplot(2, 2, 2)
categories = ['Q1', 'Q2', 'Q3', 'Q4']
values = [100, 120, 140, 160]
ax2.bar(categories, values, color='skyblue')
ax2.set_title('Quarterly Comparison')
ax2.set_ylabel('Revenue')

# 3. Pie Chart
ax3 = plt.subplot(2, 2, 3)
sizes = [30, 25, 20, 25]
labels = ['Product A', 'Product B', 'Product C', 'Product D']
ax3.pie(sizes, labels=labels, autopct='%1.1f%%')
ax3.set_title('Product Distribution')

# 4. Scatter Plot
ax4 = plt.subplot(2, 2, 4)
x_data = [1, 2, 3, 4, 5, 6]
y_data = [2, 4, 3, 5, 6, 5]
ax4.scatter(x_data, y_data, s=100, alpha=0.6, color='green')
ax4.set_title('Correlation Analysis')
ax4.set_xlabel('Variable X')
ax4.set_ylabel('Variable Y')

plt.tight_layout()
plt.savefig('visualization.png', dpi=100)
plt.show()
```

---


Thank you for your attention.   
Cho Jeonghyun ([peterchokr@gmail.com](mailto:peterchokr@gmail.com)). Yeungnam University College

"Produced in collaboration with Claude and Gemini."
