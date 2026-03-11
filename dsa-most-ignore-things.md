## 🔴 CRITICAL MISSING (Will directly cost you interview offers)

---

### 1. LOW-LEVEL DESIGN (LLD) / OBJECT-ORIENTED DESIGN

```
WHY IT'S CRITICAL:
├── Asked in EVERY product company (Google, Amazon, Flipkart, etc.)
├── Usually a FULL separate interview round
├── Most students completely ignore this
└── You can lose offer EVEN with perfect DSA if LLD is weak

WHAT TO LEARN:
│
├── OOP PRINCIPLES (Deep, not textbook):
│   ├── Encapsulation — real use in design
│   ├── Abstraction — interfaces vs abstract classes
│   ├── Inheritance — when to use, when NOT to use
│   ├── Polymorphism — compile-time vs runtime
│   └── Composition over Inheritance (VERY IMP)
│
├── SOLID PRINCIPLES ⭐⭐:
│   ├── S — Single Responsibility Principle
│   ├── O — Open/Closed Principle
│   ├── L — Liskov Substitution Principle
│   ├── I — Interface Segregation Principle
│   └── D — Dependency Inversion Principle
│
├── DESIGN PATTERNS (Know at least these 8):
│   ├── Creational:
│   │   ├── Singleton
│   │   ├── Factory
│   │   └── Builder
│   ├── Structural:
│   │   ├── Adapter
│   │   └── Decorator
│   └── Behavioral:
│       ├── Observer
│       ├── Strategy
│       └── Command
│
├── LLD INTERVIEW PROBLEMS (Practice ALL):
│   ├── Design Parking Lot ⭐
│   ├── Design Elevator System
│   ├── Design Tic-Tac-Toe
│   ├── Design BookMyShow / Movie Ticket Booking
│   ├── Design Library Management System
│   ├── Design ATM Machine
│   ├── Design Chess Game
│   ├── Design Snake and Ladder
│   ├── Design Splitwise ⭐
│   ├── Design Vending Machine
│   ├── Design Car Rental System
│   ├── Design Hotel Management System
│   └── Design Food Delivery System (Zomato/Swiggy)
│
├── HOW TO APPROACH LLD IN INTERVIEW:
│   ├── Step 1: Clarify requirements (ask questions!)
│   ├── Step 2: Identify core objects/entities
│   ├── Step 3: Define relationships (has-a, is-a)
│   ├── Step 4: Define interfaces and classes
│   ├── Step 5: Write key methods
│   └── Step 6: Handle edge cases, concurrency
│
├── RESOURCES:
│   ├── GitHub: github.com/ashishps1/awesome-low-level-design ⭐
│   ├── GitHub: github.com/tssovi/grokking-the-object-oriented-design-interview
│   ├── YouTube: "Concept && Coding" channel (BEST for LLD in Hindi)
│   ├── YouTube: "Sudocode" channel
│   └── Book: "Head First Design Patterns"
│
└── WHEN TO STUDY:
    Start Month 4 alongside Graphs
    Spend 1 hour/day on LLD from Month 4 onwards
```

---

### 2. HIGH-LEVEL DESIGN (HLD) / SYSTEM DESIGN BASICS

```
WHY IT'S CRITICAL:
├── Asked at SDE-1 level in top companies now (simplified version)
├── Even if not a full round, questions pop up in tech discussions
├── Shows you think beyond code — like an ENGINEER, not a coder
└── Differentiates you from other candidates

WHAT TO LEARN (SDE-1 LEVEL ONLY):
│
├── CONCEPTS:
│   ├── Client-Server Architecture
│   ├── Load Balancing (Round Robin, Least Connections)
│   ├── Caching (Redis, Memcached) — what, why, when
│   ├── Database:
│   │   ├── SQL vs NoSQL — when to use which
│   │   ├── Sharding & Partitioning
│   │   ├── Replication (Master-Slave)
│   │   └── Indexing — how it speeds up queries
│   │
│   ├── API Design:
│   │   ├── REST API basics
│   │   ├── HTTP methods (GET, POST, PUT, DELETE)
│   │   ├── Status codes (200, 201, 400, 401, 403, 404, 500)
│   │   └── Rate Limiting
│   │
│   ├── Message Queues (Kafka, RabbitMQ — just concept)
│   ├── CDN (Content Delivery Network)
│   ├── Consistent Hashing
│   ├── CAP Theorem
│   ├── Horizontal vs Vertical Scaling
│   └── Microservices vs Monolith (basic idea)
│
├── SYSTEM DESIGN PROBLEMS (Practice at least 5):
│   ├── Design URL Shortener (like bit.ly) ⭐
│   ├── Design Paste Bin
│   ├── Design Rate Limiter ⭐
│   ├── Design Chat System (WhatsApp basics)
│   ├── Design Notification System
│   ├── Design News Feed (Facebook/Twitter)
│   ├── Design File Storage (Google Drive basics)
│   └── Design Video Streaming (YouTube basics)
│
├── RESOURCES:
│   ├── GitHub: github.com/donnemartin/system-design-primer ⭐⭐
│   ├── GitHub: github.com/ByteByteGoHq/system-design-101
│   ├── YouTube: "Gaurav Sen" (BEST system design in India)
│   ├── YouTube: "ByteByteGo" (Alex Xu — beautiful animations)
│   ├── YouTube: "Concept && Coding" (Hindi)
│   ├── Book: "System Design Interview" by Alex Xu
│   └── Website: github.com/karanpratapsingh/system-design
│
└── WHEN TO STUDY:
    Start Month 5 alongside DP
    Spend 1 hour/day, 3-4 days/week
    Total: ~15-20 hours is enough for SDE-1 level
```

---

### 3. CS CORE SUBJECTS (OS, DBMS, CN, OOP)

```
WHY IT'S CRITICAL:
├── Indian companies (TCS, Infosys, Wipro, Zoho, etc.) = FULL ROUND on this
├── Product companies = Quick-fire questions in tech rounds
├── You ALREADY studied these in B.Tech — just need revision
└── Easiest marks to gain in interviews

OPERATING SYSTEMS:
├── Process vs Thread (differences, when to use)
├── Process States & Lifecycle
├── CPU Scheduling:
│   ├── FCFS, SJF, SRTF, Round Robin, Priority
│   └── Know tradeoffs of each
├── Synchronization:
│   ├── Critical Section Problem
│   ├── Mutex vs Semaphore vs Monitor
│   ├── Producer-Consumer Problem ⭐
│   ├── Reader-Writer Problem
│   └── Dining Philosophers Problem
├── Deadlock:
│   ├── 4 Necessary Conditions
│   ├── Prevention vs Avoidance vs Detection
│   └── Banker's Algorithm
├── Memory Management:
│   ├── Paging vs Segmentation
│   ├── Page Replacement: FIFO, LRU, Optimal ⭐
│   ├── Virtual Memory
│   ├── Thrashing
│   └── TLB (Translation Lookaside Buffer)
├── Disk Scheduling: FCFS, SSTF, SCAN, C-SCAN
└── File System basics

DBMS:
├── ER Diagrams (draw for any scenario)
├── Relational Model (keys: Primary, Foreign, Candidate, Super)
├── Normalization:
│   ├── 1NF, 2NF, 3NF, BCNF ⭐
│   ├── Functional Dependencies
│   └── Anomalies (Update, Insert, Delete)
├── SQL (MUST PRACTICE):
│   ├── SELECT, WHERE, ORDER BY, GROUP BY, HAVING
│   ├── JOINs: INNER, LEFT, RIGHT, FULL, CROSS, SELF ⭐
│   ├── Subqueries, Nested Queries
│   ├── Aggregate Functions: COUNT, SUM, AVG, MAX, MIN
│   ├── Window Functions: ROW_NUMBER, RANK, DENSE_RANK
│   ├── UNION, INTERSECT, EXCEPT
│   └── CREATE, INSERT, UPDATE, DELETE, ALTER
├── Transactions:
│   ├── ACID Properties ⭐
│   ├── Serializability
│   ├── Isolation Levels (Read Uncommitted → Serializable)
│   └── Concurrency Control (Lock-based, Timestamp-based)
├── Indexing:
│   ├── B-Tree, B+ Tree ⭐
│   ├── Hash Index
│   ├── Clustered vs Non-Clustered
│   └── When to create indexes, when NOT to
└── SQL vs NoSQL (differences, use cases)

COMPUTER NETWORKS:
├── OSI Model (7 layers) — know each layer's function ⭐
├── TCP/IP Model (4 layers)
├── TCP vs UDP ⭐ (differences, use cases)
├── TCP 3-Way Handshake
├── HTTP vs HTTPS ⭐
├── HTTP Methods, Status Codes
├── DNS (how domain → IP resolution works) ⭐
├── DHCP, ARP, NAT
├── IP Addressing, Subnetting
├── Routing: Distance Vector vs Link State
├── Congestion Control, Flow Control
├── Sockets basics
├── Cookies vs Sessions vs Tokens
└── "What happens when you type google.com" ⭐⭐⭐
    (THE most asked interview question)

OOP CONCEPTS:
├── 4 Pillars (with REAL code examples, not textbook definitions)
├── Abstract Class vs Interface ⭐
├── Constructor, Destructor, Copy Constructor
├── Static vs Dynamic Binding
├── Virtual Functions, VTable (C++)
├── Operator Overloading, Function Overloading
├── Templates/Generics
├── Exception Handling
├── Access Modifiers (public, private, protected)
├── Friend Functions (C++)
└── Shallow Copy vs Deep Copy ⭐

RESOURCES:
├── GitHub: github.com/arpit20adlakha/Data-Structure-Algorithms-LLD-HLD ⭐
├── YouTube: "Gate Smashers" (Hindi, covers OS/DBMS/CN)
├── YouTube: "Knowledge Gate" (Hindi)
├── YouTube: "Jenny's Lectures" (Hindi)
├── SQL Practice: hackerrank.com/domains/sql
├── SQL Practice: leetcode.com/studyplan/top-sql-50
├── Website: interviewbit.com (has CS fundamentals sections)
└── GitHub: github.com/DopplerHQ/awesome-interview-questions

WHEN TO STUDY:
├── Start Month 3 — just 30-45 min/day
├── Alternate: Day 1 OS, Day 2 DBMS, Day 3 CN, Day 4 OOP
└── By Month 6 you'll have revised everything 2-3 times
```

---

### 4. SQL PRACTICE (Separately — It's THAT Important)

```
WHY SEPARATE SECTION:
├── SQL is asked in EVERY company — from startups to FAANG
├── Often a separate online assessment round
├── Even frontend developers get SQL questions
└── LeetCode has 50 dedicated SQL problems

MUST-PRACTICE LEETCODE SQL PROBLEMS:
├── Easy:
│   ├── 175 — Combine Two Tables
│   ├── 176 — Second Highest Salary ⭐
│   ├── 181 — Employees Earning More Than Their Managers
│   ├── 182 — Duplicate Emails
│   ├── 183 — Customers Who Never Order
│   ├── 196 — Delete Duplicate Emails
│   └── 197 — Rising Temperature
│
├── Medium:
│   ├── 177 — Nth Highest Salary ⭐
│   ├── 178 — Rank Scores
│   ├── 180 — Consecutive Numbers
│   ├── 184 — Department Highest Salary
│   ├── 550 — Game Play Analysis
│   ├── 570 — Managers with at Least 5 Direct Reports
│   ├── 585 — Investments in 2016
│   └── 602 — Friend Requests
│
├── Hard:
│   ├── 185 — Department Top Three Salaries
│   ├── 262 — Trips and Users
│   └── 601 — Human Traffic of Stadium
│
└── STUDY PLAN: leetcode.com/studyplan/top-sql-50
    Complete this in 1-2 weeks alongside DSA
```

---

### 5. HOW TO READ CONSTRAINTS (MISSING CRITICAL SKILL)

```
THIS IS THE #1 SKILL THAT SEPARATES BEGINNERS FROM INTERMEDIATES

GIVEN CONSTRAINTS → DETERMINE REQUIRED TIME COMPLEXITY:
┌─────────────────────────────────────────────────────────────┐
│  CONSTRAINT (n)    │  MAX COMPLEXITY   │  THINK OF          │
├────────────────────┼───────────────────┼────────────────────┤
│  n ≤ 10            │  O(n!) or O(2ⁿ)  │  Backtracking,     │
│                    │                   │  brute force        │
├────────────────────┼───────────────────┼────────────────────┤
│  n ≤ 20            │  O(2ⁿ)           │  Bitmask DP,       │
│                    │                   │  backtracking       │
├────────────────────┼───────────────────┼────────────────────┤
│  n ≤ 100           │  O(n³)           │  3 nested loops,    │
│                    │                   │  Floyd-Warshall     │
├────────────────────┼───────────────────┼────────────────────┤
│  n ≤ 1,000         │  O(n²)           │  2 nested loops,    │
│                    │                   │  2D DP              │
├────────────────────┼───────────────────┼────────────────────┤
│  n ≤ 10,000        │  O(n²) barely    │  Optimized O(n²)    │
│                    │                   │  or O(n√n)          │
├────────────────────┼───────────────────┼────────────────────┤
│  n ≤ 100,000       │  O(n log n)      │  Sorting, binary    │
│  (10⁵)             │                   │  search, heap,      │
│                    │                   │  merge sort tree     │
├────────────────────┼───────────────────┼────────────────────┤
│  n ≤ 1,000,000     │  O(n) or         │  Two pointers,      │
│  (10⁶)             │  O(n log n)      │  sliding window,    │
│                    │                   │  hashing             │
├────────────────────┼───────────────────┼────────────────────┤
│  n ≤ 10,000,000    │  O(n)            │  Linear scan,       │
│  (10⁷)             │                   │  sieve, prefix sum  │
├────────────────────┼───────────────────┼────────────────────┤
│  n ≤ 10⁸ or more   │  O(log n) or     │  Binary search,     │
│                    │  O(1)            │  math formula        │
└────────────────────┴───────────────────┴────────────────────┘

RULE OF THUMB:
├── Most online judges allow ~10⁸ operations per second
├── If n = 10⁵, then O(n²) = 10¹⁰ → TLE ❌
├── If n = 10⁵, then O(n log n) = ~1.7 × 10⁶ → PASS ✅
│
├── ALWAYS READ CONSTRAINTS FIRST before writing any code
├── Constraints TELL you which algorithm to use
└── This is NOT taught in any course but is the MOST practical skill
```

---

### 6. RESUME + PROJECTS (No Resume = No Interview Call)

```
YOUR RESUME NEEDS AT LEAST:
│
├── 2 SOLID PROJECTS (Not calculator, not todo app):
│
│   PROJECT IDEAS THAT IMPRESS:
│   ├── TIER 1 — IMPRESSIVE:
│   │   ├── Full-stack web app with auth + database + deployment
│   │   │   (e.g., E-commerce site, Social media clone, Blog platform)
│   │   ├── AI/ML project (Sentiment analysis, Image classifier,
│   │   │   Chatbot with LLM)
│   │   ├── Real-time application (Chat app with WebSockets,
│   │   │   Live collaboration tool)
│   │   ├── CLI tool that solves a real problem
│   │   └── Browser extension
│   │
│   ├── TIER 2 — GOOD:
│   │   ├── REST API with database (CRUD operations)
│   │   ├── Data visualization dashboard
│   │   ├── Automation script/tool
│   │   ├── Mobile app (React Native / Flutter)
│   │   └── Portfolio website (your own)
│   │
│   └── TIER 3 — AVOID:
│       ├── ❌ Calculator
│       ├── ❌ Todo list (too basic)
│       ├── ❌ Weather app (everyone does it)
│       ├── ❌ Anything from a tutorial without modifications
│       └── ❌ Group project where you can't explain your contribution
│
├── HOW TO PRESENT PROJECTS ON RESUME:
│   ├── Use ACTION VERBS: Built, Designed, Implemented, Optimized
│   ├── Include TECH STACK: "Built with React, Node.js, MongoDB, AWS"
│   ├── Include METRICS: "Handles 1000+ concurrent users"
│   ├── Include LINKS: GitHub repo + live demo
│   └── Example:
│       "Built a full-stack e-commerce platform using React,
│        Node.js, Express, and MongoDB. Implemented JWT 
│        authentication, payment gateway integration (Razorpay),
│        and deployed on AWS EC2. Handles 500+ products with 
│        search and filter functionality."
│
├── RESUME RESOURCES:
│   ├── GitHub: github.com/resumejob/awesome-resume ⭐
│   ├── Template: Jake's Resume (Overleaf LaTeX template) ⭐⭐
│   ├── Tool: flowcv.com (free resume builder)
│   └── Video: "How to write a resume" by TechLead
│
├── RESUME FORMAT:
│   ├── 1 PAGE ONLY (for freshers, ALWAYS 1 page)
│   ├── Sections in order:
│   │   ├── Education
│   │   ├── Skills (Languages, Frameworks, Tools)
│   │   ├── Projects (2-3 with bullet points)
│   │   ├── Experience (internships if any)
│   │   ├── Achievements (competitive programming, hackathons)
│   │   └── Certifications (optional)
│   ├── NO photo (unless required)
│   ├── NO "objective" or "summary" section
│   ├── Use .pdf format
│   └── ATS-friendly (no fancy graphics, tables, or columns)
│
└── PROJECT REPOS FOR INSPIRATION:
    ├── github.com/florinpop17/app-ideas
    ├── github.com/practical-tutorials/project-based-learning
    └── github.com/codecrafters-io/build-your-own-x
```

---

## 🟡 IMPORTANT MISSING (Gives you competitive edge)

---

### 7. ADVANCED DSA TOPICS (For Competitive Programming + Hard Interviews)

```
I COVERED BASIC-TO-INTERMEDIATE DSA. HERE'S WHAT'S BEYOND:

ADVANCED GRAPH ALGORITHMS:
├── Strongly Connected Components (SCC):
│   ├── Tarjan's Algorithm ⭐
│   ├── Kosaraju's Algorithm
│   └── Problems: LC 1192 (Critical Connections)
│
├── Articulation Points & Bridges:
│   ├── Finding cut vertices in a graph
│   ├── Finding bridges (edges whose removal disconnects graph)
│   └── Used in network reliability problems
│
├── Euler Path / Circuit:
│   ├── Path that visits every EDGE exactly once
│   ├── Hierholzer's Algorithm
│   └── LC 332 (Reconstruct Itinerary)
│
├── Bipartite Matching:
│   ├── Hungarian Algorithm
│   └── Hopcroft-Karp Algorithm
│
├── Network Flow:
│   ├── Ford-Fulkerson / Edmonds-Karp
│   ├── Max Flow - Min Cut Theorem
│   └── Rarely asked in interviews, but good to know
│
└── Multi-Source BFS:
    ├── BFS from multiple starting points simultaneously
    ├── LC 994 (Rotting Oranges) — already uses this
    ├── LC 286 (Walls and Gates)
    └── LC 542 (01 Matrix)

ADVANCED DP:
├── Bitmask DP ⭐:
│   ├── State includes a bitmask representing subset
│   ├── Travelling Salesman Problem (TSP)
│   ├── LC 1723 (Find Minimum Time to Finish All Jobs)
│   └── Assignment Problem
│
├── Digit DP:
│   ├── Count numbers from 1 to N with some property
│   ├── Count numbers with no repeated digits
│   └── Rarely in interviews, common in CP
│
├── DP on Trees:
│   ├── Already partially covered
│   ├── Rerooting technique
│   └── Tree DP with states
│
├── SOS DP (Sum over Subsets):
│   └── Advanced bitmask technique
│
├── Probability DP:
│   └── Expected value calculations
│
└── Profile DP (Broken Profile):
    └── Grid problems with complex constraints

ADVANCED DATA STRUCTURES:
├── Segment Tree ⭐⭐ (VERY useful):
│   ├── Range queries: sum, min, max in O(log n)
│   ├── Point updates in O(log n)
│   ├── Lazy Propagation (range updates)
│   ├── Problems:
│   │   ├── Range Sum Query - Mutable (LC 307)
│   │   └── Count of Smaller Numbers After Self (LC 315)
│   └── MUST LEARN if doing competitive programming
│
├── Fenwick Tree / Binary Indexed Tree (BIT):
│   ├── Simpler alternative to Segment Tree
│   ├── Point update + prefix query in O(log n)
│   └── Easier to implement than Segment Tree
│
├── Sparse Table:
│   ├── O(1) range MIN/MAX queries after O(n log n) preprocessing
│   └── Immutable arrays only
│
├── Sqrt Decomposition:
│   ├── Split array into blocks of √n
│   └── O(√n) per query
│
├── AVL Tree / Red-Black Tree:
│   ├── Self-balancing BSTs
│   └── Know concept, don't implement (use TreeMap/set in STL)
│
└── Suffix Array / Suffix Tree:
    ├── Advanced string data structure
    └── Competitive programming level

ADVANCED STRING ALGORITHMS:
├── Manacher's Algorithm:
│   ├── Find ALL palindromic substrings in O(n)
│   └── LC 5 can be solved with this
│
├── Aho-Corasick:
│   ├── Multi-pattern string matching
│   └── Uses Trie + BFS
│
├── Suffix Array:
│   ├── Sorted array of all suffixes
│   └── Used with LCP array for advanced problems
│
└── Rolling Hash / Polynomial Hashing:
    ├── Used in Rabin-Karp
    └── Good for string comparison in O(1)

RESOURCES FOR ADVANCED:
├── GitHub: github.com/williamfiset/Algorithms ⭐
├── YouTube: "Errichto" (competitive programming)
├── YouTube: "Colin Galen" (advanced algorithms)
├── CP Handbook: cses.fi/book/book.pdf (FREE) ⭐⭐
├── CSES Problem Set: cses.fi/problemset ⭐⭐
│   (300 problems covering all advanced topics)
└── Codeforces EDU section

WHEN TO STUDY:
├── Only AFTER completing basic-to-intermediate DSA
├── Month 6+ or after placements
├── IF targeting Google/competitive programming
└── NOT needed for most Indian company placements
```

---

### 8. HANDLING TLE & DEBUGGING (Practical Skills)

```
WHEN YOUR SOLUTION GETS TLE (Time Limit Exceeded):
│
├── CHECKLIST:
│   ├── 1. Read constraints again → determine required complexity
│   ├── 2. Are you using correct algorithm?
│   │   └── O(n²) when O(n log n) is needed?
│   ├── 3. Are you doing unnecessary work inside loops?
│   │   ├── String concatenation in loop (use StringBuilder)
│   │   ├── Sorting inside loop
│   │   └── Map operations that could be precomputed
│   ├── 4. Is your recursion without memoization?
│   │   └── Add dp[] array to cache results
│   ├── 5. Can you use a different data structure?
│   │   ├── Array → HashMap (O(n) → O(1) lookup)
│   │   ├── List → Set (O(n) → O(1) contains)
│   │   └── Sorting + Binary Search instead of linear search
│   └── 6. Language-specific optimizations:
│       ├── C++: Use '\n' instead of endl (flushes buffer)
│       ├── C++: Use scanf/printf instead of cin/cout
│       ├── Java: Use BufferedReader instead of Scanner
│       └── Python: Use sys.stdin for faster input
│
├── COMMON OPTIMIZATION PATTERNS:
│   ├── O(n²) → O(n log n): Sort + Binary Search / Two Pointers
│   ├── O(n²) → O(n): HashMap / Sliding Window / Prefix Sum
│   ├── O(2ⁿ) → O(n²) or O(n*target): DP (memoization)
│   └── O(n*m) → O(n+m): Two Pointer on sorted data
│
DEBUGGING RECURSIVE CODE:
│
├── TECHNIQUES:
│   ├── 1. Print the function call with parameters at entry
│   ├── 2. Print the return value before returning
│   ├── 3. Draw the recursion tree on paper (ESSENTIAL)
│   ├── 4. Verify base cases with smallest inputs
│   ├── 5. Check: Are you passing by value or reference?
│   └── 6. Check: Is memoization key correct and unique?
│
└── COMMON BUGS:
    ├── Off-by-one errors in loops (< vs <=)
    ├── Integer overflow (use long long in C++)
    ├── Not handling empty input / null pointer
    ├── Modifying collection while iterating
    ├── Wrong base case in recursion
    ├── Forgetting to mark visited in graph problems
    └── Using global variables that don't reset between test cases
```

---

### 9. EDGE CASES CHEAT SHEET (For Each Data Structure)

```
ARRAYS:
├── Empty array []
├── Single element [5]
├── All same elements [3, 3, 3, 3]
├── Already sorted / reverse sorted
├── Very large numbers (integer overflow)
├── Negative numbers
└── n = 0 or n = 1

STRINGS:
├── Empty string ""
├── Single character "a"
├── All same characters "aaaa"
├── String with spaces
├── Uppercase vs lowercase
├── Special characters / numbers in string
└── Very long strings (10⁵+)

LINKED LIST:
├── Empty list (head = null)
├── Single node
├── Two nodes
├── Cycle vs no cycle
└── Very long list

TREES:
├── Empty tree (root = null)
├── Single node tree
├── Skewed tree (all left OR all right — like a linked list)
├── Perfect binary tree
├── Tree with negative values
└── BST with duplicate values

GRAPHS:
├── Single node, no edges
├── Disconnected graph
├── Self-loops
├── Multiple edges between same nodes
├── Complete graph (every node connected)
├── Directed vs Undirected handling
└── Negative edge weights

DP:
├── n = 0 or target = 0
├── First row / first column initialization
├── Negative values in array
├── When answer overflows (use MOD 10⁹+7)
└── When DP table needs long long

GENERAL:
├── Maximum/Minimum integer values
├── Division by zero
├── Empty input
└── Single element input
```

---

### 10. COMPETITIVE PROGRAMMING RATING STRATEGY (Optional but Valuable)

```
IF YOU WANT TO DO CP (alongside interview prep):

PLATFORM: Codeforces (best for CP)

RATING ROADMAP:
├── Newbie (0-1199):
│   ├── Solve A & B problems from Div 2 contests
│   ├── Focus: Implementation, basic math, sorting, greedy
│   └── Do 50-100 problems at 800-1000 rating
│
├── Pupil (1200-1399):
│   ├── Solve A, B, sometimes C
│   ├── Focus: Binary search, two pointers, basic DP
│   └── Do 50-100 problems at 1000-1200 rating
│
├── Specialist (1400-1599):
│   ├── Consistently solve C, sometimes D
│   ├── Focus: DP, graphs, number theory
│   └── This rating is IMPRESSIVE on resume
│
├── Expert (1600-1899):
│   ├── Very competitive
│   ├── Guarantees strong problem-solving
│   └── Will stand out in ANY interview
│
├── PRACTICE STRATEGY:
│   ├── Upsolve: After contest, solve problems you couldn't
│   ├── Virtual contests: Simulate past contests under time pressure
│   ├── Topic-wise practice on Codeforces Problemset (filter by tag + rating)
│   └── A2OJ Ladders (structured difficulty-wise problem sets)
│
├── RESOURCES:
│   ├── CSES Problem Set: cses.fi/problemset ⭐⭐ (BEST for CP practice)
│   ├── CP Handbook: cses.fi/book/book.pdf (FREE)
│   ├── GitHub: github.com/lnishan/awesome-competitive-programming
│   ├── AtCoder Beginner Contests (great for beginners)
│   └── USACO Guide: usaco.guide (structured CP curriculum)
│
└── TIME COMMITMENT:
    ├── 1-2 contests per week (2 hours each)
    ├── Upsolving: 1-2 hours per contest
    └── Can be done alongside interview DSA prep
```

---

## 🟢 NICE-TO-HAVE MISSING (Cherry on top)

---

### 11. BEHAVIORAL / SOFT SKILLS

```
MOST STUDENTS NEGLECT THIS COMPLETELY:
│
├── COMMUNICATION DURING CODING INTERVIEW:
│   ├── ALWAYS think aloud — interviewer wants to hear your thought process
│   ├── Start with: "Let me understand the problem..."
│   ├── Then: "The brute force approach would be..."
│   ├── Then: "We can optimize by..."
│   ├── Ask clarifying questions:
│   │   ├── "Can the array be empty?"
│   │   ├── "Are there negative numbers?"
│   │   ├── "Is the input sorted?"
│   │   ├── "What should I return if there's no answer?"
│   │   └── "What are the constraints?"
│   ├── After coding: "Let me trace through with an example..."
│   └── Finally: "Time complexity is O(...), space is O(...)"
│
├── BEHAVIORAL QUESTIONS (STAR METHOD):
│   ├── S — Situation: Set the context
│   ├── T — Task: What was your responsibility
│   ├── A — Action: What YOU specifically did
│   ├── R — Result: What was the outcome (use numbers if possible)
│   │
│   ├── Common Questions:
│   │   ├── "Tell me about yourself" (have 60-second pitch ready)
│   │   ├── "Your biggest technical challenge"
│   │   ├── "A time you disagreed with teammate"
│   │   ├── "A project you're proud of"
│   │   ├── "Your weakness"
│   │   ├── "Why this company?"
│   │   └── "Where do you see yourself in 5 years?"
│   │
│   └── Prepare 5-6 stories that can be adapted to different questions
│
├── QUESTIONS TO ASK THE INTERVIEWER:
│   ├── "What does a typical day look like for this role?"
│   ├── "What's the team structure?"
│   ├── "What tech stack does the team use?"
│   ├── "How is performance evaluated?"
│   ├── "What are the growth opportunities?"
│   └── GitHub: github.com/viraptor/reverse-interview ⭐
│
└── RESOURCES:
    ├── Book: "Cracking the Coding Interview" — Chapter on behavioral
    └── YouTube: "Jeff H Sipe" — behavioral interview prep
```

---

### 12. MENTAL HEALTH & CONSISTENCY

```
NOBODY TALKS ABOUT THIS, BUT IT'S REAL:

BURNOUT PREVENTION:
├── Take 1 full day OFF per week (no DSA, no coding)
├── Sleep 7-8 hours (your brain consolidates learning during sleep)
├── Exercise / walk daily (improves cognitive function)
├── Don't compare with others ("He solved 500 problems!")
│   └── YOUR 300 quality problems > someone's 500 copy-pasted solutions
├── It's OK to have bad days (some days you'll solve nothing)
└── Progress is NOT linear — you'll have plateaus

WHEN YOU'RE STUCK ON A PROBLEM:
├── Spent 30-40 min? → Read just the HINT, not full solution
├── Spent 60 min? → Watch the solution video
├── DON'T just copy code — understand WHY it works
├── Come back to it in 3 days and solve it fresh
└── Keep a "retry list" of problems you couldn't solve

CONSISTENCY > INTENSITY:
├── 2 hours DAILY for 6 months >>> 12 hours for 2 weeks then quit
├── Use habit stacking: "After morning coffee, I do DSA for 1 hour"
├── Track streaks (LeetCode has streak counter)
├── Find an accountability partner (friend doing same prep)
└── Join communities:
    ├── r/leetcode (Reddit)
    ├── Striver's Discord/Telegram
    ├── NeetCode Discord
    └── Your college coding club

HANDLING REJECTION:
├── You WILL get rejected — sometimes after clearing 4/5 rounds
├── Each rejection teaches you something
├── Keep applying while preparing (don't wait to be "ready")
├── Apply to 50+ companies, not just 3-4
├── Off-campus > On-campus opportunities in many cases
└── First job doesn't define your career
```

---

### 13. APPLICATION STRATEGY & TIMELINE

```
FINAL YEAR TIMELINE (ASSUMING YOU START NOW):
│
├── MONTH 1-3: PURE DSA PREPARATION
│   ├── Follow the 7-Phase roadmap
│   ├── Start building 1 project alongside
│   └── Begin OS/DBMS/CN revision (30 min/day)
│
├── MONTH 3-4: DSA + PROJECT + CORE SUBJECTS
│   ├── Continue DSA (Trees, Graphs)
│   ├── Complete Project 1, start Project 2
│   ├── LLD practice begins (1 hr/day)
│   └── Start applying to companies (early applications!)
│
├── MONTH 4-5: DSA + SYSTEM DESIGN + APPLICATIONS
│   ├── DP phase in DSA
│   ├── System Design basics (1 hr/day)
│   ├── Mock interviews (weekly)
│   ├── Apply aggressively: LinkedIn, AngelList, company career pages
│   └── Resume should be READY by now
│
├── MONTH 5-6: REVISION + INTERVIEWS
│   ├── Full DSA revision
│   ├── Company-specific preparation (tagged problems on LeetCode)
│   ├── Daily mock interviews
│   ├── Behavioral prep
│   └── Continue applying
│
├── WHERE TO APPLY:
│   ├── LinkedIn Jobs (set alerts for SDE, SWE, Software Developer)
│   ├── AngelList / Wellfound (startups)
│   ├── Company career pages directly
│   ├── Unstop (formerly D2C) — Indian competitions + hiring
│   ├── Internshala (for internship-to-PPO)
│   ├── Naukri.com (set profile as "active")
│   ├── Campus placements (obviously)
│   └── Referrals (THE most effective — ask seniors, LinkedIn connections)
│
├── HOW TO GET REFERRALS:
│   ├── Connect with alumni on LinkedIn
│   ├── Message: "Hi [Name], I'm a final year CSE student at [college].
│   │   I'm interested in [Company]. Would you be open to referring me 
│   │   for the [Role]? Here's my resume. Thank you!"
│   ├── Don't be spammy — personalize each message
│   ├── Having a good GitHub profile helps get referrals
│   └── Referrals increase response rate by 5-10x
│
└── GITHUB PROFILE OPTIMIZATION:
    ├── Pin your best 6 repos (projects + DSA-Journey)
    ├── Write good README for each project (with screenshots)
    ├── Green contribution graph (commit daily)
    ├── Add profile README (github.com/abhisheknaiidu/awesome-github-profile-readme)
    └── Your GitHub IS your portfolio — treat it like one
```

---

## 📊 COMPLETE GAP ANALYSIS

```
╔════════════════════════════════════════════════════════════════╗
║ TOPIC                        │ IN MY ROADMAP? │ IMPORTANCE   ║
╠══════════════════════════════╪════════════════╪══════════════╣
║ DSA (Basic → Advanced)       │ ✅ Yes         │ ⭐⭐⭐⭐⭐  ║
║ Reading Constraints          │ ❌ Missing     │ ⭐⭐⭐⭐⭐  ║
║ Edge Cases Awareness         │ ❌ Missing     │ ⭐⭐⭐⭐⭐  ║
║ Debugging/TLE Handling       │ ❌ Missing     │ ⭐⭐⭐⭐⭐  ║
║ Low-Level Design (LLD)       │ ❌ Missing     │ ⭐⭐⭐⭐⭐  ║
║ System Design (HLD basics)   │ ❌ Missing     │ ⭐⭐⭐⭐   ║
║ OS / DBMS / CN / OOP         │ ❌ Missing     │ ⭐⭐⭐⭐⭐  ║
║ SQL Practice                 │ ❌ Missing     │ ⭐⭐⭐⭐   ║
║ Resume Building              │ ❌ Missing     │ ⭐⭐⭐⭐⭐  ║
║ Projects                     │ ❌ Missing     │ ⭐⭐⭐⭐⭐  ║
║ Behavioral Skills            │ ❌ Missing     │ ⭐⭐⭐⭐   ║
║ Application Strategy         │ ❌ Missing     │ ⭐⭐⭐⭐   ║
║ Advanced DS (Segment Tree)   │ ❌ Missing     │ ⭐⭐⭐     ║
║ Advanced Graph (SCC, Bridges)│ ❌ Missing     │ ⭐⭐⭐     ║
║ Advanced DP (Bitmask, Digit) │ ❌ Missing     │ ⭐⭐⭐     ║
║ Competitive Programming      │ ❌ Missing     │ ⭐⭐⭐     ║
║ Mental Health / Consistency  │ ❌ Missing     │ ⭐⭐⭐⭐   ║
║ Git / Version Control        │ Partially     │ ⭐⭐⭐⭐   ║
║ Open Source Contribution     │ ❌ Missing     │ ⭐⭐⭐     ║
╠══════════════════════════════╪════════════════╪══════════════╣
║ ORIGINAL ROADMAP RATING      │                │ 9.5/10       ║
║ ACTUAL HONEST RATING         │                │ 7.5/10       ║
║ WITH THIS ADDENDUM           │                │ 9.5/10       ║
╚══════════════════════════════╧════════════════╧══════════════╝
```

---

## 🎯 REVISED COMPLETE STUDY PLAN (WITH EVERYTHING INCLUDED)

```
MONTH 1:
├── DSA: Phase 1-2 (Basics, Arrays, Strings, Binary Search, Recursion)
├── Project: START building Project 1
├── CS Core: Nothing yet — focus on DSA
└── Other: Setup GitHub, Resume draft 1

MONTH 2:
├── DSA: Phase 3-4 (Backtracking, Linked List, Stack, Queue, Hashing)
├── Project: Continue Project 1
├── CS Core: OS revision (30 min/day, 3 days/week)
├── SQL: Start LeetCode SQL 50 (2 problems/day)
└── Other: Resume draft 2

MONTH 3:
├── DSA: Phase 5 (Trees, BST, Heaps, Tries)
├── Project: Finish Project 1, START Project 2
├── CS Core: DBMS revision (30 min/day, 3 days/week)
├── SQL: Complete LeetCode SQL 50
├── LLD: Start learning SOLID principles + Design Patterns
└── Other: Finalize resume, start LinkedIn optimization

MONTH 4:
├── DSA: Phase 5 continued (Graphs — all algorithms)
├── Project: Continue Project 2
├── CS Core: CN + OOP revision (30 min/day)
├── LLD: Practice 1 LLD problem per week
├── Other: START APPLYING to companies
└── Mock: 1 mock interview per week

MONTH 5:
├── DSA: Phase 6 (Dynamic Programming — ALL)
├── Project: Finish Project 2
├── System Design: Basic HLD (1 hour/day, 3 days/week)
├── LLD: 2 LLD problems per week
├── Other: Apply aggressively, get referrals
└── Mock: 2 mock interviews per week

MONTH 6:
├── DSA: Phase 7 (Greedy, Bits, Advanced) + FULL REVISION
├── CS Core: Full revision of OS, DBMS, CN, OOP
├── System Design: Revise all designs
├── LLD: Revise all designs
├── Behavioral: Prepare 5-6 stories using STAR method
├── Company-specific: LeetCode tagged problems
├── Mock: 3-4 mock interviews per week
└── Other: Interview mode — full focus on cracking offers
```

---

**No roadmap is perfect — what matters is that you START and STAY CONSISTENT.**

---
