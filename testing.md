

# THE ULTIMATE TESTING MASTERY ROADMAP

**From Zero to Testing Expert in 8-10 Weeks**

*Every tool, every pattern, every strategy — nothing skipped*

---

## TABLE OF CONTENTS

```
PART 1:   What is Testing & Why It Matters
PART 2:   Prerequisites Checklist
PART 3:   Testing Fundamentals — Concepts & Principles (Week 1)
PART 4:   Unit Testing with Vitest/Jest (Week 2-3)
PART 5:   Component Testing with React Testing Library (Week 4-5)
PART 6:   Integration Testing (Week 6)
PART 7:   End-to-End Testing with Playwright (Week 7-8)
PART 8:   API Testing (Week 9)
PART 9:   Mocking — MSW, Spies, Stubs (Week 10)
PART 10:  Testing in Next.js (Complete)
PART 11:  Testing Patterns & Best Practices
PART 12:  Test-Driven Development (TDD)
PART 13:  Performance & Visual Regression Testing
PART 14:  CI/CD — Automated Testing Pipeline
PART 15:  Testing Configuration & Tooling
PART 16:  Build 8 Testing Projects
PART 17:  Resources (GitHub + YouTube + Courses)
PART 18:  Day-by-Day 30-Day Kickstart Plan
PART 19:  Interview Preparation (100+ Questions)
PART 20:  What Comes After Testing
```

---

## PART 1: WHAT IS TESTING & WHY IT MATTERS

### 1.1 Understanding Testing

```
WHAT IS SOFTWARE TESTING:
  Testing = Writing code that verifies your OTHER code works correctly
  
  You write CODE that:
    → Runs your functions/components
    → Checks if the output matches expectations
    → Reports pass ✅ or fail ❌
  
  Think of it as: Building a robot QA tester that never gets tired

WHY TESTING MATTERS — THE REAL COST OF BUGS:

  WITHOUT TESTS:
    1. You write code → seems to work
    2. Deploy to production
    3. User finds bug at 3 AM → app crashes 💥
    4. You wake up, debug for 4 hours
    5. Fix breaks something else
    6. Repeat endlessly
    
    Time spent: 100 hours debugging
    User trust: DESTROYED
    Sleep: GONE
    
  WITH TESTS:
    1. You write code + tests
    2. Tests catch the bug immediately ✅
    3. You fix it in 10 minutes
    4. Tests confirm nothing else broke ✅
    5. Deploy with confidence
    6. Sleep peacefully 😴
    
    Time spent: 30 hours (including writing tests)
    User trust: MAINTAINED
    Sleep: FULL 8 HOURS

  INDUSTRY FACTS:
    → Bug found during development: $100 to fix
    → Bug found during testing: $1,000 to fix
    → Bug found in production: $10,000+ to fix
    → 90% of companies require testing for hiring
    → No tests = No code review approval at any serious company

WHY DEVELOPERS SKIP TESTS (and why they're WRONG):
  ❌ "Tests slow me down" → Tests SPEED you up (catch bugs early)
  ❌ "My code works fine" → Until you change it tomorrow
  ❌ "I'll add tests later" → You never will
  ❌ "Tests are boring" → Debugging production at 3 AM is worse
  ❌ "Small project doesn't need tests" → Every project grows
```

### 1.2 The Testing Pyramid ⭐⭐⭐

```
THE TESTING PYRAMID (Industry Standard):

                    /\
                   /  \
                  / E2E \          ← Fewest tests
                 / Tests  \         (slow, expensive, brittle)
                /──────────\        (test full user flows)
               /            \
              / Integration   \    ← Some tests
             /   Tests         \    (medium speed)
            /───────────────────\   (test modules together)
           /                     \
          /     Unit Tests        \ ← Most tests
         /      (Foundation)       \ (fast, cheap, reliable)
        /───────────────────────────\ (test individual functions)


  UNIT TESTS (70% of your tests):
    ✅ Test ONE function/module in isolation
    ✅ Very fast (milliseconds)
    ✅ Easy to write and maintain
    ✅ Run frequently (on every save)
    Example: Test that add(2, 3) returns 5

  INTEGRATION TESTS (20% of your tests):
    ✅ Test multiple modules working TOGETHER
    ✅ Medium speed (seconds)
    ✅ Test database operations, API calls
    Example: Test that POST /api/users creates a user in database

  E2E TESTS (10% of your tests):
    ✅ Test COMPLETE user flows in real browser
    ✅ Slowest (seconds to minutes)
    ✅ Test critical paths only
    Example: User signs up → logs in → creates post → deletes it

  THE TROPHY MODEL (Modern alternative by Kent C. Dodds):
  
                    /\
                   / E2E\
                  /──────\
                 /  Integ-\
                / ration   \        ← MOST tests here! ⭐
               / Tests      \
              /──────────────\
             /   Unit Tests   \
            /──────────────────\
           /  Static Analysis   \   ← TypeScript, ESLint
          /──────────────────────\

  KEY INSIGHT: Integration tests give the BEST ROI ⭐
    → Not too slow, not too fast
    → Test REAL user behavior
    → Catch the most bugs per test written
    → Kent C. Dodds: "Write tests. Not too many. Mostly integration."
```

### 1.3 Types of Testing (Complete List)

```
ALL TESTING TYPES:

  ✅ UNIT TESTING — Test individual functions/modules
  ✅ COMPONENT TESTING — Test React components in isolation
  ✅ INTEGRATION TESTING — Test modules working together
  ✅ END-TO-END (E2E) TESTING — Test full user flows in browser
  ✅ API TESTING — Test HTTP endpoints
  ✅ SNAPSHOT TESTING — Compare UI output to saved snapshot
  ✅ VISUAL REGRESSION TESTING — Compare screenshots
  ✅ PERFORMANCE TESTING — Test speed, load handling
  ✅ ACCESSIBILITY TESTING — Test a11y compliance
  ✅ SECURITY TESTING — Test for vulnerabilities
  
  WHAT WE'LL COVER IN THIS ROADMAP:
    ⭐ Unit Testing (Vitest/Jest)
    ⭐ Component Testing (React Testing Library)
    ⭐ Integration Testing
    ⭐ E2E Testing (Playwright)
    ⭐ API Testing
    ⭐ Mocking (MSW)
    ⭐ CI/CD Pipeline
    ⭐ TDD
```

### 1.4 Testing Tools Ecosystem

```
THE TESTING TOOL LANDSCAPE (2025):

  TEST RUNNERS (Run your tests):
    ✅ Vitest ⭐⭐⭐ (RECOMMENDED — fastest, modern, Vite-powered)
    ✅ Jest ⭐⭐ (Industry standard, Facebook, slower)
    → Bun test (emerging)

  COMPONENT TESTING:
    ✅ React Testing Library ⭐⭐⭐ (THE standard)
    → @testing-library/react
    → @testing-library/user-event
    → @testing-library/jest-dom

  E2E TESTING:
    ✅ Playwright ⭐⭐⭐ (RECOMMENDED — Microsoft, fastest, best)
    ✅ Cypress ⭐⭐ (Popular, slower, good DX)
    → Puppeteer (Google, lower-level)

  API MOCKING:
    ✅ MSW (Mock Service Worker) ⭐⭐⭐ (THE standard)
    → Intercepts network requests at network level
    → Works in tests AND browser

  ASSERTION LIBRARIES:
    ✅ Vitest/Jest built-in (expect, toBe, etc.)
    ✅ @testing-library/jest-dom (DOM assertions)
    → Chai (alternative)

  CODE COVERAGE:
    ✅ V8 Coverage (built into Vitest) ⭐
    ✅ Istanbul (built into Jest)

  VISUAL TESTING:
    → Chromatic (Storybook visual testing)
    → Percy (visual regression)
    → Playwright screenshots

  MY RECOMMENDED STACK:
    Vitest + React Testing Library + Playwright + MSW
    This is the modern, industry-standard combo ⭐⭐⭐
```

---

## PART 2: PREREQUISITES CHECKLIST

```
BEFORE STARTING TESTING:

JavaScript/TypeScript ✅ (8/10):
  ✅ Functions, async/await, Promises
  ✅ Array methods (map, filter, find)
  ✅ Object destructuring, spread
  ✅ Modules (import/export)
  ✅ Error handling (try/catch)
  ✅ TypeScript basics (types, interfaces, generics)

React ✅ (7/10):
  ✅ Components, props, children
  ✅ useState, useEffect, useRef
  ✅ useContext
  ✅ Forms & event handling
  ✅ Conditional rendering
  ✅ Lists & keys

Next.js ✅ (6/10 — helpful but not required):
  ✅ App Router basics
  ✅ Server/Client Components
  ✅ Server Actions
  ✅ API routes

Node.js ✅ (5/10):
  ✅ npm basics
  ✅ Modules
  ✅ Basic HTTP concepts

Git ✅:
  ✅ git add, commit, push, pull, branch

IF REACT IS WEAK → Learn React first, then come back.
Testing React without knowing React = Pointless.
```

---

## PART 3: TESTING FUNDAMENTALS (Week 1)

### 3.1 Core Testing Concepts ⭐⭐⭐

```typescript
// ✅ THE ANATOMY OF A TEST

// Every test has 3 parts (AAA Pattern):
// 1. ARRANGE — Set up the test data/environment
// 2. ACT — Perform the action being tested
// 3. ASSERT — Verify the result

// Example:
test('adds two numbers correctly', () => {
  // ARRANGE
  const a = 5;
  const b = 3;
  
  // ACT
  const result = add(a, b);
  
  // ASSERT
  expect(result).toBe(8);
});


// ✅ TEST STRUCTURE

// describe() — Group related tests:
describe('Calculator', () => {
  
  describe('add', () => {
    test('adds two positive numbers', () => {
      expect(add(2, 3)).toBe(5);
    });
    
    test('adds negative numbers', () => {
      expect(add(-2, -3)).toBe(-5);
    });
    
    test('adds zero', () => {
      expect(add(5, 0)).toBe(5);
    });
  });
  
  describe('subtract', () => {
    test('subtracts two numbers', () => {
      expect(subtract(5, 3)).toBe(2);
    });
  });
});


// ✅ test() vs it() — They are IDENTICAL
test('does something', () => { /* ... */ });
it('does something', () => { /* ... */ });
// Use whichever reads better. it() reads like English:
// "it adds two numbers"
// "it returns null when user not found"


// ✅ TEST NAMING CONVENTION ⭐⭐⭐
// Name should describe WHAT is being tested + EXPECTED behavior

// ❌ Bad:
test('test 1', () => { /* ... */ });
test('add function', () => { /* ... */ });

// ✅ Good:
test('adds two positive numbers correctly', () => { /* ... */ });
test('returns null when user is not found', () => { /* ... */ });
test('throws error when email is invalid', () => { /* ... */ });
test('renders loading spinner while data is fetching', () => { /* ... */ });

// ✅ EVEN BETTER — Use Given/When/Then in name:
test('given valid credentials, when login is called, then returns user token', () => { /* ... */ });

// Or: "should" pattern:
test('should return the sum of two numbers', () => { /* ... */ });
test('should throw error for negative values', () => { /* ... */ });
```

### 3.2 Assertions (expect) ⭐⭐⭐

```typescript
// ✅ ALL ESSENTIAL MATCHERS — MEMORIZE THESE

// ========== EQUALITY ==========
expect(value).toBe(expected);              // Strict equality (===) ⭐
expect(value).toEqual(expected);           // Deep equality (objects/arrays) ⭐
expect(value).toStrictEqual(expected);     // Deep + checks undefined properties

// toBe vs toEqual:
expect(5).toBe(5);                          // ✅ Primitives: use toBe
expect({ a: 1 }).toEqual({ a: 1 });        // ✅ Objects: use toEqual
expect({ a: 1 }).toBe({ a: 1 });           // ❌ FAILS (different references)

// ========== TRUTHINESS ==========
expect(value).toBeTruthy();                // Any truthy value
expect(value).toBeFalsy();                 // Any falsy value (0, '', null, undefined, false)
expect(value).toBeNull();                  // === null
expect(value).toBeUndefined();             // === undefined
expect(value).toBeDefined();               // !== undefined
expect(value).toBeNaN();                   // NaN

// ========== NUMBERS ==========
expect(value).toBeGreaterThan(3);          // > 3
expect(value).toBeGreaterThanOrEqual(3);   // >= 3
expect(value).toBeLessThan(5);             // < 5
expect(value).toBeLessThanOrEqual(5);      // <= 5
expect(0.1 + 0.2).toBeCloseTo(0.3);       // Floating point ⭐

// ========== STRINGS ==========
expect(value).toMatch(/regex/);            // Regex match
expect(value).toMatch('substring');        // Contains substring
expect(value).toContain('substring');      // Contains substring
expect(value).toHaveLength(5);             // String length

// ========== ARRAYS ==========
expect(array).toContain(item);             // Array includes item ⭐
expect(array).toContainEqual(object);      // Array includes object (deep)
expect(array).toHaveLength(3);             // Array length ⭐
expect(array).toEqual(expect.arrayContaining([1, 2])); // Contains these items

// ========== OBJECTS ==========
expect(obj).toHaveProperty('key');         // Has property ⭐
expect(obj).toHaveProperty('key', 'value');// Has property with value
expect(obj).toMatchObject({ name: 'Nilesh' }); // Contains subset ⭐
expect(obj).toEqual(expect.objectContaining({ name: 'Nilesh' }));

// ========== ERRORS/EXCEPTIONS ==========
expect(() => throwingFn()).toThrow();                   // Throws anything ⭐
expect(() => throwingFn()).toThrow('error message');     // Throws with message
expect(() => throwingFn()).toThrow(TypeError);           // Throws specific error type
expect(() => throwingFn()).toThrow(/regex/);             // Throws matching regex

// For async:
await expect(asyncFn()).rejects.toThrow('error');        // Async throw ⭐
await expect(asyncFn()).resolves.toBe('value');          // Async resolve

// ========== NEGATION (.not) ==========
expect(value).not.toBe(5);                // NOT equal ⭐
expect(value).not.toBeNull();             // NOT null
expect(array).not.toContain(item);        // NOT in array
expect(fn).not.toThrow();                 // Does NOT throw

// ========== FUNCTION CALLS (Spies/Mocks) ==========
expect(mockFn).toHaveBeenCalled();                    // Was called ⭐
expect(mockFn).toHaveBeenCalledTimes(3);              // Called exactly 3 times ⭐
expect(mockFn).toHaveBeenCalledWith(arg1, arg2);      // Called with args ⭐
expect(mockFn).toHaveBeenLastCalledWith(arg);         // Last call args
expect(mockFn).toHaveBeenNthCalledWith(2, arg);       // 2nd call args
expect(mockFn).toHaveReturnedWith(value);             // Returned value

// ========== SNAPSHOT ==========
expect(value).toMatchSnapshot();           // Match saved snapshot
expect(value).toMatchInlineSnapshot(`"expected"`); // Inline snapshot
```

### 3.3 Setup & Teardown

```typescript
// ✅ LIFECYCLE HOOKS — Run code BEFORE/AFTER tests

describe('UserService', () => {
  
  // Runs ONCE before ALL tests in this describe:
  beforeAll(async () => {
    await database.connect();
    console.log('Database connected');
  });
  
  // Runs ONCE after ALL tests in this describe:
  afterAll(async () => {
    await database.disconnect();
    console.log('Database disconnected');
  });
  
  // Runs before EACH test:
  beforeEach(async () => {
    await database.clear();       // Clean slate for each test
    await database.seed();        // Fresh test data
    console.log('Database reset');
  });
  
  // Runs after EACH test:
  afterEach(() => {
    vi.restoreAllMocks();         // Reset all mocks
    console.log('Mocks restored');
  });
  
  test('creates a user', async () => {
    // Database is fresh and seeded for this test
    const user = await UserService.create({ name: 'Nilesh' });
    expect(user.name).toBe('Nilesh');
  });
  
  test('deletes a user', async () => {
    // Database was reset again before THIS test
    const user = await UserService.create({ name: 'Test' });
    await UserService.delete(user.id);
    const found = await UserService.findById(user.id);
    expect(found).toBeNull();
  });
});


// ✅ EXECUTION ORDER:
// beforeAll → 
//   beforeEach → test 1 → afterEach → 
//   beforeEach → test 2 → afterEach → 
//   beforeEach → test 3 → afterEach →
// afterAll


// ✅ SKIP & FOCUS TESTS

// Skip a test:
test.skip('this test is skipped', () => { /* ... */ });
xtest('also skipped', () => { /* ... */ });
xit('also skipped', () => { /* ... */ });

// Only run this test (focus):
test.only('only this test runs', () => { /* ... */ });

// Skip entire describe:
describe.skip('SkippedSuite', () => { /* all skipped */ });

// Only this describe:
describe.only('OnlySuite', () => { /* only these run */ });

// Todo test (placeholder):
test.todo('implement this test later');

// Conditional:
test.skipIf(process.env.CI)('only runs locally', () => { /* ... */ });
test.runIf(process.env.CI)('only runs in CI', () => { /* ... */ });

// ✅ TEST EACH (Parameterized tests) ⭐⭐
test.each([
  [1, 2, 3],
  [5, 10, 15],
  [-1, -2, -3],
  [0, 0, 0],
])('add(%i, %i) = %i', (a, b, expected) => {
  expect(add(a, b)).toBe(expected);
});

// With objects:
test.each([
  { input: 'hello', expected: 'HELLO' },
  { input: 'world', expected: 'WORLD' },
  { input: 'TypeScript', expected: 'TYPESCRIPT' },
])('toUpperCase($input) = $expected', ({ input, expected }) => {
  expect(input.toUpperCase()).toBe(expected);
});

// With template literal (table format):
test.each`
  a    | b    | expected
  ${1} | ${2} | ${3}
  ${5} | ${5} | ${10}
  ${0} | ${0} | ${0}
`('add($a, $b) = $expected', ({ a, b, expected }) => {
  expect(add(a, b)).toBe(expected);
});
```

---

## PART 4: UNIT TESTING WITH VITEST (Week 2-3)

### 4.1 Vitest Setup ⭐⭐⭐

```bash
# ✅ INSTALL VITEST

# For Vite projects (React + Vite):
npm install -D vitest @testing-library/react @testing-library/jest-dom 
npm install -D @testing-library/user-event jsdom

# For Next.js:
npm install -D vitest @vitejs/plugin-react @testing-library/react 
npm install -D @testing-library/jest-dom @testing-library/user-event jsdom
```

```typescript
// ✅ VITEST CONFIG
// vitest.config.ts (or vite.config.ts):

import { defineConfig } from 'vitest/config';
import react from '@vitejs/plugin-react';
import path from 'path';

export default defineConfig({
  plugins: [react()],
  test: {
    globals: true,              // ⭐ Use describe/test/expect without imports
    environment: 'jsdom',       // ⭐ Simulate browser environment
    setupFiles: ['./tests/setup.ts'],  // ⭐ Setup file
    include: ['**/*.{test,spec}.{ts,tsx}'], // Test file pattern
    coverage: {
      provider: 'v8',           // Code coverage
      reporter: ['text', 'html', 'lcov'],
      exclude: ['node_modules', 'tests/setup.ts'],
    },
    css: true,                  // Process CSS imports
  },
  resolve: {
    alias: {
      '@': path.resolve(__dirname, './'),  // Path aliases
    },
  },
});


// ✅ SETUP FILE
// tests/setup.ts:
import '@testing-library/jest-dom/vitest';  // ⭐ DOM matchers
// Adds: toBeInTheDocument(), toHaveTextContent(), toBeVisible(), etc.

// Optional: Global mocks
vi.mock('next/navigation', () => ({
  useRouter: () => ({
    push: vi.fn(),
    replace: vi.fn(),
    back: vi.fn(),
    refresh: vi.fn(),
  }),
  usePathname: () => '/',
  useSearchParams: () => new URLSearchParams(),
}));


// ✅ PACKAGE.JSON SCRIPTS:
{
  "scripts": {
    "test": "vitest",                    // Watch mode (default)
    "test:run": "vitest run",            // Run once
    "test:coverage": "vitest run --coverage", // With coverage
    "test:ui": "vitest --ui",            // Visual UI ⭐
    "test:watch": "vitest --watch"       // Explicit watch
  }
}


// ✅ FILE NAMING CONVENTION:
// utils.ts        → utils.test.ts      (co-located)
// Button.tsx      → Button.test.tsx     (co-located)
//
// OR in __tests__ folder:
// __tests__/utils.test.ts
// __tests__/Button.test.tsx
//
// MY RECOMMENDATION: Co-locate tests next to source ⭐
// src/
//   utils/
//     math.ts
//     math.test.ts ← Right next to the source!
//   components/
//     Button.tsx
//     Button.test.tsx ← Right next to the component!
```

### 4.2 Unit Testing Functions ⭐⭐⭐

```typescript
// ✅ TESTING PURE FUNCTIONS

// src/utils/math.ts:
export function add(a: number, b: number): number {
  return a + b;
}

export function multiply(a: number, b: number): number {
  return a * b;
}

export function divide(a: number, b: number): number {
  if (b === 0) throw new Error('Cannot divide by zero');
  return a / b;
}

export function clamp(value: number, min: number, max: number): number {
  return Math.min(Math.max(value, min), max);
}

export function average(numbers: number[]): number {
  if (numbers.length === 0) throw new Error('Array cannot be empty');
  return numbers.reduce((sum, n) => sum + n, 0) / numbers.length;
}


// src/utils/math.test.ts:
import { describe, test, expect } from 'vitest';
import { add, multiply, divide, clamp, average } from './math';

describe('Math utilities', () => {
  
  // ✅ TESTING BASIC FUNCTION
  describe('add', () => {
    test('adds two positive numbers', () => {
      expect(add(2, 3)).toBe(5);
    });
    
    test('adds negative numbers', () => {
      expect(add(-2, -3)).toBe(-5);
    });
    
    test('adds with zero', () => {
      expect(add(5, 0)).toBe(5);
    });
    
    test('handles decimal numbers', () => {
      expect(add(0.1, 0.2)).toBeCloseTo(0.3);
    });
  });
  
  // ✅ TESTING ERROR CASES
  describe('divide', () => {
    test('divides two numbers', () => {
      expect(divide(10, 2)).toBe(5);
    });
    
    test('returns decimal result', () => {
      expect(divide(7, 2)).toBe(3.5);
    });
    
    test('throws error when dividing by zero', () => {
      expect(() => divide(10, 0)).toThrow('Cannot divide by zero');
    });
    
    test('throws specific error type', () => {
      expect(() => divide(10, 0)).toThrow(Error);
    });
  });
  
  // ✅ TESTING EDGE CASES
  describe('clamp', () => {
    test('returns value when within range', () => {
      expect(clamp(5, 0, 10)).toBe(5);
    });
    
    test('clamps to minimum', () => {
      expect(clamp(-5, 0, 10)).toBe(0);
    });
    
    test('clamps to maximum', () => {
      expect(clamp(15, 0, 10)).toBe(10);
    });
    
    test('handles equal min and max', () => {
      expect(clamp(5, 3, 3)).toBe(3);
    });
    
    test('handles value equal to min', () => {
      expect(clamp(0, 0, 10)).toBe(0);
    });
    
    test('handles value equal to max', () => {
      expect(clamp(10, 0, 10)).toBe(10);
    });
  });
  
  // ✅ TESTING ARRAYS
  describe('average', () => {
    test('calculates average of numbers', () => {
      expect(average([2, 4, 6])).toBe(4);
    });
    
    test('handles single number', () => {
      expect(average([5])).toBe(5);
    });
    
    test('handles decimal result', () => {
      expect(average([1, 2])).toBe(1.5);
    });
    
    test('throws error for empty array', () => {
      expect(() => average([])).toThrow('Array cannot be empty');
    });
  });
});


// ✅ TESTING STRING FUNCTIONS

// src/utils/string.ts:
export function slugify(text: string): string {
  return text
    .toLowerCase()
    .trim()
    .replace(/[^\w\s-]/g, '')
    .replace(/[\s_-]+/g, '-')
    .replace(/^-+|-+$/g, '');
}

export function truncate(text: string, maxLength: number): string {
  if (text.length <= maxLength) return text;
  return text.slice(0, maxLength).trimEnd() + '...';
}

export function capitalize(text: string): string {
  if (!text) return '';
  return text.charAt(0).toUpperCase() + text.slice(1).toLowerCase();
}

export function isValidEmail(email: string): boolean {
  const emailRegex = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
  return emailRegex.test(email);
}

// src/utils/string.test.ts:
import { slugify, truncate, capitalize, isValidEmail } from './string';

describe('String utilities', () => {
  
  describe('slugify', () => {
    test('converts text to slug', () => {
      expect(slugify('Hello World')).toBe('hello-world');
    });
    
    test('handles multiple spaces', () => {
      expect(slugify('Hello    World')).toBe('hello-world');
    });
    
    test('removes special characters', () => {
      expect(slugify('Hello! @World#')).toBe('hello-world');
    });
    
    test('trims leading/trailing hyphens', () => {
      expect(slugify('  Hello World  ')).toBe('hello-world');
    });
    
    test('handles already slugified text', () => {
      expect(slugify('hello-world')).toBe('hello-world');
    });
    
    test('handles empty string', () => {
      expect(slugify('')).toBe('');
    });
  });
  
  describe('isValidEmail', () => {
    // ✅ Parameterized tests for valid emails:
    test.each([
      'user@example.com',
      'test.user@domain.co',
      'name+tag@gmail.com',
      'user123@test.org',
    ])('returns true for valid email: %s', (email) => {
      expect(isValidEmail(email)).toBe(true);
    });
    
    // ✅ Parameterized tests for invalid emails:
    test.each([
      '',
      'not-an-email',
      '@domain.com',
      'user@',
      'user @domain.com',
      'user@domain',
    ])('returns false for invalid email: %s', (email) => {
      expect(isValidEmail(email)).toBe(false);
    });
  });
});


// ✅ TESTING ASYNC FUNCTIONS ⭐⭐

// src/utils/api.ts:
export async function fetchUser(id: string): Promise<User> {
  const response = await fetch(`/api/users/${id}`);
  if (!response.ok) throw new Error(`User not found: ${id}`);
  return response.json();
}

export async function delay(ms: number): Promise<void> {
  return new Promise(resolve => setTimeout(resolve, ms));
}

export async function retryFetch<T>(
  fn: () => Promise<T>,
  retries: number = 3
): Promise<T> {
  for (let i = 0; i < retries; i++) {
    try {
      return await fn();
    } catch (error) {
      if (i === retries - 1) throw error;
      await delay(1000);
    }
  }
  throw new Error('Max retries reached');
}

// src/utils/api.test.ts:
import { fetchUser, retryFetch } from './api';

describe('API utilities', () => {
  
  describe('fetchUser', () => {
    // ✅ TESTING ASYNC SUCCESS
    test('returns user data for valid id', async () => {
      // Mock fetch globally
      global.fetch = vi.fn().mockResolvedValueOnce({
        ok: true,
        json: async () => ({ id: '1', name: 'Nilesh' }),
      });
      
      const user = await fetchUser('1');
      
      expect(user).toEqual({ id: '1', name: 'Nilesh' });
      expect(fetch).toHaveBeenCalledWith('/api/users/1');
    });
    
    // ✅ TESTING ASYNC ERRORS
    test('throws error for non-existent user', async () => {
      global.fetch = vi.fn().mockResolvedValueOnce({
        ok: false,
        status: 404,
      });
      
      await expect(fetchUser('999')).rejects.toThrow('User not found: 999');
    });
  });
  
  describe('retryFetch', () => {
    test('returns on first successful attempt', async () => {
      const fn = vi.fn().mockResolvedValueOnce('data');
      
      const result = await retryFetch(fn);
      
      expect(result).toBe('data');
      expect(fn).toHaveBeenCalledTimes(1);
    });
    
    test('retries on failure then succeeds', async () => {
      const fn = vi.fn()
        .mockRejectedValueOnce(new Error('fail'))
        .mockRejectedValueOnce(new Error('fail'))
        .mockResolvedValueOnce('success');
      
      const result = await retryFetch(fn, 3);
      
      expect(result).toBe('success');
      expect(fn).toHaveBeenCalledTimes(3);
    });
    
    test('throws after max retries exhausted', async () => {
      const fn = vi.fn().mockRejectedValue(new Error('always fails'));
      
      await expect(retryFetch(fn, 3)).rejects.toThrow('always fails');
      expect(fn).toHaveBeenCalledTimes(3);
    });
  });
});
```

### 4.3 Mocks, Spies & Stubs ⭐⭐⭐

```typescript
// ✅ MOCKING — Replace real implementations with controlled alternatives

// ========== MOCK FUNCTIONS ==========

// Create a mock function:
const mockFn = vi.fn();

mockFn('hello');
mockFn('world');

expect(mockFn).toHaveBeenCalled();
expect(mockFn).toHaveBeenCalledTimes(2);
expect(mockFn).toHaveBeenCalledWith('hello');
expect(mockFn).toHaveBeenLastCalledWith('world');

// Mock with return value:
const mockFn = vi.fn().mockReturnValue(42);
expect(mockFn()).toBe(42);

// Mock with different return values:
const mockFn = vi.fn()
  .mockReturnValueOnce(1)
  .mockReturnValueOnce(2)
  .mockReturnValue(999);  // Default after exhausted

expect(mockFn()).toBe(1);     // First call
expect(mockFn()).toBe(2);     // Second call
expect(mockFn()).toBe(999);   // Third+ calls

// Mock with implementation:
const mockFn = vi.fn((a: number, b: number) => a + b);
expect(mockFn(2, 3)).toBe(5);

// Mock async function:
const mockAsync = vi.fn().mockResolvedValue({ id: 1, name: 'Nilesh' });
const result = await mockAsync();
expect(result).toEqual({ id: 1, name: 'Nilesh' });

// Mock async rejection:
const mockReject = vi.fn().mockRejectedValue(new Error('Network error'));
await expect(mockReject()).rejects.toThrow('Network error');


// ========== SPYING ON EXISTING FUNCTIONS ==========

const calculator = {
  add: (a: number, b: number) => a + b,
  multiply: (a: number, b: number) => a * b,
};

// Spy on method (keeps original implementation):
const spy = vi.spyOn(calculator, 'add');

calculator.add(2, 3);  // Still returns 5 (real implementation)

expect(spy).toHaveBeenCalledWith(2, 3);
expect(spy).toHaveReturnedWith(5);

// Spy AND replace implementation:
vi.spyOn(calculator, 'add').mockReturnValue(999);
expect(calculator.add(2, 3)).toBe(999);  // Mock return

// Spy on console:
const consoleSpy = vi.spyOn(console, 'log');
console.log('test');
expect(consoleSpy).toHaveBeenCalledWith('test');

// Restore spy:
spy.mockRestore();


// ========== MOCKING MODULES ==========

// ✅ Mock entire module:
vi.mock('./database', () => ({
  getUser: vi.fn().mockResolvedValue({ id: '1', name: 'Nilesh' }),
  createUser: vi.fn().mockResolvedValue({ id: '2', name: 'New User' }),
  deleteUser: vi.fn().mockResolvedValue(true),
}));

// ✅ Mock with factory (dynamic):
vi.mock('./config', () => ({
  default: {
    apiUrl: 'http://test-api.com',
    timeout: 1000,
  },
}));

// ✅ Partial mock (keep some real, mock others):
vi.mock('./utils', async () => {
  const actual = await vi.importActual('./utils');
  return {
    ...actual,                    // Keep all real exports
    fetchData: vi.fn(),           // Override this one
  };
});

// ✅ Mock third-party modules:
vi.mock('next/navigation', () => ({
  useRouter: vi.fn(() => ({
    push: vi.fn(),
    replace: vi.fn(),
    back: vi.fn(),
    refresh: vi.fn(),
    prefetch: vi.fn(),
  })),
  usePathname: vi.fn(() => '/'),
  useSearchParams: vi.fn(() => new URLSearchParams()),
  redirect: vi.fn(),
}));

// ✅ Access mock to modify in individual tests:
import { useRouter } from 'next/navigation';
const mockRouter = {
  push: vi.fn(),
  replace: vi.fn(),
};
vi.mocked(useRouter).mockReturnValue(mockRouter as any);


// ========== TIMERS ==========

// ✅ Mock timers (setTimeout, setInterval, Date):
beforeEach(() => {
  vi.useFakeTimers();
});

afterEach(() => {
  vi.useRealTimers();
});

test('debounce waits before calling', () => {
  const callback = vi.fn();
  const debounced = debounce(callback, 500);
  
  debounced();
  expect(callback).not.toHaveBeenCalled();
  
  vi.advanceTimersByTime(499);
  expect(callback).not.toHaveBeenCalled();
  
  vi.advanceTimersByTime(1);
  expect(callback).toHaveBeenCalledTimes(1);
});

test('throttle limits call frequency', () => {
  const callback = vi.fn();
  const throttled = throttle(callback, 1000);
  
  throttled(); // Calls immediately
  throttled(); // Ignored (within window)
  throttled(); // Ignored
  
  expect(callback).toHaveBeenCalledTimes(1);
  
  vi.advanceTimersByTime(1000);
  throttled(); // Calls again (new window)
  
  expect(callback).toHaveBeenCalledTimes(2);
});

// Mock Date:
vi.setSystemTime(new Date('2025-01-15T10:00:00Z'));
expect(new Date().toISOString()).toBe('2025-01-15T10:00:00.000Z');


// ========== CLEANUP ==========

afterEach(() => {
  vi.clearAllMocks();      // Clear call history (keeps implementation)
  vi.resetAllMocks();      // Reset to vi.fn() (removes implementation)
  vi.restoreAllMocks();    // Restore original implementation ⭐
});
```

---

## PART 5: COMPONENT TESTING WITH REACT TESTING LIBRARY (Week 4-5)

### 5.1 React Testing Library Philosophy ⭐⭐⭐

```typescript
// ✅ THE GUIDING PRINCIPLE:
// "The more your tests resemble the way your software is used,
//  the more confidence they can give you." — Kent C. Dodds

// ❌ DON'T test implementation details (state, internal methods)
// ✅ DO test what the USER sees and does

// ❌ BAD: Test internal state
// expect(component.state.count).toBe(5);

// ✅ GOOD: Test what user sees
// expect(screen.getByText('Count: 5')).toBeInTheDocument();


// ✅ QUERY PRIORITY (Use in this order!) ⭐⭐⭐
// 1. getByRole        ← BEST (accessible, semantic) ⭐⭐⭐
// 2. getByLabelText   ← For form elements
// 3. getByPlaceholderText ← For inputs
// 4. getByText        ← For non-interactive content
// 5. getByDisplayValue ← For filled form elements
// 6. getByAltText     ← For images
// 7. getByTitle       ← For title attributes
// 8. getByTestId      ← LAST RESORT (data-testid)

// Examples:
screen.getByRole('button', { name: 'Submit' });    // ⭐ Best
screen.getByRole('heading', { name: 'Dashboard' }); // ⭐ Best
screen.getByRole('textbox', { name: 'Email' });     // ⭐ Best
screen.getByLabelText('Email');                       // Good for forms
screen.getByText('Welcome back!');                    // Good for content
screen.getByPlaceholderText('Enter email...');        // Acceptable
screen.getByTestId('custom-element');                 // Last resort
```

### 5.2 Testing React Components ⭐⭐⭐

```typescript
// ✅ BASIC COMPONENT TEST

// components/Greeting.tsx:
type GreetingProps = {
  name: string;
  isAdmin?: boolean;
};

export default function Greeting({ name, isAdmin = false }: GreetingProps) {
  return (
    <div>
      <h1>Hello, {name}!</h1>
      {isAdmin && <span className="badge">Admin</span>}
      <p>Welcome to our app.</p>
    </div>
  );
}

// components/Greeting.test.tsx:
import { render, screen } from '@testing-library/react';
import Greeting from './Greeting';

describe('Greeting', () => {
  test('renders greeting with name', () => {
    render(<Greeting name="Nilesh" />);
    
    expect(screen.getByRole('heading')).toHaveTextContent('Hello, Nilesh!');
    expect(screen.getByText('Welcome to our app.')).toBeInTheDocument();
  });
  
  test('shows admin badge when isAdmin is true', () => {
    render(<Greeting name="Nilesh" isAdmin={true} />);
    
    expect(screen.getByText('Admin')).toBeInTheDocument();
  });
  
  test('does not show admin badge by default', () => {
    render(<Greeting name="Nilesh" />);
    
    expect(screen.queryByText('Admin')).not.toBeInTheDocument();
    // ⭐ Use queryBy when element might NOT exist (returns null instead of throwing)
  });
});


// ✅ QUERY TYPES:
// getBy...    → Throws if NOT found (use when element MUST exist) ⭐
// queryBy...  → Returns null if NOT found (use to assert NON-existence) ⭐
// findBy...   → Async, waits for element to appear (use for async content) ⭐
// getAllBy... → Returns array (for multiple matches)
// queryAllBy... → Returns empty array if none found
// findAllBy... → Async, returns array


// ✅ TESTING USER INTERACTIONS ⭐⭐⭐
import { render, screen } from '@testing-library/react';
import userEvent from '@testing-library/user-event';

// components/Counter.tsx:
'use client';
import { useState } from 'react';

export default function Counter({ initialCount = 0 }: { initialCount?: number }) {
  const [count, setCount] = useState(initialCount);
  
  return (
    <div>
      <h2>Count: {count}</h2>
      <button onClick={() => setCount(c => c + 1)}>Increment</button>
      <button onClick={() => setCount(c => c - 1)}>Decrement</button>
      <button onClick={() => setCount(0)}>Reset</button>
    </div>
  );
}

// components/Counter.test.tsx:
describe('Counter', () => {
  test('starts with initial count', () => {
    render(<Counter initialCount={5} />);
    expect(screen.getByText('Count: 5')).toBeInTheDocument();
  });
  
  test('starts at 0 by default', () => {
    render(<Counter />);
    expect(screen.getByText('Count: 0')).toBeInTheDocument();
  });
  
  test('increments count when clicking increment button', async () => {
    const user = userEvent.setup();  // ⭐ Always setup userEvent
    render(<Counter />);
    
    await user.click(screen.getByRole('button', { name: 'Increment' }));
    expect(screen.getByText('Count: 1')).toBeInTheDocument();
    
    await user.click(screen.getByRole('button', { name: 'Increment' }));
    expect(screen.getByText('Count: 2')).toBeInTheDocument();
  });
  
  test('decrements count when clicking decrement button', async () => {
    const user = userEvent.setup();
    render(<Counter initialCount={5} />);
    
    await user.click(screen.getByRole('button', { name: 'Decrement' }));
    expect(screen.getByText('Count: 4')).toBeInTheDocument();
  });
  
  test('resets count to 0', async () => {
    const user = userEvent.setup();
    render(<Counter initialCount={10} />);
    
    await user.click(screen.getByRole('button', { name: 'Reset' }));
    expect(screen.getByText('Count: 0')).toBeInTheDocument();
  });
});


// ✅ TESTING FORMS ⭐⭐⭐
// components/LoginForm.tsx:
'use client';
import { useState } from 'react';

type LoginFormProps = {
  onSubmit: (email: string, password: string) => Promise<void>;
};

export default function LoginForm({ onSubmit }: LoginFormProps) {
  const [email, setEmail] = useState('');
  const [password, setPassword] = useState('');
  const [error, setError] = useState('');
  const [isLoading, setIsLoading] = useState(false);
  
  const handleSubmit = async (e: React.FormEvent) => {
    e.preventDefault();
    setError('');
    
    if (!email) { setError('Email is required'); return; }
    if (!password) { setError('Password is required'); return; }
    if (password.length < 6) { setError('Password must be at least 6 characters'); return; }
    
    setIsLoading(true);
    try {
      await onSubmit(email, password);
    } catch (err) {
      setError('Login failed. Please try again.');
    } finally {
      setIsLoading(false);
    }
  };
  
  return (
    <form onSubmit={handleSubmit}>
      <h2>Login</h2>
      
      {error && <div role="alert" className="error">{error}</div>}
      
      <label htmlFor="email">Email</label>
      <input
        id="email"
        type="email"
        value={email}
        onChange={(e) => setEmail(e.target.value)}
        placeholder="Enter your email"
      />
      
      <label htmlFor="password">Password</label>
      <input
        id="password"
        type="password"
        value={password}
        onChange={(e) => setPassword(e.target.value)}
        placeholder="Enter your password"
      />
      
      <button type="submit" disabled={isLoading}>
        {isLoading ? 'Logging in...' : 'Login'}
      </button>
    </form>
  );
}

// components/LoginForm.test.tsx:
import { render, screen, waitFor } from '@testing-library/react';
import userEvent from '@testing-library/user-event';
import LoginForm from './LoginForm';

describe('LoginForm', () => {
  const mockOnSubmit = vi.fn();
  const user = userEvent.setup();
  
  beforeEach(() => {
    mockOnSubmit.mockReset();
  });
  
  test('renders the login form', () => {
    render(<LoginForm onSubmit={mockOnSubmit} />);
    
    expect(screen.getByRole('heading', { name: 'Login' })).toBeInTheDocument();
    expect(screen.getByLabelText('Email')).toBeInTheDocument();
    expect(screen.getByLabelText('Password')).toBeInTheDocument();
    expect(screen.getByRole('button', { name: 'Login' })).toBeInTheDocument();
  });
  
  test('shows error when email is empty', async () => {
    render(<LoginForm onSubmit={mockOnSubmit} />);
    
    await user.click(screen.getByRole('button', { name: 'Login' }));
    
    expect(screen.getByRole('alert')).toHaveTextContent('Email is required');
    expect(mockOnSubmit).not.toHaveBeenCalled();
  });
  
  test('shows error when password is too short', async () => {
    render(<LoginForm onSubmit={mockOnSubmit} />);
    
    await user.type(screen.getByLabelText('Email'), 'test@example.com');
    await user.type(screen.getByLabelText('Password'), '12345');
    await user.click(screen.getByRole('button', { name: 'Login' }));
    
    expect(screen.getByRole('alert')).toHaveTextContent('Password must be at least 6 characters');
  });
  
  test('calls onSubmit with email and password', async () => {
    mockOnSubmit.mockResolvedValueOnce(undefined);
    render(<LoginForm onSubmit={mockOnSubmit} />);
    
    await user.type(screen.getByLabelText('Email'), 'test@example.com');
    await user.type(screen.getByLabelText('Password'), 'password123');
    await user.click(screen.getByRole('button', { name: 'Login' }));
    
    expect(mockOnSubmit).toHaveBeenCalledWith('test@example.com', 'password123');
    expect(mockOnSubmit).toHaveBeenCalledTimes(1);
  });
  
  test('shows loading state during submission', async () => {
    // Make onSubmit take time
    mockOnSubmit.mockImplementation(() => new Promise(resolve => setTimeout(resolve, 1000)));
    render(<LoginForm onSubmit={mockOnSubmit} />);
    
    await user.type(screen.getByLabelText('Email'), 'test@example.com');
    await user.type(screen.getByLabelText('Password'), 'password123');
    await user.click(screen.getByRole('button', { name: 'Login' }));
    
    // Button should show loading text
    expect(screen.getByRole('button', { name: 'Logging in...' })).toBeDisabled();
  });
  
  test('shows error message when login fails', async () => {
    mockOnSubmit.mockRejectedValueOnce(new Error('Invalid credentials'));
    render(<LoginForm onSubmit={mockOnSubmit} />);
    
    await user.type(screen.getByLabelText('Email'), 'test@example.com');
    await user.type(screen.getByLabelText('Password'), 'wrongpassword');
    await user.click(screen.getByRole('button', { name: 'Login' }));
    
    await waitFor(() => {
      expect(screen.getByRole('alert')).toHaveTextContent('Login failed. Please try again.');
    });
  });
});


// ✅ TESTING ASYNC COMPONENTS (Data Fetching) ⭐⭐

// components/UserList.tsx:
'use client';
import { useState, useEffect } from 'react';

type User = { id: string; name: string; email: string };

export default function UserList() {
  const [users, setUsers] = useState<User[]>([]);
  const [loading, setLoading] = useState(true);
  const [error, setError] = useState('');
  
  useEffect(() => {
    fetch('/api/users')
      .then(res => {
        if (!res.ok) throw new Error('Failed to fetch');
        return res.json();
      })
      .then(data => setUsers(data))
      .catch(err => setError(err.message))
      .finally(() => setLoading(false));
  }, []);
  
  if (loading) return <div role="status">Loading users...</div>;
  if (error) return <div role="alert">Error: {error}</div>;
  if (users.length === 0) return <p>No users found</p>;
  
  return (
    <ul>
      {users.map(user => (
        <li key={user.id}>{user.name} ({user.email})</li>
      ))}
    </ul>
  );
}

// components/UserList.test.tsx:
describe('UserList', () => {
  test('shows loading state initially', () => {
    global.fetch = vi.fn().mockImplementation(() => new Promise(() => {})); // Never resolves
    render(<UserList />);
    
    expect(screen.getByRole('status')).toHaveTextContent('Loading users...');
  });
  
  test('renders users after successful fetch', async () => {
    global.fetch = vi.fn().mockResolvedValueOnce({
      ok: true,
      json: async () => [
        { id: '1', name: 'Alice', email: 'alice@test.com' },
        { id: '2', name: 'Bob', email: 'bob@test.com' },
      ],
    });
    
    render(<UserList />);
    
    // Wait for users to appear (findBy is async!)
    expect(await screen.findByText('Alice (alice@test.com)')).toBeInTheDocument();
    expect(screen.getByText('Bob (bob@test.com)')).toBeInTheDocument();
  });
  
  test('shows error message on fetch failure', async () => {
    global.fetch = vi.fn().mockResolvedValueOnce({
      ok: false,
      status: 500,
    });
    
    render(<UserList />);
    
    expect(await screen.findByRole('alert')).toHaveTextContent('Error: Failed to fetch');
  });
  
  test('shows empty state when no users', async () => {
    global.fetch = vi.fn().mockResolvedValueOnce({
      ok: true,
      json: async () => [],
    });
    
    render(<UserList />);
    
    expect(await screen.findByText('No users found')).toBeInTheDocument();
  });
});


// ✅ TESTING WITH CONTEXT/PROVIDERS ⭐⭐
import { ThemeProvider } from '@/context/ThemeContext';

// Custom render with providers:
function renderWithProviders(ui: React.ReactElement) {
  return render(
    <ThemeProvider>
      {ui}
    </ThemeProvider>
  );
}

// OR create a custom render utility:
// tests/test-utils.tsx:
import { render, RenderOptions } from '@testing-library/react';
import { SessionProvider } from 'next-auth/react';
import { QueryClient, QueryClientProvider } from '@tanstack/react-query';

function AllProviders({ children }: { children: React.ReactNode }) {
  const queryClient = new QueryClient({
    defaultOptions: { queries: { retry: false } },
  });
  
  return (
    <SessionProvider session={null}>
      <QueryClientProvider client={queryClient}>
        {children}
      </QueryClientProvider>
    </SessionProvider>
  );
}

function customRender(ui: React.ReactElement, options?: RenderOptions) {
  return render(ui, { wrapper: AllProviders, ...options });
}

export * from '@testing-library/react';
export { customRender as render };

// Usage in tests:
import { render, screen } from '@/tests/test-utils';
// Now render() includes all providers automatically!
```

---

## PART 6: INTEGRATION TESTING (Week 6)

```typescript
// ✅ INTEGRATION TESTS — Test multiple units working together

// ✅ TESTING API ROUTES (Next.js Route Handlers)

// app/api/users/route.ts:
import { NextRequest, NextResponse } from 'next/server';
import { prisma } from '@/lib/db';

export async function GET() {
  const users = await prisma.user.findMany();
  return NextResponse.json(users);
}

export async function POST(request: NextRequest) {
  const body = await request.json();
  const { name, email } = body;
  
  if (!name || !email) {
    return NextResponse.json({ error: 'Name and email required' }, { status: 400 });
  }
  
  const user = await prisma.user.create({ data: { name, email } });
  return NextResponse.json(user, { status: 201 });
}

// __tests__/api/users.test.ts:
import { GET, POST } from '@/app/api/users/route';
import { NextRequest } from 'next/server';
import { prisma } from '@/lib/db';

// Mock Prisma
vi.mock('@/lib/db', () => ({
  prisma: {
    user: {
      findMany: vi.fn(),
      create: vi.fn(),
    },
  },
}));

describe('Users API', () => {
  afterEach(() => {
    vi.resetAllMocks();
  });
  
  describe('GET /api/users', () => {
    test('returns list of users', async () => {
      const mockUsers = [
        { id: '1', name: 'Alice', email: 'alice@test.com' },
        { id: '2', name: 'Bob', email: 'bob@test.com' },
      ];
      vi.mocked(prisma.user.findMany).mockResolvedValueOnce(mockUsers);
      
      const response = await GET();
      const data = await response.json();
      
      expect(response.status).toBe(200);
      expect(data).toEqual(mockUsers);
      expect(data).toHaveLength(2);
    });
    
    test('returns empty array when no users', async () => {
      vi.mocked(prisma.user.findMany).mockResolvedValueOnce([]);
      
      const response = await GET();
      const data = await response.json();
      
      expect(data).toEqual([]);
    });
  });
  
  describe('POST /api/users', () => {
    test('creates a new user', async () => {
      const newUser = { id: '3', name: 'Charlie', email: 'charlie@test.com' };
      vi.mocked(prisma.user.create).mockResolvedValueOnce(newUser);
      
      const request = new NextRequest('http://localhost/api/users', {
        method: 'POST',
        body: JSON.stringify({ name: 'Charlie', email: 'charlie@test.com' }),
      });
      
      const response = await POST(request);
      const data = await response.json();
      
      expect(response.status).toBe(201);
      expect(data).toEqual(newUser);
    });
    
    test('returns 400 when name is missing', async () => {
      const request = new NextRequest('http://localhost/api/users', {
        method: 'POST',
        body: JSON.stringify({ email: 'test@test.com' }),
      });
      
      const response = await POST(request);
      const data = await response.json();
      
      expect(response.status).toBe(400);
      expect(data.error).toBe('Name and email required');
    });
  });
});


// ✅ TESTING SERVER ACTIONS (Next.js)

// actions/posts.ts:
'use server';
import { prisma } from '@/lib/db';
import { revalidatePath } from 'next/cache';

export async function createPost(formData: FormData) {
  const title = formData.get('title') as string;
  const content = formData.get('content') as string;
  
  if (!title || title.length < 3) {
    return { error: 'Title must be at least 3 characters' };
  }
  
  const post = await prisma.post.create({
    data: { title, content, authorId: 'user-1' },
  });
  
  revalidatePath('/posts');
  return { data: post };
}

// __tests__/actions/posts.test.ts:
import { createPost } from '@/actions/posts';
import { prisma } from '@/lib/db';

vi.mock('@/lib/db');
vi.mock('next/cache', () => ({ revalidatePath: vi.fn() }));

describe('createPost action', () => {
  test('creates post with valid data', async () => {
    const mockPost = { id: '1', title: 'Test Post', content: 'Content' };
    vi.mocked(prisma.post.create).mockResolvedValueOnce(mockPost);
    
    const formData = new FormData();
    formData.set('title', 'Test Post');
    formData.set('content', 'Content');
    
    const result = await createPost(formData);
    
    expect(result.data).toEqual(mockPost);
    expect(prisma.post.create).toHaveBeenCalledWith({
      data: { title: 'Test Post', content: 'Content', authorId: 'user-1' },
    });
  });
  
  test('returns error when title is too short', async () => {
    const formData = new FormData();
    formData.set('title', 'AB');
    formData.set('content', 'Content');
    
    const result = await createPost(formData);
    
    expect(result.error).toBe('Title must be at least 3 characters');
    expect(prisma.post.create).not.toHaveBeenCalled();
  });
});
```

---

## PART 7: END-TO-END TESTING WITH PLAYWRIGHT (Week 7-8)

### 7.1 Playwright Setup ⭐⭐⭐

```bash
# ✅ INSTALL PLAYWRIGHT
npm init playwright@latest

# It will:
# → Install Playwright + browsers (Chromium, Firefox, WebKit)
# → Create playwright.config.ts
# → Create example tests
# → Create GitHub Actions workflow
```

```typescript
// ✅ PLAYWRIGHT CONFIG
// playwright.config.ts:
import { defineConfig, devices } from '@playwright/test';

export default defineConfig({
  testDir: './e2e',                    // Test directory
  fullyParallel: true,                 // Run tests in parallel
  forbidOnly: !!process.env.CI,        // Fail if test.only in CI
  retries: process.env.CI ? 2 : 0,    // Retry in CI
  workers: process.env.CI ? 1 : undefined,
  reporter: 'html',                    // HTML report
  
  use: {
    baseURL: 'http://localhost:3000',   // ⭐ Base URL
    trace: 'on-first-retry',           // Capture traces on retry
    screenshot: 'only-on-failure',     // Screenshot on failure
    video: 'retain-on-failure',        // Video on failure
  },
  
  projects: [
    // ✅ Test in multiple browsers:
    {
      name: 'chromium',
      use: { ...devices['Desktop Chrome'] },
    },
    {
      name: 'firefox',
      use: { ...devices['Desktop Firefox'] },
    },
    {
      name: 'webkit',
      use: { ...devices['Desktop Safari'] },
    },
    // ✅ Mobile testing:
    {
      name: 'Mobile Chrome',
      use: { ...devices['Pixel 5'] },
    },
    {
      name: 'Mobile Safari',
      use: { ...devices['iPhone 12'] },
    },
  ],
  
  // ✅ Start dev server before tests:
  webServer: {
    command: 'npm run dev',
    url: 'http://localhost:3000',
    reuseExistingServer: !process.env.CI,
    timeout: 120000,
  },
});
```

```bash
# ✅ RUN PLAYWRIGHT TESTS
npx playwright test                    # Run all tests
npx playwright test --headed           # Show browser ⭐
npx playwright test --ui               # Interactive UI ⭐⭐
npx playwright test login.spec.ts      # Run specific file
npx playwright test --project=chromium # Specific browser
npx playwright show-report             # View HTML report
npx playwright codegen                 # Record tests ⭐⭐⭐

# ✅ CODEGEN — Record tests by clicking in browser!
npx playwright codegen http://localhost:3000
# Opens browser + test recorder. Click around → code is generated!
```

### 7.2 Writing E2E Tests ⭐⭐⭐

```typescript
// ✅ BASIC NAVIGATION TEST

// e2e/navigation.spec.ts:
import { test, expect } from '@playwright/test';

test.describe('Navigation', () => {
  test('navigates to home page', async ({ page }) => {
    await page.goto('/');
    
    await expect(page).toHaveTitle(/My App/);
    await expect(page.getByRole('heading', { level: 1 })).toBeVisible();
  });
  
  test('navigates to about page', async ({ page }) => {
    await page.goto('/');
    
    await page.getByRole('link', { name: 'About' }).click();
    
    await expect(page).toHaveURL('/about');
    await expect(page.getByRole('heading', { name: 'About Us' })).toBeVisible();
  });
  
  test('shows 404 for non-existent pages', async ({ page }) => {
    await page.goto('/non-existent-page');
    
    await expect(page.getByText('404')).toBeVisible();
  });
});


// ✅ AUTHENTICATION FLOW ⭐⭐⭐

// e2e/auth.spec.ts:
test.describe('Authentication', () => {
  test('user can register', async ({ page }) => {
    await page.goto('/register');
    
    await page.getByLabel('Name').fill('Test User');
    await page.getByLabel('Email').fill('test@example.com');
    await page.getByLabel('Password').fill('password123');
    await page.getByLabel('Confirm Password').fill('password123');
    
    await page.getByRole('button', { name: 'Register' }).click();
    
    // Should redirect to dashboard
    await expect(page).toHaveURL('/dashboard');
    await expect(page.getByText('Welcome, Test User')).toBeVisible();
  });
  
  test('user can login', async ({ page }) => {
    await page.goto('/login');
    
    await page.getByLabel('Email').fill('test@example.com');
    await page.getByLabel('Password').fill('password123');
    await page.getByRole('button', { name: 'Login' }).click();
    
    await expect(page).toHaveURL('/dashboard');
    await expect(page.getByText('Dashboard')).toBeVisible();
  });
  
  test('shows error for invalid credentials', async ({ page }) => {
    await page.goto('/login');
    
    await page.getByLabel('Email').fill('wrong@example.com');
    await page.getByLabel('Password').fill('wrongpassword');
    await page.getByRole('button', { name: 'Login' }).click();
    
    await expect(page.getByRole('alert')).toHaveText(/invalid credentials/i);
    await expect(page).toHaveURL('/login'); // Stays on login page
  });
  
  test('redirects unauthenticated users from protected pages', async ({ page }) => {
    await page.goto('/dashboard');
    
    await expect(page).toHaveURL(/\/login/);
  });
  
  test('user can logout', async ({ page }) => {
    // First login
    await page.goto('/login');
    await page.getByLabel('Email').fill('test@example.com');
    await page.getByLabel('Password').fill('password123');
    await page.getByRole('button', { name: 'Login' }).click();
    await expect(page).toHaveURL('/dashboard');
    
    // Then logout
    await page.getByRole('button', { name: 'Logout' }).click();
    
    await expect(page).toHaveURL('/');
  });
});


// ✅ CRUD FLOW ⭐⭐⭐

// e2e/posts.spec.ts:
test.describe('Blog Posts', () => {
  // Login before each test
  test.beforeEach(async ({ page }) => {
    await page.goto('/login');
    await page.getByLabel('Email').fill('test@example.com');
    await page.getByLabel('Password').fill('password123');
    await page.getByRole('button', { name: 'Login' }).click();
    await expect(page).toHaveURL('/dashboard');
  });
  
  test('user can create a new post', async ({ page }) => {
    await page.getByRole('link', { name: 'New Post' }).click();
    await expect(page).toHaveURL('/posts/new');
    
    await page.getByLabel('Title').fill('My Test Post');
    await page.getByLabel('Content').fill('This is test content for my post.');
    await page.getByRole('button', { name: 'Publish' }).click();
    
    // Should redirect to post page
    await expect(page.getByRole('heading', { name: 'My Test Post' })).toBeVisible();
    await expect(page.getByText('This is test content')).toBeVisible();
  });
  
  test('user can edit a post', async ({ page }) => {
    await page.goto('/posts');
    
    await page.getByText('My Test Post').click();
    await page.getByRole('button', { name: 'Edit' }).click();
    
    await page.getByLabel('Title').clear();
    await page.getByLabel('Title').fill('Updated Title');
    await page.getByRole('button', { name: 'Save' }).click();
    
    await expect(page.getByRole('heading', { name: 'Updated Title' })).toBeVisible();
  });
  
  test('user can delete a post', async ({ page }) => {
    await page.goto('/posts');
    
    const postCount = await page.getByRole('article').count();
    
    await page.getByText('Updated Title').click();
    await page.getByRole('button', { name: 'Delete' }).click();
    
    // Confirm dialog
    await page.getByRole('button', { name: 'Confirm' }).click();
    
    await expect(page).toHaveURL('/posts');
    await expect(page.getByRole('article')).toHaveCount(postCount - 1);
  });
});


// ✅ PLAYWRIGHT USEFUL METHODS ⭐

// Locators:
page.getByRole('button', { name: 'Submit' });     // ⭐ Best
page.getByLabel('Email');                           // For form inputs
page.getByText('Welcome');                          // By text content
page.getByPlaceholder('Search...');                 // By placeholder
page.getByTestId('custom-id');                      // By data-testid
page.locator('css-selector');                       // CSS selector
page.locator('//xpath');                             // XPath

// Actions:
await page.goto('/path');                           // Navigate
await locator.click();                              // Click
await locator.fill('text');                         // Type in input
await locator.clear();                              // Clear input
await locator.check();                              // Check checkbox
await locator.uncheck();                            // Uncheck
await locator.selectOption('value');                // Select dropdown
await locator.hover();                              // Hover
await locator.press('Enter');                       // Press key
await page.keyboard.type('text');                   // Type globally
await page.waitForURL('/expected');                  // Wait for navigation

// Assertions:
await expect(page).toHaveURL('/path');
await expect(page).toHaveTitle('Title');
await expect(locator).toBeVisible();
await expect(locator).toBeHidden();
await expect(locator).toBeEnabled();
await expect(locator).toBeDisabled();
await expect(locator).toHaveText('text');
await expect(locator).toContainText('partial');
await expect(locator).toHaveValue('input value');
await expect(locator).toHaveAttribute('href', '/about');
await expect(locator).toHaveCount(5);
await expect(locator).toHaveCSS('color', 'rgb(0, 0, 0)');
await expect(locator).toHaveScreenshot();           // Visual comparison!

// Waiting:
await page.waitForSelector('.loaded');
await page.waitForResponse('/api/data');
await page.waitForLoadState('networkidle');
await expect(locator).toBeVisible({ timeout: 10000 });
```

---

## PART 8: API TESTING (Week 9)

```typescript
// ✅ TESTING REST APIs WITH PLAYWRIGHT

// e2e/api.spec.ts:
import { test, expect } from '@playwright/test';

test.describe('API Tests', () => {
  
  test('GET /api/users returns user list', async ({ request }) => {
    const response = await request.get('/api/users');
    
    expect(response.status()).toBe(200);
    expect(response.ok()).toBeTruthy();
    
    const data = await response.json();
    expect(data).toBeInstanceOf(Array);
    expect(data.length).toBeGreaterThan(0);
    expect(data[0]).toHaveProperty('id');
    expect(data[0]).toHaveProperty('name');
    expect(data[0]).toHaveProperty('email');
  });
  
  test('POST /api/users creates a new user', async ({ request }) => {
    const response = await request.post('/api/users', {
      data: {
        name: 'Test User',
        email: 'test@example.com',
      },
    });
    
    expect(response.status()).toBe(201);
    
    const user = await response.json();
    expect(user.name).toBe('Test User');
    expect(user.email).toBe('test@example.com');
    expect(user.id).toBeDefined();
  });
  
  test('POST /api/users returns 400 for missing fields', async ({ request }) => {
    const response = await request.post('/api/users', {
      data: { name: 'No Email' },
    });
    
    expect(response.status()).toBe(400);
    
    const body = await response.json();
    expect(body.error).toBeDefined();
  });
  
  test('PUT /api/users/:id updates a user', async ({ request }) => {
    const response = await request.put('/api/users/1', {
      data: { name: 'Updated Name' },
    });
    
    expect(response.status()).toBe(200);
    const user = await response.json();
    expect(user.name).toBe('Updated Name');
  });
  
  test('DELETE /api/users/:id deletes a user', async ({ request }) => {
    const response = await request.delete('/api/users/1');
    
    expect(response.status()).toBe(200);
    
    // Verify it's deleted
    const getResponse = await request.get('/api/users/1');
    expect(getResponse.status()).toBe(404);
  });
  
  test('authenticated endpoint requires token', async ({ request }) => {
    const response = await request.get('/api/profile');
    expect(response.status()).toBe(401);
    
    const authedResponse = await request.get('/api/profile', {
      headers: {
        Authorization: 'Bearer valid-token',
      },
    });
    expect(authedResponse.status()).toBe(200);
  });
});
```

---

## PART 9: MOCKING WITH MSW (Week 10) ⭐⭐⭐

```typescript
// ✅ MSW (Mock Service Worker) — THE best API mocking tool
// Intercepts HTTP requests at the NETWORK level
// Works in tests, browser dev, and Storybook!

// npm install -D msw

// ✅ SETUP HANDLERS

// mocks/handlers.ts:
import { http, HttpResponse } from 'msw';

const users = [
  { id: '1', name: 'Alice', email: 'alice@test.com' },
  { id: '2', name: 'Bob', email: 'bob@test.com' },
];

export const handlers = [
  // GET /api/users
  http.get('/api/users', () => {
    return HttpResponse.json(users);
  }),
  
  // GET /api/users/:id
  http.get('/api/users/:id', ({ params }) => {
    const user = users.find(u => u.id === params.id);
    if (!user) {
      return HttpResponse.json({ error: 'Not found' }, { status: 404 });
    }
    return HttpResponse.json(user);
  }),
  
  // POST /api/users
  http.post('/api/users', async ({ request }) => {
    const body = await request.json();
    const newUser = { id: String(users.length + 1), ...body };
    return HttpResponse.json(newUser, { status: 201 });
  }),
  
  // Simulate network error:
  http.get('/api/failing-endpoint', () => {
    return HttpResponse.error();
  }),
  
  // Simulate slow response:
  http.get('/api/slow', async () => {
    await new Promise(resolve => setTimeout(resolve, 3000));
    return HttpResponse.json({ data: 'slow' });
  }),
];

// ✅ SETUP SERVER FOR TESTS

// mocks/server.ts:
import { setupServer } from 'msw/node';
import { handlers } from './handlers';

export const server = setupServer(...handlers);

// tests/setup.ts:
import { beforeAll, afterAll, afterEach } from 'vitest';
import { server } from '@/mocks/server';

beforeAll(() => server.listen({ onUnhandledRequest: 'error' }));
afterEach(() => server.resetHandlers()); // Reset to default handlers
afterAll(() => server.close());

// ✅ USE IN TESTS — No more mocking fetch globally!

// components/UserList.test.tsx:
import { render, screen } from '@testing-library/react';
import { http, HttpResponse } from 'msw';
import { server } from '@/mocks/server';
import UserList from './UserList';

describe('UserList', () => {
  test('renders users from API', async () => {
    render(<UserList />);
    
    // MSW automatically intercepts the fetch call!
    expect(await screen.findByText('Alice')).toBeInTheDocument();
    expect(screen.getByText('Bob')).toBeInTheDocument();
  });
  
  test('shows error when API fails', async () => {
    // ✅ Override handler for THIS test only:
    server.use(
      http.get('/api/users', () => {
        return HttpResponse.json({ error: 'Server error' }, { status: 500 });
      })
    );
    
    render(<UserList />);
    
    expect(await screen.findByRole('alert')).toHaveTextContent(/error/i);
  });
  
  test('shows empty state when no users', async () => {
    server.use(
      http.get('/api/users', () => {
        return HttpResponse.json([]);
      })
    );
    
    render(<UserList />);
    
    expect(await screen.findByText('No users found')).toBeInTheDocument();
  });
});
```

---

## PART 10: TESTING IN NEXT.JS (Complete)

```typescript
// ✅ NEXT.JS SPECIFIC TESTING PATTERNS

// 1. TESTING SERVER COMPONENTS ⭐
// Server Components can be tested as async functions:

// app/posts/page.tsx:
import { prisma } from '@/lib/db';

export default async function PostsPage() {
  const posts = await prisma.post.findMany();
  return (
    <div>
      <h1>Posts</h1>
      {posts.map(post => <article key={post.id}>{post.title}</article>)}
    </div>
  );
}

// __tests__/app/posts/page.test.tsx:
import { render, screen } from '@testing-library/react';
import PostsPage from '@/app/posts/page';

vi.mock('@/lib/db', () => ({
  prisma: {
    post: {
      findMany: vi.fn().mockResolvedValue([
        { id: '1', title: 'First Post' },
        { id: '2', title: 'Second Post' },
      ]),
    },
  },
}));

test('renders list of posts', async () => {
  const Component = await PostsPage();  // ⭐ Await the async component!
  render(Component);
  
  expect(screen.getByRole('heading', { name: 'Posts' })).toBeInTheDocument();
  expect(screen.getByText('First Post')).toBeInTheDocument();
  expect(screen.getByText('Second Post')).toBeInTheDocument();
});


// 2. TESTING CLIENT COMPONENTS (Standard RTL approach)
// Already covered in Part 5!

// 3. TESTING MIDDLEWARE
// Best tested via E2E tests with Playwright

// 4. TESTING HOOKS
import { renderHook, act } from '@testing-library/react';
import { useCounter } from '@/hooks/useCounter';

test('useCounter increments correctly', () => {
  const { result } = renderHook(() => useCounter(0));
  
  expect(result.current.count).toBe(0);
  
  act(() => {
    result.current.increment();
  });
  
  expect(result.current.count).toBe(1);
});
```

---

## PART 11: TESTING PATTERNS & BEST PRACTICES

```typescript
// ✅ THE GOLDEN RULES OF TESTING ⭐⭐⭐

// 1. TEST BEHAVIOR, NOT IMPLEMENTATION
// ❌ Bad: Testing internal state
// ✅ Good: Testing what user sees

// 2. ONE ASSERTION PER CONCEPT
// Each test should test ONE thing

// 3. TESTS SHOULD BE INDEPENDENT
// No test should depend on another test running first

// 4. TESTS SHOULD BE DETERMINISTIC
// Same input → same result, every time

// 5. AVOID TESTING THIRD-PARTY CODE
// Don't test React, Next.js, Prisma — test YOUR code

// 6. TEST THE HAPPY PATH + EDGE CASES + ERROR CASES

// 7. KEEP TESTS READABLE
// Tests are documentation — they should be easy to understand

// 8. FOLLOW THE "GIVEN-WHEN-THEN" PATTERN:
// GIVEN: Setup/preconditions
// WHEN: Action
// THEN: Expected outcome


// ✅ WHAT TO TEST & WHAT NOT TO TEST

// ✅ DO TEST:
// → Business logic (calculations, transformations)
// → User interactions (clicks, typing, form submission)
// → Conditional rendering
// → Error handling
// → API integration (with mocks)
// → Authentication flows
// → Critical user paths (checkout, signup)

// ❌ DON'T TEST:
// → Implementation details (internal state, method calls)
// → Third-party library internals
// → CSS/styling (use visual regression for this)
// → TypeScript types (compiler handles this)
// → Constants/configs
// → Simple getters/setters


// ✅ CODE COVERAGE — How much is enough?

// AIM FOR:
// 80% overall coverage ⭐ (sweet spot)
// 100% for critical business logic
// Don't chase 100% everywhere (diminishing returns)

// COVERAGE TYPES:
// Statement coverage — % of lines executed
// Branch coverage — % of if/else paths covered ⭐
// Function coverage — % of functions called
// Line coverage — % of lines executed

// Run coverage:
// npx vitest run --coverage
```

---

## PART 12: TEST-DRIVEN DEVELOPMENT (TDD) ⭐⭐

```typescript
// ✅ TDD CYCLE: RED → GREEN → REFACTOR

// STEP 1: RED — Write a failing test
test('calculates total price with tax', () => {
  expect(calculateTotal(100, 0.1)).toBe(110);
});
// Run → ❌ FAILS (function doesn't exist)

// STEP 2: GREEN — Write MINIMAL code to pass
function calculateTotal(price: number, taxRate: number): number {
  return price + (price * taxRate);
}
// Run → ✅ PASSES

// STEP 3: REFACTOR — Improve without breaking tests
function calculateTotal(price: number, taxRate: number): number {
  const tax = price * taxRate;
  return Number((price + tax).toFixed(2));
}
// Run → ✅ STILL PASSES

// STEP 4: Add more tests and repeat
test('handles zero tax', () => {
  expect(calculateTotal(100, 0)).toBe(100);
});

test('handles zero price', () => {
  expect(calculateTotal(0, 0.1)).toBe(0);
});

test('rounds to 2 decimal places', () => {
  expect(calculateTotal(19.99, 0.0825)).toBe(21.64);
});

// WHY TDD:
// ✅ Forces you to think about requirements FIRST
// ✅ Ensures all code has tests
// ✅ Better API design (you write the usage before implementation)
// ✅ Smaller, focused functions
// ✅ Documentation through tests
```

---

## PART 14: CI/CD — AUTOMATED TESTING PIPELINE ⭐⭐

```yaml
# ✅ GITHUB ACTIONS — Run tests automatically on every push/PR

# .github/workflows/test.yml:
name: Tests

on:
  push:
    branches: [main, develop]
  pull_request:
    branches: [main]

jobs:
  # ✅ UNIT & INTEGRATION TESTS
  unit-tests:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: actions/setup-node@v4
        with:
          node-version: 20
          cache: 'npm'
      - run: npm ci
      - run: npm run lint
      - run: npm run type-check
      - run: npm run test:run -- --coverage
      - uses: actions/upload-artifact@v4
        with:
          name: coverage-report
          path: coverage/

  # ✅ E2E TESTS
  e2e-tests:
    runs-on: ubuntu-latest
    needs: unit-tests  # Run after unit tests pass
    steps:
      - uses: actions/checkout@v4
      - uses: actions/setup-node@v4
        with:
          node-version: 20
          cache: 'npm'
      - run: npm ci
      - run: npx playwright install --with-deps
      - run: npm run build
      - run: npx playwright test
      - uses: actions/upload-artifact@v4
        if: failure()
        with:
          name: playwright-report
          path: playwright-report/
```

---

## PART 16: BUILD 8 TESTING PROJECTS

```
PROJECT 1 — Test a Utility Library (Week 1) ⭐ STARTER
  ✅ 20+ pure functions (string, math, array, date utils)
  ✅ 100% code coverage
  ✅ Parameterized tests (test.each)
  ✅ Edge cases, error cases
  Skills: Vitest basics, assertions, test.each
  Time: 2 days

PROJECT 2 — Test a React Component Library (Week 2-3) ⭐⭐
  ✅ Button, Input, Modal, Toast, Card, Dropdown
  ✅ User interactions (click, type, select)
  ✅ Conditional rendering tests
  ✅ Accessibility tests
  Skills: RTL, userEvent, async testing
  Time: 3-4 days

PROJECT 3 — Test a Form with Validation (Week 3) ⭐⭐
  ✅ Registration form with 8+ fields
  ✅ Client-side validation
  ✅ Server submission mocking
  ✅ Error display tests
  ✅ Success flow tests
  Skills: Form testing, MSW, async
  Time: 2-3 days

PROJECT 4 — Test a Next.js Blog App (Week 4-5) ⭐⭐⭐
  ✅ Server Components tests
  ✅ Client Components tests
  ✅ Server Actions tests
  ✅ API route tests
  ✅ Auth flow tests
  ✅ MSW for API mocking
  Skills: Next.js testing patterns
  Time: 5-7 days

PROJECT 5 — E2E Test an E-Commerce Flow (Week 6) ⭐⭐⭐
  ✅ Playwright: Browse → Add to Cart → Checkout
  ✅ Auth flow (register, login, logout)
  ✅ Search & filter
  ✅ Mobile responsive tests
  ✅ Multi-browser testing
  Skills: Playwright, real user flows
  Time: 4-5 days

PROJECT 6 — TDD a REST API (Week 7) ⭐⭐
  ✅ Build API test-first (TDD)
  ✅ CRUD endpoints
  ✅ Validation tests
  ✅ Auth tests
  ✅ Database integration tests
  Skills: TDD, API testing
  Time: 3-4 days

PROJECT 7 — CI/CD Pipeline (Week 8) ⭐⭐⭐
  ✅ GitHub Actions for all tests
  ✅ Lint + Type check + Unit + E2E
  ✅ Code coverage reporting
  ✅ Auto-deploy on passing tests
  ✅ PR preview deployments
  Skills: CI/CD, automation
  Time: 2-3 days

PROJECT 8 — Test a Production App (Week 9-10) ⭐⭐⭐⭐
  ✅ Take an existing project and add FULL test suite
  ✅ 80%+ code coverage
  ✅ Unit + Component + Integration + E2E
  ✅ MSW for all API calls
  ✅ CI/CD pipeline
  ✅ Visual regression (optional)
  Skills: Everything combined
  Time: 7-10 days
```

---

## PART 17: RESOURCES

```
YOUTUBE CHANNELS:
  1. Kent C. Dodds ⭐⭐⭐ — THE testing guru (Testing Library creator)
  2. JavaScript Testing with Vitest — Jack Herrington ⭐⭐
  3. Playwright Official ⭐⭐ — Microsoft's Playwright tutorials
  4. Fireship — Quick testing overviews
  5. Web Dev Simplified — React testing tutorials
  6. Dave Gray — Complete testing courses

DOCUMENTATION:
  vitest.dev ⭐⭐⭐ — Vitest official docs
  testing-library.com ⭐⭐⭐ — React Testing Library
  playwright.dev ⭐⭐⭐ — Playwright official docs
  mswjs.io ⭐⭐⭐ — MSW docs
  jestjs.io — Jest docs (similar API to Vitest)

GITHUB:
  github.com/testing-library/react-testing-library ⭐⭐⭐
  github.com/microsoft/playwright ⭐⭐⭐
  github.com/mswjs/msw ⭐⭐⭐
  github.com/vitest-dev/vitest ⭐⭐⭐
  github.com/goldbergyoni/javascript-testing-best-practices ⭐⭐⭐
    → 50+ testing best practices with examples!

BOOKS:
  "Testing JavaScript Applications" — Lucas da Costa
  "Testing Library Docs" (free online) — Kent C. Dodds
```

---

## PART 18: 30-DAY KICKSTART PLAN

```
WEEK 1 (Days 1-7): UNIT TESTING FOUNDATIONS
  Day 1: Setup Vitest + first tests + assertions
  Day 2: Testing pure functions (math, string, array utils)
  Day 3: Async testing + error testing
  Day 4: Mocks, spies, stubs (vi.fn, vi.mock, vi.spyOn)
  Day 5: Timer mocks + parameterized tests (test.each)
  Day 6: Code coverage + test organization
  Day 7: Build Project 1 (Test Utility Library — 100% coverage)

WEEK 2 (Days 8-14): COMPONENT TESTING
  Day 8: React Testing Library setup + first component test
  Day 9: Queries (getBy, queryBy, findBy) + user interactions
  Day 10: Testing forms (inputs, validation, submission)
  Day 11: Testing async components (loading, success, error states)
  Day 12: Testing with Context/Providers + custom render
  Day 13: MSW setup + API mocking in component tests
  Day 14: Build Project 2 (Test React Component Library)

WEEK 3 (Days 15-21): INTEGRATION + E2E
  Day 15: Integration tests (API routes, Server Actions)
  Day 16: Testing Next.js Server Components
  Day 17: Playwright setup + first E2E test
  Day 18: Playwright — navigation, forms, auth flows
  Day 19: Playwright — CRUD flows, assertions, screenshots
  Day 20: Playwright — multi-browser, mobile, API testing
  Day 21: Build Project 5 (E2E Test E-Commerce Flow)

WEEK 4 (Days 22-30): ADVANCED + CI/CD
  Day 22: TDD practice — build feature test-first
  Day 23: Testing hooks (renderHook)
  Day 24: Testing patterns + best practices review
  Day 25: CI/CD — GitHub Actions for all tests
  Day 26-28: Build Project 8 (Add full test suite to existing app)
  Day 29: Code coverage analysis + fix gaps
  Day 30: Review + Interview prep + Celebrate! 🎉
```

---

## PART 19: INTERVIEW QUESTIONS (100+)

```
FUNDAMENTALS:
  ✅ What is the testing pyramid?
  ✅ Difference between unit, integration, and E2E tests?
  ✅ What is TDD? Explain the Red-Green-Refactor cycle
  ✅ What is code coverage? What's a good target?
  ✅ What are mocks, stubs, and spies? How do they differ?
  ✅ What is the AAA pattern (Arrange-Act-Assert)?
  ✅ When should you NOT write tests?

UNIT TESTING:
  ✅ How do you test async functions?
  ✅ How do you test functions that throw errors?
  ✅ What is vi.fn() / jest.fn()? When do you use it?
  ✅ How do you mock a module?
  ✅ What is the difference between mockReturnValue and mockImplementation?
  ✅ How do you test timers (setTimeout/setInterval)?
  ✅ What are setup and teardown functions?

REACT TESTING:
  ✅ What is React Testing Library? How is it different from Enzyme?
  ✅ What is the guiding principle of Testing Library?
  ✅ What is the query priority (getByRole, getByText, etc.)?
  ✅ Difference between getBy, queryBy, and findBy?
  ✅ How do you test user interactions?
  ✅ How do you test async components?
  ✅ How do you test components with Context?
  ✅ How do you test custom hooks?
  ✅ What is data-testid? When should you use it?
  ✅ How do you test form validation?
  ✅ What is snapshot testing? When is it useful?

E2E TESTING:
  ✅ What is Playwright? How does it compare to Cypress?
  ✅ How do you handle authentication in E2E tests?
  ✅ How do you test across multiple browsers?
  ✅ How do you handle flaky tests?
  ✅ What is the Page Object Model?
  ✅ How do you test API endpoints with Playwright?

MOCKING:
  ✅ What is MSW? How does it work?
  ✅ Why is MSW better than mocking fetch directly?
  ✅ How do you override handlers for specific tests?
  ✅ How do you simulate network errors?

CI/CD:
  ✅ How do you set up automated testing in CI?
  ✅ How do you handle E2E tests in CI?
  ✅ What is a test matrix?
  ✅ How do you handle test databases in CI?

BEST PRACTICES:
  ✅ What makes a good test?
  ✅ What is a flaky test? How do you fix them?
  ✅ Should you test implementation details?
  ✅ How many tests should you write?
  ✅ When should you use E2E vs integration vs unit?
  ✅ How do you test error boundaries?
  ✅ How do you maintain test suites as apps grow?
```

---

## ROADMAP RATING

```
CRITERIA                    RATING
─────────────────────────   ──────
Unit Testing Coverage       10/10
Component Testing           10/10
E2E Testing                 10/10
API Testing                 9.5/10
Mocking (MSW)               10/10
Next.js Testing             9.5/10
CI/CD Integration           9.5/10
TDD Coverage                9/10
Best Practices              10/10
Project Ideas               10/10 (8 projects)
Resources                   10/10
Day-by-Day Plan             10/10
Interview Prep              10/10

OVERALL                     9.8/10
```

---

**Testing is NOT optional — it's what separates juniors from seniors.**
**Write tests. Not too many. Mostly integration.**
**Your tests are your safety net — they let you move FAST with confidence.**
**Every bug caught by a test is a bug your users never see.** 🚀
