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

# 6. Collections

Collections store multiple values in a single variable.

Python provides four primary collection types:

| Collection | Ordered | Mutable | Duplicates | Indexing |
| ---------- | ------- | ------- | ---------- | -------- |
| List       | Yes     | Yes     | Yes        | Yes      |
| Tuple      | Yes     | No      | Yes        | Yes      |
| Set        | No*     | Yes     | No         | No       |
| Dictionary | Yes     | Yes     | Keys No    | By Key   |

* Do not rely on set ordering.

---

# Mutable vs Immutable

## Mutable

Can be modified after creation.

Examples:

```python
list
set
dictionary
```

---

## Immutable

Cannot be modified after creation.

Examples:

```python
int
float
bool
str
tuple
```

---

## Tricky Point

```python
t = ([1,2], [3,4])
```

Valid:

```python
t[0].append(5)
```

Reason:

```text
Tuple itself is immutable.
Inner lists remain mutable.
```

---

# Lists

## Definition

Ordered, mutable collection.

```python
nums = [10, 20, 30]
```

---

## Why Lists Matter

Lists are the most commonly used collection in Python.

Used for:

* Data storage
* Iteration
* Problem solving
* APIs
* AI preprocessing

---

## Creation

```python
nums = [1,2,3]

data = [1, "hello", True]
```

Mixed types are allowed.

---

## Indexing

```python
nums[0]
nums[1]
```

---

## Negative Indexing

```python
nums[-1]
nums[-2]
```

| Index | Meaning      |
| ----- | ------------ |
| -1    | Last element |
| -2    | Second last  |
| -3    | Third last   |

---

## Slicing

Syntax:

```python
list[start:end]
```

End index is excluded.

Examples:

```python
nums[1:4]
nums[:3]
nums[2:]
nums[:]
nums[::-1]
```

---

## Iteration

### Preferred

```python
for item in nums:
    print(item)
```

### Using Index

```python
for i in range(len(nums)):
    print(nums[i])
```

Use when index is required.

---

## Nested Lists

```python
matrix = [
    [1,2,3],
    [4,5,6]
]
```

Access:

```python
matrix[1][2]
```

---

## List Methods

### append()

Add element at end.

```python
nums.append(100)
```

---

### insert()

Insert at index.

```python
nums.insert(1, 50)
```

---

### remove()

Remove by value.

```python
nums.remove(20)
```

---

### pop()

Remove by index and return value.

```python
nums.pop()
nums.pop(2)
```

---

### index()

Return first position.

```python
nums.index(50)
```

---

### count()

Count occurrences.

```python
nums.count(10)
```

---

### sort()

Sort list in-place.

```python
nums.sort()
```

Descending:

```python
nums.sort(reverse=True)
```

---

### reverse()

Reverse list in-place.

```python
nums.reverse()
```

---

### clear()

Remove all elements.

```python
nums.clear()
```

---

### copy()

Create shallow copy.

```python
nums.copy()
```

---

## List Comprehension

Pythonic list creation.

Traditional:

```python
squares = []

for i in range(5):
    squares.append(i * i)
```

Pythonic:

```python
squares = [i*i for i in range(5)]
```

Conditional:

```python
evens = [x for x in nums if x % 2 == 0]
```

---

## Tricky Points

### append() vs insert()

```python
append()
```

Always end.

```python
insert()
```

Specific position.

---

### remove() vs pop()

```python
remove(value)
```

Removes value.

```python
pop(index)
```

Removes position.

---

### Empty List

```python
nums = []
```

No valid indexes exist.

Use:

```python
nums.append(value)
```

not:

```python
nums[0] = value
```

---

## Important Built-ins

```python
len(nums)
min(nums)
max(nums)
sum(nums)
sorted(nums)
```

---

## Practice

1. Reverse List
2. Second Largest Number
3. Remove Duplicates
4. Frequency Counter
5. Rotate List
6. Merge Sorted Lists

---

# Tuples

## Definition

Ordered, immutable collection.

```python
point = (10, 20)
```

---

## Why Tuples Matter

Use tuples when data should not change.

Examples:

* Coordinates
* RGB values
* Database rows
* Function returns

---

## Creation

```python
t = (1,2,3)
```

---

## Single Element Tuple

Important:

```python
t = (5,)
```

Not:

```python
t = (5)
```

Reason:

```text
Comma creates tuple.
```

---

## Indexing

```python
t[0]
t[-1]
```

---

## Slicing

```python
t[1:4]
```

---

## Iteration

```python
for item in t:
    print(item)
```

---

## Packing

```python
t = 1,2,3
```

---

## Unpacking

```python
a,b,c = (1,2,3)
```

---

## Variable Swapping

```python
a,b = b,a
```

Uses tuple unpacking internally.

---

## Returning Multiple Values

```python
def calc(a,b):
    return a+b, a*b
```

---

## Tuple Methods

### count()

Count occurrences.

```python
t.count(2)
```

---

### index()

Find position.

```python
t.index(3)
```

---

## Tricky Points

### Immutable

```python
t[0] = 10
```

Error.

---

### Mutable Objects Inside Tuple

```python
t = ([1,2], [3,4])
```

Allowed:

```python
t[0].append(5)
```

---

## Practice

1. Tuple Unpacking
2. Variable Swap
3. Multiple Return Values
4. Nested Tuple Traversal
5. Manual Min/Max

---

# Sets

## Definition

Unordered collection of unique elements.

```python
s = {1,2,3}
```

---

## Why Sets Matter

Used for:

* Fast lookup
* Duplicate removal
* Set operations
* Membership testing

---

## Empty Set

Correct:

```python
s = set()
```

Incorrect:

```python
s = {}
```

Creates dictionary.

---

## Duplicate Removal

```python
{1,2,2,3}
```

Becomes:

```python
{1,2,3}
```

---

## Membership

```python
if 5 in s:
```

Very fast.

---

## Iteration

```python
for item in s:
    print(item)
```

---

## Set Methods

### add()

Insert element.

```python
s.add(10)
```

---

### remove()

Remove element.

```python
s.remove(10)
```

Raises error if missing.

---

### discard()

Safe remove.

```python
s.discard(10)
```

---

### pop()

Remove arbitrary element.

```python
s.pop()
```

---

### clear()

Remove everything.

```python
s.clear()
```

---

## Set Operations

Assume:

```python
A = {1,2,3}
B = {3,4,5}
```

---

### Union

All unique elements.

```python
A | B
```

or

```python
A.union(B)
```

---

### Intersection

Common elements.

```python
A & B
```

---

### Difference

Elements in A but not B.

```python
A - B
```

---

### Symmetric Difference

Non-common elements.

```python
A ^ B
```

---

## Set Relationships

### Subset

All elements of A exist in B.

```python
A.issubset(B)
```

or

```python
A <= B
```

Alternative logic:

```python
A - B == set()
```

---

### Proper Subset

```python
A < B
```

---

### Disjoint

No common elements.

```python
A.isdisjoint(B)
```

Alternative logic:

```python
A & B == set()
```

---

## Tricky Points

### Elements Must Be Immutable

Valid:

```python
{1, "hello", (1,2)}
```

Invalid:

```python
{[1,2]}
```

---

### Sets Have No Indexing

```python
s[0]
```

Error.

---

## Practice

1. Remove Duplicates
2. Unique Words Counter
3. Common Elements
4. Subset Check
5. Disjoint Check

---

# Dictionaries

## Definition

Stores data as:

```text
key -> value
```

pairs.

---

## Why Dictionaries Matter

Most important collection in Python.

Used in:

* APIs
* JSON
* Databases
* Caching
* AI preprocessing
* Frequency counting

---

## Creation

```python
student = {
    "name": "Raghava",
    "age": 19
}
```

---

## Access Values

```python
student["name"]
```

---

## Add Entry

```python
student["city"] = "Hyderabad"
```

---

## Update Entry

```python
student["age"] = 20
```

---

## Delete Entry

```python
del student["age"]
```

or

```python
student.pop("age")
```

---

## Membership

Checks keys only.

```python
"name" in student
```

---

## Iteration

### Keys

```python
for key in student:
```

---

### Values

```python
for value in student.values():
```

---

### Key + Value

Most important.

```python
for key, value in student.items():
```

---

## Dictionary Methods

### keys()

Return keys.

```python
student.keys()
```

---

### values()

Return values.

```python
student.values()
```

---

### items()

Return key-value pairs.

```python
student.items()
```

---

### get()

Safe access.

```python
student.get("name")
```

Missing key returns:

```python
None
```

instead of error.

---

### update()

Merge or update values.

```python
student.update({"city": "Delhi"})
```

---

### clear()

Remove all entries.

```python
student.clear()
```

---

## Frequency Counter Pattern

Most important dictionary application.

Traditional:

```python
freq = {}

for item in data:
    if item in freq:
        freq[item] += 1
    else:
        freq[item] = 1
```

Pythonic:

```python
freq[item] = freq.get(item, 0) + 1
```

---

## Dictionary Keys

Keys must be immutable.

Valid:

```python
{
    "name": "Ravi",
    1: "one",
    (1,2): "tuple"
}
```

Invalid:

```python
{
    [1,2]: "list"
}
```

---

## Tricky Points

### {} Creates Dictionary

```python
{}
```

Dictionary, not set.

---

### Membership Checks Keys

```python
"name" in student
```

Checks keys only.

---

### Fast Lookup

```python
student["name"]
```

Much faster than searching lists manually.

---

## Practice

1. Student Dictionary
2. Frequency Counter
3. Word Frequency Counter
4. Character Frequency Counter


# 7. Strings

## Definition

A string is an immutable sequence of characters.

```python
name = "Python"
```

Strings are used everywhere:

* User input
* Files
* APIs
* JSON
* URLs
* Databases
* AI prompts

---

## Creation

```python
s = "Python"

s = 'Python'

s = """Multi-line
String"""
```

---

## String Immutability

Strings cannot be modified after creation.

Invalid:

```python
s = "Python"

s[0] = "J"
```

Error:

```text
TypeError
```

Create a new string instead:

```python
s = "J" + s[1:]
```

---

## Indexing

Access characters using positions.

```python
s = "Python"

s[0]
s[1]
s[-1]
s[-2]
```

| Index | Meaning               |
| ----- | --------------------- |
| 0     | First character       |
| 1     | Second character      |
| -1    | Last character        |
| -2    | Second last character |

---

## Slicing

Syntax:

```python
string[start:end]
```

End index is excluded.

Examples:

```python
s[1:4]
s[:3]
s[2:]
s[:]
s[::-1]
```

Common Uses:

```python
s[::-1]
```

Reverse string.

```python
s[:]
```

Copy string.

---

## Iteration

### Preferred

```python
for ch in s:
    print(ch)
```

### Using Index

```python
for i in range(len(s)):
    print(s[i])
```

---

## Membership

```python
"py" in "python"
```

```python
"java" not in "python"
```

Returns:

```python
True
False
```

---

## Concatenation

Join strings.

```python
first = "Hello"
second = "World"

result = first + second
```

---

## Repetition

```python
"-" * 20
```

Output:

```text
--------------------
```

---

## String Methods

### lower()

Convert to lowercase.

```python
s.lower()
```

---

### upper()

Convert to uppercase.

```python
s.upper()
```

---

### capitalize()

First letter uppercase.

```python
s.capitalize()
```

---

### title()

Capitalize every word.

```python
s.title()
```

---

### strip()

Remove spaces from both ends.

```python
s.strip()
```

---

### lstrip()

Remove left spaces.

```python
s.lstrip()
```

---

### rstrip()

Remove right spaces.

```python
s.rstrip()
```

---

### replace()

Replace text.

```python
s.replace("a", "x")
```

---

### split()

Convert string to list.

```python
text.split()
```

Example:

```python
"I love Python".split()
```

Result:

```python
['I', 'love', 'Python']
```

---

### join()

Convert list to string.

```python
"-".join(words)
```

Example:

```python
["A","B","C"]
```

Result:

```text
A-B-C
```

---

### find()

Return first occurrence index.

```python
s.find("th")
```

Returns:

```python
index
```

or

```python
-1
```

if not found.

---

### count()

Count occurrences.

```python
s.count("a")
```

---

### startswith()

Check prefix.

```python
s.startswith("Py")
```

---

### endswith()

Check suffix.

```python
s.endswith(".txt")
```

---

## Character Testing Methods

### isalpha()

Letters only.

```python
"Python".isalpha()
```

---

### isdigit()

Digits only.

```python
"123".isdigit()
```

---

### isalnum()

Letters or digits.

```python
"Python123".isalnum()
```

---

### islower()

All lowercase.

```python
"python".islower()
```

---

### isupper()

All uppercase.

```python
"PYTHON".isupper()
```

---

### isspace()

Whitespace only.

```python
"   ".isspace()
```

---

## ASCII Functions

### ord()

Character → ASCII value

```python
ord("A")
```

Result:

```python
65
```

---

### chr()

ASCII value → Character

```python
chr(65)
```

Result:

```python
A
```

---

## String Formatting

### f-Strings (Preferred)

```python
name = "Ravi"
age = 20

print(f"{name} is {age} years old")
```

---

### format()

```python
print("{} is {}".format(name, age))
```

---

## Building Strings

### Simple Method

```python
result += ch
```

Good for small programs.

---

### Preferred for Large Data

```python
"".join(chars)
```

More efficient.

---

# Pythonic Patterns

## Counting Pattern (Important)

Count uppercase and lowercase letters.

```python
text = "ProGrAmMiNg"

upp = sum(
    1
    for ch in text
    if 'A' <= ch <= 'Z'
)

low = sum(
    1
    for ch in text
    if 'a' <= ch <= 'z'
)
```

Applications:

* Uppercase count
* Lowercase count
* Vowel count
* Digit count
* Conditional counting

---

## Vowel Count

```python
vowels = sum(
    1
    for ch in text.lower()
    if ch in "aeiou"
)
```

---

## Digit Count

```python
digits = sum(
    1
    for ch in text
    if ch.isdigit()
)
```

---

## Frequency Counter

```python
freq = {}

for ch in text:
    freq[ch] = freq.get(ch, 0) + 1
```

---

# Collection Comparison Table

| Feature     | List            | Tuple      | Set         | Dictionary    |
| ----------- | --------------- | ---------- | ----------- | ------------- |
| Syntax      | `[]`            | `()`       | `{}`        | `{key:value}` |
| Ordered     | Yes             | Yes        | No*         | Yes           |
| Mutable     | Yes             | No         | Yes         | Yes           |
| Duplicates  | Yes             | Yes        | No          | Keys No       |
| Indexing    | Yes             | Yes        | No          | By Key        |
| Fast Lookup | No              | No         | Yes         | Yes           |
| Use Case    | General Storage | Fixed Data | Unique Data | Mapping Data  |

* Do not rely on set ordering.

---

# Mutable vs Immutable

## Mutable Objects

Can change after creation.

| Type       |
| ---------- |
| list       |
| set        |
| dictionary |

Examples:

```python
nums[0] = 100

s.add(10)

data["age"] = 20
```

---

## Immutable Objects

Cannot change after creation.

| Type  |
| ----- |
| int   |
| float |
| bool  |
| str   |
| tuple |

Examples:

```python
s[0] = "A"     # Error

t[0] = 10      # Error
```

---

# Common Built-in Functions

These work across multiple collections.

| Function     | Purpose             |
| ------------ | ------------------- |
| len()        | Count elements      |
| min()        | Smallest value      |
| max()        | Largest value       |
| sum()        | Sum values          |
| sorted()     | Return sorted copy  |
| reversed()   | Reverse iterator    |
| enumerate()  | Index + Value       |
| zip()        | Combine collections |
| type()       | Get type            |
| isinstance() | Type check          |
| range()      | Generate sequence   |

---

## enumerate()

```python
for i, value in enumerate(nums):
    print(i, value)
```

Used when index and value are both required.

---

## zip()

```python
for name, mark in zip(names, marks):
    print(name, mark)
```

Used to iterate multiple collections together.

---

## sorted()

Returns a new sorted collection.

```python
sorted(nums)
```

Original remains unchanged.

---

## reversed()

Returns reverse iterator.

```python
reversed(nums)
```

Often converted:

```python
list(reversed(nums))
```

---

# Common Beginner Mistakes

## Lists

Wrong:

```python
nums = []

nums[0] = 10
```

Correct:

```python
nums.append(10)
```

---

## Tuples

Wrong:

```python
t = (5)
```

Correct:

```python
t = (5,)
```

---

## Sets

Wrong:

```python
s = {}
```

Creates dictionary.

Correct:

```python
s = set()
```

---

## Dictionaries

Wrong assumption:

```python
"value" in dict
```

Checks keys, not values.

---

## Strings

Wrong:

```python
s[0] = "A"
```

Strings are immutable.

---

# Recommended Practice Problems

## Lists

1. Reverse List
2. Second Largest
3. Frequency Counter
4. Rotate List
5. Merge Sorted Lists

---

## Tuples

1. Tuple Unpacking
2. Variable Swap
3. Multiple Return Values
4. Nested Tuple Traversal

---

## Sets

1. Remove Duplicates
2. Common Elements
3. Unique Words
4. Subset Check
5. Disjoint Check

---

## Dictionaries

1. Frequency Counter
2. Word Frequency Counter
3. Character Frequency Counter
4. Student Marks System
5. Topper Finder

---

## Strings

1. Reverse String
2. Count Vowels
3. Uppercase/Lowercase Count
4. Palindrome Check
5. Character Frequency
6. First Non-Repeating Character

---

# Phase 1 Completion Checklist

```text
✓ Variables & Data Types
✓ Operators
✓ Control Flow
✓ Functions
✓ Recursion
✓ Lists
✓ Tuples
✓ Sets
✓ Dictionaries
✓ Strings
```

---

# What You Can Build Now

Without OOP or frameworks, you can already build:

* CLI Calculator
* ATM System
* Student Management System
* Notes Manager
* Expense Tracker
* Contact Book
* Inventory Tracker
* Word Frequency Analyzer
* Quiz Application
* Library Management (Basic)

You now have the core Python foundation required for:

* Data Structures & Algorithms
* Intermediate Python
* Backend Development
* AI Development

5. Topper Finder

---




