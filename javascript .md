

# 🗺️ ROADMAP: JavaScript — Complete Mastery Guide

> From `console.log("Hello")` to Async/Await, Closures & Beyond

---

## 📊 Roadmap Overview

```
Total Estimated Time:  10–14 Weeks (2 hrs/day)
Difficulty Curve:      ████████░░ (Easy start, tricky middle, powerful end)
Relevance:             Placements ⭐⭐⭐⭐⭐ | Web Dev ⭐⭐⭐⭐⭐ | GATE ❌ | Freelancing ⭐⭐⭐⭐⭐
```

```
🔴 = Critical (MUST know — asked in every interview, used daily)
🟡 = Important (frequently tested, expected at mid-level)
🟢 = Good to Know (gives you a competitive edge)
```

---

## ⚠️ PREREQUISITES

```
┌───────────────────────────────────────────────────────────┐
│  You need almost NOTHING to start JavaScript.             │
│                                                           │
│  ✅ Basic HTML (tags, attributes, forms) — 2 hours max   │
│  ✅ Basic CSS (selectors, properties) — 2 hours max      │
│  ✅ A browser (Chrome recommended)                        │
│  ✅ A text editor (VS Code)                               │
│                                                           │
│  That's it. JavaScript is the FIRST real programming      │
│  language for most web developers.                        │
└───────────────────────────────────────────────────────────┘
```

---

## 🧱 PHASE 1: INTRODUCTION & SETUP (Week 1, Day 1–2)
### *"Know what you're learning and why"*

```
⏱️ Estimated: 3–4 hours
```

### 1.1 What is JavaScript? 🔴

```
┌─────────────────────────────────────────────────────────────────┐
│                      WHAT IS JAVASCRIPT?                        │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│  → High-level, interpreted, dynamically-typed language          │
│  → THE language of the web (runs in every browser)              │
│  → Originally: make web pages interactive (1995, Brendan Eich)  │
│  → Now: frontend, backend, mobile, desktop, ML, IoT — EVERYTHING│
│                                                                 │
│  WHERE JS RUNS:                                                 │
│  ├── Browser (Chrome, Firefox, Edge) → Frontend                 │
│  ├── Node.js / Deno / Bun → Backend (server-side)              │
│  ├── React Native / Electron → Mobile & Desktop apps            │
│  └── TensorFlow.js → Machine Learning                          │
│                                                                 │
│  Created by: Brendan Eich (10 days! at Netscape, 1995)         │
│  Standardized as: ECMAScript (ES6/ES2015 was the game-changer) │
│  Used by: Every website on the planet. Literally.              │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
```

### 🧒 ELI5 — What is JavaScript?

> If a website were a **human body**:
> **HTML** = the skeleton (structure, bones)
> **CSS** = the clothes, skin, appearance (styling)
> **JavaScript** = the **brain & muscles** (behavior, interaction)
>
> Without JS, websites are like posters — you can look, but you can't *do* anything.
> With JS, you can click buttons, submit forms, see animations, chat in real-time, play games.

### JavaScript Versions — What Matters

```
┌─────────────┬──────┬─────────────────────────────────────────────┐
│ Version     │ Year │ Key Features                                │
├─────────────┼──────┼─────────────────────────────────────────────┤
│ ES5         │ 2009 │ strict mode, JSON, forEach, map, filter     │
│ ES6/ES2015  │ 2015 │ 🔴 let/const, arrow functions, classes,    │
│             │      │ template literals, destructuring, promises, │
│             │      │ modules, spread/rest — THE BIG UPDATE       │
│ ES2016      │ 2016 │ includes(), ** (exponentiation)             │
│ ES2017      │ 2017 │ 🔴 async/await, Object.entries/values      │
│ ES2018      │ 2018 │ rest/spread for objects, for-await-of       │
│ ES2020      │ 2020 │ 🟡 optional chaining (?.), nullish (??)    │
│ ES2021      │ 2021 │ replaceAll, Promise.any, logical assignment │
│ ES2022      │ 2022 │ top-level await, .at(), Object.hasOwn       │
│ ES2023      │ 2023 │ findLast, toSorted, toReversed (immutable)  │
│ ES2024      │ 2024 │ groupBy, Promise.withResolvers              │
├─────────────┴──────┴─────────────────────────────────────────────┤
│ 🎯 Focus on ES6+ features — that's modern JavaScript.           │
│    Interviewers test ES6+ specifically.                          │
└──────────────────────────────────────────────────────────────────┘
```

### 1.2 How to Run JavaScript 🔴

```
4 Ways to Run JS:

1. Browser Console (quickest — for testing)
   → Right-click → Inspect → Console tab
   → Type: console.log("Hello!") → Enter

2. HTML File + <script> tag
   → Create index.html, add <script> at bottom

3. Separate .js File (recommended)
   → Create script.js
   → Link in HTML: <script src="script.js"></script>

4. Node.js (for backend/terminal)
   → Install Node.js from nodejs.org
   → Run: node script.js
```

```html
<!-- index.html -->
<!DOCTYPE html>
<html>
<head>
  <title>Learning JS</title>
</head>
<body>
  <h1>Open the console!</h1>
  
  <!-- ✅ Always put script at the BOTTOM (before </body>) -->
  <script src="script.js"></script>
</body>
</html>
```

```javascript
// script.js
console.log("Hello, JavaScript! 🚀");
console.warn("This is a warning");
console.error("This is an error");
console.table([{name: "Rahul", age: 21}, {name: "Priya", age: 20}]);
```

---

## 🧱 PHASE 2: VARIABLES & DATA TYPES (Week 1)
### *"The absolute foundation — everything is built on this"*

```
⏱️ Estimated: 8–10 hours
Priority: 🔴 Every single concept here is critical
```

---

### 2.1 Variable Declarations: var, let, const 🔴🔴🔴

```javascript
// ===== var (old way — avoid in modern code) =====
var name = "Rahul";
var name = "Priya";   // ✅ Can re-declare (BAD — leads to bugs!)
name = "Amit";        // ✅ Can re-assign
// var is function-scoped (not block-scoped) — causes weird bugs

// ===== let (modern — for values that CHANGE) =====
let age = 21;
// let age = 22;      // ❌ Cannot re-declare in same scope
age = 22;             // ✅ Can re-assign

// ===== const (modern — for values that DON'T change) =====
const PI = 3.14159;
// PI = 3.14;         // ❌ Cannot re-assign
// const PI = 3;      // ❌ Cannot re-declare

// ⚠️ BUT: const objects/arrays CAN be modified (reference is constant, not value)
const student = { name: "Rahul", age: 21 };
student.age = 22;     // ✅ This works! (modifying property, not re-assigning)
// student = {};      // ❌ This fails (re-assigning the variable)

const skills = ["HTML", "CSS"];
skills.push("JavaScript");  // ✅ Works! Array is mutated, not re-assigned
// skills = [];              // ❌ Fails
```

### 🔴 var vs let vs const — Master Comparison (TOP Interview Question)

```
┌──────────────────┬──────────────┬──────────────┬──────────────┐
│ Feature          │ var          │ let          │ const        │
├──────────────────┼──────────────┼──────────────┼──────────────┤
│ Scope            │ Function     │ Block { }    │ Block { }    │
│ Re-declare       │ ✅ Yes       │ ❌ No        │ ❌ No        │
│ Re-assign        │ ✅ Yes       │ ✅ Yes       │ ❌ No        │
│ Hoisting         │ ✅ Hoisted   │ ✅ Hoisted   │ ✅ Hoisted   │
│                  │ (undefined)  │ (TDZ error)  │ (TDZ error)  │
│ Attach to window │ ✅ Yes       │ ❌ No        │ ❌ No        │
│ Use in 2025?     │ ❌ Never     │ ✅ When value│ ✅ Default   │
│                  │              │   changes    │   choice     │
└──────────────────┴──────────────┴──────────────┴──────────────┘

🎯 RULE: Use const by default. Use let only when you NEED to re-assign.
         Never use var.
```

---

### 2.2 Hoisting 🔴 (Interview Favourite!)

```
🧒 ELI5: 
JavaScript reads your code in TWO passes:
  Pass 1: "Let me note down all variable and function NAMES" (creation phase)
  Pass 2: "Now let me actually run the code" (execution phase)

Hoisting = JS moves declarations to the top (conceptually).
But only the DECLARATION, not the ASSIGNMENT.
```

```javascript
// ===== var hoisting =====
console.log(x);  // undefined (not error! var is hoisted with value = undefined)
var x = 10;
console.log(x);  // 10

// What JS actually sees:
// var x;              ← declaration hoisted
// console.log(x);     ← undefined
// x = 10;             ← assignment stays
// console.log(x);     ← 10

// ===== let/const hoisting (Temporal Dead Zone) =====
// console.log(y);  // ❌ ReferenceError: Cannot access 'y' before initialization
let y = 20;
// let and const ARE hoisted, but in a "Temporal Dead Zone" (TDZ)
// You can't use them before their declaration line

// ===== Function hoisting =====
greet();  // ✅ "Hello!" — function declarations are FULLY hoisted!

function greet() {
  console.log("Hello!");
}

// But function EXPRESSIONS are NOT hoisted:
// sayBye();  // ❌ TypeError: sayBye is not a function
var sayBye = function() {
  console.log("Bye!");
};
```

### 🧠 Hoisting Interview Trick Question

```javascript
var a = 1;
function foo() {
  console.log(a);  // What prints? 🤔
  var a = 2;
  console.log(a);
}
foo();

// Answer: undefined, then 2
// Why? Inside foo(), `var a` is hoisted to TOP of function.
// So it's like:
// function foo() {
//   var a;           ← hoisted (local a shadows global a)
//   console.log(a);  ← undefined (local a exists but no value yet)
//   a = 2;
//   console.log(a);  ← 2
// }
```

---

### 2.3 Variable Scopes 🔴

```javascript
// ===== Global Scope =====
const globalVar = "I'm everywhere";  // Accessible anywhere

// ===== Function Scope =====
function myFunc() {
  const funcVar = "I'm only inside this function";
  console.log(globalVar);   // ✅ Can access global
  console.log(funcVar);     // ✅ Can access own variable
}
// console.log(funcVar);    // ❌ ReferenceError (not accessible outside)

// ===== Block Scope (let/const) =====
if (true) {
  let blockLet = "block scoped";
  const blockConst = "also block scoped";
  var blockVar = "NOT block scoped (function scoped!)";
}
// console.log(blockLet);   // ❌ Error
// console.log(blockConst); // ❌ Error
console.log(blockVar);      // ✅ "NOT block scoped" — var leaks out!

// ===== Scope Chain (Lexical Scoping) =====
function outer() {
  const outerVar = "outer";
  
  function inner() {
    const innerVar = "inner";
    console.log(outerVar);  // ✅ Can access parent's scope
    console.log(innerVar);  // ✅ Own scope
  }
  
  inner();
  // console.log(innerVar); // ❌ Can't access child's scope
}
```

```
SCOPE VISUALIZATION:

┌─── Global Scope ──────────────────────────────┐
│  const globalVar = "..."                       │
│                                                │
│  ┌─── Function Scope (myFunc) ──────────────┐ │
│  │  const funcVar = "..."                    │ │
│  │                                           │ │
│  │  ┌─── Block Scope (if) ───────────────┐  │ │
│  │  │  let blockLet = "..."              │  │ │
│  │  │  const blockConst = "..."          │  │ │
│  │  │  // Can see: blockLet, funcVar,    │  │ │
│  │  │  //          globalVar             │  │ │
│  │  └────────────────────────────────────┘  │ │
│  │                                           │ │
│  │  // Can see: funcVar, globalVar           │ │
│  │  // Can't see: blockLet, blockConst       │ │
│  └───────────────────────────────────────────┘ │
│                                                │
│  // Can see: globalVar                         │
│  // Can't see: funcVar, blockLet               │
└────────────────────────────────────────────────┘

Rule: Inner scopes can see OUTER. Outer CANNOT see inner.
      Like one-way mirrors — you can look OUT but not IN.
```

---

### 2.4 Data Types 🔴

```javascript
// ===== 7 Primitive Types (immutable, stored by VALUE) =====

// 1. String
const name = "Rahul";
const greeting = 'Hello';
const template = `Hi, ${name}!`;  // Template literal (ES6) 🔴

// 2. Number (integers AND decimals — no separate int/float)
const age = 21;
const pi = 3.14159;
const infinity = Infinity;
const notANum = NaN;         // "Not a Number" — typeof NaN === "number" 🤯

// 3. BigInt (for very large integers)
const huge = 9007199254740991n;  // note the 'n' suffix
const also = BigInt("9007199254740991");

// 4. Boolean
const isPlaced = true;
const hasCTC = false;

// 5. undefined (declared but no value assigned)
let x;
console.log(x);  // undefined

// 6. null (intentionally empty — "nothing here")
const result = null;

// 7. Symbol (unique identifier — rarely used by beginners)
const id = Symbol("id");
const id2 = Symbol("id");
console.log(id === id2);  // false (every Symbol is unique)

// ===== Non-Primitive (Reference Types — stored by REFERENCE) =====

// Object
const student = { name: "Rahul", age: 21, branch: "CSE" };

// Array (technically an object)
const skills = ["HTML", "CSS", "JavaScript"];

// Function (also an object — first-class citizen!)
const greet = function(name) { return `Hi, ${name}!`; };

// Date, RegExp, Map, Set — all objects
```

### 🔴 typeof Operator (Interview Question!)

```javascript
console.log(typeof "hello");       // "string"
console.log(typeof 42);           // "number"
console.log(typeof true);         // "boolean"
console.log(typeof undefined);    // "undefined"
console.log(typeof null);         // "object"    ← 🐛 FAMOUS BUG! (since 1995)
console.log(typeof {});           // "object"
console.log(typeof []);           // "object"    ← Arrays are objects!
console.log(typeof function(){}); // "function"
console.log(typeof NaN);          // "number"    ← NaN is a number! 🤯
console.log(typeof Symbol());     // "symbol"
console.log(typeof 10n);          // "bigint"

// How to check for array:
Array.isArray([1, 2, 3]);  // true ✅
Array.isArray({});          // false

// How to check for null:
const val = null;
val === null;  // true ✅
```

### Primitive vs Reference — THE Crucial Difference 🔴

```javascript
// ===== Primitives: Copied by VALUE =====
let a = 10;
let b = a;    // b gets a COPY of 10
b = 20;
console.log(a);  // 10 (unchanged — they're independent copies)
console.log(b);  // 20

// ===== Objects: Copied by REFERENCE =====
let obj1 = { name: "Rahul" };
let obj2 = obj1;              // obj2 points to SAME object in memory!
obj2.name = "Priya";
console.log(obj1.name);       // "Priya" 😱 (BOTH changed!)

// To make an independent copy:
let obj3 = { ...obj1 };               // Shallow copy (spread)
let obj4 = JSON.parse(JSON.stringify(obj1));  // Deep copy (hacky)
let obj5 = structuredClone(obj1);      // Deep copy (modern ✅)
```

```
MEMORY VISUALIZATION:

Primitives (value):          Reference types:
┌────────┐                   ┌────────┐
│ a: 10  │                   │ obj1 ──┼──┐
├────────┤                   ├────────┤  │   ┌──────────────┐
│ b: 20  │ (independent)     │ obj2 ──┼──┼──►│ {name:"Priya"}│
└────────┘                   └────────┘  │   └──────────────┘
                                         │
                             Both point to SAME object!
```

---

### 2.5 Type Casting / Coercion 🔴

```javascript
// ===== Explicit Type Casting (YOU do it intentionally) =====

// To String
String(123);           // "123"
(123).toString();      // "123"
`${123}`;              // "123" (template literal)

// To Number
Number("42");          // 42
Number("hello");       // NaN
Number(true);          // 1
Number(false);         // 0
Number(null);          // 0
Number(undefined);     // NaN
parseInt("42px");      // 42 (stops at first non-numeric char)
parseFloat("3.14abc"); // 3.14
+"42";                 // 42 (unary + operator — shorthand)

// To Boolean
Boolean(0);            // false
Boolean("");           // false
Boolean(null);         // false
Boolean(undefined);    // false
Boolean(NaN);          // false
// ↑ These are the 6 "FALSY" values. Everything else is TRUTHY.
Boolean("0");          // true (non-empty string!)
Boolean([]);           // true (empty array is truthy!)
Boolean({});           // true (empty object is truthy!)
!!value;               // Shorthand: double NOT converts to boolean
```

```javascript
// ===== Implicit Type Coercion (JS does it automatically — TRICKY!) =====

// String + anything = String (concatenation wins)
"5" + 3;          // "53" (number → string)
"5" + true;       // "5true"
"5" + null;       // "5null"
"5" + undefined;  // "5undefined"

// Other operators convert to Number
"5" - 3;          // 2
"5" * 3;          // 15
"5" / 2;          // 2.5
"5" - true;       // 4 (true → 1)

// Comparison coercion
"5" == 5;          // true  (== does type coercion)
"5" === 5;         // false (=== NO coercion — strict)
null == undefined; // true  (special rule)
null === undefined;// false
NaN == NaN;        // false (NaN is not equal to anything, including itself!)
```

### 🤯 JS Coercion Memes (But Also Interview Questions)

```javascript
[] + [];           // "" (empty string)
[] + {};           // "[object Object]"
{} + [];           // 0 (block + array)
true + true;       // 2
true + false;      // 1
"b" + "a" + +"a" + "a";  // "baNaNa" 🍌
```

> 🎯 **Interview Rule**: Always use `===` (strict equality). Know why `==` is dangerous.

---

## 🧱 PHASE 3: OPERATORS & CONTROL FLOW (Week 2)
### *"Making decisions and doing math"*

```
⏱️ Estimated: 6–8 hours
Priority: 🔴 Most of this
```

### 3.1 Operators 🔴

```javascript
// ===== Arithmetic =====
10 + 3;    // 13
10 - 3;    // 7
10 * 3;    // 30
10 / 3;    // 3.333...
10 % 3;    // 1 (modulus/remainder)
10 ** 3;   // 1000 (exponentiation — ES2016)

// Increment/Decrement
let x = 5;
x++;       // Post-increment: returns 5, THEN x becomes 6
++x;       // Pre-increment: x becomes 7, THEN returns 7
// Same for x-- and --x

// ===== Comparison =====
5 == "5";   // true  (loose — coerces type)
5 === "5";  // false (strict — no coercion) 🔴 USE THIS
5 != "5";   // false
5 !== "5";  // true  🔴 USE THIS
5 > 3;      // true
5 >= 5;     // true

// ===== Logical =====
true && false;   // false (AND — both must be true)
true || false;   // true  (OR — at least one true)
!true;           // false (NOT — flips boolean)

// Short-circuit evaluation (VERY useful in React!)
const name = user && user.name;           // If user exists, get name
const displayName = name || "Anonymous";  // If name is falsy, use default

// Nullish Coalescing ?? (ES2020) — only checks null/undefined
const value = null ?? "default";    // "default"
const value2 = 0 ?? "default";     // 0 (0 is NOT null/undefined)
const value3 = 0 || "default";     // "default" (|| treats 0 as falsy)
// ↑ This is why ?? exists — || is too aggressive with falsy values

// ===== Optional Chaining ?. (ES2020) =====
const user = { address: { city: "Pune" } };
user.address.city;          // "Pune"
user.phone?.number;         // undefined (no error, even though phone doesn't exist)
// Without ?.:
// user.phone.number;       // ❌ TypeError: Cannot read property of undefined

// Works with methods too:
user.getProfile?.();        // undefined if getProfile doesn't exist

// ===== Assignment Shortcuts =====
let a = 10;
a += 5;    // a = a + 5  → 15
a -= 3;    // a = a - 3  → 12
a *= 2;    // a = a * 2  → 24
a /= 4;    // a = a / 4  → 6
a **= 2;   // a = a ** 2 → 36
a %= 5;    // a = a % 5  → 1

// Logical Assignment (ES2021)
a ||= 10;  // a = a || 10 (assign if falsy)
a &&= 20;  // a = a && 20 (assign if truthy)
a ??= 30;  // a = a ?? 30 (assign if null/undefined)

// ===== Ternary Operator =====
const result = age >= 18 ? "Adult" : "Minor";
// Same as: if (age >= 18) { result = "Adult" } else { result = "Minor" }

// ===== Spread Operator ... (ES6) 🔴 =====
const arr1 = [1, 2, 3];
const arr2 = [...arr1, 4, 5];    // [1, 2, 3, 4, 5]

const obj1 = { a: 1, b: 2 };
const obj2 = { ...obj1, c: 3 };  // { a: 1, b: 2, c: 3 }

// ===== Rest Operator ... (same syntax, different context) =====
function sum(...numbers) {        // Collects remaining args into array
  return numbers.reduce((a, b) => a + b, 0);
}
sum(1, 2, 3, 4, 5);  // 15

const [first, ...rest] = [1, 2, 3, 4];
// first = 1, rest = [2, 3, 4]
```

---

### 3.2 Equality: == vs === vs Object.is 🔴

```
┌─────────────────────┬────────────┬────────────┬────────────────┐
│ Comparison          │ ==         │ ===        │ Object.is()    │
├─────────────────────┼────────────┼────────────┼────────────────┤
│ Type coercion       │ ✅ Yes     │ ❌ No      │ ❌ No          │
│ "5" vs 5            │ true       │ false      │ false          │
│ null vs undefined   │ true       │ false      │ false          │
│ NaN vs NaN          │ false      │ false      │ true ✅        │
│ +0 vs -0            │ true       │ true       │ false          │
│ Use in 2025?        │ ❌ Avoid   │ ✅ Default │ 🟢 Edge cases  │
└─────────────────────┴────────────┴────────────┴────────────────┘

🎯 Simple Rule: ALWAYS use === and !==
```

---

### 3.3 Conditional Statements 🔴

```javascript
// if / else if / else
const cgpa = 8.5;

if (cgpa >= 9) {
  console.log("Outstanding — placed at Google!");
} else if (cgpa >= 8) {
  console.log("Excellent — product companies will shortlist you");
} else if (cgpa >= 7) {
  console.log("Good — service companies + some product companies");
} else {
  console.log("Focus on improving skills + CGPA");
}

// Switch (good for multiple fixed values)
const branch = "CSE";
switch (branch) {
  case "CSE":
  case "IT":
    console.log("Core tech roles available");
    break;                            // ⚠️ Don't forget break!
  case "ECE":
    console.log("Embedded + Software roles");
    break;
  case "ME":
    console.log("Core + IT (with extra effort)");
    break;
  default:
    console.log("Explore your options");
}
```

---

### 3.4 Loops & Iterations 🔴

```javascript
// ===== for loop (most common) =====
for (let i = 0; i < 5; i++) {
  console.log(i);  // 0, 1, 2, 3, 4
}

// ===== while loop =====
let count = 0;
while (count < 5) {
  console.log(count);
  count++;
}

// ===== do...while (runs at least ONCE) =====
let input;
do {
  input = prompt("Enter password:");
} while (input !== "secret123");

// ===== for...of (iterate VALUES — arrays, strings) 🔴 =====
const fruits = ["apple", "mango", "banana"];
for (const fruit of fruits) {
  console.log(fruit);  // "apple", "mango", "banana"
}

// Works on strings too!
for (const char of "Hello") {
  console.log(char);  // H, e, l, l, o
}

// ===== for...in (iterate KEYS — objects) 🔴 =====
const student = { name: "Rahul", age: 21, branch: "CSE" };
for (const key in student) {
  console.log(`${key}: ${student[key]}`);
  // "name: Rahul", "age: 21", "branch: CSE"
}

// ⚠️ Don't use for...in on arrays (use for...of or .forEach instead)

// ===== break & continue =====
for (let i = 0; i < 10; i++) {
  if (i === 3) continue;  // Skip 3
  if (i === 7) break;     // Stop at 7
  console.log(i);         // 0, 1, 2, 4, 5, 6
}
```

### for...of vs for...in (Interview Question!)

```
┌──────────────────┬──────────────────────┬──────────────────────┐
│ Feature          │ for...of             │ for...in             │
├──────────────────┼──────────────────────┼──────────────────────┤
│ Iterates over    │ VALUES               │ KEYS (property names)│
│ Best for         │ Arrays, Strings, Maps│ Objects              │
│ On arrays        │ ✅ Use this          │ ❌ Avoid             │
│ On objects       │ ❌ Error (not iterable)│ ✅ Use this        │
│ Includes prototype│ ❌ No              │ ✅ Yes (⚠️ careful)  │
└──────────────────┴──────────────────────┴──────────────────────┘
```

---

### 3.5 Error Handling 🔴

```javascript
// try / catch / finally
try {
  const data = JSON.parse("invalid json");  // This will throw
} catch (error) {
  console.error("Error:", error.message);   // Handle error gracefully
  // error.name    → "SyntaxError"
  // error.message → "Unexpected token i in JSON..."
  // error.stack   → Full stack trace
} finally {
  console.log("This ALWAYS runs, error or not");
  // Good for cleanup (closing connections, etc.)
}

// Throwing custom errors
function divide(a, b) {
  if (b === 0) {
    throw new Error("Division by zero is not allowed!");
  }
  return a / b;
}

try {
  divide(10, 0);
} catch (e) {
  console.error(e.message);  // "Division by zero is not allowed!"
}

// Error types:
// ReferenceError  → Variable not found
// TypeError       → Wrong type operation (null.property)
// SyntaxError     → Invalid code structure
// RangeError      → Number out of range
// URIError        → Bad URI
```

---

## 🧱 PHASE 4: FUNCTIONS — The Heart of JavaScript (Week 2–3)
### *"JavaScript is a functional language. Master functions = Master JS."*

```
⏱️ Estimated: 12–15 hours
Priority: 🔴🔴🔴 — Functions are THE most important concept
```

---

### 4.1 Function Basics 🔴

```javascript
// ===== Function Declaration =====
function greet(name) {
  return `Hello, ${name}!`;
}
greet("Rahul");  // "Hello, Rahul!"

// ===== Function Expression =====
const greet = function(name) {
  return `Hello, ${name}!`;
};

// ===== Arrow Function (ES6) 🔴🔴 =====
const greet = (name) => {
  return `Hello, ${name}!`;
};

// Shortened forms:
const greet = (name) => `Hello, ${name}!`;  // Single expression: implicit return
const double = n => n * 2;                   // Single param: no parens needed
const getRandom = () => Math.random();       // No params: empty parens
const getUser = () => ({ name: "Rahul" });   // Return object: wrap in ()

// ===== Default Parameters =====
function createStudent(name, branch = "CSE", year = 1) {
  return { name, branch, year };
}
createStudent("Rahul");                 // { name: "Rahul", branch: "CSE", year: 1 }
createStudent("Priya", "ECE", 3);       // { name: "Priya", branch: "ECE", year: 3 }

// ===== Rest Parameters (... gathers remaining args) =====
function sum(first, ...rest) {
  console.log(first);  // 1
  console.log(rest);   // [2, 3, 4, 5]
  return rest.reduce((acc, num) => acc + num, first);
}
sum(1, 2, 3, 4, 5);  // 15
```

### Function Declaration vs Expression vs Arrow 🔴

```
┌──────────────────────┬────────────┬────────────────┬──────────────┐
│ Feature              │ Declaration│ Expression     │ Arrow        │
├──────────────────────┼────────────┼────────────────┼──────────────┤
│ Hoisted?             │ ✅ Fully   │ ❌ No          │ ❌ No        │
│ Has own `this`       │ ✅ Yes     │ ✅ Yes         │ ❌ No (lexical)│
│ Can be constructor   │ ✅ Yes     │ ✅ Yes         │ ❌ No        │
│ `arguments` object   │ ✅ Yes     │ ✅ Yes         │ ❌ No        │
│ Syntax               │ Verbose    │ Verbose        │ Concise      │
│ Use in 2025          │ Named funcs│ Callbacks      │ 🔴 Default   │
└──────────────────────┴────────────┴────────────────┴──────────────┘

🎯 Use arrow functions for most things.
   Use function declarations for top-level named functions.
```

---

### 4.2 IIFE (Immediately Invoked Function Expression) 🟡

```javascript
// IIFE: Define + execute in one shot
// Used to create private scope (avoid polluting global)

(function() {
  const secret = "You can't access me outside!";
  console.log("IIFE ran!");
})();

// console.log(secret);  // ❌ ReferenceError

// Arrow IIFE
(() => {
  console.log("Arrow IIFE!");
})();

// With parameters
((name) => {
  console.log(`Hello, ${name}!`);
})("Rahul");
```

---

### 4.3 Higher-Order Functions 🔴🔴

```
🧒 ELI5: 
In JavaScript, functions are "first-class citizens" — 
they can be:
  → Stored in variables ✅
  → Passed as arguments ✅
  → Returned from other functions ✅

A Higher-Order Function = a function that:
  → Takes another function as argument, OR
  → Returns a function

This is the FOUNDATION of functional programming in JS.
```

```javascript
// ===== Function as argument (callbacks) =====
function doOperation(a, b, operation) {
  return operation(a, b);
}

const add = (x, y) => x + y;
const multiply = (x, y) => x * y;

doOperation(5, 3, add);      // 8
doOperation(5, 3, multiply); // 15

// ===== Function returning a function =====
function createMultiplier(factor) {
  return (number) => number * factor;  // Returns a function!
}

const double = createMultiplier(2);
const triple = createMultiplier(3);

double(5);   // 10
triple(5);   // 15
// double and triple are CLOSURES (they "remember" factor)
```

---

### 4.4 Closures 🔴🔴🔴 (TOP Interview Topic!)

```
🧒 ELI5:
A closure is when a function "remembers" the variables 
from the place where it was CREATED, even after that 
place has finished executing.

Like a student who leaves college but still remembers 
their professors, friends, and classroom lessons. The 
college (outer function) is gone, but the memories 
(variables) live on inside the student (inner function).
```

```javascript
// Basic Closure
function outer() {
  let count = 0;  // This variable "lives on" in the closure
  
  function inner() {
    count++;
    console.log(count);
  }
  
  return inner;
}

const counter = outer();  // outer() finishes, but count survives!
counter();  // 1
counter();  // 2
counter();  // 3
// count is PRIVATE — you can't access it directly, only through counter()

// ===== Practical Use: Data Privacy =====
function createBankAccount(initialBalance) {
  let balance = initialBalance;  // Private variable
  
  return {
    deposit(amount) {
      balance += amount;
      return `Deposited ₹${amount}. Balance: ₹${balance}`;
    },
    withdraw(amount) {
      if (amount > balance) return "Insufficient funds!";
      balance -= amount;
      return `Withdrew ₹${amount}. Balance: ₹${balance}`;
    },
    getBalance() {
      return `Balance: ₹${balance}`;
    }
  };
}

const account = createBankAccount(1000);
account.deposit(500);     // "Deposited ₹500. Balance: ₹1500"
account.withdraw(200);    // "Withdrew ₹200. Balance: ₹1300"
account.getBalance();     // "Balance: ₹1300"
// account.balance;       // undefined — can't access directly! 🔒
```

### ❌ Famous Closure Bug (Interview Classic!)

```javascript
// ❌ THE BUG: var + setTimeout in loop
for (var i = 0; i < 3; i++) {
  setTimeout(() => {
    console.log(i);
  }, 1000);
}
// Expected: 0, 1, 2
// Actual:   3, 3, 3  😱
// Why? var is function-scoped. By the time setTimeout runs,
//      the loop is done and i = 3 for all callbacks.

// ✅ FIX 1: Use let (block-scoped — creates new i each iteration)
for (let i = 0; i < 3; i++) {
  setTimeout(() => {
    console.log(i);
  }, 1000);
}
// Output: 0, 1, 2 ✅

// ✅ FIX 2: IIFE (closure captures current value)
for (var i = 0; i < 3; i++) {
  ((j) => {
    setTimeout(() => {
      console.log(j);
    }, 1000);
  })(i);
}
// Output: 0, 1, 2 ✅
```

---

### 4.5 The `this` Keyword 🔴🔴 (Confusing but Critical)

```
🧒 ELI5:
`this` refers to "who called me?"
It changes depending on HOW and WHERE a function is called.
Think of it like a pronoun — "I" means different things
depending on WHO is speaking.
```

```javascript
// ===== 1. In Global Scope =====
console.log(this);  // window (browser) | global (Node.js)

// ===== 2. In an Object Method =====
const student = {
  name: "Rahul",
  greet() {
    console.log(this.name);  // "Rahul" — this = the object that called it
  }
};
student.greet();  // "Rahul"

// ===== 3. In a Regular Function =====
function showThis() {
  console.log(this);  
  // In non-strict: window
  // In strict mode: undefined
}

// ===== 4. In Arrow Functions (NO own this!) 🔴 =====
const student = {
  name: "Rahul",
  greet: () => {
    console.log(this.name);  // undefined! Arrow takes `this` from PARENT scope
  },
  
  // ✅ Correct way:
  greetProperly() {
    // Regular method — `this` refers to student
    const inner = () => {
      console.log(this.name);  // "Rahul" — arrow inherits `this` from greetProperly
    };
    inner();
  }
};

// ===== 5. In Event Handlers =====
// DOM element:
// button.addEventListener('click', function() {
//   console.log(this);  // The button element
// });
// button.addEventListener('click', () => {
//   console.log(this);  // window (arrow doesn't have own this)
// });

// ===== 6. Explicit Binding: call, apply, bind 🔴 =====
function introduce(greeting, punctuation) {
  console.log(`${greeting}, I'm ${this.name}${punctuation}`);
}

const person = { name: "Rahul" };

// call — invoke with explicit `this`, args comma-separated
introduce.call(person, "Hi", "!");     // "Hi, I'm Rahul!"

// apply — same but args as ARRAY
introduce.apply(person, ["Hello", "."]);  // "Hello, I'm Rahul."

// bind — returns NEW function with `this` permanently set
const rahulIntro = introduce.bind(person);
rahulIntro("Hey", "!!");               // "Hey, I'm Rahul!!"
// bind is commonly used in React class components (legacy)
```

### `this` Cheat Sheet

```
┌───────────────────────────┬──────────────────────────────┐
│ Context                   │ this refers to               │
├───────────────────────────┼──────────────────────────────┤
│ Global (non-strict)       │ window / global              │
│ Global (strict)           │ undefined                    │
│ Object method             │ The object                   │
│ Arrow function            │ Inherited from parent scope  │
│ Event handler (regular)   │ The element                  │
│ Event handler (arrow)     │ Inherited (usually window)   │
│ call / apply              │ First argument               │
│ bind                      │ First argument (permanent)   │
│ new Constructor()         │ The new object               │
│ Class method              │ The instance                 │
└───────────────────────────┴──────────────────────────────┘
```

---

### 4.6 Recursion 🟡

```javascript
// Function that calls itself

// Factorial: 5! = 5 × 4 × 3 × 2 × 1 = 120
function factorial(n) {
  if (n <= 1) return 1;        // Base case (MUST have one!)
  return n * factorial(n - 1); // Recursive case
}
factorial(5);  // 120

// Fibonacci
function fibonacci(n) {
  if (n <= 1) return n;
  return fibonacci(n - 1) + fibonacci(n - 2);
}
fibonacci(10);  // 55

// Flatten nested array
function flatten(arr) {
  return arr.reduce((flat, item) => 
    flat.concat(Array.isArray(item) ? flatten(item) : item), 
  []);
}
flatten([1, [2, [3, [4]]], 5]);  // [1, 2, 3, 4, 5]

// Or use built-in: [1, [2, [3]]].flat(Infinity)
```

---

## 🧱 PHASE 5: OBJECTS & ARRAYS Deep Dive (Week 3–4)
### *"You'll work with objects and arrays in EVERY JavaScript project"*

```
⏱️ Estimated: 12–15 hours
Priority: 🔴🔴 — Absolutely critical for React, Node, interviews
```

---

### 5.1 Objects — Everything You Need 🔴

```javascript
// ===== Creating Objects =====
// Object literal (most common)
const student = {
  name: "Rahul Sharma",
  age: 21,
  branch: "CSE",
  skills: ["JavaScript", "React"],
  address: {
    city: "Pune",
    state: "Maharashtra"
  },
  // Method
  introduce() {
    return `Hi, I'm ${this.name} from ${this.branch}`;
  }
};

// ===== Accessing Properties =====
student.name;              // "Rahul Sharma" (dot notation)
student["branch"];         // "CSE" (bracket notation)
student.address.city;      // "Pune" (nested)

// Dynamic key access
const key = "age";
student[key];              // 21 (must use brackets for variables)

// ===== Adding / Modifying / Deleting =====
student.cgpa = 8.5;           // Add new property
student.age = 22;              // Modify existing
delete student.age;            // Delete property

// ===== Checking Properties =====
"name" in student;             // true
student.hasOwnProperty("name"); // true
Object.hasOwn(student, "name"); // true (modern ✅)

// ===== Object Destructuring 🔴🔴 =====
const { name, branch, age: studentAge = 20 } = student;
// name = "Rahul Sharma"
// branch = "CSE"
// studentAge = 21 (renamed + default value)

// Nested destructuring
const { address: { city, state } } = student;
// city = "Pune", state = "Maharashtra"

// In function parameters (very common in React!)
function printStudent({ name, branch, cgpa = "N/A" }) {
  console.log(`${name} | ${branch} | CGPA: ${cgpa}`);
}
printStudent(student);
```

### 🔴 Essential Object Methods

```javascript
const student = { name: "Rahul", age: 21, branch: "CSE" };

// Object.keys() — array of keys
Object.keys(student);     // ["name", "age", "branch"]

// Object.values() — array of values
Object.values(student);   // ["Rahul", 21, "CSE"]

// Object.entries() — array of [key, value] pairs
Object.entries(student);  // [["name","Rahul"], ["age",21], ["branch","CSE"]]

// Object.assign() — merge objects (shallow)
const defaults = { theme: "light", lang: "en" };
const userPrefs = { theme: "dark" };
const config = Object.assign({}, defaults, userPrefs);
// { theme: "dark", lang: "en" }

// Spread is cleaner:
const config2 = { ...defaults, ...userPrefs };
// { theme: "dark", lang: "en" }

// Object.freeze() — make immutable
const frozen = Object.freeze({ x: 1, y: 2 });
frozen.x = 10;    // Silently fails (or TypeError in strict mode)
frozen.z = 3;     // Silently fails

// Object.fromEntries() — convert entries back to object
const entries = [["a", 1], ["b", 2]];
Object.fromEntries(entries);  // { a: 1, b: 2 }

// Shorthand properties (ES6)
const name = "Rahul";
const age = 21;
const person = { name, age };  // Same as { name: name, age: age }

// Computed property names
const field = "email";
const obj = { [field]: "rahul@example.com" };  // { email: "rahul@..." }
```

---

### 5.2 Arrays — The Complete Guide 🔴🔴

```javascript
// ===== Creating Arrays =====
const fruits = ["apple", "mango", "banana"];
const numbers = new Array(1, 2, 3);     // Less common
const empty = new Array(5);              // [empty × 5] (gotcha!)
const filled = Array.from({ length: 5 }, (_, i) => i + 1);  // [1,2,3,4,5]

// ===== Array Destructuring 🔴 =====
const [first, second, ...rest] = fruits;
// first = "apple", second = "mango", rest = ["banana"]

// Skip elements
const [a, , c] = [1, 2, 3];  // a = 1, c = 3

// Swap variables (classic interview trick!)
let x = 10, y = 20;
[x, y] = [y, x];  // x = 20, y = 10 ✨
```

### 🔴🔴 Array Methods — THE Most Important Section

```javascript
const students = [
  { name: "Rahul",  cgpa: 8.5, branch: "CSE", placed: true },
  { name: "Priya",  cgpa: 9.1, branch: "ECE", placed: true },
  { name: "Amit",   cgpa: 7.2, branch: "CSE", placed: false },
  { name: "Sneha",  cgpa: 8.8, branch: "CSE", placed: true },
  { name: "Karan",  cgpa: 6.5, branch: "ME",  placed: false },
];
```

### Tier 1 — MUST Know (used daily) 🔴

```javascript
// ===== .map() — Transform each element, return NEW array =====
const names = students.map(s => s.name);
// ["Rahul", "Priya", "Amit", "Sneha", "Karan"]

const cards = students.map(s => `${s.name} (${s.branch})`);
// ["Rahul (CSE)", "Priya (ECE)", ...]

// ===== .filter() — Keep elements that pass a test =====
const cseStudents = students.filter(s => s.branch === "CSE");
// [{ name: "Rahul"... }, { name: "Amit"... }, { name: "Sneha"... }]

const topPerformers = students.filter(s => s.cgpa >= 8.5 && s.placed);
// [{ name: "Rahul"... }, { name: "Sneha"... }]

// ===== .reduce() — Accumulate to single value 🔴🔴 =====
const totalCgpa = students.reduce((sum, s) => sum + s.cgpa, 0);
// 40.1

const avgCgpa = totalCgpa / students.length;
// 8.02

// Count placed students
const placedCount = students.reduce((count, s) => s.placed ? count + 1 : count, 0);
// 3

// Group by branch
const grouped = students.reduce((groups, s) => {
  groups[s.branch] = groups[s.branch] || [];
  groups[s.branch].push(s);
  return groups;
}, {});
// { CSE: [...], ECE: [...], ME: [...] }

// ===== .forEach() — Loop (no return value) =====
students.forEach((s, index) => {
  console.log(`${index + 1}. ${s.name}`);
});
// Unlike map, forEach doesn't return anything — use for side effects only

// ===== .find() — First match (or undefined) =====
const rahul = students.find(s => s.name === "Rahul");
// { name: "Rahul", cgpa: 8.5, ... }

// ===== .findIndex() — Index of first match (or -1) =====
const idx = students.findIndex(s => s.cgpa > 9);  // 1 (Priya)

// ===== .some() — At least ONE passes test? (boolean) =====
students.some(s => s.cgpa > 9);   // true (Priya)

// ===== .every() — ALL pass test? (boolean) =====
students.every(s => s.cgpa > 7);  // false (Karan has 6.5)

// ===== .includes() — Contains value? (primitives only) =====
[1, 2, 3].includes(2);  // true
["CSE", "ECE"].includes("ME");  // false
```

### Tier 2 — Important (frequently used) 🟡

```javascript
// ===== .sort() — ⚠️ MUTATES original array =====
const nums = [40, 100, 1, 5, 25];
nums.sort();                          // [1, 100, 25, 40, 5] ← WRONG! (lexicographic)
nums.sort((a, b) => a - b);          // [1, 5, 25, 40, 100] ← Ascending ✅
nums.sort((a, b) => b - a);          // [100, 40, 25, 5, 1] ← Descending

// Sort students by CGPA descending
students.sort((a, b) => b.cgpa - a.cgpa);

// ✅ Non-mutating sort (ES2023):
const sorted = students.toSorted((a, b) => b.cgpa - a.cgpa);

// ===== .slice() — Extract portion (does NOT mutate) =====
const arr = [0, 1, 2, 3, 4, 5];
arr.slice(1, 4);   // [1, 2, 3] (start inclusive, end exclusive)
arr.slice(-2);     // [4, 5] (last 2 elements)

// ===== .splice() — Add/Remove (MUTATES!) =====
const arr2 = [1, 2, 3, 4, 5];
arr2.splice(2, 1);        // Removes 1 element at index 2 → arr2 = [1, 2, 4, 5]
arr2.splice(1, 0, 99);    // Insert 99 at index 1 → arr2 = [1, 99, 2, 4, 5]
arr2.splice(1, 1, 100);   // Replace index 1 → arr2 = [1, 100, 2, 4, 5]

// ===== .flat() — Flatten nested arrays =====
[1, [2, [3, [4]]]].flat();         // [1, 2, [3, [4]]]  (1 level)
[1, [2, [3, [4]]]].flat(Infinity); // [1, 2, 3, 4]      (all levels)

// ===== .flatMap() — map + flat(1) =====
const sentences = ["Hello World", "Hi There"];
sentences.flatMap(s => s.split(" "));  // ["Hello", "World", "Hi", "There"]

// ===== .concat() / spread — Combine arrays =====
const combined = [1, 2].concat([3, 4]);    // [1, 2, 3, 4]
const combined2 = [...[1, 2], ...[3, 4]];  // [1, 2, 3, 4] ✅ Preferred

// ===== .join() — Array to string =====
["Rahul", "Priya", "Amit"].join(", ");  // "Rahul, Priya, Amit"
["2024", "06", "15"].join("-");          // "2024-06-15"

// ===== .reverse() — ⚠️ MUTATES =====
[1, 2, 3].reverse();                    // [3, 2, 1]
[1, 2, 3].toReversed();                 // [3, 2, 1] (non-mutating, ES2023)

// ===== .fill() =====
new Array(5).fill(0);     // [0, 0, 0, 0, 0]
[1, 2, 3, 4].fill(0, 1, 3);  // [1, 0, 0, 4]

// ===== Array.from() — Convert iterable to array =====
Array.from("hello");                    // ["h", "e", "l", "l", "o"]
Array.from({ length: 5 }, (_, i) => i); // [0, 1, 2, 3, 4]
Array.from(new Set([1, 1, 2, 3]));      // [1, 2, 3] (remove dupes)
```

### 🔴 Chaining Array Methods (The Real Power)

```javascript
// Find average CGPA of placed CSE students
const avgCgpaPlacedCSE = students
  .filter(s => s.branch === "CSE" && s.placed)  // CSE + placed
  .map(s => s.cgpa)                               // Extract CGPAs
  .reduce((sum, cgpa, _, arr) => sum + cgpa / arr.length, 0);  // Average

// Get sorted list of unique branches
const branches = [...new Set(students.map(s => s.branch))].sort();
// ["CSE", "ECE", "ME"]

// Create a leaderboard string
const leaderboard = students
  .sort((a, b) => b.cgpa - a.cgpa)
  .map((s, i) => `${i + 1}. ${s.name} (${s.cgpa})`)
  .join("\n");
// "1. Priya (9.1)\n2. Sneha (8.8)\n3. Rahul (8.5)..."
```

### Mutating vs Non-Mutating Methods

```
┌───────────────────────────────────────────────────────┐
│ MUTATING (changes original)  │ NON-MUTATING (safe)    │
├──────────────────────────────┼────────────────────────┤
│ push, pop                    │ map, filter, reduce    │
│ shift, unshift               │ slice, concat          │
│ splice                       │ flat, flatMap          │
│ sort, reverse                │ toSorted (ES2023)      │
│ fill                         │ toReversed (ES2023)    │
│                              │ toSpliced (ES2023)     │
│                              │ with (ES2023)          │
└──────────────────────────────┴────────────────────────┘

🎯 In React: ALWAYS use non-mutating methods.
   State should never be mutated directly.
```

---

### 5.3 Destructuring — Complete Guide 🔴

```javascript
// ===== Object Destructuring =====
const student = { name: "Rahul", age: 21, branch: "CSE", cgpa: 8.5 };

// Basic
const { name, branch } = student;

// Rename
const { name: studentName, branch: dept } = student;

// Default values
const { name, phone = "Not provided" } = student;

// Nested
const user = { address: { city: "Pune", pin: 411001 } };
const { address: { city, pin } } = user;

// Rest in destructuring
const { name, ...otherInfo } = student;
// name = "Rahul", otherInfo = { age: 21, branch: "CSE", cgpa: 8.5 }

// ===== Array Destructuring =====
const [a, b, c] = [1, 2, 3];
const [first, , third] = [1, 2, 3];   // Skip second
const [head, ...tail] = [1, 2, 3, 4]; // head = 1, tail = [2,3,4]

// ===== In Function Parameters (React pattern!) =====
// Instead of:
function old(props) {
  console.log(props.name, props.age);
}

// Do:
function modern({ name, age, branch = "CSE" }) {
  console.log(name, age, branch);
}

// ===== Destructuring in Loops =====
const students = [
  { name: "Rahul", cgpa: 8.5 },
  { name: "Priya", cgpa: 9.1 },
];

for (const { name, cgpa } of students) {
  console.log(`${name}: ${cgpa}`);
}
```

---

## 🧱 PHASE 6: DATA STRUCTURES — Map, Set, JSON (Week 4)

```
⏱️ Estimated: 5–6 hours
Priority: 🔴 JSON, Set | 🟡 Map
```

### 6.1 Map vs Object 🟡

```javascript
// Map = key-value pairs where keys can be ANYTHING (not just strings)
const map = new Map();
map.set("name", "Rahul");
map.set(42, "answer");
map.set(true, "yes");

const objKey = { id: 1 };
map.set(objKey, "object as key!");

map.get("name");      // "Rahul"
map.get(42);           // "answer"
map.has(true);         // true
map.size;              // 4
map.delete(42);
map.clear();           // Remove all

// Iterating
for (const [key, value] of map) {
  console.log(`${key}: ${value}`);
}
```

```
┌──────────────────┬────────────────────┬──────────────────────┐
│ Feature          │ Object             │ Map                  │
├──────────────────┼────────────────────┼──────────────────────┤
│ Key types        │ String/Symbol only │ Any type             │
│ Order            │ Not guaranteed     │ Insertion order ✅   │
│ Size             │ Manual (Object.keys)│ .size property      │
│ Iteration        │ for...in           │ for...of ✅          │
│ Performance      │ OK                 │ Better for frequent  │
│                  │                    │ add/delete           │
│ JSON support     │ ✅ Yes             │ ❌ No (needs convert)│
│ Default keys     │ Has prototype keys │ None (clean)         │
└──────────────────┴────────────────────┴──────────────────────┘

Use Map when: keys aren't strings, or you need ordered/counted items
Use Object for: most cases, JSON data, configuration
```

### 6.2 Set — Unique Values Only 🔴

```javascript
const set = new Set([1, 2, 3, 3, 4, 4, 5]);
console.log(set);  // Set {1, 2, 3, 4, 5} — duplicates removed!

set.add(6);
set.has(3);        // true
set.delete(3);
set.size;          // 5

// ⭐ Most common use: Remove duplicates from array
const arr = [1, 1, 2, 2, 3, 3];
const unique = [...new Set(arr)];   // [1, 2, 3] 🔴

// Remove duplicate objects (by property)
const students = [
  { id: 1, name: "Rahul" },
  { id: 2, name: "Priya" },
  { id: 1, name: "Rahul" },  // duplicate
];
const uniqueIds = [...new Set(students.map(s => s.id))];  // [1, 2]
```

### 6.3 JSON 🔴

```javascript
// JSON = JavaScript Object Notation (data exchange format)
// Used in APIs, configuration files, localStorage

// Object → JSON string
const student = { name: "Rahul", age: 21, skills: ["JS", "React"] };
const jsonString = JSON.stringify(student);
// '{"name":"Rahul","age":21,"skills":["JS","React"]}'

// Pretty print
JSON.stringify(student, null, 2);  // Indented with 2 spaces

// JSON string → Object
const parsed = JSON.parse(jsonString);
console.log(parsed.name);  // "Rahul"

// ⚠️ JSON limitations:
// Can't store: functions, undefined, Symbol, Date (becomes string)
// Can't have: comments, trailing commas

// Deep clone trick (simple objects only)
const clone = JSON.parse(JSON.stringify(original));
// ✅ Better: structuredClone(original) (modern)
```

---

## 🧱 PHASE 7: ASYNCHRONOUS JAVASCRIPT (Week 5–6)
### *"THE hardest and most important topic. Master this = Master JS."*

```
⏱️ Estimated: 15–18 hours
Priority: 🔴🔴🔴 — Every interview asks about this.
                     Every real app uses this.
                     React is built on async patterns.
```

---

### 7.1 Why Async? 🔴

```
🧒 ELI5:
JavaScript is SINGLE-THREADED — it can do ONE thing at a time.
Like a single-counter shop — one customer at a time.

But what about things that take time?
  → Fetching data from server (network request)
  → Reading a file
  → setTimeout / animations
  → User waiting for input

If JS waited for each one, the page would FREEZE.

Solution: ASYNCHRONOUS programming.
JS says: "Hey network, fetch this data. I'll continue working.
Call me when you're done." — and keeps the page responsive.
```

```
SYNCHRONOUS vs ASYNCHRONOUS:

Synchronous (blocking):        Asynchronous (non-blocking):
┌─────────────────────┐        ┌─────────────────────┐
│ Task 1 (2 sec)      │        │ Task 1 starts       │
│ ████████████████████│        │ █████████           │
│ Task 2 (3 sec)      │        │ Task 2 starts       │
│ ██████████████████████████│  │ █████████████       │
│ Task 3 (1 sec)      │        │ Task 3 starts       │
│ ██████████          │        │ ████                │
│                     │        │ Task 3 done  ✅     │
│ Total: 6 seconds    │        │ Task 1 done  ✅     │
└─────────────────────┘        │ Task 2 done  ✅     │
                               │ Total: ~3 seconds   │
                               └─────────────────────┘
```

---

### 7.2 Event Loop 🔴🔴 (THE Most Asked Interview Topic!)

```
🧒 ELI5:
The Event Loop is like a restaurant manager:

1. CALL STACK = The Chef (does one task at a time)
2. WEB APIs = The kitchen helpers (timer, fetch, DOM events)
3. CALLBACK QUEUE = The waiting line (tasks ready to be served)
4. EVENT LOOP = The manager checking: "Is chef free? Send next task!"

┌──────────────────────────────────────────────────────────┐
│                    JAVASCRIPT ENGINE                      │
│                                                          │
│  ┌─────────────────┐     ┌──────────────────────────┐   │
│  │   CALL STACK     │     │     WEB APIs              │   │
│  │                 │     │  (setTimeout, fetch,      │   │
│  │  main()         │     │   DOM events, etc.)       │   │
│  │  ↓              │ ──► │                          │   │
│  │  function()     │     │  Timer... tick tick...    │   │
│  │  ↓              │     │  Fetch... waiting...     │   │
│  │  (empty = idle) │     │                          │   │
│  └─────────────────┘     └──────────┬───────────────┘   │
│          ▲                          │                    │
│          │                          ▼                    │
│          │              ┌───────────────────────┐        │
│          │              │  MICROTASK QUEUE       │        │
│          │◄─────────────│  (Promises, queueMicro)│       │
│          │   (Priority!)└───────────────────────┘        │
│          │                                               │
│          │              ┌───────────────────────┐        │
│          │◄─────────────│  MACROTASK QUEUE       │       │
│          │              │  (setTimeout, setInt)  │        │
│     EVENT LOOP          └───────────────────────┘        │
│  "Is stack empty?                                        │
│   → Check microtask queue first                          │
│   → Then macrotask queue"                                │
└──────────────────────────────────────────────────────────┘
```

### Event Loop Example (Interview Question!) 🔴

```javascript
console.log("1");                          // Sync → Call Stack

setTimeout(() => {
  console.log("2");                        // Macro task → Queue
}, 0);

Promise.resolve().then(() => {
  console.log("3");                        // Micro task → Queue
});

console.log("4");                          // Sync → Call Stack

// OUTPUT ORDER: 1, 4, 3, 2
// WHY?
// Step 1: "1" → sync, runs immediately
// Step 2: setTimeout → sends to Web API → goes to MACRO queue
// Step 3: Promise.then → goes to MICRO queue  
// Step 4: "4" → sync, runs immediately
// Step 5: Call stack empty → Event Loop checks MICRO first → "3"
// Step 6: Event Loop checks MACRO → "2"

// 🎯 RULE: Microtasks (Promises) ALWAYS run before Macrotasks (setTimeout)
```

### More Complex Example

```javascript
console.log("Start");

setTimeout(() => console.log("Timeout 1"), 0);
setTimeout(() => console.log("Timeout 2"), 0);

Promise.resolve()
  .then(() => console.log("Promise 1"))
  .then(() => console.log("Promise 2"));

Promise.resolve()
  .then(() => {
    console.log("Promise 3");
    setTimeout(() => console.log("Timeout 3"), 0);
  });

console.log("End");

// OUTPUT:
// Start
// End
// Promise 1
// Promise 3
// Promise 2
// Timeout 1
// Timeout 2
// Timeout 3
```

---

### 7.3 Callbacks 🔴

```javascript
// Callback = function passed as argument, called later

function fetchData(url, callback) {
  // Simulating network request
  setTimeout(() => {
    const data = { name: "Rahul", age: 21 };
    callback(null, data);  // Convention: error first, data second
  }, 2000);
}

fetchData("/api/user", (error, data) => {
  if (error) {
    console.error("Failed:", error);
    return;
  }
  console.log("Received:", data);
});
```

### Callback Hell (Pyramid of Doom) 🔴

```javascript
// ❌ THE PROBLEM — nested callbacks become unreadable
getUser(userId, (err, user) => {
  getOrders(user.id, (err, orders) => {
    getProducts(orders[0].productId, (err, product) => {
      getReviews(product.id, (err, reviews) => {
        console.log(reviews);
        // 4 levels deep... imagine 10 levels!
      });
    });
  });
});
// This is why PROMISES were invented.
```

---

### 7.4 Promises 🔴🔴🔴

```
🧒 ELI5:
A Promise is like ordering food on Swiggy/Zomato:
  1. You place the order → Promise is PENDING
  2. Food arrives → Promise is FULFILLED (resolved) ✅
  3. Order cancelled → Promise is REJECTED ❌

You don't stand at the door waiting. You continue your work.
When food arrives (or fails), you handle it.
```

```javascript
// ===== Creating a Promise =====
const myPromise = new Promise((resolve, reject) => {
  const success = true;  // Simulating success/failure
  
  setTimeout(() => {
    if (success) {
      resolve({ name: "Rahul", cgpa: 8.5 });  // ✅ Fulfilled
    } else {
      reject(new Error("Student not found"));   // ❌ Rejected
    }
  }, 2000);
});

// ===== Consuming a Promise =====
myPromise
  .then(data => {
    console.log("Success:", data);   // Runs if resolved
    return data.name;                // Can chain!
  })
  .then(name => {
    console.log("Name:", name);      // Receives returned value
  })
  .catch(error => {
    console.error("Error:", error.message);  // Runs if rejected
  })
  .finally(() => {
    console.log("Done! (always runs)");      // Always runs
  });

// ===== Promise Chaining (solves callback hell!) =====
getUser(userId)
  .then(user => getOrders(user.id))
  .then(orders => getProducts(orders[0].productId))
  .then(product => getReviews(product.id))
  .then(reviews => console.log(reviews))
  .catch(err => console.error("Something failed:", err));
// Beautiful. Flat. Readable. 😍
```

### Promise Static Methods 🔴

```javascript
// Promise.all — Wait for ALL to resolve (fail-fast on any rejection)
const [users, posts, comments] = await Promise.all([
  fetch("/api/users").then(r => r.json()),
  fetch("/api/posts").then(r => r.json()),
  fetch("/api/comments").then(r => r.json()),
]);
// All 3 requests run SIMULTANEOUSLY — much faster than sequential!
// ⚠️ If ANY one fails, entire Promise.all fails

// Promise.allSettled — Wait for ALL (don't fail on rejection)
const results = await Promise.allSettled([
  fetch("/api/users"),
  fetch("/api/broken-endpoint"),  // This fails
]);
// results = [
//   { status: "fulfilled", value: Response },
//   { status: "rejected",  reason: Error }
// ]

// Promise.race — First to settle wins (resolve OR reject)
const fastest = await Promise.race([
  fetch("https://api1.com/data"),
  fetch("https://api2.com/data"),
]);

// Promise.any — First to RESOLVE wins (ignores rejections)
const firstSuccess = await Promise.any([
  fetch("https://api1.com/data"),  // fails
  fetch("https://api2.com/data"),  // succeeds first!
  fetch("https://api3.com/data"),
]);
```

```
┌──────────────────┬──────────────────────────────────────────┐
│ Method           │ Behavior                                 │
├──────────────────┼──────────────────────────────────────────┤
│ Promise.all      │ All must resolve. One reject = all fail  │
│ Promise.allSettled│ Waits for all. Reports each status      │
│ Promise.race     │ First to settle (resolve OR reject) wins │
│ Promise.any      │ First to RESOLVE wins. Ignores rejects  │
└──────────────────┴──────────────────────────────────────────┘
```

---

### 7.5 async / await 🔴🔴🔴

```
🧒 ELI5:
async/await is SYNTACTIC SUGAR over Promises.
It makes async code LOOK like sync code — much easier to read!

Promises: .then().then().catch() — chain-based
async/await: just write normal-looking code with `await`
```

```javascript
// ===== Basic async/await =====
async function getStudentData(id) {
  try {
    const response = await fetch(`/api/students/${id}`);  // Waits here
    
    if (!response.ok) {
      throw new Error(`HTTP Error: ${response.status}`);
    }
    
    const student = await response.json();                 // Waits here
    console.log(student.name);
    return student;
  } catch (error) {
    console.error("Failed:", error.message);
  } finally {
    console.log("Request completed");
  }
}

// Call it
const student = await getStudentData(123);

// ===== Comparison: Promises vs async/await =====

// Promise chain:
function getDataPromise() {
  return fetch("/api/users")
    .then(res => res.json())
    .then(users => fetch(`/api/users/${users[0].id}/posts`))
    .then(res => res.json())
    .then(posts => console.log(posts))
    .catch(err => console.error(err));
}

// async/await (same thing, much cleaner):
async function getDataAsync() {
  try {
    const usersRes = await fetch("/api/users");
    const users = await usersRes.json();
    
    const postsRes = await fetch(`/api/users/${users[0].id}/posts`);
    const posts = await postsRes.json();
    
    console.log(posts);
  } catch (err) {
    console.error(err);
  }
}

// ===== Parallel async/await (DON'T await sequentially!) =====
// ❌ SLOW — Sequential (one after another)
async function slow() {
  const users = await fetch("/api/users");      // 2 sec
  const posts = await fetch("/api/posts");      // 2 sec
  const comments = await fetch("/api/comments");// 2 sec
  // Total: ~6 seconds 😱
}

// ✅ FAST — Parallel (all at once)
async function fast() {
  const [users, posts, comments] = await Promise.all([
    fetch("/api/users"),       // ┐
    fetch("/api/posts"),       // ├── All start at same time!
    fetch("/api/comments"),    // ┘
  ]);
  // Total: ~2 seconds ⚡
}
```

---

### 7.6 setTimeout & setInterval 🟡

```javascript
// setTimeout — run ONCE after delay
const timerId = setTimeout(() => {
  console.log("Runs after 2 seconds");
}, 2000);

// Cancel it
clearTimeout(timerId);

// setInterval — run REPEATEDLY at interval
let count = 0;
const intervalId = setInterval(() => {
  count++;
  console.log(`Tick ${count}`);
  if (count === 5) clearInterval(intervalId);  // Stop after 5
}, 1000);

// ⚠️ setTimeout(fn, 0) doesn't run "immediately"
// It runs after current synchronous code finishes + microtasks
```

---

## 🧱 PHASE 8: WORKING WITH APIs (Week 6–7)
### *"Connect to the real world — fetch data from servers"*

```
⏱️ Estimated: 6–8 hours
Priority: 🔴 — Every web app fetches data
```

### Fetch API 🔴

```javascript
// ===== GET Request =====
async function getUsers() {
  try {
    const response = await fetch("https://jsonplaceholder.typicode.com/users");
    
    if (!response.ok) {
      throw new Error(`HTTP Error: ${response.status}`);
    }
    
    const users = await response.json();
    console.log(users);
  } catch (error) {
    console.error("Fetch failed:", error.message);
  }
}

// ===== POST Request =====
async function createUser(userData) {
  try {
    const response = await fetch("https://jsonplaceholder.typicode.com/users", {
      method: "POST",
      headers: {
        "Content-Type": "application/json",
      },
      body: JSON.stringify(userData),
    });
    
    const newUser = await response.json();
    console.log("Created:", newUser);
  } catch (error) {
    console.error("Create failed:", error.message);
  }
}

createUser({ name: "Rahul", email: "rahul@example.com" });

// ===== PUT, PATCH, DELETE =====
// PUT — Replace entire resource
await fetch(`/api/users/${id}`, {
  method: "PUT",
  headers: { "Content-Type": "application/json" },
  body: JSON.stringify({ name: "Updated Name", email: "new@email.com" }),
});

// PATCH — Partial update
await fetch(`/api/users/${id}`, {
  method: "PATCH",
  headers: { "Content-Type": "application/json" },
  body: JSON.stringify({ name: "New Name" }),  // Only changed fields
});

// DELETE
await fetch(`/api/users/${id}`, { method: "DELETE" });

// ===== Abort Controller (cancel requests) =====
const controller = new AbortController();

fetch("/api/slow-data", { signal: controller.signal })
  .then(res => res.json())
  .catch(err => {
    if (err.name === 'AbortError') {
      console.log("Request was cancelled");
    }
  });

// Cancel after 3 seconds
setTimeout(() => controller.abort(), 3000);
```

### HTTP Methods Cheat Sheet

```
┌─────────┬───────────────────┬────────────┬───────────┐
│ Method  │ Purpose           │ Body?      │ Idempotent│
├─────────┼───────────────────┼────────────┼───────────┤
│ GET     │ Read/Retrieve     │ ❌ No      │ ✅ Yes    │
│ POST    │ Create new        │ ✅ Yes     │ ❌ No     │
│ PUT     │ Replace entirely  │ ✅ Yes     │ ✅ Yes    │
│ PATCH   │ Update partially  │ ✅ Yes     │ ❌ No     │
│ DELETE  │ Remove            │ ❌ Usually │ ✅ Yes    │
└─────────┴───────────────────┴────────────┴───────────┘
```

---

## 🧱 PHASE 9: MODULES (Week 7)

```
⏱️ Estimated: 3–4 hours
Priority: 🔴 — Every modern JS project uses modules
```

```javascript
// ===== ES Modules (ESM) — THE modern standard 🔴 =====

// math.js — Exporting
export const PI = 3.14159;

export function add(a, b) {
  return a + b;
}

export function multiply(a, b) {
  return a * b;
}

// Default export (one per file)
export default class Calculator {
  add(a, b) { return a + b; }
  subtract(a, b) { return a - b; }
}

// app.js — Importing
import Calculator from './math.js';              // Default import
import { add, multiply, PI } from './math.js';   // Named imports
import { add as sum } from './math.js';           // Rename
import * as MathUtils from './math.js';           // Import everything

const calc = new Calculator();
calc.add(2, 3);  // 5
MathUtils.multiply(4, 5);  // 20

// ===== CommonJS (CJS) — Node.js legacy (still common) =====
// math.js
module.exports = { add, multiply };
// OR
exports.add = (a, b) => a + b;

// app.js
const { add, multiply } = require('./math');
```

```
┌──────────────────┬────────────────────┬──────────────────────┐
│ Feature          │ ES Modules (ESM)   │ CommonJS (CJS)       │
├──────────────────┼────────────────────┼──────────────────────┤
│ Syntax           │ import/export      │ require/module.exports│
│ Loading          │ Async (static)     │ Sync (dynamic)       │
│ Browser support  │ ✅ Yes             │ ❌ No (Node only)    │
│ Tree-shaking     │ ✅ Yes             │ ❌ No                │
│ Use in 2025      │ 🔴 Default         │ 🟡 Legacy Node.js   │
└──────────────────┴────────────────────┴──────────────────────┘
```

---

## 🧱 PHASE 10: OOP & CLASSES (Week 7–8)

```
⏱️ Estimated: 6–8 hours
Priority: 🟡 — Important for understanding, less used in React
```

### 10.1 Prototypal Inheritance 🟡

```javascript
// Every JS object has a hidden [[Prototype]] link
// When you access a property, JS looks up the "prototype chain"

const animal = {
  isAlive: true,
  eat() { console.log("Eating..."); }
};

const dog = Object.create(animal);  // dog's prototype = animal
dog.bark = function() { console.log("Woof!"); };

dog.bark();     // "Woof!" — own property
dog.eat();      // "Eating..." — inherited from animal ✅
dog.isAlive;    // true — inherited

// Prototype chain: dog → animal → Object.prototype → null
```

### 10.2 ES6 Classes 🟡

```javascript
class Student {
  // Private field (ES2022)
  #password;
  
  // Static property
  static college = "IIT Bombay";
  
  constructor(name, branch, cgpa) {
    this.name = name;
    this.branch = branch;
    this.cgpa = cgpa;
    this.#password = "secret123";
  }
  
  // Method
  introduce() {
    return `Hi, I'm ${this.name} from ${this.branch}`;
  }
  
  // Getter
  get grade() {
    if (this.cgpa >= 9) return "A+";
    if (this.cgpa >= 8) return "A";
    if (this.cgpa >= 7) return "B";
    return "C";
  }
  
  // Setter
  set gpa(value) {
    if (value < 0 || value > 10) throw new Error("Invalid CGPA");
    this.cgpa = value;
  }
  
  // Static method (called on class, not instance)
  static compare(s1, s2) {
    return s2.cgpa - s1.cgpa;
  }
}

const rahul = new Student("Rahul", "CSE", 8.5);
rahul.introduce();       // "Hi, I'm Rahul from CSE"
rahul.grade;             // "A" (getter — no parentheses!)
rahul.gpa = 9.0;         // setter
Student.college;         // "IIT Bombay" (static)
// rahul.#password;      // ❌ SyntaxError (private!)

// ===== Inheritance =====
class PlacedStudent extends Student {
  constructor(name, branch, cgpa, company, ctc) {
    super(name, branch, cgpa);  // Call parent constructor
    this.company = company;
    this.ctc = ctc;
  }
  
  // Override parent method
  introduce() {
    return `${super.introduce()}, placed at ${this.company} (₹${this.ctc} LPA)`;
  }
}

const priya = new PlacedStudent("Priya", "ECE", 9.1, "Google", 45);
priya.introduce();
// "Hi, I'm Priya from ECE, placed at Google (₹45 LPA)"
```

> 🎯 **Note**: Classes in JS are **syntactic sugar** over prototypal inheritance. Under the hood, it's still prototypes. In React, you'll rarely write classes (functional components + hooks are the standard). But understanding classes helps with:
> - Reading legacy code
> - TypeScript
> - Design pattern interviews
> - Node.js backends

---

## 🧱 PHASE 11: DOM MANIPULATION (Week 8)

```
⏱️ Estimated: 6–8 hours
Priority: 🔴 for vanilla JS | 🟡 for React developers
(React handles DOM for you, but knowing the basics is essential)
```

```javascript
// ===== Selecting Elements =====
document.getElementById("title");           // By ID
document.querySelector(".card");            // First match (CSS selector)
document.querySelectorAll(".card");         // All matches (NodeList)
document.getElementsByClassName("card");    // HTMLCollection (live)

// ===== Modifying Elements =====
const title = document.querySelector("#title");
title.textContent = "New Title";             // Change text
title.innerHTML = "<em>Styled</em> Title";   // Change HTML
title.style.color = "blue";                  // Inline style
title.classList.add("active");               // Add class
title.classList.remove("active");            // Remove class
title.classList.toggle("active");            // Toggle class
title.setAttribute("data-id", "123");        // Set attribute

// ===== Creating & Adding Elements =====
const card = document.createElement("div");
card.className = "card";
card.textContent = "New Card";
document.body.appendChild(card);             // Add to end of body
document.body.prepend(card);                 // Add to beginning
parentElement.insertBefore(card, referenceElement);

// ===== Removing Elements =====
element.remove();                            // Modern
parent.removeChild(child);                   // Old way

// ===== Event Listeners 🔴 =====
const button = document.querySelector("#btn");

button.addEventListener("click", (event) => {
  console.log("Clicked!", event.target);
});

// Event delegation (listen on parent, handle child events)
document.querySelector(".list").addEventListener("click", (e) => {
  if (e.target.tagName === "LI") {
    console.log("Clicked:", e.target.textContent);
  }
});
// ↑ This pattern is how React's event system works internally!

// Common events: click, submit, input, change, keydown, keyup,
//                mouseover, mouseout, scroll, load, DOMContentLoaded
```

---

## 🧱 PHASE 12: ADVANCED TOPICS (Week 9–10)

```
⏱️ Estimated: 8–10 hours
Priority: Mix of 🟡 and 🟢
```

### 12.1 Iterators & Generators 🟢

```javascript
// Generator = function that can PAUSE and RESUME
function* numberGenerator() {
  yield 1;
  yield 2;
  yield 3;
}

const gen = numberGenerator();
gen.next();  // { value: 1, done: false }
gen.next();  // { value: 2, done: false }
gen.next();  // { value: 3, done: false }
gen.next();  // { value: undefined, done: true }

// Infinite sequence
function* fibonacci() {
  let [a, b] = [0, 1];
  while (true) {
    yield a;
    [a, b] = [b, a + b];
  }
}

const fib = fibonacci();
fib.next().value;  // 0
fib.next().value;  // 1
fib.next().value;  // 1
fib.next().value;  // 2
fib.next().value;  // 3
```

### 12.2 Strict Mode 🟡

```javascript
"use strict";
// Placed at top of file or function

// What it does:
// ❌ Prevents accidental globals
// x = 10;  // ReferenceError (must declare with let/const/var)

// ❌ Prevents duplicate parameter names
// function add(a, a) {} // SyntaxError

// ❌ this is undefined in functions (not window)
// ❌ Prevents deleting undeletable properties
// ❌ Prevents octal syntax

// 🎯 ES6 modules are automatically in strict mode
```

### 12.3 Memory Management 🟢

```javascript
// JavaScript has AUTOMATIC garbage collection
// But you should avoid memory leaks:

// ⚠️ Common memory leaks:
// 1. Forgotten timers
const interval = setInterval(() => { /* ... */ }, 1000);
// If component unmounts, CLEAR IT:
clearInterval(interval);

// 2. Forgotten event listeners
element.addEventListener('click', handler);
// When done:
element.removeEventListener('click', handler);

// 3. Closures holding references
function outer() {
  const hugeData = new Array(1000000).fill("x");
  return function inner() {
    // hugeData lives as long as inner() exists!
    console.log(hugeData.length);
  };
}

// 4. Detached DOM nodes
const element = document.querySelector(".card");
document.body.removeChild(element);
// If `element` variable still exists, DOM node isn't garbage collected

// WeakMap and WeakSet — allow garbage collection
const cache = new WeakMap();
let obj = { data: "important" };
cache.set(obj, "cached value");
obj = null;  // WeakMap allows garbage collection of the key
```

---

## 📅 COMPLETE WEEK-BY-WEEK PLAN

```
┌────────┬──────────────────────────────────────────┬─────────┬──────────────────────┐
│ Week   │ Topics                                    │ Priority│ Build                │
├────────┼──────────────────────────────────────────┼─────────┼──────────────────────┤
│ Week 1 │ Intro, Variables, Data Types, Operators    │ 🔴      │                      │
│ Week 2 │ Control Flow, Loops, Functions (basics)    │ 🔴      │ ✅ Calculator        │
│ Week 3 │ Arrow Functions, Closures, this, HOF       │ 🔴      │ ✅ Quiz App          │
│ Week 4 │ Objects, Arrays, Destructuring, Spread     │ 🔴      │ ✅ Student Dashboard │
│ Week 5 │ Async: Event Loop, Callbacks, Promises     │ 🔴      │                      │
│ Week 6 │ async/await, Fetch API, Error Handling      │ 🔴      │ ✅ GitHub User Finder│
│ Week 7 │ Modules, JSON, Map/Set                     │ 🟡      │ ✅ Notes App (CRUD)  │
│ Week 8 │ DOM Manipulation, Events                    │ 🟡      │ ✅ Interactive UI    │
│ Week 9 │ Classes, Prototypes, OOP                    │ 🟡      │                      │
│ Week 10│ Advanced: Generators, Memory, Debugging     │ 🟢      │ ✅ Mini Project      │
│ Week 11│ Practice: LeetCode JS + Interview Qs        │ 🔴      │                      │
│ Week 12│ Review + Build portfolio project             │ 🔴      │ ✅ Capstone Project  │
└────────┴──────────────────────────────────────────┴─────────┴──────────────────────┘
```

### ✅ Milestones

```
After Week 2:  You can write basic programs and functions
After Week 4:  You can work with data (objects, arrays) fluently
After Week 6:  You can fetch and handle API data ← REACT-READY ✅
After Week 8:  You can build interactive web pages (vanilla JS)
After Week 10: You understand the engine — interviews won't surprise you
After Week 12: You're confident for any JS interview + ready for React/Node
```

---

## 🏗️ BUILD THESE PROJECTS (In Order)

```
┌────┬───────────────────────────────┬──────────┬──────────────────────────────┐
│ #  │ Project                       │ Level    │ Key Concepts Practiced       │
├────┼───────────────────────────────┼──────────┼──────────────────────────────┤
│ 1  │ Calculator                    │ Beginner │ Functions, Events, DOM       │
│ 2  │ Quiz App                      │ Beginner │ Arrays, Objects, Logic       │
│ 3  │ Student Dashboard             │ Beginner+│ Array methods chain, Sort    │
│ 4  │ GitHub User Finder            │ Intermed.│ Fetch API, async/await       │
│ 5  │ Notes App (localStorage)      │ Intermed.│ CRUD, JSON, DOM, Modules    │
│ 6  │ Weather App                   │ Intermed.│ API, Error handling, UI      │
│ 7  │ Expense Tracker               │ Intermed+│ All concepts combined       │
│ 8  │ Mini E-commerce (Cart logic)  │ Advanced │ Classes, Closures, State    │
└────┴───────────────────────────────┴──────────┴──────────────────────────────┘
```

---

## 💼 JAVASCRIPT IN INTERVIEWS — What They Ask

### Top 20 Conceptual Questions 🔴

```
1.  Explain var vs let vs const
2.  What is hoisting? Give examples with var, let, function
3.  Explain closures with a practical example
4.  What is the event loop? Explain with setTimeout + Promise
5.  Explain `this` keyword in different contexts
6.  == vs === — when does == cause unexpected results?
7.  What is the prototype chain?
8.  Explain call, apply, bind with examples
9.  What are Promises? Explain states and chaining
10. async/await vs .then() — differences and error handling
11. Explain event bubbling, capturing, and delegation
12. What is debouncing and throttling?
13. Explain shallow copy vs deep copy
14. What are higher-order functions? Give examples
15. Explain map vs forEach vs reduce
16. What is callback hell and how to solve it?
17. Explain temporal dead zone (TDZ)
18. What are generators and when to use them?
19. Explain Promise.all vs Promise.allSettled vs Promise.race
20. How does garbage collection work in JavaScript?
```

### Top Coding Tasks 🔴

```
1.  Implement debounce function
2.  Implement throttle function
3.  Flatten a nested array (without .flat())
4.  Deep clone an object (without JSON or structuredClone)
5.  Implement Promise.all from scratch
6.  Implement Array.prototype.map polyfill
7.  Implement Array.prototype.reduce polyfill
8.  Create a memoize function
9.  Implement currying (infinite currying: sum(1)(2)(3)...)
10. Implement bind polyfill
11. Event emitter (pub/sub pattern)
12. Implement setInterval using setTimeout
13. Output-based questions (event loop, closures, hoisting)
14. LRU Cache implementation
15. Implement a pipe/compose function
```

### Two Killer Implementations for Interviews

```javascript
// ===== DEBOUNCE (asked in 80% of frontend interviews) =====
function debounce(fn, delay) {
  let timerId;
  return function(...args) {
    clearTimeout(timerId);
    timerId = setTimeout(() => fn.apply(this, args), delay);
  };
}

// Usage: Only search after user STOPS typing for 300ms
const searchInput = document.querySelector("#search");
const handleSearch = debounce((query) => {
  fetch(`/api/search?q=${query}`);
}, 300);
searchInput.addEventListener("input", (e) => handleSearch(e.target.value));

// ===== CURRYING (impressive to interviewers) =====
function curry(fn) {
  return function curried(...args) {
    if (args.length >= fn.length) {
      return fn.apply(this, args);
    }
    return function(...moreArgs) {
      return curried.apply(this, [...args, ...moreArgs]);
    };
  };
}

const add = curry((a, b, c) => a + b + c);
add(1)(2)(3);     // 6
add(1, 2)(3);     // 6
add(1)(2, 3);     // 6
add(1, 2, 3);     // 6
```

---

## 📚 BEST RESOURCES

| Type | Resource | Why |
|------|----------|-----|
| 📺 YouTube (Hindi) | **CodeWithHarry — JS Playlist** | Complete, beginner-friendly, Hindi |
| 📺 YouTube (Hindi) | **Chai aur Code (Hitesh)** | Practical, modern JS, Hindi |
| 📺 YouTube (Hindi) | **Akshay Saini — Namaste JavaScript** | 🔴 BEST for concepts (closures, event loop, this) |
| 📺 YouTube (English) | **Fireship — JS in 100 seconds** | Quick overview |
| 📺 YouTube (English) | **The Net Ninja — JS Playlist** | Structured, beginner |
| 📺 YouTube (English) | **Traversy Media — JS Crash Course** | Fast-paced, practical |
| 📖 Book | **"Eloquent JavaScript"** (free online) | The classic, thorough |
| 📖 Book | **"You Don't Know JS"** (Kyle Simpson) | Deep understanding |
| 📖 Docs | **MDN Web Docs** | 🔴 THE reference — always check here |
| 📖 Docs | **javascript.info** | Modern tutorial, excellent explanations |
| 🏋️ Practice | **LeetCode (JavaScript)** | Interview problems |
| 🏋️ Practice | **JavaScript30** (Wes Bos) | 30 mini projects, free |
| 🏋️ Practice | **Exercism.org/tracks/javascript** | Mentored exercises |
| 🆓 Course | **freeCodeCamp — JS Algorithms** | Certification, structured |

### 🎯 Recommended Learning Path

```
PHASE 1 (Foundation):
  📺 Akshay Saini — Namaste JavaScript (Season 1 & 2)
  → Covers execution context, hoisting, closures, event loop, 
     promises, this — with beautiful visualizations

PHASE 2 (Practice):
  🏋️ JavaScript30 by Wes Bos (30 projects in 30 days)
  → Builds real things with vanilla JS

PHASE 3 (Deep Dive):
  📖 javascript.info (The Modern JavaScript Tutorial)
  → Read chapters you're weak in

PHASE 4 (Interview Prep):
  📺 Akshay Saini — Namaste JavaScript Season 2
  → Promises, async/await, interview prep
  🏋️ 30 LeetCode Easy problems in JavaScript
```

---

## 🎯 WHAT'S NEXT AFTER JAVASCRIPT?

```
┌──────────────────────────────────────────────────────────────┐
│                     AFTER MASTERING JS                       │
│                                                              │
│  Frontend Path:                                              │
│  JS → React.js → TypeScript → Next.js → Tailwind            │
│                                                              │
│  Backend Path:                                               │
│  JS → Node.js → Express.js → MongoDB/PostgreSQL → REST APIs │
│                                                              │
│  Full Stack:                                                 │
│  JS → React + Node + DB → Full Stack Projects → Deploy       │
│                                                              │
│  Mobile:                                                     │
│  JS → React Native → Mobile Apps                             │
│                                                              │
│  🔴 RECOMMENDED: Go to React next (type "roadmap react")    │
└──────────────────────────────────────────────────────────────┘
```

---
