# Chapter 8: Loops 2 (while Loop & Loop Control Statements) — Practice Problems

---

## 📝 Multiple Choice Questions

---

### 🟢 Beginner

**Problem 1.** How many times does the following code print?

```python
count = 0
while count < 4:
    print("*")
    count += 1
```

① 3 times
② 4 times
③ 5 times
④ Infinite loop

---

**Problem 2.** What must be present in a while loop?

① break statement
② continue statement
③ Code that makes the condition false
④ else statement

---

**Problem 3.** What is the correct description of `break`?

① Terminates the entire program
② Immediately terminates the loop
③ Skips the current iteration
④ Changes the condition

---

**Problem 4.** What is the correct description of `continue`?

① Terminates the loop
② Terminates the program
③ Skips the current iteration and moves to the next one
④ Makes the condition True

---

**Problem 5.** What is the output of the following code?

```python
for i in range(1, 6):
    if i == 3:
        break
    print(i, end=" ")
```

① 1 2 3
② 1 2
③ 1 2 3 4 5
④ 3 4 5

---

**Problem 6.** What is the output of the following code?

```python
for i in range(1, 6):
    if i == 3:
        continue
    print(i, end=" ")
```

① 1 2 4 5
② 1 2 3 4 5
③ 3
④ 1 2

---

**Problem 7.** What is the correct difference between while and for loops?

① while is condition-based, for is iteration-based
② while is faster and for is slower
③ break can only be used in while
④ continue can only be used in for

---

### 🟡 Intermediate

**Problem 8.** What is the output of the following code?

```python
count = 10
while count > 0:
    count -= 3
print(count)
```

① 0
② 1
③ -2
④ 3

---

**Problem 9.** What is the output of the following code?

```python
count = 1
while count <= 5:
    if count == 3:
        count += 1
        continue
    print(count, end=" ")
    count += 1
```

① 1 2 3 4 5
② 1 2 4 5
③ 1 2
④ Infinite loop

---

**Problem 10.** What is the final value of `total`?

```python
total = 0
num = 1
while num <= 10:
    if num % 2 == 0:
        total += num
    num += 1
```

① 25
② 30
③ 55
④ 20

---

**Problem 11.** What is the output of the following code?

```python
for i in range(1, 4):
    for j in range(1, 4):
        if j == 2:
            break
        print(f"({i},{j})", end=" ")
    print()
```

① (1,1) (2,1) (3,1) each on one line
② (1,1) (1,2) (1,3) on one line
③ All combinations printed
④ Nothing printed

---

**Problem 12.** How many times does the following code print `"Hello"`?

```python
i = 0
while i < 10:
    i += 2
    if i == 6:
        continue
    print("Hello")
```

① 3 times
② 4 times
③ 5 times
④ Infinite loop

---

### 🔴 Advanced

**Problem 13.** What is the output of the following code?

```python
n = 1
while n < 100:
    n *= 2
print(n)
```

① 64
② 128
③ 100
④ 256

---

**Problem 14.** What is the output of the following code?

```python
result = ""
for i in range(5):
    if i % 2 == 0:
        result += "A"
    else:
        result += "B"
print(result)
```

① ABABA
② AABBA
③ ABAB
④ BABAB

---

**Problem 15.** How many times does the while loop repeat in the following code?

```python
x = 256
count = 0
while x > 1:
    x //= 2
    count += 1
print(count)
```

① 7
② 8
③ 9
④ 256

---

## 📝 Short Answer Questions

---

### 🟢 Beginner

**Problem 16.** Explain the difference between while and for loops, and give examples of when each is appropriate.

---

**Problem 17.** Write the output of the following code.

```python
i = 1
while i <= 5:
    print(i * i, end=" ")
    i += 1
```

---

**Problem 18.** Explain the difference between `break` and `continue`, and write a simple example for each.

---

### 🟡 Intermediate

**Problem 19.** Write the output of the following code and explain how `while True` combined with `break` works.

```python
total = 0
count = 0
while True:
    count += 1
    total += count
    if total > 10:
        break
print(f"count: {count}, total: {total}")
```

---

**Problem 20.** Write the output of the following code and explain how `break` affects nested loops.

```python
for i in range(1, 4):
    print(f"Outer {i}: ", end="")
    for j in range(1, 6):
        if j == 3:
            break
        print(j, end=" ")
    print()
```

---

### 🔴 Advanced

**Problem 21.** Write the output of the following code and explain the step-by-step changes of each variable.

```python
x = 100
steps = 0
while x != 1:
    if x % 2 == 0:
        x //= 2
    else:
        x = x * 3 + 1
    steps += 1
    if steps > 20:
        break
print(f"x: {x}, steps: {steps}")
```

---

## 💻 Hands-On Problems

---

### 🟢 Beginner

**Problem 22.** Write a program that meets the following requirements.

> Use a while loop to print a countdown from 10 to 1, then print "Blast off!"

Output:

```
10
9
8
7
6
5
4
3
2
1
Blast off!
```

---

**Problem 23.** Write a program that meets the following requirements.

> Use a for loop and `continue` to print all numbers from 1 to 10 except multiples of 3.

Output:

```
1 2 4 5 7 8 10
```

---

**Problem 24.** Write a program that meets the following requirements.

> Use a while loop to find when the sum first exceeds 100 starting from 1, and print the number and sum.

Output:

```
When 14 is added, the sum exceeds 100.
Sum: 105
```

---

### 🟡 Intermediate

**Problem 25.** Write a program that meets the following requirements.

> Use `while True` and `break` to create a simple menu program.
>
> - Menu: 1. Greeting  2. Calculate (sum of two numbers)  3. Exit
> - Selection 1: Print "Hello!"
> - Selection 2: Input two numbers and print their sum
> - Selection 3: Print "Program terminated." and exit
> - Invalid input: Print "Please select a valid menu." and continue

Output example:

```
=== Menu ===
1. Greeting
2. Calculate
3. Exit
Select: 1
Hello!

=== Menu ===
1. Greeting
2. Calculate
3. Exit
Select: 2
First number: 10
Second number: 20
Sum: 30

=== Menu ===
1. Greeting
2. Calculate
3. Exit
Select: 3
Program terminated.
```

---

### 🔴 Advanced

**Problem 26.** Write a program that meets the following requirements.

> Use nested for loops and conditional statements to receive starting and ending multiplication table numbers using `input()`, and print the multiplication tables in **horizontal format**.
> Each table should be vertically aligned.

Output example (Start: 2, End: 5):

```
[2×]       [3×]       [4×]       [5×]     
2×1= 2    3×1= 3    4×1= 4    5×1= 5  
2×2= 4    3×2= 6    4×2= 8    5×2=10  
2×3= 6    3×3= 9    4×3=12    5×3=15  
2×4= 8    3×4=12    4×4=16    5×4=20  
2×5=10    3×5=15    4×5=20    5×5=25  
2×6=12    3×6=18    4×6=24    5×6=30  
2×7=14    3×7=21    4×7=28    5×7=35  
2×8=16    3×8=24    4×8=32    5×8=40  
2×9=18    3×9=27    4×9=36    5×9=45  
```

---

---

# 🔑 Answer Key and Explanations

---

## 📝 Multiple Choice Answers

---

### 🟢 Beginner

**Problem 1. Answer: ② 4 times**

The loop repeats when `count` is 0, 1, 2, 3 (4 times). When `count` becomes 4, `count < 4` is `False`, so the loop terminates.

---

**Problem 2. Answer: ③ Code that makes the condition false**

Without code to make the condition false, a while loop will loop infinitely. Therefore, the loop body must contain code to eventually make the condition `False`.

---

**Problem 3. Answer: ② Immediately terminates the loop**

`break` immediately exits the current loop (either for or while) and continues with the code after the loop. It doesn't terminate the entire program.

---

**Problem 4. Answer: ③ Skips the current iteration and moves to the next one**

`continue` skips the remaining code in the current iteration and immediately jumps to the next iteration. The loop continues.

---

**Problem 5. Answer: ② 1 2**

When `i` is 1, 2, the code prints. When `i` becomes 3, `break` immediately terminates the loop, so 3 is never printed.

---

**Problem 6. Answer: ① 1 2 4 5**

When `i` is 3, `continue` skips the `print()` statement and jumps to the next iteration (`i=4`). The rest (1, 2, 4, 5) are printed normally.

---

**Problem 7. Answer: ① while is condition-based, for is iteration-based**

`for` repeats a predetermined number of times with `range()`, while `while` repeats as long as a condition is true. Both support `break` and `continue`.

---

### 🟡 Intermediate

**Problem 8. Answer: ③ -2**

`count` changes: 10 → 7 → 4 → 1 → -2. When `count = 1`, `1 > 0` is true, so it repeats once more: `1 - 3 = -2`. Then `-2 > 0` is `False`, so the loop terminates.

---

**Problem 9. Answer: ② 1 2 4 5**

When `count=3`, `count += 1` (becomes 4) executes before `continue`, skipping the `print()`. Then `count=4` and continues normally. Since `count` was incremented before `continue`, there's no infinite loop.

---

**Problem 10. Answer: ② 30**

Add only even numbers from 1-10: `2+4+6+8+10 = 30`.

---

**Problem 11. Answer: ① (1,1) (2,1) (3,1) each on one line**

`break` in the inner loop only terminates the inner loop, not the outer loop. For each `i`, only `j=1` is printed before `j=2` triggers `break`.

---

**Problem 12. Answer: ② 4 times**

`i` starts at 0. Each iteration: `i += 2`. Changes: 0→2(print)→4(print)→6(continue, skip)→8(print)→10(print, then condition fails). Only when `i=6` does `continue` skip the `print()`, so 4 times total.

---

### 🔴 Advanced

**Problem 13. Answer: ② 128**

`n` doubles each iteration: 1→2→4→8→16→32→64→128. When `n=64`, `64 < 100` is true, so `64*2=128`. When `n=128`, `128 < 100` is `False`, so the loop terminates.

---

**Problem 14. Answer: ① ABABA**

`range(5)` gives 0, 1, 2, 3, 4. Even indices (0,2,4) → 'A', odd indices (1,3) → 'B'. Result: A,B,A,B,A → `"ABABA"`.

---

**Problem 15. Answer: ② 8**

Divide 256 by 2 repeatedly: 256→128→64→32→16→8→4→2→1. This takes 8 divisions. Since 256 = 2⁸, log₂(256) = 8.

---

## 📝 Short Answer Key

---

### 🟢 Beginner

**Problem 16. Model Answer:**

**for loop:**

- Suitable for **predetermined number of iterations**.
- Used with `range()` to specify exact repetition count.
- Examples: Print multiplication tables, iterate through lists, calculate sum from 1 to 100.

**while loop:**

- **Condition-based** repetition, when iteration count is unknown.
- Repeats until a specific condition becomes false.
- Examples: Repeat until correct password is entered, repeat until target amount is reached, menu loop until user exits.

---

**Problem 17. Model Answer:**

```
1 4 9 16 25
```

For `i` from 1 to 5, calculate `i*i`: 1×1=1, 2×2=4, 3×3=9, 4×4=16, 5×5=25.

---

**Problem 18. Model Answer:**

**break:** **Completely and immediately terminates** the loop. Execution continues with code after the loop.

```python
for i in range(1, 6):
    if i == 3:
        break
    print(i)  # Output: 1 2
```

**continue:** **Skips the remaining code** in the current iteration and starts the next iteration.

```python
for i in range(1, 6):
    if i == 3:
        continue
    print(i)  # Output: 1 2 4 5
```

**Key difference:** `break` ends the loop entirely, while `continue` skips just one iteration and continues looping.

---

### 🟡 Intermediate

**Problem 19. Model Answer:**

Output:

```
count: 5, total: 15
```

**Process:**

| Iteration | count | total | total > 10?   |
| --------- | ----- | ----- | ------------- |
| 1         | 1     | 1     | False         |
| 2         | 2     | 3     | False         |
| 3         | 3     | 6     | False         |
| 4         | 4     | 10    | False         |
| 5         | 5     | 15    | True → break |

`while True` creates infinite loop; the condition is checked inside and `break` is used to exit. This pattern is useful when you need **"execute first, then check condition"** behavior.

---

**Problem 20. Model Answer:**

Output:

```
Outer 1: 1 2 
Outer 2: 1 2 
Outer 3: 1 2 
```

**Explanation:** `break` **terminates only the innermost loop**. When `j == 3` in the inner loop, `break` exits just that inner loop, and the outer loop continues. For each `i` value, only `j=1, 2` are printed before the inner loop breaks.

---

### 🔴 Advanced

**Problem 21. Model Answer:**

Output:

```
x: 16, steps: 21
```

**Collatz Conjecture (3n+1 problem) process:**

| steps | x   | Operation     |
| ----- | --- | ------------- |
| 0     | 100 | (start)       |
| 1     | 50  | 100÷2 (even) |
| 2     | 25  | 50÷2 (even)  |
| 3     | 76  | 25×3+1 (odd) |
| 4     | 38  | 76÷2 (even)  |
| 5     | 19  | 38÷2 (even)  |
| 6     | 58  | 19×3+1 (odd) |
| ...   | ... | ...           |
| 20    | 5   | 10÷2 (even)  |
| 21    | 16  | 5×3+1 (odd)  |

When `steps=21`, `steps > 20` becomes true, so `break` executes. `x` hasn't reached 1 yet. This code demonstrates the Collatz Conjecture (the process eventually reaches 1) but limits iterations to 20 steps.

---

## 💻 Hands-On Solutions

---

### 🟢 Beginner

**Problem 22. Model Answer:**

```python
count = 10
while count >= 1:
    print(count)
    count -= 1
print("Blast off!")
```

Key point: Initialize `count` to 10 and decrement by 1 each iteration. When `count` becomes 0, `count >= 1` is `False` and the loop terminates.

---

**Problem 23. Model Answer:**

```python
for i in range(1, 11):
    if i % 3 == 0:
        continue
    print(i, end=" ")
```

Key point: When `i % 3 == 0` (multiples of 3), use `continue` to skip `print()`. Multiples 3, 6, 9 are excluded.

---

**Problem 24. Model Answer:**

```python
total = 0
num = 0
while total <= 100:
    num += 1
    total += num
print(f"When {num} is added, the sum exceeds 100.")
print(f"Sum: {total}")
```

Key point: Add 1, 2, 3, ... sequentially until the sum exceeds 100. Since 1+2+...+14 = 105 > 100, we stop at 14.

---

### 🟡 Intermediate

**Problem 25. Model Answer:**

```python
while True:
    print("\n=== Menu ===")
    print("1. Greeting")
    print("2. Calculate")
    print("3. Exit")
    choice = input("Select: ")

    if choice == "1":
        print("Hello!")
    elif choice == "2":
        a = int(input("First number: "))
        b = int(input("Second number: "))
        print(f"Sum: {a + b}")
    elif choice == "3":
        print("Program terminated.")
        break
    else:
        print("Please select a valid menu.")
        continue
```

Key points:

- `while True` creates infinite loop to repeatedly show menu.
- When choice is "3", `break` exits the loop.
- For invalid input, `continue` shows the menu again.

---

### 🔴 Advanced

**Problem 26. Model Answer:**

```python
start = int(input("Start: "))
end = int(input("End: "))

# Print headers
for dan in range(start, end + 1):
    print(f"[{dan}×]".ljust(10), end="")
print()

# Print multiplication table
for num in range(1, 10):
    for dan in range(start, end + 1):
        result = dan * num
        print(f"{dan}×{num}={result:<2}".ljust(10), end="")
    print()
```

Key points:

- Outer loop (`num`) controls the multiplier (1-9).
- Inner loop (`dan`) prints each table horizontally on the same line.
- `ljust(10)` aligns each column to width 10 for vertical alignment.
- `end=""` prints on same line; `print()` at end creates newline.

---


Thank you for your attention.   
Cho Jeonghyun ([peterchokr@gmail.com](mailto:peterchokr@gmail.com)). Yeungnam University College

"Produced in collaboration with Claude and Gemini."
