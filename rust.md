

# 🦀 COMPLETE RUST ROADMAP
### From Zero to Systems Programming Mastery — Structured & Actionable

---

## 📍 Where You Are → Where You'll Go

```
🟢 BEGINNER            🟡 INTERMEDIATE          🔴 ADVANCED            🏆 PRO
   (Weeks 1-6)            (Weeks 7-14)            (Weeks 15-22)         (Weeks 23-28)
   
   Syntax, Variables,     Ownership, Borrowing,   Lifetimes, Macros,    Web/Systems/Game
   Control Flow,          Traits, Generics,       Async, Concurrency,   WASM, Embedded,
   Structs, Enums         Error Handling          Unsafe Rust           Ecosystem Mastery
```

---

## 🧒 ELI5: What Is Rust & Why Should You Care?

```
🏠 The Building Materials Analogy:

  C/C++ = Building with raw materials (bricks, cement, steel)
  ───────────────────────────────────────────────────────────
  Full control. Maximum speed. But one wrong measurement?
  The building COLLAPSES. Buffer overflow. Segfault. 
  Use-after-free. Memory leak. You're responsible for EVERYTHING.
  → 70% of Microsoft's CVEs are memory safety bugs in C/C++.


  Python/Java = Building with pre-fab modules (IKEA furniture)
  ──────────────────────────────────────────────────────────────
  Safe. Easy. But: a "Garbage Collector" follows you around,
  cleaning up. You can't control WHEN it cleans. Pauses happen.
  It's slower. Uses more memory. Not suitable for OS kernels,
  game engines, embedded devices.


  Rust = Building with SMART materials (self-checking bricks) 🦀
  ────────────────────────────────────────────────────────────────
  Same raw-material SPEED as C/C++. But the bricks CHECK
  THEMSELVES at compile time. The compiler is your strict 
  but brilliant professor — catches bugs BEFORE they happen.
  No garbage collector. No runtime overhead. No segfaults.

  ┌──────────────────────────────────────────────────────────────┐
  │                                                              │
  │  C/C++  : "Here's a gun. Don't shoot your foot." 🔫         │
  │  Python : "No guns allowed. Here's a nerf gun." 🔫          │
  │  Rust   : "Here's a gun. But it won't fire at feet." 🦀🔫  │
  │                                                              │
  │  The Rust compiler is the STRICTEST teacher you'll ever have.│
  │  It REFUSES to compile unsafe code.                          │
  │  Frustrating at first. Life-saving in production.            │
  │                                                              │
  └──────────────────────────────────────────────────────────────┘
```

```
🤔 WHY LEARN RUST IN 2025?

  ┌──────────────────────────────────────────────────────────────┐
  │                                                              │
  │  📊 INDUSTRY ADOPTION:                                       │
  │  • #1 Most Loved Language — Stack Overflow Survey (8 years!) │
  │  • Linux Kernel now accepts Rust (alongside C!)              │
  │  • Google: Android, Chrome, Fuchsia OS                       │
  │  • Microsoft: Windows kernel, Azure                          │
  │  • Amazon: AWS Firecracker, Bottlerocket                     │
  │  • Meta: Source control (Mononoke), Libra                    │
  │  • Discord: Switched from Go to Rust (10x perf boost)       │
  │  • Cloudflare: Performance-critical edge services            │
  │  • Dropbox: File sync engine                                 │
  │  • Firefox: Servo browser engine                             │
  │                                                              │
  │  💰 SALARY (India 2025):                                     │
  │  • Rust Developer: ₹15-50 LPA (scarce talent = high demand) │
  │  • Systems Programmer: ₹20-60 LPA                           │
  │  • Blockchain/Web3 (Solana): ₹25-80 LPA                     │
  │                                                              │
  │  🎯 BEST FOR:                                                │
  │  • Systems programming (OS, drivers, embedded)               │
  │  • WebAssembly (run near-native code in browsers)            │
  │  • Game engines & game development                           │
  │  • CLI tools (ripgrep, bat, fd, exa — all Rust!)             │
  │  • Blockchain (Solana, Polkadot — written in Rust)           │
  │  • High-performance web backends                             │
  │  • Networking tools & infrastructure                         │
  │                                                              │
  └──────────────────────────────────────────────────────────────┘
```

```
⚡ RUST vs THE WORLD — Quick Comparison

┌────────────────────┬──────────┬──────────┬────────┬──────────┬──────────┐
│  Feature           │  Rust    │  C/C++   │  Go    │  Python  │  Java    │
├────────────────────┼──────────┼──────────┼────────┼──────────┼──────────┤
│ Performance        │ ⭐⭐⭐⭐⭐│ ⭐⭐⭐⭐⭐│ ⭐⭐⭐⭐│ ⭐⭐     │ ⭐⭐⭐   │
│ Memory Safety      │ ⭐⭐⭐⭐⭐│ ⭐⭐     │ ⭐⭐⭐⭐│ ⭐⭐⭐⭐⭐│ ⭐⭐⭐⭐ │
│ Concurrency Safety │ ⭐⭐⭐⭐⭐│ ⭐⭐     │ ⭐⭐⭐⭐│ ⭐⭐     │ ⭐⭐⭐   │
│ Learning Curve     │ ⭐⭐     │ ⭐⭐     │ ⭐⭐⭐⭐│ ⭐⭐⭐⭐⭐│ ⭐⭐⭐   │
│ Garbage Collector  │ ❌ None  │ ❌ None  │ ✅ Yes │ ✅ Yes   │ ✅ Yes   │
│ Null/Nil           │ ❌ None  │ ✅ NULL  │ ✅ nil │ ✅ None  │ ✅ null  │
│ Zero-Cost Abstract.│ ✅ Yes   │ ✅ Yes   │ ❌ No  │ ❌ No    │ ❌ No    │
│ Compile Time       │ Slow 🐢 │ Medium   │ Fast 🚀│ N/A      │ Medium   │
│ Ecosystem Maturity │ Growing  │ Mature   │ Good   │ Mature   │ Mature   │
│ Job Market (India) │ Growing📈│ Stable   │ High   │ Highest  │ High     │
└────────────────────┴──────────┴──────────┴────────┴──────────┴──────────┘

💡 Rust's superpower: C/C++ PERFORMANCE + Python/Java SAFETY
   without a garbage collector. That's the magic. 🪄
```

---

## 🟢 PHASE 1: FOUNDATIONS — Introduction & Language Basics (Weeks 1–6)

### Week 1: Introduction & Environment Setup

| # | Topic | Priority | Est. Hours | Status |
|---|-------|----------|-----------|--------|
| 1 | **What is Rust?** — history, Mozilla origins, goals | 🔴 Critical | 1h | ⬜ |
| 2 | **Why use Rust?** — safety, speed, concurrency without GC | 🔴 Critical | 1h | ⬜ |
| 3 | **Installing Rust & Cargo** — `rustup`, `rustc`, `cargo` | 🔴 Critical | 1h | ⬜ |
| 4 | **IDEs & Toolchains** — VS Code + rust-analyzer, IntelliJ + Rust plugin | 🔴 Critical | 1h | ⬜ |
| 5 | **Rust Playground** — play.rust-lang.org for quick experiments | 🟡 Important | 0.5h | ⬜ |
| 6 | **Cargo Basics** — `new`, `build`, `run`, `test`, `check`, `clippy` | 🔴 Critical | 2h | ⬜ |

```bash
# 🦀 INSTALLING RUST (All Platforms)

# ─── Install rustup (official installer) ─────
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh

# ─── Verify installation ─────────────────────
rustc --version          # rustc 1.78.0 (2024-xx-xx)
cargo --version          # cargo 1.78.0
rustup --version         # rustup 1.27.0

# ─── Update Rust ──────────────────────────────
rustup update

# ─── Essential components ─────────────────────
rustup component add clippy     # Linter (catches common mistakes)
rustup component add rustfmt    # Code formatter
rustup component add rust-src   # Source code (for IDE completions)
```

```bash
# 📦 CARGO — Rust's Build Tool & Package Manager
# Think: npm for JavaScript, pip for Python, but BETTER.

# ─── Create a new project ────────────────────
cargo new hello_rust            # Creates binary project
cargo new my_lib --lib          # Creates library project

# ─── Project structure ────────────────────────
# hello_rust/
# ├── Cargo.toml                # Dependencies & metadata (like package.json)
# ├── src/
# │   └── main.rs               # Entry point
# └── target/                   # Build artifacts (auto-generated)

# ─── Daily commands ───────────────────────────
cargo build                     # Compile (debug mode)
cargo build --release           # Compile (optimized, for production)
cargo run                       # Compile + Run
cargo check                     # Type-check only (FAST — use often!)
cargo test                      # Run all tests
cargo clippy                    # Lint (catches 500+ common mistakes)
cargo fmt                       # Format code (like prettier/black)
cargo doc --open                # Generate & open documentation
cargo add serde                 # Add dependency (Rust 1.62+)

# 💡 PRO TIP: Use `cargo check` instead of `cargo build` during development.
#    It's 3-10x faster because it skips code generation.
```

```rust
// 🦀 YOUR FIRST RUST PROGRAM

fn main() {
    // println! is a MACRO (note the !) — not a regular function
    println!("Hello, Rust! 🦀");
    
    // String formatting (similar to Python f-strings)
    let name = "Rahul";
    let year = 3;
    println!("Hi, I'm {name}, a {year}rd year BTech CSE student!");
    
    // Positional arguments
    println!("{0} is learning {1}. {1} is awesome!", name, "Rust");
    
    // Debug printing (for any type that implements Debug)
    let numbers = vec![1, 2, 3, 4, 5];
    println!("Numbers: {:?}", numbers);       // Debug format
    println!("Pretty: {:#?}", numbers);       // Pretty debug format
}
```

---

### Week 2: Variables, Data Types & Constants

| # | Topic | Priority | Est. Hours | Status |
|---|-------|----------|-----------|--------|
| 7 | **Variables & Mutability** — `let`, `let mut`, immutable by default | 🔴 Critical | 2h | ⬜ |
| 8 | **Data Types — Scalar** — integers, floats, booleans, characters | 🔴 Critical | 2h | ⬜ |
| 9 | **Data Types — Compound** — tuples, arrays | 🔴 Critical | 2h | ⬜ |
| 10 | **Strings** — `String` vs `&str`, string operations | 🔴 Critical | 3h | ⬜ |
| 11 | **Constants & Shadowing** — `const`, variable shadowing | 🟡 Important | 1h | ⬜ |
| 12 | **Type Inference & Annotations** — Rust figures out types, but you can specify | 🟡 Important | 1h | ⬜ |

```rust
// 🔒 VARIABLES — Immutable by Default (This is DIFFERENT from most languages!)

fn main() {
    // ─── Immutability (default) ─────────────────
    let x = 5;
    // x = 6;   // ❌ COMPILE ERROR! Variables are immutable by default!
    //           //    "cannot assign twice to immutable variable"
    
    // ─── Mutability (opt-in) ────────────────────
    let mut y = 5;
    println!("y = {y}");     // y = 5
    y = 6;                   // ✅ OK, y is mut
    println!("y = {y}");     // y = 6
    
    // ─── Shadowing (re-declare same name) ───────
    let z = 5;
    let z = z + 1;           // ✅ OK! New variable with same name
    let z = z * 2;           // ✅ Can even change type!
    let z = "now I'm a string";  // ✅ z is now a &str!
    println!("z = {z}");
    
    // ─── Constants (truly immutable, computed at compile time) ──
    const MAX_STUDENTS: u32 = 500;
    const PI: f64 = 3.14159265358979;
    // Constants: SCREAMING_SNAKE_CASE, must have type annotation
    // Available for entire program lifetime
}

// 💡 WHY immutable by default?
// ┌──────────────────────────────────────────────────────────┐
// │  In Python/Java: Everything is mutable. Any function     │
// │  can change any variable. In a 10,000-line codebase,     │
// │  you have NO IDEA what might change your data.           │
// │                                                          │
// │  In Rust: If it's not `mut`, NOBODY can change it.       │
// │  You know EXACTLY what can be modified. Bugs ↓↓↓         │
// │                                                          │
// │  Analogy: Bank locker vs open shelf.                     │
// │  Immutable = locked. You choose what to unlock (mut).    │
// └──────────────────────────────────────────────────────────┘
```

```rust
// 📊 DATA TYPES — Complete Reference

fn main() {
    // ═══════════════════════════════════════════
    // SCALAR TYPES (single values)
    // ═══════════════════════════════════════════

    // ─── Integers ───────────────────────────────
    let a: i8   = -128;           // -128 to 127
    let b: i16  = -32_768;       // Underscores for readability!
    let c: i32  = 2_147_483_647; // DEFAULT integer type
    let d: i64  = 9_223_372_036_854_775_807;
    let e: i128 = 170_141_183_460_469_231_731_687_303_715_884_105_727;
    let f: isize = 42;           // Platform-dependent (32 or 64 bit)
    
    let g: u8   = 255;           // Unsigned: 0 to 255
    let h: u16  = 65_535;
    let i: u32  = 4_294_967_295;
    let j: u64  = 18_446_744_073_709_551_615;
    let k: u128 = 340_282_366_920_938_463_463_374_607_431_768_211_455;
    let l: usize = 42;           // Used for indexing

    // Integer literals
    let decimal     = 98_222;     // 98222
    let hex         = 0xff;       // 255
    let octal       = 0o77;      // 63
    let binary      = 0b1111_0000; // 240
    let byte        = b'A';      // 65 (u8 only)

    // ─── Floats ─────────────────────────────────
    let pi: f64 = 3.14159;      // DEFAULT float (64-bit, double precision)
    let e: f32 = 2.71828;       // 32-bit (less precise, rarely used)

    // ─── Boolean ────────────────────────────────
    let is_rustacean: bool = true;
    let is_easy: bool = false;   // 1 byte in memory

    // ─── Character ──────────────────────────────
    let letter: char = 'A';     // 4 bytes! Supports Unicode
    let emoji: char = '🦀';     // Yes, emojis are valid chars!
    let hindi: char = 'अ';      // Unicode support!

    // ═══════════════════════════════════════════
    // COMPOUND TYPES (multiple values)
    // ═══════════════════════════════════════════

    // ─── Tuple (fixed size, different types) ────
    let student: (&str, u32, f64) = ("Rahul", 101, 8.5);
    let (name, roll, cgpa) = student;  // Destructuring!
    println!("{} has roll {} with CGPA {}", name, roll, cgpa);
    println!("Name: {}", student.0);   // Dot indexing

    // ─── Array (fixed size, SAME type) ──────────
    let marks: [i32; 5] = [85, 90, 78, 92, 88];  // [type; size]
    let zeros = [0; 10];          // [0, 0, 0, 0, 0, 0, 0, 0, 0, 0]
    println!("First mark: {}", marks[0]);
    // marks[10]; // ❌ RUNTIME PANIC! Bounds checking (unlike C!)
}
```

```
📊 INTEGER TYPES — Quick Reference

┌───────┬────────────┬────────────────────────────┬─────────────┐
│ Type  │ Size       │ Range                      │ Use Case    │
├───────┼────────────┼────────────────────────────┼─────────────┤
│ i8    │ 1 byte     │ -128 to 127                │ Tiny values │
│ i16   │ 2 bytes    │ -32,768 to 32,767          │ Signals     │
│ i32   │ 4 bytes    │ -2.1B to 2.1B              │ DEFAULT ✅  │
│ i64   │ 8 bytes    │ -9.2×10¹⁸ to 9.2×10¹⁸     │ Large nums  │
│ i128  │ 16 bytes   │ ±1.7×10³⁸                  │ Crypto      │
│ isize │ ptr size   │ Platform-dependent         │ Indexing    │
├───────┼────────────┼────────────────────────────┼─────────────┤
│ u8    │ 1 byte     │ 0 to 255                   │ Bytes, RGB  │
│ u16   │ 2 bytes    │ 0 to 65,535                │ Ports       │
│ u32   │ 4 bytes    │ 0 to 4.2B                  │ IDs         │
│ u64   │ 8 bytes    │ 0 to 1.8×10¹⁹             │ Timestamps  │
│ u128  │ 16 bytes   │ 0 to 3.4×10³⁸             │ UUIDs       │
│ usize │ ptr size   │ Platform-dependent         │ Indexing ✅ │
└───────┴────────────┴────────────────────────────┴─────────────┘
```

```rust
// 🔤 STRINGS — The Most Confusing Part for Beginners

fn main() {
    // ═══════════════════════════════════════════
    // TWO string types — this confuses EVERYONE
    // ═══════════════════════════════════════════
    
    // &str — String SLICE (borrowed reference, fixed, on stack/binary)
    // Like a READ-ONLY view into a string. Lightweight.
    let greeting: &str = "Hello, Rust!";  // String literal → &str
    
    // String — OWNED string (growable, on heap, you own the memory)
    // Like a Vec<u8> that you can modify.
    let mut name: String = String::from("Rahul");
    name.push_str(" Sharma");   // ✅ Can modify!
    name.push('!');             // Push single char
    println!("{name}");         // "Rahul Sharma!"
    
    // ─── Converting between them ────────────────
    let owned: String = "hello".to_string();    // &str → String
    let owned2: String = String::from("hello"); // &str → String
    let borrowed: &str = &owned;                // String → &str (auto-deref)
    
    // ─── Common operations ──────────────────────
    let s = String::from("Hello, World!");
    println!("Length: {}", s.len());             // 13
    println!("Empty? {}", s.is_empty());         // false
    println!("Contains 'World': {}", s.contains("World")); // true
    println!("Uppercase: {}", s.to_uppercase()); // "HELLO, WORLD!"
    
    // Split
    let csv = "Rahul,Priya,Amit,Sneha";
    let names: Vec<&str> = csv.split(',').collect();
    println!("{:?}", names);  // ["Rahul", "Priya", "Amit", "Sneha"]
    
    // Format (like Python f-strings)
    let formatted = format!("{} scored {} in {}", "Rahul", 95, "DSA");
    println!("{formatted}");

    // ─── String Slicing ─────────────────────────
    let hello = &s[0..5];    // "Hello" (byte indices, careful with UTF-8!)
    let world = &s[7..12];   // "World"
}

// 💡 WHEN TO USE WHICH?
// ┌──────────────────────────────────────────────────────────┐
// │  &str  → When you just need to READ a string            │
// │           Function parameters should prefer &str          │
// │           "I'm borrowing this string for a moment"        │
// │                                                          │
// │  String → When you need to OWN or MODIFY a string        │
// │           Struct fields should use String                 │
// │           "This string belongs to me"                     │
// │                                                          │
// │  Rule: Accept &str, return String                         │
// └──────────────────────────────────────────────────────────┘
```

---

### Week 3: Control Flow & Functions

| # | Topic | Priority | Est. Hours | Status |
|---|-------|----------|-----------|--------|
| 13 | **Conditionals** — `if`/`else`, `if` as expression | 🔴 Critical | 1h | ⬜ |
| 14 | **Loops** — `loop`, `while`, `for`, `break`, `continue`, labels | 🔴 Critical | 2h | ⬜ |
| 15 | **Functions** — declaration, params, return, expressions vs statements | 🔴 Critical | 2h | ⬜ |
| 16 | **Method Syntax** — `impl` blocks, `self`, associated functions | 🔴 Critical | 2h | ⬜ |
| 17 | **Pattern Matching** — `match`, `if let`, `while let` | 🔴 Critical | 3h | ⬜ |
| 18 | **Destructuring** — tuples, structs, enums in patterns | 🟡 Important | 2h | ⬜ |

```rust
// 🔀 CONTROL FLOW — Rust Does Things Differently!

fn main() {
    // ─── if/else (NO parentheses needed!) ───────
    let cgpa = 8.5;
    
    if cgpa >= 9.0 {
        println!("Distinction! 🏆");
    } else if cgpa >= 8.0 {
        println!("First Class! ⭐");
    } else if cgpa >= 6.0 {
        println!("Second Class");
    } else {
        println!("Need improvement");
    }
    
    // 🔥 if is an EXPRESSION (returns a value!) — unlike most languages
    let grade = if cgpa >= 9.0 { "A+" } 
                else if cgpa >= 8.0 { "A" } 
                else { "B" };
    println!("Grade: {grade}");  // "A"
    // Note: both branches must return SAME type!

    // ─── Loops ──────────────────────────────────
    
    // loop = infinite loop (like while true)
    let mut counter = 0;
    let result = loop {
        counter += 1;
        if counter == 10 {
            break counter * 2;  // 🔥 loop can RETURN a value via break!
        }
    };
    println!("Result: {result}");  // 20
    
    // while loop
    let mut n = 5;
    while n > 0 {
        println!("{n}...");
        n -= 1;
    }
    println!("BLAST OFF! 🚀");
    
    // for loop (most common, most idiomatic)
    let marks = [85, 90, 78, 92, 88];
    for mark in marks.iter() {     // or just `for mark in &marks`
        println!("Score: {mark}");
    }
    
    // Range-based for (like Python's range())
    for i in 0..5 {           // 0, 1, 2, 3, 4 (exclusive end)
        print!("{i} ");
    }
    for i in 0..=5 {          // 0, 1, 2, 3, 4, 5 (INCLUSIVE end)
        print!("{i} ");
    }
    
    // Reverse
    for i in (1..=5).rev() {
        println!("{i}...");   // 5, 4, 3, 2, 1
    }
    
    // Loop labels (for nested loops)
    'outer: for i in 0..5 {
        for j in 0..5 {
            if i + j > 5 {
                break 'outer;  // Breaks the OUTER loop!
            }
        }
    }
}
```

```rust
// 🔧 FUNCTIONS — Expressions vs Statements

// Functions use snake_case (like Python, unlike Java)
fn add(a: i32, b: i32) -> i32 {
    a + b   // 🔥 No semicolon = EXPRESSION = implicit return!
    // Same as: return a + b;
}

// IMPORTANT DIFFERENCE:
// a + b    ← Expression (returns value) ✅
// a + b;   ← Statement (returns nothing/unit ()) ❌ as return

fn calculate_grade(cgpa: f64) -> &'static str {
    // match is like switch on steroids
    // It's also an expression — returns a value!
    match cgpa as u32 {
        9..=10 => "A+",
        8 => "A",
        7 => "B",
        6 => "C",
        _ => "F",   // _ = default/catch-all (REQUIRED — match must be exhaustive!)
    }
}

// Multiple return values (via tuple)
fn min_max(list: &[i32]) -> (i32, i32) {
    let mut min = list[0];
    let mut max = list[0];
    for &val in list.iter() {
        if val < min { min = val; }
        if val > max { max = val; }
    }
    (min, max)  // Return tuple
}

fn main() {
    let sum = add(3, 4);
    println!("Sum: {sum}");  // 7
    
    let grade = calculate_grade(8.5);
    println!("Grade: {grade}");  // "A"
    
    let marks = [85, 90, 78, 92, 88];
    let (min, max) = min_max(&marks);  // Destructure!
    println!("Min: {min}, Max: {max}"); // Min: 78, Max: 92
}
```

```rust
// 🎯 PATTERN MATCHING — Rust's Superpower (match, if let, while let)

#[derive(Debug)]
enum PaymentMethod {
    UPI(String),           // Holds UPI ID
    CreditCard(String, u32), // Card number, CVV
    Cash,
    Wallet { balance: f64 }, // Named fields
}

fn process_payment(method: &PaymentMethod, amount: f64) {
    // match MUST cover ALL variants — compiler enforces this!
    match method {
        PaymentMethod::UPI(upi_id) => {
            println!("💳 Paying ₹{amount} via UPI: {upi_id}");
        }
        PaymentMethod::CreditCard(number, _cvv) => {
            // _ prefix means "I know about this but don't need it"
            let masked = format!("****{}", &number[number.len()-4..]);
            println!("💳 Charging ₹{amount} to card {masked}");
        }
        PaymentMethod::Cash => {
            println!("💵 Cash payment of ₹{amount}");
        }
        PaymentMethod::Wallet { balance } if *balance >= amount => {
            // Match GUARD — extra condition!
            println!("👛 Wallet payment: ₹{amount} (balance: ₹{balance})");
        }
        PaymentMethod::Wallet { balance } => {
            println!("❌ Insufficient wallet balance: ₹{balance} < ₹{amount}");
        }
    }
}

fn main() {
    let upi = PaymentMethod::UPI("rahul@okicici".to_string());
    let card = PaymentMethod::CreditCard("4111111111111234".to_string(), 123);
    let wallet = PaymentMethod::Wallet { balance: 500.0 };
    
    process_payment(&upi, 299.0);
    process_payment(&card, 1499.0);
    process_payment(&wallet, 999.0);  // Insufficient!

    // ─── if let — when you only care about ONE variant ──
    let payment = PaymentMethod::UPI("priya@upi".to_string());
    if let PaymentMethod::UPI(id) = &payment {
        println!("UPI detected: {id}");
    }
    // Much cleaner than a full match when you only care about one case!

    // ─── Matching on numbers ────────────────────
    let marks = 85;
    let result = match marks {
        90..=100 => "Outstanding",
        75..=89  => "Excellent",
        60..=74  => "Good",
        40..=59  => "Pass",
        _        => "Fail",
    };
    println!("Result: {result}");
}
```

---

### Week 4–5: Constructs — Structs, Enums, Traits, Impl Blocks

| # | Topic | Priority | Est. Hours | Status |
|---|-------|----------|-----------|--------|
| 19 | **Structs** — named fields, tuple structs, unit structs | 🔴 Critical | 3h | ⬜ |
| 20 | **Impl Blocks** — methods, associated functions (`Self`, `&self`, `&mut self`) | 🔴 Critical | 3h | ⬜ |
| 21 | **Enums** — variants with data, Option, Result | 🔴 Critical | 3h | ⬜ |
| 22 | **Traits** — defining behavior, implementing traits, default implementations | 🔴 Critical | 4h | ⬜ |
| 23 | **Derive Macros** — `#[derive(Debug, Clone, PartialEq)]` | 🟡 Important | 1h | ⬜ |

```rust
// 🏗️ STRUCTS — Rust's "classes" (but better)

// Named struct (most common)
#[derive(Debug, Clone)]
struct Student {
    name: String,
    roll_no: u32,
    cgpa: f64,
    branch: Branch,
    is_active: bool,
}

#[derive(Debug, Clone, PartialEq)]
enum Branch {
    CSE,
    ECE,
    ME,
    CE,
}

// ─── impl block = methods (like class methods in Python/Java) ──
impl Student {
    // Associated function (like static method / constructor)
    // Called with Student::new(), not student.new()
    fn new(name: &str, roll_no: u32, cgpa: f64, branch: Branch) -> Self {
        Self {
            name: name.to_string(),
            roll_no,        // Field shorthand (name matches param)
            cgpa,
            branch,
            is_active: true,
        }
    }
    
    // Method — takes &self (immutable reference to instance)
    fn is_eligible_for_scholarship(&self) -> bool {
        self.cgpa >= 8.0 && self.is_active
    }
    
    // Method with &mut self (mutable reference)
    fn update_cgpa(&mut self, new_cgpa: f64) {
        if new_cgpa >= 0.0 && new_cgpa <= 10.0 {
            self.cgpa = new_cgpa;
            println!("✅ {} CGPA updated to {:.2}", self.name, self.cgpa);
        } else {
            println!("❌ Invalid CGPA: {new_cgpa}");
        }
    }
    
    // Method with Display
    fn display(&self) -> String {
        format!(
            "{} (Roll: {}, CGPA: {:.1}, Branch: {:?})",
            self.name, self.roll_no, self.cgpa, self.branch
        )
    }
}

fn main() {
    // Create using associated function
    let mut rahul = Student::new("Rahul Sharma", 101, 8.5, Branch::CSE);
    
    println!("{}", rahul.display());
    println!("Scholarship eligible: {}", rahul.is_eligible_for_scholarship());
    
    rahul.update_cgpa(9.1);
    
    // Struct update syntax (like spread operator in JS)
    let priya = Student {
        name: "Priya Verma".to_string(),
        roll_no: 102,
        ..rahul.clone()  // Copy remaining fields from rahul
    };
    println!("{:?}", priya);
}
```

```rust
// 🎭 TRAITS — Rust's "interfaces" (but more powerful)
// Traits define SHARED BEHAVIOR across types

use std::fmt;

// ─── Define a trait ─────────────────────────
trait Grader {
    fn calculate_grade(&self) -> &str;
    fn is_passing(&self) -> bool;
    
    // Default implementation (can be overridden)
    fn grade_summary(&self) -> String {
        format!("Grade: {}, Passing: {}", 
            self.calculate_grade(), self.is_passing())
    }
}

// ─── Implement trait for Student ────────────
impl Grader for Student {
    fn calculate_grade(&self) -> &str {
        match self.cgpa as u32 {
            9..=10 => "A+",
            8 => "A",
            7 => "B",
            6 => "C",
            _ => "F",
        }
    }
    
    fn is_passing(&self) -> bool {
        self.cgpa >= 4.0
    }
}

// ─── Implement Display trait (like __str__ in Python) ──
impl fmt::Display for Student {
    fn fmt(&self, f: &mut fmt::Formatter) -> fmt::Result {
        write!(f, "📚 {} | Roll: {} | CGPA: {:.1} | {:?}", 
            self.name, self.roll_no, self.cgpa, self.branch)
    }
}

// ─── Trait as parameter (polymorphism!) ─────
fn print_grade(item: &impl Grader) {
    println!("{}", item.grade_summary());
}

// Same thing using trait bound syntax:
fn print_grade_v2<T: Grader>(item: &T) {
    println!("{}", item.grade_summary());
}

// Multiple traits:
fn print_graded_display<T: Grader + fmt::Display>(item: &T) {
    println!("{item} → {}", item.calculate_grade());
}

fn main() {
    let rahul = Student::new("Rahul", 101, 8.5, Branch::CSE);
    
    println!("{rahul}");                    // Uses Display trait
    println!("{}", rahul.calculate_grade()); // Uses Grader trait
    print_graded_display(&rahul);
}
```

---

### Week 6: Data Structures in Rust

| # | Topic | Priority | Est. Hours | Status |
|---|-------|----------|-----------|--------|
| 24 | **Vec\<T\>** — dynamic arrays, push, pop, iteration | 🔴 Critical | 2h | ⬜ |
| 25 | **HashMap\<K, V\>** — key-value store, entry API | 🔴 Critical | 2h | ⬜ |
| 26 | **HashSet\<T\>** — unique values, set operations | 🟡 Important | 1h | ⬜ |
| 27 | **String** — as a data structure, UTF-8 encoding | 🔴 Critical | 1h | ⬜ |
| 28 | **LinkedList, VecDeque, BinaryHeap** — specialized collections | 🟡 Important | 2h | ⬜ |
| 29 | **Stack & Queue** — implementing with Vec/VecDeque | 🟡 Important | 1h | ⬜ |
| 30 | **Iterators** — `.iter()`, `.map()`, `.filter()`, `.collect()`, chaining | 🔴 Critical | 3h | ⬜ |

```rust
// 📦 RUST DATA STRUCTURES — Complete Overview

use std::collections::{HashMap, HashSet, VecDeque, BinaryHeap, LinkedList};

fn main() {
    // ═══════════════════════════════════════════
    // Vec<T> — Dynamic Array (MOST USED)
    // ═══════════════════════════════════════════
    let mut marks: Vec<i32> = Vec::new();
    marks.push(85);
    marks.push(90);
    marks.push(78);
    
    // vec! macro (shorthand)
    let marks = vec![85, 90, 78, 92, 88];
    
    println!("First: {}", marks[0]);        // 85
    println!("Last: {}", marks.last().unwrap()); // 88
    println!("Length: {}", marks.len());     // 5
    println!("Contains 90: {}", marks.contains(&90)); // true
    
    // Iterate
    for mark in &marks {
        print!("{mark} ");
    }
    
    // Iterator methods (FUNCTIONAL style — very idiomatic Rust!)
    let total: i32 = marks.iter().sum();
    let average = total as f64 / marks.len() as f64;
    let above_80: Vec<&i32> = marks.iter().filter(|&&m| m > 80).collect();
    let doubled: Vec<i32> = marks.iter().map(|&m| m * 2).collect();
    
    println!("\nAverage: {average:.1}");
    println!("Above 80: {:?}", above_80);
    println!("Doubled: {:?}", doubled);

    // ═══════════════════════════════════════════
    // HashMap<K, V> — Key-Value Store
    // ═══════════════════════════════════════════
    let mut students: HashMap<u32, String> = HashMap::new();
    students.insert(101, "Rahul".to_string());
    students.insert(102, "Priya".to_string());
    students.insert(103, "Amit".to_string());
    
    // Get value
    if let Some(name) = students.get(&101) {
        println!("Roll 101: {name}");
    }
    
    // Entry API (insert if not present)
    students.entry(104).or_insert("Sneha".to_string());
    
    // Word frequency counter (like Python's Counter)
    let text = "rust is fast rust is safe rust is fun";
    let mut freq: HashMap<&str, u32> = HashMap::new();
    for word in text.split_whitespace() {
        *freq.entry(word).or_insert(0) += 1;
    }
    println!("Word freq: {:?}", freq);
    // {"rust": 3, "is": 3, "fast": 1, "safe": 1, "fun": 1}
    
    // Iterate
    for (roll, name) in &students {
        println!("  {roll}: {name}");
    }

    // ═══════════════════════════════════════════
    // HashSet<T> — Unique Values
    // ═══════════════════════════════════════════
    let mut cse_students: HashSet<&str> = HashSet::new();
    cse_students.insert("Rahul");
    cse_students.insert("Priya");
    cse_students.insert("Rahul");  // Duplicate — ignored!
    println!("CSE students: {:?} (count: {})", cse_students, cse_students.len());
    
    let ece_students: HashSet<&str> = vec!["Priya", "Amit", "Karan"].into_iter().collect();
    
    // Set operations
    let common = cse_students.intersection(&ece_students);
    println!("In both: {:?}", common.collect::<Vec<_>>()); // ["Priya"]

    // ═══════════════════════════════════════════
    // VecDeque<T> — Double-ended queue
    // ═══════════════════════════════════════════
    let mut queue: VecDeque<&str> = VecDeque::new();
    queue.push_back("First");    // Enqueue
    queue.push_back("Second");
    queue.push_front("Zero");    // Push to front (deque!)
    let front = queue.pop_front(); // Dequeue
    println!("Dequeued: {:?}", front); // Some("Zero")

    // ═══════════════════════════════════════════
    // BinaryHeap<T> — Priority Queue (Max-Heap)
    // ═══════════════════════════════════════════
    let mut heap = BinaryHeap::new();
    heap.push(78);
    heap.push(92);
    heap.push(85);
    heap.push(95);
    println!("Max: {:?}", heap.peek());    // Some(95)
    println!("Pop: {:?}", heap.pop());     // Some(95) — removes max
}
```

```rust
// 🔄 ITERATORS — The Functional Heart of Rust

fn main() {
    let students = vec![
        ("Rahul", 8.5_f64),
        ("Priya", 9.2),
        ("Amit", 6.8),
        ("Sneha", 7.5),
        ("Karan", 8.9),
    ];
    
    // ─── Chaining iterator methods ──────────────
    let scholarship_list: Vec<String> = students
        .iter()
        .filter(|(_, cgpa)| *cgpa >= 8.0)           // Filter high CGPA
        .map(|(name, cgpa)| format!("{name}: {cgpa:.1}"))  // Format
        .collect();                                   // Collect into Vec
    
    println!("🏆 Scholarship List:");
    for s in &scholarship_list {
        println!("  {s}");
    }
    // 🏆 Scholarship List:
    //   Rahul: 8.5
    //   Priya: 9.2
    //   Karan: 8.9
    
    // ─── More iterator magic ────────────────────
    let total_cgpa: f64 = students.iter().map(|(_, c)| c).sum();
    let count = students.len();
    let avg_cgpa = total_cgpa / count as f64;
    println!("Average CGPA: {avg_cgpa:.2}");
    
    // find (first match)
    let topper = students.iter().max_by(|a, b| a.1.partial_cmp(&b.1).unwrap());
    println!("Topper: {:?}", topper); // Some(("Priya", 9.2))
    
    // any / all
    let all_passing = students.iter().all(|(_, cgpa)| *cgpa >= 4.0);
    let any_distinction = students.iter().any(|(_, cgpa)| *cgpa >= 9.0);
    println!("All passing: {all_passing}");        // true
    println!("Any distinction: {any_distinction}"); // true
    
    // enumerate (index + value)
    for (i, (name, cgpa)) in students.iter().enumerate() {
        println!("  #{}: {} ({:.1})", i + 1, name, cgpa);
    }
    
    // zip (combine two iterators)
    let names = vec!["Rahul", "Priya", "Amit"];
    let scores = vec![85, 92, 78];
    let combined: Vec<_> = names.iter().zip(scores.iter()).collect();
    println!("Zipped: {:?}", combined);
    // [("Rahul", 85), ("Priya", 92), ("Amit", 78)]
}
```

---

## 🟡 PHASE 2: THE OWNERSHIP SYSTEM — Rust's Core Innovation (Weeks 7–10)

> ⚠️ **This is THE most important topic in Rust.** If you understand ownership, you understand Rust. If you don't, you'll fight the compiler forever.

### Week 7–8: Ownership, Borrowing & References

| # | Topic | Priority | Est. Hours | Status |
|---|-------|----------|-----------|--------|
| 31 | **Ownership Rules** — the 3 rules, move semantics | 🔴 Critical | 4h | ⬜ |
| 32 | **Memory Safety** — no null, no dangling pointers, no data races | 🔴 Critical | 2h | ⬜ |
| 33 | **Borrowing & References** — `&` immutable, `&mut` mutable | 🔴 Critical | 4h | ⬜ |
| 34 | **Slices** — `&[T]`, `&str`, views into data | 🔴 Critical | 2h | ⬜ |
| 35 | **Stack vs Heap** — where data lives, why it matters | 🔴 Critical | 2h | ⬜ |
| 36 | **Copy vs Clone** — `Copy` trait, `.clone()`, when each is used | 🔴 Critical | 2h | ⬜ |

```
🏠 OWNERSHIP — The Apartment Analogy 🔑

  ┌──────────────────────────────────────────────────────────────────┐
  │                                                                  │
  │  THE 3 RULES OF OWNERSHIP:                                      │
  │  ═════════════════════════                                       │
  │                                                                  │
  │  1️⃣ Every value has exactly ONE owner                            │
  │     → Like every apartment has ONE lease holder                  │
  │     → Two people can't own the same apartment simultaneously    │
  │                                                                  │
  │  2️⃣ When the owner goes out of scope, the value is DROPPED      │
  │     → When you move out (scope ends), apartment is reclaimed     │
  │     → Memory is automatically freed. No garbage collector!       │
  │                                                                  │
  │  3️⃣ A value can be MOVED (transferred) to a new owner           │
  │     → Like transferring your lease to someone else               │
  │     → After transfer, you (original owner) CAN'T use it anymore │
  │                                                                  │
  │                                                                  │
  │  BORROWING = VISITING (temporary access, not ownership):         │
  │  ────────────────────────────────────────────────────             │
  │  • &T  = Immutable borrow = Guest can LOOK but NOT touch 👀     │
  │  • &mut T = Mutable borrow = Guest can REARRANGE furniture 🔧   │
  │                                                                  │
  │  Rules of borrowing:                                             │
  │  • You can have MANY immutable borrows (&T) at the same time    │
  │  • OR ONE mutable borrow (&mut T) at a time — NOT BOTH          │
  │  • Like: Many people can READ a notice board at the same time   │
  │    But only ONE person can WRITE on it (others must wait)        │
  │                                                                  │
  └──────────────────────────────────────────────────────────────────┘
```

```rust
// 🔑 OWNERSHIP IN ACTION — Watch Carefully!

fn main() {
    // ═══════════════════════════════════════════
    // Rule 1: Each value has ONE owner
    // ═══════════════════════════════════════════
    
    let s1 = String::from("hello");  // s1 OWNS the string
    let s2 = s1;                     // Ownership MOVES to s2
    
    // println!("{s1}");  // ❌ COMPILE ERROR!
    // "value used here after move"
    // s1 no longer owns the string — it was MOVED to s2
    
    println!("{s2}");  // ✅ s2 is the owner now

    // 💡 WHY does Rust do this?
    // String is on the HEAP. Two owners = two variables pointing to 
    // same memory. When both go out of scope = DOUBLE FREE bug!
    // Rust prevents this at compile time.

    // ─── Copy types (stack data) DON'T move ─────
    let x = 5;       // i32 is on the STACK (fixed size, cheap to copy)
    let y = x;        // x is COPIED, not moved (Copy trait)
    println!("x={x}, y={y}");  // ✅ Both work! Integers implement Copy.
    
    // Types that implement Copy: i32, f64, bool, char, tuples of Copy types
    // Types that DON'T (heap data): String, Vec, HashMap
    
    // ─── Clone (explicit deep copy) ─────────────
    let s1 = String::from("hello");
    let s2 = s1.clone();  // Explicit DEEP COPY (both valid now)
    println!("s1={s1}, s2={s2}");  // ✅ Both work!


    // ═══════════════════════════════════════════
    // Rule 2: Drop when out of scope
    // ═══════════════════════════════════════════
    {
        let scoped = String::from("I exist in this block");
        println!("{scoped}");
    } // ← scoped is DROPPED here. Memory freed automatically!
    // println!("{scoped}");  // ❌ Not in scope anymore


    // ═══════════════════════════════════════════
    // Rule 3: Functions take ownership (MOVE)
    // ═══════════════════════════════════════════
    let name = String::from("Rahul");
    takes_ownership(name);       // name is MOVED into the function
    // println!("{name}");       // ❌ name is gone! Function consumed it.
    
    let num = 42;
    makes_copy(num);             // num is COPIED (i32 implements Copy)
    println!("{num}");           // ✅ Still works!
}

fn takes_ownership(s: String) {
    println!("Got: {s}");
}  // ← s is DROPPED here

fn makes_copy(n: i32) {
    println!("Got: {n}");
}  // ← n goes out of scope, but it's Copy, so nothing special happens
```

```rust
// 🤝 BORROWING — Using Without Owning

fn main() {
    let name = String::from("Rahul Sharma");
    
    // ─── Immutable borrow (&) ───────────────────
    // "Let me LOOK at your data, I won't change it"
    let len = calculate_length(&name);  // Borrow, don't move!
    println!("'{name}' has {len} chars");  // ✅ name still usable!
    
    // Multiple immutable borrows = OK
    let r1 = &name;
    let r2 = &name;
    let r3 = &name;
    println!("{r1}, {r2}, {r3}");  // ✅ All good!
    
    
    // ─── Mutable borrow (&mut) ──────────────────
    // "Let me CHANGE your data temporarily"
    let mut scores = vec![85, 90, 78];
    add_score(&mut scores, 92);
    println!("Scores: {:?}", scores);  // [85, 90, 78, 92]
    
    
    // ─── THE GOLDEN RULE ────────────────────────
    let mut data = vec![1, 2, 3];
    
    // You can have EITHER:
    // a) ANY number of immutable references (&T)
    let r1 = &data;
    let r2 = &data;
    println!("{:?} {:?}", r1, r2);  // ✅

    // b) OR exactly ONE mutable reference (&mut T)
    let r3 = &mut data;
    r3.push(4);
    // println!("{:?}", r1);  // ❌ Can't use r1 while r3 (mutable) exists!
    println!("{:?}", r3);     // ✅
    
    // BUT NOT BOTH AT THE SAME TIME!
    // This prevents DATA RACES at compile time!
}

fn calculate_length(s: &String) -> usize {  // & = borrow
    s.len()
}  // s goes out of scope, but since it doesn't OWN the String, nothing happens

fn add_score(scores: &mut Vec<i32>, score: i32) {  // &mut = mutable borrow
    scores.push(score);
}
```

```
🧠 OWNERSHIP MENTAL MODEL — The Cheat Sheet

┌─────────────────────────────────────────────────────────────────┐
│                                                                 │
│  let s = String::from("hi")    s OWNS "hi" on the heap        │
│  let s2 = s                    Ownership MOVES to s2 (s dead)  │
│  let s2 = s.clone()            Deep COPY (both alive)          │
│  let r = &s                    Immutable BORROW (read-only)    │
│  let r = &mut s                Mutable BORROW (read-write)     │
│  fn f(s: String)               Function takes OWNERSHIP (move) │
│  fn f(s: &String)              Function BORROWS (read-only)    │
│  fn f(s: &mut String)          Function BORROWS mutably        │
│  fn f(s: &str)                 Accepts BOTH &String and &str ✅│
│                                                                 │
│  COMPILE-TIME GUARANTEES:                                       │
│  ✅ No null pointer dereference (no null exists!)               │
│  ✅ No use-after-free (ownership prevents this)                 │
│  ✅ No double-free (only one owner can drop)                    │
│  ✅ No data races (borrow checker prevents concurrent mutation) │
│  ✅ No dangling references (lifetimes ensure validity)          │
│                                                                 │
│  Stack vs Heap:                                                 │
│  ┌──────────────────────┬───────────────────────────────┐      │
│  │  Stack (fast, auto)  │  Heap (slower, manual layout) │      │
│  ├──────────────────────┼───────────────────────────────┤      │
│  │  i32, f64, bool, char│  String, Vec, HashMap         │      │
│  │  &str, tuples, arrays│  Box<T>, Rc<T>, Arc<T>        │      │
│  │  Fixed size, Copy    │  Dynamic size, Move            │      │
│  │  Popped automatically│  Dropped when owner out of    │      │
│  │                      │  scope                        │      │
│  └──────────────────────┴───────────────────────────────┘      │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
```

---

### Week 9–10: Error Handling & Modules

| # | Topic | Priority | Est. Hours | Status |
|---|-------|----------|-----------|--------|
| 37 | **Option\<T\>** — Rust's null replacement, `Some(T)` / `None` | 🔴 Critical | 3h | ⬜ |
| 38 | **Result\<T, E\>** — error handling, `Ok(T)` / `Err(E)` | 🔴 Critical | 3h | ⬜ |
| 39 | **The `?` Operator** — propagating errors elegantly | 🔴 Critical | 2h | ⬜ |
| 40 | **Custom Error Types** — implementing Error trait | 🟡 Important | 2h | ⬜ |
| 41 | **`panic!` vs `Result`** — when to crash vs when to handle | 🟡 Important | 1h | ⬜ |
| 42 | **Modules & Crates** — `mod`, `use`, `pub`, code organization | 🔴 Critical | 3h | ⬜ |
| 43 | **Cargo Dependencies** — Cargo.toml, crates.io, feature flags | 🔴 Critical | 2h | ⬜ |

```rust
// 🛡️ ERROR HANDLING — Rust Has NO Exceptions, NO null, NO try/catch

// Instead, Rust uses TWO enums:

// Option<T> — for values that might not exist (replaces null)
// enum Option<T> {
//     Some(T),    // Value exists
//     None,       // No value
// }

// Result<T, E> — for operations that might fail (replaces exceptions)
// enum Result<T, E> {
//     Ok(T),      // Success with value
//     Err(E),     // Error with error info
// }

fn find_student(students: &[(&str, f64)], name: &str) -> Option<f64> {
    // Returns Some(cgpa) or None
    for &(n, cgpa) in students {
        if n == name {
            return Some(cgpa);
        }
    }
    None  // Not found — NOT null, NOT -1, NOT an exception!
}

fn divide(a: f64, b: f64) -> Result<f64, String> {
    if b == 0.0 {
        Err("Cannot divide by zero!".to_string())
    } else {
        Ok(a / b)
    }
}

fn main() {
    let students = vec![("Rahul", 8.5), ("Priya", 9.2), ("Amit", 6.8)];
    
    // ─── Handling Option ────────────────────────
    // Method 1: match (explicit)
    match find_student(&students, "Rahul") {
        Some(cgpa) => println!("Rahul's CGPA: {cgpa}"),
        None => println!("Student not found!"),
    }
    
    // Method 2: if let (when you only care about Some)
    if let Some(cgpa) = find_student(&students, "Priya") {
        println!("Priya's CGPA: {cgpa}");
    }
    
    // Method 3: unwrap_or (with default value)
    let cgpa = find_student(&students, "Unknown").unwrap_or(0.0);
    println!("Unknown's CGPA: {cgpa}");  // 0.0
    
    // Method 4: unwrap() — CRASHES if None (use only in prototyping!)
    // let cgpa = find_student(&students, "Unknown").unwrap(); // 💥 PANIC!
    
    // Method 5: expect() — unwrap with custom error message
    // let cgpa = find_student(&students, "Unknown")
    //     .expect("Student must exist in database!"); // 💥 PANIC with message
    
    
    // ─── Handling Result ────────────────────────
    match divide(10.0, 3.0) {
        Ok(result) => println!("10/3 = {result:.2}"),
        Err(e) => println!("Error: {e}"),
    }
    
    match divide(10.0, 0.0) {
        Ok(result) => println!("10/0 = {result}"),
        Err(e) => println!("Error: {e}"),  // "Cannot divide by zero!"
    }
}
```

```rust
// ❓ THE ? OPERATOR — Error Propagation Made Beautiful

use std::fs;
use std::io;
use std::num::ParseIntError;

// Without ? operator (verbose)
fn read_config_verbose() -> Result<String, io::Error> {
    let content = match fs::read_to_string("config.txt") {
        Ok(c) => c,
        Err(e) => return Err(e),
    };
    Ok(content)
}

// With ? operator (elegant!) — SAME logic, much cleaner
fn read_config() -> Result<String, io::Error> {
    let content = fs::read_to_string("config.txt")?;  // If Err, return Err immediately
    Ok(content)
}

// Chaining ? operators
fn read_port_from_config() -> Result<u16, Box<dyn std::error::Error>> {
    let content = fs::read_to_string("config.txt")?;   // Might fail (IO)
    let port: u16 = content.trim().parse()?;            // Might fail (parse)
    Ok(port)
}

// 💡 The ? operator:
// 1. If Result is Ok(v), extracts v and continues
// 2. If Result is Err(e), RETURNS Err(e) immediately from the function
// 3. Works with Option too (returns None if None)
// 4. The function must return Result or Option

fn main() {
    match read_port_from_config() {
        Ok(port) => println!("Server running on port {port}"),
        Err(e) => eprintln!("Failed to read config: {e}"),
    }
}
```

```
🎯 panic! vs Result — When to Use What?

┌──────────────────────────────────────────────────────────────────┐
│                                                                  │
│  Use panic! (crash) when:                                        │
│  ─────────────────────────                                       │
│  • Bug in YOUR code (not user error)                             │
│  • Contract violation (impossible state reached)                 │
│  • In tests (assert! macros)                                     │
│  • Quick prototyping (unwrap() everywhere, fix later)            │
│  • Example: array[999] on a 10-element array                     │
│                                                                  │
│  Use Result (handle gracefully) when:                            │
│  ────────────────────────────────────                             │
│  • Expected failure (file not found, network error)              │
│  • User input could be wrong                                     │
│  • Library code (let the caller decide what to do)               │
│  • Production code (almost always!)                              │
│  • Example: parsing user input, reading files, HTTP requests     │
│                                                                  │
│  Rule of thumb:                                                  │
│  "If the error is MY fault → panic!"                             │
│  "If the error is EXPECTED → Result"                             │
│                                                                  │
└──────────────────────────────────────────────────────────────────┘
```

---

## 🔴 PHASE 3: ADVANCED RUST (Weeks 11–18)

### Week 11–12: Traits & Generics Deep Dive

| # | Topic | Priority | Est. Hours | Status |
|---|-------|----------|-----------|--------|
| 44 | **Generics** — generic functions, structs, enums | 🔴 Critical | 3h | ⬜ |
| 45 | **Trait Bounds** — `T: Display + Clone`, `where` clauses | 🔴 Critical | 3h | ⬜ |
| 46 | **Associated Types** — `type Item;` in traits | 🟡 Important | 2h | ⬜ |
| 47 | **Trait Objects** — `dyn Trait`, dynamic dispatch, `Box<dyn Trait>` | 🔴 Critical | 3h | ⬜ |
| 48 | **Common Traits** — `Display`, `Debug`, `Clone`, `Copy`, `PartialEq`, `From`/`Into` | 🔴 Critical | 3h | ⬜ |

```rust
// 🧬 GENERICS — Write Once, Work for ANY Type

// Without generics: write same function for every type 😩
fn largest_i32(list: &[i32]) -> &i32 { /* ... */ todo!() }
fn largest_f64(list: &[f64]) -> &f64 { /* ... */ todo!() }
fn largest_str(list: &[String]) -> &String { /* ... */ todo!() }

// With generics: ONE function for ALL types! 🎉
fn largest<T: PartialOrd>(list: &[T]) -> &T {
    let mut max = &list[0];
    for item in list {
        if item > max {
            max = item;
        }
    }
    max
}

// Generic struct
#[derive(Debug)]
struct Point<T> {
    x: T,
    y: T,
}

impl<T: std::fmt::Display> Point<T> {
    fn display(&self) {
        println!("({}, {})", self.x, self.y);
    }
}

// Different types for x and y
#[derive(Debug)]
struct MixedPoint<T, U> {
    x: T,
    y: U,
}

fn main() {
    let numbers = vec![34, 50, 25, 100, 65];
    println!("Largest: {}", largest(&numbers));  // 100
    
    let chars = vec!['y', 'm', 'a', 'q'];
    println!("Largest: {}", largest(&chars));    // 'y'
    
    let int_point = Point { x: 5, y: 10 };
    let float_point = Point { x: 1.5, y: 4.2 };
    int_point.display();    // (5, 10)
    float_point.display();  // (1.5, 4.2)
    
    let mixed = MixedPoint { x: 5, y: 4.0 };
    println!("{:?}", mixed);  // MixedPoint { x: 5, y: 4.0 }
}

// 💡 ZERO-COST ABSTRACTION:
// The compiler generates specialized code for each type at compile time.
// largest::<i32>(), largest::<char>() — no runtime overhead!
// This is called MONOMORPHIZATION.
```

```rust
// 🎭 TRAIT OBJECTS — Dynamic Dispatch (Runtime Polymorphism)

trait Shape {
    fn area(&self) -> f64;
    fn name(&self) -> &str;
}

struct Circle { radius: f64 }
struct Rectangle { width: f64, height: f64 }
struct Triangle { base: f64, height: f64 }

impl Shape for Circle {
    fn area(&self) -> f64 { std::f64::consts::PI * self.radius * self.radius }
    fn name(&self) -> &str { "Circle" }
}

impl Shape for Rectangle {
    fn area(&self) -> f64 { self.width * self.height }
    fn name(&self) -> &str { "Rectangle" }
}

impl Shape for Triangle {
    fn area(&self) -> f64 { 0.5 * self.base * self.height }
    fn name(&self) -> &str { "Triangle" }
}

// Using trait objects: Box<dyn Shape> — can hold ANY shape!
fn print_areas(shapes: &[Box<dyn Shape>]) {
    for shape in shapes {
        println!("  {} → Area: {:.2}", shape.name(), shape.area());
    }
}

fn main() {
    // A Vec holding DIFFERENT types — unified through a trait!
    let shapes: Vec<Box<dyn Shape>> = vec![
        Box::new(Circle { radius: 5.0 }),
        Box::new(Rectangle { width: 4.0, height: 6.0 }),
        Box::new(Triangle { base: 3.0, height: 8.0 }),
    ];
    
    println!("📐 Shapes:");
    print_areas(&shapes);
    // 📐 Shapes:
    //   Circle → Area: 78.54
    //   Rectangle → Area: 24.00
    //   Triangle → Area: 12.00
}

// ┌──────────────────────────────────────────────────────────┐
// │  Static Dispatch (generics):  fn f<T: Shape>(s: &T)     │
// │  → Compiler generates specialized code per type          │
// │  → Zero overhead, but larger binary                      │
// │  → Can't mix types in a collection                       │
// │                                                          │
// │  Dynamic Dispatch (trait objects): fn f(s: &dyn Shape)   │
// │  → Runtime vtable lookup (tiny overhead)                 │
// │  → CAN mix types in a collection (Box<dyn Shape>)        │
// │  → Smaller binary                                        │
// └──────────────────────────────────────────────────────────┘
```

---

### Week 13–14: Lifetimes & Borrow Checker

| # | Topic | Priority | Est. Hours | Status |
|---|-------|----------|-----------|--------|
| 49 | **Explicit Lifetime Annotations** — `'a`, `'b`, why they exist | 🔴 Critical | 4h | ⬜ |
| 50 | **Lifetime Elision Rules** — when the compiler infers lifetimes | 🔴 Critical | 2h | ⬜ |
| 51 | **Lifetimes in Structs** — holding references in structs | 🟡 Important | 2h | ⬜ |
| 52 | **`'static` Lifetime** — data that lives for the entire program | 🟡 Important | 1h | ⬜ |

```rust
// ⏳ LIFETIMES — Ensuring References Are Always Valid

// 🎓 Analogy: Library Book Return System
// When you borrow a book (reference), the library needs to ensure:
// 1. The book EXISTS while you have it
// 2. Your borrowing period doesn't exceed the book's availability
// Lifetimes = the compiler tracking these borrowing periods

// ─── The Problem ────────────────────────────
// fn longest(x: &str, y: &str) -> &str {  // ❌ Won't compile!
//     if x.len() > y.len() { x } else { y }
// }
// Compiler: "I don't know if the returned reference comes from 
//            x or y, so I don't know how long it's valid!"

// ─── The Solution: Lifetime Annotations ─────
fn longest<'a>(x: &'a str, y: &'a str) -> &'a str {
    // 'a means: "the returned reference lives at least as long as 
    //            the SHORTER of x and y's lifetimes"
    if x.len() > y.len() { x } else { y }
}

// ─── Lifetimes in Structs ───────────────────
// "This struct holds a reference. The reference must outlive the struct."
struct StudentRef<'a> {
    name: &'a str,   // This reference must be valid as long as StudentRef exists
    branch: &'a str,
}

impl<'a> StudentRef<'a> {
    fn display(&self) -> String {
        format!("{} ({})​", self.name, self.branch)
    }
}

fn main() {
    let result;
    let string1 = String::from("Rust");
    {
        let string2 = String::from("Go");
        result = longest(string1.as_str(), string2.as_str());
        println!("Longest: {result}");  // ✅ Both strings alive here
    }
    // println!("{result}");  // ❌ string2 is dropped, result might point to it!
    
    
    let student = StudentRef { name: "Rahul", branch: "CSE" };
    println!("{}", student.display());
}

// 💡 LIFETIME ELISION RULES (when you DON'T need to write 'a):
// The compiler auto-infers lifetimes in 3 cases:
//
// Rule 1: Each input reference gets its own lifetime
//   fn f(x: &str, y: &str)  →  fn f<'a, 'b>(x: &'a str, y: &'b str)
//
// Rule 2: If there's exactly one input lifetime, it's assigned to all outputs
//   fn f(x: &str) -> &str  →  fn f<'a>(x: &'a str) -> &'a str
//
// Rule 3: If one input is &self or &mut self, that lifetime is used for output
//   fn f(&self, x: &str) -> &str  →  self's lifetime used
//
// If these 3 rules don't resolve all lifetimes → you must annotate manually
```

---

### Week 15–16: Concurrency & Async

| # | Topic | Priority | Est. Hours | Status |
|---|-------|----------|-----------|--------|
| 53 | **Threads** — `std::thread::spawn`, `JoinHandle` | 🔴 Critical | 3h | ⬜ |
| 54 | **Channels & Message Passing** — `mpsc::channel`, `send`, `recv` | 🔴 Critical | 3h | ⬜ |
| 55 | **Shared State** — `Mutex<T>`, `Arc<T>`, `RwLock<T>` | 🔴 Critical | 3h | ⬜ |
| 56 | **Atomic Operations** — `AtomicBool`, `AtomicUsize` | 🟡 Important | 2h | ⬜ |
| 57 | **Async/Await** — `async fn`, `.await`, `Future` trait | 🔴 Critical | 4h | ⬜ |
| 58 | **Tokio Runtime** — async runtime, tasks, I/O | 🔴 Critical | 4h | ⬜ |

```rust
// ⚡ CONCURRENCY — "Fearless Concurrency" (Rust's Promise)

// The ownership system PREVENTS data races at compile time!
// In C/C++: data race = undefined behavior (crashes, corruption)
// In Rust:  data race = compile error ✅

use std::thread;
use std::sync::{Arc, Mutex, mpsc};
use std::time::Duration;

fn main() {
    // ─── Spawning Threads ───────────────────────
    let handle = thread::spawn(|| {
        for i in 1..=5 {
            println!("Thread: count {i}");
            thread::sleep(Duration::from_millis(100));
        }
    });
    
    for i in 1..=3 {
        println!("Main: count {i}");
        thread::sleep(Duration::from_millis(150));
    }
    
    handle.join().unwrap(); // Wait for thread to finish
    
    
    // ─── Move Closure (transfer ownership to thread) ──
    let data = vec![1, 2, 3];
    let handle = thread::spawn(move || {
        // `move` transfers ownership of `data` INTO the thread
        println!("Thread has data: {:?}", data);
    });
    // println!("{:?}", data);  // ❌ data was moved into thread!
    handle.join().unwrap();
    
    
    // ─── Channels (Message Passing) ─────────────
    // "Do not communicate by sharing memory; share memory by communicating."
    let (tx, rx) = mpsc::channel();
    
    // Multiple producers
    for i in 0..5 {
        let tx_clone = tx.clone();
        thread::spawn(move || {
            let msg = format!("Message {} from thread", i);
            tx_clone.send(msg).unwrap();
        });
    }
    drop(tx); // Drop original sender (clones still alive)
    
    // Receiver
    for received in rx {
        println!("📨 Got: {received}");
    }
    
    
    // ─── Shared State (Mutex + Arc) ─────────────
    // Arc = Atomic Reference Counted (thread-safe Rc)
    // Mutex = Mutual Exclusion (one thread at a time)
    let counter = Arc::new(Mutex::new(0));
    let mut handles = vec![];
    
    for _ in 0..10 {
        let counter = Arc::clone(&counter);
        let handle = thread::spawn(move || {
            let mut num = counter.lock().unwrap();
            *num += 1;
        });
        handles.push(handle);
    }
    
    for handle in handles {
        handle.join().unwrap();
    }
    
    println!("Counter: {}", *counter.lock().unwrap()); // 10 ✅
    // No data race! Mutex ensures only one thread modifies at a time.
    // Arc ensures the Mutex isn't dropped while threads still use it.
}
```

```rust
// 🔮 ASYNC/AWAIT — Non-Blocking I/O with Tokio

// Cargo.toml:
// [dependencies]
// tokio = { version = "1", features = ["full"] }
// reqwest = { version = "0.11", features = ["json"] }

use tokio;

async fn fetch_data(url: &str) -> Result<String, reqwest::Error> {
    let response = reqwest::get(url).await?;
    let body = response.text().await?;
    Ok(body)
}

async fn process_student(name: &str) -> String {
    // Simulate async work (DB query, API call, etc.)
    tokio::time::sleep(tokio::time::Duration::from_secs(1)).await;
    format!("{name}: processed ✅")
}

#[tokio::main]  // This sets up the async runtime
async fn main() {
    // Sequential (slow)
    // let r1 = process_student("Rahul").await;
    // let r2 = process_student("Priya").await;
    // Total: 2 seconds
    
    // Concurrent (fast!) — both run simultaneously
    let (r1, r2) = tokio::join!(
        process_student("Rahul"),
        process_student("Priya")
    );
    // Total: 1 second! Both ran concurrently.
    
    println!("{r1}");
    println!("{r2}");
    
    // Spawning tasks (like thread::spawn but for async)
    let task = tokio::spawn(async {
        process_student("Amit").await
    });
    let result = task.await.unwrap();
    println!("{result}");
}
```

---

### Week 17–18: Macros & Testing

| # | Topic | Priority | Est. Hours | Status |
|---|-------|----------|-----------|--------|
| 59 | **Declarative Macros** — `macro_rules!`, pattern matching on syntax | 🟡 Important | 3h | ⬜ |
| 60 | **Procedural Macros** — `#[derive]`, attribute macros, function-like macros | 🟡 Important | 3h | ⬜ |
| 61 | **Unit Testing** — `#[test]`, `assert!`, `assert_eq!`, `#[should_panic]` | 🔴 Critical | 3h | ⬜ |
| 62 | **Integration Testing** — `tests/` directory, testing public API | 🔴 Critical | 2h | ⬜ |
| 63 | **Documentation Tests** — `///` doc comments with testable code | 🟡 Important | 1h | ⬜ |

```rust
// 📝 MACROS — Code That Writes Code

// Declarative macro (most common, using macro_rules!)
macro_rules! vec_of_strings {
    // Pattern: zero or more expressions separated by commas
    ( $( $x:expr ),* ) => {
        {
            let mut v = Vec::new();
            $(
                v.push(String::from($x));
            )*
            v
        }
    };
}

// More useful: a hashmap! macro (Rust doesn't have one built-in)
macro_rules! hashmap {
    ( $( $key:expr => $value:expr ),* $(,)? ) => {
        {
            let mut map = std::collections::HashMap::new();
            $(
                map.insert($key, $value);
            )*
            map
        }
    };
}

fn main() {
    let names = vec_of_strings!["Rahul", "Priya", "Amit"];
    println!("{:?}", names);
    
    let scores = hashmap! {
        "Rahul" => 85,
        "Priya" => 92,
        "Amit" => 78,
    };
    println!("{:?}", scores);
}
```

```rust
// 🧪 TESTING — Built Into the Language!

// In src/lib.rs or any module:

pub fn add(a: i32, b: i32) -> i32 { a + b }

pub fn divide(a: f64, b: f64) -> Result<f64, String> {
    if b == 0.0 {
        Err("Division by zero".to_string())
    } else {
        Ok(a / b)
    }
}

pub fn calculate_grade(cgpa: f64) -> &'static str {
    match cgpa as u32 {
        9..=10 => "A+",
        8 => "A",
        7 => "B",
        _ => "F",
    }
}

// ─── Unit Tests (in same file!) ─────────────
#[cfg(test)]  // Only compiled when running tests
mod tests {
    use super::*;  // Import from parent module
    
    #[test]
    fn test_add() {
        assert_eq!(add(2, 3), 5);
    }
    
    #[test]
    fn test_add_negative() {
        assert_eq!(add(-1, 1), 0);
    }
    
    #[test]
    fn test_divide_success() {
        let result = divide(10.0, 3.0);
        assert!(result.is_ok());
        assert!((result.unwrap() - 3.333).abs() < 0.01);
    }
    
    #[test]
    fn test_divide_by_zero() {
        let result = divide(10.0, 0.0);
        assert!(result.is_err());
        assert_eq!(result.unwrap_err(), "Division by zero");
    }
    
    #[test]
    #[should_panic(expected = "index out of bounds")]
    fn test_out_of_bounds() {
        let v = vec![1, 2, 3];
        let _ = v[99]; // Should panic!
    }
    
    #[test]
    fn test_grade() {
        assert_eq!(calculate_grade(9.5), "A+");
        assert_eq!(calculate_grade(8.0), "A");
        assert_eq!(calculate_grade(5.0), "F");
    }
}

// Run: cargo test
// Run specific: cargo test test_add
// Run with output: cargo test -- --nocapture
```

---

## 🏆 PHASE 4: ECOSYSTEM & SPECIALIZATION (Weeks 19–28)

### Week 19–22: Web Development & Key Libraries

| # | Topic | Priority | Est. Hours | Status |
|---|-------|----------|-----------|--------|
| 64 | **Serde** — serialization/deserialization (JSON, TOML) | 🔴 Critical | 3h | ⬜ |
| 65 | **Axum** — modern async web framework (recommended 🏆) | 🔴 Critical | 6h | ⬜ |
| 66 | **Actix Web** — high-performance web framework | 🟡 Important | 4h | ⬜ |
| 67 | **Reqwest** — HTTP client | 🔴 Critical | 2h | ⬜ |
| 68 | **SQLx** — async SQL database library | 🔴 Critical | 4h | ⬜ |
| 69 | **Tokio** — async runtime deep dive | 🔴 Critical | 4h | ⬜ |
| 70 | **Clap** — CLI argument parsing | 🟡 Important | 2h | ⬜ |

```
🌐 RUST WEB FRAMEWORKS — Which One to Learn?

┌────────────────┬───────────────┬─────────────┬──────────┬──────────────┐
│  Framework     │  Style        │  Ecosystem  │  Perf    │  Best For    │
├────────────────┼───────────────┼─────────────┼──────────┼──────────────┤
│  Axum 🏆       │  Modular,     │  Tower eco- │  ⭐⭐⭐⭐⭐│  APIs,       │
│  (recommended) │  composable   │  system     │          │  microservices│
│                │  Uses Tokio   │  Growing 📈 │          │              │
├────────────────┼───────────────┼─────────────┼──────────┼──────────────┤
│  Actix Web     │  Actor model  │  Mature     │  ⭐⭐⭐⭐⭐│  High-perf   │
│                │  Full-featured│             │          │  APIs        │
├────────────────┼───────────────┼─────────────┼──────────┼──────────────┤
│  Rocket        │  Rails-like   │  Good       │  ⭐⭐⭐⭐ │  Full-stack  │
│                │  ergonomic    │             │          │  web apps    │
├────────────────┼───────────────┼─────────────┼──────────┼──────────────┤
│  Loco          │  Rails-like   │  New        │  ⭐⭐⭐⭐ │  Quick       │
│                │  batteries    │  Growing    │          │  prototypes  │
│                │  included     │             │          │              │
├────────────────┼───────────────┼─────────────┼──────────┼──────────────┤
│  Leptos        │  Full-stack   │  Growing    │  ⭐⭐⭐⭐ │  SPAs with   │
│                │  React-like   │             │          │  WASM        │
└────────────────┴───────────────┴─────────────┴──────────┴──────────────┘

💡 Start with Axum — it's the most "Rustic", best ecosystem, backed by Tokio team.
```

```rust
// 🚀 AXUM — Build a REST API

// Cargo.toml:
// [dependencies]
// axum = "0.7"
// tokio = { version = "1", features = ["full"] }
// serde = { version = "1", features = ["derive"] }
// serde_json = "1"

use axum::{
    extract::{Path, State, Json},
    routing::{get, post, delete},
    http::StatusCode,
    Router,
};
use serde::{Deserialize, Serialize};
use std::sync::{Arc, Mutex};
use std::collections::HashMap;

// ─── Data Models ────────────────────────────
#[derive(Debug, Serialize, Deserialize, Clone)]
struct Student {
    id: u32,
    name: String,
    cgpa: f64,
    branch: String,
}

#[derive(Debug, Deserialize)]
struct CreateStudent {
    name: String,
    cgpa: f64,
    branch: String,
}

// ─── App State ──────────────────────────────
type AppState = Arc<Mutex<HashMap<u32, Student>>>;

// ─── Handlers ───────────────────────────────
async fn list_students(
    State(db): State<AppState>,
) -> Json<Vec<Student>> {
    let db = db.lock().unwrap();
    Json(db.values().cloned().collect())
}

async fn get_student(
    State(db): State<AppState>,
    Path(id): Path<u32>,
) -> Result<Json<Student>, StatusCode> {
    let db = db.lock().unwrap();
    db.get(&id)
        .cloned()
        .map(Json)
        .ok_or(StatusCode::NOT_FOUND)
}

async fn create_student(
    State(db): State<AppState>,
    Json(input): Json<CreateStudent>,
) -> (StatusCode, Json<Student>) {
    let mut db = db.lock().unwrap();
    let id = (db.len() as u32) + 1;
    let student = Student {
        id,
        name: input.name,
        cgpa: input.cgpa,
        branch: input.branch,
    };
    db.insert(id, student.clone());
    (StatusCode::CREATED, Json(student))
}

async fn delete_student(
    State(db): State<AppState>,
    Path(id): Path<u32>,
) -> StatusCode {
    let mut db = db.lock().unwrap();
    if db.remove(&id).is_some() {
        StatusCode::NO_CONTENT
    } else {
        StatusCode::NOT_FOUND
    }
}

// ─── Main ───────────────────────────────────
#[tokio::main]
async fn main() {
    let db: AppState = Arc::new(Mutex::new(HashMap::new()));
    
    let app = Router::new()
        .route("/students", get(list_students).post(create_student))
        .route("/students/{id}", get(get_student).delete(delete_student))
        .with_state(db);
    
    println!("🦀 Server running on http://localhost:3000");
    let listener = tokio::net::TcpListener::bind("0.0.0.0:3000").await.unwrap();
    axum::serve(listener, app).await.unwrap();
}

// Test:
// curl -X POST http://localhost:3000/students \
//   -H "Content-Type: application/json" \
//   -d '{"name":"Rahul","cgpa":8.5,"branch":"CSE"}'
//
// curl http://localhost:3000/students
```

---

### Week 23–28: Specialization Tracks

| Track | Topics | Est. Hours | Status |
|-------|--------|-----------|--------|
| 🌐 **WebAssembly** | `wasm-bindgen`, `wasm-pack`, `wasmer` | 8h | ⬜ |
| 🎮 **Game Dev** | `bevy`, `ggez`, `macroquad`, `wgpu-rs` | 12h | ⬜ |
| 🖥️ **GUI** | `tauri` (Electron replacement!), `gtk-rs` | 8h | ⬜ |
| ⚙️ **Embedded/Systems** | `embedded-hal`, `rppal`, `no_std` | 10h | ⬜ |
| 🔧 **CLI Tools** | `clap`, `termion`, building real CLI apps | 6h | ⬜ |
| 📊 **Performance** | `Criterion.rs`, profiling, benchmarking | 4h | ⬜ |
| 🔒 **Crypto** | `ring`, `sodiumoxide`, `rust-crypto` | 6h | ⬜ |

```
🎯 WHICH SPECIALIZATION TO PICK?

┌─────────────────────────┬──────────────────────────────────────┐
│  Your Interest          │  Rust Track                          │
├─────────────────────────┼──────────────────────────────────────┤
│  Web Backend            │  Axum + SQLx + Tokio                 │
│  Full-Stack Web         │  Leptos (Rust WASM frontend!)        │
│  Desktop Apps           │  Tauri (replaces Electron, 10x smaller)│
│  Game Development       │  Bevy (ECS-based game engine)        │
│  Blockchain/Web3        │  Solana SDK (Anchor framework)       │
│  CLI Tools              │  Clap + Termion                      │
│  Systems/OS Dev         │  no_std, embedded-hal                │
│  DevOps/Infra           │  CLI tools, networking (hyper, quinn)│
│  Performance Tools      │  Criterion.rs, profiling             │
│  WebAssembly            │  wasm-bindgen, wasm-pack             │
└─────────────────────────┴──────────────────────────────────────┘

💰 Highest paying Rust jobs in 2025:
   1. Blockchain (Solana) — ₹25-80 LPA
   2. Systems/Infrastructure — ₹20-60 LPA
   3. WebAssembly — ₹18-50 LPA
   4. Game Engine Dev — ₹15-45 LPA
   5. Backend API — ₹15-40 LPA
```

---

## 📊 COMPLETE TIMELINE OVERVIEW

```
WEEK  1     ████ Introduction, Setup, Cargo, Hello World
WEEK  2     ████ Variables, Data Types, Strings, Constants
WEEK  3     ████ Control Flow, Functions, Pattern Matching
WEEK  4-5   ████ Structs, Enums, Traits, Impl Blocks
WEEK  6     ████ Vec, HashMap, Iterators, Collections
             ──── 🎯 MILESTONE: Write basic Rust programs ────

WEEK  7-8   ████ OWNERSHIP, Borrowing, References, Slices
WEEK  9-10  ████ Error Handling (Option/Result/?), Modules, Cargo
             ──── 🎯 MILESTONE: Understand & work with ownership ────

WEEK 11-12  ████ Generics, Trait Bounds, Trait Objects
WEEK 13-14  ████ Lifetimes, Borrow Checker Deep Dive
WEEK 15-16  ████ Concurrency: Threads, Channels, Mutex, Arc, Async
WEEK 17-18  ████ Macros, Testing (unit, integration, doc tests)
             ──── 🎯 MILESTONE: Write advanced, idiomatic Rust ────

WEEK 19-20  ████ Serde, Axum/Actix, REST API project
WEEK 21-22  ████ SQLx/Diesel, Tokio deep dive, Reqwest
WEEK 23-24  ████ Specialization Track — Part 1
WEEK 25-26  ████ Specialization Track — Part 2
WEEK 27-28  ████ Portfolio Project, Performance, Deployment
             ──── 🏆 MILESTONE: Production-ready Rust developer ────
```

---

## 🏋️ PROJECTS TO BUILD (Phase-wise)

| Phase | Project | Skills Covered | Resume Value |
|-------|---------|---------------|-------------|
| 🟢 Week 6 | **CLI Student Manager** | Structs, enums, Vec, HashMap, pattern matching | ⭐⭐ |
| 🟡 Week 10 | **File-based TODO App** | Ownership, error handling, file I/O, serde | ⭐⭐⭐ |
| 🔴 Week 14 | **Multi-threaded Web Scraper** | Concurrency, reqwest, async, error handling | ⭐⭐⭐⭐ |
| 🔴 Week 18 | **REST API with Axum** | Web framework, serde, SQLx, testing | ⭐⭐⭐⭐ |
| 🏆 Week 24 | **CLI Tool / Tauri App / Game** | Full ecosystem, publish to crates.io | ⭐⭐⭐⭐⭐ |

---

## 📚 BEST RESOURCES (Curated)

| Category | Resource | Type | Best For |
|----------|----------|------|----------|
| 📖 Book | **The Rust Programming Language** ("The Book") | Free online | THE starting point (official) |
| 📖 Book | **Rust by Example** | Free online | Learn through code examples |
| 📖 Book | **Programming Rust** (O'Reilly) | Book | Deep technical reference |
| 📖 Book | **Rust in Action** (Tim McNamara) | Book | Systems programming focus |
| 🎥 YouTube | **Let's Get Rusty** | Video | Best YouTube channel for Rust |
| 🎥 YouTube | **No Boilerplate** | Video | Why Rust is amazing (motivational) |
| 🎥 YouTube | **Jon Gjengset** | Video | Advanced Rust (deep dives) |
| 🎥 YouTube | **Fireship** — Rust in 100 Seconds | Video | Quick overview |
| 🌐 Interactive | **Rustlings** (github.com/rust-lang/rustlings) | Exercises | Learn by fixing compiler errors |
| 🌐 Interactive | **Exercism — Rust Track** | Platform | Mentored exercises |
| 🌐 Practice | **Advent of Code** (in Rust) | Platform | Problem solving |
| 🌐 Website | **roadmap.sh/rust** | Roadmap | Visual learning path |
| 🌐 Docs | **doc.rust-lang.org/std** | Official | Standard library reference |
| 🌐 Ecosystem | **lib.rs** | Crate search | Find the best crates |

---

## 💼 Interview Angle — Rust Questions Companies Ask

```
┌────────────────────────────────────────────────────────────────────┐
│              TOP RUST INTERVIEW QUESTIONS                          │
├────────────────────────────────────────────────────────────────────┤
│                                                                    │
│  FUNDAMENTALS:                                                     │
│  1. Explain ownership, borrowing, and lifetimes.                   │
│  2. What is the difference between &str and String?                │
│  3. How does Rust prevent null pointer exceptions?                 │
│  4. Explain the difference between Copy and Clone.                 │
│  5. What is the borrow checker and why does it exist?              │
│                                                                    │
│  INTERMEDIATE:                                                     │
│  6. Explain trait objects vs generics (static vs dynamic dispatch). │
│  7. How does error handling work in Rust? (Option, Result, ?)      │
│  8. What are lifetimes? When do you need explicit annotations?     │
│  9. Explain Rc<T> vs Arc<T> vs Box<T>.                            │
│  10. How does Rust achieve "fearless concurrency"?                 │
│                                                                    │
│  ADVANCED:                                                         │
│  11. Explain the Pin and Unpin traits (for async).                 │
│  12. What is unsafe Rust? When would you use it?                   │
│  13. How does the Tokio runtime work?                              │
│  14. Explain zero-cost abstractions with an example.               │
│  15. Design a thread-safe cache in Rust.                           │
│                                                                    │
│  Companies hiring Rust developers (India):                         │
│  Solana, 1Password, Cloudflare, Discord, Amazon (select teams),   │
│  Microsoft (select teams), Atlassian, Hasura, DeepSource           │
└────────────────────────────────────────────────────────────────────┘
```

---

## 🧠 RUST MENTAL MODEL — The Complete Picture

```
┌─────────────────────────────────────────────────────────────────┐
│                                                                 │
│   EVERY Rust concept connects to SAFETY:                        │
│                                                                 │
│   Ownership      → No double-free, no memory leaks             │
│   Borrowing      → No data races, no dangling pointers          │
│   Lifetimes      → No use-after-free                            │
│   Option<T>      → No null pointer dereference                  │
│   Result<T,E>    → No uncaught exceptions                       │
│   Type System    → No type confusion at runtime                 │
│   Pattern Match  → No unhandled cases                           │
│   Send/Sync      → No unsafe thread sharing                     │
│                                                                 │
│   The cost? Slower compilation. Steeper learning curve.         │
│   The payoff? If it compiles, it (almost certainly) works. 🦀   │
│                                                                 │
│   "Fighting the borrow checker" is Phase 1.                     │
│   "Thanking the borrow checker" is Phase 2.                     │
│   "Thinking in ownership naturally" is Phase 3. That's mastery. │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
```
