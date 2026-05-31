# Phase 0 — Setup + Python Transition

## Goal

Learn:

* Python installation
* Virtual environments
* Package management
* Running Python files
* Basic project workflow

**Duration:** 3–5 Days

---

# 1. Python Interpreter

The Python interpreter executes Python code.

Start interpreter:

```cmd
python
```

Exit interpreter:

```python
exit()
```

---

# 2. Create Project Folder

```cmd
mkdir python_phase0
cd python_phase0
```

---

# 3. Create Virtual Environment

```cmd
python -m venv venv
```

Purpose:

* Creates an isolated Python environment.
* Prevents dependency conflicts between projects.

---

# 4. Activate Virtual Environment

### Windows CMD

```cmd
venv\Scripts\activate
```

Activated environment:

```text
(venv)
```

appears in terminal.

---

# 5. Install Packages

Example:

```cmd
pip install requests
```

---

# 6. Create Python File

Create:

```text
test.py
```

Example:

```python
import requests

print("requests installed successfully")
```

---

# 7. Run Python File

```cmd
python test.py
```

---

# 8. View Installed Packages

```cmd
pip list
```

---

# 9. Freeze Dependencies

```cmd
pip freeze > requirements.txt
```

Purpose:

* Save installed packages.
* Create dependency snapshot.
* Reproduce project environment later.

---

# 10. Install Dependencies

```cmd
pip install -r requirements.txt
```

Used for:

* Sharing projects
* Deployment
* Team collaboration

---

# 11. Deactivate Environment

```cmd
deactivate
```

---

# Core Concepts

## Package

Reusable code written by other developers.

Examples:

```text
requests
numpy
pandas
fastapi
```

---

## pip

Python package manager.

Common commands:

```cmd
pip install package_name
pip uninstall package_name
pip list
pip freeze
```

---

## Virtual Environment

Project-specific Python environment.

Benefits:

* Dependency isolation
* Cleaner projects
* Easier deployment

---

## requirements.txt

Stores project dependencies.

Example:

```text
requests==2.32.0
numpy==2.0.0
```

---

# Basic Python Syntax Reminder

## Variable

```python
name = "Ravi"
```

---

## Input

```python
name = input("Enter name: ")
```

**Important:** `input()` always returns a string.

---

## Output

```python
print(name)
```

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
cgpa = float(input())
```

---

# Important Beginner Rules

* Always activate virtual environment before coding.
* Create one virtual environment per project.
* Never upload `venv/` to GitHub.
* Add `venv/` to `.gitignore`.
* Use `requirements.txt` in every project.

---

# Typical Project Structure

```text
project/
│
├── venv/
├── main.py
├── requirements.txt
└── README.md
```

---

# Phase 0 Practice Tasks

1. Create a project folder.
2. Create a virtual environment.
3. Activate the environment.
4. Install the `requests` package.
5. Create and run `test.py`.
6. Generate `requirements.txt`.
7. Deactivate the environment.

---

# Completion Checklist

```text
✓ Python Installed
✓ Virtual Environment Created
✓ Package Installed
✓ Python File Executed
✓ requirements.txt Generated
```

You are now ready for Python programming.
