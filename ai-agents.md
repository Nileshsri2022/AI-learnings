

# 🧭 ROADMAP: AI Agents — Complete Learning Path

---

> ⚠️ **Profile Note:** You haven't filled in your `[brackets]` yet. I'll deliver this roadmap generically for now. Fill in your profile details anytime and I'll **personalize** everything — pace, depth, resources, and priorities.

---

## 📍 Where AI Agents Sit in the Big Picture

```
Traditional Programming ➜ Machine Learning ➜ LLMs ➜ ✨ AI AGENTS ✨
                                                        ↑ YOU ARE HERE
```

**AI Agents** = LLMs that can **think, plan, and ACT** autonomously — they don't just generate text, they **use tools**, **remember context**, and **complete multi-step tasks** in the real world.

> 🧒 **ELI5:** Imagine ChatGPT, but instead of just answering, it can book your train ticket, search Google, run code, send emails, and query databases — **all on its own** by deciding what to do next. That's an AI Agent.

---

## 🗺️ FULL ROADMAP — 6 Phases

```
┌─────────────────────────────────────────────────────────────────┐
│                    AI AGENTS ROADMAP                            │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│  PHASE 0 ➜ Prerequisites (2-3 weeks)                           │
│     ↓                                                           │
│  PHASE 1 ➜ LLM Fundamentals (2-3 weeks)                       │
│     ↓                                                           │
│  PHASE 2 ➜ Prompt Engineering (1-2 weeks)                      │
│     ↓                                                           │
│  PHASE 3 ➜ AI Agents Core Concepts (2-3 weeks)                │
│     ↓                                                           │
│  PHASE 4 ➜ Building Agents (3-4 weeks)                         │
│     ↓                                                           │
│  PHASE 5 ➜ Advanced Topics (3-4 weeks)                         │
│     ↓                                                           │
│  PHASE 6 ➜ Production & Security (2-3 weeks)                   │
│                                                                 │
│  ⏱️ Total: ~16-22 weeks (4-5 months at 2 hrs/day)              │
└─────────────────────────────────────────────────────────────────┘
```

---

## PHASE 0: Prerequisites 🟢
**⏱️ 2-3 weeks | Priority: 🔴 CRITICAL — Don't skip**

You **cannot** build AI agents without these foundations.

| # | Topic | What to Learn | Priority | Est. Hours |
|---|-------|---------------|----------|------------|
| 1 | **Python (Intermediate+)** | OOP, async/await, decorators, type hints, virtual envs | 🔴 Critical | 15-20 hrs |
| 2 | **Basic Backend Development** | HTTP methods, request/response cycle, REST principles | 🔴 Critical | 8-10 hrs |
| 3 | **REST API Knowledge** | Making API calls, authentication (API keys, OAuth), JSON handling | 🔴 Critical | 6-8 hrs |
| 4 | **Git & Terminal** | Git workflow, GitHub repos, CLI basics | 🟡 Important | 4-5 hrs |
| 5 | **JSON & Data Formats** | Parsing, schemas, nested structures | 🟡 Important | 2-3 hrs |

### ✅ Checkpoint — You're ready when you can:
```python
# Write this comfortably:
import requests
import json

response = requests.post(
    "https://api.example.com/data",
    headers={"Authorization": "Bearer YOUR_KEY"},
    json={"query": "hello world"}
)
data = response.json()
print(data["result"])
```

### 📚 Resources — Phase 0
| Resource | Type | Link |
|----------|------|------|
| CodeWithHarry — Python Full Course (Hindi) | 🎥 YouTube | Free |
| FastAPI Tutorial | 📖 Docs | fastapi.tiangolo.com |
| freeCodeCamp — APIs for Beginners | 🎥 YouTube | Free |
| Git & GitHub Roadmap | 🗺️ Roadmap | roadmap.sh/git-github |

---

## PHASE 1: LLM Fundamentals 🧠
**⏱️ 2-3 weeks | Priority: 🔴 CRITICAL**

You need to understand **how LLMs work** before making them do things.

### 📗 1A: Transformer Models & LLMs
| # | Topic | What to Understand | Priority |
|---|-------|--------------------|----------|
| 1 | **What are Transformers?** | Attention mechanism (conceptual), encoder-decoder | 🔴 |
| 2 | **Tokenization** | How text → tokens, BPE, token limits, why "strawberry" is tricky | 🔴 |
| 3 | **Context Windows** | What fits in memory, 4K vs 128K context, why it matters | 🔴 |
| 4 | **Token-Based Pricing** | How API costs work, input vs output tokens, cost estimation | 🟡 |

### 📘 1B: Model Types & Ecosystem
| # | Topic | What to Understand | Priority |
|---|-------|--------------------|----------|
| 5 | **Closed-Weight Models** | GPT-4, Claude, Gemini — access via API only | 🔴 |
| 6 | **Open-Weight Models** | LLaMA, Mistral, Qwen — can download & run locally | 🔴 |
| 7 | **Model Families & Licences** | Which are free, commercial-use, restrictions | 🟡 |
| 8 | **Reasoning vs Standard Models** | GPT-4o vs o1/o3, Claude Sonnet vs Opus | 🟡 |
| 9 | **Streamed vs Unstreamed Responses** | Token-by-token vs complete response | 🟢 |

### 📕 1C: Generation Controls
| # | Topic | What It Does | Priority |
|---|-------|--------------|----------|
| 10 | **Temperature** | Controls randomness (0 = deterministic, 1 = creative) | 🔴 |
| 11 | **Top-p (Nucleus Sampling)** | Controls diversity of token selection | 🟡 |
| 12 | **Frequency Penalty** | Reduces word repetition | 🟢 |
| 13 | **Presence Penalty** | Encourages topic diversity | 🟢 |
| 14 | **Max Length / Stopping Criteria** | Control response length | 🟡 |

### 📘 1D: Key Concepts
| # | Topic | Priority |
|---|-------|----------|
| 15 | **Embeddings & Vector Search** | 🔴 — Foundational for RAG |
| 16 | **Basics of RAG** | 🔴 — Core agent pattern |
| 17 | **Fine-tuning vs Prompt Engineering** | 🟡 — Know the tradeoffs |
| 18 | **Pricing of Common Models** | 🟡 — Practical awareness |

### 💻 Hands-On — Phase 1
```python
# Make your first LLM API call (OpenAI example)
from openai import OpenAI

client = OpenAI(api_key="your-key-here")

response = client.chat.completions.create(
    model="gpt-4o-mini",         # affordable model
    temperature=0.7,              # some creativity
    max_tokens=500,
    messages=[
        {"role": "system", "content": "You are a helpful assistant."},
        {"role": "user", "content": "Explain AI agents in 3 lines."}
    ]
)

print(response.choices[0].message.content)
print(f"Tokens used: {response.usage.total_tokens}")
print(f"Cost: ~${response.usage.total_tokens * 0.00000015:.6f}")
```

### ✅ Checkpoint — You're ready when:
- [ ] You can explain tokenization to a friend
- [ ] You've made API calls to at least 2 different LLMs
- [ ] You understand why temperature=0 matters for agents
- [ ] You can estimate the cost of an API call
- [ ] You know the difference between open vs closed models

### 📚 Resources — Phase 1
| Resource | Type |
|----------|------|
| 3Blue1Brown — "But what is a GPT?" | 🎥 YouTube (Visual) |
| Andrej Karpathy — "Intro to LLMs" (1hr talk) | 🎥 YouTube (Deep) |
| OpenAI API Documentation | 📖 Official Docs |
| Anthropic Claude Docs | 📖 Official Docs |
| LiteLLM (call any model with same syntax) | 🛠️ Tool |

---

## PHASE 2: Prompt Engineering ✍️
**⏱️ 1-2 weeks | Priority: 🔴 CRITICAL**

Agents live and die by their prompts. **This is not optional.**

| # | Technique | What It Is | Use in Agents |
|---|-----------|-----------|---------------|
| 1 | **Be Specific** | "Extract the name and email" vs "parse this" | Tool instructions |
| 2 | **Provide Context** | System prompts, background info | Agent personality |
| 3 | **Use Technical Terms** | "Return valid JSON with keys: name, age" | Output parsing |
| 4 | **Few-Shot Examples** | Show 2-3 input→output examples | Consistent behavior |
| 5 | **Specify Format** | "Respond as JSON", "Use markdown table" | Structured output |
| 6 | **Chain-of-Thought** | "Think step by step before answering" | Reasoning tasks |
| 7 | **Iterate & Test** | A/B test prompts, track quality | Production tuning |

### 💻 Hands-On — Structured Output (Critical for Agents)
```python
# Agents NEED structured output — not free-form text
import json
from openai import OpenAI

client = OpenAI()

response = client.chat.completions.create(
    model="gpt-4o-mini",
    temperature=0,  # deterministic for agents!
    messages=[
        {"role": "system", "content": """You are a task planner. 
Given a user goal, output a JSON plan.
Format: {"steps": [{"action": "...", "tool": "...", "input": "..."}]}
Only output valid JSON. No explanation."""},
        {"role": "user", "content": "Find the weather in Delhi and send it to my email"}
    ]
)

plan = json.loads(response.choices[0].message.content)
print(json.dumps(plan, indent=2))
```

Expected output:
```json
{
  "steps": [
    {"action": "search_weather", "tool": "weather_api", "input": "Delhi"},
    {"action": "send_email", "tool": "email", "input": "weather results"}
  ]
}
```

### ✅ Checkpoint:
- [ ] You can write system prompts that produce consistent structured output
- [ ] You understand few-shot prompting
- [ ] You've experimented with Chain-of-Thought prompting

---

## PHASE 3: AI Agents — Core Concepts 🤖
**⏱️ 2-3 weeks | Priority: 🔴 CRITICAL**

This is the **heart** of the roadmap.

### 🧠 3A: What Are AI Agents?

```
┌──────────────────────────────────────────────────────┐
│                  THE AGENT LOOP                      │
│                                                      │
│   ┌──────────┐    ┌──────────┐    ┌──────────┐      │
│   │ PERCEIVE │───→│  REASON  │───→│   ACT    │      │
│   │ (Input)  │    │ (Plan)   │    │ (Tools)  │      │
│   └──────────┘    └──────────┘    └──────────┘      │
│        ↑                                │            │
│        │          ┌──────────┐          │            │
│        └──────────│ OBSERVE  │←─────────┘            │
│                   │(Reflect) │                       │
│                   └──────────┘                       │
│                                                      │
│   This loop repeats until the task is COMPLETE       │
└──────────────────────────────────────────────────────┘
```

| Step | What Happens | Example |
|------|-------------|---------|
| 1. **Perception** | Agent receives user input/goal | "Book me a train from Delhi to Mumbai tomorrow" |
| 2. **Reason & Plan** | LLM breaks the task into steps | Step 1: Search trains → Step 2: Compare prices → Step 3: Book cheapest |
| 3. **Act (Tool Use)** | Agent calls external tools/APIs | Calls IRCTC API to search trains |
| 4. **Observe & Reflect** | Agent evaluates tool output | "Found 5 trains. Rajdhani is cheapest at ₹1,200" |
| ↻ | **Loop repeats** until task is done | Proceeds to booking step |

### 🛠️ 3B: Tools / Actions

Tools are the **superpowers** you give your agent.

| Tool | What It Does | Example |
|------|-------------|---------|
| 🔍 **Web Search** | Search the internet | Google/Bing API, Tavily |
| 💻 **Code Execution** | Run Python/JS code | Execute calculations, data processing |
| 🗄️ **Database Queries** | Read/write to databases | SQL queries, MongoDB lookups |
| 🌐 **API Requests** | Call any external API | Weather, maps, payment gateways |
| 📧 **Email/Slack/SMS** | Send communications | Notifications, alerts |
| 📁 **File System** | Read/write files | Generate reports, parse documents |

#### Tool Definition Structure:
```python
# How a tool is defined for an LLM
tool_definition = {
    "name": "search_web",
    "description": "Search the internet for current information. Use when you need up-to-date facts.",
    "input_schema": {
        "type": "object",
        "properties": {
            "query": {
                "type": "string",
                "description": "The search query"
            },
            "num_results": {
                "type": "integer",
                "description": "Number of results to return",
                "default": 5
            }
        },
        "required": ["query"]
    }
}
```

### 🧠 3C: Agent Memory

```
┌─────────────────────────────────────────────────────┐
│                 AGENT MEMORY                        │
│                                                     │
│  ┌─────────────────┐   ┌─────────────────────────┐ │
│  │  SHORT-TERM     │   │  LONG-TERM              │ │
│  │  (Within Prompt) │   │  (Persistent Storage)   │ │
│  │                 │   │                         │ │
│  │  • Current      │   │  • Vector DB (Pinecone, │ │
│  │    conversation │   │    ChromaDB, Weaviate)  │ │
│  │  • Recent tool  │   │  • SQL Database         │ │
│  │    outputs      │   │  • User profile store   │ │
│  │  • Scratchpad   │   │  • Past interactions    │ │
│  │                 │   │  • Learned preferences  │ │
│  └─────────────────┘   └─────────────────────────┘ │
│                                                     │
│  Key Concepts:                                      │
│  • Episodic Memory = Specific past events           │
│  • Semantic Memory = General knowledge/facts        │
│  • Summarization = Compress old memories            │
│  • Forgetting = Remove irrelevant old memories      │
└─────────────────────────────────────────────────────┘
```

### 🏗️ 3D: Agent Architectures

| Architecture | How It Works | Best For | Difficulty |
|-------------|-------------|----------|------------|
| **ReAct** (Reason+Act) | Think → Act → Observe → Repeat | General-purpose agents | 🟢 Start here |
| **Chain-of-Thought (CoT)** | Step-by-step reasoning before acting | Complex reasoning tasks | 🟢 Easy |
| **RAG Agent** | Retrieve relevant docs → Generate answer | Knowledge-heavy tasks | 🟡 Medium |
| **Planner-Executor** | One LLM plans, another executes | Complex multi-step tasks | 🟡 Medium |
| **DAG Agents** | Parallel execution of independent steps | Speed-critical tasks | 🔴 Advanced |
| **Tree-of-Thought** | Explore multiple reasoning paths | Problems needing exploration | 🔴 Advanced |

### 💻 Hands-On — Build Your First Agent (from scratch!)
```python
"""
🤖 Simple ReAct Agent — No Framework, Pure Python
This agent can search the web and do math.
"""
import json
from openai import OpenAI

client = OpenAI()

# ── Define Tools ──
def search_web(query: str) -> str:
    """Simulate web search (replace with real API)"""
    fake_results = {
        "weather delhi": "Delhi: 42°C, Sunny, Humidity 25%",
        "population india": "India population: 1.44 billion (2024)",
    }
    for key, val in fake_results.items():
        if key in query.lower():
            return val
    return f"No results found for: {query}"

def calculator(expression: str) -> str:
    """Evaluate a math expression"""
    try:
        return str(eval(expression))  # ⚠️ Use safer eval in production
    except Exception as e:
        return f"Error: {e}"

# Map tool names to functions
TOOLS = {
    "search_web": search_web,
    "calculator": calculator,
}

TOOL_DESCRIPTIONS = """
Available tools:
1. search_web(query: str) - Search the internet for information
2. calculator(expression: str) - Evaluate math expressions

To use a tool, respond with JSON:
{"tool": "tool_name", "input": "tool_input"}

When you have the final answer, respond with:
{"answer": "your final answer"}
"""

def run_agent(user_goal: str, max_steps: int = 5):
    """The Agent Loop"""
    
    messages = [
        {"role": "system", "content": f"""You are an AI agent that solves tasks step by step.
{TOOL_DESCRIPTIONS}
Think carefully, use tools when needed, and provide a final answer."""},
        {"role": "user", "content": user_goal}
    ]
    
    print(f"\n🎯 Goal: {user_goal}\n{'='*50}")
    
    for step in range(max_steps):
        print(f"\n📍 Step {step + 1}:")
        
        # REASON — Ask LLM what to do
        response = client.chat.completions.create(
            model="gpt-4o-mini",
            temperature=0,
            messages=messages
        )
        
        reply = response.choices[0].message.content
        print(f"🧠 Agent thinks: {reply}")
        
        # Parse the response
        try:
            action = json.loads(reply)
        except json.JSONDecodeError:
            print("⚠️ Could not parse response, asking to retry")
            messages.append({"role": "assistant", "content": reply})
            messages.append({"role": "user", "content": "Please respond in valid JSON format."})
            continue
        
        # CHECK — Is it the final answer?
        if "answer" in action:
            print(f"\n✅ FINAL ANSWER: {action['answer']}")
            return action["answer"]
        
        # ACT — Execute the tool
        tool_name = action.get("tool")
        tool_input = action.get("input")
        
        if tool_name in TOOLS:
            result = TOOLS[tool_name](tool_input)
            print(f"🔧 Tool [{tool_name}] → {result}")
            
            # OBSERVE — Feed result back to agent
            messages.append({"role": "assistant", "content": reply})
            messages.append({"role": "user", "content": f"Tool result: {result}"})
        else:
            print(f"❌ Unknown tool: {tool_name}")
            messages.append({"role": "assistant", "content": reply})
            messages.append({"role": "user", "content": f"Tool '{tool_name}' not found. Available: {list(TOOLS.keys())}"})
    
    return "Max steps reached without answer."

# ── Run it! ──
run_agent("What is the weather in Delhi? Convert the temperature to Fahrenheit.")
```

### ✅ Checkpoint — Phase 3:
- [ ] You can explain the agent loop (Perceive → Reason → Act → Observe)
- [ ] You understand tool definitions with input/output schemas
- [ ] You know the difference between short-term and long-term memory
- [ ] You've built a basic agent from scratch (no framework)
- [ ] You can explain ReAct vs RAG vs Planner-Executor architectures

---

## PHASE 4: Building Agents — Frameworks & APIs 🏗️
**⏱️ 3-4 weeks | Priority: 🔴 CRITICAL**

Now move from scratch → production-grade tools.

### 📗 4A: LLM-Native Function Calling

| Provider | Feature | Priority |
|----------|---------|----------|
| **OpenAI Function Calling** | Native tool use in GPT models | 🔴 Learn first |
| **Anthropic Tool Use** | Claude's tool use system | 🔴 Learn this too |
| **Gemini Function Calling** | Google's implementation | 🟡 Good to know |
| **OpenAI Assistants API** | Pre-built agent infrastructure | 🟡 Useful shortcut |

```python
# OpenAI Function Calling Example
from openai import OpenAI
import json

client = OpenAI()

tools = [
    {
        "type": "function",
        "function": {
            "name": "get_weather",
            "description": "Get current weather for a city",
            "parameters": {
                "type": "object",
                "properties": {
                    "city": {"type": "string", "description": "City name"},
                    "unit": {"type": "string", "enum": ["celsius", "fahrenheit"]}
                },
                "required": ["city"]
            }
        }
    }
]

response = client.chat.completions.create(
    model="gpt-4o-mini",
    messages=[{"role": "user", "content": "What's the weather in Mumbai?"}],
    tools=tools,
    tool_choice="auto"
)

# The model decides to call the tool
tool_call = response.choices[0].message.tool_calls[0]
print(f"Model wants to call: {tool_call.function.name}")
print(f"With arguments: {tool_call.function.arguments}")
```

### 📘 4B: Model Context Protocol (MCP)

```
┌──────────────────────────────────────────────────────┐
│              MODEL CONTEXT PROTOCOL                  │
│                                                      │
│  ┌──────────┐     ┌──────────┐     ┌──────────────┐ │
│  │ MCP HOST │────→│MCP CLIENT│────→│ MCP SERVERS  │ │
│  │(Claude,  │     │(Manages  │     │(Provide      │ │
│  │ IDE,App) │     │connection│     │ tools, data, │ │
│  │          │     │   s)     │     │ capabilities)│ │
│  └──────────┘     └──────────┘     └──────────────┘ │
│                                                      │
│  Think of it as "USB-C for AI" — a universal         │
│  standard for connecting LLMs to external tools      │
│                                                      │
│  Deployment: Local Desktop | Remote / Cloud          │
└──────────────────────────────────────────────────────┘
```

| Learn | Priority |
|-------|----------|
| What MCP is and why it matters | 🟡 |
| Creating MCP Servers (core components) | 🟡 |
| Local vs Remote deployment | 🟢 |

### 📕 4C: Agent Frameworks

| Framework | Best For | Complexity | Priority |
|-----------|----------|------------|----------|
| **LangChain** | General-purpose, most popular | Medium | 🔴 Learn this |
| **LlamaIndex** | RAG-heavy applications | Medium | 🔴 If doing RAG |
| **CrewAI** | Multi-agent collaboration | Low-Medium | 🟡 Great for learning |
| **AutoGen** (Microsoft) | Multi-agent conversations | Medium | 🟡 Interesting |
| **Haystack** | Production NLP pipelines | Medium-High | 🟢 Enterprise use |
| **Smol Agents** (HuggingFace) | Lightweight, simple | Low | 🟢 Quick prototyping |

### 💻 Hands-On — LangChain Agent
```python
# pip install langchain langchain-openai tavily-python

from langchain_openai import ChatOpenAI
from langchain.agents import AgentExecutor, create_react_agent
from langchain.tools import tool
from langchain import hub

# Define custom tools
@tool
def multiply(a: int, b: int) -> int:
    """Multiply two numbers together."""
    return a * b

@tool
def search_college_info(college_name: str) -> str:
    """Search for information about an Indian engineering college."""
    # Simulated - replace with real data source
    data = {
        "IIT Bombay": "NIRF Rank 3, Avg package 25 LPA, CSE cutoff JEE Rank ~50",
        "NIT Trichy": "NIRF Rank 9, Avg package 14 LPA, CSE cutoff JEE Rank ~2000",
    }
    return data.get(college_name, f"No data found for {college_name}")

tools = [multiply, search_college_info]

# Create agent
llm = ChatOpenAI(model="gpt-4o-mini", temperature=0)
prompt = hub.pull("hwchase17/react")
agent = create_react_agent(llm, tools, prompt)
executor = AgentExecutor(agent=agent, tools=tools, verbose=True)

# Run!
result = executor.invoke({
    "input": "What's the average package at IIT Bombay? "
             "If a student gets 120% of that, how much would they earn?"
})
print(result["output"])
```

### 📗 4D: RAG (Retrieval-Augmented Generation) Agent

```
┌────────────────────────────────────────────────────┐
│                   RAG PIPELINE                     │
│                                                    │
│  📄 Documents                                      │
│    ↓                                               │
│  🔪 Chunking (split into smaller pieces)           │
│    ↓                                               │
│  🔢 Embedding (text → vector numbers)              │
│    ↓                                               │
│  💾 Vector DB (store embeddings)                    │
│    ↓  ↑ (similarity search)                        │
│  ❓ User Query → Embed → Search → Top K chunks     │
│    ↓                                               │
│  🧠 LLM (generate answer using retrieved chunks)   │
│    ↓                                               │
│  ✅ Answer (grounded in your documents)             │
└────────────────────────────────────────────────────┘
```

```python
# Simple RAG with ChromaDB
# pip install chromadb langchain-community

import chromadb
from langchain_openai import OpenAIEmbeddings, ChatOpenAI
from langchain_community.vectorstores import Chroma
from langchain.text_splitter import RecursiveCharacterTextSplitter

# 1. Your documents
documents = [
    "AI Agents can use tools to perform actions in the real world.",
    "ReAct architecture combines reasoning and acting in an interleaved manner.",
    "Vector databases store embeddings for fast similarity search.",
    "MCP (Model Context Protocol) provides a universal standard for tool use.",
]

# 2. Split into chunks (for larger docs)
splitter = RecursiveCharacterTextSplitter(chunk_size=200, chunk_overlap=20)
chunks = splitter.create_documents(documents)

# 3. Embed & Store
vectorstore = Chroma.from_documents(chunks, OpenAIEmbeddings())

# 4. Query
query = "How do AI agents interact with external tools?"
results = vectorstore.similarity_search(query, k=2)

# 5. Generate answer with context
llm = ChatOpenAI(model="gpt-4o-mini")
context = "\n".join([r.page_content for r in results])

answer = llm.invoke(
    f"Based on this context:\n{context}\n\nAnswer: {query}"
)
print(answer.content)
```

### ✅ Checkpoint — Phase 4:
- [ ] You've used OpenAI Function Calling successfully
- [ ] You've built an agent with LangChain or CrewAI
- [ ] You've built a basic RAG pipeline
- [ ] You understand MCP conceptually
- [ ] You can choose the right framework for a given use case

### 🏋️ Project Ideas — Phase 4
| Level | Project | Tech |
|-------|---------|------|
| 🟢 Beginner | **Personal Research Agent** — Ask questions, it searches web + your notes | LangChain + Tavily + ChromaDB |
| 🟡 Medium | **Code Review Agent** — Paste code, agent analyzes, suggests improvements, runs tests | OpenAI + Code Execution tool |
| 🔴 Advanced | **Multi-Agent Customer Support** — Router agent assigns to specialist agents | CrewAI / AutoGen |

---

## PHASE 5: Advanced Topics ⚡
**⏱️ 3-4 weeks | Priority: 🟡 IMPORTANT**

| # | Topic | What to Learn | Priority |
|---|-------|---------------|----------|
| 1 | **Multi-Agent Systems** | Agents collaborating, role assignment, communication | 🟡 |
| 2 | **Planning Algorithms** | Planner-Executor, hierarchical task decomposition | 🟡 |
| 3 | **Advanced RAG** | Hybrid search, re-ranking, query transformation | 🟡 |
| 4 | **Agent Memory Systems** | Persistent memory, summarization, forgetting strategies | 🟡 |
| 5 | **Human-in-the-Loop** | Asking for confirmation before critical actions | 🟡 |
| 6 | **Streaming & Real-time** | Token streaming, live agent status updates | 🟢 |
| 7 | **Local/Open-Source Agents** | Run agents with Ollama + LLaMA/Mistral (no API cost) | 🟢 |

---

## PHASE 6: Production, Evaluation & Security 🔒
**⏱️ 2-3 weeks | Priority: 🟡 IMPORTANT for jobs**

### 📊 6A: Evaluation & Testing

| What to Test | How |
|-------------|-----|
| Individual tool accuracy | Unit tests for each tool function |
| End-to-end agent flows | Integration tests with expected outcomes |
| LLM output quality | LangSmith / Ragas / DeepEval frameworks |
| Human evaluation | Human-in-the-loop scoring |

### 🔍 6B: Debugging & Observability

| Tool | Purpose | Priority |
|------|---------|----------|
| **LangSmith** | Trace every LLM call, debug chains | 🔴 |
| **LangFuse** | Open-source alternative to LangSmith | 🟡 |
| **Helicone** | API usage monitoring, cost tracking | 🟡 |
| **OpenLLMetry** | OpenTelemetry for LLMs | 🟢 |

### 🔒 6C: Security & Ethics

| Threat | What It Is | Mitigation |
|--------|-----------|------------|
| **Prompt Injection** | User tricks agent into doing unintended things | Input validation, system prompt hardening |
| **Tool Sandboxing** | Agent could access dangerous tools | Permission levels, whitelisting |
| **Data Privacy / PII** | Agent might leak sensitive data | PII redaction, data masking |
| **Bias & Toxicity** | Agent generates harmful content | Guardrails (Llama Guard, NeMo Guardrails) |
| **Jailbreaks** | Bypassing safety instructions | Red team testing, layered defenses |

---

## 📅 Week-by-Week Schedule (at 2 hrs/day)

```
┌──────────┬───────────────────────────────────────────────────┐
│  WEEK    │  WHAT TO DO                                       │
├──────────┼───────────────────────────────────────────────────┤
│  1-2     │  Python refresh, REST APIs, Git basics            │
│  3       │  Transformer basics, Tokenization, first API call │
│  4       │  Model types, generation controls, embeddings     │
│  5       │  Prompt engineering deep-dive + practice          │
│  6       │  Agent concepts: loop, tools, memory              │
│  7       │  Build first agent from scratch (no framework)    │
│  8       │  Agent architectures: ReAct, CoT, RAG             │
│  9       │  OpenAI Function Calling + Anthropic Tool Use     │
│  10      │  MCP basics + LangChain fundamentals              │
│  11      │  Build RAG agent with ChromaDB                    │
│  12      │  Build multi-tool agent with LangChain            │
│  13-14   │  🏗️ Portfolio Project #1 (pick from ideas above)  │
│  15-16   │  Multi-agent systems + CrewAI                     │
│  17-18   │  Evaluation, testing, observability               │
│  19-20   │  Security, production deployment                  │
│  21-22   │  🏗️ Portfolio Project #2 (advanced)               │
└──────────┴───────────────────────────────────────────────────┘
```

---

## 💼 How This Helps in Placements & Career

| Where | How AI Agents Knowledge Helps |
|-------|------------------------------|
| **Resume** | "Built autonomous AI agent that [did X], reducing [Y] by Z%" |
| **Interviews** | System design questions → design an AI agent system |
| **Projects** | Stands out vs yet-another-CRUD-app |
| **Startups** | AI agent SaaS is one of the hottest sectors right now |
| **Freelancing** | Build AI agents for businesses (₹50K-5L per project) |
| **FAANG/Product companies** | AI/ML teams actively hiring for agent-related roles |

---

## 📚 Complete Resource Bank

| Resource | Category | Cost |
|----------|----------|------|
| [DeepLearning.AI — AI Agents in LangGraph](https://deeplearning.ai) | Course | Free |
| [roadmap.sh/ai-agents](https://roadmap.sh) | Roadmap | Free |
| Andrej Karpathy — "Intro to LLMs" | Video | Free |
| LangChain Docs + Tutorials | Docs | Free |
| [CrewAI Docs](https://docs.crewai.com) | Docs | Free |
| OpenAI Cookbook (GitHub) | Examples | Free |
| Anthropic Prompt Engineering Guide | Guide | Free |
| "Building LLM Apps" — Chip Huyen (blog) | Article | Free |
| HuggingFace Agents Course | Course | Free |
| LangChain Academy | Course | Free |

---

## 🎯 What Should You Do RIGHT NOW?

Since you haven't shared your profile yet, here's my generic recommendation:

```
TODAY:     Make your first LLM API call (Phase 1)
THIS WEEK: Understand the Agent Loop conceptually
NEXT WEEK: Build a simple agent from scratch (Phase 3 code above)
```

---

