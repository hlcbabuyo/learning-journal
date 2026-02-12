# 🐍 Day 1: Python Basics & Data Structures
**Date:** Feb 12, 2026  
**Source:** W3Schools Python Tutorial  

---

## 📝 Key Concepts Summary

| Concept | What I Learned |
|---------|---------------|
| **Variables** | No declaration needed, dynamically typed |
| **Strings** | Immutable, indexable, many useful methods |
| **Lists** | Ordered, mutable, most used for collections |
| **Dictionaries** | Key-value pairs, basis for JSON/APIs |
| **Control Flow** | if/elif/else, for, while |
| **Functions** | Reusable code blocks with parameters |
| **Classes** | Blueprint for creating objects (OOP) |

---

## 1️⃣ Syntax & Variables

### Indentation
Python uses **indentation** (whitespace) to indicate blocks of code.

```python
if 5 > 2:
    print("Five is greater than two!")  # Indentation matters!
```

### Comments
```python
# Single-line comment

""" 
Multiline 
comment
"""

x = 5  # Inline comment
```

### Variables
- Created when you assign a value
- No declaration command needed
- Case-sensitive (`age` ≠ `Age`)

```python
x = 5           # Integer
y = "Hello"     # String
name = "John"   # Variables can have descriptive names
```

**✅ Key Takeaway:** No semicolons, no type declarations. Python is clean and readable.

---

## 2️⃣ Data Types

### Checking Type

```python
x = 5
print(type(x))  # <class 'int'>
```

### Primitive Types

| Type | Example | Description |
|------|---------|-------------|
| `str` | `"Hello"` or `'Hello'` | Text data |
| `int` | `20` | Whole numbers |
| `float` | `20.5` | Decimal numbers |
| `bool` | `True` or `False` | Boolean values |

### Type Casting (Converting Types)

```python
x = int(1)      # x will be 1
y = int(2.8)    # y will be 2 (truncates, doesn't round)
z = str(3.0)    # z will be "3.0"
w = float("4.5") # w will be 4.5
```

**⚠️ Watch Out:** `int(2.8)` gives `2`, not `3` (it truncates, doesn't round)

**🎯 Backend Use Case:** Converting user input strings to numbers for validation

---

## 3️⃣ Strings (Text Processing)

Strings are **arrays** of bytes representing Unicode characters.

### String Operations

```python
a = "Hello, World!"

# Accessing characters (0-indexed)
print(a[1])         # "e"

# Slicing [start:end] (end not included)
print(a[2:5])       # "llo"
print(a[:5])        # "Hello" (from start)
print(a[7:])        # "World!" (to end)

# String methods
print(a.strip())    # Remove whitespace from ends
print(a.lower())    # "hello, world!"
print(a.upper())    # "HELLO, WORLD!"
print(a.replace("H", "J"))  # "Jello, World!"
print(a.split(",")) # ["Hello", " World!"] (split into list)

# Checking
print("World" in a) # True
print(len(a))       # 13 (length)
```

### String Formatting (f-strings)

```python
name = "John"
age = 25
message = f"Hello {name}, you are {age} years old"
print(message)  # "Hello John, you are 25 years old"
```

**🎯 Backend Use Case:** Processing user input, formatting API responses

---

## 4️⃣ Python Collections

### 📋 Lists (Most Used in Backend)
**Ordered, Changeable, Allows Duplicates**

```python
mylist = ["apple", "banana", "cherry"]

# Accessing
print(mylist[0])        # "apple"
print(mylist[-1])       # "cherry" (last item)

# Modifying
mylist[1] = "blackcurrant"  # Change item
mylist.append("orange")     # Add to end
mylist.insert(1, "mango")   # Add at index 1
mylist.remove("banana")     # Remove specific item
mylist.pop()                # Remove last item

# Info
print(len(mylist))      # Get length
print("apple" in mylist) # Check if exists

# Looping
for item in mylist:
    print(item)
```

**✅ When to Use:** Storing ordered data (list of tasks, users, search results)

---

### 📦 Tuples
**Ordered, Unchangeable, Allows Duplicates**

```python
mytuple = ("apple", "banana", "cherry")
print(mytuple[1])  # "banana"

# mytuple[1] = "kiwi"  ❌ ERROR - Cannot modify!
```

**✅ When to Use:** Data that shouldn't change (coordinates, database records from queries)

---

### 📚 Dictionaries (CRITICAL for APIs)
**Ordered (Python 3.7+), Changeable, No Duplicate Keys**

Think of it as **key-value pairs** → Same as JSON!

```python
user = {
    "name": "John",
    "email": "john@example.com",
    "age": 25
}

# Accessing
print(user["name"])         # "John"
print(user.get("email"))    # "john@example.com"

# Modifying
user["age"] = 26            # Change value
user["phone"] = "123456"    # Add new key-value

# Looping
for key in user:
    print(key, user[key])

# Better way to loop
for key, value in user.items():
    print(f"{key}: {value}")

# Get all keys/values
print(user.keys())      # dict_keys(['name', 'email', 'age', 'phone'])
print(user.values())    # dict_values(['John', 'john@example.com', 26, '123456'])
```

**✅ When to Use:** Representing objects (users, tasks, API requests/responses)

**🎯 Backend Reality:** 90% of API data is dictionaries converted to/from JSON

---

### 🔢 Sets
**Unordered, Unchangeable Items*, No Duplicates**

```python
myset = {"apple", "banana", "cherry"}

# Adding
myset.add("orange")
myset.add("apple")  # Won't add duplicate

# Checking
print("banana" in myset)  # True

# Removing duplicates from list
mylist = [1, 2, 2, 3, 3, 3, 4]
unique = list(set(mylist))  # [1, 2, 3, 4]
```

**✅ When to Use:** Removing duplicates, checking membership, unique tags

---

## 5️⃣ Control Flow

### If... Elif... Else

```python
age = 20

if age >= 18:
    print("Adult")
elif age >= 13:
    print("Teen")
else:
    print("Child")

# One-line if (Ternary)
status = "Adult" if age >= 18 else "Minor"
```

### Comparison Operators

```python
==  # Equal
!=  # Not equal
>   # Greater than
<   # Less than
>=  # Greater than or equal
<=  # Less than or equal
```

### Logical Operators

```python
and  # Both conditions must be True
or   # At least one condition must be True
not  # Reverse the result

# Example
if age >= 18 and age < 65:
    print("Working age")
```

**🎯 Backend Use Case:** Validating user input, checking permissions

---

### While Loops
Execute statements **as long as** condition is true.

```python
i = 1
while i < 6:
    print(i)
    i += 1  # Don't forget to increment!
# Output: 1 2 3 4 5
```

**⚠️ Watch Out:** Infinite loops if you forget to update the condition!

---

### For Loops (Most Common)
Iterate over a **sequence** (list, tuple, dict, set, string).

```python
# Loop through list
fruits = ["apple", "banana", "cherry"]
for fruit in fruits:
    print(fruit)

# Loop with index
for i, fruit in enumerate(fruits):
    print(f"{i}: {fruit}")

# Loop through range
for i in range(5):
    print(i)  # 0 1 2 3 4

# Loop through dictionary
user = {"name": "John", "age": 25}
for key, value in user.items():
    print(f"{key}: {value}")
```

### Loop Control

```python
for x in range(10):
    if x == 3:
        continue  # Skip this iteration
    if x == 8:
        break     # Exit loop entirely
    print(x)
```

**🎯 Backend Use Case:** Processing lists of data, iterating through database results

---

## 6️⃣ Functions

A **reusable block of code** that runs when called.

### Basic Function

```python
def greet(name):
    print(f"Hello, {name}!")

greet("John")  # Output: Hello, John!
```

### Return Values

```python
def add(a, b):
    return a + b

result = add(5, 3)  # result = 8
```

### Default Parameters

```python
def greet(name, greeting="Hello"):
    return f"{greeting}, {name}!"

print(greet("John"))              # "Hello, John!"
print(greet("John", "Hi"))        # "Hi, John!"
```

### Multiple Return Values

```python
def get_user():
    name = "John"
    age = 25
    return name, age  # Returns tuple

name, age = get_user()
```

**🎯 Backend Use Case:** Every API endpoint is essentially a function

---

## 7️⃣ Classes & Objects (OOP Basics)

### Class Definition

```python
class Person:
    # Constructor - runs when object is created
    def __init__(self, name, age):
        self.name = name    # Instance variable
        self.age = age
    
    # Method
    def greet(self):
        return f"Hello, my name is {self.name}"

# Creating an object (instance)
person1 = Person("John", 25)

# Accessing attributes
print(person1.name)     # "John"
print(person1.age)      # 25

# Calling methods
print(person1.greet())  # "Hello, my name is John"
```

### Practical Example (Backend)

```python
class Task:
    def __init__(self, title, completed=False):
        self.title = title
        self.completed = completed
    
    def mark_complete(self):
        self.completed = True
    
    def to_dict(self):
        return {
            "title": self.title,
            "completed": self.completed
        }

# Usage
task = Task("Learn Python")
print(task.to_dict())  # {"title": "Learn Python", "completed": False}
task.mark_complete()
print(task.to_dict())  # {"title": "Learn Python", "completed": True}
```

**🎯 Backend Use Case:** Database models, API schemas

---

*"Day 1 done. Consistency > Perfection. Tomorrow: More Python."*