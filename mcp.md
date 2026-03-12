

# 🔌 MCP (Model Context Protocol) — Complete Roadmap

> **Profile Context:** Nilesh, 4th Year, MMMUT Gorakhpur, 8th Semester
> 🔥 **This is one of the HOTTEST and NEWEST topics in AI right now (2024-25)**
> You're getting in EARLY — that's a massive advantage.

---

## 🤔 First — What Exactly is MCP?

```
🧒 ELI5 — The Chai Stall Analogy

Imagine every chai stall in India has a DIFFERENT ordering system:
→ Stall A: You write on paper
→ Stall B: You shout your order  
→ Stall C: You press buttons on a machine
→ Stall D: You use an app

Frustrating, right? You have to learn each system separately.

Now imagine someone creates a UNIVERSAL ORDERING SYSTEM:
→ Works at EVERY chai stall
→ Same interface everywhere
→ One method to order chai, coffee, snacks — anything

THAT'S what MCP does for AI!

Instead of chai stalls, think of TOOLS & DATA SOURCES:
→ Files on your computer
→ Databases (PostgreSQL, MongoDB)
→ APIs (GitHub, Slack, Google Drive)
→ Web browsers
→ Code execution environments

MCP = A UNIVERSAL STANDARD for connecting AI models 
      to ANY external tool or data source.

It's like USB-C for AI 🔌
→ One protocol, connects everything.
```

### 📖 Formal Definition:

> **Model Context Protocol (MCP)** is an **open protocol** developed by **Anthropic** (creators of Claude) that provides a **standardized way** for AI applications (LLMs) to connect with external data sources, tools, and services. It follows a **client-server architecture** using **JSON-RPC 2.0** for communication.

---

## 🏗️ MCP Architecture — The Big Picture

```
┌─────────────────────────────────────────────────────────────────┐
│                        MCP ARCHITECTURE                         │
│                                                                 │
│  ┌──────────────┐                                               │
│  │   MCP HOST   │  (Claude Desktop, IDE, AI App)                │
│  │              │                                               │
│  │  ┌────────┐  │     ┌─────────────┐   ┌──────────────────┐   │
│  │  │MCP     │◄─┼────►│ MCP SERVER A│──►│ 📁 Local Files   │   │
│  │  │CLIENT 1│  │     └─────────────┘   └──────────────────┘   │
│  │  └────────┘  │                                               │
│  │              │     ┌─────────────┐   ┌──────────────────┐   │
│  │  ┌────────┐  │     │ MCP SERVER B│──►│ 🗄️ Database      │   │
│  │  │MCP     │◄─┼────►│             │   │ (PostgreSQL)     │   │
│  │  │CLIENT 2│  │     └─────────────┘   └──────────────────┘   │
│  │  └────────┘  │                                               │
│  │              │     ┌─────────────┐   ┌──────────────────┐   │
│  │  ┌────────┐  │     │ MCP SERVER C│──►│ 🌐 Web APIs      │   │
│  │  │MCP     │◄─┼────►│             │   │ (GitHub, Slack)  │   │
│  │  │CLIENT 3│  │     └─────────────┘   └──────────────────┘   │
│  │  └────────┘  │                                               │
│  └──────────────┘                                               │
│                                                                 │
│  KEY INSIGHT: Each client maintains 1:1 connection              │
│  with ONE server. Host can have MULTIPLE clients.               │
└─────────────────────────────────────────────────────────────────┘
```

### Three Core Components:

```
┌──────────────────┬──────────────────────────────────────────────┐
│ Component        │ What It Does                                 │
├──────────────────┼──────────────────────────────────────────────┤
│ 🏠 MCP HOST     │ The AI application (Claude Desktop, your     │
│                  │ custom app, VS Code + Copilot, etc.)         │
│                  │ → Manages multiple MCP clients               │
│                  │ → Has the LLM inside it                      │
├──────────────────┼──────────────────────────────────────────────┤
│ 🔌 MCP CLIENT   │ Lives inside the Host                        │
│                  │ → Maintains 1:1 connection with a server     │
│                  │ → Sends requests, receives responses         │
│                  │ → Handles the protocol communication         │
├──────────────────┼──────────────────────────────────────────────┤
│ ⚙️ MCP SERVER   │ A lightweight program YOU build              │
│                  │ → Exposes specific capabilities              │
│                  │ → Connects to actual data/tools              │
│                  │ → Can be local process OR remote service     │
└──────────────────┴──────────────────────────────────────────────┘
```

---

## 🎯 What MCP Servers Expose — 3 Primitives

```
┌─────────────────────────────────────────────────────────────┐
│              MCP SERVER CAPABILITIES                        │
├─────────────┬───────────────────────────────────────────────┤
│             │                                               │
│  📦 RESOURCES  │ DATA the AI can READ                      │
│             │ → File contents                               │
│             │ → Database records                            │
│             │ → API responses                               │
│             │ → Live system data                            │
│             │ Analogy: "Reading a menu card"                │
│             │ Control: Application-controlled               │
├─────────────┼───────────────────────────────────────────────┤
│             │                                               │
│  🔧 TOOLS   │ ACTIONS the AI can PERFORM                   │
│             │ → Send a message on Slack                     │
│             │ → Create a GitHub issue                       │
│             │ → Query a database                            │
│             │ → Run a calculation                           │
│             │ Analogy: "Ordering from the menu"             │
│             │ Control: Model-controlled (AI decides when)   │
├─────────────┼───────────────────────────────────────────────┤
│             │                                               │
│  💬 PROMPTS │ TEMPLATES for common interactions             │
│             │ → Pre-built prompt templates                  │
│             │ → Slash commands                              │
│             │ → Workflow templates                          │
│             │ Analogy: "Combo meals — pre-set orders"       │
│             │ Control: User-controlled                      │
└─────────────┴───────────────────────────────────────────────┘
```

---

## 🧭 WHY Should You Learn MCP? (Reality Check)

```
┌──────────────────────────────────────────────────────────────┐
│  🟢 REASONS TO LEARN MCP NOW:                                │
│                                                              │
│  1. 🆕 BRAND NEW (late 2024) — Very few people know it      │
│     → Early mover advantage = stand out in interviews        │
│                                                              │
│  2. 🏢 BACKED BY ANTHROPIC — Not some random project        │
│     → Already adopted by: Cursor, Windsurf, Zed,            │
│       Sourcegraph, Replit, JetBrains, and more               │
│                                                              │
│  3. 🔮 FUTURE OF AI TOOLING — AI Agents NEED this           │
│     → Every AI agent framework will use MCP or similar       │
│                                                              │
│  4. 💰 HIGH DEMAND, LOW SUPPLY of MCP developers            │
│     → Companies building AI products need this skill         │
│                                                              │
│  5. 📄 KILLER RESUME ITEM                                    │
│     → "Built custom MCP servers" = instant interview call    │
│     → Shows you understand cutting-edge AI infrastructure    │
│                                                              │
│  6. 🛠️ PRACTICAL SKILL — Not just theory                    │
│     → You can build REAL tools that people use               │
│     → Open source MCP servers get stars & recognition        │
│                                                              │
├──────────────────────────────────────────────────────────────┤
│  🟡 HONEST CAVEATS:                                          │
│                                                              │
│  → Protocol is still evolving (things may change)            │
│  → Not many "MCP Engineer" job titles exist YET              │
│  → Best combined with broader AI/LLM skills                  │
│  → Most useful if you're going into AI tooling/infra         │
└──────────────────────────────────────────────────────────────┘
```

---

## 🗺️ COMPLETE MCP ROADMAP — 5 PHASES

```
╔══════════════════════════════════════════════════════════════════════╗
║                       MCP LEARNING PATH                             ║
║                                                                      ║
║  PHASE 1 ───► PHASE 2 ───► PHASE 3 ───► PHASE 4 ───► PHASE 5      ║
║  Prerequisites  MCP        First MCP    Advanced     Portfolio &    ║
║  & Foundations  Concepts   Server       Servers      Open Source    ║
║  [1-2 weeks]   [1 week]   [1-2 weeks]  [2-3 weeks]  [2 weeks]     ║
║                                                                      ║
║              Total: ~8-10 weeks (2-2.5 months)                       ║
╚══════════════════════════════════════════════════════════════════════╝
```

---

## 📗 PHASE 1: PREREQUISITES (Week 1-2)

> **You MUST know these before touching MCP**
> Skip topics you already know, but be honest with yourself.

### 1A: Python (Intermediate+)

| # | Topic | Priority | You Need This For |
|---|-------|----------|-------------------|
| 1 | Python basics (data types, functions, loops) | 🔴 | Everything |
| 2 | **Async/Await (asyncio)** | 🔴 | MCP uses async heavily |
| 3 | **Decorators** | 🔴 | MCP SDK uses decorators |
| 4 | **Type Hints (typing module)** | 🔴 | MCP requires type annotations |
| 5 | Context Managers (with statement) | 🟡 | Resource management |
| 6 | Error Handling (try/except, custom exceptions) | 🔴 | Robust servers |
| 7 | Virtual Environments (venv, uv) | 🔴 | Project setup |
| 8 | Package management (pip, uv) | 🔴 | Installing MCP SDK |

#### 💻 Key Python Concepts for MCP:

```python
# ════════════════════════════════════════════
#  ASYNC/AWAIT — MCP's Communication Model
# ════════════════════════════════════════════

import asyncio

# ❌ Without async — BLOCKING (one task at a time)
# Like a chai stall with ONE worker — serves one customer,
# everyone else WAITS

# ✅ With async — NON-BLOCKING (multiple tasks concurrently)  
# Like a chai stall where the worker starts boiling water,
# while it heats — takes next order, while that brews — 
# serves previous customer

async def fetch_data_from_db():
    """Simulates database query (takes time)"""
    print("📡 Querying database...")
    await asyncio.sleep(2)  # Simulates I/O wait
    return {"user": "Nilesh", "cgpa": 7.67}

async def fetch_data_from_api():
    """Simulates API call (takes time)"""
    print("🌐 Calling external API...")
    await asyncio.sleep(3)  # Simulates I/O wait
    return {"weather": "sunny", "temp": 35}

async def main():
    # Run BOTH tasks concurrently (not one after another)
    # Total time: ~3 seconds (not 2+3=5 seconds!)
    results = await asyncio.gather(
        fetch_data_from_db(),
        fetch_data_from_api()
    )
    print(f"DB Result: {results[0]}")
    print(f"API Result: {results[1]}")

asyncio.run(main())

# ════════════════════════════════════════════
#  DECORATORS — How MCP SDK Registers Tools
# ════════════════════════════════════════════

# A decorator WRAPS a function with extra behavior
# MCP uses this to register your functions as "tools"

def register_tool(func):
    """Simple decorator that registers a function"""
    print(f"🔧 Registered tool: {func.__name__}")
    def wrapper(*args, **kwargs):
        print(f"⚡ Calling tool: {func.__name__}")
        return func(*args, **kwargs)
    return wrapper

@register_tool  # This is how MCP tools are defined!
def calculate_cgpa(marks: list[float]) -> float:
    return sum(marks) / len(marks)

# When this file loads: "🔧 Registered tool: calculate_cgpa"
result = calculate_cgpa([8.0, 7.5, 7.8, 7.4])
# Output: "⚡ Calling tool: calculate_cgpa"

# ════════════════════════════════════════════
#  TYPE HINTS — MCP Needs These for Schema
# ════════════════════════════════════════════

from typing import Optional

def search_student(
    name: str,                          # Required string
    branch: str = "CSE",                # Default value
    min_cgpa: Optional[float] = None,   # Optional parameter
    limit: int = 10                     # Default integer
) -> dict[str, any]:                    # Return type
    """Search for students by name and filters.
    
    Args:
        name: Student name to search for
        branch: Department filter
        min_cgpa: Minimum CGPA threshold
        limit: Max results to return
    
    Returns:
        Dictionary with matching students
    """
    # MCP automatically converts these type hints 
    # into a JSON schema that the LLM can understand!
    pass
```

### 1B: Understanding LLMs & AI Basics

| # | Topic | Priority | Time |
|---|-------|----------|------|
| 1 | What are LLMs? (GPT, Claude, etc.) | 🔴 | 1 hr |
| 2 | How LLMs use tools (function calling) | 🔴 | 2 hrs |
| 3 | What are AI Agents? | 🔴 | 1 hr |
| 4 | API keys, tokens, rate limits | 🟡 | 1 hr |
| 5 | JSON and JSON Schema | 🔴 | 1 hr |
| 6 | Basic understanding of client-server architecture | 🔴 | 1 hr |
| 7 | What is JSON-RPC? | 🟡 | 30 min |

```
🧒 ELI5 — LLM Tool Use (Function Calling)

Normally, ChatGPT/Claude can only READ and WRITE text.
It CANNOT:
  → Check your email
  → Look at your files
  → Query a database
  → Book a ticket

It's like a REALLY SMART person locked in a room 
with no phone, no internet, no tools.

FUNCTION CALLING lets you give the AI a "tool belt":
  → "Here's a calculator tool"
  → "Here's a database query tool"
  → "Here's a file reader tool"

The AI looks at your question, DECIDES which tool to use,
sends parameters, gets results, and uses them to answer.

MCP STANDARDIZES how these tools are defined and connected!
```

### 1C: Development Tools Setup

| # | Tool | Why | Install |
|---|------|-----|---------|
| 1 | **Python 3.10+** | MCP SDK needs it | python.org |
| 2 | **uv** (package manager) | Recommended by MCP docs | `pip install uv` |
| 3 | **VS Code** | Best editor for MCP dev | code.visualstudio.com |
| 4 | **Claude Desktop** | Test your MCP servers | claude.ai/download |
| 5 | **Git** | Version control | git-scm.com |
| 6 | **Node.js 18+** | For TypeScript MCP servers | nodejs.org |
| 7 | **MCP Inspector** | Debug MCP servers | npm package |

---

## 📘 PHASE 2: MCP CORE CONCEPTS (Week 3)

> **This is where you understand the protocol deeply**

### 2A: MCP Protocol Deep Dive

| # | Topic | Priority | Time |
|---|-------|----------|------|
| 1 | MCP Architecture (Host → Client → Server) | 🔴 | 2 hrs |
| 2 | **Resources** (what they are, how to define) | 🔴 | 2 hrs |
| 3 | **Tools** (what they are, how to define) | 🔴 | 2 hrs |
| 4 | **Prompts** (templates for interactions) | 🟡 | 1 hr |
| 5 | Transport Layer (stdio vs SSE/HTTP) | 🔴 | 2 hrs |
| 6 | Message Lifecycle (initialize → request → response) | 🔴 | 1 hr |
| 7 | Capabilities & Negotiation | 🟡 | 1 hr |
| 8 | Error Handling in MCP | 🟡 | 1 hr |
| 9 | Security Considerations | 🟡 | 1 hr |

### Transport Mechanisms:

```
┌─────────────────────────────────────────────────────────────┐
│                MCP TRANSPORT OPTIONS                        │
├──────────────┬──────────────────────────────────────────────┤
│              │                                              │
│  📟 STDIO    │ Communication via standard input/output      │
│  (Local)     │ → Server runs as a LOCAL process             │
│              │ → Host spawns the server as child process    │
│              │ → Fast, secure (no network)                  │
│              │ → Used for: local files, local DB, local tools│
│              │                                              │
│              │   Host ←──stdin/stdout──→ Server Process     │
│              │                                              │
├──────────────┼──────────────────────────────────────────────┤
│              │                                              │
│  🌐 HTTP+SSE │ Communication over HTTP (network)            │
│  (Remote)    │ → Server runs as a REMOTE web service        │
│              │ → Client connects via URL                    │
│              │ → SSE for server→client streaming            │
│              │ → HTTP POST for client→server requests       │
│              │ → Used for: cloud APIs, shared services      │
│              │                                              │
│              │   Host ←──HTTP/SSE──→ Remote Server          │
│              │                                              │
├──────────────┼──────────────────────────────────────────────┤
│              │                                              │
│  🔄 Streamable│ NEWEST transport (replacing SSE)            │
│  HTTP        │ → More flexible                              │
│              │ → Supports bidirectional streaming            │
│              │ → Will become the standard for remote        │
│              │                                              │
└──────────────┴──────────────────────────────────────────────┘
```

### MCP Message Flow:

```
┌──────────┐                              ┌──────────┐
│  CLIENT  │                              │  SERVER  │
└────┬─────┘                              └────┬─────┘
     │                                         │
     │  ──── initialize request ──────────►    │
     │  ◄─── initialize response ──────────    │
     │  ──── initialized notification ────►    │
     │                                         │
     │        🤝 Connection Established        │
     │                                         │
     │  ──── tools/list request ──────────►    │
     │  ◄─── tools/list response ──────────    │
     │        (returns available tools)        │
     │                                         │
     │  ──── tools/call request ──────────►    │
     │       {tool: "search", args: {...}}     │
     │  ◄─── tools/call response ──────────    │
     │       {result: "found 5 items"}         │
     │                                         │
     │  ──── resources/read request ──────►    │
     │  ◄─── resources/read response ──────    │
     │                                         │
     │         ... more interactions ...        │
     │                                         │
     │  ──── shutdown ────────────────────►    │
     ▼                                         ▼
```

---

## 📕 PHASE 3: BUILD YOUR FIRST MCP SERVER (Week 4-5)

> **This is where the real learning happens — by BUILDING**

### 3A: Hello World MCP Server

#### 💻 Step-by-Step: Your First MCP Server (Python)

```bash
# ──── STEP 0: Project Setup ────
# Using 'uv' (recommended by Anthropic)

# Install uv if you haven't
pip install uv

# Create project
uv init my-first-mcp-server
cd my-first-mcp-server

# Add MCP SDK dependency
uv add "mcp[cli]"
```

```python
# ════════════════════════════════════════════════════════
#  server.py — YOUR FIRST MCP SERVER
#  A simple server that provides weather + calculator tools
# ════════════════════════════════════════════════════════

from mcp.server.fastmcp import FastMCP

# Create server instance
mcp = FastMCP("MyFirstServer")

# ──── TOOL 1: Simple Calculator ────
@mcp.tool()
def add(a: float, b: float) -> float:
    """Add two numbers together.
    
    Args:
        a: First number
        b: Second number
    
    Returns:
        Sum of the two numbers
    """
    return a + b

@mcp.tool()
def multiply(a: float, b: float) -> float:
    """Multiply two numbers.
    
    Args:
        a: First number
        b: Second number
    
    Returns:
        Product of the two numbers
    """
    return a * b

# ──── TOOL 2: CGPA Calculator ────
@mcp.tool()
def calculate_cgpa(semester_gpas: list[float]) -> dict:
    """Calculate CGPA from semester GPAs.
    
    Args:
        semester_gpas: List of GPA values for each semester
    
    Returns:
        Dictionary with CGPA and analysis
    """
    if not semester_gpas:
        return {"error": "No GPAs provided"}
    
    cgpa = sum(semester_gpas) / len(semester_gpas)
    
    # Determine category
    if cgpa >= 9.0:
        category = "Outstanding 🌟"
    elif cgpa >= 8.0:
        category = "Excellent 🎯"
    elif cgpa >= 7.0:
        category = "Good 👍"
    elif cgpa >= 6.0:
        category = "Average 📊"
    else:
        category = "Needs Improvement 📈"
    
    return {
        "cgpa": round(cgpa, 2),
        "total_semesters": len(semester_gpas),
        "highest": max(semester_gpas),
        "lowest": min(semester_gpas),
        "category": category
    }

# ──── RESOURCE: Static Info ────
@mcp.resource("info://about")
def get_about() -> str:
    """Returns information about this server."""
    return "This is Nilesh's first MCP server! Built at MMMUT Gorakhpur."

# ──── RESOURCE: Dynamic (with URI template) ────
@mcp.resource("student://cgpa/{student_id}")
def get_student_cgpa(student_id: str) -> str:
    """Get CGPA for a specific student.
    
    Args:
        student_id: The student's ID number
    """
    # In real app, this would query a database
    students = {
        "2021001": "Nilesh - CGPA: 7.67",
        "2021002": "Rahul - CGPA: 8.23",
        "2021003": "Priya - CGPA: 9.01"
    }
    return students.get(student_id, f"Student {student_id} not found")

# ──── PROMPT: Template ────
@mcp.prompt()
def analyze_performance(student_name: str, cgpa: float) -> str:
    """Generate a prompt to analyze student performance.
    
    Args:
        student_name: Name of the student
        cgpa: Current CGPA
    """
    return f"""Please analyze the academic performance of {student_name} 
    who has a CGPA of {cgpa}. 
    
    Provide:
    1. Assessment of current standing
    2. Areas of improvement
    3. Realistic target for next semester
    4. Specific study strategies
    
    Be honest and practical, keeping in mind Indian placement standards."""

# ──── Run the server ────
if __name__ == "__main__":
    mcp.run()
```

### 3B: Connect to Claude Desktop

```json
// claude_desktop_config.json
// Location:
//   macOS: ~/Library/Application Support/Claude/claude_desktop_config.json
//   Windows: %APPDATA%\Claude\claude_desktop_config.json
//   Linux: ~/.config/Claude/claude_desktop_config.json

{
  "mcpServers": {
    "my-first-server": {
      "command": "uv",
      "args": [
        "--directory",
        "/absolute/path/to/my-first-mcp-server",
        "run",
        "server.py"
      ]
    }
  }
}
```

```
After saving this config:
1. Restart Claude Desktop
2. Look for the 🔌 (plug) icon or 🔧 (tools) icon
3. You should see your tools listed!
4. Ask Claude: "Calculate my CGPA for semesters: 7.2, 7.5, 7.8, 7.4, 7.9, 8.0, 7.7"
5. Claude will USE YOUR TOOL to calculate! 🎉
```

### 3C: Test with MCP Inspector

```bash
# MCP Inspector — Debug tool for MCP servers
npx @modelcontextprotocol/inspector uv run server.py

# Opens a web UI where you can:
# → See all registered tools, resources, prompts
# → Call tools manually with test inputs
# → See raw JSON-RPC messages
# → Debug errors
```

### 3D: Graduated Project Ideas for Phase 3

```
┌─────┬────────────────────────────────┬──────────┬───────────────────────┐
│  #  │ Project                        │ Level    │ What You Learn        │
├─────┼────────────────────────────────┼──────────┼───────────────────────┤
│  1  │ Calculator + Unit Converter    │ ⭐       │ Basic tools           │
│  2  │ File System Browser            │ ⭐⭐     │ Resources + file I/O  │
│  3  │ SQLite Database Query Server   │ ⭐⭐     │ DB + dynamic tools    │
│  4  │ Todo List Manager              │ ⭐⭐     │ CRUD operations       │
│  5  │ Note Taking App                │ ⭐⭐     │ Resources + state     │
└─────┴────────────────────────────────┴──────────┴───────────────────────┘
```

---

## 📙 PHASE 4: ADVANCED MCP SERVERS (Week 6-8)

> **Now you build REAL, useful MCP servers**

### 4A: Advanced Topics

| # | Topic | Priority | Time |
|---|-------|----------|------|
| 1 | **Database Integration** (SQLite, PostgreSQL) | 🔴 | 4 hrs |
| 2 | **External API Integration** (REST APIs) | 🔴 | 4 hrs |
| 3 | **Web Scraping Server** (BeautifulSoup/httpx) | 🟡 | 3 hrs |
| 4 | **Authentication & Security** | 🔴 | 3 hrs |
| 5 | Error Handling & Logging | 🔴 | 2 hrs |
| 6 | Streaming Responses | 🟡 | 2 hrs |
| 7 | Multi-tool Coordination | 🟡 | 2 hrs |
| 8 | **Remote MCP Servers (HTTP+SSE)** | 🔴 | 4 hrs |
| 9 | Testing MCP Servers | 🔴 | 3 hrs |
| 10 | Packaging & Distribution | 🟡 | 2 hrs |

### 💻 Example: Database MCP Server (Real-World Useful)

```python
# ════════════════════════════════════════════════════════
#  database_server.py — Query any SQLite database via AI
# ════════════════════════════════════════════════════════

import sqlite3
from mcp.server.fastmcp import FastMCP
from contextlib import closing

mcp = FastMCP("DatabaseExplorer")

DB_PATH = "college.db"

def get_connection():
    """Get database connection with row factory."""
    conn = sqlite3.connect(DB_PATH)
    conn.row_factory = sqlite3.Row
    return conn

# ──── Setup: Create sample database ────
def setup_database():
    """Create sample tables for demo."""
    conn = get_connection()
    cursor = conn.cursor()
    
    cursor.executescript("""
        CREATE TABLE IF NOT EXISTS students (
            id INTEGER PRIMARY KEY,
            name TEXT NOT NULL,
            branch TEXT NOT NULL,
            semester INTEGER,
            cgpa REAL,
            placement_status TEXT DEFAULT 'not_placed'
        );
        
        CREATE TABLE IF NOT EXISTS companies (
            id INTEGER PRIMARY KEY,
            name TEXT NOT NULL,
            type TEXT,  -- 'service' or 'product'
            ctc_lpa REAL,
            min_cgpa REAL
        );
        
        INSERT OR IGNORE INTO students VALUES
        (1, 'Nilesh', 'CSE', 8, 7.67, 'not_placed'),
        (2, 'Priya', 'CSE', 8, 9.01, 'placed'),
        (3, 'Rahul', 'IT', 6, 6.5, 'not_placed'),
        (4, 'Sneha', 'CSE', 8, 8.45, 'placed'),
        (5, 'Amit', 'ECE', 8, 7.2, 'not_placed');
        
        INSERT OR IGNORE INTO companies VALUES
        (1, 'TCS', 'service', 3.5, 6.0),
        (2, 'Infosys', 'service', 3.6, 6.0),
        (3, 'Amazon', 'product', 26.0, 7.0),
        (4, 'Google', 'product', 35.0, 8.0),
        (5, 'Microsoft', 'product', 42.0, 7.5);
    """)
    conn.commit()
    conn.close()

setup_database()

# ──── TOOL: List all tables ────
@mcp.tool()
def list_tables() -> list[str]:
    """List all tables in the database."""
    with closing(get_connection()) as conn:
        cursor = conn.cursor()
        cursor.execute(
            "SELECT name FROM sqlite_master WHERE type='table'"
        )
        return [row[0] for row in cursor.fetchall()]

# ──── TOOL: Describe table schema ────
@mcp.tool()
def describe_table(table_name: str) -> list[dict]:
    """Get the schema (columns and types) of a table.
    
    Args:
        table_name: Name of the table to describe
    """
    with closing(get_connection()) as conn:
        cursor = conn.cursor()
        cursor.execute(f"PRAGMA table_info({table_name})")
        columns = cursor.fetchall()
        return [
            {
                "name": col[1],
                "type": col[2],
                "nullable": not col[3],
                "primary_key": bool(col[5])
            }
            for col in columns
        ]

# ──── TOOL: Run SELECT queries (read-only for safety!) ────
@mcp.tool()
def query_database(sql_query: str) -> list[dict]:
    """Execute a READ-ONLY SQL query on the database.
    
    Only SELECT queries are allowed for safety.
    
    Args:
        sql_query: SQL SELECT query to execute
    """
    # Security: Only allow SELECT
    if not sql_query.strip().upper().startswith("SELECT"):
        return [{"error": "Only SELECT queries are allowed!"}]
    
    try:
        with closing(get_connection()) as conn:
            cursor = conn.cursor()
            cursor.execute(sql_query)
            columns = [desc[0] for desc in cursor.description]
            rows = cursor.fetchall()
            return [dict(zip(columns, row)) for row in rows]
    except Exception as e:
        return [{"error": str(e)}]

# ──── TOOL: Get placement-eligible students ────
@mcp.tool()
def get_eligible_students(company_name: str) -> dict:
    """Find students eligible for a specific company based on CGPA.
    
    Args:
        company_name: Name of the company to check eligibility for
    """
    with closing(get_connection()) as conn:
        cursor = conn.cursor()
        
        # Get company details
        cursor.execute(
            "SELECT * FROM companies WHERE name = ?", 
            (company_name,)
        )
        company = cursor.fetchone()
        
        if not company:
            return {"error": f"Company '{company_name}' not found"}
        
        # Find eligible students
        cursor.execute(
            """SELECT name, branch, cgpa 
               FROM students 
               WHERE cgpa >= ? AND placement_status = 'not_placed'
               ORDER BY cgpa DESC""",
            (company['min_cgpa'],)
        )
        eligible = [dict(row) for row in cursor.fetchall()]
        
        return {
            "company": company_name,
            "type": company['type'],
            "ctc_lpa": company['ctc_lpa'],
            "min_cgpa_required": company['min_cgpa'],
            "eligible_students": eligible,
            "total_eligible": len(eligible)
        }

# ──── RESOURCE: Database summary ────
@mcp.resource("db://summary")
def database_summary() -> str:
    """Get a summary of the database."""
    with closing(get_connection()) as conn:
        cursor = conn.cursor()
        
        cursor.execute("SELECT COUNT(*) FROM students")
        student_count = cursor.fetchone()[0]
        
        cursor.execute("SELECT COUNT(*) FROM companies")
        company_count = cursor.fetchone()[0]
        
        cursor.execute("SELECT AVG(cgpa) FROM students")
        avg_cgpa = cursor.fetchone()[0]
        
        return f"""Database Summary:
        - Students: {student_count}
        - Companies: {company_count}
        - Average CGPA: {avg_cgpa:.2f}
        - Tables: students, companies"""

if __name__ == "__main__":
    mcp.run()
```

### 💻 Example: GitHub Integration MCP Server

```python
# ════════════════════════════════════════════════════════
#  github_server.py — Interact with GitHub via AI
# ════════════════════════════════════════════════════════

import httpx
from mcp.server.fastmcp import FastMCP
import os

mcp = FastMCP("GitHubHelper")

GITHUB_TOKEN = os.environ.get("GITHUB_TOKEN", "")
HEADERS = {
    "Authorization": f"token {GITHUB_TOKEN}",
    "Accept": "application/vnd.github.v3+json"
}
BASE_URL = "https://api.github.com"

@mcp.tool()
async def get_repo_info(owner: str, repo: str) -> dict:
    """Get information about a GitHub repository.
    
    Args:
        owner: Repository owner (username or org)
        repo: Repository name
    """
    async with httpx.AsyncClient() as client:
        response = await client.get(
            f"{BASE_URL}/repos/{owner}/{repo}",
            headers=HEADERS
        )
        
        if response.status_code != 200:
            return {"error": f"Failed: {response.status_code}"}
        
        data = response.json()
        return {
            "name": data["full_name"],
            "description": data.get("description", "No description"),
            "stars": data["stargazers_count"],
            "forks": data["forks_count"],
            "language": data.get("language", "Unknown"),
            "open_issues": data["open_issues_count"],
            "created": data["created_at"],
            "last_updated": data["updated_at"],
            "url": data["html_url"]
        }

@mcp.tool()
async def search_repos(
    query: str, 
    language: str = "", 
    sort: str = "stars",
    limit: int = 5
) -> list[dict]:
    """Search GitHub repositories.
    
    Args:
        query: Search query
        language: Filter by programming language
        sort: Sort by 'stars', 'forks', or 'updated'
        limit: Number of results (max 10)
    """
    search_query = query
    if language:
        search_query += f" language:{language}"
    
    async with httpx.AsyncClient() as client:
        response = await client.get(
            f"{BASE_URL}/search/repositories",
            params={
                "q": search_query,
                "sort": sort,
                "per_page": min(limit, 10)
            },
            headers=HEADERS
        )
        
        data = response.json()
        return [
            {
                "name": repo["full_name"],
                "stars": repo["stargazers_count"],
                "description": repo.get("description", "")[:100],
                "url": repo["html_url"]
            }
            for repo in data.get("items", [])
        ]

@mcp.tool()
async def list_issues(
    owner: str, 
    repo: str, 
    state: str = "open",
    limit: int = 10
) -> list[dict]:
    """List issues for a repository.
    
    Args:
        owner: Repository owner
        repo: Repository name
        state: 'open', 'closed', or 'all'
        limit: Number of issues to return
    """
    async with httpx.AsyncClient() as client:
        response = await client.get(
            f"{BASE_URL}/repos/{owner}/{repo}/issues",
            params={"state": state, "per_page": limit},
            headers=HEADERS
        )
        
        return [
            {
                "number": issue["number"],
                "title": issue["title"],
                "state": issue["state"],
                "author": issue["user"]["login"],
                "labels": [l["name"] for l in issue["labels"]],
                "created": issue["created_at"],
                "url": issue["html_url"]
            }
            for issue in response.json()
            if "pull_request" not in issue  # Exclude PRs
        ]

@mcp.tool()
async def create_issue(
    owner: str,
    repo: str,
    title: str,
    body: str,
    labels: list[str] = []
) -> dict:
    """Create a new issue in a GitHub repository.
    
    Args:
        owner: Repository owner
        repo: Repository name
        title: Issue title
        body: Issue description (supports markdown)
        labels: List of label names to apply
    """
    async with httpx.AsyncClient() as client:
        response = await client.post(
            f"{BASE_URL}/repos/{owner}/{repo}/issues",
            headers=HEADERS,
            json={
                "title": title,
                "body": body,
                "labels": labels
            }
        )
        
        if response.status_code == 201:
            data = response.json()
            return {
                "success": True,
                "issue_number": data["number"],
                "url": data["html_url"]
            }
        else:
            return {
                "success": False,
                "error": response.text
            }

if __name__ == "__main__":
    mcp.run()
```

### 4B: Advanced Project Ideas

```
┌─────┬───────────────────────────────────────┬──────────┬────────────────────┐
│  #  │ Project                               │ Level    │ Impressive Because │
├─────┼───────────────────────────────────────┼──────────┼────────────────────┤
│  1  │ 🗄️ PostgreSQL Database Explorer       │ ⭐⭐     │ Real DB integration│
│  2  │ 📧 Email Manager (Gmail API)           │ ⭐⭐     │ OAuth + real use   │
│  3  │ 📊 CSV/Excel Analyzer                  │ ⭐⭐     │ Data skills        │
│  4  │ 🔍 Web Scraper (any website)           │ ⭐⭐     │ Practical tool     │
│  5  │ 📝 Notion/Google Docs Integration      │ ⭐⭐⭐   │ Productivity tool  │
│  6  │ 🐳 Docker Container Manager            │ ⭐⭐⭐   │ DevOps skills      │
│  7  │ 📡 IoT Sensor Data Server              │ ⭐⭐⭐   │ IoT + AI           │
│  8  │ 🏫 College ERP Integration             │ ⭐⭐⭐   │ Solves real problem│
│  9  │ 💹 Stock Market Data Server            │ ⭐⭐⭐   │ Finance + AI       │
│ 10  │ 🤖 Multi-Agent Coordinator             │ ⭐⭐⭐⭐ │ Cutting-edge AI    │
└─────┴───────────────────────────────────────┴──────────┴────────────────────┘
```

---

## 📗 PHASE 5: PORTFOLIO, OPEN SOURCE & CAREER (Week 9-10)

### 5A: Build Your MCP Portfolio

```
┌──────────────────────────────────────────────────────────────┐
│  YOUR MCP PORTFOLIO SHOULD INCLUDE:                          │
├──────────────────────────────────────────────────────────────┤
│                                                              │
│  📦 3-5 MCP Servers on GitHub                                │
│     → Each with excellent README                             │
│     → Demo GIF/video showing it in action                    │
│     → Clean code with comments                               │
│     → Proper error handling                                  │
│                                                              │
│  📝 1 Blog Post / Tutorial                                   │
│     → "How I built an MCP server for X"                      │
│     → Post on Dev.to, Hashnode, or Medium                    │
│     → Share on LinkedIn & Twitter                            │
│                                                              │
│  🎥 1 Demo Video (optional but powerful)                     │
│     → 2-3 minute walkthrough                                 │
│     → Show the AI using your tools in real-time              │
│                                                              │
│  🌟 Contribute to Official MCP Ecosystem                     │
│     → Submit server to awesome-mcp-servers list              │
│     → Fix bugs in MCP SDK                                    │
│     → Answer questions in MCP community                      │
│                                                              │
└──────────────────────────────────────────────────────────────┘
```

### 5B: GitHub README Template for MCP Server

```markdown
# 🔌 [Your Server Name] MCP Server

> A brief one-line description of what this does

![Demo](demo.gif)

## 🎯 What This Does

- Tool 1: Description
- Tool 2: Description  
- Resource 1: Description

## 🚀 Quick Start

### Prerequisites
- Python 3.10+
- uv package manager

### Installation

\```bash
git clone https://github.com/nilesh/your-mcp-server
cd your-mcp-server
uv install
\```

### Connect to Claude Desktop

Add to your `claude_desktop_config.json`:

\```json
{
  "mcpServers": {
    "your-server": {
      "command": "uv",
      "args": ["--directory", "/path/to/server", "run", "server.py"]
    }
  }
}
\```

## 🔧 Available Tools

| Tool | Description | Parameters |
|------|-------------|------------|
| `tool_name` | What it does | `param1`, `param2` |

## 📦 Available Resources

| URI | Description |
|-----|-------------|
| `resource://name` | What data it provides |

## 🏗️ Architecture

\```
[Your architecture diagram]
\```

## 📄 License

MIT
```

### 5C: Where MCP Fits in Your Career

```
┌──────────────────────────────────────────────────────────────┐
│         MCP SKILL → CAREER OPPORTUNITIES                     │
├──────────────────────────────────────────────────────────────┤
│                                                              │
│  🎯 JOB ROLES WHERE MCP IS VALUABLE:                        │
│                                                              │
│  → AI/ML Engineer (building AI-powered applications)         │
│  → AI Platform Engineer (infra for AI tools)                 │
│  → Developer Tools Engineer (at companies like Cursor, Replit)│
│  → Full-Stack Developer (AI-integrated apps)                 │
│  → DevOps/MLOps (AI deployment pipelines)                    │
│  → Startup Founder (AI product development)                  │
│                                                              │
│  💰 SALARY IMPACT:                                           │
│  → MCP alone won't get you a job                             │
│  → But MCP + Python + AI fundamentals = STRONG profile       │
│  → Companies building AI products WILL value this            │
│  → It's a differentiator, not a standalone skill             │
│                                                              │
│  🏢 COMPANIES USING MCP (as of 2025):                        │
│  → Anthropic (creators)                                      │
│  → Cursor (AI code editor)                                   │
│  → Windsurf (Codeium)                                        │
│  → Sourcegraph                                               │
│  → Replit                                                    │
│  → JetBrains                                                 │
│  → Zed (editor)                                              │
│  → And growing rapidly...                                    │
│                                                              │
└──────────────────────────────────────────────────────────────┘
```

---

## 📊 COMPLETE WEEK-BY-WEEK TIMELINE

```
╔════════════════════════════════════════════════════════════════════════╗
║ WEEK │ PHASE               │ KEY DELIVERABLE                         ║
╠════════════════════════════════════════════════════════════════════════╣
║  1   │ Python Prerequisites│ Async/await + decorators + type hints   ║
║      │                     │ mastered                                 ║
║  2   │ LLM/AI Foundations  │ Understand function calling & agents    ║
║      │                     │ Claude Desktop installed                 ║
║  3   │ MCP Core Concepts   │ Can explain architecture, 3 primitives ║
║      │                     │ Transport mechanisms understood          ║
║  4   │ First MCP Server    │ Calculator/utility server connected     ║
║      │                     │ to Claude Desktop ✅                     ║
║  5   │ Second Server       │ Database explorer server working        ║
║      │                     │ MCP Inspector used for debugging        ║
║  6   │ API Integration     │ GitHub/Weather API MCP server           ║
║      │                     │ External API patterns mastered          ║
║  7   │ Advanced Server     │ Complex server with auth, error         ║
║      │                     │ handling, multiple tools                 ║
║  8   │ Remote Server       │ HTTP+SSE transport, deployable server   ║
║      │                     │ Testing framework set up                 ║
║  9   │ Portfolio Project   │ 1 polished, deployed MCP server         ║
║      │                     │ Excellent GitHub README                  ║
║ 10   │ Open Source +       │ Published server, blog post written     ║
║      │ Career              │ LinkedIn updated, contributions made     ║
╚════════════════════════════════════════════════════════════════════════╝
```

---

## 📚 BEST RESOURCES FOR MCP

### 🔴 Official (Start Here):
| Resource | Link | What |
|----------|------|------|
| 📖 **MCP Official Docs** | modelcontextprotocol.io | THE primary resource |
| 📖 **MCP Specification** | spec.modelcontextprotocol.io | Detailed protocol spec |
| 💻 **MCP Python SDK** | github.com/modelcontextprotocol/python-sdk | Python library |
| 💻 **MCP TypeScript SDK** | github.com/modelcontextprotocol/typescript-sdk | TS library |
| 🔧 **MCP Inspector** | github.com/modelcontextprotocol/inspector | Debugging tool |
| 📦 **Official MCP Servers** | github.com/modelcontextprotocol/servers | Reference implementations |

### 🟡 Learning Resources:
| Resource | Type | Best For |
|----------|------|----------|
| 🎥 **Anthropic's MCP Announcement Blog** | Article | Understanding WHY |
| 🎥 **"MCP Explained" videos on YouTube** | Video | Visual learners |
| 📦 **awesome-mcp-servers (GitHub)** | Repo | See what others built |
| 🎥 **AI Jason — MCP Tutorial** | YouTube | Practical walkthrough |
| 🎥 **WorldofAI — MCP Videos** | YouTube | Beginner friendly |
| 💬 **MCP Discord Community** | Community | Ask questions, get help |

### 🟢 Practice & Explore:
| Resource | What |
|----------|------|
| **Cursor IDE** | Best MCP client experience (besides Claude Desktop) |
| **Smithery.ai** | Registry of MCP servers — see what exists |
| **Glama.ai** | Another MCP server directory |
| **mcp.run** | Run MCP servers easily |

---

## ⚡ MCP vs ALTERNATIVES — Important Context

```
┌─────────────────┬──────────────────────────────────────────────────┐
│ Approach         │ Description                                     │
├─────────────────┼──────────────────────────────────────────────────┤
│ MCP             │ Open protocol, standardized, growing ecosystem   │
│                 │ Client-server model, language agnostic            │
│                 │ ✅ Best for: universal tool connectivity          │
├─────────────────┼──────────────────────────────────────────────────┤
│ OpenAI Function │ OpenAI-specific, simpler but locked-in           │
│ Calling         │ ✅ Best for: simple OpenAI-only apps             │
├─────────────────┼──────────────────────────────────────────────────┤
│ LangChain Tools │ Python framework, lots of integrations           │
│                 │ ✅ Best for: quick prototyping                    │
├─────────────────┼──────────────────────────────────────────────────┤
│ Custom APIs     │ Build your own, full control                     │
│                 │ ✅ Best for: specific use cases                   │
├─────────────────┼──────────────────────────────────────────────────┤
│ 🏆 VERDICT      │ MCP is becoming the STANDARD.                   │
│                 │ Learn MCP + know alternatives = best position    │
└─────────────────┴──────────────────────────────────────────────────┘
```

---

## 🎯 DAILY PRACTICE STRUCTURE

```
┌──────────────────────────────────────────────────────────────┐
│  DAILY MCP ROUTINE (1.5-2 hours/day)                         │
├──────────────────────────────────────────────────────────────┤
│                                                              │
│  📖 20 min — Read MCP docs / a section of the spec          │
│  💻 60 min — Build / modify an MCP server                    │
│  🧪 20 min — Test with Claude Desktop or Inspector           │
│  📝 10 min — Document what you built (README / notes)        │
│                                                              │
│  WEEKEND BONUS:                                              │
│  🏗️ 3 hrs — Work on portfolio MCP server project            │
│  🌟 1 hr — Explore other people's MCP servers on GitHub      │
│  ✍️ 30 min — Write about what you learned (blog/LinkedIn)    │
│                                                              │
└──────────────────────────────────────────────────────────────┘
```

---

## 🧪 SKILLS CHECKLIST — Track Your Progress

```
PHASE 1: Prerequisites
  □ Python async/await — can write async functions
  □ Decorators — can create and use them
  □ Type hints — comfortable with typing module
  □ JSON — can parse, create, validate
  □ Understand what LLM function calling is
  □ Claude Desktop installed and working

PHASE 2: Core Concepts  
  □ Can explain MCP architecture (Host/Client/Server)
  □ Understand Resources vs Tools vs Prompts
  □ Know stdio vs HTTP+SSE transport
  □ Understand JSON-RPC message format
  □ Can read the MCP specification

PHASE 3: First Servers
  □ Built and connected a basic MCP server
  □ Created custom tools with proper schemas
  □ Created resource endpoints
  □ Used MCP Inspector for debugging
  □ Server works with Claude Desktop

PHASE 4: Advanced
  □ Built database integration server
  □ Built external API integration server
  □ Implemented proper error handling
  □ Built a remote (HTTP) MCP server
  □ Written tests for MCP server

PHASE 5: Portfolio
  □ 3+ MCP servers on GitHub with good READMEs
  □ 1 polished portfolio project
  □ Blog post / tutorial published
  □ Contributed to MCP ecosystem
  □ Can explain MCP in an interview (2-min pitch)
```

---

## 💼 HOW TO TALK ABOUT MCP IN INTERVIEWS

```
┌──────────────────────────────────────────────────────────────┐
│  INTERVIEW SCRIPT (2-minute pitch):                          │
├──────────────────────────────────────────────────────────────┤
│                                                              │
│  "I've been working with Model Context Protocol, which is    │
│  an open standard by Anthropic for connecting AI models      │
│  to external tools and data sources.                         │
│                                                              │
│  Think of it as USB-C for AI — one universal interface       │
│  for any AI application to access databases, APIs,           │
│  file systems, and more.                                     │
│                                                              │
│  I built [X] MCP servers, including one that lets AI         │
│  query our college database to find placement-eligible       │
│  students. The AI can automatically check which students     │
│  meet a company's CGPA criteria, analyze trends, and         │
│  generate reports — all through natural language.            │
│                                                              │
│  I used Python with async programming, the official MCP      │
│  SDK, and deployed it with both stdio and HTTP transports.   │
│  It's on my GitHub with documentation and tests.             │
│                                                              │
│  I'm excited about this because AI applications are          │
│  moving from 'just text generation' to 'actually doing       │
│  things' — and MCP is the infrastructure making that         │
│  possible."                                                  │
│                                                              │
│  EXPECTED FOLLOW-UP QUESTIONS:                               │
│  Q: How is MCP different from regular API calls?             │
│  Q: What's the security model?                               │
│  Q: How does it scale?                                       │
│  Q: Can you use it with models other than Claude?            │
│  Q: What's JSON-RPC and why does MCP use it?                 │
│                                                              │
└──────────────────────────────────────────────────────────────┘
```

---

## ⚠️ HONEST ASSESSMENT

```
┌──────────────────────────────────────────────────────────────┐
│  🟢 LEARN MCP IF:                                            │
│  → You're interested in AI/LLM application development       │
│  → You want to stand out with cutting-edge skills            │
│  → You enjoy building developer tools                        │
│  → You want to contribute to open source in AI space         │
│  → You're targeting AI startups or product companies         │
│                                                              │
│  🔴 MAYBE SKIP MCP IF:                                       │
│  → Your priority is cracking DSA rounds (do DSA first)       │
│  → You're targeting pure service companies (TCS, Infosys)    │
│  → You don't know Python well yet (learn Python first)       │
│  → You have exams in < 2 weeks (focus on exams)              │
│  → You want ML/Data Science (learn ML fundamentals first)    │
│                                                              │
│  💡 BEST COMBO:                                               │
│  → DSA (for interviews) + MCP (for differentiation)          │
│  → Python + AI basics + MCP = very strong profile            │
│  → MCP project on resume = conversation starter              │
└──────────────────────────────────────────────────────────────┘
```

---

## ❓ Next Steps — What Do You Want to Do?

| Command | What Happens |
|---------|-------------|
| `"TEACH MCP tools"` | Deep dive into MCP Tools with full code |
| `"TEACH MCP resources"` | Deep dive into MCP Resources |
| `"PROJECT MCP"` | I'll help you build a complete MCP server from scratch |
| `"LEARN async Python"` | Master async/await (MCP prerequisite) |
| `"COMPARE MCP vs LangChain"` | Detailed comparison |
| `"QUICK MCP setup"` | Just the setup commands, no explanation |
