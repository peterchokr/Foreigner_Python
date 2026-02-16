# Chapter 22: CSV Files and Data Analysis — Practice Problems

---

## 📝 Multiple Choice Questions

---

### 🟢 Beginner

**Problem 1.** What does CSV stand for?

① Comma-Separated Variables  
② **Comma-Separated Values**  
③ Character-Separated Values  
④ Column-Separated Variables  

---

**Problem 2.** What is the Python standard module for reading CSV files?

① `pandas`  
② `json`  
③ `csv`  
④ `excel`  

---

**Problem 3.** What is the correct code to read CSV file as list?

① `csv.read(file)`  
② `csv.reader(file)`  
③ `csv.load(file)`  
④ `csv.open(file)`  

---

**Problem 4.** What option prevents blank lines when writing CSV?

① `encoding='utf-8'`  
② `mode='w'`  
③ `newline=''`  
④ `strip=True`  

---

**Problem 5.** What function skips the header line (first row) in CSV?

① `skip()`  
② `next()`  
③ `pass()`  
④ `header()`  

---

**Problem 6.** What is NOT an advantage of CSV files?

① Simple text format  
② Supported by all programming languages  
③ Small file size  
④ **Can save formatting like cell colors and merging**  

---

**Problem 7.** What option prevents Korean characters from being corrupted in CSV?

① `newline=''`  
② `encoding='utf-8'`  
③ `mode='r'`  
④ `delimiter=','`  

---

### 🟡 Intermediate

**Problem 8.** What class is used to access CSV data by column name?

① `csv.reader`  
② `csv.DictReader`  
③ `csv.NameReader`  
④ `csv.HeaderReader`  

---

**Problem 9.** What method writes header to file in `csv.DictWriter`?

① `write_header()`  
② `writeheader()`  
③ `add_header()`  
④ `insert_header()`  

---

**Problem 10.** What is the correct result of this code?

```python
import csv

with open('data.csv', 'r', encoding='utf-8') as file:
    reader = csv.reader(file)
    for row in reader:
        print(type(row))
        break
```

(data.csv: `Name,Age,Grade`)

① `<class 'dict'>`  
② `<class 'str'>`  
③ `<class 'list'>`  
④ `<class 'tuple'>`  

---

**Problem 11.** What file mode appends data to existing CSV file?

① `'w'`  
② `'r'`  
③ `'a'`  
④ `'x'`  

---

**Problem 12.** What option reads tab-separated TSV file?

① `separator='\t'`  
② `delimiter='\t'`  
③ `split='\t'`  
④ `divider='\t'`  

---

### 🔴 Advanced

**Problem 13.** What does this code do?

```python
import csv

data = [
    {'Name': 'John', 'Score': 85},
    {'Name': 'Jane', 'Score': 92}
]

with open('test.csv', 'w', newline='', encoding='utf-8') as f:
    writer = csv.DictWriter(f, fieldnames=['Name', 'Score'])
    writer.writeheader()
    writer.writerows(data)
```

① Reads CSV file  
② **Writes CSV file with headers and data rows**  
③ Creates new CSV reader  
④ Deletes CSV file  

---

**Problem 14.** How to read CSV file and get sum of numeric column?

```python
total = 0
with open('sales.csv', 'r') as f:
    reader = csv.DictReader(f)
    for row in reader:
        total += float(row['Amount'])
```

① Only reads first row  
② **Sums all values in Amount column**  
③ Converts all values to float  
④ Writes to new file  

---

**Problem 15.** What is the difference between csv.reader and csv.DictReader?

① No difference  
② `csv.reader` returns list, `csv.DictReader` returns dict  
③ Only one can write files  
④ `csv.DictReader` is slower  

---

## 📝 Short Answer Questions

---

### 🟢 Beginner

**Problem 16.** Explain what CSV is and give advantages/disadvantages.

---

**Problem 17.** What are the differences between `newline=''` and `encoding='utf-8'`?

---

**Problem 18.** Explain the purpose of `next()` function in CSV reading.

---

### 🟡 Intermediate

**Problem 19.** Explain the difference between csv.reader and csv.DictReader with code examples.

```python
# csv.reader
with open('file.csv', 'r') as f:
    reader = csv.reader(f)
    for row in reader:
        print(row)  # List

# csv.DictReader
with open('file.csv', 'r') as f:
    reader = csv.DictReader(f)
    for row in reader:
        print(row)  # Dictionary
```

---

**Problem 20.** How to write CSV file without getting blank rows?

---

### 🔴 Advanced

**Problem 21.** Write code to read CSV, calculate statistics, and write results to new file.

```python
import csv

data = []
with open('scores.csv', 'r') as f:
    reader = csv.DictReader(f)
    for row in reader:
        data.append(float(row['Score']))

average = sum(data) / len(data)
highest = max(data)
lowest = min(data)

with open('statistics.csv', 'w', newline='') as f:
    writer = csv.DictWriter(f, fieldnames=['Metric', 'Value'])
    writer.writeheader()
    writer.writerows([
        {'Metric': 'Average', 'Value': average},
        {'Metric': 'Highest', 'Value': highest},
        {'Metric': 'Lowest', 'Value': lowest}
    ])
```

---

## 💻 Hands-On Problems

---

### 🟢 Beginner

**Problem 22.** Create a simple CSV file and read it.

> Write data to CSV file, then read and display.

Output example:

```
=== CSV File Demo ===
File: students.csv
Data:
Name,Age,Grade
John,20,A
Jane,21,B
Mike,19,C
```

---

**Problem 23.** Write student data to CSV file.

> Create CSV with student information.

Output example:

```
=== Write CSV ===
Student 1: John, 20, A
Student 2: Jane, 21, B
Student 3: Mike, 19, C
File saved: students.csv
```

---

### 🟡 Intermediate

**Problem 24.** Read CSV and calculate statistics.

> Read scores from CSV, calculate average, max, min.

Output example:

```
=== Score Statistics ===
File: scores.csv
Scores: [85, 92, 78, 88, 95]
Average: 87.6
Highest: 95
Lowest: 78
```

---

**Problem 25.** Read TSV file with delimiter.

> Handle tab-separated values file.

Output example:

```
=== TSV Reader ===
File: data.tsv
Name    Age    City
John    25     Seoul
Jane    23     Busan
```

---

### 🔴 Advanced

**Problem 26.** Create complete data analysis application.

> Read CSV, perform analysis, write results to new CSV.

Output example:

```
=== Data Analysis App ===
Input File: sales.csv
Date,Product,Amount
2024-01-01,A,1000
2024-01-02,B,1500
2024-01-03,A,900

Analysis:
Total Sales: 3400
Average: 1133.33
Product A: 1900
Product B: 1500

Output File: analysis.csv
```

---
---

# 🔑 Answer Key and Explanations

---

## 📝 Multiple Choice Answers

---

### 🟢 Beginner

**Problem 1. Answer: ② Comma-Separated Values**

Standard definition of CSV format.

---

**Problem 2. Answer: ③ `csv`**

Python's built-in csv module for CSV operations.

---

**Problem 3. Answer: ② `csv.reader(file)`**

csv.reader() reads CSV and returns iterator of lists.

---

**Problem 4. Answer: ③ `newline=''`**

`newline=''` prevents extra blank lines when writing.

---

**Problem 5. Answer: ② `next()`**

`next()` reads and skips first row (header).

---

**Problem 6. Answer: ④ Can save formatting**

CSV is plain text - no formatting support.

---

**Problem 7. Answer: ② `encoding='utf-8'`**

UTF-8 encoding handles Korean and other characters.

---

### 🟡 Intermediate

**Problem 8. Answer: ② `csv.DictReader`**

DictReader accesses columns by name (dictionary).

---

**Problem 9. Answer: ② `writeheader()`**

writeheader() method writes header row.

---

**Problem 10. Answer: ③ `<class 'list'>`**

csv.reader returns list for each row.

---

**Problem 11. Answer: ③ `'a'`**

'a' mode appends to existing file.

---

**Problem 12. Answer: ② `delimiter='\t'`**

Tab character '\t' separates TSV columns.

---

### 🔴 Advanced

**Problem 13. Answer: ② Writes CSV with headers and data**

DictWriter writes header then data rows.

---

**Problem 14. Answer: ② Sums all values in column**

Loop accumulates float values from Amount column.

---

**Problem 15. Answer: ② reader returns list, DictReader returns dict**

Key difference: list vs dictionary access.

---

## 📝 Short Answer Key

---

### 🟢 Beginner

**Problem 16. Model Answer:**

CSV = comma-separated plain text format.

Advantages: simple, universal, small size.  
Disadvantages: no formatting, limited data types.

---

**Problem 17. Model Answer:**

`newline=''` = prevents blank lines in output  
`encoding='utf-8'` = handles non-ASCII characters

---

**Problem 18. Model Answer:**

`next()` reads and discards first row (header) when opening file.

---

### 🟡 Intermediate

**Problem 19. Model Answer:**

csv.reader = list access (numeric index)  
csv.DictReader = dict access (column name)

---

**Problem 20. Model Answer:**

Use `newline=''` parameter when opening file in write mode.

---

### 🔴 Advanced

**Problem 21. Model Answer:**

Complete data analysis: read, calculate, write results.

---

## 💻 Hands-On Solutions

---

### 🟢 Beginner

**Problem 22. Model Answer:**

```python
import csv

# Write CSV
data = [
    ['Name', 'Age', 'Grade'],
    ['John', 20, 'A'],
    ['Jane', 21, 'B'],
    ['Mike', 19, 'C']
]

with open('students.csv', 'w', newline='', encoding='utf-8') as f:
    writer = csv.writer(f)
    writer.writerows(data)

# Read CSV
print("=== CSV File Demo ===")
with open('students.csv', 'r', encoding='utf-8') as f:
    reader = csv.reader(f)
    for row in reader:
        print(','.join(map(str, row)))
```

---

**Problem 23. Model Answer:**

```python
import csv

students = [
    {'Name': 'John', 'Age': 20, 'Grade': 'A'},
    {'Name': 'Jane', 'Age': 21, 'Grade': 'B'},
    {'Name': 'Mike', 'Age': 19, 'Grade': 'C'}
]

print("=== Write CSV ===")
with open('students.csv', 'w', newline='', encoding='utf-8') as f:
    writer = csv.DictWriter(f, fieldnames=['Name', 'Age', 'Grade'])
    writer.writeheader()
    writer.writerows(students)

for i, student in enumerate(students, 1):
    print(f"Student {i}: {student['Name']}, {student['Age']}, {student['Grade']}")

print("File saved: students.csv")
```

---

### 🟡 Intermediate

**Problem 24. Model Answer:**

```python
import csv

scores = []

with open('scores.csv', 'r', encoding='utf-8') as f:
    reader = csv.DictReader(f)
    for row in reader:
        scores.append(float(row['Score']))

print("=== Score Statistics ===")
print(f"Scores: {scores}")
print(f"Average: {sum(scores) / len(scores):.1f}")
print(f"Highest: {max(scores)}")
print(f"Lowest: {min(scores)}")
```

---

**Problem 25. Model Answer:**

```python
import csv

print("=== TSV Reader ===")
with open('data.tsv', 'r', encoding='utf-8') as f:
    reader = csv.DictReader(f, delimiter='\t')
    for row in reader:
        print(f"{row['Name']:<10} {row['Age']:<5} {row['City']}")
```

---

### 🔴 Advanced

**Problem 26. Model Answer:**

```python
import csv

# Read input file
sales = []
with open('sales.csv', 'r', encoding='utf-8') as f:
    reader = csv.DictReader(f)
    for row in reader:
        sales.append(row)

# Calculate analysis
amounts = [float(row['Amount']) for row in sales]
total = sum(amounts)
average = total / len(amounts)

product_totals = {}
for row in sales:
    product = row['Product']
    amount = float(row['Amount'])
    if product not in product_totals:
        product_totals[product] = 0
    product_totals[product] += amount

# Write results
with open('analysis.csv', 'w', newline='', encoding='utf-8') as f:
    writer = csv.DictWriter(f, fieldnames=['Metric', 'Value'])
    writer.writeheader()
    writer.writerow({'Metric': 'Total Sales', 'Value': total})
    writer.writerow({'Metric': 'Average', 'Value': f"{average:.2f}"})
    for product, amt in product_totals.items():
        writer.writerow({'Metric': f'Product {product}', 'Value': amt})

print("=== Data Analysis ===")
print(f"Total Sales: {total}")
print(f"Average: {average:.2f}")
for product, amt in product_totals.items():
    print(f"Product {product}: {amt}")
print("Results saved to analysis.csv")
```

---

Professor Cho Jeonghyun (peterchokr@gmail.com)  
Yeungnam University College.
