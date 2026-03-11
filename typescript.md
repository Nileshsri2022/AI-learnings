# THE ULTIMATE TYPESCRIPT MASTERY ROADMAP

**From Zero to TypeScript Expert in 6-8 Weeks**

*Every type, every pattern, every trick — nothing skipped*

---

## TABLE OF CONTENTS

```
PART 1:   What is TypeScript & Why It Exists
PART 2:   Prerequisites Checklist
PART 3:   TypeScript Fundamentals — Basic Types (Week 1)
PART 4:   Intermediate Types — Unions, Intersections, Narrowing (Week 2)
PART 5:   Functions & Generics (Week 3)
PART 6:   Interfaces, Types & OOP (Week 4)
PART 7:   Advanced Types — Utility Types, Mapped Types, Conditional Types (Week 5)
PART 8:   TypeScript with React & Next.js (Week 6)
PART 9:   TypeScript with Node.js & Backend (Week 7)
PART 10:  TypeScript Configuration & Tooling (Week 8)
PART 11:  Real-World Patterns & Best Practices
PART 12:  Build 6 TypeScript Projects
PART 13:  Resources (GitHub + YouTube + Courses)
PART 14:  Day-by-Day 30-Day Kickstart Plan
PART 15:  Interview Preparation (100+ Questions)
PART 16:  What Comes After TypeScript
```

---

## PART 1: WHAT IS TYPESCRIPT & WHY IT EXISTS

### 1.1 Understanding TypeScript

```
WHAT IS TYPESCRIPT:
  TypeScript = JavaScript + Types
  
  It's a SUPERSET of JavaScript — every valid JS is valid TS
  Created by Microsoft (Anders Hejlsberg — also created C#)
  Compiles to plain JavaScript (browsers don't run TS directly)
  
  TypeScript → Compiler (tsc) → JavaScript
  
  Think of it as: JavaScript with spell-check for your code

WHY TYPESCRIPT EXISTS — THE PROBLEM:

  // JavaScript — No errors until runtime 😱
  function add(a, b) {
    return a + b;
  }
  
  add(5, "3");        // "53" ← Bug! String concatenation, not addition
  add(5);             // NaN  ← Bug! b is undefined
  add({}, []);        // "[object Object]" ← WTF?!
  
  user.naem;          // undefined ← Typo! Should be "name"
  user.address.city;  // 💥 TypeError if address is null

  // TypeScript — Catches ALL these at compile time ✅
  function add(a: number, b: number): number {
    return a + b;
  }
  
  add(5, "3");        // ❌ Error: Argument of type 'string' is not assignable
  add(5);             // ❌ Error: Expected 2 arguments, but got 1
  add({}, []);        // ❌ Error: Argument of type '{}' is not assignable
  
  user.naem;          // ❌ Error: Property 'naem' does not exist. Did you mean 'name'?
  user.address.city;  // ❌ Error: Object is possibly 'null'

WHY LEARN TYPESCRIPT IN 2025:
  ✅ Required by 90%+ of companies
  ✅ Every major framework uses it (Next.js, Angular, etc.)
  ✅ Better autocomplete & IntelliSense in VS Code
  ✅ Catches bugs BEFORE they reach production
  ✅ Self-documenting code (types ARE the documentation)
  ✅ Safer refactoring (change type → see all affected code)
  ✅ Better team collaboration (types = contracts)
  ✅ Higher salary (TypeScript devs earn 10-20% more)

TYPESCRIPT IS NOT:
  ❌ A different language (it's JavaScript WITH types)
  ❌ Slower at runtime (types are removed during compilation)
  ❌ Difficult (if you know JS, you know 70% of TS already)
  ❌ Required for small projects (but always recommended)
```

### 1.2 How TypeScript Works

```
THE COMPILATION PROCESS:

  your-code.ts  →  TypeScript Compiler (tsc)  →  your-code.js
                   ↓
            Type Checking
         (errors shown here)
         Types are REMOVED
         in output JS

EXAMPLE:
  // Input: app.ts
  const greet = (name: string): string => {
    return `Hello, ${name}!`;
  };
  
  // Output: app.js (after compilation)
  const greet = (name) => {
    return `Hello, ${name}!`;
  };
  
  // Types are GONE at runtime!
  // They only exist during development

KEY INSIGHT:
  TypeScript types have ZERO runtime cost
  They exist ONLY during development
  The final JavaScript is identical
  This is called "type erasure"
```

---

## PART 2: PREREQUISITES CHECKLIST

```
BEFORE STARTING TYPESCRIPT:

JavaScript ✅ (8/10 minimum — CRITICAL):
  ✅ Variables (let, const), data types (string, number, boolean, null, undefined)
  ✅ Functions (arrow, regular, callbacks, closures)
  ✅ Arrays (map, filter, reduce, forEach, find, some, every)
  ✅ Objects (destructuring, spread, methods, computed properties)
  ✅ Classes (constructor, methods, inheritance, static)
  ✅ Async/Await, Promises
  ✅ ES Modules (import/export)
  ✅ Error handling (try/catch)
  ✅ Template literals
  ✅ Ternary operator, optional chaining (?.), nullish coalescing (??)

  IF JAVASCRIPT IS WEAK → Go back to JS first.
  TypeScript without JavaScript = Learning grammar without vocabulary.

VS Code ✅:
  ✅ Installed and comfortable using it
  ✅ TypeScript support is built-in!

Node.js ✅:
  ✅ Installed (v18+)
  ✅ npm basics
```

---

## PART 3: TYPESCRIPT FUNDAMENTALS — BASIC TYPES (Week 1)

### 3.1 Setup & First Program

```bash
# ✅ INSTALL TYPESCRIPT GLOBALLY:
npm install -g typescript
tsc --version  # Should show 5.x

# ✅ CREATE A PROJECT:
mkdir ts-learning
cd ts-learning
npm init -y
npm install -D typescript ts-node @types/node

# Initialize TypeScript config:
npx tsc --init
# Creates tsconfig.json

# ✅ COMPILE & RUN:
# Option 1: Compile then run
tsc app.ts         # Creates app.js
node app.js        # Run the JS

# Option 2: ts-node (compile + run in one step) ⭐
npx ts-node app.ts

# Option 3: tsx (faster, modern) ⭐⭐
npm install -D tsx
npx tsx app.ts

# ✅ WATCH MODE (auto-compile on save):
tsc --watch
```

```typescript
// ✅ FIRST TYPESCRIPT PROGRAM
// app.ts:

const message: string = "Hello TypeScript!";
console.log(message);

const age: number = 25;
const isActive: boolean = true;

console.log(`I am ${age} years old. Active: ${isActive}`);

// Run: npx tsx app.ts
```

### 3.2 Primitive Types ⭐⭐⭐

```typescript
// ✅ THE BASIC TYPES — MEMORIZE THESE

// ========== STRING ==========
let firstName: string = "Nilesh";
let lastName: string = 'Patel';
let greeting: string = `Hello, ${firstName}!`;  // Template literal

// ========== NUMBER ==========
let age: number = 22;
let price: number = 99.99;
let negative: number = -10;
let hex: number = 0xff;
let binary: number = 0b1010;
let infinity: number = Infinity;
let notANumber: number = NaN;  // NaN is type number!

// ========== BOOLEAN ==========
let isActive: boolean = true;
let isAdmin: boolean = false;

// ========== NULL & UNDEFINED ==========
let nothing: null = null;
let notDefined: undefined = undefined;

// ========== BIGINT ==========
let bigNumber: bigint = 100n;
let anotherBig: bigint = BigInt(100);

// ========== SYMBOL ==========
let uniqueKey: symbol = Symbol("key");


// ✅ TYPE ANNOTATION vs TYPE INFERENCE ⭐⭐⭐

// Type annotation (YOU specify the type):
let name: string = "Nilesh";        // Explicit
let age: number = 22;               // Explicit

// Type inference (TypeScript FIGURES OUT the type): ⭐
let name = "Nilesh";                // TypeScript infers: string
let age = 22;                       // TypeScript infers: number
let isActive = true;                // TypeScript infers: boolean
let items = [1, 2, 3];             // TypeScript infers: number[]

// RULE: Let TypeScript infer when possible!
// Only annotate when:
//   1. TypeScript can't infer (function parameters)
//   2. You want to be more specific
//   3. Variable initialized later

// ❌ Don't do this (unnecessary):
let name: string = "Nilesh";

// ✅ Do this (let TS infer):
let name = "Nilesh";

// ✅ But DO annotate function parameters:
function greet(name: string): string {
  return `Hello, ${name}!`;
}


// ✅ ANY — The Escape Hatch (AVOID!) ⚠️
let value: any = "hello";
value = 42;           // No error
value = true;         // No error
value = [];           // No error
value.foo.bar.baz;    // No error — but will crash at runtime!

// any turns OFF type checking — defeats the purpose of TypeScript!
// Only use when:
//   - Migrating JS to TS gradually
//   - Working with truly dynamic data (rare)

// ✅ UNKNOWN — Safe alternative to any ⭐
let value: unknown = "hello";
value = 42;           // ✅ Can assign anything

// But you MUST check the type before using:
// value.toUpperCase(); // ❌ Error: Object is of type 'unknown'

if (typeof value === "string") {
  value.toUpperCase(); // ✅ Works after type check
}

if (typeof value === "number") {
  value.toFixed(2);    // ✅ Works after type check
}

// RULE: Use unknown instead of any when you don't know the type ⭐


// ✅ VOID — Function returns nothing
function log(message: string): void {
  console.log(message);
  // No return value
}

// ✅ NEVER — Function never returns (throws or infinite loop)
function throwError(message: string): never {
  throw new Error(message);
  // Execution never reaches past this
}

function infiniteLoop(): never {
  while (true) {
    // Never ends
  }
}

// never is also used in exhaustive checks (we'll see later)
```

### 3.3 Arrays & Tuples

```typescript
// ✅ ARRAYS ⭐⭐

// Two syntaxes (both identical):
let numbers: number[] = [1, 2, 3, 4, 5];        // Preferred ⭐
let strings: Array<string> = ["a", "b", "c"];    // Generic syntax

// Type inference works:
let names = ["Alice", "Bob"];  // TypeScript infers: string[]

// Mixed arrays:
let mixed: (string | number)[] = [1, "two", 3, "four"];

// Array of objects:
let users: { name: string; age: number }[] = [
  { name: "Nilesh", age: 22 },
  { name: "Amit", age: 25 },
];

// Readonly array (cannot modify):
let readonlyNums: readonly number[] = [1, 2, 3];
// readonlyNums.push(4);  // ❌ Error: Property 'push' does not exist
// readonlyNums[0] = 10;  // ❌ Error: Index signature in type 'readonly number[]' only permits reading

const readonlyArr: ReadonlyArray<string> = ["a", "b"];

// ✅ TUPLES — Fixed-length arrays with specific types per position ⭐

// Regular array: any number of same type
let arr: number[] = [1, 2, 3, 4, 5, 6]; // any length

// Tuple: exact number of specific types
let tuple: [string, number] = ["Nilesh", 22];
//                                ↑ index 0 must be string
//                                         ↑ index 1 must be number

let tuple2: [string, number, boolean] = ["hello", 42, true];

// Accessing tuple elements:
let name: string = tuple[0];  // "Nilesh" — TypeScript knows it's string!
let age: number = tuple[1];   // 22 — TypeScript knows it's number!

// ❌ Errors:
// let t: [string, number] = [42, "hello"];  // Wrong order
// let t: [string, number] = ["hello"];      // Missing element
// let t: [string, number] = ["hello", 42, true]; // Extra element

// Named tuples (for clarity):
type UserTuple = [name: string, age: number, isActive: boolean];
let user: UserTuple = ["Nilesh", 22, true];

// Optional tuple elements:
type OptionalTuple = [string, number?];
let t1: OptionalTuple = ["hello"];
let t2: OptionalTuple = ["hello", 42];

// Rest elements in tuples:
type StringAndNumbers = [string, ...number[]];
let t: StringAndNumbers = ["hello", 1, 2, 3, 4, 5];

// Readonly tuple:
let point: readonly [number, number] = [10, 20];
// point[0] = 30;  // ❌ Cannot assign

// ✅ COMMON TUPLE USE CASES:
// React useState returns a tuple:
// const [count, setCount] = useState(0);
// → type is [number, Dispatch<SetStateAction<number>>]

// Coordinates:
type Coordinate = [x: number, y: number];
const point: Coordinate = [10, 20];

// RGB Color:
type RGB = [red: number, green: number, blue: number];
const white: RGB = [255, 255, 255];

// Key-value pair:
type Entry = [key: string, value: unknown];
const entry: Entry = ["name", "Nilesh"];
```

### 3.4 Objects & Type Aliases

```typescript
// ✅ OBJECT TYPES ⭐⭐⭐

// Inline object type:
let user: { name: string; age: number; email: string } = {
  name: "Nilesh",
  age: 22,
  email: "nilesh@gmail.com",
};

// ✅ TYPE ALIAS (Reusable type) ⭐⭐⭐
type User = {
  name: string;
  age: number;
  email: string;
};

let user1: User = { name: "Nilesh", age: 22, email: "n@gmail.com" };
let user2: User = { name: "Amit", age: 25, email: "a@gmail.com" };

// ✅ OPTIONAL PROPERTIES (?) ⭐
type Product = {
  id: number;
  name: string;
  price: number;
  description?: string;      // ← Optional (can be undefined)
  discount?: number;          // ← Optional
};

let product: Product = {
  id: 1,
  name: "Laptop",
  price: 999,
  // description and discount are optional
};

// ✅ READONLY PROPERTIES ⭐
type Config = {
  readonly apiUrl: string;    // ← Cannot be changed after creation
  readonly apiKey: string;
  timeout: number;            // ← Can be changed
};

let config: Config = {
  apiUrl: "https://api.example.com",
  apiKey: "secret123",
  timeout: 5000,
};

config.timeout = 10000;       // ✅ OK
// config.apiUrl = "new-url"; // ❌ Error: Cannot assign to 'apiUrl' because it is a read-only property

// ✅ INDEX SIGNATURES (Dynamic keys) ⭐
type Dictionary = {
  [key: string]: string;      // Any string key, string value
};

let colors: Dictionary = {
  red: "#ff0000",
  blue: "#0000ff",
  green: "#00ff00",
  // Can add any key!
};

type NumberMap = {
  [key: string]: number;
};

let scores: NumberMap = {
  math: 95,
  science: 88,
  english: 92,
};

// ✅ NESTED OBJECTS
type Address = {
  street: string;
  city: string;
  state: string;
  zipCode: string;
  country: string;
};

type UserProfile = {
  id: string;
  name: string;
  email: string;
  age: number;
  address: Address;                    // Nested object
  hobbies: string[];                   // Array of strings
  social?: {                           // Optional nested object
    twitter?: string;
    github?: string;
    linkedin?: string;
  };
  metadata: Record<string, unknown>;   // Dynamic key-value
};

let profile: UserProfile = {
  id: "1",
  name: "Nilesh",
  email: "n@gmail.com",
  age: 22,
  address: {
    street: "123 Main St",
    city: "Mumbai",
    state: "Maharashtra",
    zipCode: "400001",
    country: "India",
  },
  hobbies: ["coding", "reading"],
  social: {
    github: "nilesh",
  },
  metadata: {},
};


// ✅ TYPE ALIAS FOR PRIMITIVES, UNIONS, TUPLES
type ID = string | number;            // Union type
type Status = "active" | "inactive" | "pending";  // Literal union
type Point = [number, number];        // Tuple
type Callback = (data: string) => void;  // Function type
type Nullable<T> = T | null;          // Generic type alias

let userId: ID = "abc123";
userId = 456;  // Also valid

let status: Status = "active";
// status = "deleted"; // ❌ Error: not in the union
```

### 3.5 Enums

```typescript
// ✅ ENUMS — Named constants ⭐

// Numeric enum (default — values are 0, 1, 2...):
enum Direction {
  Up,        // 0
  Down,      // 1
  Left,      // 2
  Right,     // 3
}

let dir: Direction = Direction.Up;
console.log(dir);                    // 0
console.log(Direction[0]);           // "Up" (reverse mapping)

// Numeric enum with custom values:
enum StatusCode {
  OK = 200,
  Created = 201,
  BadRequest = 400,
  Unauthorized = 401,
  NotFound = 404,
  ServerError = 500,
}

let status: StatusCode = StatusCode.OK;

// String enum (RECOMMENDED) ⭐:
enum Color {
  Red = "RED",
  Green = "GREEN",
  Blue = "BLUE",
}

enum Role {
  Admin = "ADMIN",
  User = "USER",
  Moderator = "MODERATOR",
}

let userRole: Role = Role.Admin;
console.log(userRole); // "ADMIN"

// ✅ CONST ENUM (Inlined at compile time — better performance):
const enum Size {
  Small = "SM",
  Medium = "MD",
  Large = "LG",
}

let size = Size.Small; // Compiled to: let size = "SM"

// ✅ ENUM vs UNION TYPE — WHICH TO USE?

// Enum:
enum Status1 {
  Active = "ACTIVE",
  Inactive = "INACTIVE",
  Pending = "PENDING",
}

// Union type (MODERN ALTERNATIVE — often preferred) ⭐:
type Status2 = "ACTIVE" | "INACTIVE" | "PENDING";

// Union types are:
//   ✅ Simpler
//   ✅ No runtime overhead
//   ✅ Better tree-shaking
//   ✅ More flexible

// MY RECOMMENDATION:
// Use string literal unions for simple cases ⭐
// Use enums when you need reverse mapping or namespacing
```

### 3.6 Literal Types & Const Assertions

```typescript
// ✅ LITERAL TYPES — Exact values as types ⭐⭐

// String literal types:
type Direction = "up" | "down" | "left" | "right";

let dir: Direction = "up";     // ✅
// dir = "diagonal";           // ❌ Error

// Number literal types:
type DiceRoll = 1 | 2 | 3 | 4 | 5 | 6;

let roll: DiceRoll = 3;       // ✅
// roll = 7;                   // ❌ Error

// Boolean literal:
type True = true;
let isTrue: True = true;

// ✅ COMBINING LITERAL TYPES
type HttpMethod = "GET" | "POST" | "PUT" | "PATCH" | "DELETE";
type StatusCode = 200 | 201 | 400 | 401 | 403 | 404 | 500;

type ApiResponse = {
  method: HttpMethod;
  status: StatusCode;
  data: unknown;
};

// ✅ CONST ASSERTIONS ⭐⭐
// Makes TypeScript infer the most specific (literal) type

// Without as const:
let config = {
  url: "https://api.example.com",  // type: string
  method: "GET",                    // type: string
  retries: 3,                       // type: number
};

// With as const:
let config = {
  url: "https://api.example.com",  // type: "https://api.example.com" (literal)
  method: "GET",                    // type: "GET" (literal)
  retries: 3,                       // type: 3 (literal)
} as const;

// config.method = "POST";  // ❌ Cannot assign — it's readonly!

// Great for:
const COLORS = ["red", "green", "blue"] as const;
// type: readonly ["red", "green", "blue"]

type Color = typeof COLORS[number]; // "red" | "green" | "blue" ⭐

const ROUTES = {
  HOME: "/",
  ABOUT: "/about",
  BLOG: "/blog",
  CONTACT: "/contact",
} as const;

type Route = typeof ROUTES[keyof typeof ROUTES];
// "/" | "/about" | "/blog" | "/contact"
```

---

## PART 4: INTERMEDIATE TYPES (Week 2)

### 4.1 Union Types ⭐⭐⭐

```typescript
// ✅ UNION TYPES — Value can be ONE of several types

type StringOrNumber = string | number;

let id: StringOrNumber = "abc";
id = 123;   // Also valid

// ✅ COMMON UNION PATTERNS:

// API response:
type ApiResult = 
  | { status: "success"; data: User[] }
  | { status: "error"; message: string }
  | { status: "loading" };

// Function parameter:
function formatId(id: string | number): string {
  if (typeof id === "string") {
    return id.toUpperCase();    // ✅ TypeScript knows it's string here
  }
  return id.toString();          // ✅ TypeScript knows it's number here
}

// Event type:
type Event = 
  | { type: "click"; x: number; y: number }
  | { type: "keypress"; key: string }
  | { type: "scroll"; position: number };

// Nullable values:
type MaybeString = string | null;
type MaybeUser = User | null | undefined;
```

### 4.2 Intersection Types

```typescript
// ✅ INTERSECTION TYPES (&) — Combine multiple types ⭐

type HasName = {
  name: string;
};

type HasAge = {
  age: number;
};

type HasEmail = {
  email: string;
};

// Intersection: must have ALL properties
type Person = HasName & HasAge & HasEmail;

let person: Person = {
  name: "Nilesh",   // ← from HasName
  age: 22,          // ← from HasAge
  email: "n@g.com", // ← from HasEmail
};

// ✅ PRACTICAL EXAMPLE — Extending types:
type BaseEntity = {
  id: string;
  createdAt: Date;
  updatedAt: Date;
};

type User = BaseEntity & {
  name: string;
  email: string;
  role: "admin" | "user";
};

type Post = BaseEntity & {
  title: string;
  content: string;
  authorId: string;
  published: boolean;
};

// User has: id, createdAt, updatedAt, name, email, role
// Post has: id, createdAt, updatedAt, title, content, authorId, published

// ✅ UNION vs INTERSECTION:
// Union (|): Value is ONE of the types (OR)
// Intersection (&): Value has ALL of the types (AND)

type A = { foo: string };
type B = { bar: number };

type AorB = A | B;     // { foo: string } OR { bar: number }
type AandB = A & B;    // { foo: string, bar: number } — must have BOTH
```

### 4.3 Type Narrowing ⭐⭐⭐ (THE Most Important Skill)

```typescript
// ✅ TYPE NARROWING — Telling TypeScript which specific type you're working with
// This is what makes TypeScript PRACTICAL

// 1. typeof (for primitives) ⭐⭐⭐
function processValue(value: string | number | boolean) {
  if (typeof value === "string") {
    // TypeScript KNOWS value is string here
    console.log(value.toUpperCase());     // ✅ String methods available
    console.log(value.length);            // ✅
  } else if (typeof value === "number") {
    // TypeScript KNOWS value is number here
    console.log(value.toFixed(2));        // ✅ Number methods available
    console.log(Math.round(value));       // ✅
  } else {
    // TypeScript KNOWS value is boolean here
    console.log(value ? "yes" : "no");    // ✅
  }
}

// 2. Truthiness narrowing ⭐
function printName(name: string | null | undefined) {
  if (name) {
    // TypeScript knows name is string here (not null/undefined)
    console.log(name.toUpperCase());
  } else {
    console.log("No name provided");
  }
}

// 3. Equality narrowing ⭐
function compare(a: string | number, b: string | boolean) {
  if (a === b) {
    // a and b must BOTH be string (only common type)
    console.log(a.toUpperCase()); // ✅
    console.log(b.toUpperCase()); // ✅
  }
}

// 4. in operator (for objects) ⭐⭐
type Fish = { swim: () => void };
type Bird = { fly: () => void };
type Dog = { bark: () => void };

function move(animal: Fish | Bird | Dog) {
  if ("swim" in animal) {
    animal.swim();    // TypeScript knows: Fish
  } else if ("fly" in animal) {
    animal.fly();     // TypeScript knows: Bird
  } else {
    animal.bark();    // TypeScript knows: Dog
  }
}

// 5. instanceof (for classes) ⭐⭐
class HttpError extends Error {
  statusCode: number;
  constructor(message: string, statusCode: number) {
    super(message);
    this.statusCode = statusCode;
  }
}

class ValidationError extends Error {
  fields: string[];
  constructor(message: string, fields: string[]) {
    super(message);
    this.fields = fields;
  }
}

function handleError(error: Error) {
  if (error instanceof HttpError) {
    console.log(`HTTP ${error.statusCode}: ${error.message}`);
  } else if (error instanceof ValidationError) {
    console.log(`Validation: ${error.fields.join(", ")}`);
  } else {
    console.log(`Unknown error: ${error.message}`);
  }
}

// 6. DISCRIMINATED UNIONS ⭐⭐⭐ (Most powerful pattern!)
type Shape =
  | { kind: "circle"; radius: number }
  | { kind: "rectangle"; width: number; height: number }
  | { kind: "triangle"; base: number; height: number };

function getArea(shape: Shape): number {
  switch (shape.kind) {
    case "circle":
      return Math.PI * shape.radius ** 2;
      // TypeScript knows: { kind: "circle"; radius: number }
      
    case "rectangle":
      return shape.width * shape.height;
      // TypeScript knows: { kind: "rectangle"; width: number; height: number }
      
    case "triangle":
      return (shape.base * shape.height) / 2;
      // TypeScript knows: { kind: "triangle"; base: number; height: number }
  }
}

// Exhaustive check pattern ⭐:
function getArea(shape: Shape): number {
  switch (shape.kind) {
    case "circle":
      return Math.PI * shape.radius ** 2;
    case "rectangle":
      return shape.width * shape.height;
    case "triangle":
      return (shape.base * shape.height) / 2;
    default:
      // This ensures ALL cases are handled
      const _exhaustive: never = shape;
      throw new Error(`Unknown shape: ${_exhaustive}`);
  }
}
// If you add a new shape to the union but forget to handle it,
// TypeScript will show an error here! ⭐

// ✅ REAL-WORLD DISCRIMINATED UNION — API Response:
type ApiResponse<T> =
  | { status: "idle" }
  | { status: "loading" }
  | { status: "success"; data: T }
  | { status: "error"; error: string };

function renderUsers(response: ApiResponse<User[]>) {
  switch (response.status) {
    case "idle":
      return "Click to load";
    case "loading":
      return "Loading...";
    case "success":
      return response.data.map(u => u.name).join(", ");
      // TypeScript knows data exists here! ⭐
    case "error":
      return `Error: ${response.error}`;
      // TypeScript knows error exists here! ⭐
  }
}

// 7. TYPE PREDICATES (Custom type guards) ⭐⭐
function isString(value: unknown): value is string {
  return typeof value === "string";
}

function isUser(value: unknown): value is User {
  return (
    typeof value === "object" &&
    value !== null &&
    "name" in value &&
    "email" in value
  );
}

function processData(data: unknown) {
  if (isString(data)) {
    console.log(data.toUpperCase()); // ✅ TypeScript knows it's string
  }
  
  if (isUser(data)) {
    console.log(data.name);  // ✅ TypeScript knows it's User
    console.log(data.email); // ✅
  }
}

// 8. ASSERTION FUNCTIONS ⭐
function assertIsString(value: unknown): asserts value is string {
  if (typeof value !== "string") {
    throw new Error(`Expected string, got ${typeof value}`);
  }
}

function processInput(input: unknown) {
  assertIsString(input);
  // After this line, TypeScript knows input is string!
  console.log(input.toUpperCase()); // ✅
}

// assertNonNull:
function assertNonNull<T>(value: T | null | undefined): asserts value is T {
  if (value === null || value === undefined) {
    throw new Error("Value is null or undefined");
  }
}
```

### 4.4 Type Assertions (Type Casting)

```typescript
// ✅ TYPE ASSERTIONS — Tell TypeScript "trust me, I know the type" ⭐

// as syntax (preferred):
let value: unknown = "hello world";
let length: number = (value as string).length;

// Angle bracket syntax (doesn't work in JSX):
let length2: number = (<string>value).length;

// ✅ COMMON USE CASES:

// 1. DOM elements:
const input = document.getElementById("myInput") as HTMLInputElement;
input.value = "Hello"; // TypeScript knows it's an input element

const canvas = document.querySelector("canvas") as HTMLCanvasElement;
const ctx = canvas.getContext("2d"); // TypeScript knows ctx methods

// 2. API response:
const response = await fetch("/api/users");
const data = (await response.json()) as User[];

// 3. Event handling:
function handleChange(event: Event) {
  const target = event.target as HTMLInputElement;
  console.log(target.value);
}

// ✅ NON-NULL ASSERTION (!) — "I know this isn't null" ⚠️
// Use sparingly!
const element = document.getElementById("app")!; // Asserts non-null
// Equivalent to:
const element2 = document.getElementById("app") as HTMLElement;

// ⚠️ WARNING: Type assertions DON'T validate data!
// They just tell TypeScript to trust you.
// If you're wrong, you'll get runtime errors.

// ✅ BETTER: Use type guards instead of assertions when possible
const element = document.getElementById("app");
if (element) {
  // TypeScript knows element is HTMLElement here — SAFER!
  element.style.display = "none";
}

// ✅ CONST ASSERTION (as const) — already covered
const config = { url: "/api", method: "GET" } as const;

// ✅ SATISFIES OPERATOR (TypeScript 4.9+) ⭐⭐
// Validates type WITHOUT widening — best of both worlds!

type Colors = Record<string, string | string[]>;

// as const loses the type:
const colors1 = { red: "#ff0000" } as const;
// type: { readonly red: "#ff0000" } — lost Colors type info

// Type annotation loses specificity:
const colors2: Colors = { red: "#ff0000" };
// colors2.red — type is string | string[], not "#ff0000"

// satisfies gives you BOTH! ⭐
const colors3 = {
  red: "#ff0000",
  blue: "#0000ff",
  gradient: ["#ff0000", "#0000ff"],
} satisfies Colors;

colors3.red;       // type: string (not string | string[])
colors3.gradient;  // type: string[] (not string | string[])
// TypeScript knows exact types AND validates against Colors!
```

---

## PART 5: FUNCTIONS & GENERICS (Week 3)

### 5.1 Function Types ⭐⭐⭐

```typescript
// ✅ FUNCTION TYPE ANNOTATIONS

// Parameter types + return type:
function add(a: number, b: number): number {
  return a + b;
}

// Arrow function:
const multiply = (a: number, b: number): number => a * b;

// Return type inference (TypeScript figures it out):
const subtract = (a: number, b: number) => a - b;
// TypeScript infers return type: number

// ✅ OPTIONAL PARAMETERS ⭐
function greet(name: string, greeting?: string): string {
  return `${greeting || "Hello"}, ${name}!`;
}

greet("Nilesh");           // ✅ "Hello, Nilesh!"
greet("Nilesh", "Hey");    // ✅ "Hey, Nilesh!"

// ✅ DEFAULT PARAMETERS ⭐
function createUser(
  name: string,
  role: string = "user",
  isActive: boolean = true
): User {
  return { name, role, isActive };
}

createUser("Nilesh");                    // role = "user", isActive = true
createUser("Nilesh", "admin");           // role = "admin", isActive = true
createUser("Nilesh", "admin", false);    // role = "admin", isActive = false

// ✅ REST PARAMETERS ⭐
function sum(...numbers: number[]): number {
  return numbers.reduce((acc, n) => acc + n, 0);
}

sum(1, 2, 3);        // 6
sum(1, 2, 3, 4, 5);  // 15

function buildPath(base: string, ...segments: string[]): string {
  return [base, ...segments].join("/");
}

buildPath("/api", "users", "123", "posts");
// "/api/users/123/posts"

// ✅ FUNCTION TYPE ALIASES ⭐⭐
type MathFn = (a: number, b: number) => number;

const add: MathFn = (a, b) => a + b;
const subtract: MathFn = (a, b) => a - b;
const multiply: MathFn = (a, b) => a * b;

// Callback type:
type Callback = (error: Error | null, data?: string) => void;

function fetchData(url: string, callback: Callback): void {
  try {
    const data = "some data";
    callback(null, data);
  } catch (error) {
    callback(error as Error);
  }
}

// ✅ FUNCTION OVERLOADS ⭐⭐
// Same function name, different parameter/return types

// Overload signatures (what users see):
function createElement(tag: "a"): HTMLAnchorElement;
function createElement(tag: "canvas"): HTMLCanvasElement;
function createElement(tag: "input"): HTMLInputElement;
function createElement(tag: string): HTMLElement;

// Implementation (must handle all overloads):
function createElement(tag: string): HTMLElement {
  return document.createElement(tag);
}

const anchor = createElement("a");     // TypeScript knows: HTMLAnchorElement
const canvas = createElement("canvas"); // TypeScript knows: HTMLCanvasElement
const input = createElement("input");   // TypeScript knows: HTMLInputElement
const div = createElement("div");       // TypeScript knows: HTMLElement

// ✅ PRACTICAL OVERLOAD — Parse function:
function parse(value: string): string[];
function parse(value: number): number;
function parse(value: string | number): string[] | number {
  if (typeof value === "string") {
    return value.split(",");
  }
  return value * 2;
}

const result1 = parse("a,b,c"); // type: string[]
const result2 = parse(42);       // type: number

// ✅ VOID vs UNDEFINED
// void = function doesn't return anything meaningful
// undefined = function explicitly returns undefined

function logMessage(msg: string): void {
  console.log(msg);
  // No return statement — void
}

function getUndefined(): undefined {
  return undefined; // Must explicitly return undefined
}

// ✅ THIS PARAMETER ⭐
// Specify the type of 'this' inside a function:
function getFullName(this: { firstName: string; lastName: string }): string {
  return `${this.firstName} ${this.lastName}`;
}

const user = {
  firstName: "Nilesh",
  lastName: "Patel",
  getFullName,
};

user.getFullName(); // ✅ "Nilesh Patel"
```

### 5.2 Generics ⭐⭐⭐ (THE Most Important TypeScript Feature)

```typescript
// ✅ WHAT ARE GENERICS?
// Generics let you write REUSABLE code that works with ANY type
// Think of them as "type variables" or "type parameters"

// ❌ WITHOUT GENERICS — You'd need separate functions:
function getFirstString(arr: string[]): string { return arr[0]; }
function getFirstNumber(arr: number[]): number { return arr[0]; }
function getFirstUser(arr: User[]): User { return arr[0]; }
// This is terrible! Same logic, repeated for each type.

// ✅ WITH GENERICS — One function for ALL types:
function getFirst<T>(arr: T[]): T {
  return arr[0];
}

getFirst<string>(["a", "b", "c"]);      // returns: string — "a"
getFirst<number>([1, 2, 3]);            // returns: number — 1
getFirst([true, false]);                 // returns: boolean (TypeScript infers T = boolean)
getFirst<User>([user1, user2]);          // returns: User

// T is a TYPE VARIABLE — it captures whatever type you pass
// Convention: T (Type), K (Key), V (Value), E (Element), R (Return)


// ✅ GENERIC FUNCTIONS — COMMON PATTERNS ⭐⭐⭐

// Identity function (simplest generic):
function identity<T>(value: T): T {
  return value;
}

identity<string>("hello");  // returns: string
identity(42);               // returns: number (inferred)

// Pair function (multiple type parameters):
function makePair<K, V>(key: K, value: V): [K, V] {
  return [key, value];
}

makePair("name", "Nilesh");   // [string, string]
makePair("age", 22);          // [string, number]
makePair(1, true);            // [number, boolean]

// Array wrapper:
function wrapInArray<T>(value: T): T[] {
  return [value];
}

wrapInArray("hello");  // string[]
wrapInArray(42);       // number[]

// Map function:
function mapArray<T, U>(arr: T[], fn: (item: T) => U): U[] {
  return arr.map(fn);
}

mapArray([1, 2, 3], (n) => n.toString());      // string[]
mapArray(["a", "b"], (s) => s.length);          // number[]
mapArray(users, (user) => user.name);           // string[]


// ✅ GENERIC CONSTRAINTS (extends) ⭐⭐⭐
// Limit what types T can be

// Without constraint:
function getLength<T>(value: T): number {
  // return value.length; // ❌ Error: T might not have .length
}

// With constraint — T MUST have a .length property:
function getLength<T extends { length: number }>(value: T): number {
  return value.length;  // ✅ Now TypeScript knows .length exists
}

getLength("hello");           // ✅ string has .length
getLength([1, 2, 3]);         // ✅ array has .length
getLength({ length: 10 });    // ✅ object has .length
// getLength(42);             // ❌ number doesn't have .length

// Constrain to specific types:
function merge<T extends object, U extends object>(a: T, b: U): T & U {
  return { ...a, ...b };
}

merge({ name: "Nilesh" }, { age: 22 });
// Result type: { name: string } & { age: number }

// ✅ keyof CONSTRAINT ⭐⭐⭐
// T extends keyof — T must be a key of some object

function getProperty<T, K extends keyof T>(obj: T, key: K): T[K] {
  return obj[key];
}

const user = { name: "Nilesh", age: 22, email: "n@g.com" };

getProperty(user, "name");    // ✅ returns: string
getProperty(user, "age");     // ✅ returns: number
// getProperty(user, "foo");  // ❌ Error: "foo" is not a key of user


// ✅ GENERIC INTERFACES & TYPE ALIASES ⭐⭐⭐

// Generic interface:
interface ApiResponse<T> {
  data: T;
  status: number;
  message: string;
  timestamp: Date;
}

let userResponse: ApiResponse<User> = {
  data: { name: "Nilesh", email: "n@g.com" },
  status: 200,
  message: "Success",
  timestamp: new Date(),
};

let postsResponse: ApiResponse<Post[]> = {
  data: [{ title: "Hello", content: "World" }],
  status: 200,
  message: "Success",
  timestamp: new Date(),
};

// Generic type alias:
type Result<T> = 
  | { success: true; data: T }
  | { success: false; error: string };

let userResult: Result<User> = { success: true, data: user };
let errorResult: Result<never> = { success: false, error: "Not found" };

// Paginated response:
type PaginatedResponse<T> = {
  data: T[];
  pagination: {
    page: number;
    limit: number;
    total: number;
    totalPages: number;
  };
};

type UserListResponse = PaginatedResponse<User>;
type PostListResponse = PaginatedResponse<Post>;


// ✅ GENERIC CLASSES ⭐⭐

class Stack<T> {
  private items: T[] = [];

  push(item: T): void {
    this.items.push(item);
  }

  pop(): T | undefined {
    return this.items.pop();
  }

  peek(): T | undefined {
    return this.items[this.items.length - 1];
  }

  isEmpty(): boolean {
    return this.items.length === 0;
  }

  size(): number {
    return this.items.length;
  }
}

const numberStack = new Stack<number>();
numberStack.push(1);
numberStack.push(2);
numberStack.pop();  // returns: number | undefined

const stringStack = new Stack<string>();
stringStack.push("hello");
stringStack.push("world");


// ✅ DEFAULT GENERIC TYPES ⭐
interface EventMap {
  click: { x: number; y: number };
  keypress: { key: string };
  scroll: { position: number };
}

function on<E extends keyof EventMap = "click">(
  event: E,
  callback: (data: EventMap[E]) => void
): void {
  // ...
}

// With default:
type Container<T = string> = {
  value: T;
};

let c1: Container = { value: "hello" };          // T defaults to string
let c2: Container<number> = { value: 42 };       // T is number


// ✅ GENERIC UTILITY PATTERN — API Service ⭐⭐⭐
class ApiService {
  private baseUrl: string;

  constructor(baseUrl: string) {
    this.baseUrl = baseUrl;
  }

  async get<T>(endpoint: string): Promise<T> {
    const response = await fetch(`${this.baseUrl}${endpoint}`);
    if (!response.ok) throw new Error(`HTTP ${response.status}`);
    return response.json() as Promise<T>;
  }

  async post<T, B>(endpoint: string, body: B): Promise<T> {
    const response = await fetch(`${this.baseUrl}${endpoint}`, {
      method: "POST",
      headers: { "Content-Type": "application/json" },
      body: JSON.stringify(body),
    });
    if (!response.ok) throw new Error(`HTTP ${response.status}`);
    return response.json() as Promise<T>;
  }

  async put<T, B>(endpoint: string, body: B): Promise<T> {
    const response = await fetch(`${this.baseUrl}${endpoint}`, {
      method: "PUT",
      headers: { "Content-Type": "application/json" },
      body: JSON.stringify(body),
    });
    return response.json() as Promise<T>;
  }

  async delete<T>(endpoint: string): Promise<T> {
    const response = await fetch(`${this.baseUrl}${endpoint}`, {
      method: "DELETE",
    });
    return response.json() as Promise<T>;
  }
}

// Usage:
const api = new ApiService("https://api.example.com");

const users = await api.get<User[]>("/users");           // User[]
const user = await api.get<User>("/users/1");             // User
const newUser = await api.post<User, CreateUserDTO>("/users", { 
  name: "Nilesh", 
  email: "n@g.com" 
});
```

---

## PART 6: INTERFACES, TYPES & OOP (Week 4)

### 6.1 Interfaces vs Type Aliases ⭐⭐⭐

```typescript
// ✅ INTERFACE — Describes the shape of an object ⭐

interface User {
  id: string;
  name: string;
  email: string;
  age?: number;                    // Optional
  readonly createdAt: Date;        // Readonly
}

// ✅ TYPE ALIAS — Can describe ANY type ⭐

type User = {
  id: string;
  name: string;
  email: string;
};

// ✅ KEY DIFFERENCES:

// 1. INTERFACE can be extended (inheritance):
interface Animal {
  name: string;
}

interface Dog extends Animal {
  breed: string;
  bark(): void;
}

// TYPE uses intersection (&):
type Animal = {
  name: string;
};

type Dog = Animal & {
  breed: string;
  bark(): void;
};

// 2. INTERFACE supports declaration merging:
interface Window {
  title: string;
}

interface Window {
  customProp: string;
}

// Window now has BOTH title and customProp!
// (Used for extending third-party types)

// TYPE cannot merge — ❌ Duplicate identifier error

// 3. TYPE can do things interface CANNOT:
type ID = string | number;                    // Union ← Interface CAN'T
type Status = "active" | "inactive";          // Literal union ← Interface CAN'T
type Pair = [string, number];                 // Tuple ← Interface CAN'T
type Callback = (data: string) => void;       // Function type ← Interface CAN'T

// ✅ WHEN TO USE WHICH? ⭐⭐⭐
// 
// USE INTERFACE WHEN:
//   → Defining object shapes (classes, APIs)
//   → You need declaration merging
//   → Working with OOP/classes
//   → Public API definitions
//
// USE TYPE WHEN:
//   → Unions, intersections, tuples
//   → Complex type transformations
//   → Function types
//   → Utility types
//   → Discriminated unions
//
// MY RECOMMENDATION:
//   → Use TYPE for everything ⭐ (more flexible)
//   → Use INTERFACE only when you need merging or class implementation
//   → Be consistent in your project!


// ✅ INTERFACE EXTENDING MULTIPLE INTERFACES:
interface Timestamps {
  createdAt: Date;
  updatedAt: Date;
}

interface SoftDeletable {
  deletedAt: Date | null;
  isDeleted: boolean;
}

interface Identifiable {
  id: string;
}

// Extend multiple:
interface BaseEntity extends Identifiable, Timestamps, SoftDeletable {}

interface User extends BaseEntity {
  name: string;
  email: string;
}

// User has: id, createdAt, updatedAt, deletedAt, isDeleted, name, email


// ✅ INTERFACE FOR FUNCTIONS:
interface SearchFunction {
  (query: string, limit?: number): Promise<Result[]>;
}

const search: SearchFunction = async (query, limit = 10) => {
  return [];
};

// ✅ INTERFACE FOR CLASSES:
interface Repository<T> {
  findAll(): Promise<T[]>;
  findById(id: string): Promise<T | null>;
  create(data: Partial<T>): Promise<T>;
  update(id: string, data: Partial<T>): Promise<T>;
  delete(id: string): Promise<void>;
}

class UserRepository implements Repository<User> {
  async findAll(): Promise<User[]> { /* ... */ return []; }
  async findById(id: string): Promise<User | null> { /* ... */ return null; }
  async create(data: Partial<User>): Promise<User> { /* ... */ return {} as User; }
  async update(id: string, data: Partial<User>): Promise<User> { /* ... */ return {} as User; }
  async delete(id: string): Promise<void> { /* ... */ }
}
```

### 6.2 OOP in TypeScript

```typescript
// ✅ CLASSES ⭐⭐

class User {
  // Properties with access modifiers:
  public name: string;            // Accessible everywhere (default)
  private password: string;       // Only inside this class
  protected role: string;         // Inside this class + subclasses
  readonly id: string;            // Cannot be changed after construction

  // Static property:
  static userCount: number = 0;

  constructor(name: string, password: string, role: string = "user") {
    this.id = crypto.randomUUID();
    this.name = name;
    this.password = password;
    this.role = role;
    User.userCount++;
  }

  // Public method:
  greet(): string {
    return `Hello, I'm ${this.name}`;
  }

  // Private method:
  private hashPassword(password: string): string {
    return `hashed_${password}`;
  }

  // Getter:
  get displayName(): string {
    return this.name.toUpperCase();
  }

  // Setter:
  set displayName(value: string) {
    this.name = value.trim();
  }

  // Static method:
  static getCount(): number {
    return User.userCount;
  }
}

const user = new User("Nilesh", "pass123");
console.log(user.name);          // ✅ "Nilesh" (public)
// console.log(user.password);   // ❌ Error (private)
console.log(user.displayName);   // ✅ "NILESH" (getter)
console.log(User.getCount());    // ✅ 1 (static)

// ✅ SHORTHAND CONSTRUCTOR ⭐⭐ (Much cleaner!)
class Product {
  constructor(
    public readonly id: string,
    public name: string,
    public price: number,
    private cost: number,
    public description?: string
  ) {}
  // Properties are automatically created and assigned!
  // No need for this.id = id, etc.

  get profit(): number {
    return this.price - this.cost;
  }
}

// ✅ INHERITANCE ⭐
class Animal {
  constructor(public name: string, protected sound: string) {}
  
  makeSound(): string {
    return `${this.name} says ${this.sound}`;
  }
}

class Dog extends Animal {
  constructor(name: string, public breed: string) {
    super(name, "Woof!");  // Call parent constructor
  }
  
  fetch(item: string): string {
    return `${this.name} fetches ${item}`;
  }
  
  // Override parent method:
  override makeSound(): string {
    return `${this.name} barks: ${this.sound}!`;
  }
}

const dog = new Dog("Rex", "Labrador");
dog.makeSound();  // "Rex barks: Woof!!"
dog.fetch("ball"); // "Rex fetches ball"

// ✅ ABSTRACT CLASSES (Cannot be instantiated, must be extended) ⭐
abstract class Shape {
  abstract getArea(): number;      // MUST be implemented by subclass
  abstract getPerimeter(): number; // MUST be implemented by subclass
  
  // Can have implemented methods:
  describe(): string {
    return `Shape with area ${this.getArea().toFixed(2)}`;
  }
}

class Circle extends Shape {
  constructor(public radius: number) {
    super();
  }
  
  getArea(): number {
    return Math.PI * this.radius ** 2;
  }
  
  getPerimeter(): number {
    return 2 * Math.PI * this.radius;
  }
}

class Rectangle extends Shape {
  constructor(public width: number, public height: number) {
    super();
  }
  
  getArea(): number {
    return this.width * this.height;
  }
  
  getPerimeter(): number {
    return 2 * (this.width + this.height);
  }
}

// const shape = new Shape();     // ❌ Cannot instantiate abstract class
const circle = new Circle(5);     // ✅
const rect = new Rectangle(4, 6); // ✅

// ✅ IMPLEMENTING INTERFACES ⭐⭐
interface Serializable {
  serialize(): string;
  deserialize(data: string): void;
}

interface Printable {
  print(): void;
}

class Document implements Serializable, Printable {
  constructor(public title: string, public content: string) {}
  
  serialize(): string {
    return JSON.stringify({ title: this.title, content: this.content });
  }
  
  deserialize(data: string): void {
    const parsed = JSON.parse(data);
    this.title = parsed.title;
    this.content = parsed.content;
  }
  
  print(): void {
    console.log(`=== ${this.title} ===\n${this.content}`);
  }
}
```

---

## PART 7: ADVANCED TYPES (Week 5)

### 7.1 Utility Types ⭐⭐⭐ (MUST KNOW — Used Everywhere!)

```typescript
// ✅ BUILT-IN UTILITY TYPES — TypeScript provides these!

type User = {
  id: string;
  name: string;
  email: string;
  age: number;
  role: "admin" | "user";
  createdAt: Date;
};

// ✅ Partial<T> — All properties become optional ⭐⭐⭐
type UpdateUser = Partial<User>;
// Result:
// {
//   id?: string;
//   name?: string;
//   email?: string;
//   age?: number;
//   role?: "admin" | "user";
//   createdAt?: Date;
// }

function updateUser(id: string, updates: Partial<User>): User {
  // Can pass any subset of User properties
  return { ...existingUser, ...updates };
}

updateUser("1", { name: "New Name" });           // ✅ Only name
updateUser("1", { name: "New", age: 23 });       // ✅ name + age
updateUser("1", {});                              // ✅ Nothing (all optional)


// ✅ Required<T> — All properties become required ⭐
type RequiredUser = Required<User>;
// All optional properties (?) are now required


// ✅ Readonly<T> — All properties become readonly ⭐⭐
type ReadonlyUser = Readonly<User>;
// Cannot modify any property

const user: ReadonlyUser = { id: "1", name: "Nilesh", /* ... */ };
// user.name = "New"; // ❌ Error: Cannot assign to 'name'

// Deep readonly:
type DeepReadonly<T> = {
  readonly [K in keyof T]: T[K] extends object ? DeepReadonly<T[K]> : T[K];
};


// ✅ Pick<T, Keys> — Select specific properties ⭐⭐⭐
type UserPreview = Pick<User, "id" | "name" | "email">;
// Result:
// {
//   id: string;
//   name: string;
//   email: string;
// }

type UserCredentials = Pick<User, "email" | "role">;
// { email: string; role: "admin" | "user" }


// ✅ Omit<T, Keys> — Remove specific properties ⭐⭐⭐
type CreateUserInput = Omit<User, "id" | "createdAt">;
// Result:
// {
//   name: string;
//   email: string;
//   age: number;
//   role: "admin" | "user";
// }

type PublicUser = Omit<User, "email" | "role">;
// { id: string; name: string; age: number; createdAt: Date }


// ✅ Record<Keys, Type> — Create object type with specific keys ⭐⭐⭐
type UserRoles = Record<string, string>;
// { [key: string]: string }

type StatusMap = Record<"active" | "inactive" | "pending", number>;
// { active: number; inactive: number; pending: number }

type UserScores = Record<string, number>;
const scores: UserScores = {
  math: 95,
  science: 88,
  english: 92,
};

// Record with complex value:
type PageConfig = Record<string, {
  title: string;
  description: string;
  isProtected: boolean;
}>;


// ✅ Exclude<Union, ExcludedMembers> — Remove from union ⭐⭐
type AllStatus = "active" | "inactive" | "pending" | "deleted";
type ActiveStatus = Exclude<AllStatus, "deleted">;
// Result: "active" | "inactive" | "pending"

type NonNullString = Exclude<string | null | undefined, null | undefined>;
// Result: string


// ✅ Extract<Union, ExtractedMembers> — Keep from union ⭐⭐
type StringOrNumber = Extract<string | number | boolean, string | number>;
// Result: string | number

type ActiveStatus2 = Extract<AllStatus, "active" | "pending">;
// Result: "active" | "pending"


// ✅ NonNullable<T> — Remove null and undefined ⭐⭐
type MaybeString = string | null | undefined;
type DefiniteString = NonNullable<MaybeString>;
// Result: string


// ✅ ReturnType<T> — Get return type of a function ⭐⭐
function getUser() {
  return { id: "1", name: "Nilesh", age: 22 };
}

type UserReturn = ReturnType<typeof getUser>;
// Result: { id: string; name: string; age: number }

// Great for inferring types from functions you don't control:
type FetchReturn = ReturnType<typeof fetch>;
// Result: Promise<Response>


// ✅ Parameters<T> — Get parameter types of a function ⭐
function createUser(name: string, age: number, email: string) { /* ... */ }

type CreateUserParams = Parameters<typeof createUser>;
// Result: [string, number, string]

type FirstParam = Parameters<typeof createUser>[0]; // string


// ✅ Awaited<T> — Unwrap Promise type ⭐
type PromiseString = Promise<string>;
type ResolvedType = Awaited<PromiseString>;
// Result: string

type NestedPromise = Promise<Promise<number>>;
type ResolvedNested = Awaited<NestedPromise>;
// Result: number

// Great for async function return types:
async function fetchUsers(): Promise<User[]> { return []; }
type FetchedUsers = Awaited<ReturnType<typeof fetchUsers>>;
// Result: User[]


// ✅ ConstructorParameters<T> — Get constructor params ⭐
class MyClass {
  constructor(public name: string, public age: number) {}
}

type MyClassParams = ConstructorParameters<typeof MyClass>;
// Result: [string, number]


// ✅ InstanceType<T> — Get instance type from class ⭐
type MyInstance = InstanceType<typeof MyClass>;
// Result: MyClass
```

### 7.2 Mapped Types ⭐⭐

```typescript
// ✅ MAPPED TYPES — Transform types programmatically

// Basic mapped type:
type Stringify<T> = {
  [K in keyof T]: string;
};

type User = { name: string; age: number; isActive: boolean };
type StringUser = Stringify<User>;
// Result: { name: string; age: string; isActive: string }

// Make all properties optional:
type MyPartial<T> = {
  [K in keyof T]?: T[K];
};
// This is how Partial<T> works internally!

// Make all properties readonly:
type MyReadonly<T> = {
  readonly [K in keyof T]: T[K];
};
// This is how Readonly<T> works internally!

// Make all properties nullable:
type Nullable<T> = {
  [K in keyof T]: T[K] | null;
};

type NullableUser = Nullable<User>;
// { name: string | null; age: number | null; isActive: boolean | null }

// ✅ KEY REMAPPING (as clause) ⭐
type Getters<T> = {
  [K in keyof T as `get${Capitalize<string & K>}`]: () => T[K];
};

type UserGetters = Getters<User>;
// {
//   getName: () => string;
//   getAge: () => number;
//   getIsActive: () => boolean;
// }

// Event handlers:
type EventHandlers<T> = {
  [K in keyof T as `on${Capitalize<string & K>}Change`]: (value: T[K]) => void;
};

type UserHandlers = EventHandlers<User>;
// {
//   onNameChange: (value: string) => void;
//   onAgeChange: (value: number) => void;
//   onIsActiveChange: (value: boolean) => void;
// }

// Remove specific keys:
type RemoveKind<T> = {
  [K in keyof T as Exclude<K, "kind">]: T[K];
};
```

### 7.3 Conditional Types ⭐⭐

```typescript
// ✅ CONDITIONAL TYPES — Types that depend on conditions
// Syntax: T extends U ? TrueType : FalseType

// Basic:
type IsString<T> = T extends string ? true : false;

type A = IsString<string>;   // true
type B = IsString<number>;   // false
type C = IsString<"hello">;  // true

// Practical examples:
type IsArray<T> = T extends any[] ? true : false;

type D = IsArray<string[]>;  // true
type E = IsArray<number>;    // false

// Extract element type from array:
type ElementType<T> = T extends (infer E)[] ? E : never;

type F = ElementType<string[]>;  // string
type G = ElementType<number[]>;  // number
type H = ElementType<User[]>;   // User

// ✅ infer KEYWORD — Extract types from complex structures ⭐⭐

// Get return type:
type MyReturnType<T> = T extends (...args: any[]) => infer R ? R : never;

type FnReturn = MyReturnType<() => string>;  // string
type FnReturn2 = MyReturnType<(x: number) => boolean>;  // boolean

// Get Promise inner type:
type UnwrapPromise<T> = T extends Promise<infer U> ? U : T;

type I = UnwrapPromise<Promise<string>>;  // string
type J = UnwrapPromise<number>;           // number (not a promise, returns as-is)

// Get first argument type:
type FirstArg<T> = T extends (first: infer F, ...rest: any[]) => any ? F : never;

type K = FirstArg<(name: string, age: number) => void>;  // string

// ✅ DISTRIBUTIVE CONDITIONAL TYPES
// When T is a union, the conditional distributes over each member:

type ToArray<T> = T extends any ? T[] : never;

type L = ToArray<string | number>;
// Result: string[] | number[]  (NOT (string | number)[])

// Prevent distribution with []:
type ToArrayNonDist<T> = [T] extends [any] ? T[] : never;

type M = ToArrayNonDist<string | number>;
// Result: (string | number)[]
```

### 7.4 Template Literal Types ⭐⭐

```typescript
// ✅ TEMPLATE LITERAL TYPES — String manipulation at the type level!

type Greeting = `Hello, ${string}!`;
let g: Greeting = "Hello, Nilesh!";   // ✅
// let g: Greeting = "Hi, Nilesh!";   // ❌

// Combine unions:
type Color = "red" | "green" | "blue";
type Size = "sm" | "md" | "lg";

type ClassName = `${Color}-${Size}`;
// "red-sm" | "red-md" | "red-lg" | "green-sm" | "green-md" | "green-lg" | "blue-sm" | "blue-md" | "blue-lg"

// Event names:
type EventName = `on${Capitalize<"click" | "hover" | "focus">}`;
// "onClick" | "onHover" | "onFocus"

// CSS properties:
type CSSProperty = `${string}-${string}`;
// "background-color", "font-size", etc.

// ✅ BUILT-IN STRING MANIPULATION TYPES:
type Upper = Uppercase<"hello">;       // "HELLO"
type Lower = Lowercase<"HELLO">;       // "hello"
type Cap = Capitalize<"hello">;        // "Hello"
type Uncap = Uncapitalize<"Hello">;    // "hello"
```

### 7.5 keyof & typeof ⭐⭐⭐

```typescript
// ✅ keyof — Get all keys of a type as a union ⭐⭐⭐

type User = {
  id: string;
  name: string;
  age: number;
  email: string;
};

type UserKeys = keyof User;
// Result: "id" | "name" | "age" | "email"

function getValue(user: User, key: keyof User) {
  return user[key]; // ✅ TypeScript knows key is valid
}

// ✅ typeof — Get type from a VALUE ⭐⭐⭐

const config = {
  apiUrl: "https://api.example.com",
  timeout: 5000,
  retries: 3,
};

type Config = typeof config;
// Result:
// {
//   apiUrl: string;
//   timeout: number;
//   retries: number;
// }

type ConfigKeys = keyof typeof config;
// Result: "apiUrl" | "timeout" | "retries"

// ✅ COMBINING keyof + typeof ⭐⭐⭐
const ROUTES = {
  HOME: "/",
  ABOUT: "/about",
  BLOG: "/blog",
} as const;

type RouteKey = keyof typeof ROUTES;           // "HOME" | "ABOUT" | "BLOG"
type RouteValue = typeof ROUTES[RouteKey];     // "/" | "/about" | "/blog"

// ✅ INDEXED ACCESS TYPES — Access specific property types ⭐⭐
type UserName = User["name"];           // string
type UserAge = User["age"];             // number
type UserNameOrAge = User["name" | "age"];  // string | number

// Array element type:
type StringArray = string[];
type StringElement = StringArray[number]; // string

// Tuple element type:
type MyTuple = [string, number, boolean];
type First = MyTuple[0];   // string
type Second = MyTuple[1];  // number
```

---

## PART 8: TYPESCRIPT WITH REACT & NEXT.JS (Week 6)

### 8.1 React Component Types ⭐⭐⭐

```typescript
// ✅ COMPONENT PROPS ⭐⭐⭐

// Basic props:
type ButtonProps = {
  label: string;
  onClick: () => void;
  variant?: "primary" | "secondary" | "danger";
  size?: "sm" | "md" | "lg";
  disabled?: boolean;
  isLoading?: boolean;
};

const Button = ({ 
  label, 
  onClick, 
  variant = "primary", 
  size = "md",
  disabled = false,
  isLoading = false,
}: ButtonProps) => {
  return (
    <button 
      onClick={onClick} 
      disabled={disabled || isLoading}
      className={`btn btn-${variant} btn-${size}`}
    >
      {isLoading ? "Loading..." : label}
    </button>
  );
};

// ✅ CHILDREN PROP ⭐⭐⭐
type CardProps = {
  title: string;
  children: React.ReactNode;  // ← THE type for children
  footer?: React.ReactNode;
};

const Card = ({ title, children, footer }: CardProps) => (
  <div className="card">
    <h3>{title}</h3>
    <div>{children}</div>
    {footer && <div>{footer}</div>}
  </div>
);

// Usage:
<Card title="Hello">
  <p>Content here</p>
  <Button label="Click" onClick={() => {}} />
</Card>

// ✅ React.ReactNode vs React.ReactElement vs JSX.Element:
// React.ReactNode — MOST inclusive (string, number, null, undefined, JSX)
//                    → Use for children ⭐
// React.ReactElement — Only JSX elements
// JSX.Element — Only JSX elements (slightly different)

// ✅ EVENT HANDLERS ⭐⭐⭐
type FormProps = {
  onSubmit: (e: React.FormEvent<HTMLFormElement>) => void;
  onChange: (e: React.ChangeEvent<HTMLInputElement>) => void;
  onClick: (e: React.MouseEvent<HTMLButtonElement>) => void;
  onKeyDown: (e: React.KeyboardEvent<HTMLInputElement>) => void;
  onFocus: (e: React.FocusEvent<HTMLInputElement>) => void;
  onScroll: (e: React.UIEvent<HTMLDivElement>) => void;
};

// Common event types:
// React.MouseEvent<HTMLButtonElement>
// React.ChangeEvent<HTMLInputElement>
// React.ChangeEvent<HTMLSelectElement>
// React.ChangeEvent<HTMLTextAreaElement>
// React.FormEvent<HTMLFormElement>
// React.KeyboardEvent<HTMLInputElement>
// React.FocusEvent<HTMLInputElement>
// React.DragEvent<HTMLDivElement>
// React.ClipboardEvent<HTMLInputElement>

// ✅ Input handler shorthand:
const handleChange = (e: React.ChangeEvent<HTMLInputElement>) => {
  const { name, value } = e.target;
  setFormData(prev => ({ ...prev, [name]: value }));
};

// ✅ HOOKS WITH TYPESCRIPT ⭐⭐⭐

// useState:
const [count, setCount] = useState(0);           // Inferred: number
const [name, setName] = useState("");             // Inferred: string
const [user, setUser] = useState<User | null>(null); // Explicit: User | null ⭐
const [items, setItems] = useState<string[]>([]); // Explicit: string[]

// useRef:
const inputRef = useRef<HTMLInputElement>(null);   // DOM ref
const countRef = useRef<number>(0);                // Mutable value
const timerRef = useRef<NodeJS.Timeout | null>(null);

// useRef with input:
<input ref={inputRef} />
inputRef.current?.focus();  // TypeScript knows it's HTMLInputElement

// useContext:
type ThemeContextType = {
  theme: "light" | "dark";
  toggleTheme: () => void;
};

const ThemeContext = createContext<ThemeContextType | null>(null);

function useTheme(): ThemeContextType {
  const context = useContext(ThemeContext);
  if (!context) throw new Error("useTheme must be used within ThemeProvider");
  return context;
}

// useReducer:
type State = { count: number; step: number };
type Action =
  | { type: "INCREMENT" }
  | { type: "DECREMENT" }
  | { type: "SET_STEP"; payload: number }
  | { type: "RESET" };

function reducer(state: State, action: Action): State {
  switch (action.type) {
    case "INCREMENT":
      return { ...state, count: state.count + state.step };
    case "DECREMENT":
      return { ...state, count: state.count - state.step };
    case "SET_STEP":
      return { ...state, step: action.payload };
    case "RESET":
      return { count: 0, step: 1 };
  }
}

const [state, dispatch] = useReducer(reducer, { count: 0, step: 1 });
dispatch({ type: "INCREMENT" });
dispatch({ type: "SET_STEP", payload: 5 });

// ✅ GENERIC COMPONENTS ⭐⭐⭐
type ListProps<T> = {
  items: T[];
  renderItem: (item: T, index: number) => React.ReactNode;
  keyExtractor: (item: T) => string;
  emptyMessage?: string;
};

function List<T>({ items, renderItem, keyExtractor, emptyMessage }: ListProps<T>) {
  if (items.length === 0) return <p>{emptyMessage || "No items"}</p>;
  
  return (
    <ul>
      {items.map((item, index) => (
        <li key={keyExtractor(item)}>{renderItem(item, index)}</li>
      ))}
    </ul>
  );
}

// Usage:
<List<User>
  items={users}
  renderItem={(user) => <span>{user.name}</span>}
  keyExtractor={(user) => user.id}
/>

<List<Product>
  items={products}
  renderItem={(product) => <span>{product.name} - ${product.price}</span>}
  keyExtractor={(product) => product.id}
/>

// ✅ POLYMORPHIC COMPONENTS (as prop) ⭐⭐
type BoxProps<C extends React.ElementType> = {
  as?: C;
  children: React.ReactNode;
} & React.ComponentPropsWithoutRef<C>;

function Box<C extends React.ElementType = "div">({
  as,
  children,
  ...rest
}: BoxProps<C>) {
  const Component = as || "div";
  return <Component {...rest}>{children}</Component>;
}

<Box>Default div</Box>
<Box as="section">Section element</Box>
<Box as="a" href="/about">Link element</Box>
<Box as="button" onClick={() => {}}>Button element</Box>

// ✅ EXTENDING HTML ELEMENTS ⭐⭐
type InputProps = React.InputHTMLAttributes<HTMLInputElement> & {
  label: string;
  error?: string;
};

const Input = ({ label, error, ...rest }: InputProps) => (
  <div>
    <label>{label}</label>
    <input {...rest} className={`input ${error ? 'error' : ''}`} />
    {error && <span className="text-red-500">{error}</span>}
  </div>
);

// Gets ALL native input props (type, placeholder, onChange, etc.) for free!
<Input label="Email" type="email" placeholder="Enter email" required />
```

### 8.2 Next.js Specific Types

```typescript
// ✅ NEXT.JS PAGE PROPS ⭐

// Page component:
type PageProps = {
  params: { slug: string };
  searchParams: { page?: string; sort?: string };
};

export default function Page({ params, searchParams }: PageProps) {
  return <div>Slug: {params.slug}</div>;
}

// Layout component:
type LayoutProps = {
  children: React.ReactNode;
  params: { locale: string };
};

export default function Layout({ children, params }: LayoutProps) {
  return <div>{children}</div>;
}

// generateMetadata:
import type { Metadata } from "next";

export async function generateMetadata({ params }: PageProps): Promise<Metadata> {
  return { title: params.slug };
}

// generateStaticParams:
export async function generateStaticParams(): Promise<{ slug: string }[]> {
  return [{ slug: "first" }, { slug: "second" }];
}

// Server Action:
"use server";
export async function createPost(formData: FormData): Promise<{ error?: string }> {
  const title = formData.get("title") as string;
  // ...
  return {};
}

// Route Handler:
import { NextRequest, NextResponse } from "next/server";

export async function GET(
  request: NextRequest,
  { params }: { params: { id: string } }
): Promise<NextResponse> {
  return NextResponse.json({ id: params.id });
}

// Middleware:
import { NextRequest, NextResponse } from "next/server";

export function middleware(request: NextRequest): NextResponse {
  return NextResponse.next();
}
```

---

## PART 9: TYPESCRIPT WITH NODE.JS & BACKEND (Week 7)

```typescript
// ✅ EXPRESS WITH TYPESCRIPT ⭐

import express, { Request, Response, NextFunction } from "express";

// Typed request body:
interface CreateUserBody {
  name: string;
  email: string;
  password: string;
}

// Typed params:
interface UserParams {
  id: string;
}

// Typed query:
interface SearchQuery {
  q?: string;
  page?: string;
  limit?: string;
}

app.post("/api/users", (req: Request<{}, {}, CreateUserBody>, res: Response) => {
  const { name, email, password } = req.body; // Fully typed!
  res.json({ name, email });
});

app.get("/api/users/:id", (req: Request<UserParams>, res: Response) => {
  const { id } = req.params; // TypeScript knows id is string
  res.json({ id });
});

app.get("/api/search", (req: Request<{}, {}, {}, SearchQuery>, res: Response) => {
  const { q, page, limit } = req.query; // All typed!
  res.json({ q, page, limit });
});

// ✅ PRISMA WITH TYPESCRIPT (Types auto-generated!) ⭐⭐
import { PrismaClient, User, Post, Prisma } from "@prisma/client";

const prisma = new PrismaClient();

// Prisma generates types from your schema automatically!
async function createUser(data: Prisma.UserCreateInput): Promise<User> {
  return prisma.user.create({ data });
}

async function getUsers(where?: Prisma.UserWhereInput): Promise<User[]> {
  return prisma.user.findMany({ where });
}

// ✅ ZOD VALIDATION WITH TYPESCRIPT ⭐⭐⭐
import { z } from "zod";

const UserSchema = z.object({
  name: z.string().min(2).max(50),
  email: z.string().email(),
  age: z.number().int().min(0).max(150).optional(),
  role: z.enum(["admin", "user", "moderator"]),
});

// Infer TypeScript type from Zod schema!
type User = z.infer<typeof UserSchema>;
// Result:
// {
//   name: string;
//   email: string;
//   age?: number;
//   role: "admin" | "user" | "moderator";
// }

// Validate data:
function createUser(input: unknown): User {
  const validated = UserSchema.parse(input); // Throws if invalid
  return validated; // Fully typed!
}

// Safe parse (doesn't throw):
const result = UserSchema.safeParse(input);
if (result.success) {
  console.log(result.data.name); // Typed!
} else {
  console.log(result.error.issues); // Validation errors
}
```

---

## PART 10: TYPESCRIPT CONFIGURATION (Week 8)

### 10.1 tsconfig.json Deep Dive

```json
// ✅ tsconfig.json — UNDERSTAND EVERY IMPORTANT OPTION ⭐⭐

{
  "compilerOptions": {
    // ✅ TARGET — What JS version to compile to
    "target": "ES2022",          // Modern JS features

    // ✅ MODULE — Module system
    "module": "ESNext",          // ES modules
    "moduleResolution": "bundler", // For bundlers (Vite, Next.js)

    // ✅ STRICT MODE — ALWAYS ENABLE! ⭐⭐⭐
    "strict": true,              // Enables ALL strict checks:
    // Includes:
    //   "strictNullChecks": true     — null/undefined must be handled
    //   "strictFunctionTypes": true  — Strict function type checking
    //   "strictBindCallApply": true  — Strict bind, call, apply
    //   "noImplicitAny": true        — Must type all 'any' explicitly
    //   "noImplicitThis": true       — Must type 'this'
    //   "alwaysStrict": true         — Adds "use strict" to output

    // ✅ ADDITIONAL STRICT CHECKS (recommended):
    "noUncheckedIndexedAccess": true,  // arr[0] is T | undefined ⭐
    "noImplicitReturns": true,         // All paths must return
    "noFallthroughCasesInSwitch": true,// Switch must break/return
    "noUnusedLocals": true,            // Error on unused variables
    "noUnusedParameters": true,        // Error on unused parameters
    "exactOptionalPropertyTypes": true, // Strict optional properties

    // ✅ JSX
    "jsx": "react-jsx",         // For React 17+ (automatic JSX)

    // ✅ PATHS — Import aliases
    "baseUrl": ".",
    "paths": {
      "@/*": ["./*"],            // import from "@/components/..."
      "@/components/*": ["./components/*"],
      "@/lib/*": ["./lib/*"]
    },

    // ✅ OUTPUT
    "outDir": "./dist",          // Compiled JS output directory
    "rootDir": "./src",          // Source directory
    "declaration": true,         // Generate .d.ts files
    "sourceMap": true,           // Generate source maps

    // ✅ INTEROP
    "esModuleInterop": true,     // CommonJS/ES module compatibility
    "allowSyntheticDefaultImports": true,
    "forceConsistentCasingInFileNames": true,
    "resolveJsonModule": true,   // Import JSON files
    "isolatedModules": true,     // Required for bundlers

    // ✅ SKIP
    "skipLibCheck": true         // Skip type checking node_modules
  },
  "include": ["src/**/*", "next-env.d.ts"],
  "exclude": ["node_modules", "dist"]
}
```

### 10.2 Declaration Files (.d.ts)

```typescript
// ✅ DECLARATION FILES — Type definitions for JavaScript libraries

// If a library doesn't have types, install @types/package:
// npm install -D @types/express @types/node @types/react

// Custom type declarations:
// types/global.d.ts:
declare global {
  interface Window {
    gtag: (...args: any[]) => void;
    analytics: AnalyticsInstance;
  }
  
  namespace NodeJS {
    interface ProcessEnv {
      DATABASE_URL: string;
      NEXTAUTH_SECRET: string;
      GOOGLE_CLIENT_ID: string;
      GOOGLE_CLIENT_SECRET: string;
      NODE_ENV: "development" | "production" | "test";
    }
  }
}

export {};

// Now process.env.DATABASE_URL is typed! ⭐

// Declare module for untyped packages:
// types/untyped-package.d.ts:
declare module "untyped-package" {
  export function doSomething(input: string): number;
  export default class MyClass {
    constructor(options: { key: string });
    process(): Promise<void>;
  }
}

// Declare CSS modules:
declare module "*.module.css" {
  const classes: { readonly [key: string]: string };
  export default classes;
}

declare module "*.svg" {
  const content: React.FC<React.SVGAttributes<SVGElement>>;
  export default content;
}
```

---

## PART 11: REAL-WORLD PATTERNS & BEST PRACTICES

```typescript
// ✅ PATTERN 1: Builder Pattern ⭐
class QueryBuilder<T> {
  private filters: Partial<T> = {};
  private sortField?: keyof T;
  private sortOrder: "asc" | "desc" = "asc";
  private limitValue = 10;
  private offsetValue = 0;

  where<K extends keyof T>(field: K, value: T[K]): this {
    this.filters[field] = value;
    return this; // Enables chaining!
  }

  sort(field: keyof T, order: "asc" | "desc" = "asc"): this {
    this.sortField = field;
    this.sortOrder = order;
    return this;
  }

  limit(n: number): this { this.limitValue = n; return this; }
  offset(n: number): this { this.offsetValue = n; return this; }

  build() {
    return { filters: this.filters, sort: this.sortField, order: this.sortOrder, limit: this.limitValue, offset: this.offsetValue };
  }
}

new QueryBuilder<User>()
  .where("role", "admin")
  .where("age", 25)
  .sort("name", "asc")
  .limit(20)
  .build();


// ✅ PATTERN 2: Result Type (No try-catch everywhere) ⭐⭐
type Result<T, E = Error> =
  | { ok: true; value: T }
  | { ok: false; error: E };

function ok<T>(value: T): Result<T, never> {
  return { ok: true, value };
}

function err<E>(error: E): Result<never, E> {
  return { ok: false, error };
}

async function getUser(id: string): Promise<Result<User, string>> {
  const user = await db.findUser(id);
  if (!user) return err("User not found");
  return ok(user);
}

// Usage:
const result = await getUser("123");
if (result.ok) {
  console.log(result.value.name); // ✅ TypeScript knows it's User
} else {
  console.log(result.error);      // ✅ TypeScript knows it's string
}


// ✅ PATTERN 3: Branded Types (Prevent mixing similar types) ⭐⭐
type Brand<T, B> = T & { __brand: B };

type UserId = Brand<string, "UserId">;
type PostId = Brand<string, "PostId">;
type Email = Brand<string, "Email">;

function getUser(id: UserId): User { /* ... */ }
function getPost(id: PostId): Post { /* ... */ }

const userId = "user_123" as UserId;
const postId = "post_456" as PostId;

getUser(userId);  // ✅
// getUser(postId); // ❌ Error! Can't pass PostId where UserId is expected!


// ✅ DO'S AND DON'TS:

// ❌ DON'T use any:
let data: any = fetchSomething();

// ✅ DO use unknown + narrow:
let data: unknown = fetchSomething();
if (isUser(data)) { /* typed! */ }

// ❌ DON'T use type assertions when you can narrow:
const value = someValue as string;

// ✅ DO use type guards:
if (typeof someValue === "string") { /* typed! */ }

// ❌ DON'T duplicate types:
type CreateUser = { name: string; email: string };
type UpdateUser = { name?: string; email?: string };

// ✅ DO use utility types:
type CreateUser = { name: string; email: string };
type UpdateUser = Partial<CreateUser>;

// ❌ DON'T over-type (trust inference):
const name: string = "Nilesh";

// ✅ DO let TypeScript infer:
const name = "Nilesh";

// ❌ DON'T use enum for simple constants:
enum Color { Red, Green, Blue }

// ✅ DO use union types:
type Color = "red" | "green" | "blue";
```

---

## PART 12: BUILD 6 TYPESCRIPT PROJECTS

```
PROJECT 1 — CLI Todo App (Week 1) ⭐ STARTER
  ✅ Pure TypeScript (no framework)
  ✅ CRUD operations on JSON file
  ✅ Command-line arguments
  ✅ Type-safe data models
  Skills: Basic types, interfaces, enums
  Time: 1-2 days

PROJECT 2 — Type-Safe API Client (Week 2-3) ⭐⭐
  ✅ Generic fetch wrapper
  ✅ Typed endpoints
  ✅ Error handling with Result type
  ✅ Request/Response type inference
  Skills: Generics, utility types, async
  Time: 2-3 days

PROJECT 3 — Form Validation Library (Week 3-4) ⭐⭐
  ✅ Zod-like validation schema
  ✅ Type inference from schema
  ✅ Custom validators
  ✅ Error messages
  Skills: Generics, conditional types, inference
  Time: 3-4 days

PROJECT 4 — React Component Library (Week 4-5) ⭐⭐⭐
  ✅ Button, Input, Modal, Toast, Table
  ✅ Polymorphic components (as prop)
  ✅ Generic components (List, Select)
  ✅ Theme system with types
  ✅ Storybook documentation
  Skills: React types, generics, mapped types
  Time: 5-7 days

PROJECT 5 — Full-Stack Next.js App with TypeScript (Week 5-6) ⭐⭐⭐
  ✅ Prisma schema + generated types
  ✅ Zod validation everywhere
  ✅ Type-safe Server Actions
  ✅ Type-safe API routes
  ✅ End-to-end type safety
  Skills: Everything combined
  Time: 5-7 days

PROJECT 6 — npm Package with TypeScript (Week 7-8) ⭐⭐⭐
  ✅ Build a utility library
  ✅ Generate declaration files (.d.ts)
  ✅ Publish to npm
  ✅ Proper tsconfig for library
  ✅ Unit tests with Vitest
  Skills: Module system, declarations, publishing
  Time: 3-4 days
```

---

## PART 14: 30-DAY KICKSTART PLAN

```
WEEK 1 (Days 1-7): FUNDAMENTALS
  Day 1: Setup + Primitive types + Type inference
  Day 2: Arrays, tuples, objects, type aliases
  Day 3: Enums, literal types, const assertions
  Day 4: Union types, intersection types
  Day 5: Type narrowing (typeof, in, instanceof, discriminated unions)
  Day 6: Type assertions, satisfies, unknown vs any
  Day 7: Build Project 1 (CLI Todo)

WEEK 2 (Days 8-14): FUNCTIONS & GENERICS
  Day 8: Function types, optional params, rest params, overloads
  Day 9: Generics basics (identity, arrays, pairs)
  Day 10: Generic constraints (extends, keyof)
  Day 11: Generic interfaces, type aliases, classes
  Day 12: Utility types Part 1 (Partial, Required, Readonly, Pick, Omit)
  Day 13: Utility types Part 2 (Record, Exclude, Extract, ReturnType)
  Day 14: Build Project 2 (Type-Safe API Client)

WEEK 3 (Days 15-21): ADVANCED TYPES
  Day 15: Mapped types, key remapping
  Day 16: Conditional types, infer keyword
  Day 17: Template literal types, keyof, typeof
  Day 18: Interfaces vs types, OOP (classes, abstract, implements)
  Day 19: Declaration files, module augmentation
  Day 20: Real-world patterns (Result, Builder, Branded)
  Day 21: Build Project 3 (Form Validation Library)

WEEK 4 (Days 22-30): REACT/NEXT.JS + PRACTICE
  Day 22: React component props, children, events
  Day 23: React hooks types (useState, useRef, useContext, useReducer)
  Day 24: Generic React components, polymorphic components
  Day 25: Next.js types (pages, layouts, Server Actions, API routes)
  Day 26: Prisma + Zod + TypeScript
  Day 27-29: Build Project 5 (Full-Stack Next.js)
  Day 30: Review + tsconfig mastery + Interview prep
```

---

## PART 15: INTERVIEW QUESTIONS (100+)

```
BASICS:
  ✅ What is TypeScript? Why use it?
  ✅ What are the basic types in TypeScript?
  ✅ What is the difference between any, unknown, and never?
  ✅ What is type inference?
  ✅ What is the difference between type and interface?
  ✅ When would you use type vs interface?
  ✅ What are literal types?
  ✅ What is const assertion (as const)?
  ✅ What are enums? When to use them?
  ✅ What is the satisfies operator?

INTERMEDIATE:
  ✅ Explain union and intersection types
  ✅ What is type narrowing? Name all techniques
  ✅ What are type guards? What is a type predicate?
  ✅ What is the difference between readonly and const?
  ✅ What are index signatures?
  ✅ Explain discriminated unions with an example
  ✅ What are assertion functions?

GENERICS:
  ✅ What are generics? Why do we need them?
  ✅ What are generic constraints (extends)?
  ✅ Explain keyof and typeof
  ✅ What is the difference between T extends X and T = X?
  ✅ How do you create a generic React component?

UTILITY TYPES:
  ✅ Explain Partial, Required, Readonly
  ✅ Explain Pick and Omit
  ✅ Explain Record
  ✅ Explain Exclude, Extract, NonNullable
  ✅ Explain ReturnType, Parameters, Awaited
  ✅ How would you implement Partial from scratch?

ADVANCED:
  ✅ What are mapped types?
  ✅ What are conditional types?
  ✅ What is the infer keyword?
  ✅ What are template literal types?
  ✅ What are declaration files (.d.ts)?
  ✅ How does module augmentation work?
  ✅ What is declaration merging?
  ✅ What are branded types?
  ✅ How do you handle generic constraints with multiple types?
  ✅ Explain covariance and contravariance

REACT + TYPESCRIPT:
  ✅ How do you type React component props?
  ✅ How do you type React children?
  ✅ How do you type event handlers in React?
  ✅ How do you type useState, useRef, useContext?
  ✅ What is a generic React component?
  ✅ How do you extend HTML element props?
  ✅ What is a polymorphic component?
```

---

## PART 16: WHAT COMES AFTER TYPESCRIPT

```
AFTER MASTERING TYPESCRIPT:

✅ Advanced Patterns:
   → Type-level programming
   → HKTs (Higher-Kinded Types) patterns
   → Variance annotations (in/out)
   → Decorators (Stage 3)

✅ tRPC — End-to-end type safety
   → Type-safe APIs without REST/GraphQL
   → create.t3.gg (T3 Stack)

✅ Zod — Runtime validation + TypeScript
   → Schema-first development
   → z.infer for type generation

✅ Effect-TS — Functional programming in TypeScript
   → Error handling, concurrency
   → Growing ecosystem

✅ Contribute to DefinitelyTyped
   → Write @types/ packages
   → Help the community

THE TYPESCRIPT MASTERY LEVELS:
  Level 1: Can use basic types ← You start here
  Level 2: Comfortable with generics
  Level 3: Can write utility types
  Level 4: Can solve type challenges
  Level 5: Can design type-safe libraries ← Expert
```


**TypeScript is NOT optional in 2025 — it's REQUIRED.**
**Every type you learn prevents 10 runtime bugs.**
**Generics + Utility Types = You're ahead of 80% of developers.**
**Type safety is not about restriction — it's about CONFIDENCE.** 🚀
