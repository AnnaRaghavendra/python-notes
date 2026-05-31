# Phase 1 — Python Core Fundamentals

## Goal

Learn Python syntax, logic building, functions, collections, and string manipulation.

**Duration:** ~2 Weeks

---

# 1. Variables & Data Types

## Definition

A variable stores data in memory.

```python
name = "Raghava"
age = 19
cgpa = 8.5
```

---

## Dynamic Typing

Python automatically determines the type of a variable.

```python
x = 10
x = "Hello"
```

---

## Variable Naming Rules

Valid:

```python
name = "Ravi"
student_age = 20
_marks = 95
```

Invalid:

```python
2name = "Ravi"
student-age = 20
```

Rules:

* Must start with letter or `_`
* Cannot start with number
* Cannot contain spaces
* Case-sensitive

---

## Core Data Types

| Type  | Description    | Example    |
| ----- | -------------- | ---------- |
| int   | Integer        | `10`       |
| float | Decimal Number | `3.14`     |
| str   | Text           | `"Python"` |
| bool  | Boolean        | `True`     |

---

## Input

```python
name = input("Enter name: ")
```

**Important:** `input()` always returns a string.

---

## Type Conversion

```python
int()
float()
str()
bool()
```

Examples:

```python
age = int(input())
salary = float(input())
```

---

## Multiple Assignment

```python
a, b, c = 1, 2, 3
```

---

## Variable Swapping

```python
a, b = b, a
```

---

## Useful Built-in Functions

| Function     | Purpose        |
| ------------ | -------------- |
| len()        | Count elements |
| type()       | Get type       |
| isinstance() | Type check     |

---

## Tricky Points

* `input()` returns string.
* Python is dynamically typed.
* Variable names are case-sensitive.

---

## Practice

1. Temperature Converter
2. Interest Calculator
3. Average Marks Calculator
4. BMI Calculator
5. Electricity Bill Calculator
6. Student Information Form

---

# 2. Operators

Operators perform operations on values.

---

## Arithmetic Operators

| Operator | Meaning        |
| -------- | -------------- |
| +        | Addition       |
| -        | Subtraction    |
| *        | Multiplication |
| /        | Division       |
| //       | Floor Division |
| %        | Modulus        |
| **       | Power          |

---

## Comparison Operators

| Operator | Meaning          |
| -------- | ---------------- |
| ==       | Equal            |
| !=       | Not Equal        |
| >        | Greater Than     |
| <        | Less Than        |
| >=       | Greater or Equal |
| <=       | Less or Equal    |

Returns:

```python
True
False
```

---

## Logical Operators

| Operator | Meaning           |
| -------- | ----------------- |
| and      | Both true         |
| or       | At least one true |
| not      | Reverse boolean   |

---

## Membership Operators

| Operator | Meaning        |
| -------- | -------------- |
| in       | Exists         |
| not in   | Does not exist |

Example:

```python
"py" in "python"
```

---

## Identity Operators

| Operator | Meaning          |
| -------- | ---------------- |
| is       | Same object      |
| is not   | Different object |

Common usage:

```python
value is None
```

---

## Bitwise Odd/Even Trick

```python
n & 1
```

Result:

```text
1 -> Odd
0 -> Even
```

Example:

```python
if n & 1:
    print("Odd")
else:
    print("Even")
```

---

## Operator Precedence

```text
()
**
*, /, //, %
+, -
Comparison
not
and
or
```

Use parentheses when unsure.

---

## Tricky Points

* `=` assigns value.
* `==` compares value.
* `is` is different from `==`.
* `and` / `or` return boolean results.

---

## Practice

1. Login Validation
2. Discount Calculator
3. Voting Eligibility
4. Odd/Even Checker
5. Leap Year Checker
6. Mini Calculator

---

# 3. Control Flow

Control flow determines program execution order.

---

## if

```python
if age >= 18:
    print("Eligible")
```

---

## if-else

```python
if age >= 18:
    print("Eligible")
else:
    print("Not Eligible")
```

---

## if-elif-else

```python
if marks >= 90:
    print("A")
elif marks >= 75:
    print("B")
else:
    print("C")
```

---

## Nested if

```python
if age >= 18:
    if citizen:
        print("Eligible")
```

---

## while Loop

```python
while count < 5:
    print(count)
```

Used when number of iterations is unknown.

---

## for Loop

```python
for item in collection:
    print(item)
```

Used for iteration.

---

## range()

```python
range(stop)
range(start, stop)
range(start, stop, step)
```

Examples:

```python
range(5)
range(1, 6)
range(10, 0, -1)
```

---

## break

Exit loop immediately.

```python
break
```

---

## continue

Skip current iteration.

```python
continue
```

---

## pass

Placeholder statement.

```python
pass
```

---

## match-case (Python 3.10+)

Python's switch equivalent.

```python
match choice:
    case 1:
        print("Deposit")
    case 2:
        print("Withdraw")
```

---

## Tricky Points

* `for` is preferred when iterating collections.
* `while True` is common in menu-driven programs.
* `break` exits loop completely.
* `continue` skips only current iteration.

---

## Practice

1. Grading System
2. ATM Menu
3. Number Guessing Game
4. Prime Number Checker
5. Multiplication Table
6. Pattern Printing

---

# 4. Functions

## Definition

Reusable block of code.

---

## Syntax

```python
def greet():
    print("Hello")
```

Call:

```python
greet()
```

---

## Function Types

### No Parameters, No Return

```python
def greet():
    print("Hello")
```

### Parameters, No Return

```python
def greet(name):
    print(name)
```

### No Parameters, Return

```python
def get_pi():
    return 3.14
```

### Parameters, Return

```python
def add(a, b):
    return a + b
```

---

## return

Returns value to caller.

---

## Scope

### Local Variable

Exists only inside function.

### Global Variable

Exists outside function.

---

## Default Arguments

```python
def greet(name="Guest"):
    print(name)
```

---

## Keyword Arguments

```python
show(name="Ravi", age=19)
```

---

## Multiple Return Values

```python
def calc(a, b):
    return a+b, a*b
```

Returns a tuple.

---

## Variable-Length Arguments

### *args

Multiple positional arguments.

```python
def total(*args):
    pass
```

### **kwargs

Multiple keyword arguments.

```python
def show(**kwargs):
    pass
```

---

## Tricky Points

* Python passes object references.
* Returning multiple values actually returns a tuple.
* Mutable objects can be modified inside functions.

---

## Practice

1. Calculator Functions
2. Banking System
3. Grade Calculator
4. Max Of Three Numbers
5. Student Record Functions
6. Factorial Function

---

# 5. Recursion

## Definition

A function calling itself.

---

## Components

### Base Case

Stops recursion.

### Recursive Case

Calls itself again.

---

## Example

```python
def factorial(n):

    if n == 0:
        return 1

    return n * factorial(n - 1)
```

---

## Common Recursive Problems

* Factorial
* Fibonacci
* Power Function
* Sum Of Digits
* Reverse String
* Decimal To Binary

---

## Call Stack

Each recursive call is stored on the call stack until a base case is reached.

---

## When Not To Use Recursion

Avoid when:

* Simple loops solve the problem.
* Very deep recursion is expected.
* Memory efficiency is important.

---

## Tricky Points

* Missing base case causes infinite recursion.
* Deep recursion causes `RecursionError`.
* Every recursion problem can be solved iteratively.

---

## Practice

1. Factorial
2. Fibonacci
3. Power Function
4. Sum Of Digits
5. Reverse String
6. Decimal To Binary

---

## Phase 1 Progress(part 1)

```text
✓ Variables & Data Types
✓ Operators
✓ Control Flow
✓ Functions
✓ Recursion

Next:
Collections
- Lists
- Tuples
- Sets
- Dictionaries
```
