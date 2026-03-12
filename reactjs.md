

# 🗺️ ROADMAP: React.js — Complete Mastery Guide

> From `"Hello World"` component to Production-Ready Apps

---

## 📊 Roadmap Overview

```
Total Estimated Time:  12–16 Weeks (2 hrs/day)
Difficulty Curve:      █████████░ (Moderate start, steep middle, rewarding end)
Relevance:             Placements ⭐⭐⭐⭐⭐ | Jobs ⭐⭐⭐⭐⭐ | Freelancing ⭐⭐⭐⭐⭐ | GATE ❌
```

```
🔴 = Critical (MUST know — asked in every React interview)
🟡 = Important (frequently expected in mid-level roles)
🟢 = Good to Know (gives you a competitive edge)
```

---

## ⚠️ PREREQUISITES — Before You Touch React

```
┌─────────────────────────────────────────────────────────────────────┐
│  ❗ DO NOT start React without these JavaScript fundamentals:      │
│                                                                     │
│  🔴 Variables (let, const, var)                                     │
│  🔴 Arrow Functions         │  🔴 Template Literals                │
│  🔴 Array Methods (map, filter, reduce, forEach, find, some)       │
│  🔴 Destructuring (Objects & Arrays)                                │
│  🔴 Spread/Rest Operators (...)                                     │
│  🔴 Promises & async/await                                          │
│  🔴 Modules (import/export)                                         │
│  🔴 Ternary Operator                                                │
│  🟡 Optional Chaining (?.)                                          │
│  🟡 Short-circuit Evaluation (&&, ||, ??)                           │
│  🟡 Callbacks & Higher-Order Functions                              │
│  🟡 JSON (parse, stringify)                                         │
│  🟡 Fetch API / HTTP basics                                         │
│  🟡 DOM basics (what it is — React replaces manual DOM work)       │
│                                                                     │
│  ⏱️ If you're weak here: Spend 1–2 weeks on JS first              │
│  📺 Resource: "JavaScript for React" — Fireship (YouTube, 12 min) │
│  📺 Full JS: CodeWithHarry JS Playlist (Hindi)                     │
└─────────────────────────────────────────────────────────────────────┘
```

### Quick Self-Test — Can You Read This?

```javascript
const students = [
  { name: "Rahul", cgpa: 8.5, branch: "CSE" },
  { name: "Priya", cgpa: 9.1, branch: "ECE" },
  { name: "Amit",  cgpa: 7.2, branch: "CSE" },
  { name: "Sneha", cgpa: 8.8, branch: "CSE" },
];

const topCSE = students
  .filter(s => s.branch === "CSE" && s.cgpa > 8)
  .map(({ name, cgpa }) => `${name} (${cgpa})`)
  .join(", ");

console.log(topCSE); // What's the output?
```

```
Answer: "Rahul (8.5), Sneha (8.8)"

If you understood this instantly → You're ready for React ✅
If this confused you → Spend time on JS fundamentals first ⚠️
```

---

## 🧱 PHASE 1: FOUNDATIONS — Setup & Core Concepts (Week 1–2)
### *"Understand the 'why' of React before the 'how'"*

```
⏱️ Estimated: 10–14 hours
Prerequisites: JavaScript fundamentals
Goal: Build your first React component, understand JSX, props, state
```

---

### 1.1 What is React & Why It Exists 🔴

```
┌───────────────────────────────────────────────────────────────┐
│                    WHY REACT EXISTS                            │
├───────────────────────────────────────────────────────────────┤
│                                                               │
│  PROBLEM (Vanilla JS):                                        │
│  → Manually updating DOM is slow and error-prone              │
│  → Code becomes spaghetti as app grows                        │
│  → No reusable UI pieces                                      │
│  → State management is a nightmare                            │
│                                                               │
│  SOLUTION (React):                                            │
│  → Virtual DOM (fast, efficient updates)                      │
│  → Component-based (reusable UI blocks)                       │
│  → Declarative ("what" not "how")                             │
│  → Unidirectional data flow (predictable)                     │
│  → Massive ecosystem + community                              │
│                                                               │
│  Created by: Facebook (Meta), 2013                            │
│  Used by: Facebook, Instagram, Netflix, Airbnb, Flipkart,    │
│           Swiggy, Zomato, Razorpay — basically everyone       │
│                                                               │
└───────────────────────────────────────────────────────────────┘
```

### 🧒 ELI5 — What is React?

> Imagine you're building a house with **LEGO blocks**.
> Each block = a **Component** (navbar, card, button, footer).
> You can reuse the same block design everywhere.
> If one block changes, you don't rebuild the entire house — just swap that one block.
> That's React — **UI built from reusable, independent pieces**.

---

### 1.2 Project Setup with Vite 🔴

```bash
# ❌ DON'T use Create React App (CRA) — it's deprecated/slow
# ✅ Use Vite — modern, blazing fast

# Step 1: Create project
npm create vite@latest my-react-app -- --template react

# Step 2: Navigate into project
cd my-react-app

# Step 3: Install dependencies
npm install

# Step 4: Start development server
npm run dev

# 🌐 Open http://localhost:5173 in browser
```

### Project Structure

```
my-react-app/
├── node_modules/        # Dependencies (don't touch)
├── public/              # Static files (favicon, images)
├── src/                 # 👈 YOUR CODE LIVES HERE
│   ├── App.jsx          # Root component
│   ├── App.css          # Root styles
│   ├── main.jsx         # Entry point (mounts React to DOM)
│   ├── index.css        # Global styles
│   └── assets/          # Images, fonts etc.
├── index.html           # Single HTML page (SPA!)
├── package.json         # Project config & dependencies
├── vite.config.js       # Vite configuration
└── .gitignore
```

---

### 1.3 JSX — JavaScript + HTML 🔴

```jsx
// JSX = JavaScript XML
// Looks like HTML, but it's actually JavaScript

// ✅ JSX (what you write)
const greeting = <h1>Hello, React!</h1>;

// ✅ What React compiles it to (behind the scenes)
const greeting = React.createElement('h1', null, 'Hello, React!');
```

### JSX Rules

```jsx
function App() {
  const name = "Rahul";
  const isLoggedIn = true;
  const skills = ["React", "Node", "MongoDB"];

  return (
    // Rule 1: Must return ONE parent element (use <> fragment if needed)
    <>
      {/* Rule 2: Use className, not class */}
      <div className="container">
        
        {/* Rule 3: JavaScript expressions inside {} */}
        <h1>Hello, {name}!</h1>
        
        {/* Rule 4: All tags must be closed */}
        <img src="photo.jpg" alt="Profile" />  {/* self-closing */}
        <br />
        
        {/* Rule 5: style takes an OBJECT, not a string */}
        <p style={{ color: "blue", fontSize: "18px" }}>
          Welcome to React
        </p>
        
        {/* Rule 6: Conditional rendering */}
        {isLoggedIn ? <p>Welcome back!</p> : <p>Please log in</p>}
        
        {/* Rule 7: Rendering lists with map */}
        <ul>
          {skills.map((skill, index) => (
            <li key={index}>{skill}</li>
          ))}
        </ul>
      </div>
    </>
  );
}

export default App;
```

### ❌ Common JSX Mistakes

```jsx
// ❌ WRONG: class (HTML) → className (JSX)
<div class="box">           // Error!
<div className="box">       // ✅ Correct

// ❌ WRONG: for (HTML) → htmlFor (JSX)  
<label for="email">         // Error!
<label htmlFor="email">     // ✅ Correct

// ❌ WRONG: Inline style as string
<p style="color: red">      // Error!
<p style={{ color: "red" }}> // ✅ Correct (double curly braces)

// ❌ WRONG: Multiple root elements
return (
  <h1>Title</h1>
  <p>Paragraph</p>           // Error! Two roots
);

// ✅ Correct: Wrap in fragment
return (
  <>
    <h1>Title</h1>
    <p>Paragraph</p>
  </>
);
```

---

### 1.4 Components — The Building Blocks 🔴

```
🧒 ELI5: Components are like DABBA (tiffin box) layers.
Each layer is separate, has its own contents, 
but together they make a complete meal.
Your app is just components inside components inside components.
```

```jsx
// ===== Functional Component (the ONLY way you need to learn) =====

// Simple component (no props)
function Welcome() {
  return <h1>Welcome to my app!</h1>;
}

// Component with props
function StudentCard({ name, cgpa, branch }) {
  return (
    <div className="card">
      <h2>{name}</h2>
      <p>Branch: {branch}</p>
      <p>CGPA: {cgpa}</p>
      {cgpa >= 8.5 && <span className="badge">🌟 Top Performer</span>}
    </div>
  );
}

// Using components (composition)
function App() {
  return (
    <div>
      <Welcome />
      <StudentCard name="Rahul" cgpa={8.5} branch="CSE" />
      <StudentCard name="Priya" cgpa={9.1} branch="ECE" />
      <StudentCard name="Amit" cgpa={7.2} branch="CSE" />
    </div>
  );
}
```

> ⚠️ **Note**: React used to have **Class Components**. They are **legacy** — you don't need to learn them. Modern React is 100% functional components + hooks. You might see them in old codebases, but never write new ones.

---

### 1.5 Props — Data Flowing Down 🔴

```
🧒 ELI5: Props are like ARGUMENTS to a function.
Parent component passes data to child.
Props are READ-ONLY — child cannot modify them.

Think of it like your professor giving you a question paper.
You can READ it, you can WORK with it.
But you can't CHANGE the question paper itself.
```

```jsx
// Parent passes props
function App() {
  return (
    <UserProfile 
      name="Rahul Sharma"
      age={21}
      skills={["React", "Node.js"]}
      isPlaced={true}
      address={{ city: "Pune", state: "Maharashtra" }}
    />
  );
}

// Child receives and uses props
function UserProfile({ name, age, skills, isPlaced, address }) {
  return (
    <div>
      <h2>{name}, {age}</h2>
      <p>📍 {address.city}, {address.state}</p>
      <p>Skills: {skills.join(", ")}</p>
      <p>Status: {isPlaced ? "✅ Placed" : "🔍 Searching"}</p>
    </div>
  );
}

// Props with default values
function Button({ text = "Click Me", color = "blue", onClick }) {
  return (
    <button 
      style={{ backgroundColor: color, color: "white", padding: "10px 20px" }}
      onClick={onClick}
    >
      {text}
    </button>
  );
}

// Children prop (special — content between opening/closing tags)
function Card({ title, children }) {
  return (
    <div className="card">
      <h3>{title}</h3>
      <div className="card-body">
        {children}  {/* Whatever is placed between <Card>...</Card> */}
      </div>
    </div>
  );
}

// Usage
<Card title="My Profile">
  <p>This is the card content!</p>
  <button>Edit Profile</button>
</Card>
```

---

### 1.6 State — Dynamic Data 🔴🔴🔴

```
🧒 ELI5: 
Props = data from PARENT (read-only, like a letter you receive)
State = data YOU own (read-write, like your personal diary)

When state changes → React RE-RENDERS the component automatically.
That's the MAGIC of React. You update data, UI updates itself.
Like a live cricket scoreboard — score changes, display updates.
```

```jsx
import { useState } from 'react';

function Counter() {
  // useState returns [currentValue, setterFunction]
  const [count, setCount] = useState(0);  // 0 is initial value

  return (
    <div>
      <h2>Count: {count}</h2>
      <button onClick={() => setCount(count + 1)}>+1</button>
      <button onClick={() => setCount(count - 1)}>-1</button>
      <button onClick={() => setCount(0)}>Reset</button>
    </div>
  );
}
```

### State with Different Data Types

```jsx
function ProfileForm() {
  // String state
  const [name, setName] = useState("");
  
  // Boolean state
  const [isEditing, setIsEditing] = useState(false);
  
  // Array state
  const [skills, setSkills] = useState(["JavaScript"]);
  
  // Object state
  const [address, setAddress] = useState({ city: "", state: "" });

  // ⚠️ IMPORTANT: Never mutate state directly!
  
  // ❌ WRONG
  // skills.push("React");          // Mutating directly — React won't re-render!
  
  // ✅ CORRECT — Create new array
  const addSkill = (newSkill) => {
    setSkills([...skills, newSkill]);           // Spread + add
  };

  const removeSkill = (index) => {
    setSkills(skills.filter((_, i) => i !== index));  // Filter out
  };

  // ✅ Updating objects — spread existing, override specific field
  const updateCity = (newCity) => {
    setAddress({ ...address, city: newCity });
  };

  // ✅ Functional update (when new state depends on old state)
  const [count, setCount] = useState(0);
  const increment = () => {
    setCount(prev => prev + 1);   // ✅ Safer than setCount(count + 1)
  };

  return (
    <div>
      <input 
        value={name} 
        onChange={(e) => setName(e.target.value)} 
        placeholder="Enter name"
      />
      <p>Hello, {name || "Stranger"}!</p>
      
      <button onClick={() => setIsEditing(!isEditing)}>
        {isEditing ? "Save" : "Edit"}
      </button>
      
      <ul>
        {skills.map((skill, i) => (
          <li key={i}>
            {skill} 
            <button onClick={() => removeSkill(i)}>❌</button>
          </li>
        ))}
      </ul>
    </div>
  );
}
```

### Props vs State — Master Comparison 🔴

```
┌────────────────────┬──────────────────────┬──────────────────────┐
│ Feature            │ Props                │ State                │
├────────────────────┼──────────────────────┼──────────────────────┤
│ Owner              │ Parent component     │ Component itself     │
│ Mutable?           │ ❌ Read-only         │ ✅ Can be updated    │
│ Direction          │ Parent → Child       │ Internal to component│
│ Triggers re-render │ When parent re-renders│ When setState called│
│ Analogy            │ Function arguments   │ Local variables      │
│ Purpose            │ Configuration/data   │ Dynamic/interactive  │
└────────────────────┴──────────────────────┴──────────────────────┘
```

---

### 1.7 Conditional Rendering 🔴

```jsx
function Dashboard({ isLoggedIn, role, notifications }) {
  // Method 1: Ternary operator (inline)
  return (
    <div>
      {isLoggedIn ? <h1>Welcome back!</h1> : <h1>Please sign in</h1>}
      
      {/* Method 2: && short-circuit (show only if true) */}
      {notifications > 0 && (
        <span className="badge">{notifications} new notifications</span>
      )}
      
      {/* Method 3: Early return (for complex conditions) */}
      <RoleBasedContent role={role} />
    </div>
  );
}

function RoleBasedContent({ role }) {
  if (role === "admin") return <AdminPanel />;
  if (role === "student") return <StudentDashboard />;
  if (role === "teacher") return <TeacherView />;
  return <GuestView />;   // Default fallback
}
```

---

### 1.8 Lists & Keys 🔴

```jsx
function StudentList() {
  const students = [
    { id: 1, name: "Rahul", cgpa: 8.5 },
    { id: 2, name: "Priya", cgpa: 9.1 },
    { id: 3, name: "Amit",  cgpa: 7.2 },
  ];

  return (
    <div>
      <h2>Students</h2>
      <ul>
        {students.map(student => (
          // ⚠️ key is MANDATORY — must be unique & stable
          <li key={student.id}>
            {student.name} — CGPA: {student.cgpa}
          </li>
        ))}
      </ul>
    </div>
  );
}
```

```
🔴 KEY RULES:
├── key must be UNIQUE among siblings
├── key should be STABLE (don't use Math.random())
├── ❌ Don't use array index as key (if list can reorder/delete)
├── ✅ Use id from data (database id, UUID)
└── key is NOT passed as a prop — it's React-internal
```

---

### 1.9 Event Handling 🔴

```jsx
function EventExamples() {
  // Basic click
  const handleClick = () => {
    alert("Button clicked!");
  };

  // With parameter
  const handleDelete = (id) => {
    console.log(`Deleting item ${id}`);
  };

  // Form submission
  const handleSubmit = (e) => {
    e.preventDefault();  // ⚠️ Prevent page reload!
    console.log("Form submitted");
  };

  // Input change
  const [text, setText] = useState("");
  const handleChange = (e) => {
    setText(e.target.value);
  };

  return (
    <div>
      {/* Basic event */}
      <button onClick={handleClick}>Click Me</button>
      
      {/* ⚠️ WRONG: This calls function immediately! */}
      {/* <button onClick={handleDelete(5)}>Delete</button> */}
      
      {/* ✅ CORRECT: Wrap in arrow function to pass args */}
      <button onClick={() => handleDelete(5)}>Delete</button>
      
      {/* Form */}
      <form onSubmit={handleSubmit}>
        <input value={text} onChange={handleChange} />
        <button type="submit">Submit</button>
      </form>
    </div>
  );
}
```

---

### 🏗️ Phase 1 Project: Build a To-Do App (Basic)

```
Features:
✅ Add a task (input + button)
✅ Display list of tasks
✅ Mark task as complete (strikethrough)
✅ Delete a task
✅ Show count of remaining tasks

Concepts practiced: Components, Props, State, Events, Lists, Conditional Rendering
Time: 2–3 hours

This is your "Hello World" of React. EVERY React developer has built this.
```

---

## 🧱 PHASE 2: HOOKS Deep Dive (Week 3–4)
### *"Hooks are the heart of modern React"*

```
⏱️ Estimated: 12–16 hours
Prerequisites: Phase 1
This phase separates React beginners from React developers.
```

---

### 2.1 useState — Already Covered ✅ (Phase 1.6)

### 2.2 useEffect — Side Effects 🔴🔴🔴

```
🧒 ELI5: 
Your component is like a chef making food (rendering UI).
useEffect is like cleanup/setup tasks AROUND the cooking:
  → Before cooking: Wash hands, preheat oven (setup)
  → After cooking: Wash dishes, wipe counters (cleanup)
  
useEffect handles things OUTSIDE the render:
  → Fetching data from API
  → Setting up timers/intervals
  → Subscribing to events
  → Updating document title
  → Interacting with browser APIs
```

```jsx
import { useState, useEffect } from 'react';

function UserProfile({ userId }) {
  const [user, setUser] = useState(null);
  const [loading, setLoading] = useState(true);

  // ===== useEffect Patterns =====

  // Pattern 1: Run on EVERY render (no dependency array)
  // ⚠️ Rarely useful — can cause infinite loops
  useEffect(() => {
    console.log("Component rendered");
  });

  // Pattern 2: Run ONCE on mount (empty dependency array [])
  useEffect(() => {
    console.log("Component mounted — like componentDidMount");
    
    // Cleanup function (runs on unmount)
    return () => {
      console.log("Component unmounted — like componentWillUnmount");
    };
  }, []);  // ← Empty array = run once

  // Pattern 3: Run when SPECIFIC values change
  useEffect(() => {
    // This runs whenever userId changes
    setLoading(true);
    
    fetch(`https://api.example.com/users/${userId}`)
      .then(res => res.json())
      .then(data => {
        setUser(data);
        setLoading(false);
      })
      .catch(err => {
        console.error(err);
        setLoading(false);
      });

    // Cleanup: cancel any pending work
    return () => {
      // cleanup logic (e.g., abort controller)
    };
  }, [userId]);  // ← Runs when userId changes

  if (loading) return <p>Loading...</p>;
  if (!user) return <p>User not found</p>;
  
  return <h2>{user.name}</h2>;
}
```

### useEffect Dependency Array Cheat Sheet

```
┌──────────────────────────────┬────────────────────────────────┐
│ Dependency Array             │ When it Runs                   │
├──────────────────────────────┼────────────────────────────────┤
│ No array at all              │ Every render (⚠️ be careful)   │
│ useEffect(() => {})          │                                │
├──────────────────────────────┼────────────────────────────────┤
│ Empty array []               │ Once on mount only             │
│ useEffect(() => {}, [])      │                                │
├──────────────────────────────┼────────────────────────────────┤
│ With values [a, b]           │ On mount + when a or b change  │
│ useEffect(() => {}, [a, b])  │                                │
└──────────────────────────────┴────────────────────────────────┘
```

### ❌ Common useEffect Mistakes

```jsx
// ❌ MISTAKE 1: Infinite loop
const [count, setCount] = useState(0);
useEffect(() => {
  setCount(count + 1);  // Updates state → triggers re-render → triggers effect → ∞
}); // No dependency array!

// ❌ MISTAKE 2: Object/Array in dependencies (always "changes")
useEffect(() => {
  // This runs EVERY render because {} !== {} (reference comparison)
}, [{ name: "Rahul" }]);  // ❌ New object each render

// ❌ MISTAKE 3: Forgetting cleanup (memory leak)
useEffect(() => {
  const interval = setInterval(() => console.log("tick"), 1000);
  // If component unmounts, interval keeps running → memory leak!
  
  return () => clearInterval(interval);  // ✅ Always cleanup!
}, []);

// ❌ MISTAKE 4: async directly in useEffect
useEffect(async () => {      // ❌ useEffect can't be async directly
  const data = await fetch(url);
});

// ✅ CORRECT: Define async function inside
useEffect(() => {
  const fetchData = async () => {
    const res = await fetch(url);
    const data = await res.json();
    setUser(data);
  };
  fetchData();
}, []);
```

---

### 2.3 useRef 🟡

```
🧒 ELI5: useRef is like a STICKY NOTE attached to your component.
→ It persists across renders (like state)
→ But changing it does NOT trigger a re-render (unlike state)
→ Also used to directly access DOM elements
```

```jsx
import { useRef, useState, useEffect } from 'react';

function SearchBox() {
  const inputRef = useRef(null);       // DOM reference
  const renderCount = useRef(0);        // Persistent value (no re-render)
  const [query, setQuery] = useState("");

  // Auto-focus input on mount
  useEffect(() => {
    inputRef.current.focus();
  }, []);

  // Track renders without causing re-renders
  useEffect(() => {
    renderCount.current += 1;
    console.log(`Rendered ${renderCount.current} times`);
  });

  return (
    <div>
      <input 
        ref={inputRef}                  // Attach ref to DOM element
        value={query}
        onChange={(e) => setQuery(e.target.value)}
        placeholder="Search..."
      />
      <button onClick={() => inputRef.current.focus()}>
        Focus Input
      </button>
    </div>
  );
}
```

### When to Use useRef vs useState

```
┌───────────────────┬───────────────────┬──────────────────────┐
│ Feature           │ useState          │ useRef               │
├───────────────────┼───────────────────┼──────────────────────┤
│ Triggers render   │ ✅ Yes            │ ❌ No                │
│ Persists across   │ ✅ Yes            │ ✅ Yes               │
│ renders           │                   │                      │
│ Access DOM        │ ❌ No             │ ✅ Yes               │
│ Use when          │ UI needs to update│ Value needed but no  │
│                   │                   │ UI update required   │
└───────────────────┴───────────────────┴──────────────────────┘
```

---

### 2.4 useContext — Global State Without Prop Drilling 🔴

```
🧒 ELI5: 
Imagine you have a WiFi password. Without Context:
  Grandpa tells Dad → Dad tells You → You tell your Friend
  (Every person in chain has to pass it — ANNOYING)

With Context:
  Grandpa writes password on the fridge.
  ANYONE in the house can read it directly.

That's useContext — shared data accessible to any component
without passing through every level.
```

```
                      THE PROP DRILLING PROBLEM
                      
           Without Context:          With Context:
           
           App (theme="dark")        App ← Provider(theme)
            │                            │
            ├── Header (theme)           ├── Header
            │    └── Nav (theme)         │    └── Nav ← useContext ✅
            │         └── Logo (theme)   │         └── Logo ← useContext ✅
            │                            │
            └── Main (theme)             └── Main
                 └── Card (theme)             └── Card ← useContext ✅
                      └── Button (theme)           └── Button ← useContext ✅
                      
           theme passed 4 levels!       Any component reads directly!
```

```jsx
// Step 1: Create Context
import { createContext, useContext, useState } from 'react';

const ThemeContext = createContext();

// Step 2: Create Provider (wraps your app)
function ThemeProvider({ children }) {
  const [theme, setTheme] = useState("light");
  
  const toggleTheme = () => {
    setTheme(prev => prev === "light" ? "dark" : "light");
  };

  return (
    <ThemeContext.Provider value={{ theme, toggleTheme }}>
      {children}
    </ThemeContext.Provider>
  );
}

// Step 3: Consume anywhere with useContext
function Navbar() {
  const { theme, toggleTheme } = useContext(ThemeContext);
  
  return (
    <nav style={{ 
      background: theme === "dark" ? "#333" : "#fff",
      color: theme === "dark" ? "#fff" : "#333" 
    }}>
      <h1>My App</h1>
      <button onClick={toggleTheme}>
        Switch to {theme === "light" ? "🌙 Dark" : "☀️ Light"} Mode
      </button>
    </nav>
  );
}

// Step 4: Wrap app with Provider
function App() {
  return (
    <ThemeProvider>
      <Navbar />
      <Main />
      <Footer />
    </ThemeProvider>
  );
}
```

---

### 2.5 useReducer — Complex State Logic 🟡

```
🧒 ELI5: 
useState is like a simple ON/OFF switch.
useReducer is like a full REMOTE CONTROL — 
multiple buttons (actions) that change state in different ways.

Use useReducer when:
→ State has multiple sub-values (objects)
→ Next state depends on previous state
→ State logic is complex
→ Multiple ways to update state
```

```jsx
import { useReducer } from 'react';

// Step 1: Define reducer function (pure function)
function todoReducer(state, action) {
  switch (action.type) {
    case "ADD":
      return [...state, { 
        id: Date.now(), 
        text: action.payload, 
        done: false 
      }];
    case "TOGGLE":
      return state.map(todo =>
        todo.id === action.payload 
          ? { ...todo, done: !todo.done } 
          : todo
      );
    case "DELETE":
      return state.filter(todo => todo.id !== action.payload);
    case "CLEAR_COMPLETED":
      return state.filter(todo => !todo.done);
    default:
      return state;
  }
}

// Step 2: Use in component
function TodoApp() {
  const [todos, dispatch] = useReducer(todoReducer, []);
  const [input, setInput] = useState("");

  const handleAdd = () => {
    if (input.trim()) {
      dispatch({ type: "ADD", payload: input });
      setInput("");
    }
  };

  return (
    <div>
      <input value={input} onChange={e => setInput(e.target.value)} />
      <button onClick={handleAdd}>Add</button>
      <button onClick={() => dispatch({ type: "CLEAR_COMPLETED" })}>
        Clear Done
      </button>
      
      <ul>
        {todos.map(todo => (
          <li key={todo.id}>
            <span 
              onClick={() => dispatch({ type: "TOGGLE", payload: todo.id })}
              style={{ textDecoration: todo.done ? "line-through" : "none" }}
            >
              {todo.text}
            </span>
            <button onClick={() => dispatch({ type: "DELETE", payload: todo.id })}>
              🗑
            </button>
          </li>
        ))}
      </ul>
    </div>
  );
}
```

---

### 2.6 useMemo & useCallback — Performance Optimization 🟡

```
🧒 ELI5:
useMemo = Caches a COMPUTED VALUE (like memorizing an exam answer)
useCallback = Caches a FUNCTION (like saving a recipe)

Why? Because in React, EVERY re-render re-creates everything.
For expensive calculations or stable function references, 
we "memorize" them so they don't recompute unnecessarily.
```

```jsx
import { useMemo, useCallback, useState } from 'react';

function ExpensiveComponent({ items, onItemClick }) {
  // useMemo — cache expensive calculation
  const sortedItems = useMemo(() => {
    console.log("Sorting... (expensive operation)");
    return [...items].sort((a, b) => a.price - b.price);
  }, [items]);  // Only recalculate when items change

  // useCallback — cache function reference
  const handleClick = useCallback((id) => {
    onItemClick(id);
  }, [onItemClick]);  // Only recreate when onItemClick changes

  return (
    <ul>
      {sortedItems.map(item => (
        <li key={item.id} onClick={() => handleClick(item.id)}>
          {item.name} — ₹{item.price}
        </li>
      ))}
    </ul>
  );
}
```

```
⚠️ IMPORTANT — Don't Over-Optimize!

useMemo/useCallback have their own cost (memory).
Use them ONLY when:
  ✅ Calculation is genuinely expensive (large arrays, complex math)
  ✅ Passing functions/values to memoized child components
  ✅ You've measured a performance problem

DON'T use for:
  ❌ Simple calculations (2 + 2)
  ❌ Everything "just in case"
  ❌ Without measuring first
```

---

### 2.7 Custom Hooks — Reusable Logic 🔴

```
🧒 ELI5: Custom Hooks are like creating your own SHORTCUT.
If you find yourself writing the same logic in multiple components,
extract it into a custom hook and reuse it.

Rules:
1. Name MUST start with "use" (e.g., useFetch, useLocalStorage)
2. Can use other hooks inside
3. Each component using it gets its OWN copy of state
```

```jsx
// Custom Hook: useFetch (reusable data fetching)
function useFetch(url) {
  const [data, setData] = useState(null);
  const [loading, setLoading] = useState(true);
  const [error, setError] = useState(null);

  useEffect(() => {
    const controller = new AbortController();
    
    setLoading(true);
    fetch(url, { signal: controller.signal })
      .then(res => {
        if (!res.ok) throw new Error(`HTTP ${res.status}`);
        return res.json();
      })
      .then(data => {
        setData(data);
        setLoading(false);
      })
      .catch(err => {
        if (err.name !== 'AbortError') {
          setError(err.message);
          setLoading(false);
        }
      });

    return () => controller.abort();  // Cleanup on unmount
  }, [url]);

  return { data, loading, error };
}

// Usage — clean and reusable!
function UserList() {
  const { data: users, loading, error } = useFetch("https://api.example.com/users");
  
  if (loading) return <p>Loading...</p>;
  if (error) return <p>Error: {error}</p>;
  
  return (
    <ul>
      {users.map(user => <li key={user.id}>{user.name}</li>)}
    </ul>
  );
}

// Custom Hook: useLocalStorage
function useLocalStorage(key, initialValue) {
  const [value, setValue] = useState(() => {
    const stored = localStorage.getItem(key);
    return stored ? JSON.parse(stored) : initialValue;
  });

  useEffect(() => {
    localStorage.setItem(key, JSON.stringify(value));
  }, [key, value]);

  return [value, setValue];
}

// Usage
function Settings() {
  const [theme, setTheme] = useLocalStorage("theme", "light");
  // Persists even after page refresh!
}
```

---

### 🏗️ Phase 2 Project: Weather App

```
Features:
✅ Search for any city
✅ Fetch weather data from OpenWeatherMap API
✅ Display temperature, humidity, wind speed
✅ Show different icons for different weather
✅ Loading states and error handling
✅ Save last searched city (localStorage)

Concepts practiced: useState, useEffect, useFetch custom hook,
                    API calls, conditional rendering, error handling
Time: 4–6 hours
API: https://openweathermap.org/api (free tier)
```

---

## 🧱 PHASE 3: ROUTING (Week 5)
### *"Multi-page feel in a single-page app"*

```
⏱️ Estimated: 5–7 hours
Priority: 🔴 — Every React app needs routing
```

```bash
npm install react-router-dom
```

```jsx
// App.jsx — Setting up routes
import { BrowserRouter, Routes, Route, Link, NavLink, 
         useParams, useNavigate, Navigate, Outlet } from 'react-router-dom';

function App() {
  const [isLoggedIn, setIsLoggedIn] = useState(false);

  return (
    <BrowserRouter>
      {/* Navigation */}
      <nav>
        <NavLink to="/" className={({isActive}) => isActive ? "active" : ""}>
          Home
        </NavLink>
        <NavLink to="/about">About</NavLink>
        <NavLink to="/students">Students</NavLink>
      </nav>

      {/* Route Definitions */}
      <Routes>
        <Route path="/" element={<Home />} />
        <Route path="/about" element={<About />} />
        
        {/* Nested Routes */}
        <Route path="/students" element={<StudentLayout />}>
          <Route index element={<StudentList />} />         {/* /students */}
          <Route path=":id" element={<StudentDetail />} />  {/* /students/123 */}
        </Route>
        
        {/* Protected Route */}
        <Route path="/dashboard" element={
          isLoggedIn ? <Dashboard /> : <Navigate to="/login" />
        } />
        
        {/* 404 Catch-all */}
        <Route path="*" element={<h1>404 — Page Not Found</h1>} />
      </Routes>
    </BrowserRouter>
  );
}

// Layout with Outlet (renders child routes)
function StudentLayout() {
  return (
    <div>
      <h1>Students Section</h1>
      <Outlet />  {/* Child route renders here */}
    </div>
  );
}

// Dynamic Route Parameters
function StudentDetail() {
  const { id } = useParams();             // Get :id from URL
  const navigate = useNavigate();          // Programmatic navigation

  return (
    <div>
      <h2>Student ID: {id}</h2>
      <button onClick={() => navigate("/students")}>
        ← Back to List
      </button>
      <button onClick={() => navigate(-1)}>
        ← Go Back
      </button>
    </div>
  );
}
```

### React Router Cheat Sheet

```
┌─────────────────────┬───────────────────────────────────────┐
│ Component/Hook      │ Purpose                               │
├─────────────────────┼───────────────────────────────────────┤
│ <BrowserRouter>     │ Wraps app, enables routing            │
│ <Routes>            │ Container for route definitions       │
│ <Route>             │ Maps path to component                │
│ <Link>              │ Navigation without page reload        │
│ <NavLink>           │ Link with active state styling        │
│ <Navigate>          │ Redirect to another route             │
│ <Outlet>            │ Renders child routes (nested)         │
│ useParams()         │ Access URL parameters (:id)           │
│ useNavigate()       │ Navigate programmatically             │
│ useLocation()       │ Current URL info                      │
│ useSearchParams()   │ Read/write query strings (?q=react)   │
└─────────────────────┴───────────────────────────────────────┘
```

---

## 🧱 PHASE 4: STYLING (Week 5–6)
### *"Make it look good — no one uses ugly apps"*

```
⏱️ Estimated: 5–6 hours
Priority: 🔴 Tailwind CSS (industry standard) | 🟡 Others
```

### Styling Approaches Comparison

```
┌────────────────────┬────────┬──────────┬───────────┬───────────────┐
│ Approach           │ Learn  │ Industry │ Bundle    │ Recommendation│
│                    │ Curve  │ Usage    │ Size      │               │
├────────────────────┼────────┼──────────┼───────────┼───────────────┤
│ Tailwind CSS       │ Medium │ ⭐⭐⭐⭐⭐│ Small     │ 🔴 LEARN THIS │
│ CSS Modules        │ Low    │ ⭐⭐⭐   │ Zero      │ 🟡 Good to know│
│ Styled Components  │ Medium │ ⭐⭐⭐   │ Medium    │ 🟢 Optional   │
│ Material UI (MUI)  │ Low    │ ⭐⭐⭐⭐  │ Large     │ 🟡 For speed  │
│ shadcn/ui          │ Low    │ ⭐⭐⭐⭐⭐│ Small     │ 🔴 LEARN THIS │
│ Plain CSS          │ Low    │ ⭐⭐     │ Zero      │ Basics only   │
└────────────────────┴────────┴──────────┴───────────┴───────────────┘
```

### Tailwind CSS Quick Start

```bash
# Already included if you used Vite + React template
npm install -D tailwindcss @tailwindcss/vite
```

```jsx
// Tailwind — utility-first CSS in your JSX
function StudentCard({ name, cgpa, branch }) {
  return (
    <div className="max-w-sm mx-auto bg-white rounded-xl shadow-md 
                    overflow-hidden hover:shadow-lg transition-shadow 
                    duration-300 p-6 m-4">
      <h2 className="text-xl font-bold text-gray-800">{name}</h2>
      <p className="text-gray-500 mt-1">{branch}</p>
      <div className="mt-4 flex items-center justify-between">
        <span className={`px-3 py-1 rounded-full text-sm font-semibold
          ${cgpa >= 8.5 
            ? "bg-green-100 text-green-800" 
            : cgpa >= 7 
            ? "bg-yellow-100 text-yellow-800" 
            : "bg-red-100 text-red-800"
          }`}>
          CGPA: {cgpa}
        </span>
      </div>
    </div>
  );
}
```

### shadcn/ui — Beautiful, Copy-Paste Components 🔴

```bash
# Modern component library (not installed as dependency — you OWN the code)
npx shadcn@latest init
npx shadcn@latest add button card input
```

```jsx
import { Button } from "@/components/ui/button";
import { Card, CardHeader, CardTitle, CardContent } from "@/components/ui/card";

function Dashboard() {
  return (
    <Card>
      <CardHeader>
        <CardTitle>Welcome Back, Rahul!</CardTitle>
      </CardHeader>
      <CardContent>
        <p>You have 3 pending assignments.</p>
        <Button variant="default">View All</Button>
        <Button variant="outline" className="ml-2">Dismiss</Button>
      </CardContent>
    </Card>
  );
}
```

> 🎯 **2025 Stack Recommendation**: **Tailwind CSS + shadcn/ui** — This is what most startups and product companies use. Master this combo.

---

## 🧱 PHASE 5: STATE MANAGEMENT (Week 6–7)
### *"When useContext isn't enough"*

```
⏱️ Estimated: 8–10 hours
Priority: 🔴 Context (already covered) + Zustand | 🟡 Others
```

### When Do You Need External State Management?

```
✅ useContext is ENOUGH for:
  → Theme (dark/light)
  → Auth (logged in user)
  → Language/locale
  → Small-medium apps

❌ useContext is NOT enough when:
  → Many components update shared state frequently
  → Complex state logic
  → Need middleware (logging, persistence)
  → Performance issues (Context re-renders ALL consumers)

📊 State Management Options (2025):
┌──────────────┬────────┬──────────┬────────────────────────────┐
│ Library      │ Size   │ Learning │ Best For                   │
├──────────────┼────────┼──────────┼────────────────────────────┤
│ Zustand      │ 1.1KB  │ Easy     │ 🔴 Most apps — start here │
│ Jotai        │ 2.4KB  │ Easy     │ 🟡 Atomic state           │
│ Redux Toolkit│ 11KB   │ Medium   │ 🟡 Large enterprise apps   │
│ MobX         │ 16KB   │ Medium   │ 🟢 Observable pattern     │
│ Context API  │ 0KB    │ Easy     │ 🔴 Simple shared state     │
└──────────────┴────────┴──────────┴────────────────────────────┘

🎯 Recommendation: Learn Zustand. It's simple, tiny, and covers 90% of use cases.
   Redux is still asked in interviews — know the concepts, but build with Zustand.
```

### Zustand — Simple & Powerful

```bash
npm install zustand
```

```jsx
// store.js — Create your store
import { create } from 'zustand';

const useCartStore = create((set, get) => ({
  // State
  items: [],
  totalPrice: 0,

  // Actions
  addItem: (product) => set((state) => ({
    items: [...state.items, { ...product, quantity: 1 }],
    totalPrice: state.totalPrice + product.price,
  })),

  removeItem: (productId) => set((state) => ({
    items: state.items.filter(item => item.id !== productId),
    totalPrice: state.totalPrice - 
      state.items.find(i => i.id === productId)?.price || 0,
  })),

  clearCart: () => set({ items: [], totalPrice: 0 }),

  // Computed (using get)
  getItemCount: () => get().items.length,
}));

export default useCartStore;
```

```jsx
// ANY component can use it — no Provider needed!
import useCartStore from './store';

function ProductCard({ product }) {
  const addItem = useCartStore(state => state.addItem);
  
  return (
    <div className="card">
      <h3>{product.name}</h3>
      <p>₹{product.price}</p>
      <button onClick={() => addItem(product)}>Add to Cart 🛒</button>
    </div>
  );
}

function CartIcon() {
  const itemCount = useCartStore(state => state.items.length);
  
  return (
    <div className="cart-icon">
      🛒 <span className="badge">{itemCount}</span>
    </div>
  );
}

function CartPage() {
  const { items, totalPrice, removeItem, clearCart } = useCartStore();
  
  return (
    <div>
      <h2>Your Cart</h2>
      {items.map(item => (
        <div key={item.id}>
          <span>{item.name} — ₹{item.price}</span>
          <button onClick={() => removeItem(item.id)}>Remove</button>
        </div>
      ))}
      <h3>Total: ₹{totalPrice}</h3>
      <button onClick={clearCart}>Clear Cart</button>
    </div>
  );
}
```

---

## 🧱 PHASE 6: API CALLS & DATA FETCHING (Week 7–8)
### *"Connect your frontend to the real world"*

```
⏱️ Estimated: 8–10 hours
Priority: 🔴 TanStack Query (react-query) | 🟡 axios | 🔴 fetch
```

### API Fetching Approaches

```
┌──────────────────┬────────────────────────────────────────────────┐
│ Method           │ When to Use                                    │
├──────────────────┼────────────────────────────────────────────────┤
│ fetch (built-in) │ 🔴 Simple requests, learning phase             │
│ axios            │ 🟡 Better error handling, interceptors          │
│ TanStack Query   │ 🔴 Production apps (caching, retries, etc.)    │
│ SWR              │ 🟢 Alternative to TanStack Query               │
└──────────────────┴────────────────────────────────────────────────┘
```

### TanStack Query (React Query) — Industry Standard 🔴

```bash
npm install @tanstack/react-query
```

```jsx
// main.jsx — Setup
import { QueryClient, QueryClientProvider } from '@tanstack/react-query';

const queryClient = new QueryClient();

function App() {
  return (
    <QueryClientProvider client={queryClient}>
      <YourApp />
    </QueryClientProvider>
  );
}
```

```jsx
import { useQuery, useMutation, useQueryClient } from '@tanstack/react-query';

// Fetching data — automatic caching, loading states, error handling
function StudentList() {
  const { data: students, isLoading, error } = useQuery({
    queryKey: ['students'],                           // Cache key
    queryFn: () => fetch('/api/students').then(r => r.json()),  // Fetch function
    staleTime: 5 * 60 * 1000,                         // Cache for 5 min
  });

  if (isLoading) return <Skeleton />;
  if (error) return <ErrorMessage message={error.message} />;

  return (
    <ul>
      {students.map(s => <li key={s.id}>{s.name}</li>)}
    </ul>
  );
}

// Mutating data (POST/PUT/DELETE) — with optimistic updates
function AddStudentForm() {
  const queryClient = useQueryClient();

  const mutation = useMutation({
    mutationFn: (newStudent) => 
      fetch('/api/students', {
        method: 'POST',
        headers: { 'Content-Type': 'application/json' },
        body: JSON.stringify(newStudent),
      }),
    onSuccess: () => {
      queryClient.invalidateQueries({ queryKey: ['students'] });
      // ↑ Refetch students list after adding
    },
  });

  const handleSubmit = (e) => {
    e.preventDefault();
    mutation.mutate({ name: "New Student", cgpa: 8.0 });
  };

  return (
    <form onSubmit={handleSubmit}>
      {/* ... form fields ... */}
      <button disabled={mutation.isPending}>
        {mutation.isPending ? "Adding..." : "Add Student"}
      </button>
      {mutation.isError && <p>Error: {mutation.error.message}</p>}
    </form>
  );
}
```

---

## 🧱 PHASE 7: FORMS & VALIDATION (Week 8)

```
⏱️ Estimated: 5–6 hours
Priority: 🔴 React Hook Form + Zod
```

```bash
npm install react-hook-form zod @hookform/resolvers
```

```jsx
import { useForm } from 'react-hook-form';
import { zodResolver } from '@hookform/resolvers/zod';
import { z } from 'zod';

// Step 1: Define validation schema with Zod
const registrationSchema = z.object({
  name: z.string().min(2, "Name must be at least 2 characters"),
  email: z.string().email("Invalid email address"),
  password: z.string()
    .min(8, "Password must be at least 8 characters")
    .regex(/[A-Z]/, "Must contain uppercase letter")
    .regex(/[0-9]/, "Must contain a number"),
  confirmPassword: z.string(),
  branch: z.enum(["CSE", "ECE", "IT", "ME"], {
    errorMap: () => ({ message: "Please select a branch" })
  }),
  cgpa: z.number().min(0).max(10),
  agreeToTerms: z.literal(true, {
    errorMap: () => ({ message: "You must accept the terms" })
  }),
}).refine(data => data.password === data.confirmPassword, {
  message: "Passwords don't match",
  path: ["confirmPassword"],
});

// Step 2: Build the form
function RegistrationForm() {
  const { 
    register, 
    handleSubmit, 
    formState: { errors, isSubmitting },
    reset 
  } = useForm({
    resolver: zodResolver(registrationSchema),
  });

  const onSubmit = async (data) => {
    console.log("Valid data:", data);
    // Send to API...
    reset();
  };

  return (
    <form onSubmit={handleSubmit(onSubmit)} className="space-y-4">
      <div>
        <input {...register("name")} placeholder="Full Name" />
        {errors.name && <p className="text-red-500">{errors.name.message}</p>}
      </div>

      <div>
        <input {...register("email")} placeholder="Email" />
        {errors.email && <p className="text-red-500">{errors.email.message}</p>}
      </div>

      <div>
        <input {...register("password")} type="password" placeholder="Password" />
        {errors.password && <p className="text-red-500">{errors.password.message}</p>}
      </div>

      <div>
        <select {...register("branch")}>
          <option value="">Select Branch</option>
          <option value="CSE">CSE</option>
          <option value="ECE">ECE</option>
          <option value="IT">IT</option>
        </select>
        {errors.branch && <p className="text-red-500">{errors.branch.message}</p>}
      </div>

      <button type="submit" disabled={isSubmitting}>
        {isSubmitting ? "Registering..." : "Register"}
      </button>
    </form>
  );
}
```

---

## 🧱 PHASE 8: TESTING (Week 9)

```
⏱️ Estimated: 5–6 hours
Priority: 🟡 for placements | 🔴 for actual jobs
```

```
┌─────────────────────┬─────────────────────────────────────┐
│ Tool                │ Purpose                             │
├─────────────────────┼─────────────────────────────────────┤
│ Vitest              │ 🔴 Test runner (fast, Vite-native)  │
│ React Testing Lib   │ 🔴 Test components (user-focused)   │
│ Playwright          │ 🟡 End-to-end testing               │
│ Cypress             │ 🟡 E2E alternative                  │
└─────────────────────┴─────────────────────────────────────┘
```

```jsx
// Counter.test.jsx
import { render, screen, fireEvent } from '@testing-library/react';
import { describe, it, expect } from 'vitest';
import Counter from './Counter';

describe('Counter Component', () => {
  it('renders initial count of 0', () => {
    render(<Counter />);
    expect(screen.getByText('Count: 0')).toBeInTheDocument();
  });

  it('increments when + button is clicked', () => {
    render(<Counter />);
    fireEvent.click(screen.getByText('+1'));
    expect(screen.getByText('Count: 1')).toBeInTheDocument();
  });

  it('resets to 0 when Reset is clicked', () => {
    render(<Counter />);
    fireEvent.click(screen.getByText('+1'));
    fireEvent.click(screen.getByText('+1'));
    fireEvent.click(screen.getByText('Reset'));
    expect(screen.getByText('Count: 0')).toBeInTheDocument();
  });
});
```

---

## 🧱 PHASE 9: TYPES WITH TYPESCRIPT (Week 9–10)

```
⏱️ Estimated: 8–10 hours
Priority: 🔴 — TypeScript is expected in 2025 React jobs
```

```tsx
// Props with TypeScript
interface StudentCardProps {
  name: string;
  cgpa: number;
  branch: "CSE" | "ECE" | "IT" | "ME";
  isPlaced?: boolean;           // Optional prop
  onSelect: (id: number) => void;  // Function prop
}

function StudentCard({ name, cgpa, branch, isPlaced = false, onSelect }: StudentCardProps) {
  return (
    <div onClick={() => onSelect(1)}>
      <h2>{name}</h2>
      <p>{branch} — {cgpa}</p>
      {isPlaced && <span>✅ Placed</span>}
    </div>
  );
}

// State with TypeScript
interface User {
  id: number;
  name: string;
  email: string;
}

function UserProfile() {
  const [user, setUser] = useState<User | null>(null);
  const [count, setCount] = useState<number>(0);
  const [items, setItems] = useState<string[]>([]);
  
  // ...
}

// Event types
function SearchInput() {
  const handleChange = (e: React.ChangeEvent<HTMLInputElement>) => {
    console.log(e.target.value);
  };

  const handleSubmit = (e: React.FormEvent<HTMLFormElement>) => {
    e.preventDefault();
  };

  return (
    <form onSubmit={handleSubmit}>
      <input onChange={handleChange} />
    </form>
  );
}
```

---

## 🧱 PHASE 10: FRAMEWORKS — Next.js (Week 10–12)
### *"React on steroids — production-ready framework"*

```
⏱️ Estimated: 15–20 hours
Priority: 🔴🔴 — Most React job listings mention Next.js
```

```
WHY NEXT.JS?

React alone is a CLIENT-SIDE library.
Next.js adds:
  ✅ Server-Side Rendering (SSR) — faster page loads, SEO
  ✅ Static Site Generation (SSG) — pre-built pages
  ✅ File-based routing (no react-router needed)
  ✅ API routes (backend in same project!)
  ✅ Image optimization
  ✅ Built-in TypeScript support
  ✅ Deployment on Vercel (free, one-click)
```

```bash
npx create-next-app@latest my-next-app
```

```
my-next-app/
├── app/                    # App Router (new — learn this)
│   ├── layout.tsx          # Root layout (wraps all pages)
│   ├── page.tsx            # Home page (/)
│   ├── about/
│   │   └── page.tsx        # /about
│   ├── students/
│   │   ├── page.tsx        # /students
│   │   └── [id]/
│   │       └── page.tsx    # /students/123 (dynamic route)
│   └── api/
│       └── students/
│           └── route.ts    # API endpoint: /api/students
├── components/
├── public/
└── package.json
```

```tsx
// app/students/page.tsx — Server Component (fetches on server!)
async function StudentsPage() {
  // This runs on the SERVER — no useEffect needed!
  const res = await fetch('https://api.example.com/students', {
    cache: 'no-store',  // SSR (fresh data every request)
    // next: { revalidate: 60 }  // ISR (revalidate every 60 seconds)
  });
  const students = await res.json();

  return (
    <div>
      <h1>Students</h1>
      {students.map(s => (
        <div key={s.id}>{s.name} — {s.cgpa}</div>
      ))}
    </div>
  );
}

export default StudentsPage;
```

```tsx
// Client Component (needs interactivity)
'use client';  // ← This directive makes it a client component

import { useState } from 'react';

export default function SearchBar() {
  const [query, setQuery] = useState('');
  
  return (
    <input 
      value={query}
      onChange={e => setQuery(e.target.value)}
      placeholder="Search students..."
    />
  );
}
```

```
Server Components vs Client Components:

┌─────────────────────┬──────────────────┬──────────────────┐
│ Feature             │ Server Component │ Client Component │
├─────────────────────┼──────────────────┼──────────────────┤
│ Runs on             │ Server           │ Browser          │
│ Can use hooks       │ ❌ No            │ ✅ Yes           │
│ Can use events      │ ❌ No            │ ✅ Yes           │
│ Can fetch directly  │ ✅ Yes (async)   │ Via useEffect    │
│ Bundle size impact  │ ✅ Zero          │ Adds to bundle   │
│ SEO                 │ ✅ Excellent     │ ❌ Needs work    │
│ Directive needed    │ Default          │ 'use client'     │
│ Use for             │ Data display     │ Interactive UI   │
└─────────────────────┴──────────────────┴──────────────────┘

🎯 Rule of thumb: Keep components SERVER by default.
   Only add 'use client' when you NEED interactivity.
```

---

## 🧱 PHASE 11: ADVANCED TOPICS (Week 12–14)

```
⏱️ Estimated: 10–12 hours
Priority: 🟡 to 🟢 — Learn as needed
```

| Topic | Priority | What & Why |
|-------|----------|------------|
| **Error Boundaries** | 🟡 | Catch errors in component tree, show fallback UI |
| **Suspense** | 🟡 | Show loading state while child component loads |
| **Portals** | 🟢 | Render component outside root DOM (modals, tooltips) |
| **React.memo** | 🟡 | Skip re-render if props haven't changed |
| **Lazy Loading** | 🟡 | Load components only when needed (code splitting) |
| **Framer Motion** | 🟢 | Beautiful animations |
| **React Native** | 🟢 | Mobile apps with React (separate learning path) |

```jsx
// Lazy Loading (Code Splitting)
import { lazy, Suspense } from 'react';

const HeavyComponent = lazy(() => import('./HeavyComponent'));

function App() {
  return (
    <Suspense fallback={<p>Loading...</p>}>
      <HeavyComponent />
    </Suspense>
  );
}

// Error Boundary (class component — one of the few exceptions)
class ErrorBoundary extends React.Component {
  state = { hasError: false };

  static getDerivedStateFromError(error) {
    return { hasError: true };
  }

  render() {
    if (this.state.hasError) {
      return <h2>Something went wrong. Please refresh.</h2>;
    }
    return this.props.children;
  }
}

// Usage
<ErrorBoundary>
  <MyComponent />
</ErrorBoundary>
```

---

## 🧱 PHASE 12: DEPLOYMENT & PRODUCTION (Week 14–16)

```
⏱️ Estimated: 3–4 hours
Priority: 🔴 — An app nobody can access is useless
```

```
┌──────────────────┬───────┬──────────┬─────────────────────────┐
│ Platform         │ Free? │ Best For │ Deploy Command          │
├──────────────────┼───────┼──────────┼─────────────────────────┤
│ Vercel           │ ✅    │ Next.js  │ Push to GitHub → auto   │
│ Netlify          │ ✅    │ React    │ Push to GitHub → auto   │
│ Railway          │ ✅*   │ Full stack│ railway up              │
│ GitHub Pages     │ ✅    │ Static   │ npm run deploy          │
│ AWS Amplify      │ ✅*   │ Enterprise│ amplify publish        │
└──────────────────┴───────┴──────────┴─────────────────────────┘

🎯 Recommendation:
  → React (Vite) app → Vercel or Netlify
  → Next.js app → Vercel (built by same team — best integration)
```

---

## 📅 COMPLETE WEEK-BY-WEEK PLAN

```
┌────────┬──────────────────────────────────────┬─────────┬─────────────────────────┐
│ Week   │ Topics                                │ Priority│ Project                 │
├────────┼──────────────────────────────────────┼─────────┼─────────────────────────┤
│ Week 1 │ Setup, JSX, Components, Props         │ 🔴      │                         │
│ Week 2 │ State, Events, Conditional, Lists      │ 🔴      │ ✅ Todo App             │
│ Week 3 │ useEffect, useRef, Custom Hooks        │ 🔴      │                         │
│ Week 4 │ useContext, useReducer, useMemo         │ 🔴      │ ✅ Weather App          │
│ Week 5 │ React Router, Navigation               │ 🔴      │                         │
│ Week 6 │ Tailwind CSS, shadcn/ui                 │ 🔴      │ ✅ Portfolio Website    │
│ Week 7 │ Zustand, State Management               │ 🟡      │                         │
│ Week 8 │ API Calls (TanStack Query), Forms        │ 🔴      │ ✅ E-commerce Frontend │
│ Week 9 │ Testing, TypeScript basics               │ 🟡      │                         │
│ Week 10│ Next.js Fundamentals                     │ 🔴      │                         │
│ Week 11│ Next.js Advanced (SSR, API Routes)       │ 🔴      │ ✅ Full Stack Blog      │
│ Week 12│ Auth, Deployment                         │ 🔴      │                         │
│ Week 13│ Advanced Topics, Optimization            │ 🟡      │ ✅ Capstone Project     │
│ Week 14│ Polish projects, prepare for interviews  │ 🔴      │                         │
└────────┴──────────────────────────────────────┴─────────┴─────────────────────────┘
```

### ✅ Milestones

```
After Week 2:  You can build basic interactive UIs
After Week 4:  You can build single-page apps with API integration
After Week 6:  You can build beautiful, styled applications
After Week 8:  You're ready for internship-level React work ✅
After Week 12: You're ready for product company frontend interviews ✅
After Week 14: You have a portfolio that stands out ✅
```

---

## 🏗️ PORTFOLIO PROJECTS (Build These — In Order)

```
┌────┬─────────────────────────┬──────────────┬─────────────────────────────┐
│ #  │ Project                 │ Level        │ Skills Demonstrated         │
├────┼─────────────────────────┼──────────────┼─────────────────────────────┤
│ 1  │ Todo App                │ Beginner     │ State, Events, CRUD         │
│ 2  │ Weather App             │ Beginner+    │ API, useEffect, Custom Hooks│
│ 3  │ Portfolio Website       │ Intermediate │ Routing, Styling, Deploy    │
│ 4  │ E-commerce Store        │ Intermediate │ State mgmt, Cart, API       │
│ 5  │ Blog with CMS           │ Intermediate+│ Next.js, SSR, DB, Auth      │
│ 6  │ Real-time Chat App      │ Advanced     │ WebSockets, Auth, Deploy    │
│ 7  │ Project Management Tool │ Advanced     │ Full CRUD, Teams, Dashboard │
└────┴─────────────────────────┴──────────────┴─────────────────────────────┘

🎯 For placements: Build at least projects #1-#5
🎯 For product companies: Add #6 or #7
🎯 Deploy ALL of them. GitHub repo + Live link = 💪
```

---

## 💼 REACT IN INTERVIEWS — What They Ask

### Conceptual Questions 🔴

```
1.  What is the Virtual DOM? How does it work?
2.  Explain the component lifecycle (in hooks context)
3.  useState vs useReducer — when to use which?
4.  What are controlled vs uncontrolled components?
5.  Explain the useEffect cleanup function
6.  What is prop drilling? How to solve it?
7.  What is React.memo? When to use it?
8.  Explain the key prop — why is it important?
9.  What are Higher Order Components?
10. Server Components vs Client Components (Next.js)
11. Explain reconciliation (diffing algorithm)
12. What is hydration in SSR?
13. How does useRef differ from useState?
14. What are error boundaries?
15. Explain code splitting and lazy loading
```

### Coding Round — Common Tasks

```
1.  Build a counter with increment/decrement/reset
2.  Build a search filter (search from list)
3.  Build a star rating component
4.  Fetch and display data from API
5.  Build a modal/dialog component
6.  Create a multi-step form
7.  Build an infinite scroll list
8.  Create a debounced search input
9.  Build a dark/light theme toggle
10. Create a countdown timer
```

### Machine Coding Round (45–60 min)

```
Build one of these from scratch in interview:
  → Kanban Board (drag & drop)
  → File Explorer (tree structure)
  → Auto-complete Search
  → Pagination Component
  → Shopping Cart
  → Tic-tac-toe Game
  → Accordian / Tabs Component
  → Comment Section (nested comments)
```

---

## 📚 BEST RESOURCES

| Type | Resource | Why |
|------|----------|-----|
| 📺 YouTube (Hindi) | **Chai aur Code — React Playlist** | Hitesh Choudhary, practical, Hindi |
| 📺 YouTube (Hindi) | **CodeWithHarry — React Crash Course** | Quick start, Hindi |
| 📺 YouTube (English) | **Jack Herrington** | Advanced patterns, real-world |
| 📺 YouTube (English) | **Theo Browne (t3.gg)** | Industry perspective, modern stack |
| 📺 YouTube (English) | **Web Dev Simplified** | Clear explanations |
| 📖 Official Docs | **react.dev** | 🔴 BEST resource — interactive tutorials |
| 📖 Official Docs | **nextjs.org/learn** | Best Next.js tutorial |
| 🆓 Course | **Full Stack Open (Helsinki)** | Comprehensive, free, university-level |
| 📺 Playlist | **Codevolution — React** | Systematic, complete |
| 🏋️ Practice | **React Coding Challenges** (GreatFrontEnd) | Interview-style practice |

---

## 🔧 RECOMMENDED DEV SETUP (2025)

```
Editor:          VS Code
Extensions:
  🔴 ES7+ React/Redux/React-Native Snippets
  🔴 Tailwind CSS IntelliSense
  🔴 Prettier (auto-formatting)
  🔴 ESLint
  🟡 Auto Rename Tag
  🟡 Thunder Client (API testing)
  🟡 GitLens

Browser Extensions:
  🔴 React Developer Tools (Chrome)
  🟡 Redux DevTools (if using Redux)

Terminal: Use integrated VS Code terminal
```

---

## 🎯 THE MODERN REACT TECH STACK (2025)

```
The "I'm ready for any frontend job" stack:

┌─────────────────────────────────────────────────┐
│  Framework:      Next.js 15 (App Router)        │
│  Language:       TypeScript                      │
│  Styling:        Tailwind CSS + shadcn/ui        │
│  State:          Zustand (+ React Context)       │
│  Data Fetching:  TanStack Query                  │
│  Forms:          React Hook Form + Zod           │
│  Auth:           NextAuth.js (Auth.js)           │
│  Database:       Prisma + PostgreSQL             │
│  Deployment:     Vercel                           │
│  Testing:        Vitest + React Testing Library  │
│  Version Control: Git + GitHub                   │
└─────────────────────────────────────────────────┘

This stack is used by: Vercel, cal.com, Dub.co,
and hundreds of YC startups.
```

---
