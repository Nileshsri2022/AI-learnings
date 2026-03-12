

# 🐍 COMPLETE PYTHON ROADMAP
### From Zero to Industry-Ready — Structured & Actionable

---

## 📍 Where You Are → Where You'll Go

```
🟢 BEGINNER           🟡 INTERMEDIATE          🔴 ADVANCED           🏆 PRO
   (Weeks 1-4)           (Weeks 5-10)            (Weeks 11-16)        (Weeks 17-20)
   
   Syntax, Loops         OOP, Modules,           Frameworks,          System Design,
   Functions, DS         Decorators, Regex        Concurrency,         Testing, Deploy
                                                  Async
```

---

## 🟢 PHASE 1: LEARN THE BASICS (Weeks 1–4)

### Week 1: Core Syntax & Foundations
| # | Topic | Priority | Est. Hours | Status |
|---|-------|----------|-----------|--------|
| 1 | **Basic Syntax** — indentation, comments, `print()`, `input()` | 🔴 Critical | 2h | ⬜ |
| 2 | **Variables & Data Types** — `int`, `float`, `str`, `bool`, `None` | 🔴 Critical | 3h | ⬜ |
| 3 | **Type Casting** — `int()`, `str()`, `float()`, implicit vs explicit | 🟡 Important | 1h | ⬜ |
| 4 | **Operators** — arithmetic, comparison, logical, bitwise | 🔴 Critical | 2h | ⬜ |
| 5 | **Conditionals** — `if`, `elif`, `else`, nested conditions, ternary | 🔴 Critical | 2h | ⬜ |
| 6 | **Loops** — `for`, `while`, `range()`, `break`, `continue`, `pass` | 🔴 Critical | 3h | ⬜ |

```python
# 🏋️ Week 1 Mini Project: Simple Calculator
def calculator():
    num1 = float(input("Enter first number: "))
    op = input("Enter operator (+, -, *, /): ")
    num2 = float(input("Enter second number: "))
    
    if op == '+':
        print(f"Result: {num1 + num2}")
    elif op == '-':
        print(f"Result: {num1 - num2}")
    elif op == '*':
        print(f"Result: {num1 * num2}")
    elif op == '/':
        print(f"Result: {num1 / num2}" if num2 != 0 else "Cannot divide by zero!")
    else:
        print("Invalid operator!")

calculator()
```

---

### Week 2: Data Structures (Built-in)
| # | Topic | Priority | Est. Hours | Status |
|---|-------|----------|-----------|--------|
| 7 | **Lists** — create, index, slice, methods (`append`, `pop`, `sort`) | 🔴 Critical | 3h | ⬜ |
| 8 | **Tuples** — immutability, packing/unpacking, `namedtuple` | 🟡 Important | 2h | ⬜ |
| 9 | **Sets** — union, intersection, difference, `frozenset` | 🟡 Important | 2h | ⬜ |
| 10 | **Dictionaries** — CRUD, `.get()`, `.items()`, nesting, comprehensions | 🔴 Critical | 3h | ⬜ |
| 11 | **Strings (Deep Dive)** — f-strings, methods, slicing, immutability | 🔴 Critical | 2h | ⬜ |

```python
# 🔍 Quick Comparison Table
"""
┌─────────────┬──────────┬──────────┬───────────┬────────────┐
│  Feature    │  List    │  Tuple   │   Set     │   Dict     │
├─────────────┼──────────┼──────────┼───────────┼────────────┤
│  Syntax     │  [1,2,3] │ (1,2,3)  │ {1,2,3}   │ {"a": 1}   │
│  Mutable?   │  ✅ Yes  │ ❌ No    │ ✅ Yes    │ ✅ Yes     │
│  Ordered?   │  ✅ Yes  │ ✅ Yes   │ ❌ No     │ ✅ (3.7+)  │
│  Duplicates?│  ✅ Yes  │ ✅ Yes   │ ❌ No     │ Keys: No   │
│  Indexed?   │  ✅ Yes  │ ✅ Yes   │ ❌ No     │ By Key     │
│  Use Case   │ General  │ Constants│ Unique    │ Key-Value  │
│             │ storage  │ coords   │ items     │ mapping    │
└─────────────┴──────────┴──────────┴───────────┴────────────┘
"""
```

```python
# 🏋️ Week 2 Mini Project: Student Grade Manager
students = {}

def add_student(name, marks):
    students[name] = marks

def get_average(name):
    if name in students:
        marks = students[name]
        return sum(marks) / len(marks)
    return "Student not found"

def get_topper():
    return max(students, key=lambda s: sum(students[s]) / len(students[s]))

# Usage
add_student("Rahul", [85, 90, 78, 92])
add_student("Priya", [95, 88, 92, 96])
add_student("Amit", [70, 75, 80, 72])

print(f"Rahul's Average: {get_average('Rahul'):.2f}")
print(f"Topper: {get_topper()}")
```

---

### Week 3: Functions & Error Handling
| # | Topic | Priority | Est. Hours | Status |
|---|-------|----------|-----------|--------|
| 12 | **Functions** — `def`, parameters, `return`, default args, `*args`, `**kwargs` | 🔴 Critical | 3h | ⬜ |
| 13 | **Built-in Functions** — `map()`, `filter()`, `zip()`, `enumerate()`, `sorted()` | 🔴 Critical | 2h | ⬜ |
| 14 | **Lambda Functions** — anonymous functions, use with `map`/`filter`/`sorted` | 🟡 Important | 2h | ⬜ |
| 15 | **Exceptions** — `try/except/else/finally`, custom exceptions, `raise` | 🔴 Critical | 2h | ⬜ |
| 16 | **Scope** — LEGB rule, `global`, `nonlocal` | 🟡 Important | 1h | ⬜ |

```python
# 💡 *args and **kwargs — The Indian Thali Analogy 🍽️
# *args   = "jitne chaiye utne roti lo" (take as many rotis as you want)
# **kwargs = "customize karo — extra butter, less salt" (customize your order)

def order_thali(name, *items, **customization):
    print(f"\n🍽️ Order for: {name}")
    print(f"  Items: {', '.join(items)}")
    for key, value in customization.items():
        print(f"  {key}: {value}")

order_thali("Rahul", "roti", "dal", "paneer", "rice",
            spice_level="medium", extra_butter=True)

# Output:
# 🍽️ Order for: Rahul
#   Items: roti, dal, paneer, rice
#   spice_level: medium
#   extra_butter: True
```

```python
# Exception Handling — Real-World Pattern
def safe_divide(a, b):
    try:
        result = a / b
    except ZeroDivisionError:
        return "❌ Cannot divide by zero!"
    except TypeError:
        return "❌ Invalid input types!"
    else:
        return f"✅ Result: {result}"
    finally:
        print("📝 Division operation attempted.")

print(safe_divide(10, 3))   # ✅ Result: 3.333...
print(safe_divide(10, 0))   # ❌ Cannot divide by zero!
```

---

### Week 4: Modules & File Handling
| # | Topic | Priority | Est. Hours | Status |
|---|-------|----------|-----------|--------|
| 17 | **Modules** — `import`, `from...import`, creating custom modules | 🔴 Critical | 2h | ⬜ |
| 18 | **Built-in Modules** — `os`, `sys`, `math`, `random`, `datetime`, `json` | 🟡 Important | 3h | ⬜ |
| 19 | **File Handling** — `open()`, read/write/append, `with` statement, CSV/JSON | 🔴 Critical | 3h | ⬜ |
| 20 | **Virtual Environments** — `venv`, `virtualenv`, `pyenv` | 🟡 Important | 1h | ⬜ |
| 21 | **Package Managers** — `pip install`, `requirements.txt`, `pyproject.toml` | 🟡 Important | 1h | ⬜ |

```python
# 🏋️ Week 4 Mini Project: Expense Tracker (File-Based)
import json
from datetime import datetime

FILE = "expenses.json"

def load_expenses():
    try:
        with open(FILE, 'r') as f:
            return json.load(f)
    except (FileNotFoundError, json.JSONDecodeError):
        return []

def save_expense(category, amount, description):
    expenses = load_expenses()
    expenses.append({
        "date": datetime.now().strftime("%Y-%m-%d %H:%M"),
        "category": category,
        "amount": amount,
        "description": description
    })
    with open(FILE, 'w') as f:
        json.dump(expenses, f, indent=2)
    print(f"✅ Saved: ₹{amount} for {description}")

def monthly_summary():
    expenses = load_expenses()
    total = sum(e["amount"] for e in expenses)
    by_category = {}
    for e in expenses:
        by_category[e["category"]] = by_category.get(e["category"], 0) + e["amount"]
    
    print(f"\n📊 Total Spent: ₹{total}")
    for cat, amt in sorted(by_category.items(), key=lambda x: -x[1]):
        print(f"  {cat}: ₹{amt}")

# Usage
save_expense("Food", 250, "Lunch at canteen")
save_expense("Transport", 100, "Auto to college")
monthly_summary()
```

---

## 🟡 PHASE 2: INTERMEDIATE PYTHON (Weeks 5–10)

### Week 5–6: Object-Oriented Programming (OOP)
| # | Topic | Priority | Est. Hours | Status |
|---|-------|----------|-----------|--------|
| 22 | **Classes & Objects** — `__init__`, `self`, attributes, methods | 🔴 Critical | 3h | ⬜ |
| 23 | **Inheritance** — single, multiple, `super()`, MRO | 🔴 Critical | 3h | ⬜ |
| 24 | **Encapsulation** — private `_`, protected `__`, property decorators | 🟡 Important | 2h | ⬜ |
| 25 | **Polymorphism** — method overriding, duck typing | 🟡 Important | 2h | ⬜ |
| 26 | **Abstraction** — `ABC`, `@abstractmethod` | 🟡 Important | 2h | ⬜ |
| 27 | **Dunder/Magic Methods** — `__str__`, `__repr__`, `__len__`, `__eq__`, `__add__` | 🟡 Important | 3h | ⬜ |
| 28 | **Class vs Static Methods** — `@classmethod`, `@staticmethod` | 🟡 Important | 1h | ⬜ |
| 29 | **Dataclasses** — `@dataclass` decorator (Python 3.7+) | 🟢 Good to know | 1h | ⬜ |

```python
# 🎨 OOP — UPI Payment System Example
from abc import ABC, abstractmethod
from datetime import datetime

class PaymentMethod(ABC):
    """Abstract base class — like a blueprint"""
    
    @abstractmethod
    def pay(self, amount: float) -> bool:
        pass
    
    @abstractmethod
    def get_balance(self) -> float:
        pass

class UPIPayment(PaymentMethod):
    def __init__(self, upi_id: str, balance: float):
        self.upi_id = upi_id
        self._balance = balance  # protected
        self.__pin = None        # private
        self.transactions = []
    
    def set_pin(self, pin: int):
        if len(str(pin)) == 4:
            self.__pin = pin
            print("✅ PIN set successfully!")
        else:
            print("❌ PIN must be 4 digits!")
    
    def pay(self, amount: float, receiver: str = "Unknown") -> bool:
        if amount > self._balance:
            print(f"❌ Insufficient balance! Available: ₹{self._balance}")
            return False
        self._balance -= amount
        self.transactions.append({
            "type": "DEBIT", "amount": amount,
            "to": receiver, "time": datetime.now().strftime("%H:%M")
        })
        print(f"✅ ₹{amount} sent to {receiver}")
        return True
    
    def get_balance(self) -> float:
        return self._balance
    
    # Dunder methods
    def __str__(self):
        return f"UPI: {self.upi_id} | Balance: ₹{self._balance}"
    
    def __len__(self):
        return len(self.transactions)

# Usage
gpay = UPIPayment("rahul@okicici", 5000.0)
gpay.set_pin(1234)
gpay.pay(500, "chai_wala@upi")
gpay.pay(1200, "amazon@apl")
print(gpay)                    # UPI: rahul@okicici | Balance: ₹3300.0
print(f"Transactions: {len(gpay)}")  # Transactions: 2
```

---

### Week 7–8: Intermediate Concepts
| # | Topic | Priority | Est. Hours | Status |
|---|-------|----------|-----------|--------|
| 30 | **List Comprehensions** — filtering, nested, with conditions | 🔴 Critical | 2h | ⬜ |
| 31 | **Generator Expressions** — `yield`, lazy evaluation, memory efficiency | 🟡 Important | 2h | ⬜ |
| 32 | **Decorators** — function decorators, `@wraps`, chaining, real-world use | 🔴 Critical | 3h | ⬜ |
| 33 | **Iterators** — `__iter__`, `__next__`, `itertools` module | 🟡 Important | 2h | ⬜ |
| 34 | **Context Managers** — `with` statement, `__enter__`/`__exit__`, `contextlib` | 🟡 Important | 2h | ⬜ |
| 35 | **Regular Expressions** — `re` module, patterns, groups, common patterns | 🟡 Important | 3h | ⬜ |

```python
# 🎯 Decorators — The "Security Guard" Analogy 🔒
# A decorator is like a security guard at a building entrance
# The guard (decorator) checks things BEFORE and AFTER you enter

import time
from functools import wraps

def timer(func):
    """Measures how long a function takes — like a stopwatch"""
    @wraps(func)
    def wrapper(*args, **kwargs):
        start = time.time()
        result = func(*args, **kwargs)
        end = time.time()
        print(f"⏱️ {func.__name__} took {end - start:.4f} seconds")
        return result
    return wrapper

def retry(max_attempts=3):
    """Retries a function if it fails — like re-sending OTP"""
    def decorator(func):
        @wraps(func)
        def wrapper(*args, **kwargs):
            for attempt in range(1, max_attempts + 1):
                try:
                    return func(*args, **kwargs)
                except Exception as e:
                    print(f"⚠️ Attempt {attempt}/{max_attempts} failed: {e}")
                    if attempt == max_attempts:
                        raise
        return wrapper
    return decorator

@timer
@retry(max_attempts=3)
def fetch_data(url):
    """Simulated API call"""
    import random
    if random.random() < 0.5:
        raise ConnectionError("Server not responding!")
    return {"status": "success", "data": [1, 2, 3]}

result = fetch_data("https://api.example.com")
```

```python
# 💡 Generators — Memory Efficient (read LARGE files line by line)
def read_large_file(file_path):
    """Reads a 10GB log file without loading it all into memory"""
    with open(file_path, 'r') as f:
        for line in f:
            yield line.strip()

# Comprehension vs Generator — Memory Comparison
import sys

list_comp = [x**2 for x in range(1000000)]     # Stores ALL in memory
gen_expr  = (x**2 for x in range(1000000))     # Computes ONE at a time

print(f"List: {sys.getsizeof(list_comp):,} bytes")  # ~8,000,000 bytes
print(f"Generator: {sys.getsizeof(gen_expr)} bytes") # ~200 bytes 🔥
```

---

### Week 9–10: DSA in Python + Advanced Built-ins
| # | Topic | Priority | Est. Hours | Status |
|---|-------|----------|-----------|--------|
| 36 | **Arrays & Linked Lists** — implementation from scratch | 🔴 Critical | 4h | ⬜ |
| 37 | **Hash Tables** — dict internals, collision handling, custom hashmap | 🔴 Critical | 3h | ⬜ |
| 38 | **Stacks & Queues** — implementation + `collections.deque` | 🔴 Critical | 3h | ⬜ |
| 39 | **Heaps** — `heapq` module, min/max heap, priority queue | 🟡 Important | 2h | ⬜ |
| 40 | **Binary Search Trees** — insert, search, traversals | 🟡 Important | 3h | ⬜ |
| 41 | **Recursion** — base case, stack overflow, memoization | 🔴 Critical | 3h | ⬜ |
| 42 | **Sorting Algorithms** — bubble, selection, insertion, merge, quick | 🔴 Critical | 4h | ⬜ |
| 43 | **`collections` module** — `Counter`, `defaultdict`, `OrderedDict`, `deque` | 🟡 Important | 2h | ⬜ |

```python
# 🔥 DSA Essentials in Python — Quick Reference
from collections import Counter, defaultdict, deque
import heapq

# ─── Counter (Frequency Map) ─────────────────
votes = ["Modi", "Rahul", "Modi", "Kejriwal", "Modi", "Rahul"]
result = Counter(votes)
print(result.most_common(2))  # [('Modi', 3), ('Rahul', 2)]

# ─── defaultdict (No KeyError ever) ──────────
graph = defaultdict(list)
edges = [(1,2), (1,3), (2,4), (3,4)]
for u, v in edges:
    graph[u].append(v)
    graph[v].append(u)
print(dict(graph))  # {1: [2, 3], 2: [1, 4], 3: [1, 4], 4: [2, 3]}

# ─── Heap (Get min/max efficiently) ──────────
scores = [85, 92, 78, 95, 88]
heapq.heapify(scores)               # Min-heap
print(heapq.heappop(scores))        # 78 (smallest)
print(heapq.nlargest(2, scores))    # [95, 92] (top 2)

# ─── Deque (Stack + Queue in one) ────────────
dq = deque([1, 2, 3])
dq.appendleft(0)    # O(1) — unlike list.insert(0, x) which is O(n)
dq.append(4)        # O(1)
dq.popleft()         # O(1)
```

---

## 🔴 PHASE 3: ADVANCED PYTHON (Weeks 11–16)

### Week 11–12: Static Typing & Code Quality
| # | Topic | Priority | Est. Hours | Status |
|---|-------|----------|-----------|--------|
| 44 | **Type Hints** — `typing` module, `Optional`, `Union`, `List`, `Dict` | 🟡 Important | 2h | ⬜ |
| 45 | **Pydantic** — data validation, `BaseModel`, settings management | 🟡 Important | 3h | ⬜ |
| 46 | **mypy / pyright** — static type checking, catching bugs early | 🟢 Good to know | 2h | ⬜ |
| 47 | **Code Formatting** — `ruff`, `black`, consistent code style | 🟡 Important | 1h | ⬜ |
| 48 | **Linting** — `ruff` (replaces flake8 + isort + more) | 🟢 Good to know | 1h | ⬜ |

```python
# 📐 Type Hints — Make Your Code Self-Documenting
from typing import Optional
from pydantic import BaseModel, validator

class Student(BaseModel):
    name: str
    roll_no: int
    cgpa: float
    branch: str = "CSE"
    email: Optional[str] = None
    
    @validator('cgpa')
    def cgpa_must_be_valid(cls, v):
        if not 0.0 <= v <= 10.0:
            raise ValueError('CGPA must be between 0 and 10')
        return round(v, 2)
    
    @validator('email')
    def email_must_be_college(cls, v):
        if v and not v.endswith('.edu.in'):
            raise ValueError('Must use college email!')
        return v

# ✅ Valid
s = Student(name="Rahul", roll_no=101, cgpa=8.75)
print(s.model_dump())

# ❌ Invalid — will raise clear error
# s = Student(name="Rahul", roll_no=101, cgpa=11.0)
```

---

### Week 13–14: Concurrency & Async Programming
| # | Topic | Priority | Est. Hours | Status |
|---|-------|----------|-----------|--------|
| 49 | **GIL (Global Interpreter Lock)** — what it is, why it matters | 🟡 Important | 1h | ⬜ |
| 50 | **Threading** — `threading` module, I/O-bound tasks, thread safety | 🟡 Important | 3h | ⬜ |
| 51 | **Multiprocessing** — `multiprocessing` module, CPU-bound tasks | 🟡 Important | 3h | ⬜ |
| 52 | **Async/Await** — `asyncio`, event loop, coroutines | 🔴 Critical | 4h | ⬜ |
| 53 | **`aiohttp`** — async HTTP requests | 🟢 Good to know | 2h | ⬜ |

```
┌─────────────────────────────────────────────────────────────┐
│              When to Use What?                              │
├──────────────┬──────────────────┬───────────────────────────┤
│  Scenario    │  Tool            │  Analogy                  │
├──────────────┼──────────────────┼───────────────────────────┤
│  Downloading │  Threading /     │  One person ordering      │
│  files, API  │  asyncio         │  from multiple shops      │
│  calls       │  (I/O-bound)     │  simultaneously           │
├──────────────┼──────────────────┼───────────────────────────┤
│  Image       │  Multiprocessing │  Multiple people each     │
│  processing, │  (CPU-bound)     │  doing one task in        │
│  ML training │                  │  parallel                 │
├──────────────┼──────────────────┼───────────────────────────┤
│  Web server  │  asyncio         │  One waiter handling      │
│  handling    │                  │  100 tables — doesn't     │
│  requests    │                  │  wait, keeps moving       │
└──────────────┴──────────────────┴───────────────────────────┘
```

```python
# ⚡ Async Example — Fetch Multiple APIs Simultaneously
import asyncio
import aiohttp

async def fetch_url(session, url):
    async with session.get(url) as response:
        data = await response.json()
        print(f"✅ Got {len(data)} items from {url}")
        return data

async def main():
    urls = [
        "https://jsonplaceholder.typicode.com/posts",
        "https://jsonplaceholder.typicode.com/users",
        "https://jsonplaceholder.typicode.com/todos",
    ]
    
    async with aiohttp.ClientSession() as session:
        # All 3 requests happen SIMULTANEOUSLY, not one after another
        tasks = [fetch_url(session, url) for url in urls]
        results = await asyncio.gather(*tasks)
    
    print(f"\n📊 Total items fetched: {sum(len(r) for r in results)}")

asyncio.run(main())
# Without async: ~3 seconds (1s each, sequential)
# With async:    ~1 second  (all at once!) 🚀
```

---

### Week 15–16: Learn a Framework
| # | Topic | Priority | Est. Hours | Status |
|---|-------|----------|-----------|--------|
| 54 | **Flask** (if beginner) — routes, templates, REST API | 🟡 Important | 8h | ⬜ |
| 55 | **FastAPI** (recommended 🔥) — async, auto-docs, Pydantic integration | 🔴 Critical | 10h | ⬜ |
| 56 | **Django** (for full-stack) — ORM, admin, auth, MTV pattern | 🟡 Important | 12h | ⬜ |

```
🤔 Which Framework Should I Learn?

┌────────────┬───────────────┬────────────────┬────────────────┐
│  Criteria  │  Flask        │  FastAPI 🏆    │  Django        │
├────────────┼───────────────┼────────────────┼────────────────┤
│ Learning   │ Easiest       │ Easy-Medium    │ Steeper        │
│ Curve      │               │                │                │
├────────────┼───────────────┼────────────────┼────────────────┤
│ Speed      │ Moderate      │ Fastest 🚀     │ Moderate       │
├────────────┼───────────────┼────────────────┼────────────────┤
│ Best For   │ Small APIs,   │ APIs, Microser-│ Full websites, │
│            │ prototypes    │ vices, ML APIs │ admin panels   │
├────────────┼───────────────┼────────────────┼────────────────┤
│ Async?     │ Add-on        │ Built-in ✅    │ Partial (4.1+) │
├────────────┼───────────────┼────────────────┼────────────────┤
│ Auto Docs  │ Manual        │ Auto (Swagger) │ Manual         │
├────────────┼───────────────┼────────────────┼────────────────┤
│ Jobs 2025  │ Moderate      │ Growing fast 📈│ High           │
├────────────┼───────────────┼────────────────┼────────────────┤
│ Companies  │ Netflix,      │ Microsoft,     │ Instagram,     │
│ Using It   │ Reddit        │ Uber, Netflix  │ Spotify,       │
│            │               │                │ Pinterest      │
└────────────┴───────────────┴────────────────┴────────────────┘

💡 My Recommendation:
   → API/Backend focus → FastAPI
   → Full-stack web apps → Django  
   → Quick prototyping → Flask
```

```python
# 🚀 FastAPI — Build a REST API in 20 lines
from fastapi import FastAPI, HTTPException
from pydantic import BaseModel

app = FastAPI(title="Student API")

class Student(BaseModel):
    name: str
    roll_no: int
    cgpa: float

students_db: dict[int, Student] = {}

@app.post("/students/")
def create_student(student: Student):
    if student.roll_no in students_db:
        raise HTTPException(status_code=400, detail="Student already exists!")
    students_db[student.roll_no] = student
    return {"message": f"✅ {student.name} added!", "data": student}

@app.get("/students/{roll_no}")
def get_student(roll_no: int):
    if roll_no not in students_db:
        raise HTTPException(status_code=404, detail="Student not found!")
    return students_db[roll_no]

@app.get("/students/")
def list_students():
    return list(students_db.values())

# Run: uvicorn main:app --reload
# Visit: http://localhost:8000/docs → Auto Swagger UI! 🎉
```

---

## 🏆 PHASE 4: PRO LEVEL (Weeks 17–20)

### Week 17–18: Testing & Documentation
| # | Topic | Priority | Est. Hours | Status |
|---|-------|----------|-----------|--------|
| 57 | **pytest** — test functions, fixtures, parametrize, mocking | 🔴 Critical | 4h | ⬜ |
| 58 | **unittest** — `TestCase`, assertions, test suites | 🟡 Important | 2h | ⬜ |
| 59 | **doctest** — tests inside docstrings | 🟢 Good to know | 1h | ⬜ |
| 60 | **tox** — test across multiple Python versions | 🟢 Good to know | 1h | ⬜ |
| 61 | **Sphinx** — auto-generate documentation | 🟢 Good to know | 2h | ⬜ |

```python
# 🧪 pytest Example — Clean, Pythonic Testing
# file: test_calculator.py

import pytest

def add(a, b):
    return a + b

def divide(a, b):
    if b == 0:
        raise ValueError("Cannot divide by zero!")
    return a / b

# ─── Basic Tests ──────────────────────────
def test_add():
    assert add(2, 3) == 5

def test_add_negative():
    assert add(-1, 1) == 0

# ─── Parametrized Tests (multiple inputs) ─
@pytest.mark.parametrize("a, b, expected", [
    (10, 5, 2.0),
    (9, 3, 3.0),
    (7, 2, 3.5),
])
def test_divide(a, b, expected):
    assert divide(a, b) == expected

# ─── Testing Exceptions ──────────────────
def test_divide_by_zero():
    with pytest.raises(ValueError, match="Cannot divide by zero"):
        divide(10, 0)

# Run: pytest test_calculator.py -v
```

---

### Week 19–20: Environment & DevOps Essentials
| # | Topic | Priority | Est. Hours | Status |
|---|-------|----------|-----------|--------|
| 62 | **Virtual Environments** — `venv`, `pyenv`, `uv` (new & fast) | 🔴 Critical | 2h | ⬜ |
| 63 | **`pyproject.toml`** — modern Python project configuration | 🟡 Important | 1h | ⬜ |
| 64 | **Poetry / uv** — dependency management | 🟡 Important | 2h | ⬜ |
| 65 | **Docker basics** — containerize Python apps | 🟡 Important | 3h | ⬜ |
| 66 | **CI/CD** — GitHub Actions for Python projects | 🟡 Important | 2h | ⬜ |
| 67 | **Deployment** — deploy to Railway / Render / AWS | 🟡 Important | 3h | ⬜ |

---

## 📊 COMPLETE TIMELINE OVERVIEW

```
WEEK  1  ████ Syntax, Variables, Loops, Conditionals
WEEK  2  ████ Lists, Tuples, Sets, Dicts, Strings
WEEK  3  ████ Functions, Lambdas, Error Handling
WEEK  4  ████ Modules, Files, Pip, venv
          ──── 🎯 MILESTONE: Build CLI Expense Tracker ────

WEEK  5  ████ OOP — Classes, Inheritance
WEEK  6  ████ OOP — Dunder Methods, Abstraction
WEEK  7  ████ Comprehensions, Generators, Decorators
WEEK  8  ████ Iterators, Context Managers, Regex
WEEK  9  ████ DSA — Arrays, Hashing, Stacks, Queues
WEEK 10  ████ DSA — Trees, Recursion, Sorting
          ──── 🎯 MILESTONE: Build OOP-Based Project ────

WEEK 11  ████ Type Hints, Pydantic, mypy
WEEK 12  ████ Code Quality — ruff, black, linting
WEEK 13  ████ Threading, Multiprocessing, GIL
WEEK 14  ████ Async/Await, asyncio, aiohttp
WEEK 15  ████ FastAPI / Django — Part 1
WEEK 16  ████ FastAPI / Django — Part 2 + Project
          ──── 🎯 MILESTONE: Build & Deploy REST API ────

WEEK 17  ████ Testing — pytest, unittest
WEEK 18  ████ Documentation — Sphinx, docstrings
WEEK 19  ████ Docker, CI/CD, pyproject.toml
WEEK 20  ████ Deployment + Portfolio Project
          ──── 🏆 MILESTONE: Full-Stack Python Project ────
```

---

## 🏋️ PROJECTS TO BUILD (Phase-wise)

| Phase | Project | Skills Covered | Resume Value |
|-------|---------|---------------|-------------|
| 🟢 Week 4 | **CLI Expense Tracker** | File I/O, Functions, JSON | ⭐⭐ |
| 🟢 Week 6 | **Library Management System** (OOP) | Classes, Inheritance, File handling | ⭐⭐⭐ |
| 🟡 Week 10 | **Web Scraper + Data Analyzer** | Modules, Regex, Data processing | ⭐⭐⭐ |
| 🔴 Week 16 | **REST API** (FastAPI/Django) | Frameworks, DB, Auth, Pydantic | ⭐⭐⭐⭐ |
| 🏆 Week 20 | **Full-Stack App with Docker + CI/CD** | Everything combined | ⭐⭐⭐⭐⭐ |

---

## 📚 BEST RESOURCES (Curated)

| Category | Resource | Type | Best For |
|----------|----------|------|----------|
| 🎥 Beginner | **CodeWithHarry** (Hindi) | YouTube | Absolute basics |
| 🎥 Beginner | **Telusko** | YouTube | Clear explanations |
| 🎥 Intermediate | **Corey Schafer** | YouTube | OOP, Decorators, Generators |
| 🎥 Advanced | **ArjanCodes** | YouTube | Design patterns, best practices |
| 📖 Book | **Automate the Boring Stuff** (Al Sweigart) | Free online | Practical Python |
| 📖 Book | **Fluent Python** (Luciano Ramalho) | Book | Deep Python mastery |
| 🌐 Practice | **LeetCode** (Python) | Platform | DSA in Python |
| 🌐 Practice | **HackerRank Python Track** | Platform | Language-specific practice |
| 🌐 Docs | **docs.python.org** | Official | Standard library reference |
| 🌐 Roadmap | **roadmap.sh/python** | Website | Visual learning path |

---
