# Phase 3 — File Handling, JSON and CSV Files

---

# Chapter 1 — File Handling

## Why Learn File Handling?

Variables and collections store data only while the program runs.

When the program stops:

```python
students = []
```

All data is lost.

File Handling allows data to be stored permanently.

Used for:

- Configuration files
- Logs
- Student records
- Reports
- Data processing
- Persistence

---

# 1. What is a File?

A file is a collection of data stored on disk.

Examples:

```text
notes.txt
students.json
employees.csv
image.jpg
```

---

# 2. Opening a File

Syntax:

```python
open(filename, mode)
```

Example:

```python
file = open("data.txt", "r")
```

---

# 3. File Modes

| Mode | Meaning           |
| ---- | ----------------- |
| r    | Read              |
| w    | Write (overwrite) |
| a    | Append            |
| x    | Create file       |
| rb   | Read binary       |
| wb   | Write binary      |
| ab   | Append binary     |

---

## Read Mode

```python
file = open("data.txt", "r")
```

File must exist.

---

## Write Mode

```python
file = open("data.txt", "w")
```

Creates file if missing.

Deletes existing content.

---

## Append Mode

```python
file = open("data.txt", "a")
```

Adds data at the end.

Does not remove existing content.

---

## Create Mode

```python
file = open("data.txt", "x")
```

Creates new file.

Raises error if file already exists.

---

# 4. Closing Files

```python
file.close()
```

Always close files when done.

---

# 5. with Statement (Recommended)

Instead of:

```python
file = open("data.txt")
...
file.close()
```

Use:

```python
with open("data.txt", "r") as file:
    ...
```

Advantages:

- Cleaner
- Automatically closes file
- Prevents resource leaks

---

# 6. Reading Files

## read()

Reads entire file.

```python
with open("data.txt", "r") as file:
    data = file.read()
```

Returns:

```python
str
```

---

## readline()

Reads one line.

```python
line = file.readline()
```

Returns:

```python
str
```

---

## readlines()

Reads all lines.

```python
lines = file.readlines()
```

Returns:

```python
list
```

---

# 7. Writing Files

## write()

```python
file.write("Hello")
```

Writes string to file.

---

## Multiple Lines

```python
file.write("Python\n")
file.write("Java\n")
```

---

# 8. Cursor Concept

File has a cursor.

Think:

```text
Python|Java|Git
^
cursor
```

Reading moves cursor.

---

Example:

```python
file.read()
file.read()
```

Second read returns:

```text
''
```

because cursor reached end.

---

# 9. seek()

Moves cursor manually.

```python
file.seek(0)
```

Moves to beginning.

---

Example:

```python
file.read()

file.seek(0)

file.read()
```

Reads file again.

---

# 10. tell()

Returns cursor position.

```python
position = file.tell()
```

Useful for debugging.

---

# 11. Counting Lines

```python
with open("data.txt") as file:
    lines = file.readlines()

print(len(lines))
```

---

# 12. Counting Words

```python
with open("data.txt") as file:
    words = file.read().split()

print(len(words))
```

---

# 13. Binary Files (Introduction)

Text files store characters.

Binary files store bytes.

Examples:

```text
jpg
png
pdf
mp4
exe
```

Modes:

```python
rb
wb
ab
```

Learn later after mastering text files.

---

# File Handling Best Practices

- Always use `with open()`
- Use correct mode
- Close files automatically
- Use `seek()` when re-reading
- Handle file exceptions

---

# File Handling Practice Questions

1. Create a file and write three lines.
2. Read entire file using `read()`.
3. Read line-by-line using `readline()`.
4. Count number of lines.
5. Count number of words.
6. Count words in each line.
7. Copy contents from one file to another.

---

# Chapter 2 — JSON Files

## What is JSON?

JSON stands for:

```text
JavaScript Object Notation
```

A text-based format used for storing structured data.

---

## Why JSON?

Instead of:

```text
Raghava,24X51A0501,19,CSE,9.1
```

Use:

```json
{
  "name": "Raghava",
  "roll_no": "24X51A0501",
  "age": 19,
  "branch": "CSE",
  "cgpa": 9.1
}
```

Data becomes self-descriptive.

---

# JSON Data Types

| JSON   | Python    |
| ------ | --------- |
| String | str       |
| Number | int/float |
| true   | True      |
| false  | False     |
| null   | None      |
| Array  | list      |
| Object | dict      |

---

# JSON Object

Equivalent to Python dictionary.

JSON:

```json
{
  "name": "Raghava"
}
```

Python:

```python
{
    "name": "Raghava"
}
```

---

# JSON Array

Equivalent to Python list.

JSON:

```json
["Python", "Java"]
```

Python:

```python
[
    "Python",
    "Java"
]
```

---

# Import JSON Module

```python
import json
```

---

# json.dump()

Save Python object into JSON file.

Syntax:

```python
json.dump(data, file)
```

Example:

```python
with open("students.json", "w") as file:
    json.dump(students, file)
```

---

# indent Parameter

```python
json.dump(students, file, indent=4)
```

Makes JSON readable.

---

# json.load()

Load JSON file into Python object.

Syntax:

```python
data = json.load(file)
```

Example:

```python
with open("students.json", "r") as file:
    students = json.load(file)
```

---

# dump vs load

## dump

```text
Python Object
↓
JSON File
```

---

## load

```text
JSON File
↓
Python Object
```

---

# Common JSON Structure

Most common real-world structure:

```python
[
    {
        "name": "Raghava",
        "cgpa": 9.1
    },
    {
        "name": "Hima",
        "cgpa": 8.7
    }
]
```

List of dictionaries.

---

# JSON Best Practices

- Always use `indent`
- Store structured data
- Prefer JSON over custom text formats
- Validate loaded data
- Use exception handling for corrupted JSON

---

# JSON Practice Questions

1. Save a dictionary into JSON.
2. Load a dictionary from JSON.
3. Save a list into JSON.
4. Load a list from JSON.
5. Save a list of dictionaries.
6. Add a record and save again.
7. Delete a record and save again.

---

# Chapter 3 — CSV Files

## What is CSV?

CSV stands for:

```text
Comma Separated Values
```

Used for tabular data.

Example:

```text
name,age,cgpa
Raghava,19,9.1
Hima,20,8.7
```

---

# Why CSV?

Used for:

- Excel data
- Reports
- Datasets
- Data Science
- Data Exchange

---

# CSV Module

```python
import csv
```

---

# csv.reader()

Reads CSV rows.

Example:

```python
import csv

with open("students.csv") as file:
    reader = csv.reader(file)

    for row in reader:
        print(row)
```

Output:

```python
['name', 'age']
['Raghava', '19']
```

---

# csv.writer()

Writes CSV rows.

Example:

```python
import csv

with open("students.csv", "w", newline="") as file:
    writer = csv.writer(file)

    writer.writerow(["name", "age"])
    writer.writerow(["Raghava", 19])
```

---

# DictReader

Reads rows as dictionaries.

Example:

```python
reader = csv.DictReader(file)
```

Output:

```python
{
    "name": "Raghava",
    "age": "19"
}
```

---

# DictWriter

Writes dictionaries directly.

Example:

```python
writer = csv.DictWriter(
    file,
    fieldnames=["name", "age"]
)
```

---

# CSV vs JSON

| Feature         | CSV       | JSON         |
| --------------- | --------- | ------------ |
| Structure       | Tabular   | Hierarchical |
| Human Readable  | Yes       | Yes          |
| Nested Data     | No        | Yes          |
| Excel Friendly  | Excellent | Poor         |
| APIs            | Rare      | Very Common  |
| Python Projects | Sometimes | Very Common  |

---

# When to Use CSV

Use CSV for:

- Tables
- Reports
- Excel exports
- Datasets

Use JSON for:

- Applications
- APIs
- Configuration files
- Structured storage

---

# CSV Practice Questions

1. Create a CSV file with student data.
2. Read CSV rows using `csv.reader()`.
3. Count rows in a CSV file.
4. Find student with highest marks.
5. Write student records using `csv.writer()`.
6. Read CSV using `DictReader`.
7. Write dictionaries using `DictWriter`.

---

# Quick Revision

```text
FILE HANDLING

open()
read()
readline()
readlines()
write()
seek()
tell()
with open()

JSON

import json
json.dump()
json.load()
indent

CSV

import csv
csv.reader()
csv.writer()
csv.DictReader()
csv.DictWriter()

TXT → Simple text
JSON → Structured data
CSV → Tabular data
```
# Phase 3 — Exception Handling (Python)

## Why Learn Exception Handling?

Programs should not crash when unexpected situations occur.

Examples:

* User enters invalid input
* File does not exist
* Division by zero
* Invalid list index
* Missing dictionary key

Exception Handling allows us to:

* Detect errors
* Handle errors gracefully
* Keep the program running
* Show meaningful messages to users

---

# 1. What is an Exception?

An Exception is an error that occurs while the program is running.

Example:

```python
num = int("abc")
```

Output:

```text
ValueError: invalid literal for int()
```

Python stops execution because it cannot convert `"abc"` into an integer.

---

# 2. Syntax Errors vs Exceptions

## Syntax Error

Program cannot start.

```python
print("Hello"
```

Output:

```text
SyntaxError
```

---

## Exception

Program starts, then crashes while running.

```python
num = int("abc")
```

Output:

```text
ValueError
```

---

# 3. Why Exceptions Exist

Without exception handling:

```python
print("Start")

num = int("abc")

print("End")
```

Output:

```text
Start
ValueError
```

Program stops immediately.

---

# 4. try Block

Used for risky code.

Syntax:

```python
try:
    risky_code
```

Example:

```python
try:
    num = int("abc")
```

Python attempts execution.

---

# 5. except Block

Runs when an exception occurs.

Syntax:

```python
try:
    risky_code

except:
    handle_error
```

Example:

```python
try:
    num = int("abc")

except:
    print("Invalid Input")
```

Output:

```text
Invalid Input
```

Program continues normally.

---

# 6. Specific Exceptions

Avoid:

```python
except:
```

Prefer:

```python
except ValueError:
```

Example:

```python
try:
    num = int("abc")

except ValueError:
    print("Invalid Number")
```

Specific exception handling improves readability and debugging.

---

# 7. Common Built-in Exceptions

## ValueError

Invalid value for conversion.

```python
int("abc")
```

---

## ZeroDivisionError

```python
10 / 0
```

---

## IndexError

```python
nums = [1,2,3]

nums[10]
```

---

## KeyError

```python
data = {"name":"Ravi"}

data["age"]
```

---

## TypeError

```python
"5" + 5
```

---

## FileNotFoundError

```python
open("abc.txt")
```

when file doesn't exist.

---

## PermissionError

Occurs when access is denied.

```python
open(protected_file)
```

---

# 8. Multiple Exception Handling

Different exceptions can be handled separately.

Example:

```python
try:
    num = int(input())
    result = 10 / num

except ValueError:
    print("Enter numbers only")

except ZeroDivisionError:
    print("Cannot divide by zero")
```

---

# 9. else Block

Runs only when NO exception occurs.

Syntax:

```python
try:
    risky_code

except:
    handle_error

else:
    success_code
```

Example:

```python
try:
    num = int(input())

except ValueError:
    print("Invalid")

else:
    print("Success")
```

---

# 10. finally Block

Always executes.

Syntax:

```python
try:
    risky_code

finally:
    cleanup_code
```

Example:

```python
try:
    print("Hello")

finally:
    print("Goodbye")
```

Output:

```text
Hello
Goodbye
```

Even if an exception occurs.

---

# 11. Complete Structure

```python
try:
    risky_code

except ValueError:
    handle_error

else:
    success_code

finally:
    cleanup_code
```

All blocks are optional except `try`.

---

# 12. Exception Objects

Actual error information can be captured.

Syntax:

```python
except ExceptionType as e:
```

Example:

```python
try:
    int("abc")

except ValueError as e:
    print(e)
```

Output:

```text
invalid literal for int() with base 10: 'abc'
```

---

# 13. Raising Exceptions

You can create exceptions manually.

Syntax:

```python
raise ExceptionType("message")
```

Example:

```python
age = -5

if age < 0:
    raise ValueError("Age cannot be negative")
```

Output:

```text
ValueError: Age cannot be negative
```

---

# 14. Why raise?

Used to enforce rules.

Example:

```python
marks = -10
```

This value is logically invalid.

Instead of allowing bad data:

```python
raise ValueError(...)
```

---

# 15. Custom Exceptions (Introduction)

Python allows creating your own exceptions.

Example:

```python
class InvalidAgeError(Exception):
    pass
```

Usage:

```python
raise InvalidAgeError("Age Invalid")
```

Useful in larger applications.

---

# Exception Handling Flow

```text
try
 │
 ├── No Exception
 │      │
 │      └── else
 │
 └── Exception
        │
        └── except

finally
(always executes)
```

---

# Exception Hierarchy

Python exceptions follow inheritance.

```text
BaseException
│
├── SystemExit
├── KeyboardInterrupt
├── GeneratorExit
│
└── Exception
     │
     ├── ArithmeticError
     │     └── ZeroDivisionError
     │
     ├── LookupError
     │     ├── IndexError
     │     └── KeyError
     │
     ├── ValueError
     ├── TypeError
     ├── FileNotFoundError
     ├── PermissionError
     └── ...
```

---

# Important Hierarchy Concept

Since:

```text
Exception
│
└── ValueError
```

this works:

```python
except Exception:
```

because ValueError is a child of Exception.

But:

```python
except ValueError:
```

only catches ValueError.

---

# Catching Multiple Exceptions Together

Example:

```python
try:
    num = int(input())

except (ValueError, TypeError):
    print("Invalid Input")
```

Useful when handling similar errors.

---

# Best Practices

## Catch Specific Exceptions

Good:

```python
except ValueError:
```

Bad:

```python
except:
```

---

## Keep try Block Small

Good:

```python
try:
    num = int(input())
```

Bad:

```python
try:
    100 lines of code
```

---

## Don't Hide Errors

Bad:

```python
except:
    pass
```

Avoid unless absolutely necessary.

---

## Use Meaningful Messages

Good:

```python
except ValueError:
    print("Please enter a valid integer.")
```

---

# Practice Questions

## Familiarity

### 1. Integer Input Validation

Take input.

Handle:

```text
ValueError
```

if user enters text.

---

### 2. Division Calculator

Take two numbers.

Handle:

```text
ZeroDivisionError
```

---

### 3. List Index Access

Take index from user.

Handle:

```text
IndexError
```

---

### 4. Dictionary Key Search

Search a key in dictionary.

Handle:

```text
KeyError
```

---

### 5. File Opening

Open a file.

Handle:

```text
FileNotFoundError
```

---

### 6. Print Actual Error

Use:

```python
except Exception as e
```

Print the exception message.

---

### 7. Custom Validation

Take age input.

If age is negative:

```python
raise ValueError(...)
```

Handle it properly.

---

# Quick Revision

```text
try       → risky code

except    → handles exceptions

else      → runs if no exception

finally   → always executes

raise     → manually create exception

ValueError
ZeroDivisionError
IndexError
KeyError
TypeError
FileNotFoundError

except Exception as e
```

## Learning Outcome

After this topic you should be able to:

* Prevent program crashes
* Handle invalid user input
* Handle file-related errors
* Read exception messages
* Raise your own exceptions
* Understand Python's exception hierarchy
* Build more reliable programs

  ---

  # Phase 3 — Modules

---

# Why Learn Modules?

As programs grow larger, keeping everything inside one file becomes difficult.

Instead of writing hundreds of lines in a single file, code can be split into multiple files based on responsibility.

Benefits:

* Better organization
* Easier maintenance
* Code reusability
* Cleaner project structure
* Easier debugging

---

# What is a Module?

A module is simply:

```text
A Python file (.py)
```

Example:

```text
calculator.py
```

```python
def add(a, b):
    return a + b
```

The file itself is a module.

---

# Creating Your First Module

## calculator.py

```python
def add(a, b):
    return a + b

def subtract(a, b):
    return a - b
```

## main.py

```python
import calculator

print(calculator.add(10, 5))
print(calculator.subtract(10, 5))
```

Output:

```text
15
5
```

---

# import Statement

Syntax:

```python
import module_name
```

Example:

```python
import math
```

Use:

```python
math.sqrt(25)
```

Output:

```text
5.0
```

---

# Why module_name.function_name ?

When Python imports a module, it imports the entire module namespace.

Example:

```python
import math
```

Access functions using:

```python
math.sqrt(25)
math.factorial(5)
```

This avoids naming conflicts.

---

# from ... import ...

Instead of:

```python
import math

print(math.sqrt(25))
```

You can write:

```python
from math import sqrt

print(sqrt(25))
```

Output:

```text
5.0
```

---

# Import Multiple Functions

```python
from math import sqrt, factorial
```

Example:

```python
print(sqrt(16))
print(factorial(5))
```

Output:

```text
4.0
120
```

---

# Import Everything

```python
from math import *
```

Example:

```python
print(sqrt(25))
print(factorial(5))
```

---

# Why Avoid import * ?

Avoid:

```python
from module import *
```

Reasons:

* Imports everything
* Can overwrite existing names
* Harder to understand code
* Difficult to debug

Prefer:

```python
import module
```

or

```python
from module import specific_function
```

---

# Aliases

Aliases provide shorter names.

Syntax:

```python
import module_name as alias
```

Example:

```python
import math as m

print(m.sqrt(25))
```

Output:

```text
5.0
```

---

# Built-in Modules

Python provides many built-in modules.

## math

```python
import math

print(math.sqrt(25))
print(math.factorial(5))
```

---

## random

```python
import random

print(random.randint(1, 10))
```

---

## datetime

```python
from datetime import datetime

print(datetime.now())
```

---

## json

```python
import json
```

Used for JSON file handling.

---

# Module Execution

Consider:

## test.py

```python
print("Hello")
```

Run:

```bash
python test.py
```

Output:

```text
Hello
```

---

# The Special Variable: **name**

Every Python file automatically receives a special variable:

```python
__name__
```

Example:

```python
print(__name__)
```

---

# Running Directly

File:

```python
print(__name__)
```

Run:

```bash
python test.py
```

Output:

```text
__main__
```

---

# Importing

If the same file is imported:

```python
import test
```

Output:

```text
test
```

The module name becomes the filename.

---

# **name** == "**main**"

One of the most important Python patterns.

Syntax:

```python
if __name__ == "__main__":
    # code
```

Example:

```python
def add(a, b):
    return a + b

if __name__ == "__main__":
    print(add(10, 20))
```

---

# Why Use It?

Without:

```python
def add(a, b):
    return a + b

print(add(10, 20))
```

Importing the module executes:

```python
print(add(10, 20))
```

every time.

---

With:

```python
def add(a, b):
    return a + b

if __name__ == "__main__":
    print(add(10, 20))
```

The print statement runs only when the file is executed directly.

---

# Module Search Path

When Python encounters:

```python
import calculator
```

it searches:

1. Current folder
2. Python standard library
3. Installed packages

If not found:

```text
ModuleNotFoundError
```

occurs.

---

# Common Errors

## ModuleNotFoundError

Example:

```python
import calculator
```

Error:

```text
ModuleNotFoundError
```

Possible reasons:

* Wrong filename
* Wrong folder
* Module does not exist

---

# Circular Import

Avoid:

```text
module_a imports module_b
module_b imports module_a
```

This can create import issues.

---

# Best Practices

* One responsibility per module
* Use meaningful file names
* Avoid `import *`
* Use aliases when appropriate
* Use `if __name__ == "__main__":`
* Keep modules focused and small

---

# Practice Questions

## Familiarity

### 1. Calculator Module

Create:

```text
calculator.py
```

Functions:

```python
add()
subtract()
```

Import and use them.

---

### 2. Greeting Module

Create:

```text
greetings.py
```

Function:

```python
say_hello()
```

Import and call it.

---

### 3. Use math Module

Practice:

```python
sqrt()
factorial()
pow()
```

---

## Important

### 4. Use from ... import ...

Import only:

```python
sqrt
```

and use it.

---

### 5. Use Aliases

Import:

```python
math as m
```

Use:

```python
m.sqrt()
m.factorial()
```

---

### 6. Observe **name**

Create a file that prints:

```python
print(__name__)
```

Run directly.

Then import it from another file.

Observe the difference.

---

## Useful

### 7. String Utility Module

Create:

```text
string_utils.py
```

Functions:

```python
count_vowels()
reverse_string()
is_palindrome()
```

Import and test them.

---

# Quick Revision

```text
Module
→ Python file

import module

from module import function

import module as alias

Avoid:
from module import *

Special Variable:
__name__

Important Pattern:
if __name__ == "__main__":

Built-in Modules:
math
random
datetime
json
```

---

# Phase 3 — Packages

---

# Why Learn Packages?

As projects grow, the number of modules increases.

Instead of:

```text
calculator.py
string_utils.py
json_utils.py
file_utils.py
date_utils.py
```

all being placed in one folder, related modules can be grouped together.

Packages provide:

* Better organization
* Cleaner project structure
* Easier maintenance
* Better scalability
* Logical grouping of modules

---

# What is a Package?

A package is:

```text
A folder containing Python modules.
```

Example:

```text
utils/

├── __init__.py
├── calculator.py
├── string_utils.py
```

Here:

```text
utils
```

is a package.

---

# Module vs Package

| Feature   | Module        | Package           |
| --------- | ------------- | ----------------- |
| Meaning   | Python File   | Folder of Modules |
| Extension | .py           | Folder            |
| Example   | calculator.py | utils/            |
| Purpose   | Store Code    | Organize Modules  |

---

# Package Structure

Example:

```text
project/

├── main.py

└── utils/
    ├── __init__.py
    ├── calculator.py
    └── string_utils.py
```

---

# The **init**.py File

## What is it?

A special Python file placed inside a package.

Example:

```text
utils/

├── __init__.py
├── calculator.py
└── string_utils.py
```

---

## Historical Purpose

Originally:

```text
Folder + __init__.py
=
Python Package
```

Python used this file to recognize packages.

---

## Modern Python

Modern Python versions can work without it in many cases.

However:

```text
Using __init__.py is still recommended.
```

---

# Why **init**.py Exists

The real purpose is:

```text
Package Initialization
```

When a package is imported:

```python
import utils
```

Python executes:

```python
utils/__init__.py
```

first.

---

# Package Initialization Example

## **init**.py

```python
print("Package Loaded")
```

## main.py

```python
import utils
```

Output:

```text
Package Loaded
```

---

# Exporting Functions

Suppose:

## calculator.py

```python
def add(a, b):
    return a + b
```

---

## **init**.py

```python
from .calculator import add
```

Now:

```python
from utils import add
```

works.

Instead of:

```python
from utils.calculator import add
```

---

# Package-Level Variables

## **init**.py

```python
VERSION = "1.0"
```

Use:

```python
import utils

print(utils.VERSION)
```

Output:

```text
1.0
```

---

# Importing from Packages

## Import Specific Function

```python
from utils.calculator import add
```

Use:

```python
print(add(10, 20))
```

---

## Import Entire Module

```python
import utils.calculator
```

Use:

```python
print(utils.calculator.add(10, 20))
```

---

## Import Multiple Functions

```python
from utils.calculator import add, subtract
```

---

# Aliases

```python
import utils.calculator as calc
```

Use:

```python
calc.add(10, 20)
```

---

# Relative Imports

Inside packages you may see:

```python
from .calculator import add
```

The dot means:

```text
Current Package
```

Example:

```python
from .string_utils import reverse
```

means:

```text
Import reverse from string_utils.py
inside the same package.
```

---

# Nested Packages

Packages can contain packages.

Example:

```text
app/

├── __init__.py

├── services/
│   ├── __init__.py
│   ├── auth.py
│   └── email.py
```

Import:

```python
from services.auth import login
```

---

# Package Search

When Python encounters:

```python
import utils
```

it searches:

1. Current Project Folder
2. Python Standard Library
3. Installed Packages

If not found:

```text
ModuleNotFoundError
```

occurs.

---

# Common Errors

## ModuleNotFoundError

Example:

```python
import utils
```

Error:

```text
ModuleNotFoundError
```

Possible reasons:

* Wrong folder name
* Wrong module name
* Package not found

---

## Circular Imports

Avoid:

```text
module_a imports module_b

module_b imports module_a
```

This can cause import issues.

---

# Best Practices

* Group related modules together
* Use meaningful package names
* Keep packages focused
* Use `__init__.py`
* Avoid deeply nested structures initially
* Avoid circular imports

---

# Practice Questions

## Familiarity

### 1

Create:

```text
utils/

├── __init__.py
├── calculator.py
```

Import a function from calculator.py.

---

### 2

Create:

```text
helpers/

├── __init__.py
├── greetings.py
```

Import and call a function.

---

### 3

Import an entire module from a package.

---

## Important

### 4

Use:

```python
from package.module import function
```

---

### 5

Use alias imports:

```python
import package.module as alias
```

---

### 6

Create a variable inside:

```python
__init__.py
```

and access it.

---

## Useful

### 7

Use:

```python
from .module import function
```

inside a package.

Observe how relative imports work.

---

# Quick Revision

```text
Module
→ Python File

Package
→ Folder of Modules

Special File
→ __init__.py

Uses of __init__.py

1. Package Initialization

2. Export Functions

3. Package Variables

4. Startup Code

Import Examples

from package.module import function

import package.module

Relative Import

from .module import function

Package Benefits

Organization
Maintainability
Scalability
Code Reuse
```


