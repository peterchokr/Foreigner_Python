# Chapter 22. CSV Files and Data Analysis

---

## 📚 Learning Objectives

After completing this chapter, you will be able to read and write CSV files, analyze and process data. You'll learn how to handle table-formatted data like Excel in Python and apply it in practice.

이번 장을 마치면 여러분은 CSV 파일을 읽고 쓰며, 데이터를 분석하고 처리할 수 있습니다. 엑셀 같은 표 형태의 데이터를 파이썬으로 다루는 방법을 익혀 실무에서 활용할 수 있게 됩니다.

---

## 1️⃣ What is CSV? (CSV 파일이란?)

CSV stands for **Comma-Separated Values**, a file format for storing values separated by commas.

CSV는 **Comma-Separated Values**의 약자로, 쉼표로 구분된 값들을 저장하는 파일 형식입니다.

### Why Learn CSV? (왜 CSV를 배워야 할까?)

Excel, which we commonly use, can also be saved as a CSV file. CSV is one of the most commonly used formats for exchanging data!

우리가 흔히 사용하는 엑셀도 CSV 파일로 저장할 수 있습니다. CSV는 데이터를 주고받을 때 가장 많이 사용되는 형식 중 하나입니다!

```
What CSV file looks like (CSV 파일의 모습)

Name,Age,Job
John Smith,25,Developer
Sarah Davis,30,Designer
Michael Johnson,28,Planner

↓ Opens in Excel (엑셀에서 열면)

┌─────────────┬──────┬──────────────┐
│    Name     │ Age  │      Job     │
├─────────────┼──────┼──────────────┤
│ John Smith│  25  │  Developer   │
│ Sarah Davis│  30  │  Designer    │
│ Michael Johnson │  28  │  Planner     │
└─────────────┴──────┴──────────────┘
```

### Features of CSV (CSV의 특징)

**Advantages (장점):**

- ✅ Simple text format (can open with notepad) (간단한 텍스트 형식 - 메모장으로 열 수 있음)
- ✅ Opens directly in Excel, Google Sheets (엑셀, 구글 시트에서 바로 열림)
- ✅ Small file size (용량이 작음)
- ✅ Supported by all programming languages (모든 프로그래밍 언어에서 지원)

**Disadvantages (단점):**

- ❌ Formatting not saved (text color, cell merge, etc.) (글자 색, 셀 병합 등 서식 저장 안 됨)
- ❌ Can only save one sheet (하나의 시트만 저장 가능)

### Real-World Examples (실생활 사용 예시)

```
🏢 In Companies (회사에서)
- Employee list (직원 명단)
- Sales data (매출 데이터)
- Customer list (고객 목록)

📊 Data Analysis (데이터 분석)
- Survey results (설문조사 결과)
- Experiment data (실험 데이터)
- Statistical data (통계 자료)

🛒 E-commerce (전자상거래)
- Product list (상품 목록)
- Order history (주문 내역)
- Inventory status (재고 현황)
```

---

## 2️⃣ Reading CSV Files - Basic (CSV 파일 읽기 - 기본)

The simplest way to read a CSV file.

CSV 파일을 읽는 가장 간단한 방법입니다.

### Import csv module (csv 모듈 import)

```python
import csv
```

It comes with Python by default, so no separate installation is needed!

파이썬에 기본으로 포함되어 있어 별도 설치가 필요 없습니다!

### Creating a CSV file for practice (실습용 CSV 파일 만들기)

First, let's create a CSV file to use for practice. Open a notepad or text editor and enter the following content, then save it as `students.csv`.

먼저 실습에 사용할 CSV 파일을 만들어봅시다. 메모장이나 텍스트 에디터를 열어서 다음 내용을 입력하고 `students.csv`로 저장하세요.

**students.csv file contents (파일 내용):**

```
Name,Age,Grade
John Smith,20,2
Sarah Davis,21,3
Michael Johnson,19,1
```

💡 **How to create a CSV file (CSV 파일 만드는 법):**

1. Open Notepad (Windows) or Text Editor (Mac) (메모장/텍스트편집기 열기)
2. Enter the above content (separated by commas) (위 내용 입력)
3. File > Save As → Filename: `students.csv` → Encoding: UTF-8
4. Save in the same folder as Python file (같은 폴더에 저장)

Or in Excel (또는 엑셀에서):

1. Enter the above content in Excel (엑셀에 입력)
2. File > Save As → File format: CSV (Comma-delimited)

### Reading CSV File - As List (CSV 파일 읽기 - 리스트로)

```python
import csv

# Open CSV file (CSV 파일 열기)
with open('students.csv', 'r', encoding='utf-8') as file:
    # Create CSV reader (CSV 리더 생성)
    csv_reader = csv.reader(file)
  
    # Read line by line (한 줄씩 읽기)
    for row in csv_reader:
        print(row)
```

**Execution result (실행 결과):**

```
['Name', 'Age', 'Grade']
['John Smith', '20', '2']
['Sarah Davis', '21', '3']
['Michael Johnson', '19', '1']
```

Each line is returned as a list!

각 줄이 리스트로 반환됩니다!

### Skipping the first row (header) (첫 줄(헤더) 건너뛰기)

When you want to skip the first line, which is usually a column name (컬럼 이름):

첫 줄은 보통 컬럼 이름이므로 건너뛰고 싶을 때:

```python
import csv

with open('students.csv', 'r', encoding='utf-8') as file:
    csv_reader = csv.reader(file)
  
    # Skip first line (첫 줄 건너뛰기)
    next(csv_reader)
  
    # Read only data (데이터만 읽기)
    for row in csv_reader:
        print(f"Name: {row[0]}, Age: {row[1]}, Grade: {row[2]}")
```

**Execution result (실행 결과):**

```
Name: John Smith, Age: 20, Grade: 2
Name: Sarah Davis, Age: 21, Grade: 3
Name: Michael Johnson, Age: 19, Grade: 1
```

---

## 3️⃣ Reading CSV Files - As Dictionary (CSV 파일 읽기 - 딕셔너리로)

Use `DictReader` if you want to access by column name!

컬럼 이름으로 접근하고 싶다면 `DictReader`를 사용합니다!

### Using DictReader (DictReader 사용법)

```python
import csv

with open('students.csv', 'r', encoding='utf-8') as file:
    # Create DictReader (first line automatically recognized as header) (DictReader 생성)
    csv_reader = csv.DictReader(file)
  
    for row in csv_reader:
        # Access by column name like a dictionary! (딕셔너리처럼 접근)
        print(f"Name: {row['Name']}, Age: {row['Age']}, Grade: {row['Grade']}")
```

**Execution result (실행 결과):**

```
Name: John Smith, Age: 20, Grade: 2
Name: Sarah Davis, Age: 21, Grade: 3
Name: Michael Johnson, Age: 19, Grade: 1
```

💡 **DictReader Advantages**: You can access by column name (`row['Name']`) instead of index (`row[0]`), making the code easier to read!

💡 **DictReader의 장점**: 인덱스(`row[0]`) 대신 컬럼 이름(`row['Name']`)으로 접근할 수 있어 코드가 읽기 쉽습니다!

### Saving Data as List (데이터 리스트로 저장하기)

```python
import csv

students = []  # Create empty list (빈 리스트 생성)

with open('students.csv', 'r', encoding='utf-8') as file:
    csv_reader = csv.DictReader(file)
  
    for row in csv_reader:
        # Add dictionary to list (딕셔너리를 리스트에 추가)
        student = {
            'Name': row['Name'],
            'Age': int(row['Age']),  # Convert to number (숫자로 변환)
            'Grade': int(row['Grade'])
        }
        students.append(student)

# Check saved data (저장된 데이터 확인)
print(f"Total {len(students)} students")
for student in students:
    print(student)
```

---

## 4️⃣ Writing CSV Files (CSV 파일 쓰기)

You can create a new CSV file or save data.

새로운 CSV 파일을 만들거나 데이터를 저장할 수 있습니다.

### Basic Writing (기본 쓰기)

```python
import csv

# Data to save (저장할 데이터)
students = [
    ['Name', 'Age', 'Grade'],  # Header
    ['Robert Taylor', 22, 2],
    ['Jennifer Anderson', 20, 1],
    ['David Thomas', 23, 3]
]

# Write to CSV file (CSV 파일에 쓰기)
with open('new_students.csv', 'w', newline='', encoding='utf-8') as file:
    csv_writer = csv.writer(file)
  
    # Write all rows (모든 행 쓰기)
    csv_writer.writerows(students)

print("File saved!")
```

💡 **Note**: You must use `newline=''`! Without it, blank lines are created.

💡 **주의**: `newline=''`을 꼭 써야 합니다!

### Writing with DictWriter (DictWriter로 쓰기)

```python
import csv

# Data to save (dictionary list) (저장할 데이터)
students = [
    {'Name': 'Robert Taylor', 'Age': 22, 'Grade': 2},
    {'Name': 'Jennifer Anderson', 'Age': 20, 'Grade': 1},
    {'Name': 'David Thomas', 'Age': 23, 'Grade': 3}
]

# Write to CSV file (CSV 파일에 쓰기)
with open('students_dict.csv', 'w', newline='', encoding='utf-8') as file:
    # Specify column names (컬럼 이름 지정)
    fieldnames = ['Name', 'Age', 'Grade']
  
    csv_writer = csv.DictWriter(file, fieldnames=fieldnames)
  
    # Write header (헤더 쓰기)
    csv_writer.writeheader()
  
    # Write data (데이터 쓰기)
    csv_writer.writerows(students)

print("File saved!")
```

---

## 5️⃣ Basics of Data Analysis (데이터 분석 기초)

Let's read the data from the CSV file and do some simple analysis.

CSV 파일의 데이터를 읽어서 간단한 분석을 해봅시다.

### Example Data Preparation (예제 데이터 준비)

First, let's create a CSV file with grade data.

먼저 성적 데이터가 담긴 CSV 파일을 만들어봅시다.

**Creating scores.csv file (scores.csv 파일 만들기):**

Open a notepad or text editor and enter the following content, then save it as `scores.csv`.

메모장이나 텍스트 에디터를 열어서 다음 내용을 입력하고 `scores.csv`로 저장하세요.

**scores.csv file contents (파일 내용):**

```
Name,Korean,English,Math
John Smith,85,90,78
Sarah Davis,92,88,95
Michael Johnson,78,85,82
Emily Wilson,88,92,90
James Brown,95,78,88
```

💡 **File structure explanation (파일 구조 설명):**

- **Row 1 (Header)**: Column names (Name, Korean, English, Math) (컬럼 이름)
- **Rows 2-6 (Data)**: Each student's subject scores (각 학생의 과목별 점수)
- Separated by comma (`,`) (쉼표로 구분)
- Encoding: UTF-8 (UTF-8로 저장)

**How to create in Excel (엑셀에서 만드는 방법):**

```
┌─────────────┬────────┬────────┬────────┐
│    Name     │ Korean │ English│  Math  │
├─────────────┼────────┼────────┼────────┤
│ John Smith│   85   │   90   │   78   │
│ Sarah Davis│   92   │   88   │   95   │
│ Michael Johnson │   78   │   85   │   82   │
│ Emily Wilson │   88   │   92   │   90   │
│ James Brown │   95   │   78   │   88   │
└─────────────┴────────┴────────┴────────┘

↓ "File > Save As"
↓ "File format: CSV (Comma-delimited)"
```

### Calculating Average (평균 계산)

```python
import csv

# Read data (데이터 읽기)
students = []
with open('scores.csv', 'r', encoding='utf-8') as file:
    csv_reader = csv.DictReader(file)
    for row in csv_reader:
        students.append({
            'Name': row['Name'],
            'Korean': int(row['Korean']),
            'English': int(row['English']),
            'Math': int(row['Math'])
        })

# Calculate average for each student (각 학생의 평균 계산)
print("=" * 50)
print("Average by Student")
print("=" * 50)

for student in students:
    average = (student['Korean'] + student['English'] + student['Math']) / 3
    print(f"{student['Name']:15} : {average:.1f} points")

# Calculate average by subject (과목별 평균 계산)
print("\n" + "=" * 50)
print("Average by Subject")
print("=" * 50)

korean_total = sum(s['Korean'] for s in students)
english_total = sum(s['English'] for s in students)
math_total = sum(s['Math'] for s in students)

count = len(students)

print(f"Korean average: {korean_total / count:.1f} points")
print(f"English average: {english_total / count:.1f} points")
print(f"Math average: {math_total / count:.1f} points")
```

**Execution result (실행 결과):**

```
==================================================
Average by Student
==================================================
John Smith      : 84.3 points
Sarah Davis    : 91.7 points
Michael Johnson       : 81.7 points
Emily Wilson       : 90.0 points
James Brown       : 87.0 points

==================================================
Average by Subject
==================================================
Korean average: 87.6 points
English average: 86.6 points
Math average: 86.6 points
```

### Finding Highest and Lowest Scores (최고점, 최저점 찾기)

```python
import csv

# Read data (데이터 읽기)
students = []
with open('scores.csv', 'r', encoding='utf-8') as file:
    csv_reader = csv.DictReader(file)
    for row in csv_reader:
        students.append({
            'Name': row['Name'],
            'Korean': int(row['Korean']),
            'English': int(row['English']),
            'Math': int(row['Math'])
        })

# Calculate total score for each student (각 학생의 총점 계산)
for student in students:
    student['Total'] = student['Korean'] + student['English'] + student['Math']

# Sort by total score (총점 순으로 정렬)
students.sort(key=lambda x: x['Total'], reverse=True)

# Display result (결과 출력)
print("=" * 60)
print("Grade Report (Sorted by Total Score)")
print("=" * 60)
print(f"{'Rank':^4} {'Name':^10} {'Korean':^8} {'English':^8} {'Math':^8} {'Total':^8}")
print("-" * 60)

for rank, student in enumerate(students, 1):
    print(f"{rank:^4} {student['Name']:^10} {student['Korean']:^8} {student['English']:^8} {student['Math']:^8} {student['Total']:^8}")

print("=" * 60)
print(f"\n🥇 1st Place: {students[0]['Name']} ({students[0]['Total']} points)")
print(f"🥈 2nd Place: {students[1]['Name']} ({students[1]['Total']} points)")
print(f"🥉 3rd Place: {students[2]['Name']} ({students[2]['Total']} points)")
```

---

## 📝 Key Concepts Summary (핵심 개념 정리)

### Reading CSV (CSV 읽기)

```python
import csv

# Read as list (리스트로 읽기)
with open('file.csv', 'r', encoding='utf-8') as file:
    csv_reader = csv.reader(file)
    for row in csv_reader:
        print(row)

# Read as dictionary (딕셔너리로 읽기)
with open('file.csv', 'r', encoding='utf-8') as file:
    csv_reader = csv.DictReader(file)
    for row in csv_reader:
        print(row['Column Name'])
```

### Writing CSV (CSV 쓰기)

```python
# Write as list (리스트로 쓰기)
with open('file.csv', 'w', newline='', encoding='utf-8') as file:
    csv_writer = csv.writer(file)
    csv_writer.writerows(data)

# Write as dictionary (딕셔너리로 쓰기)
with open('file.csv', 'w', newline='', encoding='utf-8') as file:
    csv_writer = csv.DictWriter(file, fieldnames=['Column1', 'Column2'])
    csv_writer.writeheader()
    csv_writer.writerows(data)
```

### Important Notes (주의사항)

- `encoding='utf-8'` required (prevents Korean character corruption) (한글 깨짐 방지)
- `newline=''` required (prevents blank lines) (빈 줄 방지)
- Numbers are read as strings → Need `int()`, `float()` conversion (숫자는 문자로 읽힘 → 변환 필요)

---

## 💡 Practice Assignments (실습 과제)

### Assignment 1: Grade Management Program (성적 관리 프로그램)

**Goal**: Read CSV file, analyze grades, assign grades, and save to new file

**목표**: CSV 파일을 읽어 성적을 분석하고 등급을 부여한 후 새 파일로 저장

**Step 1: Prepare data file (데이터 파일 준비)**

Create `students.csv` file:

```
Name,Korean,English,Math
Robert Taylor,85,90,75
Jennifer Anderson,92,88,95
David Thomas,78,82,80
Jessica Chen,95,87,92
Christopher Lee,88,78,85
```

**Step 2: Requirements (요구사항)**

Implement the following features:

1. **Calculate average**: Calculate average of 3 subjects for each student
2. **Assign grades**:
   - 90 or higher: A
   - 80 or higher: B
   - 70 or higher: C
   - 60 or higher: D
   - Below 60: F
3. **Calculate rank**: Assign rank by average score
4. **Save result**: Save to `result.csv` (include name, Korean, English, Math, average, grade, rank)

**Step 3: Output example (출력 예시)**

```
====================================
Grade Report
====================================
Name          Korean  English  Math  Average  Grade
------------------------------------
Robert Taylor    85      90      75    83.3     B
Jennifer Anderson   92      88      95    91.7     A
...
====================================

✓ Result has been saved to result.csv.
```

**Hint:**

```python
# 1. Read data and calculate average (데이터 읽고 평균 계산)
for student in students:
    student['Average'] = (student['Korean'] + student['English'] + student['Math']) / 3

# 2. Assign grade (등급 부여)
def get_grade(average):
    if average >= 90:
        return 'A'
    elif average >= 80:
        return 'B'
    # ...

# 3. Sort and assign rank (정렬 후 석차)
students.sort(key=lambda x: x['Average'], reverse=True)
for rank, student in enumerate(students, 1):
    student['Rank'] = rank
```

---

### Assignment 2: Product Inventory Management (상품 재고 관리)

**Goal**: Analyze product inventory and display warning messages

**목표**: 상품 재고를 분석하고 경고 메시지 출력

**Step 1: Prepare data file (데이터 파일 준비)**

Create `products.csv` file:

```
Product Name,Stock,Price
Laptop,5,1500000
Mouse,3,30000
Keyboard,15,120000
Monitor,2,350000
Webcam,8,80000
```

**Step 2: Requirements (요구사항)**

Display the following information:

1. **Product list**: Display product name, stock, price
2. **Low stock warning**: Display products with stock of 5 or less
3. **Total inventory value**: Sum of (stock × price) for all products
4. **Most expensive product**: Product with highest price
5. **Sorted by stock**: Sort by stock and save to `inventory_sorted.csv`

**Step 3: Output example (출력 예시)**

```
====================================
📦 Inventory Status
====================================
Product Name        Stock    Price
------------------------------------
Laptop               5pcs    1,500,000 won
Mouse                3pcs       30,000 won
...

⚠️  Low Stock Warning!
------------------------------------
Mouse: 3pcs (Urgent order needed)
Monitor: 2pcs (Urgent order needed)

💰 Total Inventory Value: 10,290,000 won

⭐ Most Expensive Product: Laptop (1,500,000 won)

✓ Sorted inventory list has been saved to inventory_sorted.csv.
```

**Hint:**

```python
# 1. Find low stock products (재고 부족 상품 찾기)
low_stock = [p for p in products if p['Stock'] <= 5]

# 2. Total inventory value (총 재고 가치)
total_value = sum(p['Stock'] * p['Price'] for p in products)

# 3. Most expensive product (가장 비싼 상품)
most_expensive = max(products, key=lambda x: x['Price'])

# 4. Sort by stock (재고 순 정렬)
products.sort(key=lambda x: x['Stock'], reverse=True)
```

---

## ✅ Quiz (퀴즈)

### [Beginner] Question 1

What module is used to read CSV files?

### [Intermediate] Question 2

What class is used to read CSV as a dictionary?

### [Intermediate] Question 3

What is an essential option when writing to CSV file?

### [Advanced] Question 4

What function is used to skip the first line of CSV file?

### [Advanced] Question 5

What mode is used to add data to an existing CSV file?

---

## 🔑 Quiz Answers (퀴즈 정답)

**Question 1**: csv

**Question 2**: DictReader

**Question 3**: newline='', encoding='utf-8'

**Question 4**: next()

**Question 5**: 'a' (append mode)

---

## 🎯 Next Chapter Preview (다음 장 예고)

Next chapter, we will learn data visualization using Matplotlib. We'll learn how to read CSV data and display it as graphs for easier understanding!

다음 장에서는 Matplotlib을 사용한 데이터 시각화를 배웁니다. CSV 데이터를 읽어 그래프로 만들어 보기 쉽게 표현하는 방법을 학습합니다!

---

Thank you for your attention.  
Cho Jeonghyun ([peterchokr@gmail.com](mailto:peterchokr@gmail.com)). Yeungnam University College

"Produced in collaboration with Claude and Gemini."
