# Chapter 8. Loop 2 (while Statement & Flow Control)

---

## 📚 Learning Objectives

After completing this chapter, you will be able to implement condition-based loops using while statements, and control loop flow using break and continue. You will also be able to solve complex problems by using nested loops.

이번 장을 마치면 여러분은 while 문으로 조건 기반 반복을 구현하고, break와 continue로 반복문의 흐름을 제어할 수 있습니다. 또한 중첩 반복문을 활용하여 복잡한 문제를 해결할 수 있습니다.

---

## 1️⃣ What is a while Loop? (while 문이란?)

A while loop repeatedly executes code as long as a condition is true. Use for loops when you know the number of repetitions, and while loops when you don't know the repetition count.

while 문은 조건이 참(True)인 동안 계속 반복하는 구문입니다. for 문은 반복 횟수를 알 때 사용하고, while 문은 반복 횟수를 모를 때 사용합니다.

```python
# while statement basic structure (while 문 기본 구조)
while condition:
    code to repeat (반복할 코드)
    # Code to make condition false is necessary! (조건을 거짓으로 만드는 코드 필요!)
```

```
while Loop vs for Loop (while 문 vs for 문)

┌──────────────┬──────────────┐
│  for Loop    │  while Loop  │
├──────────────┼──────────────┤
│Fixed count   │Condition-based│
│Uses range()  │Uses condition│
│Auto-exit     │Manual control│
└──────────────┴──────────────┘
```

### Basic Example (기본 예제)

```python
# while loop example (while 문 예제)
count = 1

while count <= 5:
    print(f"Iteration {count}")  # (반복 {count}번)
    count = count + 1  # Condition change is essential! (조건 변경 필수!)

print("Loop complete")

# Output (출력):
# Iteration 1
# Iteration 2
# Iteration 3
# Iteration 4
# Iteration 5
# Loop complete
```

⚠️ **Warning**: In while loops, you must have code to make the condition false. Otherwise, you'll be trapped in an infinite loop!

⚠️ **주의**: while 문에서는 반드시 조건을 거짓으로 만드는 코드가 필요합니다. 그렇지 않으면 무한 반복에 빠집니다!

```python
# Infinite loop example (dangerous!) (무한 반복 예제 (위험!))
# while True:
#     print("Never stops!")  # Ctrl+C to force quit (Ctrl+C로 강제 종료 필요)
```

---

## 2️⃣ while Loop Usage (while 문 활용)

### Example 1: Password Verification (예제 1: 비밀번호 확인)

A program that repeats until the correct password is entered.

올바른 비밀번호를 입력할 때까지 반복하는 프로그램입니다.

```python
# Password verification program (비밀번호 확인 프로그램)
print("🔐" + "=" * 38 + "🔐")
print("   Login System")
print("🔐" + "=" * 38 + "🔐")

correct_password = "python123"
max_attempts = 3
attempts = 0

print(f"\nEnter password (Max {max_attempts} attempts)")

while attempts < max_attempts:
    password = input(f"\nAttempt {attempts + 1}/{max_attempts}: ")
  
    if password == correct_password:
        print("\n✅ Login successful!")
        print("Welcome! 🎉")
        break  # Exit loop (반복 종료)
    else:
        attempts = attempts + 1
        remaining = max_attempts - attempts
    
        if remaining > 0:
            print(f"❌ Incorrect password.")
            print(f"Remaining attempts: {remaining}")
        else:
            print("\n🚫 Login failed!")
            print("Maximum attempts exceeded.")
```


---

## 3️⃣ break - Stop Loop (break - 반복 중단)

`break` immediately terminates the loop.

`break`는 반복문을 즉시 종료합니다.

```python
# break example (break 예제)
for i in range(1, 11):
    if i == 5:
        break  # Stop when i equals 5 (i가 5가 되면 반복 중단)
    print(i)

# Output: 1, 2, 3, 4
```

```
How break Works (break의 동작)

    ┌─────────┐
    │ Start   │
    │ Loop    │
    └────┬────┘
         │
     ┌───▼─────┐
     │Condition│
     │ Check   │
     └────┬────┘
          │
     ┌────┴────┐
    Yes        No
     │          │
 ┌───▼──┐   ┌──▼───┐
 │break!│   │Continue
 └───┬──┘   └──┬────┘
     │         │
     ▼         │
  Exit    ─────┘
```


---

## 4️⃣ continue - Next Iteration (continue - 다음 반복으로)

`continue` skips the current iteration and moves to the next one.

`continue`는 현재 반복을 건너뛰고 다음 반복으로 넘어갑니다.

```python
# continue example (continue 예제)
for i in range(1, 6):
    if i == 3:
        continue  # Skip when i equals 3 (i가 3일 때는 건너뛰기)
    print(i)

# Output: 1, 2, 4, 5 (3 is not printed)
```

```
How continue Works (continue의 동작)

    ┌─────────┐
    │ Start   │
    │ Loop    │
    └────┬────┘
         │
     ┌───▼─────┐
     │Condition│
     │ Check   │
     └────┬────┘
          │
     ┌────┴────┐
    Yes        No
     │          │
 ┌───▼────┐  ┌─▼──┐
 │continue │  │Run │
 └────┬────┘  └──┬─┘
      │          │
      └────┬─────┘
           │
       Next Iteration
```

### Example 2: Print Only Even Numbers (예제 2: 짝수만 출력)

A program that prints only even numbers from 1 to 20.

1부터 20까지 중 짝수만 출력하는 프로그램입니다.

```python
# Print even numbers only (짝수만 출력)
print("📊 Even numbers from 1 to 20:")
print("-" * 40)

for i in range(1, 21):
    if i % 2 != 0:  # If odd (홀수면)
        continue    # Skip (건너뛰기)
    print(i, end=" ")

print("\n" + "-" * 40)
```

---

## 5️⃣ while True and break Combination (while True와 break 조합)

Creating infinite loops and breaking out with specific conditions is a very useful pattern.

무한 반복을 만들고 특정 조건에서 break로 빠져나오는 패턴은 매우 유용합니다.

### Example 3: Shopping Cart (예제 3: 쇼핑 장바구니)

A program that adds products as desired and calculates the total when done.

원하는 만큼 상품을 담고, 종료 신호를 받으면 총 금액을 계산하는 프로그램입니다.

```python
# Shopping cart program (쇼핑 장바구니 프로그램)
print("🛒" + "=" * 38 + "🛒")
print("   Shopping Cart")
print("🛒" + "=" * 38 + "🛒")

print("\nAdd products (Exit: 'q')")
print("-" * 40)

total_price = 0
item_count = 0

while True:
    product = input("\nProduct name (Exit: q): ")
  
    # Exit condition (종료 조건)
    if product == 'q' or product == 'Q':
        break
  
    # Ignore empty input (빈 입력 무시)
    if product == "":
        continue
  
    price = int(input("Price: $"))
  
    # Ignore if price is 0 or less (가격이 0원 이하면 무시)
    if price <= 0:
        print("⚠️ Please enter a valid price.")
        continue
  
    item_count = item_count + 1
    total_price = total_price + price
    print(f"✓ {product} added (${price})")

# Display results (결과 출력)
print("\n" + "=" * 40)
print("Cart Summary")
print("=" * 40)
print(f"Total items: {item_count}")
print(f"Subtotal: ${total_price}")

# Calculate delivery fee (배달비 계산)
if total_price >= 30:
    delivery = 0
    print(f"Delivery fee: FREE")
else:
    delivery = 3
    print(f"Delivery fee: ${delivery}")

final_price = total_price + delivery
print("-" * 40)
print(f"Final payment: ${final_price}")
print("=" * 40)
```

---

## 6️⃣ Nested Loops and Flow Control (중첩 반복문과 제어문)

When using break and continue in nested loops, caution is needed.

중첩된 반복문에서 break와 continue를 사용할 때는 주의가 필요합니다.

```python
# break in nested loops (중첩 반복문에서 break)
for i in range(1, 4):
    print(f"\nOuter loop: {i}")
  
    for j in range(1, 4):
        if j == 2:
            break  # Only inner loop ends (안쪽 반복만 종료)
        print(f"  Inner loop: {j}")

# Output (출력):
# Outer loop: 1
#   Inner loop: 1
# Outer loop: 2
#   Inner loop: 1
# Outer loop: 3
#   Inner loop: 1
```

---



## 📝 Summary of Key Concepts (핵심 개념 정리)

A while loop repeats as long as a condition is true and is useful when you don't know the repetition count. In while loops, you must have code to make the condition false to avoid infinite loops.

while 문은 조건이 참인 동안 계속 반복하며, 반복 횟수를 모를 때 유용합니다. while 문에서는 반드시 조건을 거짓으로 만드는 코드가 있어야 무한 반복을 피할 수 있습니다.

`break` immediately terminates the loop, and `continue` skips the current iteration and moves to the next one. Combining `while True` with `break` allows flexible loop control.

`break`는 반복문을 즉시 종료하고, `continue`는 현재 반복을 건너뛰고 다음 반복으로 넘어갑니다. `while True`와 `break`를 조합하면 유연한 반복 제어가 가능합니다.

In nested loops, break only terminates the innermost loop. Combining loops and conditionals with flow control allows complex program logic.

중첩 반복문에서 break는 가장 안쪽 반복문만 종료합니다. 반복문과 조건문, 제어문을 잘 조합하면 복잡한 프로그램 로직을 구현할 수 있습니다.

---

## 💡 Practical Assignments (실습 과제)

### Assignment 1: ATM Machine (과제 1: ATM 기계)

Write an ATM program with balance check, deposit, and withdrawal functions.

잔액 확인, 입금, 출금 기능이 있는 ATM 프로그램을 작성하세요.

```python
# Hint
balance = 10000  # Initial balance (초기 잔액)

while True:
    print("\n1. Check balance")
    print("2. Deposit")
    print("3. Withdraw")
    print("4. Exit")
  
    choice = input("\nSelect: ")
  
    if choice == "1":
        # Print balance
        pass
    elif choice == "2":
        # Process deposit
        pass
    elif choice == "3":
        # Process withdrawal (check balance)
        pass
    elif choice == "4":
        break
```

### Assignment 2: Number Baseball Game (과제 2: 숫자 야구 게임)

Create a game to guess the 3-digit number the computer is thinking of.

컴퓨터가 생각한 3자리 숫자를 맞추는 게임을 만드세요.

```python
# Hint
import random
# Generate 3 different numbers between 1-9
# Get user input
# Calculate strikes and balls
# End game on 3 strikes
```

---

## ✅ Quiz (퀴즈)

### [Beginner] Question 1

How many times is "*" printed?

다음 코드의 출력 횟수는?

```python
count = 0
while count < 3:
    print("*")
    count = count + 1
```

1. 2 times
2. 3 times
3. 4 times
4. Infinite loop

### [Intermediate] Question 2

What is the output?

다음 코드의 출력 결과는?

```python
for i in range(1, 6):
    if i == 3:
        break
    print(i)
```

1. 1 2 3
2. 1 2
3. 3 4 5
4. 1 2 3 4 5

### [Intermediate] Question 3

What is the output?

다음 코드의 출력 결과는?

```python
for i in range(1, 6):
    if i == 3:
        continue
    print(i)
```

1. 1 2 4 5
2. 1 2 3 4 5
3. 3
4. 1 2

### [Advanced] Question 4

What does this code print?

다음 코드는 무엇을 출력할까요?

```python
count = 1
while count <= 5:
    if count == 3:
        count = count + 1
        continue
    print(count)
    count = count + 1
```

1. 1 2 3 4 5
2. 1 2 4 5
3. 1 2 3 4
4. Infinite loop

### [Advanced] Question 5

What is the difference between break and continue?

break와 continue의 차이점은?

```python
1. break exits loop, continue goes to next iteration
2. break skips, continue exits
3. Same function
4. Only break works in while
```

1. 1번
2. 2번
3. 3번
4. 4번

---

## 🔑 Quiz Answers and Explanations (퀴즈 정답 및 해설)

**Question 1 Answer: 2**
count is 0, 1, 2, so it repeats 3 times. When count becomes 3, the condition `count < 3` becomes false and the loop ends.

count가 0, 1, 2일 때 3번 반복됩니다. count가 3이 되면 조건이 거짓이 되어 반복이 종료됩니다.

**Question 2 Answer: 2**
When i is 1, 2, it prints. When i is 3, break terminates the loop. Result: "1 2"

i가 1, 2일 때 출력되고, i가 3이 되면 break로 반복이 종료됩니다.

**Question 3 Answer: 1**
When i is 3, continue skips the print statement, so only 1, 2, 4, 5 are printed.

i가 3일 때 continue로 print를 건너뛰므로, 1, 2, 4, 5만 출력됩니다.

**Question 4 Answer: 2**
When count is 1, 2, it prints. At 3, continue is executed and count becomes 4, so 4, 5 are printed. Result: "1 2 4 5"

count가 1, 2일 때 출력되고, 3일 때는 continue로 건너뛰므로 4, 5가 출력됩니다.

**Question 5 Answer: 1**
break completely terminates the loop, while continue skips only the current iteration and continues the next one.

break는 반복문을 완전히 종료하고, continue는 현재 반복만 건너뛰고 다음 반복을 계속합니다.

---

## 🎯 Preview of Next Chapter (다음 장 예고)

In the next chapter, we will learn the basics of functions. We will learn how to create functions from frequently used code and reuse them. Understanding functions will allow you to organize and manage code systematically!

다음 장에서는 함수의 기본에 대해 배웁니다. 자주 사용하는 코드를 함수로 만들어 재사용하는 방법을 학습하게 됩니다.

---

Thank you for your attention.  
Cho Jeonghyun ([peterchokr@gmail.com](mailto:peterchokr@gmail.com)). Yeungnam University College

"Produced in collaboration with Claude and Gemini."
