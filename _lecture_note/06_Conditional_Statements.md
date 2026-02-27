# Chapter 6. Conditional Statements

---

## 📚 Learning Objectives

After completing this chapter, you will be able to make your program perform different actions depending on situations. Conditional statements are a core feature that gives programs decision-making ability, allowing you to create much more intelligent programs.

이번 장을 마치면 여러분은 프로그램이 상황에 따라 다른 동작을 하도록 만들 수 있습니다. 조건문은 프로그램에 판단 능력을 부여하는 핵심 기능으로, 이를 통해 훨씬 더 지능적인 프로그램을 만들 수 있게 됩니다.

---

## 1️⃣ if Statement Basics (if 문 기본)

A conditional statement is a structure that executes code only when a specific condition is true. Just like "if it rains, I'll bring an umbrella," you make decisions based on conditions.

조건문은 특정 조건이 참일 때만 코드를 실행하는 구조입니다. 마치 "만약 비가 오면 우산을 가져간다"처럼 조건에 따라 행동을 결정하는 것과 같습니다.

### Basic Structure (기본 구조)

```python
# Basic if statement (if 문의 기본 형태)
if condition:
    execute this code
```

If the condition is true (True), the indented code is executed. If false (False), it is not executed. Indentation is very important in Python; generally 4 spaces are used.

조건식이 참(True)이면 들여쓰기된 코드가 실행되고, 거짓(False)이면 실행되지 않습니다. 파이썬에서 들여쓰기는 매우 중요하며, 일반적으로 스페이스 4칸을 사용합니다.

```python
# Age check (나이 확인)
age = int(input("Enter your age: "))

if age >= 18:
    print("You are an adult.")
    print("You can watch all movies.")

print("Program terminates.")
```

In the above example, if age is 18 or older, both messages are printed. The last line always executes regardless of the condition.

위 예제에서 나이가 18세 이상이면 "You are an adult."와 "You can watch all movies."가 출력됩니다. 마지막 줄은 조건과 관계없이 항상 실행됩니다.

```
Conditional Statement Execution Flow (조건문 실행 흐름)

       Start (시작)
        │
        ▼
   [Check Condition] (조건 검사)
    age >= 18?
      /    \
   True   False
    /        \
   ▼          │
Execute Block  │
(Indented)     │
   │          │
   ▼          ▼
   Execute Next Code (다음 코드 실행)
```

### Example 1: Coffee Morning Discount (예제 1: 커피 모닝 할인)

A coffee ordering program that applies discounts based on time.

시간에 따라 할인을 적용하는 커피 주문 프로그램입니다.

```python
# Coffee shop morning discount system (커피숍 모닝 할인 시스템)
print("☕ === Coffee Shop Order System === ☕\n")

# Order information (주문 정보)
drink = input("Drink: ")
price = int(input("Price: "))
hour = int(input("Current time (0-23): "))

print("\n" + "=" * 40)
print("Order Details")
print("=" * 40)
print(f"Drink: {drink}")
print(f"Regular price: ${price}")

# Morning discount (6 AM ~ 10 AM) (모닝 할인 (오전 6시 ~ 10시))
if hour >= 6 and hour < 10:
    discount = int(price * 0.3)  # 30% discount (30% 할인)
    price = price - discount
    print(f"Morning discount 30%: -${discount}")

print(f"Final price: ${price}")
print("=" * 40)

if hour >= 6 and hour < 10:
    print("🌅 Good morning!")
```

---

## 2️⃣ if-else Statement

To perform different actions when a condition is true versus false, use `else`.

조건이 참일 때와 거짓일 때 각각 다른 동작을 하려면 `else`를 사용합니다.

```python
# if-else basic structure (if-else 기본 구조)
if condition:
    execute when condition is true (조건이 참일 때 실행)
else:
    execute when condition is false (조건이 거짓일 때 실행)
```

```python
# Movie rating check (영화 관람 등급 확인)
age = int(input("Age: "))

if age >= 18:
    print("Adult authentication complete")
    print("You can watch R-rated movies.")
else:
    print("You are a minor.")
    print("You can only watch youth-rated movies.")
```

### Example 2: Delivery Fee Calculation (예제 2: 배달비 계산)

A program that applies different delivery fees based on order amount.

주문 금액에 따라 배달비를 다르게 적용하는 프로그램입니다.

```python
# Delivery order system (배달 주문 시스템)
print("🚚 === Delivery Order System === 🚚\n")

# Order information (주문 정보)
restaurant = input("Restaurant name: ")
menu = input("Menu: ")
price = int(input("Order amount: "))

# Calculate delivery fee (배달비 계산)
delivery_fee = 3

print("\n" + "=" * 40)
print("Order Details")
print("=" * 40)
print(f"Restaurant: {restaurant}")
print(f"Menu: {menu}")
print(f"Order amount: ${price}")

# Check free delivery condition (30 or more) (무료 배달 조건 확인 (30 이상))
if price >= 30:
    delivery_fee = 0
    print(f"Delivery fee: FREE (Order $30 or more)")
else:
    print(f"Delivery fee: ${delivery_fee}")
    print(f"※ Free delivery for orders $30 or more")

total = price + delivery_fee
print("-" * 40)
print(f"Total payment: ${total}")
print("=" * 40)
```

---

## 3️⃣ if-elif-else Statement

Use `elif` (else if) when checking multiple conditions sequentially.

여러 조건을 순차적으로 검사할 때는 `elif`(else if의 줄임말)를 사용합니다.

```python
# if-elif-else basic structure (if-elif-else 기본 구조)
if condition1:
    execute when condition1 is true (조건1이 참일 때)
elif condition2:
    execute when condition1 is false and condition2 is true
    (조건1은 거짓, 조건2가 참일 때)
elif condition3:
    execute when condition1,2 are false and condition3 is true
    (조건1,2는 거짓, 조건3이 참일 때)
else:
    execute when all conditions are false (모든 조건이 거짓일 때)
```

Conditions are checked in order from top to bottom. Once a condition is satisfied, only that block executes and the rest are skipped.

조건은 위에서부터 순서대로 검사되며, 처음으로 참인 조건의 블록만 실행됩니다. 한 번 조건이 만족되면 나머지 조건은 검사하지 않습니다.

```python
# Grade determination (성적 등급 판정)
score = int(input("Score: "))

if score >= 90:
    grade = "A"
    print("Grade A. Excellent!")
elif score >= 80:
    grade = "B"
    print("Grade B. Great work!")
elif score >= 70:
    grade = "C"
    print("Grade C. Keep trying!")
elif score >= 60:
    grade = "D"
    print("Grade D. Try harder!")
else:
    grade = "F"
    print("Grade F. Retake the course!")

print(f"Final grade: {grade}")
```

### Example 3: Weather-Based Clothing Recommendation (예제 3: 날씨별 옷차림 추천)

A program that recommends appropriate clothing based on temperature.

기온에 따라 적절한 옷차림을 추천하는 프로그램입니다.

```python
# Weather-based clothing recommendation system (날씨별 옷차림 추천 시스템)
print("🌡️ === Clothing Recommendation Service === 🌡️\n")

# Get weather information (날씨 정보 입력)
location = input("Location: ")
temperature = int(input("Current temperature (°C): "))
is_raining = input("Is it raining? (yes/no): ")

print("\n" + "=" * 40)
print(f"📍 {location} Weather Information")
print("=" * 40)
print(f"Temperature: {temperature}°C")

# Clothing recommendation based on temperature (온도에 따른 옷차림 추천)
if temperature >= 28:
    clothes = "T-shirt, shorts, dress"
    print(f"\n🔥 Very hot! ({temperature}°C)")
elif temperature >= 23:
    clothes = "Thin long sleeves, cotton pants, blouse"
    print(f"\n☀️ Warm! ({temperature}°C)")
elif temperature >= 17:
    clothes = "Sweater, cardigan, jeans"
    print(f"\n🍂 Cool! ({temperature}°C)")
elif temperature >= 10:
    clothes = "Jacket, leather jacket, basic coat"
    print(f"\n🍃 Chilly! ({temperature}°C)")
elif temperature >= 5:
    clothes = "Coat, heat tech, fleece pants"
    print(f"\n❄️ Cold! ({temperature}°C)")
else:
    clothes = "Padding, thick coat, scarf, gloves"
    print(f"\n⛄ Very cold! ({temperature}°C)")

print(f"Recommended clothing: {clothes}")

# Umbrella recommendation (우산 추천)
if is_raining == "yes":
    print("\n☔ Don't forget your umbrella!")

print("=" * 40)
```

---

## 4️⃣ Nested Conditional Statements (중첩 조건문)

You can place a conditional statement inside another conditional statement. This is called nested conditional statements.

조건문 안에 또 다른 조건문을 넣을 수 있습니다. 이를 중첩 조건문이라고 합니다.

```python
# Nested conditional statement structure (중첩 조건문 기본 구조)
if condition1:
    if condition2:
        execute when both condition1 and condition2 are true
        (조건1과 조건2가 모두 참일 때)
    else:
        execute when condition1 is true and condition2 is false
        (조건1은 참, 조건2는 거짓일 때)
else:
    execute when condition1 is false (조건1이 거짓일 때)
```

```python
# Movie ticket price calculation (영화 티켓 가격 계산)
age = int(input("Age: "))
is_student = input("Are you a student? (yes/no): ")

price = 14  # Base price ($14)

if age < 18:
    price = 11  # Youth price ($11)
    print("Youth rate applied.")
else:
    if is_student == "yes":
        price = 12  # Adult student discount ($12)
        print("Adult student discount applied.")
    else:
        print("Regular rate applied.")

print(f"Ticket price: ${price}")
```

### Example 4: Diet Calorie Management (예제 4: 다이어트 칼로리 관리)

A program that evaluates diet status considering intake and exercise calories.

섭취 칼로리와 운동량을 고려하여 다이어트 상태를 판정하는 프로그램입니다.

```python
# Diet calorie management system (다이어트 칼로리 관리 시스템)
print("🍎 === Diet Calorie Management === 🍎\n")

# User information (사용자 정보)
name = input("Name: ")
target_cal = int(input("Target calories: "))

# Today's meals (오늘의 식사)
breakfast = int(input("\nBreakfast (kcal): "))
lunch = int(input("Lunch (kcal): "))
dinner = int(input("Dinner (kcal): "))
snack = int(input("Snacks (kcal): "))

# Exercise (운동)
exercise_cal = int(input("Calories burned from exercise (kcal): "))

# Calculate net calories (순 칼로리 계산)
total_intake = breakfast + lunch + dinner + snack
net_cal = total_intake - exercise_cal

print("\n" + "=" * 40)
print(f"{name}'s Calorie Report")
print("=" * 40)
print(f"Total intake: {total_intake:,}kcal")
print(f"Exercise burned: {exercise_cal:,}kcal")
print(f"Net calories: {net_cal:,}kcal")
print(f"Target calories: {target_cal:,}kcal")

# Evaluate against target (목표 대비 평가)
difference = net_cal - target_cal
print("-" * 40)

if net_cal <= target_cal:
    print("✅ Goal achieved!")
    if difference <= -200:
        print("💪 Amazing! You consumed much less than target!")
    else:
        print("👍 You're doing great!")
else:
    print("⚠️ Goal exceeded!")
    if difference <= 200:
        print("💭 Try a little harder!")
    else:
        print("😅 Pay more attention tomorrow!")
    print(f"Excess: {difference:,}kcal")

print("=" * 40)
```

---

## 5️⃣ Conditional Expression (Ternary Operator) (조건 표현식)

Simple if-else statements can be expressed in one line. This is called a conditional expression or ternary operator.

간단한 if-else 문은 한 줄로 표현할 수 있습니다. 이를 조건 표현식 또는 삼항 연산자라고 합니다.

```python
# Conditional expression structure (조건 표현식 기본 구조)
variable = value_if_true if condition else value_if_false
```

```python
# Regular if-else (일반적인 if-else)
age = 20
if age >= 18:
    status = "adult"
else:
    status = "minor"

# Simplified with conditional expression (조건 표현식으로 간단하게)
age = 20
status = "adult" if age >= 18 else "minor"
print(status)  # adult

# Find maximum (최댓값 구하기)
a = 10
b = 20
max_value = a if a > b else b
print(f"Maximum: {max_value}")  # 20

# Find absolute value (절댓값 구하기)
num = -5
abs_num = num if num >= 0 else -num
print(f"Absolute value: {abs_num}")  # 5
```

### Example 5: YouTuber Rating System (예제 5: 유튜버 등급 판정)

A program that determines YouTuber tier based on subscriber count.

구독자 수에 따라 유튜버 등급을 판정하는 프로그램입니다.

```python
# YouTuber statistics system (유튜버 통계 시스템)
print("📺 === YouTuber Statistics System === 📺\n")

# Channel information (채널 정보)
channel_name = input("Channel name: ")
subscribers = int(input("Subscriber count: "))
views = int(input("Total views: "))
videos = int(input("Number of videos: "))

# Calculate average views (평균 조회수)
avg_views = views / videos if videos > 0 else 0

# Determine tier (등급 판정)
if subscribers >= 1000000:
    tier = "💎 Diamond"
    message = "Congratulations! You are a top YouTuber!"
elif subscribers >= 100000:
    tier = "🏆 Gold"
    message = "Great! You are a popular YouTuber!"
elif subscribers >= 10000:
    tier = "🥈 Silver"
    message = "Doing well! Growing fast!"
elif subscribers >= 1000:
    tier = "🥉 Bronze"
    message = "Good start!"
else:
    tier = "🌱 Seedling"
    message = "Fighting! Keep uploading!"

# Display results (결과 출력)
print("\n" + "╔" + "═" * 48 + "╗")
print("║" + f"{channel_name} Channel Statistics".center(48) + "║")
print("╠" + "═" * 50 + "╣")
print(f"║  Subscribers: {subscribers:,}".ljust(50) + "║")
print(f"║  Total views: {views:,}".ljust(50) + "║")
print(f"║  Number of videos: {videos}".ljust(50) + "║")
print(f"║  Average views: {avg_views:,.0f}".ljust(50) + "║")
print("╠" + "─" * 50 + "╣")
print(f"║  Tier: {tier}".ljust(50) + "║")
print(f"║  {message}".ljust(50) + "║")

# Next goal (다음 등급까지)
if subscribers < 1000:
    next_goal = 1000 - subscribers
    print(f"║  {next_goal:,} more to Bronze!".ljust(50) + "║")
elif subscribers < 10000:
    next_goal = 10000 - subscribers
    print(f"║  {next_goal:,} more to Silver!".ljust(50) + "║")
elif subscribers < 100000:
    next_goal = 100000 - subscribers
    print(f"║  {next_goal:,} more to Gold!".ljust(50) + "║")
elif subscribers < 1000000:
    next_goal = 1000000 - subscribers
    print(f"║  {next_goal:,} more to Diamond!".ljust(50) + "║")

print("╚" + "═" * 50 + "╝")
```

---

## 6️⃣ Logical Operators and Conditionals (논리 연산자와 조건문)

Use logical operators `and`, `or`, `not` to create complex conditions.

복잡한 조건을 만들 때는 논리 연산자 `and`, `or`, `not`을 활용합니다.

```python
# and: True only when all conditions are true (모두 참이어야 참)
age = 25
has_license = True

if age >= 18 and has_license:
    print("You can drive.")

# or: True if any condition is true (하나라도 참이면 참)
is_weekend = True
is_holiday = False

if is_weekend or is_holiday:
    print("Day off!")

# not: Reverses true and false (참과 거짓을 반대로)
is_raining = False

if not is_raining:
    print("No need for an umbrella.")
```

### Example 6: Movie Booking System (예제 6: 영화 예매 시스템)

A movie booking system considering age, time, and seating.

나이, 시간, 좌석을 고려한 영화 예매 시스템입니다.

```python
# Movie booking system (영화 예매 시스템)
print("🎬 === Movie Booking System === 🎬\n")

# Movie information (영화 정보)
movie = input("Movie title: ")
rating = input("Rating (G/PG/PG-13/R): ")

# Customer information (고객 정보)
name = input("\nBooker name: ")
age = int(input("Age: "))
is_student = input("Are you a student? (yes/no): ")

# Booking information (예매 정보)
time = int(input("\nShowtime (0-23 hours): "))
seat_type = input("Seat type (standard/VIP): ")
tickets = int(input("Number of tickets: "))

# Base price (기본 가격)
base_price = 14

# Adjust for seat type (좌석 등급별 가격)
if seat_type == "VIP":
    base_price = 18

# Apply age discount (나이별 할인)
if age < 13:
    base_price = 10  # Child rate
elif age >= 65:
    base_price = 11  # Senior rate
elif is_student == "yes":
    base_price = base_price - 2  # Student discount

# Early morning discount (6-10 AM) (조조 할인)
morning_discount = 0
if time >= 6 and time < 10:
    morning_discount = 2
    base_price = base_price - morning_discount

# Calculate total price (총 가격)
total_price = base_price * tickets

# Check if can watch (관람 가능 여부 확인)
can_watch = True
reason = ""

if rating == "R" and age < 18:
    can_watch = False
    reason = "R-rated movies are for adults only."
elif rating == "PG-13" and age < 13:
    can_watch = False
    reason = "PG-13 rating requires age 13+."

# Display results (결과 출력)
print("\n" + "=" * 50)
if can_watch:
    print("✅ Booking Complete!")
    print("=" * 50)
    print(f"Movie: {movie} ({rating})")
    print(f"Booker: {name} ({age} years old)")
    print(f"Showtime: {time}:00")
    print(f"Seats: {seat_type} × {tickets}")
    print("-" * 50)
    print(f"Ticket price: ${base_price} × {tickets}")
  
    if morning_discount > 0:
        print(f"Early morning discount: -${morning_discount}")
  
    if is_student == "yes" and age >= 13 and age < 65:
        print(f"Student discount applied")
  
    print("-" * 50)
    print(f"Total payment: ${total_price}")
    print("=" * 50)
    print("\n🍿 Enjoy the movie!")
else:
    print("❌ Booking Not Available!")
    print("=" * 50)
    print(f"Reason: {reason}")
    print("=" * 50)
```

---

## 📝 Summary of Key Concepts (핵심 개념 정리)

The `if` statement executes code only when a condition is true. Using `else`, you can specify what happens when the condition is false. For multiple sequential conditions, use `elif`, which only executes the first true condition's block.

`if`문은 조건이 참일 때만 코드를 실행합니다. `else`를 사용하면 조건이 거짓일 때의 동작을 지정할 수 있습니다. 여러 조건을 순차적으로 검사하려면 `elif`를 사용하며, 처음으로 참인 조건의 블록만 실행됩니다.

Nested conditional statements, which place conditionals inside other conditionals, allow more complex logic. Simple conditions can be written as one-liners using conditional expressions (ternary operator).

조건문 안에 다른 조건문을 넣는 중첩 조건문을 사용하면 더 복잡한 논리를 표현할 수 있습니다. 간단한 조건은 조건 표현식(삼항 연산자)으로 한 줄로 작성할 수 있습니다.

Logical operators `and`, `or`, and `not` combine multiple conditions. `and` requires all conditions to be true, `or` requires at least one to be true, and `not` reverses the condition.

논리 연산자 `and`, `or`, `not`을 사용하면 여러 조건을 결합할 수 있습니다. `and`는 모든 조건이 참이어야 하고, `or`는 하나라도 참이면 되며, `not`은 조건을 반대로 만듭니다.

Indentation is crucial in Python and defines conditional statement blocks. Generally, 4 spaces are used.

들여쓰기는 파이썬에서 매우 중요하며, 조건문의 블록을 구분하는 기준이 됩니다. 일반적으로 스페이스 4칸을 사용합니다.

---

## 💡 Practical Assignments (실습 과제)

### Assignment 1: Coffee Recommendation System (과제 1: 커피 주문 추천 시스템)

Write a program that recommends appropriate coffee based on time of day and weather.

시간대와 날씨에 따라 적절한 커피를 추천하는 프로그램을 작성하세요.

```
Conditions:
- Morning (6-11 AM): Recommend Americano
- Afternoon (12-5 PM): Recommend Latte  
- Evening (6-11 PM): Recommend Decaf
- Hot weather (75°F+): Recommend Iced
- Cold weather (60°F-): Recommend Hot
```

### Assignment 2: Taxi Fare Calculator (과제 2: 택시 요금 계산기)

Write a program that calculates taxi fare based on distance and time.

거리와 시간에 따라 택시 요금을 계산하는 프로그램을 작성하세요.

```python
# Hint
distance = float(input("Distance (km): "))
time = int(input("Pickup time (0-23 hours): "))

base_fare = 5  # Base fare (first 1 mile)
extra_fare = 0

# Additional $2 per mile over 1 mile
if distance > 1:
    extra_fare = (distance - 1) * 2

# Late night surcharge (0-4 AM): 20% additional
if time >= 0 and time < 4:
    extra_fare = extra_fare * 1.2

total_fare = base_fare + extra_fare
print(f"Taxi fare: ${total_fare:.2f}")
```

---

## ✅ Quiz (퀴즈)

### [Beginner] Question 1

What is the output of the following code?

다음 코드에서 출력되는 결과는?

```python
x = 10
if x > 5:
    print("A")
print("B")
```

1. A
2. B
3. A B (with line break)
4. Nothing

### [Intermediate] Question 2

Which will NOT be printed?

다음 중 출력되지 않는 것은?

```python
score = 85
if score >= 90:
    print("A")
elif score >= 80:
    print("B")
elif score >= 70:
    print("C")
else:
    print("D")
```

1. A
2. B
3. C
4. D

### [Intermediate] Question 3

What is the output of this conditional expression?

다음 조건 표현식의 결과는?

```python
age = 15
result = "adult" if age >= 18 else "minor"
print(result)
```

1. adult
2. minor
3. True
4. False

### [Intermediate] Question 4

When is "Pass" printed?

다음 코드에서 "Pass"가 출력되는 조건은?

```python
score = 75
attendance = 85

if score >= 60 and attendance >= 80:
    print("Pass")
else:
    print("Fail")
```

1. Only when score is 60+
2. Only when attendance is 80+
3. When either condition is met
4. When both conditions are met

### [Advanced] Question 5

What is the output?

다음 코드의 출력 결과는?

```python
x = 10
y = 20

if x > 5:
    if y > 15:
        print("A")
    else:
        print("B")
else:
    print("C")
```

1. A
2. B
3. C
4. A B

---

## 🔑 Quiz Answers and Explanations (퀴즈 정답 및 해설)

**Question 1 Answer: 3**
`x > 5` is true (10 > 5), so "A" is printed. Then `print("B")` is outside the if block, so it always executes and "B" is also printed. Result: "A" and "B" on separate lines.

`x > 5`는 참이므로 "A"가 출력됩니다. 그 다음 `print("B")`는 if문 밖에 있으므로 조건과 관계없이 항상 실행되어 "B"도 출력됩니다.

**Question 2 Answer: 1, 3, 4**
Since `score = 85`, the first condition `score >= 90` is false. The second condition `score >= 80` is true, so "B" is printed and the remaining elif and else are skipped. Only one block executes in elif-else structure.

`score = 85`이므로 첫 번째 조건은 거짓입니다. 두 번째 조건이 참이므로 "B"가 출력되고, 나머지는 실행되지 않습니다.

**Question 3 Answer: 2**
Since `age = 15` and `age >= 18` is false, the else clause executes, assigning "minor" to result.

`age = 15`이고 조건이 거짓이므로 "minor"가 result에 할당됩니다.

**Question 4 Answer: 4**
The `and` operator requires both conditions to be true. Both `score >= 60` and `attendance >= 80` must be satisfied to print "Pass".

`and` 연산자는 두 조건이 모두 참이어야 전체가 참입니다.

**Question 5 Answer: 1**
`x > 5` is true (10 > 5), so the first if block executes. Inside, `y > 15` is also true (20 > 15), so "A" is printed.

`x > 5`는 참이므로 첫 번째 if 블록으로 들어갑니다. 그 안에서 `y > 15`도 참이므로 "A"가 출력됩니다.

---

## 🎯 Preview of Next Chapter (다음 장 예고)

In the next chapter, we will learn about loops. We will learn how to use for and while loops to repeat the same task multiple times. Loops will make your programs much more powerful!

다음 장에서는 반복문에 대해 배웁니다. for문과 while문을 사용하여 같은 작업을 여러 번 반복하는 방법을 학습하게 됩니다.

---

Thank you for your attention.   
Cho Jeonghyun ([peterchokr@gmail.com](mailto:peterchokr@gmail.com)). Yeungnam University College

"Produced in collaboration with Claude and Gemini."
