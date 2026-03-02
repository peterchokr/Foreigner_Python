# Chapter 7. Loop 1 (for Statement)

---

## 📚 Learning Objectives

After completing this chapter, you will be able to use for loops to repeat code a set number of times. Loops are a core feature of programming that allows you to automatically perform the same task multiple times.

이번 장을 마치면 여러분은 for 문을 사용하여 정해진 횟수만큼 코드를 반복 실행할 수 있습니다. 반복문은 프로그래밍의 핵심 기능으로, 같은 작업을 여러 번 자동으로 수행할 수 있게 해줍니다.

---

## 1️⃣ What is a for Loop? (for 문이란?)

A for loop is a statement that repeatedly executes code a set number of times or through a range. It allows you to easily implement commands like "do this task 10 times" or "process every item in this list."

for 문은 정해진 범위나 횟수만큼 코드를 반복 실행하는 구문입니다. "이 작업을 10번 해라", "이 리스트의 모든 항목에 대해 작업해라"와 같은 명령을 쉽게 구현할 수 있습니다.

```python
# Without for loop - repetitive coding (for 문 없이 반복 작업)
print("Hello")
print("Hello")
print("Hello")
print("Hello")
print("Hello")

# With for loop - simple and clean (for 문으로 간단하게)
for i in range(5):
    print("Hello")
```

```
How for Loop Works (for 문의 동작 원리)

      Start (시작)
        │
        ▼
    ┌───────┐
    │Generate│
    │ range  │
    └───┬───┘
        │
    ┌───▼────┐
 ┌─>│Any more│
 │  │ values?│
 │  └───┬────┘
 │      │
 │  ┌───┴───┐
 │ Yes     No
 │  │       │
 │┌─▼─┐  ┌─▼──┐
 ││Loop│  │End │
 ││Run │  └────┘
 │└─┬─┘
 │  │
 └──┘
```

---

## 2️⃣ range() Function (range() 함수)

The `range()` function generates a numeric range. It's the most frequently used function with for loops.

`range()` 함수는 숫자 범위를 생성하는 함수입니다. for 문과 함께 가장 많이 사용됩니다.

### Three Forms of range() (range()의 세 가지 형태)

```python
# 1. range(end)
# From 0 to (end-1) (0부터 (끝-1)까지)
for i in range(5):
    print(i, end=" ")
# Output: 0 1 2 3 4

print()

# 2. range(start, end)
# From start to (end-1) (시작부터 (끝-1)까지)
for i in range(1, 6):
    print(i, end=" ")
# Output: 1 2 3 4 5

print()

# 3. range(start, end, step)
# From start to (end-1) increasing by step (시작부터 (끝-1)까지 간격만큼 증가)
for i in range(0, 10, 2):
    print(i, end=" ")
# Output: 0 2 4 6 8
```

```
Understanding range() Function (range() 함수의 이해)

range(5)
┌───┬───┬───┬───┬───┐
│ 0 │ 1 │ 2 │ 3 │ 4 │
└───┴───┴───┴───┴───┘

range(1, 6)
┌───┬───┬───┬───┬───┐
│ 1 │ 2 │ 3 │ 4 │ 5 │
└───┴───┴───┴───┴───┘

range(0, 10, 2)
┌───┬───┬───┬───┬───┐
│ 0 │ 2 │ 4 │ 6 │ 8 │
└───┴───┴───┴───┴───┘

range(10, 0, -1)
┌────┬───┬───┬───┬───┬───┬───┬───┬───┬───┐
│ 10 │ 9 │ 8 │ 7 │ 6 │ 5 │ 4 │ 3 │ 2 │ 1 │
└────┴───┴───┴───┴───┴───┴───┴───┴───┴───┘
```

### Reverse Order Loop (역순 반복)

```python
# Reverse loop (negative step) (역순으로 반복 (간격을 음수로))
for i in range(5, 0, -1):
    print(i, end=" ")
# Output: 5 4 3 2 1
```

### Example 1: Rocket Launch Countdown (예제 1: 로켓 발사 카운트다운)

A program that counts down for rocket launch.

로켓 발사 카운트다운을 만드는 프로그램입니다.

```python
# Rocket launch countdown (로켓 발사 카운트다운)
print("🚀" + "=" * 38 + "🚀")
print("   Rocket Launch Countdown")
print("🚀" + "=" * 38 + "🚀")

print("\nPreparing for launch...")
print()

# Countdown from 10 to 1 (10부터 1까지 카운트다운)
for count in range(10, 0, -1):
    print(f"  {count}...")

print("\n🚀 Liftoff!!! 🚀")
print()

# Display altitude (상승 표시)
for altitude in range(0, 101, 20):
    print(f"Altitude: {altitude}m")

print("\n✨ Launch successful!")
```

---

## 3️⃣ String Iteration (문자열 순회)

You can process each character in a string one by one using a for loop.

for 문으로 문자열의 각 문자를 하나씩 처리할 수 있습니다.

```python
# String iteration (문자열 순회)
message = "PYTHON"

for char in message:
    print(char)

# Output:
# P
# Y
# T
# H
# O
# N
```

### Count Vowels (모음 개수 세기)

```python
text = "Hello World"
vowel_count = 0

for char in text:
    if char in "aeiouAEIOU":
        vowel_count = vowel_count + 1

print(f"Number of vowels: {vowel_count}")  # 3
```

### Example 2: Name Analyzer (예제 2: 이름 분석기)

A program that analyzes an entered name.

입력받은 이름을 분석하는 프로그램입니다.

```python
# Name analyzer program (이름 분석 프로그램)
print("✨" + "=" * 38 + "✨")
print("   Name Analyzer")
print("✨" + "=" * 38 + "✨")

name = input("\nEnter your name: ")

# Analysis results (분석 결과)
print("\n" + "=" * 40)
print("Analysis Results")
print("=" * 40)

# 1. Number of characters (글자 수)
print(f"Total characters: {len(name)}")

# 2. Display each character (각 글자 출력)
print("\nCharacter breakdown:")
for i in range(len(name)):
    print(f"  Position {i+1}: {name[i]}")

# 3. Reverse spelling (거꾸로)
print("\nReverse spelling:")
reverse_name = ""
for char in name:
    reverse_name = char + reverse_name
print(f"  {reverse_name}")

# 4. Convert to uppercase (대문자로 (영문인 경우))
print("\nUppercase conversion:")
upper_name = ""
for char in name:
    upper_name = upper_name + char.upper()
print(f"  {upper_name}")

print("=" * 40)
```

---

## 4️⃣ Loops and Accumulation (반복문과 누적)

In loops, you can accumulate values to calculate sums, averages, and other statistics.

반복문에서 값을 누적하여 합계, 평균 등을 계산할 수 있습니다.

```python
# Sum from 1 to 10 (1부터 10까지의 합)
total = 0

for i in range(1, 11):
    total = total + i
    print(f"Sum up to {i}: {total}")

print(f"\nFinal total: {total}")  # 55
```

### Example 3: Savings Challenge Calculator (예제 3: 저금통 계산기)

A program that tracks accumulated daily savings.

매일 저축한 금액을 누적하여 계산하는 프로그램입니다.

```python
# Savings challenge program (저금통 계산 프로그램)
print("🐷" + "=" * 38 + "🐷")
print("   30-Day Savings Challenge")
print("🐷" + "=" * 38 + "🐷")

print("\nEnter your daily savings amount")
daily_amount = int(input("Daily savings: $"))

total_saved = 0

print("\n" + "=" * 40)
print("Savings Progress")
print("=" * 40)

# Savings for 30 days (30일 동안 저축)
for day in range(1, 31):
    total_saved = total_saved + daily_amount
  
    # Mid-report every 7 days (7일마다 중간 보고)
    if day % 7 == 0:
        print(f"Day {day}: ${total_saved} 💰")

# Final results (최종 결과)
print("\n" + "=" * 40)
print("30-Day Challenge Complete!")
print("=" * 40)
print(f"Total saved: ${total_saved}")
print(f"Daily average: ${daily_amount}")

# Goal achievement (목표 달성 여부)
goal = 100
if total_saved >= goal:
    print(f"\n🎉 Goal of ${goal} achieved!")
else:
    shortage = goal - total_saved
    print(f"\n💡 Short by ${shortage} to reach goal")

print("=" * 40)
```

---

## 5️⃣ Nested for Loops (중첩 for 문)

You can place a for loop inside another for loop. This is useful for creating 2D patterns or tables.

for 문 안에 또 다른 for 문을 넣을 수 있습니다. 2차원 패턴이나 표를 만들 때 유용합니다.

```python
# Nested for loop (중첩 for 문)
for i in range(1, 4):
    for j in range(1, 4):
        print(f"({i}, {j})", end=" ")
    print()  # Newline (줄바꿈)

# Output:
# (1, 1) (1, 2) (1, 3)
# (2, 1) (2, 2) (2, 3)
# (3, 1) (3, 2) (3, 3)
```

### Example 4: Multiplication Table (예제 4: 구구단)

A program that prints multiplication tables.

구구단을 출력하는 프로그램입니다.

```python
# Multiplication table program (구구단 프로그램)
print("📚" + "=" * 38 + "📚")
print("   Multiplication Tables")
print("📚" + "=" * 38 + "📚")

start_table = int(input("\nStart table: "))
end_table = int(input("End table: "))

print("\n" + "=" * 40)

# Display each table (각 단 출력)
for table in range(start_table, end_table + 1):
    print(f"\n[ Table {table} ]")
    print("-" * 20)
  
    # Multiply from 1 to 9 (1부터 9까지 곱하기)
    for num in range(1, 10):
        result = table * num
        print(f"{table} × {num} = {result}")

print("\n" + "=" * 40)
```

---

## 6️⃣ Star Pattern Display (별 패턴 출력)

You can create various patterns using nested loops.

중첩 반복문을 사용하여 다양한 패턴을 만들 수 있습니다.

### Pattern 1: Triangle (패턴 1: 삼각형)

```python
# Star triangle (별 삼각형)
print("Star Triangle")
print("-" * 20)

for i in range(1, 6):
    print("★" * i)

# Output:
# ★
# ★★
# ★★★
# ★★★★
# ★★★★★
```

### Pattern 2: Reverse Triangle (패턴 2: 역삼각형)

```python
# Reverse triangle (역삼각형)
print("\nReverse Triangle")
print("-" * 20)

for i in range(5, 0, -1):
    print("★" * i)

# Output:
# ★★★★★
# ★★★★
# ★★★
# ★★
# ★
```

### Example 5: Pattern Generator (예제 5: 패턴 출력기)

A program that prints various star patterns.

다양한 별 패턴을 출력하는 프로그램입니다.

```python
# Star pattern generator (별 패턴 출력 프로그램)
print("⭐" + "=" * 38 + "⭐")
print("   Star Pattern Generator")
print("⭐" + "=" * 38 + "⭐")

height = int(input("\nEnter height (1-10): "))

print("\n" + "=" * 40)
print("Pattern 1: Right Triangle")
print("=" * 40)

for i in range(1, height + 1):
    print("★" * i)

print("\n" + "=" * 40)
print("Pattern 2: Reverse Right Triangle")
print("=" * 40)

for i in range(height, 0, -1):
    print("★" * i)

print("\n" + "=" * 40)
print("Pattern 3: Pyramid")
print("=" * 40)

for i in range(1, height + 1):
    # Print spaces (공백 출력)
    spaces = " " * (height - i)
    # Print stars (별 출력)
    stars = "★" * (2 * i - 1)
    print(spaces + stars)

print("\n" + "=" * 40)
print("Pattern 4: Diamond")
print("=" * 40)

# Top triangle (위쪽 삼각형)
for i in range(1, height + 1):
    spaces = " " * (height - i)
    stars = "★" * (2 * i - 1)
    print(spaces + stars)

# Bottom reverse triangle (아래쪽 역삼각형)
for i in range(height - 1, 0, -1):
    spaces = " " * (height - i)
    stars = "★" * (2 * i - 1)
    print(spaces + stars)

print("=" * 40)
```

---

## 7️⃣ Practical Examples (실전 활용 예제)

### Example 6: Test Score Analysis (예제 6: 시험 점수 분석)

A program that analyzes multiple students' test scores.

여러 학생의 점수를 입력받아 분석하는 프로그램입니다.

```python
# Test score analysis program (시험 점수 분석 프로그램)
print("📝" + "=" * 38 + "📝")
print("   Test Score Analysis")
print("📝" + "=" * 38 + "📝")

student_count = int(input("\nNumber of students: "))

total_score = 0
highest_score = 0
lowest_score = 100
pass_count = 0  # 60 or higher (60점 이상)

print("\nEnter scores:")

for i in range(1, student_count + 1):
    score = int(input(f"Student {i}: "))
  
    # Accumulate total (합계 누적)
    total_score = total_score + score
  
    # Find highest score (최고점 찾기)
    if score > highest_score:
        highest_score = score
  
    # Find lowest score (최저점 찾기)
    if score < lowest_score:
        lowest_score = score
  
    # Count passes (합격자 수 세기)
    if score >= 60:
        pass_count = pass_count + 1

# Calculate average (평균 계산)
average = total_score / student_count

# Display results (결과 출력)
print("\n" + "=" * 40)
print("Analysis Results")
print("=" * 40)
print(f"Total students: {student_count}")
print(f"Average score: {average:.1f}")
print(f"Highest score: {highest_score}")
print(f"Lowest score: {lowest_score}")
print(f"Passes: {pass_count} ({pass_count/student_count*100:.0f}%)")

# Grade distribution (등급 분포)
print("\nGrade Distribution:")
print("  A Grade (90+)")
print("  B Grade (80-89)")
print("  C Grade (70-79)")
print("  D Grade (60-69)")
print("  F Grade (below 60)")

print("=" * 40)
```


---

## 📝 Summary of Key Concepts (핵심 개념 정리)

A for loop repeatedly executes code a set number of times. The `range()` function specifies the numeric range, with three forms: `range(end)`, `range(start, end)`, and `range(start, end, step)`.

for 문은 정해진 범위나 횟수만큼 코드를 반복 실행합니다. `range()` 함수로 숫자 범위를 지정하며, `range(끝)`, `range(시작, 끝)`, `range(시작, 끝, 간격)` 세 가지 형태로 사용할 수 있습니다.

Strings can also be traversed with for loops, allowing you to process each character individually. You can accumulate values in loops to calculate totals, averages, maximums, and minimums.

문자열도 for 문으로 순회할 수 있으며, 각 문자를 하나씩 처리할 수 있습니다. 반복문에서 변수에 값을 누적하여 합계, 평균, 최댓값, 최솟값 등을 계산할 수 있습니다.

Nested for loops place loops within loops and are useful for creating 2D patterns and tables. You can create programs like multiplication tables, star patterns, and seating arrangements.

중첩 for 문은 반복문 안에 또 다른 반복문을 넣는 것으로, 2차원 패턴이나 표를 만들 때 유용합니다. 별 패턴, 구구단, 좌석 배치도 등 다양한 프로그램을 만들 수 있습니다.

---

## 💡 Practical Assignments (실습 과제)

### Assignment 1: Select Multiplication Table (과제 1: 구구단 선택 출력)

Write a program that prints only the multiplication table for a user-selected number.

사용자가 원하는 단 하나만 출력하는 프로그램을 작성하세요.

```python
# Hint
table = int(input("Which table? "))

print(f"\nTable {table}")
print("=" * 20)

for i in range(1, 10):
    print(f"{table} × {i} = {table * i}")
```

### Assignment 2: Star Rectangle (과제 2: 별 사각형 출력)

Write a program that draws a rectangle with stars based on input width and height.

가로와 세로 크기를 입력받아 별로 사각형을 그리는 프로그램을 작성하세요.

```python
# Hint
width = int(input("Width: "))
height = int(input("Height: "))

for i in range(height):
    print("★" * width)
```

---

## ✅ Quiz (퀴즈)

### [Beginner] Question 1

How many times is "Hello" printed?

다음 코드의 출력 횟수는?

```python
for i in range(5):
    print("Hello")
```

1. 4 times
2. 5 times
3. 6 times
4. Infinite loop

### [Intermediate] Question 2

What is the output?

다음 코드의 출력 결과는?

```python
for i in range(2, 5):
    print(i, end=" ")
```

1. 2 3 4
2. 2 3 4 5
3. 3 4 5
4. 1 2 3 4 5

### [Intermediate] Question 3

What is the value of total?

다음 코드의 total 값은?

```python
total = 0
for i in range(1, 6):
    total = total + i
```

1. 5
2. 10
3. 15
4. 21

### [Advanced] Question 4

How many lines are printed?

다음 코드의 출력 줄 수는?

```python
for i in range(1, 4):
    for j in range(1, 3):
        print("*")
```

1. 3 lines
2. 4 lines
3. 6 lines
4. 9 lines

### [Advanced] Question 5

Which code prints in reverse order?

다음 중 역순으로 출력하는 코드는?

```python
1) for i in range(5, 0):
2) for i in range(5, 0, -1):
3) for i in range(0, 5, -1):
4) for i in range(5, -1, -1):
```

1. 1번
2. 2번
3. 3번
4. 4번

---

## 🔑 Quiz Answers and Explanations (퀴즈 정답 및 해설)

**Question 1 Answer: 2**
`range(5)` generates 0, 1, 2, 3, 4, so it repeats 5 times total.

`range(5)`는 0, 1, 2, 3, 4를 생성하므로 총 5번 반복됩니다.

**Question 2 Answer: 1**
`range(2, 5)` is from 2 to 4 (5 not included), so "2 3 4" is printed.

`range(2, 5)`는 2부터 4까지(5는 포함 안 됨)이므로 "2 3 4"가 출력됩니다.

**Question 3 Answer: 3**
1+2+3+4+5 = 15. `range(1, 6)` means 1 through 5.

1+2+3+4+5 = 15입니다. range(1, 6)은 1부터 5까지를 의미합니다.

**Question 4 Answer: 3**
The outer loop runs 3 times (i=1,2,3), and the inner loop runs 2 times (j=1,2) each, so 3×2 = 6 lines are printed.

바깥 반복문이 3번(i=1,2,3), 안쪽 반복문이 각각 2번(j=1,2) 실행되므로 총 3×2 = 6줄이 출력됩니다.

**Question 5 Answer: 2**
`range(5, 0, -1)` prints from 5 to 1 in reverse. Option 1 has an empty range, option 3 has an empty range, and option 4 prints from 5 to 0.

`range(5, 0, -1)`은 5부터 1까지 역순으로 출력합니다. 1번은 범위가 비어있고, 3번도 범위가 비어있으며, 4번은 5부터 0까지입니다.

---

## 🎯 Preview of Next Chapter (다음 장 예고)

In the next chapter, we will learn about while loops and flow control statements (break, continue). We'll learn how while loops execute while a condition is true, and how to control the flow of loops. Let's make your programs even more powerful!

다음 장에서는 while 문과 break, continue에 대해 배웁니다. 조건이 참인 동안 반복하는 while 문과, 반복문의 흐름을 제어하는 방법을 학습하게 됩니다!

---

Thank you for your attention.  
Cho Jeonghyun ([peterchokr@gmail.com](mailto:peterchokr@gmail.com)). Yeungnam University College

"Produced in collaboration with Claude and Gemini."
