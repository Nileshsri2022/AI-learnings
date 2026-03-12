

# 🧭 ROADMAP: Go (Golang) — Complete Learning Path
### 🎓 Tutor + 💼 Placement Mentor + 🧭 Career Advisor Mode Activated

---

> ⚠️ **Profile Status:** You haven't filled in your `[brackets]` yet. This roadmap is delivered at **intermediate depth** generically. Fill your profile and I'll personalize everything — pace, skip known topics, prioritize for YOUR goals (backend placements? DevOps? system design? competitive programming?).

---

## 📍 Where Go Sits in the Big Picture

```
C (low-level) → Java (enterprise) → Python (scripting) → ✨ Go ✨ (modern systems)
                                                           ↑ YOU ARE HERE

Go = The sweet spot between C's performance and Python's simplicity
```

> 🧒 **ELI5 — The IRCTC Analogy:**
> Imagine you're rebuilding IRCTC. Python would crash under 10 lakh concurrent users. Java would work but need 50 servers and 500 config files. C would be blazing fast but take 2 years to build. **Go handles 10 lakh concurrent users, on 5 servers, and you build it in 3 months.** That's why Google created it — they needed something fast to write AND fast to run.

---

## 🤔 Why Learn Go? (Honest Assessment)

| Factor | Go's Position | Verdict |
|--------|--------------|---------|
| **Performance** | ~10-40x faster than Python, comparable to Java/Rust | 🔴 Excellent |
| **Concurrency** | Built-in goroutines — best-in-class | 🔴 Industry-leading |
| **Simplicity** | Only 25 keywords, minimal syntax | 🔴 Very easy to learn |
| **Compilation** | Compiles to single binary, no runtime dependency | 🔴 Deployment dream |
| **Job Market (India)** | Growing fast — Razorpay, Zerodha, Flipkart, Google, Uber use Go | 🟡 Growing rapidly |
| **Salary (India)** | ₹8-30 LPA for freshers with Go skills | 🟡 Higher than average |
| **Use Cases** | Backend APIs, microservices, DevOps tools, CLIs, cloud infra | 🔴 Perfect for modern backend |
| **Learning Curve** | Can be productive in 2-3 weeks | 🔴 Easiest systems language |
| **Community** | Smaller than Python/JS but very high quality | 🟡 Good |
| **Ecosystem** | Docker, Kubernetes, Terraform, Prometheus — ALL written in Go | 🔴 Dominant in infrastructure |

### Who Should Learn Go?

```
✅ LEARN GO IF:                          ❌ MAYBE NOT IF:
├── You want backend/systems roles       ├── You want frontend/mobile dev
├── You're interested in DevOps/Cloud    ├── You need heavy ML/AI libraries
├── You want to work at startups         ├── You're doing data science
├── You love simplicity & performance    ├── You need a huge ecosystem NOW
├── You want to build CLIs & tools       └── You want maximum job postings
├── You're targeting product companies       (Java/Python still have more)
└── You want to stand out (fewer 
    people know Go = less competition)
```

### 📊 Go vs Other Backend Languages (India Context)

| Aspect | Go | Java | Python | Node.js | Rust |
|--------|----|----|--------|---------|------|
| Learning curve | 🟢 Easy | 🟡 Medium | 🟢 Easy | 🟢 Easy | 🔴 Hard |
| Performance | ⚡ Fast | ⚡ Fast | 🐢 Slow | 🟡 Medium | ⚡⚡ Fastest |
| Concurrency | 🔴 Best | 🟡 Good | 🟡 Decent | 🟡 Good | 🟡 Good |
| Job postings (India) | 🟡 Growing | 🔴 Most | 🔴 Most | 🟡 Many | 🟢 Few |
| Salary ceiling | 🔴 High | 🟡 Medium | 🟡 Medium | 🟡 Medium | 🔴 High |
| Startup adoption | 🔴 Very High | 🟡 Medium | 🔴 High | 🔴 High | 🟢 Low |
| DevOps/Cloud | 🔴 Dominant | 🟢 Some | 🟡 Good | 🟢 Some | 🟢 Some |

---

## 🗺️ FULL ROADMAP — 10 Phases

```
┌──────────────────────────────────────────────────────────────────┐
│                      GOLANG ROADMAP                              │
├──────────────────────────────────────────────────────────────────┤
│                                                                  │
│  PHASE 1  ➜ Introduction & Setup (2-3 days)                     │
│     ↓                                                            │
│  PHASE 2  ➜ Language Basics (1-2 weeks)                         │
│     ↓                                                            │
│  PHASE 3  ➜ Composite Types & Control Flow (1-2 weeks)          │
│     ↓                                                            │
│  PHASE 4  ➜ Functions, Pointers & Memory (1-2 weeks)            │
│     ↓                                                            │
│  PHASE 5  ➜ Methods, Interfaces & Generics (2 weeks)            │
│     ↓                                                            │
│  PHASE 6  ➜ Error Handling & Code Organization (1 week)         │
│     ↓                                                            │
│  PHASE 7  ➜ Concurrency (Go's Superpower) (2-3 weeks)          │
│     ↓                                                            │
│  PHASE 8  ➜ Standard Library & Testing (2 weeks)                │
│     ↓                                                            │
│  PHASE 9  ➜ Ecosystem: Web, DB, CLI, gRPC (3-4 weeks)          │
│     ↓                                                            │
│  PHASE 10 ➜ Toolchain, Advanced Topics & Deployment (2 weeks)   │
│                                                                  │
│  ⏱️ Total: ~16-22 weeks (4-5.5 months at 2 hrs/day)             │
└──────────────────────────────────────────────────────────────────┘
```

---

## PHASE 1: Introduction & Environment Setup 🚀
**⏱️ 2-3 days | Priority: 🔴 CRITICAL**

### 📗 1A: History & "Why Go?"

| Fact | Detail |
|------|--------|
| **Created by** | Robert Griesemer, Rob Pike, Ken Thompson (at Google, 2009) |
| **Why created** | Google was frustrated with C++ compile times and Java complexity |
| **Design goals** | Simplicity, fast compilation, built-in concurrency, great tooling |
| **Mascot** | The Go Gopher 🐹 |
| **Used by** | Google, Uber, Twitch, Docker, Kubernetes, Terraform, Razorpay, Zerodha |

### 📘 1B: Setting Up the Environment

```bash
# ── Install Go ──

# Linux (recommended for Go development)
wget https://go.dev/dl/go1.22.4.linux-amd64.tar.gz
sudo rm -rf /usr/local/go
sudo tar -C /usr/local -xzf go1.22.4.linux-amd64.tar.gz

# Add to PATH (~/.bashrc or ~/.zshrc)
export PATH=$PATH:/usr/local/go/bin
export GOPATH=$HOME/go
export PATH=$PATH:$GOPATH/bin

# Verify
go version
# go version go1.22.4 linux/amd64

# macOS
brew install go

# Windows
# Download installer from https://go.dev/dl/

# ── Recommended IDE ──
# VS Code + Go extension (by Google) ← Best for beginners
# GoLand (JetBrains) ← Best overall, paid but free for students
# Neovim + gopls ← For terminal lovers
```

### 📕 1C: Hello World & The `go` Command

```go
// main.go — Your first Go program
package main           // Every Go file belongs to a package
                       // 'main' package = executable program

import "fmt"           // Import the formatting package

func main() {          // Entry point — MUST be in package main
    fmt.Println("Hello, Duniya! 🇮🇳")  // Print to console
}
```

```bash
# ── Essential `go` commands ──

# Run directly (compile + execute)
go run main.go

# Build binary (creates executable file)
go build -o myapp main.go
./myapp

# Initialize a new module (project)
go mod init github.com/yourusername/myproject

# Format code (Go has ONE standard format — no debates!)
go fmt ./...

# Run tests
go test ./...

# Get documentation
go doc fmt.Println

# Check Go version
go version

# Install a tool/binary
go install github.com/some/tool@latest
```

### 🔍 Key Differences from Other Languages (Day 1 Surprises)

```go
// ❌ No semicolons needed (compiler adds them)
fmt.Println("No semicolons!")

// ❌ No unused variables allowed — WON'T COMPILE
x := 5    // Error: x declared but not used

// ❌ No unused imports allowed — WON'T COMPILE
import "os"   // Error if 'os' is not used

// ❌ No while loop — only `for`
for i := 0; i < 10; i++ { }   // C-style for
for condition { }               // This IS Go's "while"
for { }                         // Infinite loop

// ✅ Opening brace MUST be on same line
func main() {     // ✅ Correct
}

func main()       // ❌ Won't compile!
{
}

// ✅ Capitalization = visibility
func PublicFunc() {}   // Exported (public) — Capital letter
func privateFunc() {}  // Unexported (private) — lowercase

// ✅ Multiple return values — no exceptions!
value, err := someFunction()
if err != nil {
    // handle error
}
```

### ✅ Checkpoint — Phase 1:
- [ ] Go installed and `go version` works
- [ ] IDE set up with Go extension
- [ ] Ran "Hello World" with `go run`
- [ ] Built a binary with `go build`
- [ ] Created a module with `go mod init`
- [ ] You know the 5 key differences from other languages

---

## PHASE 2: Language Basics 📝
**⏱️ 1-2 weeks | Priority: 🔴 CRITICAL**

### 📗 2A: Variables & Constants

```go
package main

import "fmt"

func main() {
    // ═══════════════════════════════════════
    //           VARIABLES
    // ═══════════════════════════════════════
    
    // Method 1: var declaration (explicit type)
    var name string = "Rahul"
    var age int = 21
    var cgpa float64 = 8.5
    
    // Method 2: var with type inference
    var college = "IIT Delhi"     // Go infers: string
    var year = 3                  // Go infers: int
    
    // Method 3: Short declaration (:=) — MOST COMMON ✅
    // Only works INSIDE functions
    city := "Delhi"               // Inferred as string
    isPlaced := false             // Inferred as bool
    
    // Method 4: Multiple declarations
    var (
        x int     = 10
        y float64 = 3.14
        z string  = "hello"
    )
    
    // Method 5: Multiple short declarations
    a, b, c := 1, "two", 3.0
    
    fmt.Println(name, age, cgpa, college, year, city, isPlaced)
    fmt.Println(x, y, z, a, b, c)
    
    // ═══════════════════════════════════════
    //        var vs := (IMPORTANT!)
    // ═══════════════════════════════════════
    
    // var: Can be used anywhere (package level + function level)
    // :=  : ONLY inside functions
    
    // var: Useful when you want zero value without assignment
    var count int           // count = 0 (zero value)
    var message string      // message = "" (zero value)
    var active bool         // active = false (zero value)
    
    fmt.Println(count, message, active)
    
    // ═══════════════════════════════════════
    //         ZERO VALUES
    // ═══════════════════════════════════════
    // Go initializes ALL variables to their "zero value"
    // No null pointer surprises! (unlike Java/C++)
    
    var i int        // 0
    var f float64    // 0.0
    var s string     // "" (empty string)
    var b2 bool      // false
    var p *int       // nil (only pointers can be nil)
    
    fmt.Println(i, f, s, b2, p)
    
    // ═══════════════════════════════════════
    //          CONSTANTS
    // ═══════════════════════════════════════
    
    const pi = 3.14159
    const maxRetries = 3
    const appName = "MyApp"
    
    // const CANNOT be changed
    // pi = 3.14  // ❌ Error: cannot assign to pi
    
    // ── iota: Auto-incrementing constants ──
    // Perfect for enums!
    const (
        Sunday    = iota  // 0
        Monday            // 1
        Tuesday           // 2
        Wednesday         // 3
        Thursday          // 4
        Friday            // 5
        Saturday          // 6
    )
    
    fmt.Println("Wednesday =", Wednesday)  // 3
    
    // Practical iota example: File sizes
    const (
        _  = iota              // 0 (skip)
        KB = 1 << (10 * iota)  // 1 << 10 = 1024
        MB                     // 1 << 20 = 1,048,576
        GB                     // 1 << 30
        TB                     // 1 << 40
    )
    
    fmt.Printf("1 KB = %d bytes\n", KB)   // 1024
    fmt.Printf("1 MB = %d bytes\n", MB)   // 1048576
    
    // ═══════════════════════════════════════
    //      SCOPE AND SHADOWING
    // ═══════════════════════════════════════
    
    outer := "I'm outer"
    {
        outer := "I'm inner (SHADOWED!)"  // New variable, same name
        fmt.Println(outer)                 // "I'm inner (SHADOWED!)"
    }
    fmt.Println(outer)  // "I'm outer" (original unchanged)
    
    // ⚠️ Shadowing is a common bug source — be careful!
}
```

### 📘 2B: Data Types

```go
package main

import (
    "fmt"
    "math"
    "unicode/utf8"
)

func main() {
    // ═══════════════════════════════════════
    //          NUMERIC TYPES
    // ═══════════════════════════════════════
    
    // ── Integers ──
    // Signed: int8, int16, int32, int64, int
    // Unsigned: uint8, uint16, uint32, uint64, uint
    
    var small int8 = 127          // -128 to 127
    var medium int16 = 32767      // -32768 to 32767
    var large int64 = 9223372036854775807
    var auto int = 42             // Platform dependent (32 or 64 bit)
    
    var positive uint8 = 255      // 0 to 255 (byte is alias for uint8)
    var bigPositive uint64 = 18446744073709551615
    
    fmt.Println(small, medium, large, auto, positive, bigPositive)
    
    // ── Floating Points ──
    var price float32 = 99.99     // ~7 decimal digits precision
    var precise float64 = 3.141592653589793  // ~15 digits (USE THIS) ✅
    
    fmt.Println(price, precise)
    fmt.Println("Max float64:", math.MaxFloat64)
    
    // ── Complex Numbers (rarely needed) ──
    var c1 complex64 = 3 + 4i
    var c2 complex128 = complex(5, 12)
    fmt.Println(c1, c2, real(c2), imag(c2))
    
    // ═══════════════════════════════════════
    //         BOOLEAN
    // ═══════════════════════════════════════
    
    isStudent := true
    isPlaced := false
    canApply := isStudent && !isPlaced  // true
    fmt.Println(canApply)
    
    // ═══════════════════════════════════════
    //         STRINGS & RUNES
    // ═══════════════════════════════════════
    
    // Strings are IMMUTABLE sequences of bytes (UTF-8 encoded)
    greeting := "Hello, दुनिया!"  // Supports Unicode natively!
    
    // Length
    fmt.Println(len(greeting))                    // Bytes count (not characters!)
    fmt.Println(utf8.RuneCountInString(greeting))  // Character count ✅
    
    // ── Raw String Literals ──
    // Backticks: no escape sequences, multi-line OK
    rawSQL := `SELECT * FROM users
               WHERE age > 18
               AND city = 'Delhi'`
    fmt.Println(rawSQL)
    
    // ── Interpreted String Literals ──
    // Double quotes: escape sequences processed
    formatted := "Name:\tRahul\nAge:\t21"
    fmt.Println(formatted)
    
    // ── Runes ──
    // A rune = a Unicode code point (alias for int32)
    var r rune = 'अ'           // Hindi character
    fmt.Printf("Rune: %c, Code: %d, Unicode: %U\n", r, r, r)
    // Rune: अ, Code: 2309, Unicode: U+0905
    
    // Iterating strings correctly
    name := "गोलांग"
    for i, ch := range name {
        fmt.Printf("Index: %d, Rune: %c\n", i, ch)
    }
    // ⚠️ Index jumps because Hindi chars are multi-byte!
    
    // ═══════════════════════════════════════
    //       TYPE CONVERSION
    // ═══════════════════════════════════════
    
    // Go has NO implicit conversions — everything explicit
    var myInt int = 42
    var myFloat float64 = float64(myInt)    // int → float64
    var backToInt int = int(myFloat)         // float64 → int (truncates!)
    
    // String conversions
    import "strconv"
    numStr := "42"
    num, err := strconv.Atoi(numStr)      // string → int
    if err != nil {
        fmt.Println("Error:", err)
    }
    str := strconv.Itoa(num)              // int → string
    
    fmt.Println(myFloat, backToInt, num, str)
}
```

### 📊 Data Types Summary Table

```
┌─────────────────────────────────────────────────────────┐
│                  GO DATA TYPES                          │
├──────────────┬──────────────┬───────────────────────────┤
│  Category    │  Type        │  Zero Value / Notes       │
├──────────────┼──────────────┼───────────────────────────┤
│  Boolean     │  bool        │  false                    │
├──────────────┼──────────────┼───────────────────────────┤
│  Integers    │  int         │  0 (platform-dependent)   │
│  (Signed)    │  int8/16/32  │  0                        │
│              │  int64       │  0                        │
├──────────────┼──────────────┼───────────────────────────┤
│  Integers    │  uint        │  0 (platform-dependent)   │
│  (Unsigned)  │  uint8/16/32 │  0                        │
│              │  uint64      │  0                        │
│              │  byte(uint8) │  0                        │
├──────────────┼──────────────┼───────────────────────────┤
│  Floats      │  float32     │  0.0 (~7 digit precision) │
│              │  float64 ✅  │  0.0 (~15 digit precision)│
├──────────────┼──────────────┼───────────────────────────┤
│  Complex     │  complex64   │  (0+0i)                   │
│              │  complex128  │  (0+0i)                   │
├──────────────┼──────────────┼───────────────────────────┤
│  String      │  string      │  "" (empty, immutable)    │
├──────────────┼──────────────┼───────────────────────────┤
│  Rune        │  rune(int32) │  0 (Unicode code point)   │
├──────────────┼──────────────┼───────────────────────────┤
│  Pointer     │  *T          │  nil                      │
├──────────────┼──────────────┼───────────────────────────┤
│  Error       │  error       │  nil                      │
└──────────────┴──────────────┴───────────────────────────┘

💡 Rule of thumb:
   int, float64, string, bool, error — these 5 cover 90% of use cases
```

### ✅ Checkpoint — Phase 2:
- [ ] You know `var` vs `:=` and when to use each
- [ ] You understand zero values (no null surprises!)
- [ ] You can use `const` and `iota` for enums
- [ ] You know the difference between `len()` and `RuneCountInString()`
- [ ] You understand that Go has NO implicit type conversions

---

## PHASE 3: Composite Types & Control Flow 🏗️
**⏱️ 1-2 weeks | Priority: 🔴 CRITICAL**

### 📗 3A: Arrays & Slices

```go
package main

import "fmt"

func main() {
    // ═══════════════════════════════════════
    //            ARRAYS (Fixed Size)
    // ═══════════════════════════════════════
    // Rarely used directly — use slices instead!
    
    var marks [5]int                        // [0, 0, 0, 0, 0]
    marks[0] = 85
    marks[1] = 92
    
    subjects := [3]string{"Math", "Physics", "CS"}  // Literal
    auto := [...]int{10, 20, 30, 40}                 // Size inferred
    
    fmt.Println(marks, subjects, auto)
    fmt.Println("Length:", len(subjects))
    
    // ⚠️ Arrays are VALUE types — copying creates a FULL COPY
    original := [3]int{1, 2, 3}
    copy := original          // Full copy!
    copy[0] = 999
    fmt.Println(original)     // [1 2 3] — unchanged!
    
    // ═══════════════════════════════════════
    //       SLICES (Dynamic — USE THIS!) ✅
    // ═══════════════════════════════════════
    
    // A slice is a REFERENCE to an underlying array
    // Has: pointer + length + capacity
    
    // ── Creating Slices ──
    
    // Method 1: Slice literal
    fruits := []string{"Apple", "Mango", "Banana"}
    
    // Method 2: make() — when you know capacity
    scores := make([]int, 3, 10)   // len=3, cap=10
    // make([]T, length, capacity)
    
    // Method 3: Nil slice
    var empty []int    // nil, len=0, cap=0
    
    // Method 4: From array
    arr := [5]int{10, 20, 30, 40, 50}
    slice := arr[1:4]  // [20, 30, 40] — indexes 1,2,3
    
    fmt.Println(fruits, scores, empty, slice)
    
    // ── Append (Dynamic Growth) ──
    nums := []int{1, 2, 3}
    nums = append(nums, 4)           // Add one
    nums = append(nums, 5, 6, 7)     // Add multiple
    
    more := []int{8, 9, 10}
    nums = append(nums, more...)      // Append another slice
    
    fmt.Println(nums)  // [1 2 3 4 5 6 7 8 9 10]
    
    // ── Length vs Capacity ──
    s := make([]int, 3, 5)
    fmt.Printf("len=%d cap=%d %v\n", len(s), cap(s), s)
    // len=3 cap=5 [0 0 0]
    
    s = append(s, 1)
    fmt.Printf("len=%d cap=%d %v\n", len(s), cap(s), s)
    // len=4 cap=5 [0 0 0 1]   — no reallocation
    
    s = append(s, 2, 3)  // Exceeds capacity!
    fmt.Printf("len=%d cap=%d %v\n", len(s), cap(s), s)
    // len=6 cap=10 [0 0 0 1 2 3]  — capacity DOUBLED
    
    // ── Slicing Syntax ──
    data := []int{0, 1, 2, 3, 4, 5, 6, 7, 8, 9}
    
    fmt.Println(data[2:5])    // [2 3 4]     — index 2 to 4
    fmt.Println(data[:3])     // [0 1 2]     — first 3
    fmt.Println(data[7:])     // [7 8 9]     — from index 7
    fmt.Println(data[:])      // [0 1 ... 9] — full copy reference
    
    // ── Copy Slices ──
    src := []int{1, 2, 3}
    dst := make([]int, len(src))
    copied := copy(dst, src)       // Returns number copied
    fmt.Println(dst, copied)       // [1 2 3] 3
    
    // ── Delete Element (no built-in, use slicing) ──
    s2 := []int{1, 2, 3, 4, 5}
    // Delete index 2 (value 3)
    s2 = append(s2[:2], s2[3:]...)
    fmt.Println(s2)  // [1 2 4 5]
    
    // ── Slice to Array Conversion (Go 1.20+) ──
    sl := []int{1, 2, 3, 4, 5}
    ar := [3]int(sl[:3])      // Slice → Array
    fmt.Println(ar)            // [1 2 3]
}
```

```
┌──────────────────── SLICE INTERNALS ────────────────────┐
│                                                         │
│  slice := []int{10, 20, 30, 40, 50}                    │
│                                                         │
│  ┌─────────────────┐                                    │
│  │ Slice Header    │                                    │
│  │ ┌─────────────┐ │     ┌────┬────┬────┬────┬────┐    │
│  │ │ Pointer ────────────→│ 10 │ 20 │ 30 │ 40 │ 50 │   │
│  │ ├─────────────┤ │     └────┴────┴────┴────┴────┘    │
│  │ │ Length: 5    │ │      Underlying Array              │
│  │ ├─────────────┤ │                                    │
│  │ │ Capacity: 5 │ │                                    │
│  │ └─────────────┘ │                                    │
│  └─────────────────┘                                    │
│                                                         │
│  ⚠️ Slices are REFERENCE types!                         │
│  Passing a slice to a function = both see same data     │
└─────────────────────────────────────────────────────────┘
```

### 📘 3B: Maps

```go
package main

import "fmt"

func main() {
    // ═══════════════════════════════════════
    //              MAPS
    // ═══════════════════════════════════════
    // Key-value pairs (like Python dict, Java HashMap)
    
    // ── Creating Maps ──
    
    // Method 1: Literal
    student := map[string]int{
        "Math":    85,
        "Physics": 92,
        "CS":      98,    // Trailing comma required!
    }
    
    // Method 2: make()
    ages := make(map[string]int)
    ages["Rahul"] = 21
    ages["Priya"] = 22
    
    // Method 3: Nil map (READ-ONLY — writing panics!)
    var nilMap map[string]int   // nil
    // nilMap["key"] = 1        // ❌ PANIC!
    _ = nilMap
    
    fmt.Println(student)
    
    // ── Access ──
    mathScore := student["Math"]
    fmt.Println("Math:", mathScore)
    
    // ── Comma-Ok Idiom (VERY IMPORTANT!) ──
    // Distinguishes "key exists with value 0" from "key doesn't exist"
    
    score, exists := student["English"]
    if exists {
        fmt.Println("English:", score)
    } else {
        fmt.Println("English not found!")  // This runs
    }
    
    // Common pattern:
    if val, ok := student["CS"]; ok {
        fmt.Println("CS score:", val)
    }
    
    // ── Delete ──
    delete(student, "Physics")
    fmt.Println(student)  // Physics removed
    
    // ── Iterate ──
    for subject, score := range student {
        fmt.Printf("%s: %d\n", subject, score)
    }
    // ⚠️ Map iteration order is RANDOM! Not insertion order.
    
    // ── Map of Slices (common pattern) ──
    classStudents := map[string][]string{
        "CSE": {"Rahul", "Priya", "Amit"},
        "ECE": {"Sneha", "Vikram"},
    }
    classStudents["CSE"] = append(classStudents["CSE"], "Neha")
    fmt.Println(classStudents)
}
```

### 📕 3C: Structs

```go
package main

import (
    "encoding/json"
    "fmt"
)

// ═══════════════════════════════════════
//            STRUCTS
// ═══════════════════════════════════════
// Go's version of classes (but NO inheritance!)

// Define a struct
type Student struct {
    Name       string   `json:"name"`              // Struct tags!
    RollNo     int      `json:"roll_no"`
    CGPA       float64  `json:"cgpa"`
    Subjects   []string `json:"subjects,omitempty"` // Omit if empty
    IsPlaced   bool     `json:"is_placed"`
    college    string   // lowercase = unexported (private)
}

// ── Embedding Structs (Composition over Inheritance) ──
type Address struct {
    City    string `json:"city"`
    State   string `json:"state"`
    Pincode int    `json:"pincode"`
}

type Employee struct {
    Student            // Embedded! Employee "has-a" Student
    Address            // Embedded! Employee "has-a" Address
    Company string     `json:"company"`
    Salary  int        `json:"salary"`
}

func main() {
    // ── Creating Structs ──
    
    // Method 1: Named fields (RECOMMENDED ✅)
    s1 := Student{
        Name:     "Rahul Sharma",
        RollNo:   101,
        CGPA:     8.5,
        Subjects: []string{"DSA", "OS", "DBMS"},
        IsPlaced: false,
    }
    
    // Method 2: Positional (fragile — don't use)
    // s2 := Student{"Priya", 102, 9.1, nil, true, "IIT"}
    
    // Method 3: Zero value struct
    var s3 Student   // All fields are zero values
    
    // Method 4: Pointer to struct
    s4 := &Student{
        Name:   "Amit",
        RollNo: 103,
    }
    
    fmt.Println(s1.Name, s1.CGPA)
    fmt.Println(s3)
    fmt.Println(s4.Name)  // Go auto-dereferences! No need for (*s4).Name
    
    // ── Struct Tags & JSON ──
    jsonData, _ := json.MarshalIndent(s1, "", "  ")
    fmt.Println(string(jsonData))
    /*
    {
      "name": "Rahul Sharma",
      "roll_no": 101,
      "cgpa": 8.5,
      "subjects": ["DSA", "OS", "DBMS"],
      "is_placed": false
    }
    */
    
    // JSON → Struct
    jsonStr := `{"name": "Sneha", "roll_no": 104, "cgpa": 9.2}`
    var s5 Student
    json.Unmarshal([]byte(jsonStr), &s5)
    fmt.Println(s5)  // {Sneha 104 9.2 [] false }
    
    // ── Embedded Structs ──
    emp := Employee{
        Student: Student{Name: "Vikram", RollNo: 105, CGPA: 8.0},
        Address: Address{City: "Bangalore", State: "Karnataka", Pincode: 560001},
        Company: "Google",
        Salary:  2500000,
    }
    
    // Access embedded fields DIRECTLY!
    fmt.Println(emp.Name)      // "Vikram" — from Student
    fmt.Println(emp.City)      // "Bangalore" — from Address
    fmt.Println(emp.Company)   // "Google" — from Employee
}
```

### 📗 3D: Control Flow

```go
package main

import "fmt"

func main() {
    // ═══════════════════════════════════════
    //          CONDITIONALS
    // ═══════════════════════════════════════
    
    // ── if / else ──
    cgpa := 8.5
    
    if cgpa >= 9.0 {
        fmt.Println("Distinction!")
    } else if cgpa >= 7.0 {
        fmt.Println("First Class")
    } else {
        fmt.Println("Keep improving")
    }
    
    // ── if with initialization (Go specialty!) ──
    if score := calculateScore(); score > 80 {
        fmt.Println("Great score:", score)
    }
    // 'score' doesn't exist here — scoped to if block!
    
    // ── switch (much more powerful than C/Java) ──
    day := "Wednesday"
    
    switch day {
    case "Monday", "Tuesday", "Wednesday", "Thursday", "Friday":
        fmt.Println("Weekday — study hard!")
    case "Saturday":
        fmt.Println("Hackathon day!")
    case "Sunday":
        fmt.Println("Rest day")
    default:
        fmt.Println("Invalid day")
    }
    // ⚠️ No `break` needed — Go doesn't fall through by default!
    // Use `fallthrough` keyword if you WANT fall-through (rare)
    
    // ── Tagless switch (like if-else chain) ──
    marks := 75
    switch {
    case marks >= 90:
        fmt.Println("A+")
    case marks >= 80:
        fmt.Println("A")
    case marks >= 70:
        fmt.Println("B")
    default:
        fmt.Println("C")
    }
    
    // ═══════════════════════════════════════
    //              LOOPS
    // ═══════════════════════════════════════
    // Go has ONLY `for` — no while, no do-while
    
    // ── Classic for loop ──
    for i := 0; i < 5; i++ {
        fmt.Print(i, " ")  // 0 1 2 3 4
    }
    fmt.Println()
    
    // ── While-style ──
    count := 0
    for count < 5 {
        fmt.Print(count, " ")
        count++
    }
    fmt.Println()
    
    // ── Infinite loop ──
    // for {
    //     // Use break to exit
    // }
    
    // ── for range (iterate collections) ──
    
    // Slice
    fruits := []string{"Apple", "Mango", "Banana"}
    for index, fruit := range fruits {
        fmt.Printf("%d: %s\n", index, fruit)
    }
    
    // Ignore index
    for _, fruit := range fruits {
        fmt.Println(fruit)
    }
    
    // Map
    scores := map[string]int{"Math": 85, "CS": 98}
    for subject, score := range scores {
        fmt.Printf("%s: %d\n", subject, score)
    }
    
    // String (iterates RUNES, not bytes!)
    for i, ch := range "Go भाषा" {
        fmt.Printf("%d: %c\n", i, ch)
    }
    
    // ── break & continue ──
    for i := 0; i < 10; i++ {
        if i == 3 { continue }  // Skip 3
        if i == 7 { break }     // Stop at 7
        fmt.Print(i, " ")       // 0 1 2 4 5 6
    }
    fmt.Println()
    
    // ── Labeled break (nested loops) ──
    outer:
    for i := 0; i < 3; i++ {
        for j := 0; j < 3; j++ {
            if i == 1 && j == 1 {
                break outer  // Breaks OUTER loop
            }
            fmt.Printf("(%d,%d) ", i, j)
        }
    }
}
```

### ✅ Checkpoint — Phase 3:
- [ ] You understand arrays vs slices (use slices!)
- [ ] You can use `make()`, `append()`, `copy()` for slices
- [ ] You know the comma-ok idiom for maps
- [ ] You can create structs with JSON tags
- [ ] You understand struct embedding (composition)
- [ ] You can write all loop patterns (`for`, `for range`, infinite)
- [ ] You know Go's switch doesn't need `break`

---

## PHASE 4: Functions, Pointers & Memory 🔧
**⏱️ 1-2 weeks | Priority: 🔴 CRITICAL**

### 📗 4A: Functions

```go
package main

import (
    "errors"
    "fmt"
    "strings"
)

// ── Basic Function ──
func add(a int, b int) int {
    return a + b
}

// ── Short parameter syntax (same type) ──
func multiply(a, b, c int) int {
    return a * b * c
}

// ── Multiple Return Values ── (Go's KILLER feature!)
func divide(a, b float64) (float64, error) {
    if b == 0 {
        return 0, errors.New("division by zero")
    }
    return a / b, nil
}

// ── Named Return Values ──
func calculateStats(nums []int) (sum int, avg float64) {
    for _, n := range nums {
        sum += n
    }
    avg = float64(sum) / float64(len(nums))
    return  // "naked return" — returns named values
}

// ── Variadic Functions (variable args) ──
func total(nums ...int) int {
    sum := 0
    for _, n := range nums {
        sum += n
    }
    return sum
}

// ── Functions as First-Class Citizens ──
func applyOperation(a, b int, op func(int, int) int) int {
    return op(a, b)
}

func main() {
    // Basic calls
    fmt.Println(add(3, 5))          // 8
    fmt.Println(multiply(2, 3, 4))  // 24
    
    // Multiple returns
    result, err := divide(10, 3)
    if err != nil {
        fmt.Println("Error:", err)
    } else {
        fmt.Printf("10/3 = %.2f\n", result)
    }
    
    // Ignore a return value
    _, err2 := divide(10, 0)
    fmt.Println(err2)  // "division by zero"
    
    // Named returns
    sum, avg := calculateStats([]int{80, 90, 85, 95})
    fmt.Printf("Sum: %d, Avg: %.1f\n", sum, avg)
    
    // Variadic
    fmt.Println(total(1, 2, 3))         // 6
    fmt.Println(total(1, 2, 3, 4, 5))   // 15
    
    nums := []int{10, 20, 30}
    fmt.Println(total(nums...))          // Spread slice
    
    // ── Anonymous Functions ──
    greet := func(name string) string {
        return "Hello, " + name + "!"
    }
    fmt.Println(greet("Rahul"))
    
    // Immediately invoked
    func() {
        fmt.Println("I run immediately!")
    }()
    
    // ── Closures ──
    counter := makeCounter()
    fmt.Println(counter())  // 1
    fmt.Println(counter())  // 2
    fmt.Println(counter())  // 3
    
    // ── Higher-order functions ──
    result2 := applyOperation(10, 5, func(a, b int) int {
        return a - b
    })
    fmt.Println(result2)  // 5
    
    // ── Call by Value ──
    // Go ALWAYS passes by value (copies the argument)
    x := 10
    doubleValue(x)
    fmt.Println(x)  // Still 10! (copy was modified, not original)
    
    // To modify original, use pointers (next section)
    doublePointer(&x)
    fmt.Println(x)  // Now 20!
    
    // ⚠️ BUT: slices, maps, channels are REFERENCE types
    // Passing them passes a reference (underlying data is shared)
    s := []int{1, 2, 3}
    modifySlice(s)
    fmt.Println(s)  // [999 2 3] — modified!
}

func makeCounter() func() int {
    count := 0
    return func() int {
        count++  // Closes over 'count'
        return count
    }
}

func doubleValue(n int) { n *= 2 }
func doublePointer(n *int) { *n *= 2 }
func modifySlice(s []int) { s[0] = 999 }
```

### 📘 4B: Pointers

```go
package main

import "fmt"

// ═══════════════════════════════════════
//             POINTERS
// ═══════════════════════════════════════
// Pointers hold the MEMORY ADDRESS of a variable
// Much simpler than C/C++ pointers — NO pointer arithmetic!

type Student struct {
    Name string
    CGPA float64
}

func main() {
    // ── Basics ──
    x := 42
    p := &x         // & = "address of" → p is a pointer to x
    
    fmt.Println(x)   // 42          (value)
    fmt.Println(p)   // 0xc000012088 (memory address)
    fmt.Println(*p)  // 42          (* = "value at" / dereference)
    
    *p = 100         // Modify through pointer
    fmt.Println(x)   // 100 (original changed!)
    
    // ── Pointer zero value is nil ──
    var ptr *int     // nil
    // fmt.Println(*ptr)  // ❌ PANIC: nil pointer dereference!
    
    // Always check:
    if ptr != nil {
        fmt.Println(*ptr)
    }
    
    // ── new() function ──
    q := new(int)    // Allocates memory, returns pointer
    *q = 50
    fmt.Println(*q)  // 50
    
    // ── Pointers with Structs ──
    s := &Student{Name: "Rahul", CGPA: 8.5}
    
    // Go auto-dereferences struct pointers!
    fmt.Println(s.Name)    // "Rahul" (same as (*s).Name)
    s.CGPA = 9.0           // Modify through pointer
    fmt.Println(s.CGPA)    // 9.0
    
    // ── Function using pointer to modify struct ──
    updateCGPA(s, 9.5)
    fmt.Println(s.CGPA)    // 9.5
    
    // ── Pointers with Maps & Slices ──
    // Maps and slices are already references — no pointer needed!
    m := map[string]int{"a": 1}
    updateMap(m)           // No & needed
    fmt.Println(m["a"])    // 999
    
    sl := []int{1, 2, 3}
    updateSlice(sl)        // No & needed
    fmt.Println(sl)        // [999 2 3]
}

func updateCGPA(s *Student, newCGPA float64) {
    s.CGPA = newCGPA
}

func updateMap(m map[string]int) {
    m["a"] = 999
}

func updateSlice(s []int) {
    s[0] = 999
}
```

```
┌──────────── POINTER CHEAT SHEET ──────────────────────┐
│                                                       │
│  &variable  →  Get address (creates pointer)          │
│  *pointer   →  Get value at address (dereference)     │
│  *Type      →  Pointer type declaration               │
│  new(Type)  →  Allocate memory, return pointer        │
│                                                       │
│  Pass to function to MODIFY original:                 │
│  func modify(p *int) { *p = 42 }                     │
│  modify(&x)                                           │
│                                                       │
│  ⚠️ No pointer arithmetic in Go (unlike C)            │
│  ⚠️ Maps, slices, channels = already references       │
│  ⚠️ nil pointer dereference = runtime PANIC           │
└───────────────────────────────────────────────────────┘
```

### 📕 4C: Memory Management & Garbage Collection

```
┌──────────── GO MEMORY MODEL ──────────────────────────┐
│                                                       │
│  STACK (fast, automatic)                              │
│  ├── Local variables                                  │
│  ├── Function parameters                              │
│  ├── Return values                                    │
│  └── Automatically freed when function returns        │
│                                                       │
│  HEAP (slower, garbage collected)                     │
│  ├── Variables that "escape" the function             │
│  ├── Pointers returned from functions                 │
│  ├── Closures capturing variables                     │
│  └── Freed by GC when no longer referenced            │
│                                                       │
│  Go decides stack vs heap automatically!              │
│  You write code, compiler handles allocation.         │
│                                                       │
│  Key insight: Go's GC is concurrent, low-latency      │
│  (~1ms pause times). No manual free() needed!         │
└───────────────────────────────────────────────────────┘
```

### ✅ Checkpoint — Phase 4:
- [ ] You can write functions with multiple return values
- [ ] You understand variadic functions and closures
- [ ] You know Go is call-by-value (and why pointers matter)
- [ ] You can use `&`, `*`, and `new()` correctly
- [ ] You know maps/slices are references (no pointer needed)
- [ ] You understand stack vs heap (conceptually)

---

## PHASE 5: Methods, Interfaces & Generics 🎯
**⏱️ 2 weeks | Priority: 🔴 CRITICAL (This is Go's OOP replacement)**

### 📗 5A: Methods

```go
package main

import (
    "fmt"
    "math"
)

// ── Methods = Functions attached to a Type ──

type Circle struct {
    Radius float64
}

type Rectangle struct {
    Width, Height float64
}

// Value Receiver — works on a COPY
func (c Circle) Area() float64 {
    return math.Pi * c.Radius * c.Radius
}

func (c Circle) Perimeter() float64 {
    return 2 * math.Pi * c.Radius
}

// Pointer Receiver — works on the ORIGINAL (can modify!)
func (c *Circle) Scale(factor float64) {
    c.Radius *= factor   // Modifies the original circle
}

func (r Rectangle) Area() float64 {
    return r.Width * r.Height
}

func main() {
    c := Circle{Radius: 5}
    fmt.Printf("Area: %.2f\n", c.Area())           // 78.54
    fmt.Printf("Perimeter: %.2f\n", c.Perimeter())  // 31.42
    
    c.Scale(2)  // Doubles radius
    fmt.Printf("New area: %.2f\n", c.Area())         // 314.16
    
    r := Rectangle{Width: 10, Height: 5}
    fmt.Printf("Rectangle area: %.2f\n", r.Area())   // 50.00
}

// ┌─────────────────────────────────────────────────────┐
// │     WHEN TO USE VALUE vs POINTER RECEIVER?          │
// │                                                     │
// │  Value Receiver:                                    │
// │  ✅ Small structs (≤ 3 fields)                      │
// │  ✅ Read-only methods                               │
// │  ✅ When you want immutability                      │
// │                                                     │
// │  Pointer Receiver:                                  │
// │  ✅ Need to MODIFY the struct                       │
// │  ✅ Large structs (avoid copying)                   │
// │  ✅ Consistency — if one method needs pointer,      │
// │     make ALL methods pointer receivers              │
// │                                                     │
// │  Rule of thumb: When in doubt, use pointer receiver │
// └─────────────────────────────────────────────────────┘
```

### 📘 5B: Interfaces (Go's MOST POWERFUL Feature)

```go
package main

import (
    "fmt"
    "math"
)

// ═══════════════════════════════════════
//           INTERFACES
// ═══════════════════════════════════════
// An interface defines BEHAVIOR (what methods a type must have)
// Go interfaces are IMPLICIT — no "implements" keyword!
// If a type has the methods, it automatically satisfies the interface

// Define interface
type Shape interface {
    Area() float64
    Perimeter() float64
}

// Stringer interface (from fmt package)
// type Stringer interface {
//     String() string
// }

type Circle struct{ Radius float64 }
type Rectangle struct{ Width, Height float64 }

// Circle implements Shape (IMPLICITLY — no "implements" keyword!)
func (c Circle) Area() float64      { return math.Pi * c.Radius * c.Radius }
func (c Circle) Perimeter() float64 { return 2 * math.Pi * c.Radius }
func (c Circle) String() string     { return fmt.Sprintf("Circle(r=%.1f)", c.Radius) }

// Rectangle implements Shape (IMPLICITLY!)
func (r Rectangle) Area() float64      { return r.Width * r.Height }
func (r Rectangle) Perimeter() float64 { return 2 * (r.Width + r.Height) }
func (r Rectangle) String() string     { return fmt.Sprintf("Rect(%g×%g)", r.Width, r.Height) }

// Function that accepts ANY Shape
func printShapeInfo(s Shape) {
    fmt.Printf("Shape: %v\n", s)
    fmt.Printf("  Area: %.2f\n", s.Area())
    fmt.Printf("  Perimeter: %.2f\n", s.Perimeter())
}

// Calculate total area of any shapes
func totalArea(shapes []Shape) float64 {
    total := 0.0
    for _, s := range shapes {
        total += s.Area()
    }
    return total
}

func main() {
    c := Circle{Radius: 5}
    r := Rectangle{Width: 10, Height: 4}
    
    // Both satisfy Shape interface!
    printShapeInfo(c)
    printShapeInfo(r)
    
    // Slice of interfaces
    shapes := []Shape{
        Circle{Radius: 3},
        Rectangle{Width: 5, Height: 8},
        Circle{Radius: 7},
    }
    fmt.Printf("Total area: %.2f\n", totalArea(shapes))
    
    // ── Empty Interface (any) ──
    // interface{} or `any` (Go 1.18+) accepts ANY type
    var anything any
    anything = 42
    anything = "hello"
    anything = Circle{Radius: 5}
    fmt.Println(anything)
    
    // ── Type Assertions ──
    // Extract the concrete type from an interface
    var s Shape = Circle{Radius: 10}
    
    // Safe assertion with comma-ok
    if circle, ok := s.(Circle); ok {
        fmt.Println("It's a circle with radius:", circle.Radius)
    }
    
    // ── Type Switch ──
    describeShape(Circle{Radius: 5})
    describeShape(Rectangle{Width: 3, Height: 4})
    describeShape("not a shape")
    
    // ── Interface Embedding ──
    // Compose interfaces from smaller ones
}

// Type switch
func describeShape(i interface{}) {
    switch v := i.(type) {
    case Circle:
        fmt.Printf("Circle with radius %.1f\n", v.Radius)
    case Rectangle:
        fmt.Printf("Rectangle %g × %g\n", v.Width, v.Height)
    default:
        fmt.Printf("Unknown type: %T\n", v)
    }
}

// ── Interface Embedding ──
type Reader interface {
    Read(p []byte) (n int, err error)
}

type Writer interface {
    Write(p []byte) (n int, err error)
}

// Composed interface!
type ReadWriter interface {
    Reader
    Writer
}
```

```
┌──────────── GO INTERFACES MENTAL MODEL ───────────────┐
│                                                       │
│  🐍 Python: "If it walks like a duck..." (duck typing)│
│  ☕ Java:   class Dog implements Animal { }            │
│  🔵 Go:     If Dog has Speak() and Walk(),             │
│              it IS an Animal. No declaration needed!   │
│                                                       │
│  KEY INTERFACES TO KNOW:                              │
│  ├── fmt.Stringer    → String() string                │
│  ├── error           → Error() string                 │
│  ├── io.Reader       → Read([]byte) (int, error)      │
│  ├── io.Writer       → Write([]byte) (int, error)     │
│  ├── sort.Interface  → Len(), Less(), Swap()          │
│  └── http.Handler    → ServeHTTP(w, r)                │
│                                                       │
│  DESIGN PRINCIPLE:                                    │
│  "Accept interfaces, return structs"                  │
│  — Go Proverb                                         │
└───────────────────────────────────────────────────────┘
```

### 📕 5C: Generics (Go 1.18+)

```go
package main

import (
    "fmt"
    "golang.org/x/exp/constraints"
)

// ═══════════════════════════════════════
//            GENERICS
// ═══════════════════════════════════════
// Write functions/types that work with MULTIPLE types
// Added in Go 1.18 (2022) — relatively new!

// ── Generic Function ──
// [T comparable] means T can be any type that supports == and !=
func Contains[T comparable](slice []T, target T) bool {
    for _, item := range slice {
        if item == target {
            return true
        }
    }
    return false
}

// ── Type Constraint ──
// constraints.Ordered = int, float64, string, etc. (types that support < > ==)
func Max[T constraints.Ordered](a, b T) T {
    if a > b {
        return a
    }
    return b
}

func Min[T constraints.Ordered](a, b T) T {
    if a < b {
        return a
    }
    return b
}

// ── Generic Type ──
type Stack[T any] struct {
    items []T
}

func (s *Stack[T]) Push(item T) {
    s.items = append(s.items, item)
}

func (s *Stack[T]) Pop() (T, bool) {
    var zero T
    if len(s.items) == 0 {
        return zero, false
    }
    item := s.items[len(s.items)-1]
    s.items = s.items[:len(s.items)-1]
    return item, true
}

func (s *Stack[T]) Peek() (T, bool) {
    var zero T
    if len(s.items) == 0 {
        return zero, false
    }
    return s.items[len(s.items)-1], true
}

func (s *Stack[T]) Size() int {
    return len(s.items)
}

// ── Custom Constraint Interface ──
type Number interface {
    ~int | ~int32 | ~int64 | ~float32 | ~float64
    // ~ means "underlying type" (includes type aliases)
}

func Sum[T Number](nums []T) T {
    var total T
    for _, n := range nums {
        total += n
    }
    return total
}

func main() {
    // Type inference — Go figures out T automatically
    fmt.Println(Contains([]int{1, 2, 3, 4, 5}, 3))       // true
    fmt.Println(Contains([]string{"a", "b", "c"}, "d"))   // false
    
    fmt.Println(Max(10, 20))         // 20
    fmt.Println(Max("apple", "mango"))  // "mango" (string comparison)
    
    // Generic Stack
    intStack := Stack[int]{}
    intStack.Push(10)
    intStack.Push(20)
    intStack.Push(30)
    
    val, _ := intStack.Pop()
    fmt.Println(val)  // 30
    
    strStack := Stack[string]{}
    strStack.Push("Hello")
    strStack.Push("World")
    
    // Sum with custom constraint
    fmt.Println(Sum([]int{1, 2, 3, 4, 5}))          // 15
    fmt.Println(Sum([]float64{1.1, 2.2, 3.3}))      // 6.6
}
```

### ✅ Checkpoint — Phase 5:
- [ ] You can write methods with value & pointer receivers
- [ ] You understand implicit interface satisfaction
- [ ] You can use type assertions and type switches
- [ ] You know the key stdlib interfaces (Stringer, Reader, Writer, error)
- [ ] You can write generic functions and types
- [ ] You understand "Accept interfaces, return structs"

---

## PHASE 6: Error Handling & Code Organization 📦
**⏱️ 1 week | Priority: 🔴 CRITICAL**

### 📗 6A: Error Handling (Go's Controversial Feature)

```go
package main

import (
    "errors"
    "fmt"
    "os"
    "strconv"
)

// ═══════════════════════════════════════
//         ERROR HANDLING IN GO
// ═══════════════════════════════════════
// Go has NO exceptions (no try/catch)!
// Errors are VALUES returned from functions.
// "Don't panic!" — Go Proverb

// ── The `error` interface ──
// type error interface {
//     Error() string
// }

// ── Creating Errors ──

// Method 1: errors.New
var ErrNotFound = errors.New("not found")           // Sentinel error
var ErrUnauthorized = errors.New("unauthorized")

// Method 2: fmt.Errorf (with formatting)
func findStudent(id int) (string, error) {
    if id <= 0 {
        return "", fmt.Errorf("invalid student ID: %d", id)
    }
    if id > 1000 {
        return "", ErrNotFound
    }
    return "Rahul", nil  // nil = no error
}

// ── Custom Error Type ──
type ValidationError struct {
    Field   string
    Message string
}

func (e *ValidationError) Error() string {
    return fmt.Sprintf("validation error: %s - %s", e.Field, e.Message)
}

func validateAge(age int) error {
    if age < 0 || age > 150 {
        return &ValidationError{
            Field:   "age",
            Message: fmt.Sprintf("%d is not a valid age", age),
        }
    }
    return nil
}

// ── Wrapping Errors (Go 1.13+) ──
func readConfig(path string) ([]byte, error) {
    data, err := os.ReadFile(path)
    if err != nil {
        // Wrap error with context using %w
        return nil, fmt.Errorf("reading config %s: %w", path, err)
    }
    return data, nil
}

func main() {
    // ── Basic error handling pattern ──
    name, err := findStudent(42)
    if err != nil {
        fmt.Println("Error:", err)
        return
    }
    fmt.Println("Found:", name)
    
    // ── Sentinel error checking ──
    _, err = findStudent(9999)
    if errors.Is(err, ErrNotFound) {
        fmt.Println("Student not found!")  // This runs
    }
    
    // ── Custom error type checking ──
    err = validateAge(-5)
    var valErr *ValidationError
    if errors.As(err, &valErr) {
        fmt.Printf("Field: %s, Message: %s\n", valErr.Field, valErr.Message)
    }
    
    // ── Error wrapping chain ──
    _, err = readConfig("/nonexistent/config.yaml")
    if err != nil {
        fmt.Println(err)
        // "reading config /nonexistent/config.yaml: open ...: no such file"
        
        // Unwrap to check underlying error
        if errors.Is(err, os.ErrNotExist) {
            fmt.Println("File doesn't exist!")
        }
    }
    
    // ── Multiple error returns (common pattern) ──
    num, err := strconv.Atoi("not_a_number")
    if err != nil {
        fmt.Println("Parse error:", err)
    } else {
        fmt.Println("Parsed:", num)
    }
    
    // ═══════════════════════════════════════
    //      PANIC AND RECOVER (RARE!)
    // ═══════════════════════════════════════
    // panic = unrecoverable error (like exception)
    // recover = catch a panic (in defer)
    // USE SPARINGLY — prefer returning errors!
    
    fmt.Println(safeDivide(10, 0))  // "recovered: division by zero"
}

func safeDivide(a, b int) (result string) {
    defer func() {
        if r := recover(); r != nil {
            result = fmt.Sprintf("recovered: %v", r)
        }
    }()
    
    if b == 0 {
        panic("division by zero")
    }
    return fmt.Sprintf("%d", a/b)
}
```

```
┌────────── ERROR HANDLING PATTERNS CHEAT SHEET ────────┐
│                                                       │
│  1. BASIC:                                            │
│     val, err := doSomething()                         │
│     if err != nil { return err }                      │
│                                                       │
│  2. WRAP WITH CONTEXT:                                │
│     if err != nil {                                   │
│         return fmt.Errorf("doing X: %w", err)         │
│     }                                                 │
│                                                       │
│  3. SENTINEL CHECK:                                   │
│     if errors.Is(err, ErrNotFound) { ... }            │
│                                                       │
│  4. TYPE CHECK:                                       │
│     var myErr *MyError                                │
│     if errors.As(err, &myErr) { ... }                 │
│                                                       │
│  5. PANIC/RECOVER: Almost never. Only for truly       │
│     unrecoverable situations.                         │
│                                                       │
│  Rule: Handle errors where you can ADD CONTEXT.       │
│  Don't just pass them up blindly.                     │
└───────────────────────────────────────────────────────┘
```

### 📘 6B: Code Organization — Modules & Packages

```
┌─────────── GO PROJECT STRUCTURE ──────────────────────┐
│                                                       │
│  myproject/                                           │
│  ├── go.mod              # Module definition          │
│  ├── go.sum              # Dependency checksums       │
│  ├── main.go             # Entry point                │
│  ├── internal/           # Private to this module     │
│  │   ├── auth/                                        │
│  │   │   └── auth.go                                  │
│  │   └── database/                                    │
│  │       └── db.go                                    │
│  ├── pkg/                # Public, reusable packages  │
│  │   ├── models/                                      │
│  │   │   └── user.go                                  │
│  │   └── utils/                                       │
│  │       └── helpers.go                               │
│  ├── cmd/                # CLI entry points           │
│  │   ├── server/                                      │
│  │   │   └── main.go                                  │
│  │   └── cli/                                         │
│  │       └── main.go                                  │
│  └── api/                # API definitions            │
│      └── handlers/                                    │
│          └── user.go                                  │
│                                                       │
└───────────────────────────────────────────────────────┘
```

```bash
# ── Module Commands ──

# Initialize a module
go mod init github.com/rahul/myproject

# Add a dependency
go get github.com/gin-gonic/gin

# Clean up unused dependencies
go mod tidy

# Vendor dependencies (copy into project)
go mod vendor

# ── go.mod file ──
# module github.com/rahul/myproject
# 
# go 1.22
# 
# require (
#     github.com/gin-gonic/gin v1.9.1
#     github.com/lib/pq v1.10.9
# )
```

```go
// ── Package Rules ──

// 1. Package name = directory name
// File: pkg/models/user.go
package models  // matches directory name

type User struct {
    ID    int
    Name  string
    Email string
}

// 2. Exported (public) = Capital letter
func NewUser(name, email string) User {  // Exported ✅
    return User{Name: name, Email: email}
}

func validateEmail(email string) bool {  // unexported (private)
    return len(email) > 0
}

// 3. Import in main.go
// import "github.com/rahul/myproject/pkg/models"
// user := models.NewUser("Rahul", "rahul@email.com")
```

### ✅ Checkpoint — Phase 6:
- [ ] You handle errors with `if err != nil` confidently
- [ ] You know `errors.Is()`, `errors.As()`, `fmt.Errorf("%w")`
- [ ] You understand panic/recover (and when NOT to use it)
- [ ] You can organize a Go project with packages and modules
- [ ] You know `go mod init`, `go mod tidy`, `go get`

---

## PHASE 7: Concurrency (Go's Superpower!) ⚡
**⏱️ 2-3 weeks | Priority: 🔴 CRITICAL — This is what makes Go special**

> 🧒 **ELI5 — The Chai Stall Analogy:**
> Imagine a chai stall at your college. **Without concurrency:** one chaiwala, one customer at a time — huge queue. **With goroutines:** 1000 chaiwalas, all working simultaneously, all on one stove (CPU), taking turns efficiently. Go can handle **millions** of goroutines using just a few OS threads. Java/C++ threads are like hiring actual people — expensive (2MB each). Goroutines are like lightweight tasks — just 2KB each!

### 📗 7A: Goroutines

```go
package main

import (
    "fmt"
    "sync"
    "time"
)

// ═══════════════════════════════════════
//          GOROUTINES
// ═══════════════════════════════════════
// A goroutine is a lightweight thread managed by Go runtime
// Just add `go` before a function call!

func downloadFile(filename string) {
    fmt.Printf("⏳ Downloading %s...\n", filename)
    time.Sleep(2 * time.Second)  // Simulate download
    fmt.Printf("✅ Downloaded %s\n", filename)
}

func main() {
    start := time.Now()
    
    // ── Without goroutines (sequential) ──
    // downloadFile("file1.pdf")   // 2s
    // downloadFile("file2.pdf")   // 2s
    // downloadFile("file3.pdf")   // 2s
    // Total: ~6 seconds
    
    // ── With goroutines (concurrent) ──
    var wg sync.WaitGroup
    
    files := []string{"file1.pdf", "file2.pdf", "file3.pdf"}
    
    for _, file := range files {
        wg.Add(1)               // Increment counter
        go func(f string) {     // Launch goroutine
            defer wg.Done()     // Decrement counter when done
            downloadFile(f)
        }(file)
    }
    
    wg.Wait()  // Wait for all goroutines to finish
    
    fmt.Printf("\n⏱️ Total time: %v\n", time.Since(start))
    // ~2 seconds (all 3 downloaded concurrently!)
    
    // ⚠️ Common mistake: Goroutine with loop variable
    // WRONG:
    // for _, file := range files {
    //     go func() {
    //         downloadFile(file)  // All goroutines see LAST value!
    //     }()
    // }
    
    // CORRECT: Pass as parameter (shown above)
    // or use Go 1.22+ where loop variable is per-iteration
}
```

### 📘 7B: Channels

```go
package main

import (
    "fmt"
    "time"
)

// ═══════════════════════════════════════
//           CHANNELS
// ═══════════════════════════════════════
// Channels are pipes for goroutines to communicate
// "Don't communicate by sharing memory; share memory by communicating."

func main() {
    // ── Unbuffered Channel (synchronous) ──
    ch := make(chan string)  // Create channel
    
    go func() {
        time.Sleep(1 * time.Second)
        ch <- "Hello from goroutine!"  // SEND to channel
    }()
    
    msg := <-ch  // RECEIVE from channel (blocks until data available)
    fmt.Println(msg)
    
    // ── Buffered Channel (asynchronous up to buffer size) ──
    buffered := make(chan int, 3)  // Buffer size 3
    
    buffered <- 10  // Doesn't block (buffer not full)
    buffered <- 20
    buffered <- 30
    // buffered <- 40  // Would BLOCK — buffer full!
    
    fmt.Println(<-buffered)  // 10 (FIFO)
    fmt.Println(<-buffered)  // 20
    fmt.Println(<-buffered)  // 30
    
    // ── Channel Direction (restrict in function signature) ──
    // chan<- int  → send-only channel
    // <-chan int  → receive-only channel
    
    ch2 := make(chan int)
    go producer(ch2)
    consumer(ch2)
    
    // ── Select Statement (multiplexing channels) ──
    ch3 := make(chan string)
    ch4 := make(chan string)
    
    go func() {
        time.Sleep(1 * time.Second)
        ch3 <- "from channel 3"
    }()
    go func() {
        time.Sleep(500 * time.Millisecond)
        ch4 <- "from channel 4"
    }()
    
    // Wait for WHICHEVER is ready first
    for i := 0; i < 2; i++ {
        select {
        case msg1 := <-ch3:
            fmt.Println("Received:", msg1)
        case msg2 := <-ch4:
            fmt.Println("Received:", msg2)
        // case <-time.After(2 * time.Second):
        //     fmt.Println("Timeout!")
        }
    }
    
    // ── Worker Pool Pattern ──
    fmt.Println("\n--- Worker Pool ---")
    workerPoolDemo()
}

// Send-only channel parameter
func producer(ch chan<- int) {
    for i := 0; i < 5; i++ {
        ch <- i
    }
    close(ch)  // IMPORTANT: close channel when done sending
}

// Receive-only channel parameter
func consumer(ch <-chan int) {
    // range over channel — stops when channel is closed
    for val := range ch {
        fmt.Printf("Received: %d\n", val)
    }
}

// ── Worker Pool Pattern ──
func workerPoolDemo() {
    jobs := make(chan int, 100)
    results := make(chan int, 100)
    
    // Start 3 workers
    for w := 1; w <= 3; w++ {
        go worker(w, jobs, results)
    }
    
    // Send 9 jobs
    for j := 1; j <= 9; j++ {
        jobs <- j
    }
    close(jobs)
    
    // Collect results
    for r := 1; r <= 9; r++ {
        fmt.Printf("Result: %d\n", <-results)
    }
}

func worker(id int, jobs <-chan int, results chan<- int) {
    for j := range jobs {
        fmt.Printf("Worker %d processing job %d\n", id, j)
        time.Sleep(200 * time.Millisecond)
        results <- j * 2  // Send result
    }
}
```

### 📕 7C: sync Package & Context

```go
package main

import (
    "context"
    "fmt"
    "sync"
    "time"
)

func main() {
    // ═══════════════════════════════════════
    //         sync.Mutex (Mutual Exclusion)
    // ═══════════════════════════════════════
    
    var counter int
    var mu sync.Mutex
    var wg sync.WaitGroup
    
    for i := 0; i < 1000; i++ {
        wg.Add(1)
        go func() {
            defer wg.Done()
            mu.Lock()         // Lock before accessing shared data
            counter++
            mu.Unlock()       // Unlock after
        }()
    }
    
    wg.Wait()
    fmt.Println("Counter:", counter)  // Always 1000 ✅
    // Without mutex: race condition → random number
    
    // ═══════════════════════════════════════
    //        context Package
    // ═══════════════════════════════════════
    // Used for: deadlines, cancellation, passing request-scoped values
    // CRITICAL for production Go code!
    
    // ── Context with Timeout ──
    ctx, cancel := context.WithTimeout(context.Background(), 2*time.Second)
    defer cancel()
    
    result := make(chan string, 1)
    
    go func() {
        // Simulate slow API call
        time.Sleep(3 * time.Second)
        result <- "API response"
    }()
    
    select {
    case res := <-result:
        fmt.Println("Got result:", res)
    case <-ctx.Done():
        fmt.Println("Timeout! Error:", ctx.Err())  // This runs (3s > 2s deadline)
    }
    
    // ── Context with Cancellation ──
    ctx2, cancel2 := context.WithCancel(context.Background())
    
    go func(ctx context.Context) {
        for {
            select {
            case <-ctx.Done():
                fmt.Println("Worker stopped:", ctx.Err())
                return
            default:
                fmt.Println("Working...")
                time.Sleep(500 * time.Millisecond)
            }
        }
    }(ctx2)
    
    time.Sleep(2 * time.Second)
    cancel2()  // Signal the goroutine to stop
    time.Sleep(100 * time.Millisecond)
}
```

### 📗 7D: Concurrency Patterns

```
┌────────── GO CONCURRENCY PATTERNS ────────────────────┐
│                                                       │
│  1. FAN-OUT: One goroutine → Multiple goroutines      │
│     ┌─→ Worker 1                                      │
│  In ├─→ Worker 2                                      │
│     └─→ Worker 3                                      │
│                                                       │
│  2. FAN-IN: Multiple goroutines → One channel         │
│     Worker 1 ─→┐                                      │
│     Worker 2 ─→├─→ Merged Output                      │
│     Worker 3 ─→┘                                      │
│                                                       │
│  3. PIPELINE: Chain of processing stages              │
│     Generate → Square → Filter → Print                │
│        ↓          ↓        ↓        ↓                 │
│     (channel)  (channel) (channel) (output)           │
│                                                       │
│  4. WORKER POOL: Fixed number of workers, job queue   │
│     Jobs channel → [Worker 1, Worker 2, Worker 3]     │
│                    → Results channel                  │
│                                                       │
│  5. SEMAPHORE: Limit concurrent operations            │
│     sem := make(chan struct{}, maxConcurrent)          │
└───────────────────────────────────────────────────────┘
```

```bash
# ── Race Detector (ALWAYS use during development!) ──
go run -race main.go
go test -race ./...

# If race detected, output shows exactly where the data race is
```

### ✅ Checkpoint — Phase 7:
- [ ] You can launch goroutines and use `sync.WaitGroup`
- [ ] You understand buffered vs unbuffered channels
- [ ] You can use `select` for multiplexing
- [ ] You know the Worker Pool pattern
- [ ] You can use `sync.Mutex` for shared data
- [ ] You understand `context` for timeouts and cancellation
- [ ] You always run with `-race` flag during development

---

## PHASE 8: Standard Library & Testing 📚
**⏱️ 2 weeks | Priority: 🟡 IMPORTANT**

### 📗 8A: Key Standard Library Packages

| Package | What It Does | Must-Know? |
|---------|-------------|------------|
| `fmt` | Formatting I/O (Print, Sprintf, Scanf) | 🔴 Yes |
| `os` | OS interaction (files, env vars, args) | 🔴 Yes |
| `io` | I/O interfaces (Reader, Writer) | 🔴 Yes |
| `bufio` | Buffered I/O (Scanner, Reader) | 🟡 |
| `strings` | String manipulation (Split, Join, Contains) | 🔴 Yes |
| `strconv` | String ↔ number conversion | 🔴 Yes |
| `encoding/json` | JSON marshal/unmarshal | 🔴 Yes |
| `net/http` | HTTP client & server | 🔴 Yes |
| `time` | Time, duration, timers | 🔴 Yes |
| `flag` | CLI argument parsing | 🟡 |
| `regexp` | Regular expressions | 🟡 |
| `slog` | Structured logging (Go 1.21+) | 🟡 |
| `sync` | Concurrency primitives | 🔴 Yes |
| `context` | Deadlines, cancellation | 🔴 Yes |
| `errors` | Error handling utilities | 🔴 Yes |
| `testing` | Unit tests, benchmarks | 🔴 Yes |
| `go/embed` | Embed files in binary | 🟢 |

### 📘 8B: Testing

```go
// ═══════════════════════════════════════
//          TESTING IN GO
// ═══════════════════════════════════════
// File: math.go
package mathutil

func Add(a, b int) int      { return a + b }
func Multiply(a, b int) int { return a * b }
func Divide(a, b float64) (float64, error) {
    if b == 0 {
        return 0, fmt.Errorf("division by zero")
    }
    return a / b, nil
}
func IsPrime(n int) bool {
    if n < 2 { return false }
    for i := 2; i*i <= n; i++ {
        if n%i == 0 { return false }
    }
    return true
}

// ──────────────────────────────────────
// File: math_test.go (MUST end in _test.go)
package mathutil

import "testing"

// ── Basic Test ──
func TestAdd(t *testing.T) {
    result := Add(2, 3)
    if result != 5 {
        t.Errorf("Add(2, 3) = %d; want 5", result)
    }
}

// ── Table-Driven Tests (Go's RECOMMENDED pattern!) ──
func TestMultiply(t *testing.T) {
    tests := []struct {
        name     string
        a, b     int
        expected int
    }{
        {"positive numbers", 3, 4, 12},
        {"with zero", 5, 0, 0},
        {"negative numbers", -3, 4, -12},
        {"both negative", -3, -4, 12},
        {"large numbers", 1000, 1000, 1000000},
    }
    
    for _, tt := range tests {
        t.Run(tt.name, func(t *testing.T) {
            result := Multiply(tt.a, tt.b)
            if result != tt.expected {
                t.Errorf("Multiply(%d, %d) = %d; want %d",
                    tt.a, tt.b, result, tt.expected)
            }
        })
    }
}

// ── Test with error checking ──
func TestDivide(t *testing.T) {
    t.Run("valid division", func(t *testing.T) {
        result, err := Divide(10, 3)
        if err != nil {
            t.Fatalf("unexpected error: %v", err)
        }
        if result < 3.33 || result > 3.34 {
            t.Errorf("Divide(10, 3) = %f; want ~3.33", result)
        }
    })
    
    t.Run("division by zero", func(t *testing.T) {
        _, err := Divide(10, 0)
        if err == nil {
            t.Error("expected error for division by zero")
        }
    })
}

// ── Benchmark ──
func BenchmarkIsPrime(b *testing.B) {
    for i := 0; i < b.N; i++ {
        IsPrime(7919)  // Large prime
    }
}
```

```bash
# ── Running Tests ──
go test ./...                     # All tests in all packages
go test -v ./...                  # Verbose output
go test -run TestAdd ./...        # Run specific test
go test -race ./...               # With race detector
go test -cover ./...              # Show coverage %
go test -coverprofile=cover.out ./...   # Generate coverage file
go tool cover -html=cover.out     # View coverage in browser

# ── Running Benchmarks ──
go test -bench=. ./...
go test -bench=BenchmarkIsPrime -benchmem ./...
```

### ✅ Checkpoint — Phase 8:
- [ ] You know the key stdlib packages and when to use each
- [ ] You can write table-driven tests
- [ ] You can write and run benchmarks
- [ ] You achieve >80% test coverage on your code

---

## PHASE 9: Ecosystem — Web, DB, CLI, gRPC 🌐
**⏱️ 3-4 weeks | Priority: 🟡 IMPORTANT (🔴 for backend roles)**

### 📗 9A: Web Development

| Approach | What | When to Use | Priority |
|----------|------|-------------|----------|
| **net/http** | Standard library HTTP | Small projects, learning | 🔴 Learn first |
| **Gin** | Fast, minimalist framework | Most popular, production use | 🔴 Learn this |
| **Echo** | Similar to Gin, slightly more features | Alternative to Gin | 🟡 |
| **Fiber** | Express.js-like, built on fasthttp | Coming from Node.js | 🟢 |
| **Chi** | Lightweight router, idiomatic Go | stdlib-compatible | 🟡 |

```go
// ── net/http (Standard Library) ──
package main

import (
    "encoding/json"
    "fmt"
    "log"
    "net/http"
)

type Response struct {
    Message string `json:"message"`
    Status  int    `json:"status"`
}

func main() {
    // Routes
    http.HandleFunc("/", homeHandler)
    http.HandleFunc("/api/hello", helloHandler)
    http.HandleFunc("/api/users", usersHandler)
    
    fmt.Println("🚀 Server running on http://localhost:8080")
    log.Fatal(http.ListenAndServe(":8080", nil))
}

func homeHandler(w http.ResponseWriter, r *http.Request) {
    fmt.Fprintf(w, "Welcome to Go Web Server!")
}

func helloHandler(w http.ResponseWriter, r *http.Request) {
    name := r.URL.Query().Get("name")
    if name == "" {
        name = "World"
    }
    
    resp := Response{
        Message: fmt.Sprintf("Hello, %s!", name),
        Status:  200,
    }
    
    w.Header().Set("Content-Type", "application/json")
    json.NewEncoder(w).Encode(resp)
}

func usersHandler(w http.ResponseWriter, r *http.Request) {
    switch r.Method {
    case http.MethodGet:
        // Return users
        json.NewEncoder(w).Encode(map[string]string{"users": "list"})
    case http.MethodPost:
        // Create user
        var user map[string]string
        json.NewDecoder(r.Body).Decode(&user)
        w.WriteHeader(http.StatusCreated)
        json.NewEncoder(w).Encode(user)
    default:
        http.Error(w, "Method not allowed", http.StatusMethodNotAllowed)
    }
}
```

```go
// ── Gin Framework (Most Popular) ──
// go get github.com/gin-gonic/gin

package main

import (
    "net/http"
    "github.com/gin-gonic/gin"
)

type User struct {
    ID    int    `json:"id"`
    Name  string `json:"name" binding:"required"`
    Email string `json:"email" binding:"required,email"`
}

var users = []User{
    {ID: 1, Name: "Rahul", Email: "rahul@email.com"},
    {ID: 2, Name: "Priya", Email: "priya@email.com"},
}

func main() {
    r := gin.Default()  // Includes logger and recovery middleware
    
    // Routes
    api := r.Group("/api/v1")
    {
        api.GET("/users", getUsers)
        api.GET("/users/:id", getUserByID)
        api.POST("/users", createUser)
        api.PUT("/users/:id", updateUser)
        api.DELETE("/users/:id", deleteUser)
    }
    
    r.Run(":8080")
}

func getUsers(c *gin.Context) {
    c.JSON(http.StatusOK, gin.H{"data": users})
}

func getUserByID(c *gin.Context) {
    id := c.Param("id")
    c.JSON(http.StatusOK, gin.H{"id": id})
}

func createUser(c *gin.Context) {
    var newUser User
    if err := c.ShouldBindJSON(&newUser); err != nil {
        c.JSON(http.StatusBadRequest, gin.H{"error": err.Error()})
        return
    }
    newUser.ID = len(users) + 1
    users = append(users, newUser)
    c.JSON(http.StatusCreated, newUser)
}

func updateUser(c *gin.Context) { /* ... */ }
func deleteUser(c *gin.Context) { /* ... */ }
```

### 📘 9B: Database Access

| Library | Type | Best For | Priority |
|---------|------|----------|----------|
| **database/sql** | Standard library | Learning, simple queries | 🟡 |
| **pgx** | PostgreSQL driver | Direct Postgres access | 🔴 |
| **GORM** | Full ORM | Rapid development | 🔴 Learn this |
| **sqlx** | Enhanced database/sql | Complex SQL without ORM | 🟡 |
| **sqlc** | Code gen from SQL | Type-safe SQL | 🟡 |

```go
// ── GORM Example ──
// go get gorm.io/gorm gorm.io/driver/postgres

package main

import (
    "fmt"
    "gorm.io/driver/postgres"
    "gorm.io/gorm"
)

type Student struct {
    gorm.Model          // Adds ID, CreatedAt, UpdatedAt, DeletedAt
    Name     string     `gorm:"not null"`
    RollNo   int        `gorm:"uniqueIndex"`
    CGPA     float64
    Branch   string     `gorm:"default:'CSE'"`
    IsPlaced bool       `gorm:"default:false"`
}

func main() {
    dsn := "host=localhost user=postgres password=secret dbname=college port=5432"
    db, err := gorm.Open(postgres.Open(dsn), &gorm.Config{})
    if err != nil {
        panic("failed to connect to database")
    }
    
    // Auto-migrate (creates table)
    db.AutoMigrate(&Student{})
    
    // CREATE
    student := Student{Name: "Rahul", RollNo: 101, CGPA: 8.5}
    db.Create(&student)
    
    // READ
    var found Student
    db.First(&found, "roll_no = ?", 101)
    fmt.Println(found.Name)
    
    // READ all with condition
    var toppers []Student
    db.Where("cgpa > ?", 8.0).Find(&toppers)
    
    // UPDATE
    db.Model(&found).Update("CGPA", 9.0)
    
    // DELETE
    db.Delete(&found)
}
```

### 📕 9C: Building CLIs, gRPC & Logging

```
┌────────── GO ECOSYSTEM MAP ──────────────────────────┐
│                                                       │
│  🖥️ CLI Tools:                                       │
│  ├── Cobra (most popular CLI framework)               │
│  ├── urfave/cli (simpler alternative)                 │
│  └── bubbletea (TUI / terminal UIs)                   │
│                                                       │
│  🔗 gRPC:                                             │
│  ├── google.golang.org/grpc                           │
│  ├── Protocol Buffers for API definition              │
│  └── Used by: Google, Netflix, Square                 │
│                                                       │
│  📝 Logging:                                          │
│  ├── slog (stdlib, Go 1.21+) — start here             │
│  ├── Zerolog (fastest, zero allocation)               │
│  └── Zap (by Uber, very popular)                      │
│                                                       │
│  🔄 Realtime:                                         │
│  ├── Melody (WebSocket)                               │
│  └── Centrifugo (realtime messaging server)           │
└───────────────────────────────────────────────────────┘
```

### ✅ Checkpoint — Phase 9:
- [ ] Built a REST API with net/http AND Gin
- [ ] Connected to a database with GORM or pgx
- [ ] Built a simple CLI tool with Cobra
- [ ] Understand what gRPC is and when to use it

---

## PHASE 10: Toolchain, Advanced Topics & Deployment 🔧
**⏱️ 2 weeks | Priority: 🟡 IMPORTANT (🔴 for DevOps/senior roles)**

### 📗 10A: Go Toolchain

```bash
# ═══════════════════════════════════════
#          GO TOOLCHAIN CHEAT SHEET
# ═══════════════════════════════════════

# Core Commands
go run main.go           # Compile + run (development)
go build -o myapp .      # Build binary
go install .             # Build + install to $GOPATH/bin
go fmt ./...             # Format ALL code (standard format)
go vet ./...             # Find suspicious code patterns
go test ./...            # Run all tests
go test -race ./...      # Tests + race detector
go mod tidy              # Clean up dependencies
go doc fmt.Println       # View documentation
go clean -cache          # Clear build cache
go version               # Show Go version

# Code Quality
go vet ./...                          # Built-in linter
goimports -w .                        # Fix imports + format
golangci-lint run ./...               # Mega-linter (30+ linters)
staticcheck ./...                     # Advanced static analysis

# Security
govulncheck ./...                     # Check for known vulnerabilities

# Performance Profiling
go test -bench=. -cpuprofile=cpu.out  # CPU profile
go tool pprof cpu.out                  # Analyze profile
go test -bench=. -memprofile=mem.out  # Memory profile
go test -trace=trace.out              # Execution trace
go tool trace trace.out

# Build for different platforms (Cross-compilation!)
GOOS=linux GOARCH=amd64 go build -o myapp-linux .
GOOS=windows GOARCH=amd64 go build -o myapp.exe .
GOOS=darwin GOARCH=arm64 go build -o myapp-mac .

# Code Generation
go generate ./...                     # Run //go:generate directives

# Build Tags
go build -tags "production" .         # Conditional compilation
```

### 📘 10B: Advanced Topics

| Topic | What It Is | When You Need It | Priority |
|-------|-----------|------------------|----------|
| **Escape Analysis** | Where Go allocates memory (stack vs heap) | Performance optimization | 🟢 |
| **Reflection** | Inspect/modify types at runtime | Frameworks, serialization | 🟡 |
| **Unsafe Package** | Bypass type safety, raw memory access | Low-level, FFI | 🟢 Rare |
| **Build Constraints** | Compile different code per OS/arch | Cross-platform code | 🟡 |
| **CGO** | Call C code from Go | Using C libraries | 🟢 Avoid if possible |
| **Compiler/Linker Flags** | Custom build options | Embedding version info | 🟡 |
| **Plugins** | Dynamic loading of Go code | Extensible apps | 🟢 Rare |

```bash
# Escape Analysis (see what goes to heap)
go build -gcflags="-m" main.go

# Embed version at build time
go build -ldflags="-X main.version=1.2.3" -o myapp .
```

### 📕 10C: Deployment

```dockerfile
# ── Multi-stage Dockerfile for Go (Production-Ready) ──
# Stage 1: Build
FROM golang:1.22-alpine AS builder
WORKDIR /app
COPY go.mod go.sum ./
RUN go mod download
COPY . .
RUN CGO_ENABLED=0 GOOS=linux go build -o /app/server ./cmd/server

# Stage 2: Run (minimal image)
FROM alpine:3.19
RUN apk --no-cache add ca-certificates
WORKDIR /app
COPY --from=builder /app/server .
EXPOSE 8080
CMD ["./server"]

# Result: ~15MB image (vs ~1GB with full Go image!)
```

---

## 📅 Week-by-Week Schedule (at 2 hrs/day)

```
┌──────────┬───────────────────────────────────────────────────┐
│  WEEK    │  WHAT TO DO                                       │
├──────────┼───────────────────────────────────────────────────┤
│  1       │  Setup, Hello World, variables, data types        │
│  2       │  Arrays, slices, maps, structs, JSON              │
│  3       │  Control flow, loops, for range                   │
│  4       │  Functions deep-dive, closures, pointers          │
│  5       │  Methods, interfaces (CRITICAL WEEK)              │
│  6       │  Generics, error handling patterns                │
│  7       │  Modules, packages, project structure             │
│  8       │  🏗️ Mini Project: CLI tool or simple API          │
│  9       │  Goroutines + Channels (CRITICAL WEEK)            │
│  10      │  sync, context, concurrency patterns              │
│  11      │  Race detection, worker pools, fan-in/fan-out     │
│  12      │  Standard library tour + testing mastery          │
│  13      │  net/http → Build REST API from scratch           │
│  14      │  Gin framework + GORM database                    │
│  15      │  🏗️ Portfolio Project: Full REST API + DB + Auth  │
│  16      │  gRPC, CLI with Cobra, logging                    │
│  17      │  Toolchain, profiling, cross-compilation          │
│  18      │  Docker deployment, CI/CD pipeline                │
│  19-20   │  🏗️ Capstone Project: Microservice or DevOps tool │
│  21-22   │  Advanced topics, open source contribution        │
└──────────┴───────────────────────────────────────────────────┘
```

---

## 🏗️ Portfolio Project Ideas

| Level | Project | Skills Demonstrated |
|-------|---------|-------------------|
| 🟢 Beginner | **URL Shortener CLI + API** — Shorten URLs, store in SQLite, CLI to create/list, HTTP API to redirect | Go basics, net/http, database, CLI |
| 🟡 Medium | **Real-time Chat Server** — WebSocket server, multiple rooms, user authentication, message history | Goroutines, channels, WebSocket, database |
| 🟡 Medium | **Task Queue System** — Producer-consumer with worker pools, retry logic, dashboard API | Concurrency, channels, patterns |
| 🔴 Advanced | **API Gateway / Rate Limiter** — Reverse proxy, rate limiting, authentication, logging, metrics | Middleware, concurrency, system design |
| 🔴 Advanced | **Distributed Key-Value Store** — In-memory store with persistence, replication, HTTP API | Concurrency, networking, system design |
| 🔴 Advanced | **Kubernetes Operator** — Custom controller for managing a specific application on K8s | CRDs, controller patterns, K8s API |

---

## 💼 How Go Helps in Placements & Career (India)

| Company | Uses Go For | India Presence |
|---------|------------|----------------|
| **Google** | Core infrastructure, Cloud services | ✅ Bangalore, Hyderabad |
| **Uber** | Microservices backbone | ✅ Bangalore, Hyderabad |
| **Razorpay** | Payment processing backend | ✅ Bangalore |
| **Zerodha** | Trading platform (Kite) | ✅ Bangalore |
| **Flipkart** | Backend services | ✅ Bangalore |
| **Swiggy** | Backend microservices | ✅ Bangalore |
| **Dream11** | Real-time gaming backend | ✅ Mumbai |
| **Zomato** | Backend services | ✅ Gurgaon |
| **Postman** | Core platform | ✅ Bangalore |
| **CRED** | Backend services | ✅ Bangalore |

### 🎯 Interview Topics — Go-Specific

```
Most Asked in Go Interviews:
┌────────────────────────────────────────────────┐
│ 1. Goroutines vs OS Threads (ALWAYS asked!)    │
│ 2. Channels: buffered vs unbuffered            │
│ 3. Interface implementation (implicit)         │
│ 4. Error handling patterns                     │
│ 5. Slice internals (len vs cap, append)        │
│ 6. Context package (timeout, cancellation)     │
│ 7. Mutex vs Channel (when to use which)        │
│ 8. defer, panic, recover                       │
│ 9. Map concurrency (sync.Map vs mutex)         │
│ 10. Garbage collection (how GC works in Go)    │
│ 11. Value vs Pointer receivers                 │
│ 12. init() function behavior                   │
└────────────────────────────────────────────────┘
```

---

## 📚 Complete Resource Bank

### 🎥 YouTube (Free)
| Channel / Video | What It Covers | Language |
|----------------|---------------|----------|
| **Tech With Tim** — Go Full Course | Complete beginner course | English |
| **Akhil Sharma** — Go Projects | Project-based Go learning | English (Indian) |
| **Anthony GG** — Go Production Code | Real-world Go patterns | English |
| **NerdCademy** — Go Crash Course | Quick overview | English |
| **Hitesh Choudhary** — Go Playlist | Hindi Go tutorials | Hindi |
| **Go in One Video** — Traversy Media | Fast overview | English |

### 📖 Books & Docs
| Resource | Type | Cost |
|----------|------|------|
| **"The Go Programming Language"** (Donovan & Kernighan) | 📖 THE Go bible | ~₹700 |
| **"Learning Go"** (Jon Bodner, O'Reilly) | 📖 Modern, idiomatic | ~₹800 |
| **"Let's Go"** + **"Let's Go Further"** (Alex Edwards) | 📖 Web dev focused | ~₹1500 |
| **Go by Example** (gobyexample.com) | 🌐 Interactive examples | Free |
| **Effective Go** (go.dev/doc/effective_go) | 📖 Official style guide | Free |
| **A Tour of Go** (go.dev/tour) | 🌐 Interactive tutorial | Free |
| **roadmap.sh/golang** | 🗺️ Interactive roadmap | Free |

### 🛠️ Practice
| Platform | What |
|----------|------|
| **Exercism — Go Track** | Guided exercises with mentoring | Free |
| **Go Playground** (go.dev/play) | Browser-based Go coding | Free |
| **LeetCode** (filter by Go) | DSA in Go | Free |
| **Gophercises** (gophercises.com) | Project-based exercises | Free |

---

## 🎯 What Should You Do RIGHT NOW?

```
IF you know Python/Java/C++ well:
  → Go's syntax will feel EASY. Start Phase 2 today.
  → Focus extra time on Phase 5 (interfaces) and Phase 7 (concurrency)
  → These are where Go is fundamentally DIFFERENT.

IF you're a complete beginner to programming:
  → Go is actually a GREAT first language (simple, strict, good habits)
  → Take Phase 2-4 slowly (2-3 weeks each)

IF you're targeting backend placements:
  → Rush to Phase 9 (Web + DB) by week 10
  → Build 2 projects: REST API + Concurrent system
  → Go on resume = instant differentiation from Java/Python crowd

IF you're targeting DevOps/Cloud:
  → This is THE language. Docker, K8s, Terraform = all Go.
  → After Phase 7, start building CLI tools and infrastructure code
  → Combine with your Kubernetes roadmap
```
