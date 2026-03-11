

# 🚀 THE ULTIMATE DSA MASTERY ROADMAP
### From Zero to Interview-Ready in 6 Months
#### *Built for Final Year B.Tech CSE Students*

---

## 📋 TABLE OF CONTENTS
```
PART 1: Setup & Foundation
PART 2: The 7-Phase Roadmap (Week-by-Week)
PART 3: Exact Daily Schedule Template
PART 4: Resources (GitHub + YouTube + Platforms)
PART 5: Problem Lists (Topic-wise with LeetCode numbers)
PART 6: Common Mistakes to Avoid
PART 7: Interview Preparation Strategy
PART 8: 30-Day Kickstart Plan (Day-by-Day)
```

---

# PART 1: SETUP & FOUNDATION

## 1.1 Choose Your Language (Day 1 Decision — Never Change)

```
┌─────────────────────────────────────────────────────────────┐
│                    LANGUAGE COMPARISON                       │
├──────────┬──────────────┬──────────────┬───────────────────┤
│ Factor   │    C++       │    Java      │    Python         │
├──────────┼──────────────┼──────────────┼───────────────────┤
│ Speed    │ ⭐⭐⭐⭐⭐  │ ⭐⭐⭐⭐    │ ⭐⭐⭐           │
│ DSA      │ ⭐⭐⭐⭐⭐  │ ⭐⭐⭐⭐⭐  │ ⭐⭐⭐⭐         │
│ Content  │              │              │                   │
│ STL/Lib  │ ⭐⭐⭐⭐⭐  │ ⭐⭐⭐⭐    │ ⭐⭐⭐⭐⭐       │
│ Syntax   │ ⭐⭐⭐       │ ⭐⭐⭐      │ ⭐⭐⭐⭐⭐       │
│ Jobs     │ ⭐⭐⭐⭐    │ ⭐⭐⭐⭐⭐  │ ⭐⭐⭐⭐         │
│ CP       │ ⭐⭐⭐⭐⭐  │ ⭐⭐⭐      │ ⭐⭐⭐           │
├──────────┴──────────────┴──────────────┴───────────────────┤
│                                                             │
│  MY RECOMMENDATION:                                         │
│  → C++ if you want competitive programming + placements     │
│  → Python if you want AI/ML career + faster coding          │
│  → Java if you're targeting product companies (Google,      │
│    Amazon love Java)                                        │
│                                                             │
│  🎯 BEST OVERALL FOR DSA: C++ (STL is unbeatable)          │
└─────────────────────────────────────────────────────────────┘
```

## 1.2 Must-Know C++ STL (or equivalents)

```cpp
// IF YOU CHOOSE C++, master these BEFORE starting DSA:

// 1. VECTORS (Dynamic Arrays)
vector<int> v = {1, 2, 3};
v.push_back(4);          // Add element
v.pop_back();             // Remove last
v.size();                 // Size
sort(v.begin(), v.end()); // Sort

// 2. STRINGS
string s = "hello";
s.length();               // Length
s.substr(1, 3);           // Substring
s.find("ell");            // Find

// 3. PAIRS & TUPLES
pair<int, int> p = {1, 2};
p.first; p.second;

// 4. MAPS (Hash Maps)
unordered_map<string, int> mp;
mp["key"] = value;
mp.count("key");          // Check existence
for(auto& [k, v] : mp)   // Iterate

// 5. SETS
unordered_set<int> s;
s.insert(5);
s.count(5);               // Check existence
set<int> ordered_s;       // Sorted set

// 6. STACKS & QUEUES
stack<int> st;
st.push(1); st.top(); st.pop();
queue<int> q;
q.push(1); q.front(); q.pop();

// 7. PRIORITY QUEUE (Heap)
priority_queue<int> maxHeap;                          // Max heap
priority_queue<int, vector<int>, greater<int>> minHeap; // Min heap

// 8. ALGORITHMS
sort(v.begin(), v.end());
reverse(v.begin(), v.end());
*max_element(v.begin(), v.end());
*min_element(v.begin(), v.end());
binary_search(v.begin(), v.end(), target);
lower_bound(v.begin(), v.end(), target);
upper_bound(v.begin(), v.end(), target);
```

## 1.3 Setup Your Environment

```
TOOLS TO INSTALL (Day 1):
├── IDE: VS Code (with C/C++ extension + Code Runner)
├── Online: LeetCode account (FREE tier is enough)
├── Online: CodeStudio/Coding Ninjas (for Striver problems)
├── GitHub: Create repo "DSA-Journey" with this structure:
│
│   DSA-Journey/
│   ├── 01-Basics/
│   ├── 02-Sorting/
│   ├── 03-Arrays/
│   ├── 04-Strings/
│   ├── 05-Recursion/
│   ├── 06-LinkedList/
│   ├── 07-Stack-Queue/
│   ├── 08-Trees/
│   ├── 09-Heaps/
│   ├── 10-Hashing/
│   ├── 11-Tries/
│   ├── 12-Graphs/
│   ├── 13-DP/
│   ├── 14-Greedy/
│   ├── 15-BitManipulation/
│   ├── 16-StringAlgorithms/
│   ├── NOTES.md
│   └── PROGRESS.md
│
└── Tracker: Spreadsheet to track problems solved daily
```

---

# PART 2: THE 7-PHASE ROADMAP

## ═══════════════════════════════════════
## PHASE 1: FUNDAMENTALS (Week 1-2)
## ═══════════════════════════════════════

### 1A. Time & Space Complexity (Week 1 — 3 days)

```
CONCEPTS TO MASTER:
├── What is Big-O notation
├── O(1) → Constant     : Accessing array element
├── O(log n) → Logarithmic : Binary Search
├── O(n) → Linear       : Single loop
├── O(n log n) → Linearithmic : Merge Sort
├── O(n²) → Quadratic   : Nested loops
├── O(2ⁿ) → Exponential : Recursion without memo
├── O(n!) → Factorial   : Permutations
│
├── Space Complexity:
│   ├── Auxiliary space vs Total space
│   ├── Recursion stack space
│   └── In-place vs extra space algorithms
│
├── HOW TO ANALYZE:
│   ├── Single loop → O(n)
│   ├── Nested loop → O(n²)
│   ├── Loop with i = i*2 → O(log n)
│   ├── Two separate loops → O(n) + O(m)
│   └── Recursion → Draw recursion tree → count nodes
│
└── PRACTICE:
    └── Analyze complexity of 15-20 code snippets
```

**Test yourself:** Can you tell the complexity of this?
```cpp
for(int i = 0; i < n; i++) {          // O(n)
    for(int j = i; j < n; j++) {      // O(n) — but starts from i
        cout << i << j;               // O(1)
    }
}
// Answer: O(n²) — n + (n-1) + (n-2) + ... + 1 = n(n+1)/2
```

### 1B. Basic Mathematics for DSA (Week 1 — 2 days)

```
MUST KNOW:
├── GCD / LCM (Euclidean algorithm)
├── Prime numbers / Sieve of Eratosthenes
├── Modular arithmetic (why we use 10⁹+7)
├── Power function (fast exponentiation)
├── Factorial / nCr / nPr
├── Count digits
├── Palindrome number
├── Armstrong number
└── Reverse a number

PRACTICE: 15-20 problems
```

### 1C. Sorting Algorithms (Week 2 — FULL WEEK) ⚠️ CRITICAL

```
MUST IMPLEMENT FROM SCRATCH:
│
├── 1. Bubble Sort      → O(n²)   — Understand swapping
├── 2. Selection Sort   → O(n²)   — Find min, place it
├── 3. Insertion Sort   → O(n²)   — Insert in sorted portion
├── 4. Merge Sort       → O(n log n) — DIVIDE & CONQUER ⭐
├── 5. Quick Sort       → O(n log n) avg — PARTITION ⭐
├── 6. Counting Sort    → O(n+k)  — Non-comparison based
│
├── KNOW BUT DON'T IMPLEMENT:
│   ├── Radix Sort
│   ├── Bucket Sort
│   └── Heap Sort (learn when you reach Heaps)
│
├── UNDERSTAND:
│   ├── Stable vs Unstable sorting
│   ├── In-place vs Not in-place
│   ├── When to use which sort
│   └── Why O(n log n) is the best comparison-based limit
│
└── ⚡ KEY INSIGHT:
    Merge Sort teaches DIVIDE & CONQUER
    Quick Sort teaches PARTITIONING
    Both patterns appear in 100+ problems later
```

**Week 1-2 Problem Target: 40-50 problems**

---

## ═══════════════════════════════════════
## PHASE 2: ARRAYS + STRINGS (Week 3-5)
## ═══════════════════════════════════════

### 2A. Arrays — Easy Level (Week 3)

```
CONCEPTS:
├── Array traversal, insertion, deletion
├── Finding max, min, second largest
├── Reverse an array
├── Rotate array by K positions
├── Remove duplicates from sorted array
├── Move zeros to end
├── Check if array is sorted
├── Merge two sorted arrays
└── Missing number in array

PATTERNS TO LEARN:
├── Brute Force → think of simplest solution first
├── Frequency Array → count occurrences
└── Basic iteration patterns
```

### 2B. Arrays — Medium Level (Week 4)

```
PATTERNS:
├── 🔥 TWO POINTERS
│   ├── Two Sum (sorted array)
│   ├── Container With Most Water
│   ├── 3Sum
│   ├── Trapping Rain Water
│   └── Remove duplicates
│
├── 🔥 SLIDING WINDOW
│   ├── Max sum subarray of size K (fixed window)
│   ├── Longest substring without repeating chars (variable)
│   ├── Minimum window substring
│   ├── Maximum of all subarrays of size K
│   └── Count subarrays with sum = K
│
├── 🔥 PREFIX SUM
│   ├── Range sum queries
│   ├── Subarray sum equals K
│   ├── Product of array except self
│   └── Equilibrium index
│
├── 🔥 KADANE'S ALGORITHM
│   ├── Maximum subarray sum
│   ├── Maximum circular subarray sum
│   └── Maximum product subarray
│
├── 🔥 DUTCH NATIONAL FLAG
│   ├── Sort 0s, 1s, 2s
│   └── Partition around pivot
│
└── 🔥 MOORE'S VOTING ALGORITHM
    ├── Majority element (> n/2)
    └── Majority element II (> n/3)
```

### 2C. Strings (Week 5)

```
CONCEPTS:
├── String traversal, comparison
├── Palindrome check
├── Reverse words in a string
├── Anagram check
├── Character frequency counting
├── String to integer (atoi)
├── Longest common prefix
├── String compression
├── Valid parentheses (intro to stack thinking)
└── Isomorphic strings

KEY PATTERNS:
├── Frequency map on strings
├── Two pointer on strings (palindrome variations)
├── Sliding window on strings (longest substring problems)
└── StringBuilder / String manipulation tricks
```

**Week 3-5 Problem Target: 60-80 problems**

### 📝 MUST-SOLVE LEETCODE PROBLEMS (Arrays + Strings)

```
EASY (Do ALL):
├── 1. Two Sum
├── 26. Remove Duplicates from Sorted Array
├── 27. Remove Element
├── 53. Maximum Subarray (Kadane's)
├── 88. Merge Sorted Array
├── 121. Best Time to Buy and Sell Stock
├── 136. Single Number
├── 169. Majority Element
├── 217. Contains Duplicate
├── 283. Move Zeroes
├── 349. Intersection of Two Arrays
└── 448. Find All Numbers Disappeared in Array

MEDIUM (Do ALL):
├── 3. Longest Substring Without Repeating Characters
├── 11. Container With Most Water
├── 15. 3Sum
├── 33. Search in Rotated Sorted Array
├── 34. Find First and Last Position
├── 49. Group Anagrams
├── 56. Merge Intervals
├── 75. Sort Colors (Dutch National Flag)
├── 128. Longest Consecutive Sequence
├── 152. Maximum Product Subarray
├── 238. Product of Array Except Self
├── 347. Top K Frequent Elements
└── 560. Subarray Sum Equals K

HARD (Try after medium):
├── 42. Trapping Rain Water
├── 76. Minimum Window Substring
└── 239. Sliding Window Maximum
```

---

## ═══════════════════════════════════════
## PHASE 3: RECURSION & BACKTRACKING (Week 6-8)
## ═══════════════════════════════════════

### ⚠️ THIS IS THE MOST IMPORTANT PHASE — DON'T RUSH IT

```
WHY RECURSION IS THE BACKBONE OF DSA:
┌─────────────────────────────────────────────┐
│                                             │
│              RECURSION                      │
│                │                            │
│     ┌──────────┼──────────────┐             │
│     │          │              │             │
│   TREES     GRAPHS          DP             │
│  (all      (DFS is       (Memoized        │
│  traversals  recursive)   recursion)       │
│  are                                       │
│  recursive)                                │
│     │          │              │             │
│     └──────────┼──────────────┘             │
│              │                              │
│         BACKTRACKING                        │
│        (Recursion +                         │
│         Undo choices)                       │
│                                             │
│  If you DON'T master recursion,             │
│  you CANNOT do Trees, Graphs, or DP.        │
│  PERIOD.                                    │
└─────────────────────────────────────────────┘
```

### 3A. Basic Recursion (Week 6)

```
BUILD INTUITION STEP BY STEP:

LEVEL 1 — Simple recursion:
├── Print 1 to N
├── Print N to 1
├── Sum of first N numbers
├── Factorial
├── Fibonacci
├── Power of a number
├── Count digits
└── Sum of digits

LEVEL 2 — Recursion on arrays/strings:
├── Check if array is sorted
├── Linear search using recursion
├── Reverse a string recursively
├── Check palindrome recursively
├── Sum of array elements
└── Find max/min recursively

LEVEL 3 — Multiple recursion calls:
├── Fibonacci (see how tree branches)
├── Tower of Hanoi
├── Print all subsequences of a string
└── Power set

MENTAL MODEL:
┌────────────────────────────────────────┐
│  Every recursive function has:        │
│                                        │
│  1. BASE CASE — When to stop          │
│  2. RECURSIVE CASE — Make problem     │
│     smaller + call yourself           │
│  3. TRUST — Assume the recursive      │
│     call works correctly              │
│                                        │
│  Think: "If I solve for n-1,          │
│         how do I solve for n?"        │
└────────────────────────────────────────┘
```

### 3B. Intermediate Recursion (Week 7)

```
LEVEL 4 — Recursion with choices (PICK / NOT PICK):
├── Print all subsequences
├── Print subsequences with sum = K
├── Count subsequences with sum = K
├── Subset Sum I (does a subset with sum S exist?)
├── Subset Sum II (all unique subsets)
├── Combination Sum I (unlimited picks)
├── Combination Sum II (limited picks)
└── Letter Combinations of a Phone Number

THIS "PICK / NOT PICK" PATTERN IS THE FOUNDATION OF DP!
```

### 3C. Backtracking (Week 8)

```
CONCEPT:
├── Try a choice → Recurse → If dead end → UNDO choice → Try next
│
├── Template:
│   void backtrack(state, choices):
│       if (goal reached):
│           add to result
│           return
│       for each choice in choices:
│           if (choice is valid):
│               make choice
│               backtrack(new_state, remaining_choices)
│               undo choice  ← THIS IS BACKTRACKING
│
PROBLEMS:
├── Permutations (LC 46)
├── Permutations II — with duplicates (LC 47)
├── N-Queens (LC 51) ⭐ CLASSIC
├── Sudoku Solver (LC 37)
├── Word Search (LC 79)
├── Palindrome Partitioning (LC 131)
├── Rat in a Maze
├── Generate Parentheses (LC 22)
└── Combination Sum variants
```

**Week 6-8 Problem Target: 40-50 problems**

---

## ═══════════════════════════════════════
## PHASE 4: LINEAR DATA STRUCTURES (Week 9-11)
## ═══════════════════════════════════════

### 4A. Linked List (Week 9)

```
CONCEPTS:
├── Singly Linked List:
│   ├── Insertion (head, tail, middle)
│   ├── Deletion (head, tail, middle)
│   ├── Traversal
│   ├── Search
│   └── Length
│
├── Doubly Linked List:
│   ├── Insertion / Deletion
│   └── Reverse
│
├── IMPORTANT PATTERNS:
│   ├── 🔥 SLOW-FAST POINTER (Tortoise & Hare)
│   │   ├── Find middle of LL
│   │   ├── Detect cycle (LC 141)
│   │   ├── Find cycle start (LC 142)
│   │   └── Check palindrome LL
│   │
│   ├── 🔥 REVERSE LINKED LIST
│   │   ├── Reverse full list (LC 206)
│   │   ├── Reverse in groups of K (LC 25)
│   │   └── Reverse between positions (LC 92)
│   │
│   └── 🔥 MERGE PATTERN
│       ├── Merge two sorted lists (LC 21)
│       ├── Merge K sorted lists (LC 23)
│       └── Sort a linked list (LC 148) — Merge Sort on LL
│
MUST-SOLVE:
├── LC 206 — Reverse Linked List
├── LC 21  — Merge Two Sorted Lists
├── LC 141 — Linked List Cycle
├── LC 142 — Linked List Cycle II
├── LC 19  — Remove Nth Node From End
├── LC 876 — Middle of Linked List
├── LC 234 — Palindrome Linked List
├── LC 148 — Sort List
├── LC 25  — Reverse Nodes in K-Group
└── LC 138 — Copy List with Random Pointer
```

### 4B. Stack (Week 10)

```
CONCEPTS:
├── LIFO principle
├── Implementation (array-based and linked list-based)
├── Standard operations: push, pop, top, isEmpty
│
├── APPLICATIONS:
│   ├── Balanced parentheses (LC 20)
│   ├── Next Greater Element (LC 496, 503) ⭐
│   ├── Next Smaller Element
│   ├── Stock Span Problem
│   ├── Largest Rectangle in Histogram (LC 84) ⭐⭐
│   ├── Min Stack (LC 155)
│   ├── Evaluate Reverse Polish Notation (LC 150)
│   ├── Daily Temperatures (LC 739)
│   └── Asteroid Collision (LC 735)
│
├── 🔥 MONOTONIC STACK PATTERN:
│   ├── Maintain a stack that is always increasing or decreasing
│   ├── Used for "next greater", "next smaller", "span" problems
│   ├── Template:
│   │   for each element:
│   │       while stack not empty AND stack.top() < current:
│   │           process stack.top()
│   │           stack.pop()
│   │       stack.push(current)
│   └── This ONE pattern solves 20+ problems
│
└── TRAPPING RAIN WATER using stack approach
```

### 4C. Queue & Deque (Week 10-11)

```
CONCEPTS:
├── FIFO principle
├── Implementation: circular array, linked list
├── Operations: enqueue, dequeue, front, rear
│
├── VARIANTS:
│   ├── Circular Queue
│   ├── Deque (Double-ended queue)
│   └── Priority Queue (→ covered in Heaps)
│
├── APPLICATIONS:
│   ├── BFS (Breadth First Search) — most important use
│   ├── Sliding Window Maximum using deque (LC 239)
│   ├── First non-repeating character in stream
│   ├── Implement Stack using Queues (LC 225)
│   └── Implement Queue using Stacks (LC 232)
│
└── 🔥 KEY INSIGHT:
    Queue = BFS
    Stack = DFS
    Remember this. It's used EVERYWHERE in Trees & Graphs.
```

### 4D. Binary Search Deep Dive (Week 11)

```
BEYOND BASIC BINARY SEARCH:
│
├── CATEGORY 1 — Search in sorted arrays:
│   ├── Basic binary search (LC 704)
│   ├── Search Insert Position (LC 35)
│   ├── First & Last Position (LC 34)
│   ├── Search in Rotated Sorted Array (LC 33)
│   ├── Find Minimum in Rotated Sorted Array (LC 153)
│   ├── Search a 2D Matrix (LC 74)
│   └── Peak Element (LC 162)
│
├── CATEGORY 2 — Binary Search on Answer ⭐⭐ (VERY IMP):
│   ├── Square Root (LC 69)
│   ├── Koko Eating Bananas (LC 875)
│   ├── Minimum Days to Make M Bouquets
│   ├── Capacity to Ship Packages (LC 1011)
│   ├── Split Array Largest Sum (LC 410)
│   ├── Aggressive Cows (classic)
│   ├── Book Allocation Problem (classic)
│   ├── Painter's Partition
│   └── Median of Two Sorted Arrays (LC 4) — HARD
│
│   TEMPLATE FOR "BS ON ANSWER":
│   ├── Identify: answer lies in range [min, max]
│   ├── Binary search on this range
│   ├── For each mid, check: "Is this answer feasible?"
│   ├── If yes → try smaller (go left)
│   ├── If no → try larger (go right)
│   └── This pattern is ASKED IN EVERY INTERVIEW
│
└── CATEGORY 3 — Binary Search on real numbers:
    ├── Nth root of a number
    └── Median in row-wise sorted matrix
```

**Week 9-11 Problem Target: 60-70 problems**

---

## ═══════════════════════════════════════
## PHASE 5: NON-LINEAR DS (Week 12-17)
## ═══════════════════════════════════════

### 5A. Hashing (Week 12)

```
CONCEPTS:
├── Hash Table / Hash Map — how it works internally
├── Hash function, collision handling (chaining, open addressing)
├── Time complexity: O(1) average for insert/search/delete
│
├── APPLICATIONS:
│   ├── Two Sum (LC 1)
│   ├── Group Anagrams (LC 49)
│   ├── Longest Consecutive Sequence (LC 128)
│   ├── Subarray Sum Equals K (LC 560)
│   ├── Valid Anagram (LC 242)
│   ├── Top K Frequent Elements (LC 347)
│   ├── Longest Substring Without Repeating Characters (LC 3)
│   └── First Unique Character (LC 387)
│
└── 🔥 MENTAL MODEL:
    "If you need O(1) lookup → think HashMap"
    "If you need to count frequencies → think HashMap"
    "If you need to check existence → think HashSet"
```

### 5B. Trees (Week 13-14) ⭐⭐ VERY HIGH WEIGHTAGE IN INTERVIEWS

```
WEEK 13 — Tree Basics & Traversals:
│
├── CONCEPTS:
│   ├── Binary Tree terminology (root, node, leaf, height, depth)
│   ├── Binary Tree vs Binary Search Tree (BST)
│   ├── Complete, Full, Perfect, Balanced trees
│   └── Height vs Depth
│
├── TRAVERSALS (implement ALL 4 both recursively AND iteratively):
│   ├── Inorder (Left → Root → Right)    — gives sorted order in BST
│   ├── Preorder (Root → Left → Right)   — used for serialization
│   ├── Postorder (Left → Right → Root)  — used for deletion
│   └── Level Order (BFS using Queue)    — level-by-level
│
├── BASIC PROBLEMS:
│   ├── Height of binary tree (LC 104)
│   ├── Diameter of binary tree (LC 543)
│   ├── Check balanced tree (LC 110)
│   ├── Same tree (LC 100)
│   ├── Symmetric tree (LC 101)
│   ├── Invert binary tree (LC 226)
│   ├── Path sum (LC 112)
│   └── Count nodes (LC 222)

WEEK 14 — Advanced Trees & BST:
│
├── MEDIUM/HARD TREE PROBLEMS:
│   ├── Lowest Common Ancestor (LC 236) ⭐
│   ├── Binary Tree Right Side View (LC 199)
│   ├── Zigzag Level Order (LC 103)
│   ├── Flatten Binary Tree to Linked List (LC 114)
│   ├── Construct Tree from Inorder + Preorder (LC 105)
│   ├── Construct Tree from Inorder + Postorder (LC 106)
│   ├── Maximum Path Sum (LC 124) — HARD
│   ├── Serialize and Deserialize (LC 297)
│   └── Vertical Order Traversal (LC 987)
│
├── BST SPECIFIC:
│   ├── Search in BST (LC 700)
│   ├── Insert into BST (LC 701)
│   ├── Delete from BST (LC 450)
│   ├── Validate BST (LC 98) ⭐
│   ├── Kth Smallest in BST (LC 230)
│   ├── LCA in BST (LC 235)
│   ├── Inorder Successor in BST
│   └── Convert Sorted Array to BST (LC 108)
│
└── 🔥 TREE PROBLEM-SOLVING FRAMEWORK:
    Step 1: Can I solve it with a traversal? (DFS or BFS)
    Step 2: Do I need info from children? → POSTORDER
    Step 3: Do I need info from parent? → Pass as parameter
    Step 4: Do I need level info? → BFS with queue
    Step 5: Is it a BST? → Use BST property (inorder = sorted)
```

### 5C. Heaps / Priority Queue (Week 15)

```
CONCEPTS:
├── Complete Binary Tree property
├── Max Heap vs Min Heap
├── Heapify: O(log n)
├── Build Heap: O(n) — NOT O(n log n)!
├── Heap Sort: O(n log n)
│
├── OPERATIONS:
│   ├── Insert: O(log n)
│   ├── Extract Max/Min: O(log n)
│   ├── Peek: O(1)
│   └── Build from array: O(n)
│
├── PROBLEMS:
│   ├── Kth Largest Element (LC 215) ⭐
│   ├── Top K Frequent Elements (LC 347)
│   ├── K Closest Points to Origin (LC 973)
│   ├── Find Median from Data Stream (LC 295) ⭐⭐
│   ├── Merge K Sorted Lists (LC 23)
│   ├── Sort Nearly Sorted Array
│   ├── Task Scheduler (LC 621)
│   ├── Reorganize String (LC 767)
│   └── Kth Smallest Element in Sorted Matrix (LC 378)
│
└── 🔥 WHEN TO USE HEAP:
    "Anything with K largest/smallest" → HEAP
    "Anything with streaming data + top K" → HEAP
    "Merge K sorted things" → HEAP
    "Running median" → TWO HEAPS (max + min)
```

### 5D. Tries / Prefix Trees (Week 15)

```
CONCEPTS:
├── Trie is a tree where each node represents a character
├── Used for: prefix search, autocomplete, spell checker, word games
│
├── OPERATIONS:
│   ├── Insert: O(word length)
│   ├── Search: O(word length)
│   └── StartsWith: O(prefix length)
│
├── IMPLEMENT FROM SCRATCH:
│   struct TrieNode {
│       TrieNode* children[26];  // for lowercase English
│       bool isEnd;
│   };
│
├── PROBLEMS:
│   ├── Implement Trie (LC 208) ⭐
│   ├── Word Search II (LC 212)
│   ├── Design Add and Search Words (LC 211)
│   ├── Longest Word in Dictionary (LC 720)
│   └── Replace Words (LC 648)
│
└── NOT many problems, but it's asked frequently in interviews.
    Learn to implement from scratch = instant interview points.
```

### 5E. Graphs (Week 16-17) ⭐⭐⭐ HIGHEST WEIGHTAGE TOPIC

```
WEEK 16 — Graph Basics:
│
├── REPRESENTATIONS:
│   ├── Adjacency Matrix — O(V²) space, O(1) edge lookup
│   ├── Adjacency List — O(V+E) space, most common ⭐
│   └── Edge List — used in Kruskal's
│
├── BFS (Breadth First Search):
│   ├── Uses QUEUE
│   ├── Level-by-level traversal
│   ├── Finds shortest path in UNWEIGHTED graphs
│   ├── Template:
│   │   queue.push(start)
│   │   visited[start] = true
│   │   while queue not empty:
│   │       node = queue.front(); queue.pop()
│   │       for each neighbor of node:
│   │           if not visited:
│   │               visited[neighbor] = true
│   │               queue.push(neighbor)
│   │
│   ├── Problems:
│   │   ├── Number of Islands (LC 200) ⭐
│   │   ├── Rotting Oranges (LC 994) ⭐
│   │   ├── 01 Matrix (LC 542)
│   │   ├── Word Ladder (LC 127)
│   │   └── Shortest Path in Binary Matrix (LC 1091)
│
├── DFS (Depth First Search):
│   ├── Uses STACK (or recursion)
│   ├── Go deep, then backtrack
│   ├── Template (recursive):
│   │   void dfs(node):
│   │       visited[node] = true
│   │       for each neighbor:
│   │           if not visited:
│   │               dfs(neighbor)
│   │
│   ├── Problems:
│   │   ├── Number of Islands (LC 200)
│   │   ├── Clone Graph (LC 133)
│   │   ├── Pacific Atlantic Water Flow (LC 417)
│   │   ├── Surrounded Regions (LC 130)
│   │   └── Number of Provinces (LC 547)
│
├── CYCLE DETECTION:
│   ├── Undirected graph → DFS/BFS with parent tracking
│   └── Directed graph → DFS with coloring (white/gray/black)
│
└── CONNECTED COMPONENTS:
    └── Count components using DFS/BFS

WEEK 17 — Advanced Graph Algorithms:
│
├── TOPOLOGICAL SORT ⭐⭐ (VERY IMP FOR INTERVIEWS):
│   ├── Only for DAG (Directed Acyclic Graph)
│   ├── Kahn's Algorithm (BFS with indegree)
│   ├── DFS-based approach
│   ├── Problems:
│   │   ├── Course Schedule (LC 207) ⭐
│   │   ├── Course Schedule II (LC 210)
│   │   ├── Alien Dictionary
│   │   └── Task ordering problems
│
├── SHORTEST PATH ALGORITHMS:
│   ├── BFS → unweighted graphs (already covered)
│   ├── Dijkstra → weighted graphs, NO negative edges ⭐
│   │   ├── Uses Priority Queue (Min Heap)
│   │   ├── Time: O((V+E) log V)
│   │   ├── Network Delay Time (LC 743)
│   │   └── Cheapest Flights Within K Stops (LC 787)
│   │
│   ├── Bellman-Ford → handles NEGATIVE edges
│   │   ├── Time: O(V * E)
│   │   ├── Detects negative cycles
│   │   └── Cheapest Flights problem variant
│   │
│   └── Floyd-Warshall → ALL pairs shortest path
│       ├── Time: O(V³)
│       └── Small graphs only
│
├── MINIMUM SPANNING TREE (MST):
│   ├── Prim's Algorithm (Priority Queue based)
│   ├── Kruskal's Algorithm (Sort edges + Union-Find)
│   └── Min Cost to Connect All Points (LC 1584)
│
├── UNION-FIND / DISJOINT SET UNION (DSU) ⭐:
│   ├── Operations: find(), union()
│   ├── Optimizations: path compression, union by rank
│   ├── Problems:
│   │   ├── Number of Connected Components
│   │   ├── Redundant Connection (LC 684)
│   │   ├── Accounts Merge (LC 721)
│   │   └── Number of Islands II
│   │
│   └── Template:
│       int parent[N], rank[N];
│       int find(int x):
│           if parent[x] != x:
│               parent[x] = find(parent[x])  // path compression
│           return parent[x]
│       void union(int x, int y):
│           px = find(x), py = find(y)
│           if rank[px] < rank[py]: swap
│           parent[py] = px
│           if rank[px] == rank[py]: rank[px]++
│
└── GRAPH SUMMARY:
    ┌────────────────────────────────────────────┐
    │ PROBLEM TYPE        → ALGORITHM            │
    ├────────────────────────────────────────────┤
    │ Traversal           → BFS / DFS            │
    │ Shortest (unweight) → BFS                  │
    │ Shortest (weighted) → Dijkstra             │
    │ Shortest (neg edge) → Bellman-Ford         │
    │ All pairs shortest  → Floyd-Warshall       │
    │ Cycle detection     → DFS coloring         │
    │ Topological order   → Kahn's (BFS)         │
    │ MST                 → Prim's / Kruskal's   │
    │ Components/Groups   → Union-Find / DFS     │
    └────────────────────────────────────────────┘
```

**Week 12-17 Problem Target: 80-100 problems**

---

## ═══════════════════════════════════════
## PHASE 6: DYNAMIC PROGRAMMING (Week 18-23)
## ═══════════════════════════════════════

### ⚠️ DP IS THE HARDEST TOPIC — TAKE YOUR TIME

```
THE SECRET TO DP:
┌─────────────────────────────────────────────────────────┐
│                                                         │
│  DP = Recursion + Memoization                          │
│                                                         │
│  STEP 1: Write recursive solution (brute force)        │
│  STEP 2: Add memoization (cache results)               │
│  STEP 3: Convert to tabulation (bottom-up)             │
│  STEP 4: Optimize space if possible                    │
│                                                         │
│  If you followed Phase 3 (Recursion) properly,         │
│  DP will feel like a NATURAL EXTENSION.                 │
│  If you skipped recursion, DP will feel IMPOSSIBLE.     │
│                                                         │
└─────────────────────────────────────────────────────────┘
```

### 6A. 1D DP (Week 18-19)

```
LEARN THE FRAMEWORK:
│
├── PROBLEM: Climbing Stairs (LC 70)
│
│   STEP 1 — Recursion:
│   int solve(n):
│       if n <= 1: return 1
│       return solve(n-1) + solve(n-2)
│   // Time: O(2ⁿ) — TOO SLOW
│
│   STEP 2 — Memoization (Top-Down):
│   int solve(n, dp[]):
│       if n <= 1: return 1
│       if dp[n] != -1: return dp[n]
│       return dp[n] = solve(n-1, dp) + solve(n-2, dp)
│   // Time: O(n), Space: O(n)
│
│   STEP 3 — Tabulation (Bottom-Up):
│   dp[0] = 1, dp[1] = 1
│   for i = 2 to n:
│       dp[i] = dp[i-1] + dp[i-2]
│   return dp[n]
│   // Time: O(n), Space: O(n)
│
│   STEP 4 — Space Optimization:
│   prev2 = 1, prev1 = 1
│   for i = 2 to n:
│       curr = prev1 + prev2
│       prev2 = prev1
│       prev1 = curr
│   return prev1
│   // Time: O(n), Space: O(1) ✅
│
├── 1D DP PROBLEMS:
│   ├── Climbing Stairs (LC 70)
│   ├── House Robber (LC 198) ⭐
│   ├── House Robber II (LC 213)
│   ├── Coin Change (LC 322) ⭐
│   ├── Coin Change II (LC 518)
│   ├── Longest Increasing Subsequence (LC 300) ⭐⭐
│   ├── Word Break (LC 139)
│   ├── Decode Ways (LC 91)
│   ├── Maximum Product Subarray (LC 152)
│   ├── Partition Equal Subset Sum (LC 416)
│   ├── Perfect Squares (LC 279)
│   └── Min Cost Climbing Stairs (LC 746)
```

### 6B. 2D DP (Week 20-21)

```
2D DP PROBLEMS:
│
├── GRID DP:
│   ├── Unique Paths (LC 62)
│   ├── Unique Paths II (LC 63)
│   ├── Minimum Path Sum (LC 64)
│   ├── Triangle (LC 120)
│   ├── Maximal Square (LC 221)
│   └── Dungeon Game (LC 174)
│
├── STRING DP:
│   ├── Longest Common Subsequence (LC 1143) ⭐⭐
│   ├── Edit Distance (LC 72) ⭐⭐
│   ├── Longest Palindromic Subsequence (LC 516)
│   ├── Longest Palindromic Substring (LC 5)
│   ├── Shortest Common Supersequence (LC 1092)
│   ├── Distinct Subsequences (LC 115)
│   └── Wildcard Matching (LC 44)
│
├── KNAPSACK FAMILY ⭐⭐⭐ (MOST IMPORTANT DP PATTERN):
│   ├── 0/1 Knapsack (classic)
│   │   ├── For each item: PICK or NOT PICK
│   │   ├── dp[i][w] = max(dp[i-1][w], value[i] + dp[i-1][w-weight[i]])
│   │   └── Target Sum (LC 494) — variant
│   │
│   ├── Unbounded Knapsack:
│   │   ├── Can pick same item multiple times
│   │   ├── Coin Change (LC 322)
│   │   └── Coin Change II (LC 518)
│   │
│   └── Subset Sum:
│       ├── Partition Equal Subset Sum (LC 416)
│       └── Last Stone Weight II (LC 1049)
│
├── LIS (Longest Increasing Subsequence) FAMILY:
│   ├── LIS (LC 300) — O(n²) DP, O(n log n) with binary search
│   ├── Longest String Chain (LC 1048)
│   ├── Russian Doll Envelopes (LC 354)
│   └── Number of LIS (LC 673)
```

### 6C. Advanced DP (Week 22-23)

```
├── DP ON TREES:
│   ├── Diameter of Binary Tree (already solved, but see DP angle)
│   ├── Binary Tree Maximum Path Sum (LC 124)
│   ├── House Robber III (LC 337) — DP on tree
│   └── Longest Path With Same Value
│
├── PARTITION DP:
│   ├── Matrix Chain Multiplication (classic)
│   ├── Burst Balloons (LC 312) ⭐
│   ├── Palindrome Partitioning II (LC 132)
│   ├── Minimum Cost to Cut a Stick (LC 1547)
│   └── Boolean Parenthesization
│
├── DP ON STOCKS ⭐ (Complete all 6 variants):
│   ├── LC 121 — Buy and Sell Stock I (one transaction)
│   ├── LC 122 — Buy and Sell Stock II (unlimited transactions)
│   ├── LC 123 — Buy and Sell Stock III (at most 2 transactions)
│   ├── LC 188 — Buy and Sell Stock IV (at most K transactions)
│   ├── LC 309 — With Cooldown
│   └── LC 714 — With Transaction Fee
│
└── DP PROBLEM IDENTIFICATION CHEAT SHEET:
    ┌─────────────────────────────────────────────────┐
    │ CLUE IN PROBLEM          → DP TYPE              │
    ├─────────────────────────────────────────────────┤
    │ "Count ways"             → DP (add choices)     │
    │ "Minimum/Maximum"        → DP (min/max choices) │
    │ "Can you...? (Yes/No)"   → DP (OR choices)      │
    │ "Longest/Shortest"       → DP                   │
    │ "Subsequence"            → Pick/Not Pick DP     │
    │ "Partition into groups"  → Partition DP          │
    │ "String matching"        → 2D String DP         │
    │ "Using items with limit" → Knapsack DP          │
    └─────────────────────────────────────────────────┘
```

**Week 18-23 Problem Target: 60-80 problems**

---

## ═══════════════════════════════════════
## PHASE 7: ADVANCED TOPICS + REVISION (Week 24-26)
## ═══════════════════════════════════════

### 7A. Greedy Algorithms (Week 24)

```
CONCEPT:
├── Make locally optimal choice at each step
├── Hope it leads to globally optimal solution
├── PROOF: Usually by contradiction or exchange argument
│
├── KEY DIFFERENCE FROM DP:
│   DP: Try ALL choices → pick best
│   Greedy: Pick BEST choice now → never look back
│
├── PROBLEMS:
│   ├── Activity Selection / Meeting Rooms
│   ├── Jump Game (LC 55)
│   ├── Jump Game II (LC 45)
│   ├── Gas Station (LC 134)
│   ├── Candy (LC 135)
│   ├── Task Scheduler (LC 621)
│   ├── Hand of Straights (LC 846)
│   ├── Merge Triplets (LC 1899)
│   ├── Partition Labels (LC 763) ⭐
│   ├── Valid Parenthesis String (LC 678)
│   ├── Non-overlapping Intervals (LC 435) ⭐
│   └── Minimum Platforms (classic)
│
└── GREEDY vs DP — HOW TO TELL:
    If greedy FAILS (can construct counter-example) → use DP
    If greedy WORKS (can prove it) → use Greedy (simpler)
```

### 7B. Bit Manipulation (Week 24-25)

```
CONCEPTS:
├── AND (&), OR (|), XOR (^), NOT (~)
├── Left shift (<<), Right shift (>>)
├── Check if bit is set: (n >> i) & 1
├── Set a bit: n | (1 << i)
├── Clear a bit: n & ~(1 << i)
├── Toggle a bit: n ^ (1 << i)
│
├── KEY PROPERTIES:
│   ├── a ^ a = 0 (XOR with itself = 0)
│   ├── a ^ 0 = a (XOR with 0 = itself)
│   ├── n & (n-1) removes last set bit
│   └── n & (-n) isolates last set bit
│
├── PROBLEMS:
│   ├── Single Number (LC 136)
│   ├── Single Number II (LC 137)
│   ├── Single Number III (LC 260)
│   ├── Counting Bits (LC 338)
│   ├── Missing Number (LC 268)
│   ├── Reverse Bits (LC 190)
│   ├── Number of 1 Bits (LC 191)
│   ├── Sum of Two Integers without + (LC 371)
│   └── Power of Two (LC 231)
```

### 7C. String Algorithms (Week 25)

```
ADVANCED STRING ALGORITHMS (Know at least KMP):
│
├── KMP (Knuth-Morris-Pratt) ⭐:
│   ├── Pattern matching in O(n+m)
│   ├── LPS (Longest Prefix Suffix) array
│   ├── Find Pattern in String (LC 28)
│   └── Repeated Substring Pattern (LC 459)
│
├── Rabin-Karp:
│   ├── Rolling hash for pattern matching
│   └── Good for multiple pattern search
│
├── Z-Algorithm:
│   ├── Z-array computation
│   └── Pattern matching variant
│
└── For interviews: KMP is enough. Others are for competitive.
```

### 7D. Revision Strategy (Week 25-26)

```
REVISION IS NOT OPTIONAL — IT'S THE MOST IMPORTANT PHASE

STRATEGY:
├── Re-solve ALL problems you struggled with (keep a "hard" list)
├── Do 3-4 random LeetCode mediums daily
├── Time yourself: 20-25 min per medium, 40 min per hard
├── Practice explaining your approach OUT LOUD
│
├── SPACED REPETITION:
│   ├── Day 1: Solve new problem
│   ├── Day 3: Re-solve without looking
│   ├── Day 7: Re-solve again
│   ├── Day 30: Final revision
│   └── If you can solve it in < 10 min → you've mastered it
│
└── WEEKLY MOCK INTERVIEW:
    ├── Use Pramp (free) or Interviewing.io
    ├── Or practice with a friend
    └── Simulate real interview: 45 min, 2 problems, explain aloud
```

---

# PART 3: DAILY SCHEDULE TEMPLATE

```
╔═══════════════════════════════════════════════════════════╗
║                  WEEKDAY SCHEDULE (3-4 hours)             ║
╠═══════════════════════════════════════════════════════════╣
║                                                           ║
║  ⏰ SESSION 1 (1 hour) — LEARN                           ║
║  ├── Watch concept video (Striver/NeetCode)              ║
║  ├── Take notes in your own words                        ║
║  └── Understand the pattern/template                     ║
║                                                           ║
║  ⏰ SESSION 2 (1.5-2 hours) — SOLVE                     ║
║  ├── Solve 2-3 problems on that topic                    ║
║  ├── For each problem:                                   ║
║  │   ├── Read → Think 10 min → Attempt                  ║
║  │   ├── If stuck 30 min → Watch solution video          ║
║  │   ├── Code it yourself (DON'T copy-paste)             ║
║  │   └── Analyze time & space complexity                 ║
║  └── Push solutions to GitHub                            ║
║                                                           ║
║  ⏰ SESSION 3 (30 min) — REVISE                         ║
║  ├── Re-solve 1-2 problems from previous days            ║
║  └── Update progress tracker                             ║
║                                                           ║
╠═══════════════════════════════════════════════════════════╣
║                  WEEKEND SCHEDULE (5-6 hours)             ║
╠═══════════════════════════════════════════════════════════╣
║                                                           ║
║  ⏰ Morning (3 hours):                                   ║
║  ├── Finish remaining problems from the week's topic     ║
║  └── Solve 4-5 new problems                              ║
║                                                           ║
║  ⏰ Afternoon (2-3 hours):                               ║
║  ├── Revision: re-solve week's hardest problems          ║
║  ├── 1 LeetCode contest (biweekly) — optional but good  ║
║  └── Update notes, clean up GitHub code                  ║
║                                                           ║
╚═══════════════════════════════════════════════════════════╝
```

---

# PART 4: ALL RESOURCES (ORGANIZED)

## 4.1 YouTube Channels (FREE — Better than any paid course)

```
TIER 1 — PRIMARY (Follow one as your main guide):
┌──────────────────────────────────────────────────────────────┐
│ 1. Take U Forward (Striver)                                  │
│    → THE BEST for DSA in India                               │
│    → Complete A2Z playlist: 350+ videos                      │
│    → Hindi + English mix                                     │
│    → Covers EVERY topic from scratch                         │
│    → YouTube: @takeUforward                                  │
│                                                              │
│ 2. NeetCode                                                  │
│    → THE BEST for pattern-based learning                     │
│    → Clean animations, short videos (10-15 min)              │
│    → English only                                            │
│    → YouTube: @NeetCode                                      │
└──────────────────────────────────────────────────────────────┘

TIER 2 — SUPPLEMENTARY (Use for specific topics):
┌──────────────────────────────────────────────────────────────┐
│ 3. Abdul Bari                                                │
│    → BEST for algorithm theory (complexity, sorting, DP)     │
│                                                              │
│ 4. Kunal Kushwaha                                            │
│    → BEST Java DSA bootcamp (if you chose Java)              │
│                                                              │
│ 5. Aditya Verma                                              │
│    → BEST playlist for Dynamic Programming                   │
│    → Also great for Binary Search, Sliding Window, Heap      │
│                                                              │
│ 6. William Fiset                                             │
│    → BEST for Graph algorithms (deep & visual)               │
│                                                              │
│ 7. Errichto                                                  │
│    → BEST for competitive programming                        │
│                                                              │
│ 8. Pepcoding (for Hindi learners)                            │
│    → Level-wise DSA with great explanations                  │
└──────────────────────────────────────────────────────────────┘

TIER 3 — ACADEMIC (For deep understanding):
┌──────────────────────────────────────────────────────────────┐
│ 9. MIT OCW 6.006 (Introduction to Algorithms)                │
│    → Gold standard for algorithm theory                      │
│                                                              │
│ 10. MIT OCW 6.046 (Design & Analysis of Algorithms)          │
│    → Advanced algorithms                                     │
└──────────────────────────────────────────────────────────────┘
```

## 4.2 GitHub Repositories

```
🥇 PRIMARY REPOS (Star these NOW):

1. Striver A2Z DSA Sheet Solutions:
   github.com/es-amit/Striver-A2Z-DSA-Sheet
   github.com/Codensity30/Strivers-A2Z-DSA-Sheet
   → Use for: Topic order + solution reference

2. NeetCode Solutions:
   github.com/neetcode-gh/leetcode
   → Use for: Pattern-based solutions, clean code

3. TheAlgorithms:
   github.com/TheAlgorithms/Python
   github.com/TheAlgorithms/C-Plus-Plus
   github.com/TheAlgorithms/Java
   → Use for: Clean implementations of every algorithm

4. Coding Interview University:
   github.com/jwasham/coding-interview-university
   → Use for: Overall CS study plan

5. Tech Interview Handbook:
   github.com/yangshun/tech-interview-handbook
   → Use for: Interview tips, behavioral questions

🥈 SECONDARY REPOS (Use when needed):

6. JavaScript Algorithms:
   github.com/trekhleb/javascript-algorithms
   → Beautiful visualizations of algorithms

7. LeetCode Patterns:
   github.com/seanprashad/leetcode-patterns
   → Categorized problems by pattern

8. Blind 75:
   No specific repo, but the list:
   neetcode.io/practice (NeetCode 150 includes Blind 75)

9. Kunal Kushwaha DSA Bootcamp:
   github.com/kunal-kushwaha/DSA-Bootcamp-Java
   → Great for Java learners

10. Algorithm Visualizer:
    github.com/algorithm-visualizer/algorithm-visualizer
    → SEE algorithms run visually
```

## 4.3 Practice Platforms

```
┌──────────────────────────────────────────────────────────────┐
│ PLATFORM         │ USE FOR                   │ PRIORITY     │
├──────────────────┼───────────────────────────┼──────────────┤
│ LeetCode         │ PRIMARY practice platform │ ⭐⭐⭐⭐⭐  │
│                  │ Interview-style problems  │              │
│                  │ Company-tagged questions   │              │
├──────────────────┼───────────────────────────┼──────────────┤
│ Coding Ninjas    │ Striver A2Z problems      │ ⭐⭐⭐⭐    │
│ (CodeStudio)     │ Free, with video hints    │              │
├──────────────────┼───────────────────────────┼──────────────┤
│ GeeksforGeeks    │ Company-specific problems │ ⭐⭐⭐⭐    │
│                  │ Indian company prep       │              │
├──────────────────┼───────────────────────────┼──────────────┤
│ Codeforces       │ Competitive programming   │ ⭐⭐⭐      │
│                  │ Contests, rating system   │              │
├──────────────────┼───────────────────────────┼──────────────┤
│ HackerRank       │ Absolute beginners        │ ⭐⭐⭐      │
│                  │ Language practice          │              │
├──────────────────┼───────────────────────────┼──────────────┤
│ InterviewBit     │ Structured DSA course     │ ⭐⭐⭐      │
│                  │ Good for beginners        │              │
└──────────────────┴───────────────────────────┴──────────────┘

MY RECOMMENDATION:
├── Month 1-2: LeetCode Easy + CodeStudio (Striver sheet)
├── Month 3-4: LeetCode Medium + Codeforces (optional contests)
├── Month 5-6: LeetCode Medium/Hard + Mock Interviews
└── Throughout: GFG for company-specific prep
```

## 4.4 Books (Optional but excellent)

```
IF YOU WANT TO READ:
├── "Cracking the Coding Interview" — Gayle Laakmann McDowell
│   → Best interview prep book ever written
│   → 189 programming questions with solutions
│
├── "Introduction to Algorithms" (CLRS) — Cormen et al.
│   → THE textbook for algorithms
│   → Use as reference, NOT as primary learning
│
├── "Algorithm Design Manual" — Steven Skiena
│   → More practical than CLRS
│   → Great war stories and real-world applications
│
└── "Competitive Programming 3" — Steven & Felix Halim
    → If you want to do competitive programming
```

---

# PART 5: COMPLETE PROBLEM LIST (300+ PROBLEMS)

## Organized by Topic with LeetCode Numbers

```
ARRAYS (35 problems):
├── Easy:
│   1, 26, 27, 53, 88, 121, 136, 169, 217, 283, 349, 448
├── Medium:
│   11, 15, 31, 48, 54, 56, 73, 75, 128, 152, 189, 238,
│   287, 347, 442, 560
└── Hard:
    42, 239, 41

STRINGS (15 problems):
├── Easy: 14, 20, 125, 242, 344, 387, 409
├── Medium: 3, 5, 49, 151, 271, 438
└── Hard: 76

BINARY SEARCH (18 problems):
├── Easy: 35, 69, 278, 374, 704
├── Medium: 33, 34, 74, 153, 162, 540, 875, 981, 1011
└── Hard: 4, 410

LINKED LIST (15 problems):
├── Easy: 21, 141, 160, 206, 234, 876
├── Medium: 2, 19, 138, 142, 143, 148, 287
└── Hard: 23, 25

STACK (12 problems):
├── Easy: 20, 155, 225, 232
├── Medium: 150, 496, 503, 739, 735, 394
└── Hard: 84, 85

RECURSION & BACKTRACKING (15 problems):
├── Medium: 17, 22, 39, 40, 46, 47, 77, 78, 79, 90, 131
└── Hard: 37, 51, 52, 212

TREES (30 problems):
├── Easy: 94, 100, 101, 104, 108, 110, 144, 226, 543, 572
├── Medium:
│   98, 102, 103, 105, 106, 114, 199, 230, 235, 236,
│   337, 450, 701, 987, 1448
└── Hard: 124, 297

TRIES (5 problems):
├── Medium: 208, 211, 648, 720
└── Hard: 212

HEAPS (12 problems):
├── Easy: 703, 1046
├── Medium: 215, 347, 355, 621, 767, 973, 1337
└── Hard: 23, 295, 378

GRAPHS (30 problems):
├── Medium:
│   130, 133, 200, 207, 210, 261, 323, 417, 547, 684,
│   695, 721, 743, 785, 787, 802, 841, 994, 1091, 1584
└── Hard: 127, 269, 332, 778

DYNAMIC PROGRAMMING (50 problems):
├── Easy: 70, 118, 119, 338, 392, 509, 746
├── Medium:
│   5, 62, 63, 64, 91, 97, 120, 139, 152, 198, 213,
│   221, 279, 300, 309, 322, 416, 474, 494, 518, 583,
│   647, 714, 740, 1048, 1143
└── Hard:
    10, 44, 72, 115, 123, 124, 132, 188, 312, 329,
    354, 1092, 1547

GREEDY (15 problems):
├── Medium:
│   45, 55, 134, 435, 452, 621, 678, 763, 846, 1899
└── Hard: 135, 502

BIT MANIPULATION (10 problems):
├── Easy: 136, 190, 191, 231, 268, 338, 389
├── Medium: 137, 260, 371
```

---

# PART 6: COMMON MISTAKES TO AVOID

```
❌ MISTAKE 1: "I'll learn 3 languages for DSA"
✅ FIX: Pick ONE. Stick to it for 6 months. Period.

❌ MISTAKE 2: "Let me solve random LeetCode problems"
✅ FIX: Follow a structured sheet (Striver A2Z or NeetCode 150).
        Random solving = random results.

❌ MISTAKE 3: "I'll look at the solution after 5 minutes"
✅ FIX: Struggle for at least 20-30 minutes on Easy, 
        40-60 minutes on Medium. The struggle IS the learning.

❌ MISTAKE 4: "I solved it, moving on forever"
✅ FIX: Re-solve it after 3 days and 7 days. 
        If you can't solve it again, you didn't learn it.

❌ MISTAKE 5: "I'll skip Easy problems, they're too simple"
✅ FIX: Easy problems teach you patterns. 
        Medium problems combine patterns.
        Hard problems chain multiple patterns.
        You CANNOT skip the foundation.

❌ MISTAKE 6: "I'll just memorize solutions"
✅ FIX: Understand the PATTERN, not the solution.
        Two Sum teaches "complement lookup with HashMap."
        If you understand the pattern, you can solve 20 variants.
        If you memorize the code, you can solve only that 1 problem.

❌ MISTAKE 7: "DSA is enough for placement"
✅ FIX: You also need:
        → 1-2 solid projects on resume
        → Basic System Design knowledge
        → OS, DBMS, CN fundamentals (CS core subjects)
        → Communication skills for behavioral rounds

❌ MISTAKE 8: "I need to solve 1000 problems"
✅ FIX: 300 QUALITY problems with deep understanding
        > 1000 problems solved by copy-pasting.
        
❌ MISTAKE 9: "I'll start competitive programming to learn DSA"
✅ FIX: CP and interview DSA are DIFFERENT skills.
        CP: Speed + tricks + obscure algorithms
        Interview DSA: Patterns + communication + clean code
        Focus on interview DSA first. CP is optional.

❌ MISTAKE 10: "I'll start with DP because it's the hardest"
✅ FIX: DP requires recursion. Recursion requires arrays/strings.
        FOLLOW THE ORDER. There are no shortcuts.
```

---

# PART 7: INTERVIEW PREPARATION STRATEGY

```
INTERVIEW STRUCTURE (Most product companies):
│
├── ROUND 1: Online Assessment (OA)
│   ├── 2-3 coding problems in 60-90 minutes
│   ├── Usually Easy + Medium + Medium/Hard
│   ├── Prep: LeetCode timed practice
│   └── Tip: Solve Easy in < 10 min, Medium in < 25 min
│
├── ROUND 2: Technical Interview 1 (DSA)
│   ├── 1-2 coding problems in 45-60 minutes
│   ├── You code in shared editor (no IDE autocomplete!)
│   ├── YOU MUST EXPLAIN your thought process
│   ├── Interviewer evaluates:
│   │   ├── Problem-solving approach
│   │   ├── Communication
│   │   ├── Code quality
│   │   ├── Edge case handling
│   │   └── Complexity analysis
│   └── Prep: Practice talking while coding
│
├── ROUND 3: Technical Interview 2 (DSA + System Design lite)
│   ├── Harder DSA problems
│   ├── May include basic system design
│   │   (Design URL shortener, Design parking lot)
│   └── Prep: System Design Primer (GitHub)
│
├── ROUND 4: CS Fundamentals (Indian companies especially)
│   ├── Operating Systems:
│   │   ├── Process vs Thread
│   │   ├── Deadlock, Mutex, Semaphore
│   │   ├── Memory management (Paging, Segmentation)
│   │   ├── CPU scheduling algorithms
│   │   └── Virtual memory
│   │
│   ├── DBMS:
│   │   ├── SQL queries (JOIN, GROUP BY, HAVING)
│   │   ├── Normalization (1NF, 2NF, 3NF, BCNF)
│   │   ├── ACID properties
│   │   ├── Indexing
│   │   └── Transactions
│   │
│   ├── Computer Networks:
│   │   ├── OSI model, TCP/IP model
│   │   ├── TCP vs UDP
│   │   ├── HTTP vs HTTPS
│   │   ├── DNS
│   │   └── How the internet works
│   │
│   └── OOP Concepts:
│       ├── 4 Pillars (Encapsulation, Abstraction, 
│       │   Inheritance, Polymorphism)
│       ├── SOLID principles
│       └── Design Patterns (Singleton, Factory, Observer)
│
├── ROUND 5: Behavioral / HR
│   ├── "Tell me about yourself"
│   ├── "Describe a challenging project"
│   ├── "Conflict with teammate"
│   ├── "Why this company?"
│   └── Prep: STAR method (Situation, Task, Action, Result)
│
└── CS CORE GITHUB REPOS:
    ├── github.com/arialdomartini/Back-End-Developer-Interview-Questions
    ├── github.com/DopplerHQ/awesome-interview-questions
    └── github.com/viraptor/reverse-interview
```

---

# PART 8: 30-DAY KICKSTART PLAN (Day-by-Day)

```
═══════════════════════════════════════════════════════
WEEK 1: FOUNDATIONS
═══════════════════════════════════════════════════════

DAY 1 (Setup Day):
├── Install VS Code + extensions
├── Create LeetCode account
├── Create GitHub repo "DSA-Journey"
├── Choose language (C++ recommended)
├── Watch: "How to start DSA" by Striver (1 video)
└── Solve: Print "Hello World", basic I/O (3-4 warmup programs)

DAY 2 (Complexity):
├── Learn: Big-O notation (watch Abdul Bari's complexity video)
├── Practice: Analyze complexity of 10 code snippets
├── Solve: Basic math problems
│   └── LC 9 (Palindrome Number), LC 7 (Reverse Integer)
└── Time: 3 hours

DAY 3 (Complexity + Math):
├── Learn: GCD (Euclidean), Prime check, Sieve
├── Solve:
│   ├── LC 1492 (Kth Factor of n)
│   ├── Count digits, Armstrong number
│   └── GCD, LCM implementation
└── Time: 3 hours

DAY 4 (Sorting - Part 1):
├── Learn: Bubble Sort, Selection Sort, Insertion Sort
├── Implement all 3 from scratch
├── Understand: Stable vs Unstable, Time/Space of each
└── Time: 3 hours

DAY 5 (Sorting - Part 2):
├── Learn: Merge Sort (VERY IMPORTANT — understand recursion here)
├── Implement Merge Sort from scratch
├── Dry run on paper with example array
├── Solve: LC 912 (Sort an Array — use merge sort)
└── Time: 3 hours

DAY 6 (Sorting - Part 3):
├── Learn: Quick Sort + Partition logic
├── Implement Quick Sort from scratch
├── Learn: Counting Sort
├── Solve: LC 75 (Sort Colors — Dutch National Flag)
└── Time: 4 hours

DAY 7 (Revision + STL):
├── Revise all sorting algorithms (implement without looking)
├── Learn STL: vectors, pairs, maps, sets, sort()
├── Practice: 5 basic STL usage problems
└── Time: 4 hours

═══════════════════════════════════════════════════════
WEEK 2: ARRAYS (EASY)
═══════════════════════════════════════════════════════

DAY 8:
├── Learn: Array basics, traversal patterns
├── Solve:
│   ├── LC 217 (Contains Duplicate)
│   ├── LC 136 (Single Number)
│   ├── LC 283 (Move Zeroes)
│   └── LC 26 (Remove Duplicates from Sorted Array)
└── Time: 3 hours

DAY 9:
├── Learn: Kadane's Algorithm (Maximum Subarray)
├── Solve:
│   ├── LC 53 (Maximum Subarray) ⭐
│   ├── LC 121 (Best Time to Buy and Sell Stock) ⭐
│   └── LC 169 (Majority Element)
└── Time: 3 hours

DAY 10:
├── Learn: Two Pointer technique
├── Solve:
│   ├── LC 1 (Two Sum) ⭐
│   ├── LC 167 (Two Sum II - Sorted)
│   ├── LC 88 (Merge Sorted Array)
│   └── LC 283 re-solve using two pointers
└── Time: 3 hours

DAY 11:
├── Learn: Prefix Sum technique
├── Solve:
│   ├── LC 303 (Range Sum Query)
│   ├── LC 238 (Product of Array Except Self) ⭐
│   ├── LC 448 (Find Disappeared Numbers)
│   └── LC 349 (Intersection of Two Arrays)
└── Time: 3 hours

DAY 12:
├── Learn: Sliding Window (Fixed Size)
├── Solve:
│   ├── Max sum subarray of size K
│   ├── LC 643 (Maximum Average Subarray I)
│   ├── LC 219 (Contains Duplicate II)
│   └── LC 1004 (Max Consecutive Ones III)
└── Time: 3-4 hours

DAY 13:
├── Learn: Sliding Window (Variable Size)
├── Solve:
│   ├── LC 3 (Longest Substring Without Repeating Characters) ⭐
│   ├── LC 209 (Minimum Size Subarray Sum)
│   └── LC 424 (Longest Repeating Character Replacement)
└── Time: 3-4 hours

DAY 14 (Weekend - Heavy):
├── Revision: Re-solve any 3 problems from Week 2 without looking
├── Solve NEW:
│   ├── LC 11 (Container With Most Water)
│   ├── LC 15 (3Sum)
│   ├── LC 560 (Subarray Sum Equals K)
│   └── LC 189 (Rotate Array)
├── Update GitHub with all solutions
└── Time: 5-6 hours

═══════════════════════════════════════════════════════
WEEK 3: ARRAYS (MEDIUM) + STRINGS
═══════════════════════════════════════════════════════

DAY 15:
├── Solve:
│   ├── LC 56 (Merge Intervals) ⭐
│   ├── LC 57 (Insert Interval)
│   └── LC 128 (Longest Consecutive Sequence) ⭐
└── Time: 3-4 hours

DAY 16:
├── Solve:
│   ├── LC 48 (Rotate Image)
│   ├── LC 54 (Spiral Matrix)
│   ├── LC 73 (Set Matrix Zeroes)
│   └── LC 287 (Find the Duplicate Number)
└── Time: 3-4 hours

DAY 17:
├── Learn: String fundamentals
├── Solve:
│   ├── LC 125 (Valid Palindrome)
│   ├── LC 242 (Valid Anagram) ⭐
│   ├── LC 344 (Reverse String)
│   └── LC 14 (Longest Common Prefix)
└── Time: 3 hours

DAY 18:
├── Solve:
│   ├── LC 49 (Group Anagrams) ⭐
│   ├── LC 5 (Longest Palindromic Substring) ⭐
│   ├── LC 409 (Longest Palindrome)
│   └── LC 387 (First Unique Character)
└── Time: 3-4 hours

DAY 19:
├── Learn: Binary Search basics
├── Solve:
│   ├── LC 704 (Binary Search)
│   ├── LC 35 (Search Insert Position)
│   ├── LC 34 (First and Last Position) ⭐
│   └── LC 33 (Search in Rotated Sorted Array) ⭐
└── Time: 3-4 hours

DAY 20:
├── Learn: Binary Search on Answer
├── Solve:
│   ├── LC 69 (Sqrt)
│   ├── LC 875 (Koko Eating Bananas) ⭐
│   ├── LC 153 (Find Min in Rotated Sorted Array)
│   └── LC 162 (Peak Element)
└── Time: 3-4 hours

DAY 21 (Weekend - Heavy):
├── REVISION: Re-solve hardest 5 problems from Week 2-3
├── Solve:
│   ├── LC 42 (Trapping Rain Water) — try it! ⭐⭐
│   ├── LC 76 (Minimum Window Substring) — hard but try
│   └── LC 347 (Top K Frequent Elements) ⭐
├── Update GitHub, clean up notes
└── Time: 5-6 hours

═══════════════════════════════════════════════════════
WEEK 4: RECURSION (THE MOST IMPORTANT WEEK)
═══════════════════════════════════════════════════════

DAY 22:
├── Learn: Recursion basics (Striver's recursion playlist - first 3 videos)
├── Implement:
│   ├── Print 1 to N, N to 1
│   ├── Sum of N numbers
│   ├── Factorial
│   ├── Fibonacci
│   └── Reverse array using recursion
└── Time: 3 hours

DAY 23:
├── Learn: Recursion on arrays/strings
├── Implement:
│   ├── Check palindrome recursively
│   ├── Power function (recursive)
│   ├── Count digits
│   ├── Sum of digits
│   └── Check if array is sorted
└── Time: 3 hours

DAY 24:
├── Learn: Subsequences pattern (PICK / NOT PICK)
├── Solve:
│   ├── LC 78 (Subsets) ⭐⭐
│   ├── LC 90 (Subsets II)
│   └── Print all subsequences of "abc"
└── Time: 3-4 hours

DAY 25:
├── Solve:
│   ├── LC 39 (Combination Sum) ⭐
│   ├── LC 40 (Combination Sum II)
│   └── LC 216 (Combination Sum III)
└── Time: 3-4 hours

DAY 26:
├── Learn: Backtracking concept
├── Solve:
│   ├── LC 46 (Permutations) ⭐
│   ├── LC 47 (Permutations II)
│   └── LC 22 (Generate Parentheses) ⭐
└── Time: 3-4 hours

DAY 27:
├── Solve:
│   ├── LC 79 (Word Search)
│   ├── LC 131 (Palindrome Partitioning) ⭐
│   └── LC 17 (Letter Combinations of Phone Number)
└── Time: 3-4 hours

DAY 28 (Weekend - Heavy):
├── Solve:
│   ├── LC 51 (N-Queens) ⭐⭐ — THE classic backtracking problem
│   ├── LC 37 (Sudoku Solver)
│   └── LC 77 (Combinations)
├── REVISION: Re-solve 5 hardest problems from entire month
├── Update GitHub with ALL remaining solutions
└── Time: 5-6 hours

DAY 29:
├── FULL REVISION DAY
├── Re-solve 8-10 problems you found hardest
├── Write pattern notes:
│   ├── Two Pointer template
│   ├── Sliding Window template
│   ├── Binary Search template
│   ├── Backtracking template
│   └── Common array tricks
└── Time: 4-5 hours

DAY 30:
├── ASSESSMENT DAY
├── Set timer: Solve 3 random LeetCode Mediums in 90 min
├── If you solve 2/3: You're on track! ✅
├── If you solve 1/3: Normal for a beginner, keep going 💪
├── If you solve 0/3: Re-do Week 2-3 problems more carefully
├── Plan Month 2: Linked List, Stack, Queue, Trees
└── CELEBRATE — You survived Month 1! 🎉
```

---

# 📊 MONTH-BY-MONTH SUMMARY

```
╔═══════════════════════════════════════════════════════════╗
║  MONTH  │ TOPICS                      │ PROBLEMS │ LEVEL ║
╠═════════╪═════════════════════════════╪══════════╪═══════╣
║    1    │ Complexity, Sorting,        │  80-100  │ Easy  ║
║         │ Arrays, Strings,            │          │   +   ║
║         │ Binary Search, Recursion    │          │  Med  ║
╠═════════╪═════════════════════════════╪══════════╪═══════╣
║    2    │ Linked List, Stack, Queue,  │  60-80   │  Med  ║
║         │ Hashing                     │          │       ║
╠═════════╪═════════════════════════════╪══════════╪═══════╣
║    3    │ Trees, BST, Heaps, Tries   │  60-70   │  Med  ║
║         │                             │          │   +   ║
║         │                             │          │ Hard  ║
╠═════════╪═════════════════════════════╪══════════╪═══════╣
║    4    │ Graphs (all algorithms)     │  50-60   │  Med  ║
║         │                             │          │   +   ║
║         │                             │          │ Hard  ║
╠═════════╪═════════════════════════════╪══════════╪═══════╣
║    5    │ Dynamic Programming         │  60-80   │  Med  ║
║         │ (1D, 2D, Strings, Trees)   │          │   +   ║
║         │                             │          │ Hard  ║
╠═════════╪═════════════════════════════╪══════════╪═══════╣
║    6    │ Greedy, Bits, String Algos │  40-50   │ Mixed ║
║         │ + FULL REVISION            │          │       ║
║         │ + Mock Interviews          │          │       ║
╠═════════╪═════════════════════════════╪══════════╪═══════╣
║  TOTAL  │ ALL DSA TOPICS             │ 350-440  │       ║
╚═════════╧═════════════════════════════╧══════════╧═══════╝
```

---

# 🏆 SELF-RATING OF THIS ROADMAP

```
╔═══════════════════════════════════════════════════╗
║  CRITERIA              │ PERPLEXITY │ MY VERSION ║
╠════════════════════════╪════════════╪════════════╣
║  Topic Coverage        │   6/10     │   9.5/10   ║
║  Topic Order           │   7/10     │   9.5/10   ║
║  Realism               │   5/10     │   9/10     ║
║  Problem Specificity   │   4/10     │   10/10    ║
║  Resource Quality      │   7/10     │   9.5/10   ║
║  Actionability         │   6/10     │   10/10    ║
║  Day-by-Day Plan       │   0/10     │   10/10    ║
║  Mistake Prevention    │   2/10     │   9/10     ║
║  Interview Strategy    │   1/10     │   9/10     ║
║  Templates/Patterns    │   3/10     │   9/10     ║
╠════════════════════════╪════════════╪════════════╣
║  OVERALL               │   7.5/10   │   9.5/10   ║
╚════════════════════════╧════════════╧════════════╝

What could make this 10/10:
→ A custom web app to track your progress
→ Spaced repetition schedule auto-generated
→ Company-specific problem lists (Google, Amazon, etc.)
→ Mock interview recordings to review
```

---

> **START TOMORROW. Not Monday. Not "after exams." TOMORROW.**
