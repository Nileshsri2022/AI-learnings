

# 🏛️ COMPLETE SOFTWARE DESIGN & ARCHITECTURE ROADMAP
### From Messy Code to Enterprise-Grade Architecture — Structured & Actionable

---

## 📍 Where You Are → Where You'll Go

```
🟢 FOUNDATION          🟡 INTERMEDIATE          🔴 ADVANCED            🏆 ARCHITECT
   (Weeks 1-5)            (Weeks 6-12)            (Weeks 13-18)         (Weeks 19-24)
   
   Clean Code,            Design Patterns,        Architectural          Microservices,
   Paradigms,             SOLID, DRY,             Styles & Patterns,     DDD, CQRS,
   OOP Mastery            Composition             System Thinking        Enterprise
```

---

## 🧒 ELI5: Why Software Design & Architecture Matters

```
🏠 Building a House Analogy:

  CODING without Design = Building a house by randomly 
  placing bricks. It might "work" for a shed, but try 
  building a 10-floor building that way → it COLLAPSES.

  ┌──────────────────────────────────────────────────────────┐
  │                                                          │
  │  Student Code          vs       Professional Code        │
  │  ─────────────                  ─────────────────        │
  │  • 1 file, 2000 lines           • 50 files, 40 lines each│
  │  • "it works" = done             • maintainable = done    │
  │  • copy-paste everywhere         • DRY, reusable          │
  │  • God class does everything     • Single responsibility  │
  │  • Change 1 thing → 10 break    • Change 1 thing → only  │
  │                                    1 thing changes        │
  │  • Only YOU understand it        • Team can understand    │
  │  • Works for college project     • Works for 10M users    │
  │                                                          │
  └──────────────────────────────────────────────────────────┘

  Software Design = Blueprint of EACH room (how code is written)
  Architecture     = Blueprint of the ENTIRE building 
                     (how systems talk to each other)
```

```
📊 THE FULL PICTURE — How Everything Connects

  ┌─────────────────────────────────────────────────────────────┐
  │                                                             │
  │   CLEAN CODE          "How do I write a single line well?"  │
  │        ▼                                                    │
  │   PROGRAMMING         "What style/paradigm should I use?"   │
  │   PARADIGMS                                                 │
  │        ▼                                                    │
  │   OOP                 "How do I model real-world objects?"   │
  │        ▼                                                    │
  │   DESIGN PRINCIPLES   "What rules make my code flexible?"   │
  │        ▼                                                    │
  │   DESIGN PATTERNS     "What are proven solutions to         │
  │        ▼               common problems?"                    │
  │   ARCHITECTURAL       "How do I structure the WHOLE app?"   │
  │   PRINCIPLES                                                │
  │        ▼                                                    │
  │   ARCHITECTURAL       "What communication style should      │
  │   STYLES               my components use?"                  │
  │        ▼                                                    │
  │   ARCHITECTURAL       "What's the overall blueprint?"       │
  │   PATTERNS             (MVC, Microservices, etc.)           │
  │        ▼                                                    │
  │   ENTERPRISE          "How do I handle business logic       │
  │   PATTERNS             at scale?"                           │
  │                                                             │
  │   ZOOM:  Line → Class → Module → Component → System → Org  │
  │                                                             │
  └─────────────────────────────────────────────────────────────┘
```

---

## 🟢 PHASE 1: FOUNDATION — Clean Code & Paradigms (Weeks 1–5)

### Week 1–2: Clean Code Principles

| # | Topic | Priority | Est. Hours | Status |
|---|-------|----------|-----------|--------|
| 1 | **Meaningful Names** — variables, functions, classes | 🔴 Critical | 2h | ⬜ |
| 2 | **Be Consistent** — naming, formatting, patterns | 🔴 Critical | 1h | ⬜ |
| 3 | **Keep Methods/Classes/Files Small** — SRP at micro level | 🔴 Critical | 2h | ⬜ |
| 4 | **Pure Functions** — no side effects, predictable output | 🔴 Critical | 2h | ⬜ |
| 5 | **Indentation & Code Style** — linting, formatting tools | 🟡 Important | 1h | ⬜ |
| 6 | **Minimize Cyclomatic Complexity** — reduce nesting, early returns | 🟡 Important | 2h | ⬜ |
| 7 | **Avoid Passing Nulls & Booleans** — use enums, optionals | 🟡 Important | 1h | ⬜ |
| 8 | **Command-Query Separation** — methods either DO or RETURN, not both | 🟡 Important | 1h | ⬜ |
| 9 | **Keep Framework Code Distant** — isolate vendor dependencies | 🟡 Important | 2h | ⬜ |
| 10 | **Use Correct Constructs** — right tool for the right job | 🟢 Good to know | 1h | ⬜ |
| 11 | **Tests: Fast & Independent** — no test depends on another | 🟡 Important | 2h | ⬜ |
| 12 | **Organize Code by Actor** — group by feature, not by type | 🟡 Important | 1h | ⬜ |
| 13 | **Refactor Often** — KISS, continuous improvement | 🔴 Critical | 2h | ⬜ |

```python
# ❌ DIRTY CODE — What Most Students Write

def p(d):
    t = 0
    for i in d:
        if i['t'] == 'f':
            if i['a'] > 1000:
                t = t + i['a']
                i['s'] = True
            else:
                i['s'] = False
        elif i['t'] == 'v':
            if i['a'] > 500:
                t = t + i['a']
                i['s'] = True
            else:
                i['s'] = False
    return t

# What does this do? 🤷 Nobody knows without reading every line.
# What is 'p'? 'd'? 't'? 'f'? 'a'? 's'?
```

```python
# ✅ CLEAN CODE — What Professionals Write

from dataclasses import dataclass
from enum import Enum
from typing import List


class PaymentType(Enum):
    FULL = "full"
    PARTIAL = "partial"  # Instead of magic strings "f", "v"


@dataclass
class FeePayment:
    student_name: str
    payment_type: PaymentType
    amount: float
    is_verified: bool = False


# 🎯 Rule: Meaningful names > comments
# 🎯 Rule: Small, focused functions (each does ONE thing)

def calculate_minimum_threshold(payment_type: PaymentType) -> float:
    """Returns minimum amount for verification based on payment type."""
    thresholds = {
        PaymentType.FULL: 1000.0,
        PaymentType.PARTIAL: 500.0,
    }
    return thresholds[payment_type]


def verify_payment(payment: FeePayment) -> bool:
    """Verify if payment meets minimum threshold."""
    threshold = calculate_minimum_threshold(payment.payment_type)
    return payment.amount >= threshold


def process_fee_payments(payments: List[FeePayment]) -> float:
    """Process all payments, verify eligible ones, return total verified."""
    total_verified = 0.0

    for payment in payments:
        payment.is_verified = verify_payment(payment)
        if payment.is_verified:
            total_verified += payment.amount

    return total_verified


# Usage — reads like English!
payments = [
    FeePayment("Rahul", PaymentType.FULL, 1500),
    FeePayment("Priya", PaymentType.FULL, 800),
    FeePayment("Amit", PaymentType.PARTIAL, 600),
]

total = process_fee_payments(payments)
print(f"Total verified: ₹{total}")  # ₹2100
```

```
🧹 CLEAN CODE CHEAT SHEET

┌────────────────────────────────────┬───────────────────────────────────┐
│         ❌ DIRTY                   │         ✅ CLEAN                  │
├────────────────────────────────────┼───────────────────────────────────┤
│  d = 86400                        │  SECONDS_IN_A_DAY = 86400        │
│  temp = get_data()                │  active_students = get_students()│
│  # check if student is eligible   │  is_eligible = cgpa > 7.0        │
│  if s > 7.0:                      │  if is_eligible:                 │
├────────────────────────────────────┼───────────────────────────────────┤
│  def process(d, f, t, x):        │  def enroll_student(             │
│      ...                          │      student, course,            │
│                                    │      semester, fee):             │
├────────────────────────────────────┼───────────────────────────────────┤
│  if condition:                     │  if not condition:               │
│      if another:                   │      return   # ← early return  │
│          if yet_another:           │  if not another:                 │
│              do_thing()            │      return   # ← guard clause  │
│                                    │  do_thing()                      │
├────────────────────────────────────┼───────────────────────────────────┤
│  def get_student_and_save(id):    │  def get_student(id): ...        │
│      # Does 2 things! ❌          │  def save_student(s): ...        │
│                                    │  # CQS: separate read & write   │
├────────────────────────────────────┼───────────────────────────────────┤
│  def calculate(data, flag=True):  │  def calculate_with_tax(data):   │
│      if flag:                      │  def calculate_without_tax(data):│
│          # with tax                │  # No boolean params!            │
│      else:                         │                                   │
│          # without tax             │                                   │
├────────────────────────────────────┼───────────────────────────────────┤
│  500-line class                    │  50-line class (max)              │
│  20-param function                 │  3-param function (max)           │
│  Deep nesting (5+ levels)          │  Max 2 levels of nesting         │
└────────────────────────────────────┴───────────────────────────────────┘
```

```
📏 PURE FUNCTIONS — The Gold Standard

A function is PURE if:
  1. Same input ALWAYS gives same output
  2. No side effects (doesn't modify anything outside itself)

┌────────────────────────────────┬──────────────────────────────────┐
│  ❌ IMPURE                     │  ✅ PURE                         │
├────────────────────────────────┼──────────────────────────────────┤
│  tax_rate = 0.18               │  def calc_tax(amount, rate):     │
│  def calc_tax(amount):         │      return amount * rate        │
│      return amount * tax_rate  │                                  │
│  # depends on external state!  │  # depends only on arguments    │
├────────────────────────────────┼──────────────────────────────────┤
│  total = 0                     │  def get_total(items):           │
│  def add_to_total(x):          │      return sum(items)           │
│      global total              │                                  │
│      total += x  # MUTATES!   │  # No mutation, returns new val  │
├────────────────────────────────┼──────────────────────────────────┤
│  def greet():                  │  def greet(name):                │
│      name = input()  # I/O!   │      return f"Hello, {name}"     │
│      print(f"Hello, {name}")  │                                  │
└────────────────────────────────┴──────────────────────────────────┘

Why pure functions matter:
  ✅ Easy to test (no mocking needed)
  ✅ Easy to reason about (predictable)
  ✅ Parallelizable (no shared state)
  ✅ Cacheable (same input = same output = cache it!)
```

---

### Week 3: Programming Paradigms

| # | Topic | Priority | Est. Hours | Status |
|---|-------|----------|-----------|--------|
| 14 | **Structured Programming** — sequential, selection, iteration, no `goto` | 🟡 Important | 2h | ⬜ |
| 15 | **Functional Programming** — immutability, higher-order functions, composition | 🔴 Critical | 4h | ⬜ |
| 16 | **Object-Oriented Programming** — encapsulation, inheritance, polymorphism, abstraction | 🔴 Critical | 4h | ⬜ |
| 17 | **Comparing Paradigms** — when to use which, hybrid approaches | 🟡 Important | 2h | ⬜ |

```
🎭 THREE PARADIGMS — The Restaurant Kitchen Analogy 🍳

┌──────────────────────────────────────────────────────────────────┐
│                                                                  │
│  STRUCTURED = Recipe Book 📖                                     │
│  ─────────────────────────                                       │
│  "Step 1: Boil water. Step 2: Add rice. Step 3: Wait 15 min."   │
│  → Follow steps top to bottom                                    │
│  → Use if/else for decisions, loops for repetition               │
│  → No jumping around (no goto)                                   │
│  → Good for: Scripts, simple programs                            │
│                                                                  │
│                                                                  │
│  OOP = Restaurant with Roles 🏪                                  │
│  ───────────────────────────                                      │
│  Chef object: knows how to cook, has recipes (data + behavior)   │
│  Waiter object: knows how to serve, has tables assigned           │
│  Manager object: knows how to manage, has staff list              │
│  Each person (object) has their own job (methods)                │
│  and their own stuff (attributes/state)                          │
│  → Good for: Large apps, teams, modeling real-world entities     │
│                                                                  │
│                                                                  │
│  FUNCTIONAL = Assembly Line 🏭                                    │
│  ────────────────────────────                                     │
│  Raw vegetables → wash() → chop() → cook() → plate() → serve() │
│  Each step is a PURE function (no side effects)                  │
│  Input goes in, output comes out, nothing else changes           │
│  Functions are passed around like values (first-class citizens)  │
│  → Good for: Data processing, concurrent systems, ML pipelines  │
│                                                                  │
└──────────────────────────────────────────────────────────────────┘
```

```python
# 🎯 Same Problem, Three Paradigms
# Problem: Filter students with CGPA > 8, apply scholarship, get names

students = [
    {"name": "Rahul", "cgpa": 9.1, "branch": "CSE"},
    {"name": "Priya", "cgpa": 7.5, "branch": "ECE"},
    {"name": "Amit", "cgpa": 8.3, "branch": "CSE"},
    {"name": "Sneha", "cgpa": 6.8, "branch": "ME"},
    {"name": "Karan", "cgpa": 8.9, "branch": "CSE"},
]

# ─── STRUCTURED (Imperative) ────────────────
scholarship_names = []
for student in students:
    if student["cgpa"] > 8.0:
        scholarship_names.append(student["name"].upper())
# → Tells the computer HOW to do it step by step


# ─── OOP ─────────────────────────────────────
class Student:
    def __init__(self, name, cgpa, branch):
        self.name = name
        self.cgpa = cgpa
        self.branch = branch
    
    def is_eligible_for_scholarship(self, min_cgpa=8.0):
        return self.cgpa > min_cgpa
    
    def get_scholarship_name(self):
        return self.name.upper()

class ScholarshipSystem:
    def __init__(self, students):
        self.students = [Student(**s) for s in students]
    
    def get_scholars(self):
        return [
            s.get_scholarship_name()
            for s in self.students
            if s.is_eligible_for_scholarship()
        ]

system = ScholarshipSystem(students)
scholarship_names = system.get_scholars()
# → Models real-world entities and their behaviors


# ─── FUNCTIONAL ──────────────────────────────
from functools import reduce

is_eligible = lambda s: s["cgpa"] > 8.0
get_name = lambda s: s["name"].upper()

scholarship_names = list(map(get_name, filter(is_eligible, students)))

# Or with pipe-style (more readable):
scholarship_names = (
    [s["name"].upper() for s in students if s["cgpa"] > 8.0]
)
# → Declares WHAT to do, not HOW
# → No mutation, no side effects, composable
```

```
⚡ PARADIGM COMPARISON

┌────────────────────┬──────────────┬──────────────┬───────────────┐
│  Feature           │  Structured  │  OOP         │  Functional   │
├────────────────────┼──────────────┼──────────────┼───────────────┤
│  State             │  Global/     │  Encapsulated│  Immutable    │
│  Management        │  Shared      │  in objects  │  (no state)   │
├────────────────────┼──────────────┼──────────────┼───────────────┤
│  Core Unit         │  Procedure   │  Class/Object│  Function     │
├────────────────────┼──────────────┼──────────────┼───────────────┤
│  Data Flow         │  Modified    │  Messages    │  Transformed  │
│                    │  in place    │  between obj │  through fns  │
├────────────────────┼──────────────┼──────────────┼───────────────┤
│  Side Effects      │  Common      │  Controlled  │  Avoided      │
├────────────────────┼──────────────┼──────────────┼───────────────┤
│  Concurrency       │  Difficult   │  Moderate    │  Easy ✅      │
├────────────────────┼──────────────┼──────────────┼───────────────┤
│  Best For          │  Scripts,    │  Large apps, │  Data pipes,  │
│                    │  embedded    │  modeling    │  ML, math     │
├────────────────────┼──────────────┼──────────────┼───────────────┤
│  Languages         │  C, Pascal   │  Java, C++,  │  Haskell,     │
│                    │              │  Python, C#  │  Elixir, Lisp │
├────────────────────┼──────────────┼──────────────┼───────────────┤
│  Industry          │  Declining   │  Dominant    │  Growing 📈   │
│  Trend 2025        │              │  (still #1)  │               │
└────────────────────┴──────────────┴──────────────┴───────────────┘

💡 Reality: Modern code is MULTI-PARADIGM.
   Python/JavaScript/Kotlin support ALL three.
   Use OOP for structure + FP for data transformations.
```

---

### Week 4–5: Object-Oriented Programming (Deep Dive)

| # | Topic | Priority | Est. Hours | Status |
|---|-------|----------|-----------|--------|
| 18 | **Encapsulation** — data hiding, getters/setters, properties | 🔴 Critical | 2h | ⬜ |
| 19 | **Abstraction** — abstract classes, interfaces, hiding complexity | 🔴 Critical | 2h | ⬜ |
| 20 | **Inheritance** — single, multiple, diamond problem, super() | 🔴 Critical | 3h | ⬜ |
| 21 | **Polymorphism** — method overriding, duck typing, runtime dispatch | 🔴 Critical | 2h | ⬜ |
| 22 | **Abstract Classes vs Interfaces** — when to use which | 🔴 Critical | 2h | ⬜ |
| 23 | **Concrete Classes vs Class Variants** — mixins, inner classes | 🟡 Important | 1h | ⬜ |
| 24 | **Scope/Visibility** — public, private, protected, package | 🟡 Important | 1h | ⬜ |
| 25 | **Model-Driven Design** — Domain models, Anemic models, Domain Language | 🟡 Important | 3h | ⬜ |
| 26 | **Layered Architectures** — presentation, business, data layers | 🟡 Important | 2h | ⬜ |

```
🏗️ OOP FOUR PILLARS — The College Analogy 🎓

┌─────────────────────────────────────────────────────────────────┐
│                                                                 │
│  1. ENCAPSULATION 🔒 = College ID Card                          │
│  ─────────────────────                                          │
│  Your Aadhaar number is PRIVATE (only you know it)              │
│  Your name is PUBLIC (everyone can see it)                      │
│  Your marks are PROTECTED (only teachers can see)               │
│  → Data + methods that operate on that data = bundled together  │
│  → Control WHO can access WHAT                                  │
│                                                                 │
│  2. ABSTRACTION 🎭 = UPI Payment                                │
│  ──────────────────                                              │
│  You tap "Pay ₹500" on GPay                                    │
│  You DON'T know: IMPS? NEFT? Which server? Which protocol?     │
│  → Hide complex implementation, show simple interface           │
│  → User sees: pay(amount) — that's it                           │
│                                                                 │
│  3. INHERITANCE 👨‍👦 = Family Tree                                 │
│  ───────────────────                                             │
│  Grandparent: Person (has name, age)                            │
│    Parent: Student (inherits name, age + adds roll_no, cgpa)    │
│      Child: CSEStudent (inherits all + adds programming_langs)  │
│  → Reuse code, build hierarchies, specialize behavior           │
│                                                                 │
│  4. POLYMORPHISM 🦎 = "Pay" Button                               │
│  ──────────────────────                                          │
│  Same action "pay()" behaves differently:                       │
│    CreditCard.pay()  → charges card                             │
│    UPI.pay()         → sends via UPI                            │
│    Cash.pay()        → deducts from wallet                      │
│  → Same interface, different implementations                    │
│  → The caller doesn't care HOW it's done                        │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
```

```python
# 🏗️ OOP In Action — Payment Gateway System

from abc import ABC, abstractmethod
from dataclasses import dataclass, field
from datetime import datetime
from typing import List
from enum import Enum


# ─── ABSTRACTION: Define WHAT, not HOW ───────
class PaymentMethod(ABC):
    """Abstract class — cannot be instantiated directly"""
    
    @abstractmethod
    def pay(self, amount: float) -> bool:
        """Process payment — each method implements differently"""
        pass
    
    @abstractmethod
    def refund(self, transaction_id: str) -> bool:
        pass
    
    def validate_amount(self, amount: float) -> bool:
        """Common validation — inherited by all subclasses"""
        return amount > 0


# ─── INHERITANCE + POLYMORPHISM ──────────────
class UPIPayment(PaymentMethod):
    def __init__(self, upi_id: str):
        self._upi_id = upi_id  # ENCAPSULATION: protected
    
    def pay(self, amount: float) -> bool:
        if not self.validate_amount(amount):
            return False
        print(f"💳 UPI: ₹{amount} debited from {self._upi_id}")
        return True
    
    def refund(self, transaction_id: str) -> bool:
        print(f"↩️ UPI Refund initiated for {transaction_id}")
        return True


class CreditCardPayment(PaymentMethod):
    def __init__(self, card_number: str):
        self.__card_number = card_number  # ENCAPSULATION: private
    
    def pay(self, amount: float) -> bool:
        if not self.validate_amount(amount):
            return False
        masked = f"****{self.__card_number[-4:]}"
        print(f"💳 Card: ₹{amount} charged to {masked}")
        return True
    
    def refund(self, transaction_id: str) -> bool:
        print(f"↩️ Card Refund: {transaction_id} (5-7 business days)")
        return True


class WalletPayment(PaymentMethod):
    def __init__(self, balance: float = 0):
        self._balance = balance
    
    def pay(self, amount: float) -> bool:
        if amount > self._balance:
            print(f"❌ Insufficient wallet balance!")
            return False
        self._balance -= amount
        print(f"👛 Wallet: ₹{amount} paid. Remaining: ₹{self._balance}")
        return True
    
    def refund(self, transaction_id: str) -> bool:
        print(f"↩️ Wallet Refund: instant credit for {transaction_id}")
        return True


# ─── POLYMORPHISM IN ACTION ──────────────────
# The checkout function doesn't know/care WHICH payment method
# Same code works for UPI, Card, Wallet, or any future method!

@dataclass
class Order:
    items: List[str]
    total: float
    payment: PaymentMethod  # ← accepts ANY payment method
    
    def checkout(self) -> bool:
        """Polymorphic — works with ANY PaymentMethod subclass"""
        print(f"\n🛒 Order: {', '.join(self.items)} = ₹{self.total}")
        return self.payment.pay(self.total)  # ← SAME call, DIFFERENT behavior


# Usage — see how the SAME checkout() works differently
upi = UPIPayment("rahul@okicici")
card = CreditCardPayment("4111111111111234")
wallet = WalletPayment(balance=2000)

Order(["Laptop Stand"], 899, upi).checkout()
#  💳 UPI: ₹899 debited from rahul@okicici

Order(["Keyboard"], 1499, card).checkout()
#  💳 Card: ₹1499 charged to ****1234

Order(["Mouse"], 599, wallet).checkout()
#  👛 Wallet: ₹599 paid. Remaining: ₹1401

# 🎯 KEY INSIGHT: If tomorrow you add CryptoPayment, 
# you just create a new class. ZERO changes to Order/checkout!
```

```
📊 Abstract Class vs Interface — When to Use What?

┌──────────────────────┬──────────────────────┬──────────────────────┐
│                      │  Abstract Class      │  Interface           │
├──────────────────────┼──────────────────────┼──────────────────────┤
│  Methods             │  Can have both       │  Only abstract       │
│                      │  abstract + concrete │  (in pure form)      │
├──────────────────────┼──────────────────────┼──────────────────────┤
│  State (variables)   │  ✅ Can have         │  ❌ Cannot           │
├──────────────────────┼──────────────────────┼──────────────────────┤
│  Multiple            │  ❌ (in Java/C#)     │  ✅ Yes              │
│  Inheritance         │  ✅ (in Python/C++)  │                      │
├──────────────────────┼──────────────────────┼──────────────────────┤
│  Constructor         │  ✅ Yes              │  ❌ No               │
├──────────────────────┼──────────────────────┼──────────────────────┤
│  When to Use         │  "IS-A" with shared  │  "CAN-DO" — defines │
│                      │  behavior/state      │  a capability        │
├──────────────────────┼──────────────────────┼──────────────────────┤
│  Example             │  Vehicle (has engine, │  Payable, Printable, │
│                      │  shared start())     │  Serializable        │
├──────────────────────┼──────────────────────┼──────────────────────┤
│  Analogy             │  "All students have  │  "Anyone who can     │
│                      │  name & attend class"│  code can enter      │
│                      │  (shared identity)   │  hackathon"          │
│                      │                      │  (shared capability) │
└──────────────────────┴──────────────────────┴──────────────────────┘
```

```
🏢 MODEL-DRIVEN DESIGN CONCEPTS

  DOMAIN MODEL (Rich):
  ────────────────────
  class Student:
      name, cgpa, courses
      enroll(course)         ← Business logic INSIDE the model
      calculate_gpa()        ← Model knows how to do things
      is_eligible_for_exam()
  → Object has BOTH data AND behavior
  → ✅ Preferred in DDD (Domain-Driven Design)
  
  
  ANEMIC MODEL (Thin):
  ────────────────────
  class Student:
      name, cgpa, courses    ← Just data, no logic
  
  class StudentService:
      enroll(student, course)      ← Logic is OUTSIDE
      calculate_gpa(student)       ← In "service" classes
      check_eligibility(student)
  → Object is just a data bag (like a struct)
  → ❌ Considered anti-pattern by some (Martin Fowler)
  → But commonly seen in enterprise Java/Spring code


  DOMAIN LANGUAGE (Ubiquitous Language):
  ──────────────────────────────────────
  Use the SAME terms that business/domain experts use.
  
  ❌ Code: user.setFlag(true)
  ✅ Code: student.enroll_in_semester(semester=5)
  
  ❌ Code: process_type_2_transaction()
  ✅ Code: approve_scholarship_application()
```

---

## 🟡 PHASE 2: DESIGN PRINCIPLES & PATTERNS (Weeks 6–12)

### Week 6–7: Design Principles — SOLID & Beyond

| # | Topic | Priority | Est. Hours | Status |
|---|-------|----------|-----------|--------|
| 27 | **SOLID — S: Single Responsibility Principle** | 🔴 Critical | 2h | ⬜ |
| 28 | **SOLID — O: Open/Closed Principle** | 🔴 Critical | 2h | ⬜ |
| 29 | **SOLID — L: Liskov Substitution Principle** | 🔴 Critical | 2h | ⬜ |
| 30 | **SOLID — I: Interface Segregation Principle** | 🔴 Critical | 2h | ⬜ |
| 31 | **SOLID — D: Dependency Inversion Principle** | 🔴 Critical | 2h | ⬜ |
| 32 | **DRY** — Don't Repeat Yourself | 🔴 Critical | 1h | ⬜ |
| 33 | **YAGNI** — You Aren't Gonna Need It | 🟡 Important | 1h | ⬜ |
| 34 | **Composition over Inheritance** | 🔴 Critical | 2h | ⬜ |
| 35 | **Encapsulate What Varies** | 🟡 Important | 1h | ⬜ |
| 36 | **Program Against Abstractions** | 🔴 Critical | 2h | ⬜ |
| 37 | **Hollywood Principle** — "Don't call us, we'll call you" | 🟡 Important | 1h | ⬜ |
| 38 | **Law of Demeter** — "Talk only to your friends" | 🟡 Important | 1h | ⬜ |
| 39 | **Tell, Don't Ask** — objects decide, callers don't micromanage | 🟡 Important | 1h | ⬜ |

```
🔴 SOLID PRINCIPLES — The 5 Commandments of OOP

Each explained with a college analogy 🎓 + code example:

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

S — SINGLE RESPONSIBILITY PRINCIPLE (SRP)
"A class should have only ONE reason to change"

  🎓 Analogy: A professor should ONLY teach.
     Not also clean classrooms, repair AC, and cook canteen food.
     If cooking policy changes, why should the professor's job change?

  ❌ VIOLATION:
  class Student:
      def calculate_gpa(self): ...
      def save_to_database(self): ...     # DB concern!
      def generate_pdf_report(self): ...  # UI/Report concern!
      def send_email(self): ...           # Communication concern!
  
  ✅ FIX:
  class Student:
      def calculate_gpa(self): ...         # Only student logic
  
  class StudentRepository:
      def save(self, student): ...         # Only DB operations
  
  class ReportGenerator:
      def generate_pdf(self, student): ... # Only report logic
  
  class EmailService:
      def send(self, to, subject): ...     # Only email logic

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

O — OPEN/CLOSED PRINCIPLE (OCP)
"Open for EXTENSION, Closed for MODIFICATION"

  🎓 Analogy: College can ADD new departments (CSE, AI, DS)
     without MODIFYING the existing administration building.
     New wings are ADDED, old structure stays untouched.

  ❌ VIOLATION:
  def calculate_fee(student_type):
      if student_type == "regular":
          return 50000
      elif student_type == "lateral":
          return 40000
      elif student_type == "nri":       # Adding new type = modifying!
          return 200000
      # Every new type = modify this function = risky!
  
  ✅ FIX (using polymorphism):
  class FeeCalculator(ABC):
      @abstractmethod
      def calculate(self) -> float: pass
  
  class RegularFee(FeeCalculator):
      def calculate(self): return 50000
  
  class LateralFee(FeeCalculator):
      def calculate(self): return 40000
  
  class NRIFee(FeeCalculator):          # NEW class, no old code touched!
      def calculate(self): return 200000

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

L — LISKOV SUBSTITUTION PRINCIPLE (LSP)
"Subclass must be usable in place of its parent class"

  🎓 Analogy: If you hire a "Teaching Assistant" (TA),
     they should be able to do everything a "Teacher" can.
     If a TA can't grade papers but a Teacher can,
     and your system expects anyone labeled "Teacher" to grade,
     the TA BREAKS the system.

  ❌ VIOLATION:
  class Bird:
      def fly(self): print("Flying!")
  
  class Penguin(Bird):                   # Penguin IS-A Bird...
      def fly(self): raise Exception()   # ...but CAN'T fly! 💥
  
  ✅ FIX:
  class Bird(ABC):
      @abstractmethod
      def move(self): pass
  
  class Sparrow(Bird):
      def move(self): print("Flying!")
  
  class Penguin(Bird):
      def move(self): print("Swimming!")  # All birds can move ✅

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

I — INTERFACE SEGREGATION PRINCIPLE (ISP)
"Don't force a class to implement methods it doesn't need"

  🎓 Analogy: Don't make every student join ALL clubs.
     Sports student shouldn't be forced to join Coding Club.
     Let students pick which clubs (interfaces) they join.

  ❌ VIOLATION:
  class Worker(ABC):
      @abstractmethod
      def code(self): pass
      @abstractmethod
      def design(self): pass
      @abstractmethod
      def test(self): pass
      @abstractmethod
      def manage(self): pass   # A junior dev shouldn't manage!
  
  ✅ FIX (split into focused interfaces):
  class Coder(ABC):
      @abstractmethod
      def code(self): pass
  
  class Designer(ABC):
      @abstractmethod
      def design(self): pass
  
  class Manager(ABC):
      @abstractmethod
      def manage(self): pass
  
  class FullStackDev(Coder, Designer):  # Picks ONLY what it needs
      def code(self): ...
      def design(self): ...

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

D — DEPENDENCY INVERSION PRINCIPLE (DIP)
"High-level modules should NOT depend on low-level modules.
 Both should depend on ABSTRACTIONS."

  🎓 Analogy: The Dean (high-level) shouldn't directly depend
     on a specific professor (low-level). The Dean depends on
     the ROLE "Professor" (abstraction). Any professor can 
     fill that role.

  ❌ VIOLATION:
  class MySQLDatabase:
      def save(self, data): ...    # Concrete implementation
  
  class StudentService:
      def __init__(self):
          self.db = MySQLDatabase()  # DIRECTLY depends on MySQL!
          # What if we want to switch to PostgreSQL? 
          # Must CHANGE StudentService! 💥
  
  ✅ FIX:
  class Database(ABC):              # Abstraction
      @abstractmethod
      def save(self, data): pass
  
  class MySQLDatabase(Database):
      def save(self, data): ...
  
  class PostgresDatabase(Database):
      def save(self, data): ...
  
  class StudentService:
      def __init__(self, db: Database):  # Depends on ABSTRACTION
          self.db = db                   # Can inject ANY database!
  
  # Usage:
  service = StudentService(PostgresDatabase())  # Easy to switch!
```

```python
# 🔥 COMPOSITION OVER INHERITANCE — The Most Important Principle

# ❌ INHERITANCE HELL (Rigid hierarchy)
class Animal:
    def eat(self): print("eating")

class FlyingAnimal(Animal):
    def fly(self): print("flying")

class SwimmingAnimal(Animal):
    def swim(self): print("swimming")

# Problem: Duck can BOTH fly AND swim!
# Multiple inheritance? → Diamond problem
# Create FlyingSwimmingAnimal? → Explosion of classes!


# ✅ COMPOSITION (Flexible, mix-and-match)
class FlyAbility:
    def fly(self): print("flying")

class SwimAbility:
    def swim(self): print("swimming")

class RunAbility:
    def run(self): print("running")


class Duck:
    def __init__(self):
        self.flying = FlyAbility()    # HAS-A flying ability
        self.swimming = SwimAbility() # HAS-A swimming ability
    
    def fly(self): self.flying.fly()
    def swim(self): self.swimming.swim()


class Dog:
    def __init__(self):
        self.running = RunAbility()
        self.swimming = SwimAbility()
    
    def run(self): self.running.run()
    def swim(self): self.swimming.swim()

# 💡 Rule of thumb:
#    Use INHERITANCE for "is-a" (Dog IS-A Animal)
#    Use COMPOSITION for "has-a" (Car HAS-A Engine)
#    When in doubt → COMPOSITION
```

```
📏 OTHER DESIGN PRINCIPLES — Quick Reference

┌────────────────────────────┬─────────────────────────────────────────┐
│  Principle                 │  ELI5 + Rule                            │
├────────────────────────────┼─────────────────────────────────────────┤
│  DRY                       │  Don't copy-paste! Extract common code │
│  (Don't Repeat Yourself)   │  into functions/classes/modules.       │
│                            │  "Every piece of knowledge must have   │
│                            │   a single representation"             │
├────────────────────────────┼─────────────────────────────────────────┤
│  YAGNI                     │  Don't build features "just in case".  │
│  (You Aren't Gonna Need It)│  Build ONLY what's needed NOW.        │
│                            │  "Maybe we'll need blockchain" → NO    │
├────────────────────────────┼─────────────────────────────────────────┤
│  KISS                      │  Keep It Simple, Stupid.               │
│                            │  Simplest solution that works = best.  │
├────────────────────────────┼─────────────────────────────────────────┤
│  Law of Demeter            │  Only talk to your DIRECT friends.     │
│  (Don't talk to strangers) │  ❌ student.department.hod.email       │
│                            │  ✅ student.get_hod_email()            │
├────────────────────────────┼─────────────────────────────────────────┤
│  Tell, Don't Ask           │  Don't check object's state then act.  │
│                            │  ❌ if student.cgpa > 8: give_award()  │
│                            │  ✅ student.check_and_give_award()     │
├────────────────────────────┼─────────────────────────────────────────┤
│  Hollywood Principle       │  "Don't call us, we'll call you."      │
│                            │  Framework calls YOUR code, not vice   │
│                            │  versa. (Inversion of Control)         │
├────────────────────────────┼─────────────────────────────────────────┤
│  Encapsulate What Varies   │  Identify what changes often and       │
│                            │  isolate it behind an interface.       │
│                            │  Payment method changes? → Strategy    │
│                            │  pattern behind PaymentMethod ABC.     │
├────────────────────────────┼─────────────────────────────────────────┤
│  Program Against           │  Depend on interfaces, not concrete    │
│  Abstractions              │  classes. Same as DIP from SOLID.      │
│                            │  ❌ def save(mysql: MySQL)             │
│                            │  ✅ def save(db: Database)             │
└────────────────────────────┴─────────────────────────────────────────┘
```

---

### Week 8–10: Design Patterns (GoF)

| # | Topic | Priority | Est. Hours | Status |
|---|-------|----------|-----------|--------|
| 40 | **What are Design Patterns?** — why they exist, categories | 🔴 Critical | 1h | ⬜ |
| | **CREATIONAL PATTERNS** | | | |
| 41 | **Singleton** — one instance only | 🔴 Critical | 2h | ⬜ |
| 42 | **Factory Method** — create objects without specifying class | 🔴 Critical | 2h | ⬜ |
| 43 | **Abstract Factory** — family of related objects | 🟡 Important | 2h | ⬜ |
| 44 | **Builder** — construct complex objects step by step | 🔴 Critical | 2h | ⬜ |
| 45 | **Prototype** — clone existing objects | 🟢 Good to know | 1h | ⬜ |
| | **STRUCTURAL PATTERNS** | | | |
| 46 | **Adapter** — make incompatible interfaces work together | 🔴 Critical | 2h | ⬜ |
| 47 | **Decorator** — add behavior dynamically | 🔴 Critical | 2h | ⬜ |
| 48 | **Facade** — simplify complex subsystem | 🔴 Critical | 1h | ⬜ |
| 49 | **Proxy** — control access to an object | 🟡 Important | 2h | ⬜ |
| 50 | **Composite** — tree structures, part-whole hierarchies | 🟡 Important | 2h | ⬜ |
| 51 | **Bridge** — separate abstraction from implementation | 🟢 Good to know | 1h | ⬜ |
| 52 | **Flyweight** — share objects to save memory | 🟢 Good to know | 1h | ⬜ |
| | **BEHAVIORAL PATTERNS** | | | |
| 53 | **Strategy** — swap algorithms at runtime | 🔴 Critical | 2h | ⬜ |
| 54 | **Observer** — notify multiple objects of changes | 🔴 Critical | 2h | ⬜ |
| 55 | **Command** — encapsulate requests as objects | 🟡 Important | 2h | ⬜ |
| 56 | **Template Method** — define algorithm skeleton, subclass fills steps | 🟡 Important | 1h | ⬜ |
| 57 | **Iterator** — traverse collections without exposing internals | 🟡 Important | 1h | ⬜ |
| 58 | **State** — change behavior when internal state changes | 🟡 Important | 2h | ⬜ |
| 59 | **Chain of Responsibility** — pass request along handler chain | 🟢 Good to know | 1h | ⬜ |
| 60 | **Mediator** — reduce chaotic dependencies between objects | 🟢 Good to know | 1h | ⬜ |
| 61 | **Memento** — save and restore state (undo) | 🟢 Good to know | 1h | ⬜ |
| 62 | **Visitor** — add operations without modifying objects | 🟢 Good to know | 1h | ⬜ |

```
🗂️ DESIGN PATTERNS — The Complete Map

  23 GoF (Gang of Four) Patterns from the legendary 1994 book

  ┌─────────────────────────────────────────────────────────────────┐
  │                     DESIGN PATTERNS                             │
  ├───────────────┬──────────────────┬──────────────────────────────┤
  │  CREATIONAL   │  STRUCTURAL      │  BEHAVIORAL                  │
  │  (How to      │  (How to         │  (How objects                │
  │   CREATE)     │   COMPOSE)       │   COMMUNICATE)               │
  ├───────────────┼──────────────────┼──────────────────────────────┤
  │               │                  │                              │
  │  Singleton    │  Adapter 🔌      │  Strategy 🎯                 │
  │  Factory  🏭  │  Decorator 🎀   │  Observer 👁️                 │
  │  Abstract     │  Facade 🏠      │  Command  📦                 │
  │   Factory     │  Proxy 🛡️       │  Template Method 📋          │
  │  Builder 🔧   │  Composite 🌲   │  Iterator 🔄                 │
  │  Prototype 📋 │  Bridge 🌉      │  State 🔄                    │
  │               │  Flyweight 🪶   │  Chain of Responsibility ⛓️  │
  │               │                  │  Mediator 🤝                 │
  │               │                  │  Memento 💾                  │
  │               │                  │  Visitor 🚶                  │
  │               │                  │                              │
  ├───────────────┴──────────────────┴──────────────────────────────┤
  │  MUST KNOW for interviews: Strategy, Observer, Factory,        │
  │  Singleton, Adapter, Decorator, Builder, Command               │
  └─────────────────────────────────────────────────────────────────┘
```

```python
# 🏭 FACTORY PATTERN — "Don't use 'new', use a factory"

# 🎓 Analogy: College Admission Office
# You don't go to each department to register.
# You go to ONE admission office, tell them your branch,
# they CREATE the right student object for you.

from abc import ABC, abstractmethod


class Notification(ABC):
    @abstractmethod
    def send(self, message: str) -> None:
        pass


class EmailNotification(Notification):
    def send(self, message: str):
        print(f"📧 Email: {message}")


class SMSNotification(Notification):
    def send(self, message: str):
        print(f"📱 SMS: {message}")


class PushNotification(Notification):
    def send(self, message: str):
        print(f"🔔 Push: {message}")


class WhatsAppNotification(Notification):
    def send(self, message: str):
        print(f"💬 WhatsApp: {message}")


# ─── FACTORY ─────────────────────────────────
class NotificationFactory:
    """Creates the right notification object based on type"""
    
    _creators = {
        "email": EmailNotification,
        "sms": SMSNotification,
        "push": PushNotification,
        "whatsapp": WhatsAppNotification,
    }
    
    @staticmethod
    def create(channel: str) -> Notification:
        creator = NotificationFactory._creators.get(channel)
        if not creator:
            raise ValueError(f"Unknown channel: {channel}")
        return creator()


# Usage — caller doesn't know which concrete class is created!
notification = NotificationFactory.create("whatsapp")
notification.send("Your OTP is 4521")
# 💬 WhatsApp: Your OTP is 4521

# Adding a new channel = just add to _creators dict. 
# NO changes to calling code. Open/Closed Principle! ✅
```

```python
# 🎯 STRATEGY PATTERN — "Swap algorithms at runtime"

# 🎓 Analogy: Choosing how to go to college
# Same destination, different strategies: Bus, Auto, Walk, Metro
# You PICK the strategy based on situation (rain? late? budget?)

from abc import ABC, abstractmethod
from typing import List


class SortStrategy(ABC):
    @abstractmethod
    def sort(self, data: List[int]) -> List[int]:
        pass


class BubbleSort(SortStrategy):
    def sort(self, data: List[int]) -> List[int]:
        arr = data.copy()
        n = len(arr)
        for i in range(n):
            for j in range(0, n - i - 1):
                if arr[j] > arr[j + 1]:
                    arr[j], arr[j + 1] = arr[j + 1], arr[j]
        print("📊 Used: Bubble Sort (small data)")
        return arr


class QuickSort(SortStrategy):
    def sort(self, data: List[int]) -> List[int]:
        if len(data) <= 1:
            return data
        pivot = data[len(data) // 2]
        left = [x for x in data if x < pivot]
        middle = [x for x in data if x == pivot]
        right = [x for x in data if x > pivot]
        print("⚡ Used: Quick Sort (large data)")
        return self.sort(left) + middle + self.sort(right)


class Sorter:
    """Context — uses whatever strategy is injected"""
    
    def __init__(self, strategy: SortStrategy):
        self._strategy = strategy
    
    def set_strategy(self, strategy: SortStrategy):
        """Change strategy at RUNTIME!"""
        self._strategy = strategy
    
    def sort(self, data: List[int]) -> List[int]:
        return self._strategy.sort(data)


# Usage
data = [64, 34, 25, 12, 22, 11, 90]

sorter = Sorter(BubbleSort())
print(sorter.sort(data))  # Uses BubbleSort

sorter.set_strategy(QuickSort())  # SWITCH strategy!
print(sorter.sort(data))  # Uses QuickSort

# 💡 In real world: payment strategies, compression algorithms,
# pricing rules, authentication methods — all use Strategy pattern
```

```python
# 👁️ OBSERVER PATTERN — "When something changes, notify everyone"

# 🎓 Analogy: College Notice Board
# When a notice is posted, ALL subscribed students get notified.
# You can subscribe/unsubscribe anytime.
# The notice board doesn't know/care WHO is listening.

from abc import ABC, abstractmethod
from typing import List, Dict, Any


class EventManager:
    """The notice board — manages subscribers"""
    
    def __init__(self):
        self._listeners: Dict[str, List] = {}
    
    def subscribe(self, event_type: str, listener):
        if event_type not in self._listeners:
            self._listeners[event_type] = []
        self._listeners[event_type].append(listener)
        print(f"  ✅ {listener.__class__.__name__} subscribed to '{event_type}'")
    
    def unsubscribe(self, event_type: str, listener):
        self._listeners[event_type].remove(listener)
    
    def notify(self, event_type: str, data: Any):
        if event_type in self._listeners:
            for listener in self._listeners[event_type]:
                listener.update(event_type, data)


class Observer(ABC):
    @abstractmethod
    def update(self, event_type: str, data: Any):
        pass


# ─── Concrete Observers ─────────────────────
class EmailAlert(Observer):
    def update(self, event_type: str, data: Any):
        print(f"  📧 Email Alert: [{event_type}] {data}")


class SMSAlert(Observer):
    def update(self, event_type: str, data: Any):
        print(f"  📱 SMS Alert: [{event_type}] {data}")


class DashboardUpdater(Observer):
    def update(self, event_type: str, data: Any):
        print(f"  📊 Dashboard Updated: [{event_type}] {data}")


class LogWriter(Observer):
    def update(self, event_type: str, data: Any):
        print(f"  📝 Log Written: [{event_type}] {data}")


# ─── Subject (Publisher) ─────────────────────
class OrderSystem:
    def __init__(self):
        self.events = EventManager()
    
    def place_order(self, order_id: str, amount: float):
        print(f"\n🛒 Order {order_id} placed for ₹{amount}")
        self.events.notify("order_placed", 
                          {"order_id": order_id, "amount": amount})
    
    def cancel_order(self, order_id: str):
        print(f"\n❌ Order {order_id} cancelled")
        self.events.notify("order_cancelled", {"order_id": order_id})


# Usage
shop = OrderSystem()

# Subscribe different observers to different events
email = EmailAlert()
sms = SMSAlert()
dashboard = DashboardUpdater()
logger = LogWriter()

shop.events.subscribe("order_placed", email)
shop.events.subscribe("order_placed", sms)
shop.events.subscribe("order_placed", dashboard)
shop.events.subscribe("order_cancelled", email)
shop.events.subscribe("order_cancelled", logger)

shop.place_order("ORD001", 1499)
# 📧 Email Alert: [order_placed] {...}
# 📱 SMS Alert: [order_placed] {...}
# 📊 Dashboard Updated: [order_placed] {...}

shop.cancel_order("ORD001")
# 📧 Email Alert: [order_cancelled] {...}
# 📝 Log Written: [order_cancelled] {...}
```

```python
# 🎀 DECORATOR PATTERN — "Add features without modifying the original"

# 🎓 Analogy: Pizza toppings!
# Base pizza = ₹200
# Add cheese = +₹50
# Add mushroom = +₹70
# Add paneer = +₹80
# You WRAP the pizza with toppings. The base pizza doesn't change.

from abc import ABC, abstractmethod


class Coffee(ABC):
    @abstractmethod
    def cost(self) -> float:
        pass
    
    @abstractmethod
    def description(self) -> str:
        pass


class BasicCoffee(Coffee):
    def cost(self): return 50.0
    def description(self): return "Basic Coffee"


# ─── Decorators (Wrappers) ───────────────────
class CoffeeDecorator(Coffee, ABC):
    def __init__(self, coffee: Coffee):
        self._coffee = coffee  # WRAPS another coffee


class MilkDecorator(CoffeeDecorator):
    def cost(self): return self._coffee.cost() + 20.0
    def description(self): return self._coffee.description() + " + Milk"


class SugarDecorator(CoffeeDecorator):
    def cost(self): return self._coffee.cost() + 10.0
    def description(self): return self._coffee.description() + " + Sugar"


class WhippedCreamDecorator(CoffeeDecorator):
    def cost(self): return self._coffee.cost() + 40.0
    def description(self): return self._coffee.description() + " + Whipped Cream"


# Usage — stack decorators like toppings!
coffee = BasicCoffee()                          # ₹50
coffee = MilkDecorator(coffee)                   # ₹70
coffee = SugarDecorator(coffee)                  # ₹80
coffee = WhippedCreamDecorator(coffee)           # ₹120

print(f"☕ {coffee.description()}")
print(f"💰 Total: ₹{coffee.cost()}")
# ☕ Basic Coffee + Milk + Sugar + Whipped Cream
# 💰 Total: ₹120.0
```

```
🎯 WHEN TO USE WHICH PATTERN — Quick Decision Guide

┌─────────────────────────────┬────────────────────────────────────────┐
│  When you need to...        │  Use this pattern                      │
├─────────────────────────────┼────────────────────────────────────────┤
│  Ensure only one instance   │  Singleton (DB connection, Logger)     │
│  Create objects without     │  Factory (Notifications, Payments)     │
│  specifying exact class     │                                        │
│  Build complex object       │  Builder (Query builder, Config)       │
│  step by step               │                                        │
│  Make incompatible things   │  Adapter (Legacy API wrapper)          │
│  work together              │                                        │
│  Add behavior dynamically   │  Decorator (Middleware, Logging)       │
│  Simplify complex subsystem │  Facade (Payment gateway SDK)          │
│  Control access to object   │  Proxy (Caching, Auth, Lazy loading)  │
│  Swap algorithms at runtime │  Strategy (Sorting, Pricing, Auth)     │
│  React to state changes     │  Observer (Events, Pub-Sub)            │
│  Encapsulate a request      │  Command (Undo/Redo, Task queue)       │
│  Define algorithm skeleton  │  Template Method (Data pipeline)       │
│  Change behavior by state   │  State (Order status, Game states)     │
│  Pass request along chain   │  Chain of Resp. (Middleware, Filters)  │
└─────────────────────────────┴────────────────────────────────────────┘
```

---

### Week 11–12: PoSA Patterns & Pattern Mastery

| # | Topic | Priority | Est. Hours | Status |
|---|-------|----------|-----------|--------|
| 63 | **PoSA Patterns** — Layers, Pipes & Filters, Broker, MVC | 🟡 Important | 3h | ⬜ |
| 64 | **Anti-Patterns** — God Object, Spaghetti Code, Golden Hammer | 🟡 Important | 2h | ⬜ |
| 65 | **Refactoring to Patterns** — identify code smells, apply patterns | 🔴 Critical | 4h | ⬜ |
| 66 | **Combining Patterns** — real systems use multiple patterns | 🟡 Important | 3h | ⬜ |

```
⚠️ ANTI-PATTERNS — What NOT to Do

┌─────────────────────────┬────────────────────────────────────────┐
│  Anti-Pattern           │  What It Means                         │
├─────────────────────────┼────────────────────────────────────────┤
│  God Object / God Class │  One class that does EVERYTHING.       │
│                         │  2000-line class with 50 methods.      │
│                         │  Fix: Split into focused classes (SRP) │
├─────────────────────────┼────────────────────────────────────────┤
│  Spaghetti Code         │  Tangled, no structure, impossible to  │
│                         │  follow. goto everywhere, no functions.│
│                         │  Fix: Refactor into modules/functions  │
├─────────────────────────┼────────────────────────────────────────┤
│  Golden Hammer          │  "I know React, so I'll use React for  │
│                         │  everything — even a CLI tool!"        │
│                         │  Fix: Choose right tool for the job    │
├─────────────────────────┼────────────────────────────────────────┤
│  Premature              │  Optimizing code before it even works. │
│  Optimization           │  "Should I use a B-tree here?"         │
│                         │  Fix: Make it work → Make it right     │
│                         │  → Make it fast                        │
├─────────────────────────┼────────────────────────────────────────┤
│  Copy-Paste             │  Duplicating code instead of           │
│  Programming            │  abstracting. Same bug in 10 places.   │
│                         │  Fix: DRY — extract into functions     │
├─────────────────────────┼────────────────────────────────────────┤
│  Lava Flow              │  Dead code nobody dares to remove.     │
│                         │  "What if it breaks something?"        │
│                         │  Fix: Tests + version control = safe   │
│                         │  to delete                             │
└─────────────────────────┴────────────────────────────────────────┘
```

---

## 🔴 PHASE 3: ARCHITECTURE — Principles, Styles & Patterns (Weeks 13–18)

### Week 13–14: Architectural Principles

| # | Topic | Priority | Est. Hours | Status |
|---|-------|----------|-----------|--------|
| 67 | **Component Principles** — cohesion, coupling, component design | 🔴 Critical | 3h | ⬜ |
| 68 | **Coupling & Cohesion** — loose coupling, high cohesion | 🔴 Critical | 3h | ⬜ |
| 69 | **Policy vs Detail** — business rules vs infrastructure | 🟡 Important | 2h | ⬜ |
| 70 | **Boundaries** — defining system boundaries, ports & adapters | 🔴 Critical | 3h | ⬜ |

```
🔗 COUPLING & COHESION — The Two Most Important Architecture Concepts

┌─────────────────────────────────────────────────────────────────┐
│                                                                 │
│  COUPLING = How DEPENDENT modules are on each other             │
│  ─────────────────────────────────────────────────               │
│                                                                 │
│  TIGHT Coupling (❌ Bad):                                       │
│  Module A directly calls Module B's internal functions           │
│  Change B → Must change A → Must change C → 💥 Chain reaction  │
│                                                                 │
│  ┌───────┐     ┌───────┐     ┌───────┐                         │
│  │   A   │────►│   B   │────►│   C   │  Everything connected   │
│  │       │◄────│       │◄────│       │  to everything!         │
│  └───┬───┘     └───┬───┘     └───┬───┘                         │
│      │             │             │                              │
│      └─────────────┴─────────────┘  = Spaghetti 🍝             │
│                                                                 │
│  LOOSE Coupling (✅ Good):                                      │
│  Modules talk through INTERFACES (contracts)                    │
│  Change B's internals → A doesn't even know → ✅               │
│                                                                 │
│  ┌───────┐     ┌─────────┐     ┌───────┐                       │
│  │   A   │────►│Interface│◄────│   B   │  A knows the          │
│  └───────┘     └─────────┘     └───────┘  interface, not B     │
│                                                                 │
│                                                                 │
│  COHESION = How RELATED things inside a module are              │
│  ────────────────────────────────────────────────                │
│                                                                 │
│  LOW Cohesion (❌ Bad):                                         │
│  UserModule: login(), calculate_tax(), send_email(), sort_data()│
│  → Unrelated things shoved together → "Junk drawer"            │
│                                                                 │
│  HIGH Cohesion (✅ Good):                                       │
│  AuthModule: login(), logout(), reset_password(), verify_otp()  │
│  → All related to ONE concept → "Organized toolbox"            │
│                                                                 │
│                                                                 │
│  🎯 GOAL: HIGH Cohesion + LOOSE Coupling                        │
│     = Independent, focused modules that talk through contracts  │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
```

```
🧱 BOUNDARIES & POLICY VS DETAIL

  POLICY = Business Rules (WHAT the system does)
  ─────────────────────────────────────────────
  "Students with CGPA > 8.0 get scholarship"
  "Orders above ₹500 get free delivery"
  → Changes rarely, core of the business
  → Should be at the CENTER of your architecture

  DETAIL = Implementation Choices (HOW it's done)
  ─────────────────────────────────────────────
  "Use MySQL" vs "Use PostgreSQL"
  "Use React" vs "Use Angular"
  "Use AWS" vs "Use GCP"
  → Changes often, should be at the EDGE
  → Should be PLUGGABLE

  ┌────────────────────────────────────────────────────┐
  │                                                    │
  │           ┌──────────────────────┐                 │
  │           │   BUSINESS RULES     │  ← Most stable  │
  │           │   (Domain/Policy)    │                 │
  │           │                      │                 │
  │       ┌───┤   Student.enroll()   ├───┐             │
  │       │   │   Order.calculate()  │   │             │
  │       │   └──────────────────────┘   │             │
  │       │                              │             │
  │   ┌───┴────────┐          ┌─────────┴───┐         │
  │   │  USE CASES  │          │  INTERFACES  │         │
  │   │ (App Logic) │          │  (Ports)     │         │
  │   └───┬────────┘          └─────────┬───┘         │
  │       │                              │             │
  │   ┌───┴────────────────────────────┴───┐          │
  │   │        INFRASTRUCTURE              │          │
  │   │   (DB, API, UI, Frameworks)        │ ← Most   │
  │   │                                    │   volatile│
  │   │   MySQL, React, AWS, SendGrid      │          │
  │   └────────────────────────────────────┘          │
  │                                                    │
  │   Dependencies point INWARD (toward business rules)│
  │   Business rules NEVER depend on infrastructure    │
  │                                                    │
  └────────────────────────────────────────────────────┘
```

---

### Week 15–16: Architectural Styles

| # | Topic | Priority | Est. Hours | Status |
|---|-------|----------|-----------|--------|
| 71 | **Monolithic** — single deployable unit | 🔴 Critical | 2h | ⬜ |
| 72 | **Layered** — presentation, business, data access layers | 🔴 Critical | 3h | ⬜ |
| 73 | **Component-Based** — independent, reusable components | 🟡 Important | 2h | ⬜ |
| 74 | **Client-Server** — request-response model | 🔴 Critical | 1h | ⬜ |
| 75 | **Peer-to-Peer** — decentralized, equal nodes | 🟢 Good to know | 1h | ⬜ |
| 76 | **Event-Driven** — react to events, async processing | 🔴 Critical | 3h | ⬜ |
| 77 | **Publish-Subscribe** — producers and consumers via topics | 🔴 Critical | 2h | ⬜ |
| 78 | **Messaging** — message queues, async communication | 🟡 Important | 2h | ⬜ |
| 79 | **Distributed** — systems across multiple machines | 🟡 Important | 2h | ⬜ |

```
🏗️ ARCHITECTURAL STYLES — The Building Types Analogy 🏘️

┌─────────────────────────────────────────────────────────────────┐
│                                                                 │
│  STRUCTURAL STYLES (How you organize the structure)             │
│                                                                 │
│  MONOLITHIC = One Big Building 🏢                               │
│  ──────────────────────────────                                  │
│  Everything under one roof. One codebase, one deployment.       │
│  ✅ Simple to develop, test, deploy initially                   │
│  ❌ Hard to scale, one bug = entire building shuts down         │
│  📍 Best for: Startups, MVPs, small teams (< 5 devs)           │
│                                                                 │
│  LAYERED = Multi-Floor Building 🏗️                              │
│  ────────────────────────────────                                │
│  Each floor has one purpose:                                    │
│    Floor 4: Presentation (UI)                                   │
│    Floor 3: Business Logic                                      │
│    Floor 2: Data Access                                         │
│    Floor 1: Database                                            │
│  Each floor only talks to the one directly below it.            │
│  ✅ Organized, separation of concerns                           │
│  ❌ Can be rigid, "sinkhole" anti-pattern                       │
│  📍 Best for: Enterprise apps, traditional web apps             │
│                                                                 │
│  COMPONENT-BASED = Modular Building 🧩                          │
│  ────────────────────────────────────                            │
│  Independent rooms that can be rearranged/replaced.             │
│  Auth component, Payment component, Search component.           │
│  ✅ Reusable, replaceable                                       │
│  📍 Best for: Large frontends (React components), plugin systems│
│                                                                 │
│                                                                 │
│  COMMUNICATION STYLES (How components talk)                     │
│                                                                 │
│  CLIENT-SERVER = Restaurant 🍽️                                  │
│  ────────────────────────────                                    │
│  Client (customer) requests, Server (kitchen) responds.         │
│  ✅ Clear roles, centralized server                              │
│  📍 Best for: Web apps, APIs, most internet applications        │
│                                                                 │
│  PEER-TO-PEER = Group Study 👥                                  │
│  ───────────────────────────                                     │
│  Everyone is both client AND server. Share directly.            │
│  ✅ No single point of failure, scales well                      │
│  📍 Best for: File sharing (BitTorrent), Blockchain, WebRTC     │
│                                                                 │
│  EVENT-DRIVEN = WhatsApp Group 📱                               │
│  ──────────────────────────────                                  │
│  Something happens → event fires → listeners react.            │
│  "Order placed" → warehouse preps, email sends, payment charges │
│  ✅ Decoupled, async, scalable                                   │
│  ❌ Hard to debug, eventual consistency                          │
│  📍 Best for: Real-time systems, microservices communication    │
│                                                                 │
│  PUB-SUB = YouTube Subscriptions 🔔                             │
│  ──────────────────────────────────                              │
│  Publisher posts content, Subscribers get notified.              │
│  Publisher doesn't know who's subscribed.                        │
│  ✅ Fully decoupled, scalable                                    │
│  📍 Best for: Notifications, event streaming, chat systems      │
│                                                                 │
│  MESSAGING = Post Office 📬                                     │
│  ────────────────────────                                        │
│  Send message to a queue, receiver picks it up when ready.      │
│  ✅ Async, reliable delivery, load buffering                     │
│  📍 Best for: Background jobs, microservice communication       │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
```

```
⚡ STYLE COMPARISON TABLE

┌───────────────────┬───────────┬────────────┬──────────┬───────────┐
│  Style            │ Coupling  │ Scalability│ Complex. │ Best For  │
├───────────────────┼───────────┼────────────┼──────────┼───────────┤
│ Monolithic        │ High      │ Low        │ Low      │ MVP/Start │
│ Layered           │ Medium    │ Medium     │ Low      │ Enterprise│
│ Client-Server     │ Medium    │ Medium     │ Low      │ Web Apps  │
│ Component-Based   │ Low       │ Medium     │ Medium   │ UI/Plugin │
│ Event-Driven      │ Very Low  │ High       │ High     │ Real-time │
│ Pub-Sub           │ Very Low  │ Very High  │ High     │ Streaming │
│ Peer-to-Peer      │ None      │ Very High  │ Very High│ P2P/Block │
│ Distributed       │ Low       │ Very High  │ Very High│ Cloud     │
└───────────────────┴───────────┴────────────┴──────────┴───────────┘
```

---

### Week 17–18: Architectural Patterns

| # | Topic | Priority | Est. Hours | Status |
|---|-------|----------|-----------|--------|
| 80 | **MVC (Model-View-Controller)** — the most common pattern | 🔴 Critical | 3h | ⬜ |
| 81 | **Microservices** — independent services, API communication | 🔴 Critical | 5h | ⬜ |
| 82 | **Domain-Driven Design (DDD)** — bounded contexts, aggregates | 🔴 Critical | 5h | ⬜ |
| 83 | **CQRS** — Command Query Responsibility Segregation | 🟡 Important | 3h | ⬜ |
| 84 | **Event Sourcing** — store events, not state | 🟡 Important | 3h | ⬜ |
| 85 | **SOA (Service-Oriented Architecture)** — enterprise services | 🟡 Important | 2h | ⬜ |
| 86 | **Serverless** — FaaS, managed services, pay-per-use | 🟡 Important | 2h | ⬜ |
| 87 | **Message Queues/Streams** — RabbitMQ, Kafka | 🟡 Important | 3h | ⬜ |
| 88 | **Microkernel** — plugin-based architecture | 🟢 Good to know | 1h | ⬜ |
| 89 | **Blackboard Pattern** — knowledge sources collaborate | 🟢 Good to know | 1h | ⬜ |

```
🏛️ ARCHITECTURAL PATTERNS — The Grand Tour

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

📱 MVC — Model-View-Controller

  ┌──────────────────────────────────────────────────────────┐
  │                                                          │
  │   USER clicks "Show Students"                            │
  │         │                                                │
  │         ▼                                                │
  │   ┌──────────┐      ┌──────────┐      ┌──────────┐     │
  │   │   VIEW   │◄─────│CONTROLLER│─────►│  MODEL   │     │
  │   │          │      │          │      │          │     │
  │   │ HTML/UI  │      │ Routes,  │      │ Business │     │
  │   │ Template │      │ Logic,   │      │ Data,    │     │
  │   │ Display  │      │ Handlers │      │ DB, Rules│     │
  │   └──────────┘      └──────────┘      └──────────┘     │
  │                                                          │
  │   Flow: User → Controller → Model → Controller → View   │
  │                                                          │
  │   Used by: Django (MTV), Rails, Spring MVC, Laravel      │
  └──────────────────────────────────────────────────────────┘

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

🔲 MONOLITH vs MICROSERVICES

  MONOLITH:
  ┌─────────────────────────────────┐
  │         ONE BIG APP             │
  │  ┌─────┐ ┌─────┐ ┌──────────┐ │
  │  │Auth │ │Order│ │ Payment  │ │
  │  ├─────┤ ├─────┤ ├──────────┤ │
  │  │User │ │Cart │ │ Inventory│ │
  │  └─────┘ └─────┘ └──────────┘ │
  │                                 │
  │  ONE database, ONE deployment   │
  │  ONE codebase, ONE language     │
  └─────────────────────────────────┘


  MICROSERVICES:
  ┌──────┐   ┌──────┐   ┌────────┐   ┌──────────┐
  │ Auth │   │Order │   │Payment │   │Inventory │
  │Service│  │Service│  │Service │   │ Service  │
  │      │   │      │   │        │   │          │
  │ 🗄️DB │   │ 🗄️DB │   │ 🗄️DB  │   │  🗄️DB   │
  └──┬───┘   └──┬───┘   └───┬────┘   └────┬─────┘
     │          │            │              │
     └──────────┴────────────┴──────────────┘
                API Gateway / Message Bus
  
  Each service: own DB, own deployment, can use different language


  COMPARISON:
  ┌──────────────────┬──────────────────┬──────────────────────┐
  │                  │ Monolith         │ Microservices        │
  ├──────────────────┼──────────────────┼──────────────────────┤
  │ Team Size        │ 1-10 devs        │ 10-1000+ devs        │
  │ Deployment       │ All or nothing   │ Independent per svc  │
  │ Scaling          │ Scale everything │ Scale what's needed  │
  │ Tech Stack       │ One language     │ Polyglot allowed     │
  │ Data Consistency │ Easy (one DB)    │ Hard (distributed)   │
  │ Debugging        │ Easy (one app)   │ Hard (distributed)   │
  │ Initial Speed    │ Fast ✅          │ Slow (overhead)      │
  │ Long-term Speed  │ Slows down       │ Stays fast ✅        │
  │ Failure Impact   │ Entire app down  │ One service down     │
  ├──────────────────┼──────────────────┼──────────────────────┤
  │ Companies        │ Most startups    │ Netflix, Amazon,     │
  │                  │                  │ Uber, Flipkart       │
  ├──────────────────┼──────────────────┼──────────────────────┤
  │ 💡 Start with   │ ✅ Always start  │ Migrate when needed  │
  │                  │ monolith!        │ (not before!)        │
  └──────────────────┴──────────────────┴──────────────────────┘

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

📦 CQRS — Command Query Responsibility Segregation

  Traditional:
  ┌──────────────────┐
  │   Same Model     │  ← Reads AND Writes use same model
  │   for Read &     │     Same DB, same schema
  │   Write          │     ✅ Simple  ❌ Not optimized
  └──────────────────┘

  CQRS:
  ┌──────────────┐         ┌───────────────┐
  │  COMMAND     │         │  QUERY         │
  │  (Write)     │         │  (Read)        │
  │              │         │                │
  │  CreateOrder │         │  GetOrderList  │
  │  UpdateOrder │         │  GetOrderById  │
  │  DeleteOrder │         │  SearchOrders  │
  │              │         │                │
  │  🗄️ Write DB │ ──sync──► 🗄️ Read DB     │
  │  (normalized)│         │  (denormalized,│
  │              │         │   optimized    │
  │              │         │   for queries) │
  └──────────────┘         └───────────────┘

  ✅ Read and write models optimized separately
  ✅ Scale reads and writes independently  
  ❌ Complexity, eventual consistency

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

📜 EVENT SOURCING — Store Events, Not State

  Traditional DB:
  ┌──────────────────────────────────┐
  │  Account: Rahul                  │
  │  Balance: ₹3000                  │  ← Only CURRENT state
  │  Last Updated: 2025-01-15        │     History is LOST
  └──────────────────────────────────┘

  Event Sourcing:
  ┌──────────────────────────────────┐
  │  Event 1: AccountCreated(₹0)    │
  │  Event 2: Deposited(₹5000)      │
  │  Event 3: Withdrawn(₹1000)      │  ← FULL history
  │  Event 4: Deposited(₹2000)      │     Can rebuild state
  │  Event 5: Withdrawn(₹3000)      │     at ANY point in time
  │                                  │
  │  Current Balance = replay all    │
  │  events = ₹0+5000-1000+2000     │
  │           -3000 = ₹3000          │
  └──────────────────────────────────┘

  ✅ Complete audit trail (banks, financial systems love this)
  ✅ Can replay events to debug
  ✅ Can build different "views" from same events
  ❌ Complex, event schema evolution is hard
  
  Used by: Banks, Flipkart order tracking, Git (!)
```

```python
# 🏗️ CLEAN ARCHITECTURE — Putting It All Together

# Directory structure of a well-architected Python project:

"""
my_app/
├── domain/                    # 🏛️ CORE — Business Rules (innermost)
│   ├── entities/
│   │   ├── student.py         # Student entity with business logic
│   │   └── course.py          
│   ├── value_objects/
│   │   ├── email.py           # Email value object (immutable)
│   │   └── cgpa.py            
│   ├── repositories/          # Repository INTERFACES (not implementations!)
│   │   └── student_repo.py    # class StudentRepository(ABC)
│   └── services/
│       └── enrollment.py      # Domain service (enrollment rules)
│
├── application/               # 📋 USE CASES — Application Logic
│   ├── commands/
│   │   ├── enroll_student.py  # EnrollStudentCommand
│   │   └── update_cgpa.py     
│   ├── queries/
│   │   ├── get_student.py     # GetStudentQuery
│   │   └── list_students.py   
│   └── dtos/
│       └── student_dto.py     # Data Transfer Objects
│
├── infrastructure/            # 🔧 ADAPTERS — External World
│   ├── database/
│   │   ├── postgres_repo.py   # PostgresStudentRepository (implements interface)
│   │   └── models.py          # SQLAlchemy/ORM models
│   ├── api/
│   │   ├── routes.py          # FastAPI/Flask routes
│   │   └── schemas.py         # Pydantic request/response schemas
│   ├── email/
│   │   └── sendgrid.py        # Email sending implementation
│   └── config/
│       └── settings.py        
│
├── tests/
│   ├── unit/
│   ├── integration/
│   └── e2e/
│
└── main.py                    # Composition root — wire everything together
"""

# KEY RULE: Dependencies point INWARD
# domain/ knows NOTHING about infrastructure/
# application/ knows domain/ but NOT infrastructure/
# infrastructure/ knows everything (it's the outer layer)
# 
# This means you can swap PostgreSQL for MongoDB
# without touching a SINGLE line of business logic!
```

---

## 🏆 PHASE 4: ENTERPRISE PATTERNS (Weeks 19–24)

### Week 19–21: Enterprise Patterns

| # | Topic | Priority | Est. Hours | Status |
|---|-------|----------|-----------|--------|
| 90 | **DTOs (Data Transfer Objects)** — shape data for different layers | 🔴 Critical | 2h | ⬜ |
| 91 | **Repository Pattern** — abstract data access behind an interface | 🔴 Critical | 3h | ⬜ |
| 92 | **Use Cases / Application Services** — orchestrate business operations | 🔴 Critical | 3h | ⬜ |
| 93 | **Value Objects** — immutable objects defined by value, not identity | 🟡 Important | 2h | ⬜ |
| 94 | **Entities** — objects with identity that persists over time | 🔴 Critical | 2h | ⬜ |
| 95 | **Domain Models** — rich models with business logic | 🟡 Important | 3h | ⬜ |
| 96 | **Mappers** — convert between layers (Entity ↔ DTO ↔ DB Model) | 🟡 Important | 2h | ⬜ |
| 97 | **Commands/Queries** — separate read and write intentions | 🟡 Important | 2h | ⬜ |
| 98 | **Transaction Script** — procedural approach to business logic | 🟢 Good to know | 1h | ⬜ |
| 99 | **Identity Maps** — ensure one instance per entity in memory | 🟢 Good to know | 1h | ⬜ |
| 100 | **ORMs** — Object-Relational Mapping (SQLAlchemy, Django ORM) | 🔴 Critical | 4h | ⬜ |

```
📦 ENTERPRISE PATTERNS — Quick Reference

┌────────────────────┬────────────────────────────────────────────┐
│  Pattern           │  What & Why                                │
├────────────────────┼────────────────────────────────────────────┤
│                    │                                            │
│  ENTITY            │  Has IDENTITY. Two students with same name │
│                    │  are DIFFERENT (different roll_no).         │
│                    │  student.id = 101 → always THIS student    │
│                    │                                            │
│  VALUE OBJECT      │  Defined by VALUE, not identity.           │
│                    │  ₹500 = ₹500 regardless of which note.    │
│                    │  Email("a@b.com") == Email("a@b.com") ✅   │
│                    │  IMMUTABLE — can't change after creation   │
│                    │                                            │
│  DTO               │  "Tiffin box" — carries data between      │
│                    │  layers. No logic, just data fields.       │
│                    │  API → DTO → Service → Entity → DB        │
│                    │                                            │
│  REPOSITORY        │  "Librarian" — abstracts data storage.     │
│                    │  repo.find(id), repo.save(student)         │
│                    │  You don't know if it's SQL, Mongo, or file│
│                    │                                            │
│  USE CASE          │  "Recipe" — orchestrates one business      │
│                    │  operation. "Enroll student in course"      │
│                    │  Uses entities + repositories + services    │
│                    │                                            │
│  MAPPER            │  "Translator" — converts between formats.  │
│                    │  DB Row → Entity → DTO → API Response      │
│                    │                                            │
│  COMMAND           │  "Write operation" — changes state.        │
│                    │  CreateStudentCommand(name, branch, cgpa)   │
│                    │                                            │
│  QUERY             │  "Read operation" — returns data.          │
│                    │  GetStudentQuery(roll_no=101)               │
│                    │                                            │
└────────────────────┴────────────────────────────────────────────┘
```

```python
# 🏢 ENTERPRISE PATTERNS — Complete Working Example

from abc import ABC, abstractmethod
from dataclasses import dataclass, field
from typing import Optional, List
from datetime import datetime
from uuid import uuid4


# ═══════════════════════════════════════════════
# DOMAIN LAYER — Pure business logic, no dependencies
# ═══════════════════════════════════════════════

# ─── Value Objects (Immutable, compared by value) ─────
@dataclass(frozen=True)  # frozen=True makes it immutable
class Email:
    value: str
    
    def __post_init__(self):
        if '@' not in self.value:
            raise ValueError(f"Invalid email: {self.value}")
    
    def __str__(self):
        return self.value


@dataclass(frozen=True)
class CGPA:
    value: float
    
    def __post_init__(self):
        if not 0.0 <= self.value <= 10.0:
            raise ValueError(f"CGPA must be 0-10, got {self.value}")
    
    def is_eligible_for_scholarship(self) -> bool:
        return self.value >= 8.0


# ─── Entity (Has identity, compared by ID) ───────────
@dataclass
class Student:
    id: str
    name: str
    email: Email
    cgpa: CGPA
    branch: str
    enrolled_courses: List[str] = field(default_factory=list)
    created_at: datetime = field(default_factory=datetime.now)
    
    def enroll_in_course(self, course_id: str):
        """Business rule: max 6 courses per semester"""
        if len(self.enrolled_courses) >= 6:
            raise ValueError("Cannot enroll in more than 6 courses!")
        if course_id in self.enrolled_courses:
            raise ValueError(f"Already enrolled in {course_id}")
        self.enrolled_courses.append(course_id)
    
    def is_scholarship_eligible(self) -> bool:
        return self.cgpa.is_eligible_for_scholarship()


# ─── Repository Interface (Port) ─────────────────────
class StudentRepository(ABC):
    """Interface — the DOMAIN defines what it needs,
    infrastructure provides the implementation."""
    
    @abstractmethod
    def find_by_id(self, student_id: str) -> Optional[Student]:
        pass
    
    @abstractmethod
    def find_by_email(self, email: Email) -> Optional[Student]:
        pass
    
    @abstractmethod
    def save(self, student: Student) -> None:
        pass
    
    @abstractmethod
    def find_all(self, limit: int = 10, offset: int = 0) -> List[Student]:
        pass


# ═══════════════════════════════════════════════
# APPLICATION LAYER — Use Cases / Commands / Queries
# ═══════════════════════════════════════════════

# ─── DTOs (What goes in and comes out of use cases) ───
@dataclass(frozen=True)
class CreateStudentDTO:
    name: str
    email: str
    cgpa: float
    branch: str


@dataclass(frozen=True)
class StudentResponseDTO:
    id: str
    name: str
    email: str
    cgpa: float
    branch: str
    is_scholarship_eligible: bool
    course_count: int


# ─── Mapper (Converts between layers) ────────────────
class StudentMapper:
    @staticmethod
    def to_response_dto(student: Student) -> StudentResponseDTO:
        return StudentResponseDTO(
            id=student.id,
            name=student.name,
            email=str(student.email),
            cgpa=student.cgpa.value,
            branch=student.branch,
            is_scholarship_eligible=student.is_scholarship_eligible(),
            course_count=len(student.enrolled_courses),
        )


# ─── Use Case (Command) ──────────────────────────────
class CreateStudentUseCase:
    """One class = one use case = single responsibility"""
    
    def __init__(self, repo: StudentRepository):
        self._repo = repo  # Injected! (DIP)
    
    def execute(self, dto: CreateStudentDTO) -> StudentResponseDTO:
        # 1. Validate (create value objects)
        email = Email(dto.email)
        cgpa = CGPA(dto.cgpa)
        
        # 2. Check business rules
        existing = self._repo.find_by_email(email)
        if existing:
            raise ValueError(f"Student with email {email} already exists!")
        
        # 3. Create entity
        student = Student(
            id=str(uuid4()),
            name=dto.name,
            email=email,
            cgpa=cgpa,
            branch=dto.branch,
        )
        
        # 4. Persist
        self._repo.save(student)
        
        # 5. Return DTO (not entity!)
        return StudentMapper.to_response_dto(student)


# ═══════════════════════════════════════════════
# INFRASTRUCTURE LAYER — Concrete implementations
# ═══════════════════════════════════════════════

# ─── In-Memory Implementation (for dev/testing) ──────
class InMemoryStudentRepository(StudentRepository):
    def __init__(self):
        self._store: dict[str, Student] = {}
    
    def find_by_id(self, student_id: str) -> Optional[Student]:
        return self._store.get(student_id)
    
    def find_by_email(self, email: Email) -> Optional[Student]:
        for student in self._store.values():
            if student.email == email:
                return student
        return None
    
    def save(self, student: Student) -> None:
        self._store[student.id] = student
    
    def find_all(self, limit: int = 10, offset: int = 0) -> List[Student]:
        students = list(self._store.values())
        return students[offset:offset + limit]


# ═══════════════════════════════════════════════
# COMPOSITION ROOT — Wire everything together
# ═══════════════════════════════════════════════

# Create infrastructure
repo = InMemoryStudentRepository()

# Inject into use case
create_student = CreateStudentUseCase(repo)

# Execute!
result = create_student.execute(CreateStudentDTO(
    name="Rahul Sharma",
    email="rahul@college.edu.in",
    cgpa=8.7,
    branch="CSE"
))

print(f"✅ Created: {result.name}")
print(f"   Email: {result.email}")
print(f"   CGPA: {result.cgpa}")
print(f"   Scholarship Eligible: {result.is_scholarship_eligible}")

# 💡 To switch to PostgreSQL:
# repo = PostgresStudentRepository(db_url="...")
# create_student = CreateStudentUseCase(repo)  # Same use case!
# ZERO changes to business logic! That's the power of clean architecture.
```

---

### Week 22–24: DDD Deep Dive & Synthesis

| # | Topic | Priority | Est. Hours | Status |
|---|-------|----------|-----------|--------|
| 101 | **Bounded Contexts** — dividing complex domains | 🔴 Critical | 3h | ⬜ |
| 102 | **Aggregates** — consistency boundaries, aggregate roots | 🔴 Critical | 3h | ⬜ |
| 103 | **Domain Events** — communicate between bounded contexts | 🟡 Important | 2h | ⬜ |
| 104 | **Ubiquitous Language** — shared vocabulary with domain experts | 🟡 Important | 1h | ⬜ |
| 105 | **Context Maps** — how bounded contexts relate to each other | 🟡 Important | 2h | ⬜ |
| 106 | **Putting It All Together** — full architecture case study | 🔴 Critical | 5h | ⬜ |

```
🗺️ DOMAIN-DRIVEN DESIGN (DDD) — The Big Picture

  Problem: An e-commerce system is HUGE. One team can't understand
  all of it: orders, payments, shipping, inventory, users, reviews...

  Solution: Split into BOUNDED CONTEXTS — each is its own mini-world
  with its own language, models, and rules.

  ┌─────────────────────────────────────────────────────────────┐
  │                     E-COMMERCE SYSTEM                       │
  │                                                             │
  │  ┌──────────────┐   ┌──────────────┐   ┌──────────────┐   │
  │  │   ORDERING    │   │   PAYMENT    │   │   SHIPPING   │   │
  │  │   Context     │   │   Context    │   │   Context    │   │
  │  │              │   │              │   │              │   │
  │  │  "Order"     │   │  "Transaction│   │  "Shipment"  │   │
  │  │  "LineItem"  │   │   "Invoice"  │   │  "Package"   │   │
  │  │  "Cart"      │   │   "Refund"   │   │  "Tracking"  │   │
  │  │              │   │              │   │              │   │
  │  │  "Customer"  │   │  "Customer"  │   │  "Recipient" │   │
  │  │  = buyer info│   │  = billing   │   │  = delivery  │   │
  │  │    + address │   │    info      │   │    address   │   │
  │  └──────┬───────┘   └──────┬───────┘   └──────┬───────┘   │
  │         │                  │                   │           │
  │         └──── Events ──────┴──── Events ───────┘           │
  │           OrderPlaced →        PaymentReceived →            │
  │                                                             │
  │  🔑 KEY INSIGHT: "Customer" means different things in       │
  │     different contexts! That's OK and intentional.          │
  │     Each context has its OWN model of "Customer".           │
  └─────────────────────────────────────────────────────────────┘
```

---

## 📊 COMPLETE TIMELINE OVERVIEW

```
WEEK  1-2   ████ Clean Code Principles — naming, small fns, pure fns
WEEK  3     ████ Programming Paradigms — Structured, FP, OOP
WEEK  4-5   ████ OOP Deep Dive — 4 Pillars, Abstractions, Models
             ──── 🎯 MILESTONE: Write clean, well-structured OOP code ────

WEEK  6-7   ████ SOLID Principles — S, O, L, I, D + DRY, YAGNI
            ████ Composition over Inheritance, Law of Demeter
WEEK  8-9   ████ Creational Patterns — Factory, Builder, Singleton
            ████ Structural Patterns — Adapter, Decorator, Facade, Proxy
WEEK 10     ████ Behavioral Patterns — Strategy, Observer, Command, State
WEEK 11-12  ████ Anti-Patterns, Refactoring, Pattern Combinations
             ──── 🎯 MILESTONE: Apply design patterns to real projects ────

WEEK 13-14  ████ Architectural Principles — Coupling, Cohesion, Boundaries
WEEK 15-16  ████ Architectural Styles — Monolith, Layered, Event-Driven
WEEK 17-18  ████ Architectural Patterns — MVC, Microservices, CQRS
             ──── 🎯 MILESTONE: Design system-level architecture ────

WEEK 19-21  ████ Enterprise Patterns — Repository, DTO, Entities, Use Cases
WEEK 22-24  ████ DDD — Bounded Contexts, Aggregates, Domain Events
             ──── 🏆 MILESTONE: Architect production-grade systems ────
```

---

## 🏋️ PROJECTS TO BUILD (Phase-wise)

| Phase | Project | Patterns Applied | Resume Value |
|-------|---------|-----------------|-------------|
| 🟢 Week 5 | **Refactor a messy codebase** — take spaghetti code, apply clean code | Clean Code, OOP | ⭐⭐ |
| 🟡 Week 12 | **Design Pattern Library** — implement all 23 GoF patterns with examples | All GoF Patterns | ⭐⭐⭐ |
| 🔴 Week 18 | **E-Commerce Backend** — layered architecture, MVC, proper separation | SOLID, Architecture | ⭐⭐⭐⭐ |
| 🏆 Week 24 | **Microservices Project** — DDD, CQRS, Event Sourcing, Clean Arch | Enterprise Patterns | ⭐⭐⭐⭐⭐ |

---

## 📚 BEST RESOURCES (Curated)

| Category | Resource | Type | Best For |
|----------|----------|------|----------|
| 📖 Book | **Clean Code** (Robert C. Martin) | Book | Clean code fundamentals (MUST READ) |
| 📖 Book | **Head First Design Patterns** | Book | GoF patterns (beginner-friendly) |
| 📖 Book | **Design Patterns** (GoF — Gang of Four) | Book | Original reference (advanced) |
| 📖 Book | **Clean Architecture** (Robert C. Martin) | Book | Architecture principles |
| 📖 Book | **Domain-Driven Design** (Eric Evans) | Book | DDD bible (advanced) |
| 🎥 YouTube | **Christopher Okhravi** — Design Patterns | Video | Best visual pattern explanations |
| 🎥 YouTube | **ArjanCodes** — Python Design Patterns | Video | Practical Python patterns |
| 🎥 YouTube | **Fireship** — Design Patterns in 100 Seconds | Video | Quick overviews |
| 🎥 YouTube | **CodeAesthetic** — Clean Code Principles | Video | Beautiful clean code explanations |
| 🌐 Website | **refactoring.guru** | Interactive | Best pattern reference + diagrams |
| 🌐 Website | **roadmap.sh/software-design-architecture** | Roadmap | Visual learning path |
| 🌐 Website | **sourcemaking.com** | Reference | Patterns + Anti-patterns + Refactoring |

---

## 💼 Interview Angle — What Companies Ask

```
┌────────────────────────────────────────────────────────────────────┐
│          SOFTWARE DESIGN & ARCHITECTURE INTERVIEW QUESTIONS       │
├────────────────────────────────────────────────────────────────────┤
│                                                                    │
│  MOST ASKED (Every Company):                                      │
│  1. Explain SOLID principles with examples.                       │
│  2. What design patterns have you used? When and why?             │
│  3. What's the difference between Abstract Class and Interface?   │
│  4. Explain Strategy pattern. Give a real-world example.          │
│  5. What is Dependency Injection? Why does it matter?             │
│                                                                    │
│  INTERMEDIATE (Product Companies):                                 │
│  6. Design a parking lot system (LLD — Low Level Design)          │
│  7. Design a library management system (LLD)                      │
│  8. Explain composition over inheritance with example.            │
│  9. What is the Observer pattern? Where is it used?               │
│  10. How would you refactor a God class?                          │
│                                                                    │
│  ADVANCED (Senior / SDE-2):                                       │
│  11. Monolith vs Microservices — how do you decide?               │
│  12. Explain CQRS and Event Sourcing.                             │
│  13. What is DDD? What are Bounded Contexts?                      │
│  14. How do you ensure loose coupling in a large system?          │
│  15. Design the architecture for a food delivery app.             │
│                                                                    │
│  Companies that HEAVILY test this:                                 │
│  Amazon, Google, Microsoft, Flipkart, Atlassian, Uber,            │
│  Goldman Sachs, PayPal, Adobe, Intuit                              │
└────────────────────────────────────────────────────────────────────┘
```

---
