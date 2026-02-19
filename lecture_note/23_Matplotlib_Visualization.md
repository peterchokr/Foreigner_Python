# Chapter 23. Matplotlib Data Visualization

---

## 📚 Learning Objectives

After completing this chapter, you will understand how to use Matplotlib to visualize data as graphs. You will be able to create line graphs, bar charts, pie charts, and other visualizations to make data easy to understand at a glance.

이번 장을 마치면 여러분은 Matplotlib을 사용하여 데이터를 그래프로 시각화할 수 있습니다. 꺾은선 그래프, 막대 그래프, 원 그래프 등을 그려 데이터를 한눈에 이해하기 쉽게 표현할 수 있게 됩니다.

---

## 1️⃣ What is Data Visualization? (데이터 시각화란?)

Numeric data alone is difficult to understand. However, when you draw it as a graph, you can grasp it at a glance!

숫자로만 된 데이터는 이해하기 어렵습니다. 하지만 그래프로 그리면 한눈에 파악할 수 있습니다!

### Why is Visualization Necessary? (왜 시각화가 필요할까?)

```
Data as numbers              Data as a graph
━━━━━━━━━━━━━━━━━━━━━━━━     ━━━━━━━━━━━━━━━━━━━━
January: 100 people               ↑
February: 120 people          150 │     ●
March: 90 people                  │   ●   ●
April: 150 people             100 │ ●       ●
May: 130 people                   │
                               50 │
                                  └─────────────→
                                  1  2  3  4  5

? Looks complex...             ✓ Easy to see!
```

**Benefits of Visualization:**

- ✅ Easy to discover patterns and trends
- ✅ Convenient data comparison
- ✅ Quick identification of outliers
- ✅ Effective for reports and presentations

### What is Matplotlib? (Matplotlib이란?)

Matplotlib is the most widely used graph drawing library in Python. It allows you to create various types of charts and customize them easily.

파이썬에서 가장 많이 사용되는 그래프 그리기 라이브러리입니다.

---

## 2️⃣ Installing Matplotlib and Basic Usage (Matplotlib 설치 및 기본 사용)

### Installing Matplotlib (설치하기)

In the terminal or command prompt, run the following command:

터미널이나 명령 프롬프트에서 다음 명령어를 실행하세요:

```bash
pip install matplotlib
```

### Drawing Your First Graph (첫 번째 그래프 그리기)

```python
import matplotlib.pyplot as plt

# Prepare data (데이터 준비)
x = [1, 2, 3, 4, 5]
y = [2, 4, 6, 8, 10]

# Draw the graph (그래프 그리기)
plt.plot(x, y)

# Display the graph (그래프 표시)
plt.show()
```

**When you run it, a line graph will appear!**

실행하면 꺾은선 그래프가 나타납니다!

### Adding Title and Labels to the Graph (그래프에 제목과 라벨 추가)

```python
import matplotlib.pyplot as plt

# Data (데이터)
x = [1, 2, 3, 4, 5]
y = [2, 4, 6, 8, 10]

# Draw the graph (그래프 그리기)
plt.plot(x, y)

# Add title and labels (제목과 라벨 추가)
plt.title('Simple Line Graph')                    # Title (제목)
plt.xlabel('X Axis')                              # X-axis name (X축 이름)
plt.ylabel('Y Axis')                              # Y-axis name (Y축 이름)

# Display the graph (그래프 표시)
plt.show()
```


## 3️⃣ Line Graphs (꺾은선 그래프)

Line graphs are best used to show changes over time.

시간에 따른 변화를 보여줄 때 가장 좋습니다.

### Basic Line Graph (기본 꺾은선 그래프)

```python
import matplotlib.pyplot as plt

# Data (monthly sales) (데이터 - 월별 판매량)
months = [1, 2, 3, 4, 5, 6]
sales = [100, 120, 90, 150, 130, 170]

# Draw the graph (그래프 그리기)
plt.plot(months, sales)

# Add title and labels (제목과 라벨)
plt.title('Monthly Sales', fontsize=16)
plt.xlabel('Month', fontsize=12)
plt.ylabel('Sales (Units)', fontsize=12)

# Add grid (격자 추가)
plt.grid(True, linestyle='--', alpha=0.7)

plt.show()
```

### Styling Line Appearance (선 스타일 꾸미기)

```python
import matplotlib.pyplot as plt

months = [1, 2, 3, 4, 5, 6]
sales = [100, 120, 90, 150, 130, 170]

# Specify line style (선 스타일 지정)
plt.plot(months, sales, 
         color='blue',           # Color (색상)
         linewidth=2,            # Line thickness (선 굵기)
         linestyle='-',          # Line style ('-', '--', '-.', ':')
         marker='o',             # Point shape ('o', 's', '^', '*' etc.) (점 모양)
         markersize=8,           # Point size (점 크기)
         label='2024 Sales')     # Legend name (범례 이름)

plt.title('Monthly Sales', fontsize=16)
plt.xlabel('Month', fontsize=12)
plt.ylabel('Sales (Units)', fontsize=12)
plt.legend()  # Display legend (범례 표시)
plt.grid(True, linestyle='--', alpha=0.5)

plt.show()
```

### Drawing Multiple Lines (여러 선 그리기)

```python
import matplotlib.pyplot as plt

months = [1, 2, 3, 4, 5, 6]
sales_2023 = [80, 95, 85, 120, 100, 140]
sales_2024 = [100, 120, 90, 150, 130, 170]

# Draw two lines (두 개의 선 그리기)
plt.plot(months, sales_2023, marker='o', label='2023', linewidth=2)
plt.plot(months, sales_2024, marker='s', label='2024', linewidth=2)

plt.title('Year-over-Year Sales Comparison', fontsize=16)
plt.xlabel('Month', fontsize=12)
plt.ylabel('Sales (Units)', fontsize=12)
plt.legend(fontsize=10)
plt.grid(True, linestyle='--', alpha=0.5)

plt.show()
```

---

## 4️⃣ Bar Charts (막대 그래프)

Bar charts are used to compare sizes between items.

항목 간의 크기를 비교할 때 사용합니다.

### Basic Bar Chart (기본 막대 그래프)

```python
import matplotlib.pyplot as plt

# Data (fruit sales) (데이터 - 과일별 판매량)
fruits = ['Apple', 'Banana', 'Orange', 'Grape', 'Strawberry']
sales = [150, 120, 180, 90, 200]

# Draw bar chart (막대 그래프)
plt.bar(fruits, sales, color='skyblue', width=0.6)

plt.title('Fruit Sales', fontsize=16)
plt.xlabel('Fruit', fontsize=12)
plt.ylabel('Sales (Units)', fontsize=12)
plt.grid(axis='y', linestyle='--', alpha=0.5)

plt.show()
```

### Different Bar Colors (막대 색상 다르게)

```python
import matplotlib.pyplot as plt

fruits = ['Apple', 'Banana', 'Orange', 'Grape', 'Strawberry']
sales = [150, 120, 180, 90, 200]
colors = ['red', 'yellow', 'orange', 'purple', 'pink']

# Specify bar colors (막대 색상 지정)
plt.bar(fruits, sales, color=colors, width=0.6)

plt.title('Fruit Sales', fontsize=16)
plt.xlabel('Fruit', fontsize=12)
plt.ylabel('Sales (Units)', fontsize=12)

# Display number on each bar (각 막대 위에 숫자 표시)
for i, v in enumerate(sales):
    plt.text(i, v + 5, str(v), ha='center', fontsize=10)

plt.show()
```

### Horizontal Bar Chart (가로 막대 그래프)

```python
import matplotlib.pyplot as plt

fruits = ['Apple', 'Banana', 'Orange', 'Grape', 'Strawberry']
sales = [150, 120, 180, 90, 200]

# Draw horizontal bar chart (가로 막대 그래프)
plt.barh(fruits, sales, color='lightgreen')

plt.title('Fruit Sales', fontsize=16)
plt.xlabel('Sales (Units)', fontsize=12)
plt.ylabel('Fruit', fontsize=12)
plt.grid(axis='x', linestyle='--', alpha=0.5)

plt.show()
```

### Grouped Bar Chart (그룹 막대 그래프)

```python
import matplotlib.pyplot as plt
import numpy as np

# Data (데이터)
categories = ['Q1', 'Q2', 'Q3', 'Q4']
product_a = [100, 120, 90, 150]
product_b = [90, 110, 100, 130]

# X-axis positions (x축 위치)
x = np.arange(len(categories))
width = 0.35  # Bar width (막대 너비)

# Draw grouped bar chart (그룹 막대 그래프)
plt.bar(x - width/2, product_a, width, label='Product A', color='skyblue')
plt.bar(x + width/2, product_b, width, label='Product B', color='lightcoral')

plt.title('Quarterly Product Sales', fontsize=16)
plt.xlabel('Quarter', fontsize=12)
plt.ylabel('Sales', fontsize=12)
plt.xticks(x, categories)  # Set x-axis labels (x축 라벨 설정)
plt.legend()
plt.grid(axis='y', linestyle='--', alpha=0.5)

plt.show()
```

---

## 5️⃣ Pie Charts (원 그래프)

Pie charts are used to show the proportion of each item in the whole.

전체에서 각 항목이 차지하는 비율을 보여줄 때 사용합니다.

### Basic Pie Chart (기본 원 그래프)

```python
import matplotlib.pyplot as plt

# Data (hobby preferences) (데이터 - 취미 선호도)
hobbies = ['Sports', 'Reading', 'Movies', 'Gaming', 'Music']
counts = [30, 25, 20, 15, 10]

# Draw pie chart (원 그래프)
plt.pie(counts, labels=hobbies, autopct='%1.1f%%', startangle=90)

plt.title('Hobby Preferences', fontsize=16)
plt.axis('equal')  # Make the circle accurate (원을 정확한 원으로)

plt.show()
```

### Styling Pie Chart (원 그래프 꾸미기)

```python
import matplotlib.pyplot as plt

hobbies = ['Sports', 'Reading', 'Movies', 'Gaming', 'Music']
counts = [30, 25, 20, 15, 10]
colors = ['#ff9999', '#66b3ff', '#99ff99', '#ffcc99', '#ff99cc']
explode = (0.1, 0, 0, 0, 0)  # Highlight first slice (첫 번째 조각 강조)

# Draw pie chart with styling (원 그래프 꾸미기)
plt.pie(counts, 
        labels=hobbies,
        colors=colors,
        autopct='%1.1f%%',     # Display percentage (퍼센트 표시)
        startangle=90,          # Starting angle (시작 각도)
        explode=explode,        # Separate slices (조각 띄우기)
        shadow=True)            # Add shadow (그림자)

plt.title('Hobby Preferences', fontsize=16)
plt.axis('equal')

plt.show()
```

---

## 6️⃣ Scatter Plots (산점도)

Scatter plots are used to show the relationship between two variables.

두 변수 간의 관계를 보여줄 때 사용합니다.

### Basic Scatter Plot (기본 산점도)

```python
import matplotlib.pyplot as plt

# Data (height and weight) (데이터 - 키와 몸무게)
height = [160, 165, 170, 175, 180, 185]
weight = [55, 60, 65, 70, 75, 80]

# Draw scatter plot (산점도)
plt.scatter(height, weight, s=100, c='blue', alpha=0.6)

plt.title('Relationship between Height and Weight', fontsize=16)
plt.xlabel('Height (cm)', fontsize=12)
plt.ylabel('Weight (kg)', fontsize=12)
plt.grid(True, linestyle='--', alpha=0.5)

plt.show()
```

### Different Colors by Group (그룹별 색상 다르게)

```python
import matplotlib.pyplot as plt

# Male data (남성 데이터)
male_height = [170, 175, 180, 185, 190]
male_weight = [65, 70, 75, 80, 85]

# Female data (여성 데이터)
female_height = [155, 160, 165, 170, 175]
female_weight = [50, 55, 60, 65, 70]

# Draw scatter plot by group (산점도 - 그룹별)
plt.scatter(male_height, male_weight, s=100, c='blue', label='Male', alpha=0.6)
plt.scatter(female_height, female_weight, s=100, c='red', label='Female', alpha=0.6)

plt.title('Height and Weight by Gender', fontsize=16)
plt.xlabel('Height (cm)', fontsize=12)
plt.ylabel('Weight (kg)', fontsize=12)
plt.legend()
plt.grid(True, linestyle='--', alpha=0.5)

plt.show()
```

---

## 7️⃣ Histograms (히스토그램)

Histograms are used to show the distribution of data.

데이터의 분포를 보여줄 때 사용합니다.

### Basic Histogram (기본 히스토그램)

```python
import matplotlib.pyplot as plt
import random

# Data (test scores) (데이터 - 시험 점수)
random.seed(42)
scores = [random.randint(50, 100) for _ in range(100)]

# Draw histogram (히스토그램)
plt.hist(scores, bins=10, color='lightblue', edgecolor='black', alpha=0.7)

plt.title('Score Distribution', fontsize=16)
plt.xlabel('Score Range', fontsize=12)
plt.ylabel('Frequency', fontsize=12)
plt.grid(axis='y', alpha=0.5)

plt.show()
```

### Multiple Histograms (여러 개의 히스토그램)

```python
import matplotlib.pyplot as plt
import random

# Data (과목별 점수)
random.seed(42)
math_scores = [random.randint(60, 100) for _ in range(100)]
english_scores = [random.randint(50, 95) for _ in range(100)]

# Draw histograms (히스토그램)
plt.hist(math_scores, bins=10, alpha=0.6, label='Math', color='blue')
plt.hist(english_scores, bins=10, alpha=0.6, label='English', color='red')

plt.title('Score Distribution by Subject', fontsize=16)
plt.xlabel('Score Range', fontsize=12)
plt.ylabel('Frequency', fontsize=12)
plt.legend()
plt.grid(axis='y', alpha=0.5)

plt.show()
```

---

## 8️⃣ Multiple Graphs (여러 그래프)

You can display multiple graphs in one figure using subplot.

subplot을 사용하여 한 화면에 여러 그래프를 배치할 수 있습니다.

```python
import matplotlib.pyplot as plt
import numpy as np

# Create figure (Figure 생성)
plt.figure(figsize=(12, 8))

# Data (데이터)
x = np.linspace(0, 10, 100)
y1 = np.sin(x)
y2 = np.cos(x)
y3 = np.tan(x)

# First graph (첫 번째 그래프)
plt.subplot(2, 2, 1)
plt.plot(x, y1, color='blue')
plt.title('sin(x)')
plt.grid(True, alpha=0.3)

# Second graph (두 번째 그래프)
plt.subplot(2, 2, 2)
plt.plot(x, y2, color='red')
plt.title('cos(x)')
plt.grid(True, alpha=0.3)

# Third graph (세 번째 그래프)
plt.subplot(2, 2, 3)
plt.scatter(x, y1, alpha=0.5)
plt.title('sin(x) Scatter')
plt.grid(True, alpha=0.3)

# Fourth graph (네 번째 그래프)
plt.subplot(2, 2, 4)
plt.bar(range(10), [i**2 for i in range(10)], color='green')
plt.title('Square Numbers')
plt.grid(axis='y', alpha=0.3)

# Adjust spacing between graphs (그래프 간격 조정)
plt.tight_layout()
plt.show()
```

---

## 9️⃣ Practical Example: Visualizing CSV Data (실전 예제: CSV 데이터 시각화)

Let's read data from a CSV file and draw graphs.

CSV 파일의 데이터를 읽어서 그래프로 그려봅시다.

### Preparing Data File (데이터 파일 준비)

First, let's create a CSV file to visualize.

먼저 시각화할 CSV 파일을 만들어봅시다.

**Creating scores.csv file:**

Open a text editor and enter the following content, then save it as `scores.csv` (Encoding: UTF-8):

메모장을 열어 다음 내용을 입력하고 `scores.csv`로 저장하세요 (인코딩: UTF-8):

```
Name,Korean,English,Math
Kim Cheol-soo,85,90,78
Park Young-hee,92,88,95
Lee Min-soo,78,85,82
Choi Ji-eun,88,92,90
Jung Min-ho,95,78,88
```

💡 **File Structure:**

- Line 1: Column names (header)
- Lines 2-6: Each student's scores
- Comma-separated

파일 구조: 1행은 컬럼 이름(헤더), 2-6행은 각 학생의 점수, 쉼표로 구분

### Visualizing Student Grades (학생 성적 시각화)

```python
import matplotlib.pyplot as plt
import csv

# Read CSV file (CSV 파일 읽기)
students = []
with open('scores.csv', 'r', encoding='utf-8') as file:
    csv_reader = csv.DictReader(file)
    for row in csv_reader:
        students.append({
            'name': row['Name'],
            'korean': int(row['Korean']),
            'english': int(row['English']),
            'math': int(row['Math'])
        })

# Extract data (데이터 추출)
names = [s['name'] for s in students]
korean = [s['korean'] for s in students]
english = [s['english'] for s in students]
math = [s['math'] for s in students]

# Calculate average (평균 계산)
averages = [(s['korean'] + s['english'] + s['math']) / 3 for s in students]

# Create figure (Figure 생성)
plt.figure(figsize=(12, 10))

# 1. Score comparison by subject (grouped bar) (과목별 비교 - 그룹 막대)
plt.subplot(2, 2, 1)
x = range(len(names))
width = 0.25

plt.bar([i - width for i in x], korean, width, label='Korean', color='skyblue')
plt.bar([i for i in x], english, width, label='English', color='lightgreen')
plt.bar([i + width for i in x], math, width, label='Math', color='lightcoral')

plt.title('Score Comparison by Subject', fontsize=14)
plt.xlabel('Student', fontsize=11)
plt.ylabel('Score', fontsize=11)
plt.xticks(x, names, rotation=45)
plt.legend()
plt.grid(axis='y', alpha=0.3)

# 2. Average scores (line) (평균 점수 - 꺾은선)
plt.subplot(2, 2, 2)
plt.plot(names, averages, marker='o', linewidth=2, markersize=8, color='purple')
plt.title('Average Score by Student', fontsize=14)
plt.xlabel('Student', fontsize=11)
plt.ylabel('Average Score', fontsize=11)
plt.xticks(rotation=45)
plt.grid(True, alpha=0.3)

# 3. Average by subject (bar) (과목별 평균 - 막대)
plt.subplot(2, 2, 3)
subject_avg = [sum(korean)/len(korean), sum(english)/len(english), sum(math)/len(math)]
subjects = ['Korean', 'English', 'Math']
colors = ['skyblue', 'lightgreen', 'lightcoral']

plt.bar(subjects, subject_avg, color=colors)
plt.title('Average Score by Subject', fontsize=14)
plt.ylabel('Average Score', fontsize=11)

for i, v in enumerate(subject_avg):
    plt.text(i, v + 1, f'{v:.1f}', ha='center', fontsize=10)

plt.grid(axis='y', alpha=0.3)

# 4. Score distribution (histogram) (점수 분포 - 히스토그램)
plt.subplot(2, 2, 4)
all_scores = korean + english + math
plt.hist(all_scores, bins=10, color='lightblue', edgecolor='black', alpha=0.7)
plt.title('Overall Score Distribution', fontsize=14)
plt.xlabel('Score Range', fontsize=11)
plt.ylabel('Frequency', fontsize=11)
plt.grid(axis='y', alpha=0.3)

plt.tight_layout()
plt.show()
```

---

## 🔟 Saving Graphs (그래프 저장하기)

You can save the graph you drew as an image file.

그린 그래프를 이미지 파일로 저장할 수 있습니다.

```python
import matplotlib.pyplot as plt

# Draw graph (그래프 그리기)
x = [1, 2, 3, 4, 5]
y = [2, 4, 6, 8, 10]

plt.plot(x, y, marker='o')
plt.title('Sample Graph')
plt.xlabel('X Axis')
plt.ylabel('Y Axis')
plt.grid(True)

# Save to file (파일로 저장)
plt.savefig('graph.png', dpi=300, bbox_inches='tight')
print("✓ Saved as graph.png!")

# Display on screen (화면에 표시)
plt.show()
```

**Key Options:**

- `dpi`: Resolution (default 100, high resolution is 300)
- `bbox_inches='tight'`: Minimize margins
- Supported formats: png, jpg, pdf, svg, etc.

---

## 📝 Key Concepts Summary (핵심 개념 정리)

### Basic Structure (기본 구조)

```python
import matplotlib.pyplot as plt

plt.plot(x, y)           # Draw graph (그래프 그리기)
plt.title('Title')
plt.xlabel('X Axis')
plt.ylabel('Y Axis')
plt.grid(True)
plt.legend()
plt.show()               # Display on screen (화면에 표시)
```

### Main Graph Types (주요 그래프)

- `plt.plot()`: Line graph (꺾은선 그래프)
- `plt.bar()`: Bar chart (막대 그래프)
- `plt.barh()`: Horizontal bar chart (가로 막대 그래프)
- `plt.pie()`: Pie chart (원 그래프)
- `plt.scatter()`: Scatter plot (산점도)
- `plt.hist()`: Histogram (히스토그램)

### Korean Font Setting (한글 설정)

```python
plt.rcParams['font.family'] = 'Malgun Gothic'
plt.rcParams['axes.unicode_minus'] = False
```

### Subplot (여러 그래프)

```python
plt.subplot(rows, columns, number)
```

---

## 💡 Practice Assignments (실습 과제)

### Assignment 1: Weather Data Visualization (과제 1: 월별 날씨 데이터 시각화)

**Objective**: Read a year's worth of weather data and visualize it as graphs.

목표: 1년간의 날씨 데이터를 읽어 그래프로 시각화

**Step 1: Prepare Data File (1단계: 데이터 파일 준비)**

Create a `weather.csv` file:

`weather.csv` 파일을 만드세요:

```
Month,Average Temp,Rainfall
1,2.5,20
2,4.8,25
3,10.2,45
4,15.8,60
5,20.5,80
6,24.3,120
7,27.8,250
8,28.5,230
9,23.7,140
10,17.2,50
11,10.8,40
12,4.5,25
```

💡 **Column Description:**

- **Month**: 1-12
- **Average Temp**: Average temperature (°C)
- **Rainfall**: Total rainfall (mm)

컬럼 설명: 월(1-12), 평균기온(해당 월 평균 온도 °C), 강수량(해당 월 총 강수량 mm)

**Step 2: Requirements (2단계: 요구사항)**

Arrange the following 2 graphs with subplot:

다음 2개의 그래프를 subplot으로 배치하세요:

1. **Average Temperature Graph** (Line)

   - X-axis: Month (1-12)
   - Y-axis: Average Temperature (°C)
   - Line color: Red
   - Marker: Circle
   - Show grid
2. **Rainfall Graph** (Bar)

   - X-axis: Month (1-12)
   - Y-axis: Rainfall (mm)
   - Bar color: Blue
   - Show grid

**Step 3: Additional Features (3단계: 추가 기능)**

- Overall title: "2024 Monthly Weather Statistics"
- Print the hottest month and the month with the most rainfall
- Save the graph as `weather_chart.png`

**Hint:**

```python
import matplotlib.pyplot as plt
import csv

# 1. Read CSV (CSV 읽기)
months = []
temps = []
rain = []

with open('weather.csv', 'r', encoding='utf-8') as file:
    csv_reader = csv.DictReader(file)
    for row in csv_reader:
        months.append(int(row['Month']))
        temps.append(float(row['Average Temp']))
        rain.append(int(row['Rainfall']))

# 2. Draw graphs (그래프 그리기)
plt.figure(figsize=(12, 5))

# 2-1. Temperature graph
plt.subplot(1, 2, 1)
plt.plot(months, temps, marker='o', color='red', linewidth=2)
# ...

# 2-2. Rainfall graph
plt.subplot(1, 2, 2)
plt.bar(months, rain, color='blue')
# ...

# 3. Find maximum values (최댓값 찾기)
max_temp_idx = temps.index(max(temps))
max_rain_idx = rain.index(max(rain))
print(f"Hottest month: {months[max_temp_idx]} ({temps[max_temp_idx]}°C)")
print(f"Maximum rainfall: {months[max_rain_idx]} ({rain[max_rain_idx]}mm)")

# 4. Save (저장)
plt.tight_layout()
plt.savefig('weather_chart.png', dpi=300)
plt.show()
```

**Expected Output:**

```
Hottest month: 8 (28.5°C)
Maximum rainfall: 7 (250mm)
✓ Graph saved as weather_chart.png.
```

---

### Assignment 2: Survey Results Visualization (과제 2: 설문조사 결과 시각화)

**Objective**: Express survey results using various graphs.

목표: 설문조사 결과를 다양한 그래프로 표현

**Step 1: Prepare Data File (1단계: 데이터 파일 준비)**

Create a `survey.csv` file:

`survey.csv` 파일을 만드세요:

```
Name,Age,Gender,Satisfaction
Kim Cheol-soo,25,M,5
Park Young-hee,30,F,4
Lee Min-soo,28,M,5
Choi Ji-eun,22,F,3
Jung Min-ho,35,M,4
Kang Su-jin,27,F,5
Lee Ha-neul,24,M,4
Park Seo-yeon,29,F,5
Yoon Dong-hyuk,26,M,3
Han Ji-min,31,F,4
```

💡 **Column Description:**

- **Age**: Respondent age
- **Gender**: M/F
- **Satisfaction**: 1-5 points (5 is highest)

컬럼 설명: 나이(응답자 나이), 성별(남/여), 만족도(1-5점, 5점이 가장 높음)

**Step 2: Requirements (2단계: 요구사항)**

Draw the following 4 graphs with 2x2 layout:

2x2 레이아웃으로 다음 4개 그래프를 그리세요:

1. **Age Group Distribution** (Bar chart)

   - Divide into 20s and 30s
   - X-axis: Age group, Y-axis: Number of people
2. **Gender Distribution** (Pie chart)

   - Ratio of men to women
   - Show percentage
3. **Satisfaction Distribution** (Bar chart)

   - X-axis: Satisfaction (1-5), Y-axis: Number of respondents
   - Different color for each satisfaction level
4. **Age vs Satisfaction Relationship** (Scatter plot)

   - X-axis: Age, Y-axis: Satisfaction
   - Show men/women in different colors

**Step 3: Print Statistics (3단계: 통계 출력)**

```
====================================
📊 Survey Analysis Results
====================================
Total respondents: 10 people
Average age: 27.7 years
Average satisfaction: 4.2/5.0

Gender distribution:
  Male: 5 people (50.0%)
  Female: 5 people (50.0%)

By age group:
  20s: 8 people
  30s: 2 people
====================================
```

**Hint:**

```python
# Divide age groups (연령대 구분)
age_20s = sum(1 for age in ages if 20 <= age < 30)
age_30s = sum(1 for age in ages if 30 <= age < 40)

# Count by gender (성별 카운트)
from collections import Counter
gender_count = Counter(genders)

# Count by satisfaction (만족도별 카운트)
satisfaction_count = Counter(satisfactions)

# Scatter plot by gender (산점도 - 성별로 분리)
male_ages = [ages[i] for i in range(len(ages)) if genders[i] == 'M']
male_sats = [satisfactions[i] for i in range(len(satisfactions)) if genders[i] == 'M']
# Do the same for females...

plt.scatter(male_ages, male_sats, label='Male', color='blue', s=100)
plt.scatter(female_ages, female_sats, label='Female', color='red', s=100)
```

---

## ✅ Quiz

### [Beginner] Question 1

What is the Python library used to draw graphs?

그래프를 그리는 파이썬 라이브러리는?

1. NumPy
2. Matplotlib
3. Pandas
4. TensorFlow

### [Intermediate] Question 2

What is the function to draw a bar chart?

막대 그래프를 그리는 함수는?

1. plt.line()
2. plt.bar()
3. plt.draw()
4. plt.graph()

### [Intermediate] Question 3

What is the function to display the graph on screen?

그래프를 화면에 표시하는 함수는?

1. plt.display()
2. plt.print()
3. plt.show()
4. plt.view()

### [Advanced] Question 4

What is the function to arrange multiple graphs on one screen?

한 화면에 여러 그래프를 배치하는 함수는?

1. plt.arrange()
2. plt.subplot()
3. plt.layout()
4. plt.grid()

### [Advanced] Question 5

What is the function to save the graph as a file?

그래프를 파일로 저장하는 함수는?

1. plt.save()
2. plt.export()
3. plt.savefig()
4. plt.output()

---

## 🔑 Quiz Answers and Explanations (퀴즈 정답 및 해설)

**Answer 1: 2**

Matplotlib is the most widely used library in Python for drawing graphs. It provides various functions to create line graphs, bar charts, pie charts, and more.

Matplotlib은 파이썬에서 그래프를 그릴 때 가장 많이 사용되는 라이브러리입니다. 선 그래프, 막대 그래프, 원 그래프 등 다양한 함수를 제공합니다.

---

**Answer 2: 2**

The `plt.bar()` function is used to draw a bar chart. You specify the x-axis data and y-axis data as parameters.

`plt.bar()` 함수는 막대 그래프를 그릴 때 사용합니다. 매개변수로 x축 데이터와 y축 데이터를 지정합니다.

---

**Answer 3: 3**

The `plt.show()` function displays the graph on the screen. Without this function, the graph will not be visible.

`plt.show()` 함수는 그래프를 화면에 표시합니다. 이 함수가 없으면 그래프가 화면에 나타나지 않습니다.

---

**Answer 4: 2**

The `plt.subplot()` function allows you to arrange multiple graphs on one screen. You specify the number of rows, columns, and the position number.

`plt.subplot()` 함수를 사용하면 한 화면에 여러 그래프를 배치할 수 있습니다. 행 개수, 열 개수, 위치 번호를 지정합니다.

---

**Answer 5: 3**

The `plt.savefig()` function saves the graph as an image file. You can specify the filename, resolution (dpi), and format.

`plt.savefig()` 함수는 그래프를 이미지 파일로 저장합니다. 파일명, 해상도(dpi), 형식 등을 지정할 수 있습니다.

---

## 🎯 Next Chapter Preview (다음 장 예고)

In the next chapter, you will learn about web scraping. You will discover how to automatically collect data from websites and process it.

다음 장에서는 웹 스크래핑을 배웁니다. 웹사이트에서 데이터를 자동으로 수집하는 방법을 학습합니다!

---

Thank you for your attention.

Prof. Cho Jeonghyun (peterchokr@gmail.com)
Yeungnam University College
