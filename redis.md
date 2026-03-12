

# 🔴 COMPLETE REDIS ROADMAP
### From Zero to Production-Grade In-Memory Data Store — Structured & Actionable

---

## 📍 Where You Are → Where You'll Go

```
🟢 BEGINNER            🟡 INTERMEDIATE          🔴 ADVANCED            🏆 PRO
   (Weeks 1-4)            (Weeks 5-9)             (Weeks 10-14)         (Weeks 15-18)
   
   What is Redis?,        Advanced Data            Pub/Sub, Streams,    Clustering,
   Strings, Lists,        Structures, Key          Transactions, Lua,   Monitoring,
   Sets, Hashes,          Management, Sorted       Persistence,         Production,
   Sorted Sets            Sets, Pipelining         Replication          Enterprise
```

---

## 🧒 ELI5: What Is Redis & Why Should You Care?

```
☕ The Chai Stall Analogy:

  Imagine you run a chai stall near a college. 🍵

  WITHOUT REDIS (just a database):
  ─────────────────────────────────
  Customer: "Ek chai dena"
  You: Walk to the BACK ROOM (database), find the recipe,
       check ingredients, prepare chai, come back.
  Time: 5 minutes per customer.
  100 customers? → 500 minutes. Queue wraps around the building.


  WITH REDIS (in-memory cache):
  ─────────────────────────────
  You pre-make 50 cups and keep them on the COUNTER (Redis = RAM).
  Customer: "Ek chai dena"
  You: Pick up from counter. Instant.
  Time: 5 SECONDS per customer.
  100 customers? → Done in minutes. No queue.

  But the counter (RAM) is small — you can't keep 10,000 cups there.
  So you keep the MOST POPULAR items on the counter,
  and the rest in the back room (database).


  ┌──────────────────────────────────────────────────────────────┐
  │                                                              │
  │  DATABASE (PostgreSQL/MySQL) = Back Room / Warehouse 🏪      │
  │  → Stores EVERYTHING permanently                             │
  │  → Reliable, persistent, structured                          │
  │  → SLOW: data on disk, complex queries                       │
  │  → Latency: 5-100 milliseconds                               │
  │                                                              │
  │  REDIS = Counter / Cash Register 💨                           │
  │  → Stores HOT DATA temporarily (or permanently)              │
  │  → Blazingly fast: data in RAM                               │
  │  → FAST: sub-millisecond responses                           │
  │  → Latency: 0.1-1 milliseconds (100x faster!)               │
  │                                                              │
  │  ┌─────────┐          ┌─────────┐          ┌──────────┐     │
  │  │  Client  │──────►  │  REDIS  │──miss──► │ Database │     │
  │  │  (App)   │◄──────  │  (RAM)  │◄─────── │  (Disk)  │     │
  │  └─────────┘  fast!   └─────────┘  slower  └──────────┘     │
  │                                                              │
  │  Cache HIT  → Redis has it → return instantly ⚡             │
  │  Cache MISS → Redis doesn't have it → query DB → store in   │
  │               Redis for next time → return to client         │
  │                                                              │
  └──────────────────────────────────────────────────────────────┘
```

```
🤔 REDIS = Remote Dictionary Server

  It's NOT just a cache. It's a full data structure server:

  ┌──────────────────────────────────────────────────────────────┐
  │                                                              │
  │  WHAT REDIS ACTUALLY IS:                                     │
  │                                                              │
  │  1️⃣ In-Memory Data Structure Store                           │
  │     → Think: Python dict/Java HashMap, but shared across     │
  │       your entire infrastructure, accessible via network      │
  │                                                              │
  │  2️⃣ Key-Value Database                                       │
  │     → Every piece of data has a KEY (name) and VALUE (data)  │
  │     → But values can be strings, lists, sets, hashes, etc.   │
  │                                                              │
  │  3️⃣ Cache                                                     │
  │     → Store frequently accessed data in RAM for speed        │
  │     → Auto-expire data after a time (TTL)                    │
  │                                                              │
  │  4️⃣ Message Broker                                            │
  │     → Pub/Sub: publish messages, subscribers receive them    │
  │     → Streams: like Kafka-lite, ordered message log          │
  │                                                              │
  │  5️⃣ Real-Time Engine                                          │
  │     → Leaderboards, rate limiters, session stores            │
  │     → Anything that needs sub-millisecond speed              │
  │                                                              │
  └──────────────────────────────────────────────────────────────┘
```

```
🎯 CORE USE CASES — Where Redis Shines

┌────────────────────────┬──────────────────────────────────────────┐
│  Use Case              │  Real-World Example                      │
├────────────────────────┼──────────────────────────────────────────┤
│  🔄 Caching            │  Cache DB query results, API responses.  │
│                        │  Amazon product pages cached in Redis.    │
│                        │  Instagram feed cached for fast loading.  │
├────────────────────────┼──────────────────────────────────────────┤
│  👤 Session Management │  Store user login sessions.              │
│                        │  "User 101 is logged in, cart has 3      │
│                        │   items" → stored in Redis, not DB.      │
├────────────────────────┼──────────────────────────────────────────┤
│  📊 Real-time Analytics│  Live dashboard counters, page views.    │
│                        │  Hotstar cricket score updates.           │
│                        │  Swiggy tracking live order count.        │
├────────────────────────┼──────────────────────────────────────────┤
│  📢 Pub/Sub Messaging  │  Chat applications, notifications.      │
│                        │  "New message in group" → all members    │
│                        │   notified instantly.                     │
├────────────────────────┼──────────────────────────────────────────┤
│  🏆 Leaderboards       │  Gaming leaderboards, ranking systems.  │
│                        │  "Top 100 players" updated in real-time. │
│                        │  Sorted Sets make this trivial!          │
├────────────────────────┼──────────────────────────────────────────┤
│  🚦 Rate Limiting      │  API rate limiting (100 req/min).       │
│                        │  "User has made 95/100 requests this     │
│                        │   minute" → stored in Redis with TTL.    │
├────────────────────────┼──────────────────────────────────────────┤
│  🔒 Distributed Locks  │  Prevent double-booking, double-payment.│
│                        │  "Only one server processes this order   │
│                        │   at a time."                             │
├────────────────────────┼──────────────────────────────────────────┤
│  📬 Task Queues        │  Background job processing.             │
│                        │  "Send email later" → push to Redis     │
│                        │   list, worker pops and processes.        │
└────────────────────────┴──────────────────────────────────────────┘
```

```
⚡ REDIS vs OTHER DATABASES

┌──────────────────┬────────────┬────────────┬────────────┬──────────┐
│  Feature         │ Redis      │ PostgreSQL │ MongoDB    │ Memcached│
├──────────────────┼────────────┼────────────┼────────────┼──────────┤
│ Storage          │ RAM (+ disk│ Disk       │ Disk       │ RAM only │
│                  │ optional)  │            │            │          │
├──────────────────┼────────────┼────────────┼────────────┼──────────┤
│ Speed            │ ⚡⚡⚡⚡⚡    │ ⚡⚡        │ ⚡⚡⚡      │ ⚡⚡⚡⚡⚡  │
│ (read latency)   │ <1ms       │ 5-50ms     │ 2-20ms    │ <1ms     │
├──────────────────┼────────────┼────────────┼────────────┼──────────┤
│ Data Structures  │ Rich ✅    │ Tables     │ Documents  │ Strings  │
│                  │ 10+ types  │ (relational│ (JSON)     │ only ❌  │
├──────────────────┼────────────┼────────────┼────────────┼──────────┤
│ Persistence      │ Optional   │ Always ✅  │ Always ✅  │ Never ❌ │
├──────────────────┼────────────┼────────────┼────────────┼──────────┤
│ Queries          │ Key-based  │ SQL (rich) │ Query lang │ Key-based│
├──────────────────┼────────────┼────────────┼────────────┼──────────┤
│ Pub/Sub          │ ✅ Built-in│ ✅ LISTEN  │ ✅ Change  │ ❌ No    │
│                  │            │ /NOTIFY    │  Streams   │          │
├──────────────────┼────────────┼────────────┼────────────┼──────────┤
│ Clustering       │ ✅ Built-in│ ✅ (complex)│ ✅ Replica │ ❌ No    │
│                  │            │            │  Sets      │          │
├──────────────────┼────────────┼────────────┼────────────┼──────────┤
│ Best For         │ Cache, RT  │ OLTP,      │ Flexible   │ Simple   │
│                  │ analytics, │ complex    │ schemas,   │ caching  │
│                  │ sessions   │ queries    │ documents  │          │
├──────────────────┼────────────┼────────────┼────────────┼──────────┤
│ Used By          │ Twitter,   │ Instagram, │ Uber,      │ Facebook,│
│                  │ GitHub,    │ Spotify,   │ eBay       │ YouTube  │
│                  │ Snapchat   │ Reddit     │            │          │
└──────────────────┴────────────┴────────────┴────────────┴──────────┘

💡 Redis REPLACES Memcached (more features, same speed).
   Redis COMPLEMENTS PostgreSQL/MongoDB (not replaces!).
   Use BOTH: Redis for speed + PostgreSQL for persistence.
```

---

## 🟢 PHASE 1: GETTING STARTED & CORE DATA STRUCTURES (Weeks 1–4)

### Week 1: Introduction & Setup

| # | Topic | Priority | Est. Hours | Status |
|---|-------|----------|-----------|--------|
| 1 | **What is Redis?** — in-memory data store, key-value, multi-purpose | 🔴 Critical | 1h | ⬜ |
| 2 | **Core Use Cases** — caching, sessions, analytics, pub/sub, leaderboards | 🔴 Critical | 1h | ⬜ |
| 3 | **Key Features** — persistence options, rich data structures, performance | 🟡 Important | 1h | ⬜ |
| 4 | **Redis vs SQL/NoSQL DBs** — when to choose Redis | 🟡 Important | 1h | ⬜ |
| 5 | **Installing Redis** — locally, via package manager, via Docker | 🔴 Critical | 1h | ⬜ |
| 6 | **Running Redis** — starting server, connecting via CLI | 🔴 Critical | 1h | ⬜ |
| 7 | **Basic Commands** — SET, GET, DEL, EXISTS, expire, TTL | 🔴 Critical | 2h | ⬜ |
| 8 | **Overview of Data Types** — strings, lists, sets, hashes, sorted sets | 🔴 Critical | 1h | ⬜ |

```bash
# 🔧 INSTALLING REDIS

# ─── Option 1: Docker (RECOMMENDED — cleanest) ──
docker run -d --name my-redis -p 6379:6379 redis:7-alpine

# Connect to it:
docker exec -it my-redis redis-cli

# ─── Option 2: macOS (Homebrew) ──────────────────
brew install redis
brew services start redis
redis-cli   # Connect

# ─── Option 3: Ubuntu/Debian ────────────────────
sudo apt update
sudo apt install redis-server
sudo systemctl start redis-server
redis-cli   # Connect

# ─── Option 4: Windows (WSL recommended) ────────
# Install WSL2, then follow Ubuntu instructions
# Or use Docker Desktop for Windows

# ─── Verify Installation ────────────────────────
redis-cli ping
# Response: PONG  ← Redis is running! 🎉
```

```bash
# 🎯 FIRST STEPS — Basic Commands (redis-cli)

# ═══════════════════════════════════════════════
# SET & GET — The bread and butter
# ═══════════════════════════════════════════════

# SET key value
SET name "Rahul Sharma"
# OK

# GET key
GET name
# "Rahul Sharma"

# SET with options
SET user:101:name "Rahul" EX 3600   # Expires in 3600 seconds (1 hour)
SET user:101:name "Rahul" PX 5000   # Expires in 5000 milliseconds
SET user:101:name "Rahul" NX        # Set only if key does NOT exist
SET user:101:name "Rahul" XX        # Set only if key ALREADY exists

# ═══════════════════════════════════════════════
# Key Operations
# ═══════════════════════════════════════════════

EXISTS name          # 1 (exists) or 0 (doesn't exist)
DEL name             # Delete key → returns number of keys deleted
UNLINK name          # Non-blocking delete (async, for large values)

TYPE name            # Returns the data type: string, list, set, hash, zset
RENAME old_key new_key   # Rename a key

# ═══════════════════════════════════════════════
# Expiration & TTL
# ═══════════════════════════════════════════════

SET session:abc123 "user_101"
EXPIRE session:abc123 1800          # Expire in 1800 seconds (30 min)
TTL session:abc123                  # Returns remaining seconds (-1 = no expiry)
PTTL session:abc123                 # Returns remaining milliseconds
PERSIST session:abc123              # Remove expiry (make permanent)

# ═══════════════════════════════════════════════
# Key Discovery
# ═══════════════════════════════════════════════

KEYS *               # List ALL keys (⚠️ NEVER use in production! Blocks server)
KEYS user:*          # Pattern matching
SCAN 0 MATCH user:* COUNT 100  # Safe alternative (cursor-based, non-blocking) ✅
DBSIZE               # Total number of keys
RANDOMKEY            # Return a random key
```

```
📐 KEY NAMING CONVENTIONS — Best Practices

  ┌──────────────────────────────────────────────────────────────┐
  │                                                              │
  │  Use COLONS (:) as separators (like path/namespace)          │
  │                                                              │
  │  ✅ GOOD:                                                     │
  │  user:101:profile         → User 101's profile               │
  │  user:101:sessions        → User 101's sessions              │
  │  product:sku:ABC123       → Product by SKU                   │
  │  cache:api:/v1/students   → Cached API response              │
  │  session:abc123def        → Session by token                 │
  │  rate_limit:user:101      → Rate limit counter               │
  │  leaderboard:game:chess   → Chess leaderboard                │
  │                                                              │
  │  ❌ BAD:                                                      │
  │  rahul_profile            → No structure, not scalable       │
  │  userProfileData          → camelCase doesn't fit Redis      │
  │  user-101-profile         → Hyphens less common than colons  │
  │  u:101:p                  → Too cryptic                      │
  │                                                              │
  │  PATTERN: object_type:id:field                               │
  │           entity:identifier:attribute                        │
  │                                                              │
  └──────────────────────────────────────────────────────────────┘
```

---

### Week 2: Core Data Structures — Strings & Lists

| # | Topic | Priority | Est. Hours | Status |
|---|-------|----------|-----------|--------|
| 9 | **Strings** — SET, GET, INCR, DECR, APPEND, STRLEN, MSET, MGET | 🔴 Critical | 3h | ⬜ |
| 10 | **String Use Cases** — caching, counters, rate limiting, flags | 🔴 Critical | 2h | ⬜ |
| 11 | **Lists** — LPUSH, RPUSH, LPOP, RPOP, LRANGE, LINDEX, LLEN, LMOVE | 🔴 Critical | 3h | ⬜ |
| 12 | **List Use Cases** — message queues, activity feeds, recent items | 🔴 Critical | 2h | ⬜ |

```
📊 REDIS DATA STRUCTURES — The Complete Map

  ┌──────────────────────────────────────────────────────────────┐
  │                     REDIS DATA TYPES                         │
  │                                                              │
  │  BASIC:                                                      │
  │  ┌──────────┐ ┌──────────┐ ┌──────────┐ ┌──────────────┐   │
  │  │ Strings  │ │  Lists   │ │   Sets   │ │   Hashes     │   │
  │  │ "hello"  │ │ [a,b,c]  │ │ {a,b,c}  │ │ {f1:v1,f2:v2}│  │
  │  └──────────┘ └──────────┘ └──────────┘ └──────────────┘   │
  │                                                              │
  │  ┌──────────────┐                                            │
  │  │ Sorted Sets  │                                            │
  │  │ {a:1,b:2,c:3}│  (elements with scores)                   │
  │  └──────────────┘                                            │
  │                                                              │
  │  ADVANCED:                                                   │
  │  ┌──────────┐ ┌─────────────┐ ┌──────────┐ ┌────────────┐  │
  │  │ Bitmaps  │ │ HyperLogLog │ │ Streams  │ │ Geospatial │  │
  │  │ 01101001 │ │ ~count      │ │ log/event│ │ lat/long   │  │
  │  └──────────┘ └─────────────┘ └──────────┘ └────────────┘  │
  │                                                              │
  └──────────────────────────────────────────────────────────────┘
```

```bash
# 🔤 STRINGS — The Most Versatile Type

# Strings can store: text, numbers, binary data, JSON, anything up to 512MB

# ─── Basic Operations ────────────────────────
SET greeting "Hello, Redis!"
GET greeting                       # "Hello, Redis!"
APPEND greeting " 🦀"             # Append to existing string
STRLEN greeting                    # Length in bytes

# ─── Multiple Keys at Once ───────────────────
MSET user:101:name "Rahul" user:101:branch "CSE" user:101:cgpa "8.5"
MGET user:101:name user:101:branch user:101:cgpa
# 1) "Rahul"
# 2) "CSE"
# 3) "8.5"

# ─── Numeric Operations (Atomic!) ────────────
SET page_views 0
INCR page_views                    # 1 (increment by 1)
INCR page_views                    # 2
INCRBY page_views 10               # 12 (increment by 10)
DECR page_views                    # 11
DECRBY page_views 5                # 6
INCRBYFLOAT price 9.99             # Floating-point increment

# 💡 WHY ATOMIC MATTERS:
# 100 servers running INCR simultaneously → EXACT count, no race condition!
# In regular code: read → add 1 → write = RACE CONDITION if concurrent
# Redis INCR: single-threaded, atomic, no locks needed!

# ─── String Ranges ───────────────────────────
SET msg "Hello, World!"
GETRANGE msg 0 4                   # "Hello"
SETRANGE msg 7 "Redis!"           # "Hello, Redis!"

# ─── Conditional SET ─────────────────────────
SET lock:order:123 "processing" NX EX 30
# NX = set only if NOT exists (distributed lock!)
# EX 30 = expires in 30 seconds (auto-unlock!)
# Returns OK if set, nil if key already exists
```

```bash
# 🎯 STRING USE CASES — Real-World Patterns

# ═══════════════════════════════════════════════
# 1. CACHING — Store expensive query results
# ═══════════════════════════════════════════════

# Cache API response for 5 minutes
SET cache:api:/v1/students '{"students":[{"name":"Rahul","cgpa":8.5}]}' EX 300

# Check cache first, then DB
# Pseudocode:
# cached = redis.GET("cache:api:/v1/students")
# if cached:
#     return cached  ← FAST! (cache hit)
# else:
#     data = database.query("SELECT * FROM students")
#     redis.SET("cache:api:/v1/students", json(data), EX=300)
#     return data  ← Slower, but now cached for next time


# ═══════════════════════════════════════════════
# 2. COUNTERS — Page views, likes, API calls
# ═══════════════════════════════════════════════

# Track page views per article
INCR pageview:article:42            # 1
INCR pageview:article:42            # 2
INCR pageview:article:42            # 3
GET pageview:article:42             # "3"


# ═══════════════════════════════════════════════
# 3. RATE LIMITING — 100 requests per minute
# ═══════════════════════════════════════════════

# Simple rate limiter for user 101:
SET rate:user:101 1 EX 60 NX       # First request, expires in 60s
INCR rate:user:101                  # Increment on each request
# If INCR result > 100 → reject request (429 Too Many Requests)


# ═══════════════════════════════════════════════
# 4. SESSION STORE — User login sessions
# ═══════════════════════════════════════════════

SET session:abc123def '{"user_id":101,"name":"Rahul","role":"student"}' EX 1800
# Session expires in 30 minutes

GET session:abc123def
# Returns user data → user is logged in!

DEL session:abc123def
# Logout → delete session


# ═══════════════════════════════════════════════
# 5. DISTRIBUTED LOCK — Prevent double-processing
# ═══════════════════════════════════════════════

SET lock:payment:order:789 "server-1" NX EX 30
# NX ensures only ONE server gets the lock
# EX 30 = auto-release after 30 seconds (safety net)
# If returns OK → this server processes the payment
# If returns nil → another server already has it, skip
```

```bash
# 📋 LISTS — Ordered Collection (Linked List)

# Lists are ORDERED, allow DUPLICATES, accessed by index.
# O(1) push/pop from both ends! O(N) for middle access.

# ═══════════════════════════════════════════════
# Basic Operations
# ═══════════════════════════════════════════════

# LPUSH = push to LEFT (head), RPUSH = push to RIGHT (tail)
RPUSH notifications:user:101 "Welcome to the platform!"
RPUSH notifications:user:101 "Your course CSE301 starts tomorrow"
RPUSH notifications:user:101 "Assignment due in 2 days"
LPUSH notifications:user:101 "URGENT: Exam schedule released"

# LRANGE = get range of elements (0-based, inclusive)
LRANGE notifications:user:101 0 -1
# 1) "URGENT: Exam schedule released"    (LPUSH → head)
# 2) "Welcome to the platform!"
# 3) "Your course CSE301 starts tomorrow"
# 4) "Assignment due in 2 days"           (RPUSH → tail)

LRANGE notifications:user:101 0 2   # First 3 elements
LLEN notifications:user:101         # 4 (length)
LINDEX notifications:user:101 1     # Element at index 1

# POP operations
LPOP notifications:user:101         # Remove & return from head
RPOP notifications:user:101         # Remove & return from tail
BLPOP queue:tasks 30                # Blocking pop (wait up to 30s) — for queues!

# ═══════════════════════════════════════════════
# Trim (keep only N recent items)
# ═══════════════════════════════════════════════

# Keep only the 100 most recent notifications
LTRIM notifications:user:101 0 99
# Deletes everything beyond index 99
```

```bash
# 🎯 LIST USE CASES

# ═══════════════════════════════════════════════
# 1. MESSAGE QUEUE (Simple Job Queue)
# ═══════════════════════════════════════════════

# Producer: push tasks to the queue
RPUSH queue:emails '{"to":"rahul@email.com","subject":"Welcome!"}'
RPUSH queue:emails '{"to":"priya@email.com","subject":"Verify account"}'

# Consumer: pop tasks from the queue (blocking)
BLPOP queue:emails 0
# Waits until a message is available, then pops it
# This is a simple but effective job queue!

# Multiple consumers can BLPOP the same queue → load balancing!


# ═══════════════════════════════════════════════
# 2. ACTIVITY FEED / RECENT ITEMS
# ═══════════════════════════════════════════════

# Log user activity (keep last 50)
LPUSH activity:user:101 '{"action":"login","time":"2025-01-15T10:30:00"}'
LPUSH activity:user:101 '{"action":"view_course","course":"DSA","time":"..."}'
LTRIM activity:user:101 0 49     # Keep only 50 most recent

# Get last 10 activities
LRANGE activity:user:101 0 9


# ═══════════════════════════════════════════════
# 3. STACK (LIFO) & QUEUE (FIFO)
# ═══════════════════════════════════════════════

# Stack: LPUSH + LPOP (last in, first out)
LPUSH stack:undo "action1"
LPUSH stack:undo "action2"
LPUSH stack:undo "action3"
LPOP stack:undo              # "action3" ← most recent

# Queue: RPUSH + LPOP (first in, first out)
RPUSH queue:print "doc1"
RPUSH queue:print "doc2"
RPUSH queue:print "doc3"
LPOP queue:print             # "doc1" ← oldest first
```

---

### Week 3: Core Data Structures — Sets & Hashes

| # | Topic | Priority | Est. Hours | Status |
|---|-------|----------|-----------|--------|
| 13 | **Sets** — SADD, SMEMBERS, SREM, SISMEMBER, SINTER, SUNION, SDIFF, SCARD | 🔴 Critical | 3h | ⬜ |
| 14 | **Set Use Cases** — tags, unique visitors, common friends | 🔴 Critical | 2h | ⬜ |
| 15 | **Hashes** — HSET, HGET, HGETALL, HDEL, HEXISTS, HINCRBY | 🔴 Critical | 3h | ⬜ |
| 16 | **Hash Use Cases** — object storage, user profiles, configurations | 🔴 Critical | 2h | ⬜ |

```bash
# 🎯 SETS — Unordered, Unique Elements (No Duplicates!)

# Like Python's set() or Java's HashSet
# O(1) add, remove, check membership!

# ═══════════════════════════════════════════════
# Basic Operations
# ═══════════════════════════════════════════════

SADD skills:user:101 "python" "javascript" "rust" "docker"
SADD skills:user:101 "python"      # Ignored! Already exists (no duplicates)

SMEMBERS skills:user:101           # All members (unordered)
# 1) "python"
# 2) "javascript"  
# 3) "rust"
# 4) "docker"

SISMEMBER skills:user:101 "python"  # 1 (true)
SISMEMBER skills:user:101 "java"    # 0 (false)
SCARD skills:user:101               # 4 (cardinality = count)
SREM skills:user:101 "docker"       # Remove element
SRANDMEMBER skills:user:101 2       # 2 random members
SPOP skills:user:101                # Remove & return random member

# ═══════════════════════════════════════════════
# SET OPERATIONS — The Superpower ⚡
# ═══════════════════════════════════════════════

SADD skills:user:101 "python" "javascript" "rust" "docker"
SADD skills:user:102 "python" "java" "docker" "kubernetes"

# INTERSECTION — Skills BOTH users have
SINTER skills:user:101 skills:user:102
# 1) "python"
# 2) "docker"

# UNION — ALL skills combined
SUNION skills:user:101 skills:user:102
# python, javascript, rust, docker, java, kubernetes

# DIFFERENCE — Skills user:101 has that user:102 doesn't
SDIFF skills:user:101 skills:user:102
# 1) "javascript"
# 2) "rust"

# Store results in a new key
SINTERSTORE common:skills skills:user:101 skills:user:102
```

```bash
# 🎯 SET USE CASES

# ═══════════════════════════════════════════════
# 1. UNIQUE VISITORS (Track without counting duplicates)
# ═══════════════════════════════════════════════

SADD visitors:2025-01-15 "user:101" "user:102" "user:103"
SADD visitors:2025-01-15 "user:101"    # Already counted — ignored!
SCARD visitors:2025-01-15              # 3 unique visitors

# ═══════════════════════════════════════════════
# 2. TAGS / CATEGORIES
# ═══════════════════════════════════════════════

# Tag articles
SADD article:42:tags "rust" "programming" "systems"
SADD article:43:tags "rust" "webdev" "api"

# All articles tagged "rust"
SADD tag:rust:articles "42" "43"

# Common tags between articles
SINTER article:42:tags article:43:tags    # "rust"

# ═══════════════════════════════════════════════
# 3. MUTUAL FRIENDS (Social Networks)
# ═══════════════════════════════════════════════

SADD friends:rahul "priya" "amit" "sneha" "karan"
SADD friends:priya "rahul" "amit" "deepa" "riya"

# Mutual friends
SINTER friends:rahul friends:priya
# 1) "amit"

# People Rahul knows but Priya doesn't (friend suggestions!)
SDIFF friends:rahul friends:priya
# "sneha", "karan"

# ═══════════════════════════════════════════════
# 4. ONLINE USERS
# ═══════════════════════════════════════════════

SADD online:users "user:101" "user:102" "user:103"
SREM online:users "user:102"           # User went offline
SISMEMBER online:users "user:101"      # Is user online? → 1 (yes)
SCARD online:users                     # How many online? → 2
```

```bash
# 📦 HASHES — Field-Value Pairs (Like Objects/Dicts)

# Perfect for representing OBJECTS with multiple fields
# Like a Python dict or JSON object, but each field is independently accessible

# ═══════════════════════════════════════════════
# Basic Operations
# ═══════════════════════════════════════════════

# Store a student as a hash
HSET student:101 name "Rahul Sharma"
HSET student:101 branch "CSE" cgpa "8.5" year "3" email "rahul@college.edu.in"

# Or set multiple fields at once
HSET student:102 name "Priya Verma" branch "ECE" cgpa "9.2" year "3"

# Get single field
HGET student:101 name                    # "Rahul Sharma"
HGET student:101 cgpa                    # "8.5"

# Get ALL fields and values
HGETALL student:101
# 1) "name"       2) "Rahul Sharma"
# 3) "branch"     4) "CSE"
# 5) "cgpa"       6) "8.5"
# 7) "year"       8) "3"
# 9) "email"      10) "rahul@college.edu.in"

# Get only values
HVALS student:101

# Get only keys (field names)
HKEYS student:101

# Check if field exists
HEXISTS student:101 email                # 1 (yes)
HEXISTS student:101 phone                # 0 (no)

# Delete a field
HDEL student:101 email

# Number of fields
HLEN student:101                         # 4

# Increment numeric field
HINCRBY student:101 year 1              # Promote to year 4!
HINCRBYFLOAT student:101 cgpa 0.3       # CGPA updated to 8.8

# Get multiple fields
HMGET student:101 name cgpa branch
# 1) "Rahul Sharma"
# 2) "8.8"
# 3) "CSE"
```

```bash
# 🎯 HASH USE CASES

# ═══════════════════════════════════════════════
# 1. USER PROFILES (Most common!)
# ═══════════════════════════════════════════════

HSET user:101 name "Rahul" email "rahul@email.com" role "student" login_count "0"
HINCRBY user:101 login_count 1         # Increment on each login

# Update single field without touching others
HSET user:101 email "rahul.new@email.com"

# ═══════════════════════════════════════════════
# 2. SHOPPING CART
# ═══════════════════════════════════════════════

HSET cart:user:101 "product:laptop" "1" "product:mouse" "2" "product:keyboard" "1"
HINCRBY cart:user:101 "product:mouse" 1    # Add one more mouse → 3
HDEL cart:user:101 "product:keyboard"      # Remove keyboard from cart
HGETALL cart:user:101                      # View entire cart

# ═══════════════════════════════════════════════
# 3. CONFIGURATION / SETTINGS
# ═══════════════════════════════════════════════

HSET config:app max_upload_size "10MB" theme "dark" language "en" debug "false"
HGET config:app debug                  # "false"
HSET config:app debug "true"           # Toggle debug mode
```

```
📊 WHY HASHES OVER STRINGS FOR OBJECTS?

  Approach 1: Separate string keys (wasteful)
  ──────────────────────────────────────────────
  SET user:101:name "Rahul"
  SET user:101:email "rahul@email.com"
  SET user:101:cgpa "8.5"
  → 3 keys, 3 GET commands to fetch all data
  → More memory overhead per key
  
  Approach 2: JSON string (inflexible)
  ──────────────────────────────────────────────
  SET user:101 '{"name":"Rahul","email":"rahul@email.com","cgpa":8.5}'
  → 1 key, but must GET + parse + modify + SET entire JSON 
    to change ONE field
  
  Approach 3: Hash (✅ BEST)
  ──────────────────────────────────────────────
  HSET user:101 name "Rahul" email "rahul@email.com" cgpa "8.5"
  → 1 key, individual field access
  → HGET user:101 cgpa  ← get ONE field, fast!
  → HINCRBY user:101 login_count 1  ← atomic increment on single field
  → Memory-efficient (Redis optimizes small hashes!)
  
  ┌──────────────────┬────────────┬────────────┬──────────────┐
  │ Approach         │ Memory     │ Flexibility│ Performance  │
  ├──────────────────┼────────────┼────────────┼──────────────┤
  │ Separate keys    │ ❌ High    │ ✅ Good    │ ❌ Many calls│
  │ JSON string      │ ✅ Low     │ ❌ Poor    │ ❌ Parse all │
  │ Hash ✅          │ ✅ Low     │ ✅ Good    │ ✅ Best      │
  └──────────────────┴────────────┴────────────┴──────────────┘
```

---

### Week 4: Sorted Sets

| # | Topic | Priority | Est. Hours | Status |
|---|-------|----------|-----------|--------|
| 17 | **Sorted Sets** — ZADD, ZRANGE, ZRANGEBYSCORE, ZREM, ZINCRBY, ZRANK, ZCOUNT | 🔴 Critical | 4h | ⬜ |
| 18 | **Sorted Set Use Cases** — leaderboards, priority queues, time-series | 🔴 Critical | 3h | ⬜ |
| 19 | **Reverse Operations** — ZREVRANGE, ZREVRANK, ZREVRANGEBYSCORE | 🟡 Important | 1h | ⬜ |

```bash
# 🏆 SORTED SETS — Elements with Scores (Ordered by Score)

# Like a Set, but each element has a SCORE (floating-point number).
# Elements are automatically sorted by score. O(log N) operations!
# THE secret weapon for leaderboards, rankings, and priority queues.

# ═══════════════════════════════════════════════
# Basic Operations
# ═══════════════════════════════════════════════

# ZADD key score member [score member ...]
ZADD leaderboard 850 "Rahul" 920 "Priya" 780 "Amit" 890 "Sneha" 950 "Karan"

# ZRANGE — Get elements by rank (index), low→high
ZRANGE leaderboard 0 -1 WITHSCORES
# 1) "Amit"     2) "780"
# 3) "Rahul"    4) "850"
# 5) "Sneha"    6) "890"
# 7) "Priya"    8) "920"
# 9) "Karan"    10) "950"

# ZREVRANGE — High→Low (for leaderboards!)
ZREVRANGE leaderboard 0 2 WITHSCORES
# 1) "Karan"    2) "950"     ← Rank 1
# 3) "Priya"    4) "920"     ← Rank 2
# 5) "Sneha"    6) "890"     ← Rank 3

# Top 3 players! Done in O(log N + 3). For millions of players.

# ZRANK — Get rank of a specific member (0-based, low→high)
ZRANK leaderboard "Rahul"      # 1 (0-based, 2nd from bottom)
ZREVRANK leaderboard "Rahul"   # 3 (0-based, 4th from top)

# ZSCORE — Get score of a member
ZSCORE leaderboard "Priya"     # "920"

# ZINCRBY — Increment score (atomic!)
ZINCRBY leaderboard 50 "Rahul" # Rahul's score → 900
# Rahul scored 50 more points!

# ZRANGEBYSCORE — Get elements within score range
ZRANGEBYSCORE leaderboard 800 900 WITHSCORES
# Elements with scores between 800 and 900

# ZCOUNT — Count elements in score range
ZCOUNT leaderboard 800 900     # How many scored 800-900?

# ZREM — Remove member
ZREM leaderboard "Amit"

# ZCARD — Total members
ZCARD leaderboard              # 4
```

```bash
# 🎯 SORTED SET USE CASES — Where They SHINE

# ═══════════════════════════════════════════════
# 1. GAMING LEADERBOARD (The Classic!)
# ═══════════════════════════════════════════════

# Players earn points
ZADD game:leaderboard 1500 "player:ninja42"
ZADD game:leaderboard 2100 "player:coder_king"
ZADD game:leaderboard 1800 "player:speed_demon"

# Player scores 200 more points
ZINCRBY game:leaderboard 200 "player:ninja42"    # → 1700

# Top 10 players
ZREVRANGE game:leaderboard 0 9 WITHSCORES

# What's my rank?
ZREVRANK game:leaderboard "player:ninja42"        # Your position

# Players who scored between 1500-2000
ZRANGEBYSCORE game:leaderboard 1500 2000 WITHSCORES


# ═══════════════════════════════════════════════
# 2. PRIORITY QUEUE (Process high-priority first)
# ═══════════════════════════════════════════════

# Score = priority (lower = more urgent)
ZADD priority:queue 1 '{"task":"server_down","severity":"critical"}'
ZADD priority:queue 3 '{"task":"slow_query","severity":"medium"}'
ZADD priority:queue 2 '{"task":"disk_90_percent","severity":"high"}'

# Pop highest priority (lowest score)
ZPOPMIN priority:queue            # Returns critical task first


# ═══════════════════════════════════════════════
# 3. RATE LIMITER (Sliding Window)
# ═══════════════════════════════════════════════

# Track API requests with timestamps as scores
# Score = Unix timestamp of request
# Member = unique request ID

# Log a request
ZADD rate:user:101 1705312800 "req:abc123"
ZADD rate:user:101 1705312801 "req:def456"

# Count requests in last 60 seconds
ZCOUNT rate:user:101 (NOW-60) NOW

# Remove old entries (cleanup)
ZREMRANGEBYSCORE rate:user:101 0 (NOW-60)


# ═══════════════════════════════════════════════
# 4. TRENDING / HOT ARTICLES
# ═══════════════════════════════════════════════

# Score = view count / engagement score
ZINCRBY trending:articles 1 "article:42"      # +1 view
ZINCRBY trending:articles 1 "article:42"      # +1 view
ZINCRBY trending:articles 1 "article:15"      # +1 view

# Top 5 trending articles
ZREVRANGE trending:articles 0 4 WITHSCORES


# ═══════════════════════════════════════════════
# 5. AUTOCOMPLETE / SEARCH SUGGESTIONS
# ═══════════════════════════════════════════════

# Score = search frequency
ZINCRBY search:suggestions 1 "python tutorial"
ZINCRBY search:suggestions 1 "python tutorial"
ZINCRBY search:suggestions 1 "python for beginners"
ZINCRBY search:suggestions 1 "pytorch installation"

# Top suggestions starting with "python"
# (requires ZRANGEBYLEX for prefix matching or RediSearch module)
ZREVRANGE search:suggestions 0 4 WITHSCORES
```

```
📊 CORE DATA STRUCTURES — Complete Comparison

┌──────────────┬────────────────┬──────────┬──────────────┬───────────────────┐
│ Type         │ Analogy        │ Ordered? │ Duplicates?  │ Best For          │
├──────────────┼────────────────┼──────────┼──────────────┼───────────────────┤
│ String       │ Single value   │ N/A      │ N/A          │ Cache, counters,  │
│              │ in a variable  │          │              │ sessions, locks   │
├──────────────┼────────────────┼──────────┼──────────────┼───────────────────┤
│ List         │ Python list    │ ✅ Yes   │ ✅ Yes       │ Queues, feeds,    │
│              │ (linked list)  │ (insert) │              │ recent items      │
├──────────────┼────────────────┼──────────┼──────────────┼───────────────────┤
│ Set          │ Python set     │ ❌ No    │ ❌ No        │ Tags, unique      │
│              │ {1, 2, 3}      │          │              │ items, relations  │
├──────────────┼────────────────┼──────────┼──────────────┼───────────────────┤
│ Hash         │ Python dict    │ ❌ No    │ Fields unique│ Objects, profiles,│
│              │ {"k": "v"}     │          │              │ settings, carts   │
├──────────────┼────────────────┼──────────┼──────────────┼───────────────────┤
│ Sorted Set   │ Set + priority │ ✅ Yes   │ ❌ No        │ Leaderboards,     │
│              │                │ (score)  │              │ rankings, queues  │
└──────────────┴────────────────┴──────────┴──────────────┴───────────────────┘
```

---

## 🟡 PHASE 2: WORKING WITH REDIS & ADVANCED STRUCTURES (Weeks 5–9)

### Week 5: Key Management & Batch Operations

| # | Topic | Priority | Est. Hours | Status |
|---|-------|----------|-----------|--------|
| 20 | **Key Naming Conventions** — colon-separated namespaces | 🔴 Critical | 1h | ⬜ |
| 21 | **Key Retrieval by Pattern** — SCAN, KEYS (dangers), cursor iteration | 🔴 Critical | 2h | ⬜ |
| 22 | **Key Expiration** — EXPIRE, PEXPIRE, EXPIREAT, TTL, PERSIST | 🟡 Important | 1h | ⬜ |
| 23 | **Atomicity in Redis** — single-threaded model, atomic commands | 🔴 Critical | 2h | ⬜ |
| 24 | **Pipelining** — batch multiple commands in one round trip | 🔴 Critical | 2h | ⬜ |
| 25 | **Batch Operations** — MSET/MGET, multiple key operations | 🟡 Important | 1h | ⬜ |

```bash
# ⚡ PIPELINING — Send Many Commands at Once

# Without pipelining (SLOW):
# Client → Server: SET key1 value1      (1 round trip)
# Client → Server: SET key2 value2      (1 round trip)
# Client → Server: SET key3 value3      (1 round trip)
# Total: 3 round trips × ~1ms network latency = ~3ms

# With pipelining (FAST):
# Client → Server: [SET key1 value1, SET key2 value2, SET key3 value3]
# Total: 1 round trip = ~1ms

# redis-cli pipelining:
redis-cli --pipe <<EOF
SET student:1 "Rahul"
SET student:2 "Priya"
SET student:3 "Amit"
INCR counter
LPUSH queue:tasks "task1"
EOF
```

```python
# 🐍 PIPELINING IN PYTHON (redis-py)

import redis

r = redis.Redis(host='localhost', port=6379, decode_responses=True)

# ─── Without pipelining (slow) ───────────────
# 1000 individual round trips!
for i in range(1000):
    r.set(f"key:{i}", f"value:{i}")  # 1000 round trips!

# ─── With pipelining (fast!) ─────────────────
# 1 round trip for all 1000 commands!
pipe = r.pipeline()
for i in range(1000):
    pipe.set(f"key:{i}", f"value:{i}")
results = pipe.execute()  # All 1000 commands sent at once!

# ⏱️ Performance difference:
# Without pipeline: ~1000ms (1000 × 1ms per round trip)
# With pipeline:    ~5ms    (1 round trip + processing)
# That's 200x faster! 🚀
```

```
⚛️ ATOMICITY IN REDIS — Why Redis Is Thread-Safe

  ┌──────────────────────────────────────────────────────────────┐
  │                                                              │
  │  Redis is SINGLE-THREADED for command processing.            │
  │  (I/O is multi-threaded in Redis 6+, but command execution  │
  │   is still single-threaded)                                  │
  │                                                              │
  │  This means:                                                 │
  │  • INCR is ATOMIC — no race condition, ever                  │
  │  • Every command completes fully before the next starts      │
  │  • No need for mutexes, locks, or synchronization           │
  │  • 100 servers doing INCR simultaneously → perfect count    │
  │                                                              │
  │  ┌─────┐ ┌─────┐ ┌─────┐                                   │
  │  │App 1│ │App 2│ │App 3│  ← 3 servers, concurrent           │
  │  └──┬──┘ └──┬──┘ └──┬──┘                                    │
  │     │       │       │                                        │
  │     └───────┼───────┘                                        │
  │             ▼                                                │
  │      ┌──────────┐                                            │
  │      │  REDIS   │ ← Commands processed ONE AT A TIME        │
  │      │ (single  │                                            │
  │      │ threaded)│   INCR counter  → 1                        │
  │      │          │   INCR counter  → 2  (no race condition!)  │
  │      │          │   INCR counter  → 3                        │
  │      └──────────┘                                            │
  │                                                              │
  │  ⚠️ But: Long commands (KEYS *, SORT on huge sets) BLOCK    │
  │     the entire server. Use SCAN instead of KEYS!             │
  │                                                              │
  └──────────────────────────────────────────────────────────────┘
```

---

### Week 6–7: Advanced Data Structures

| # | Topic | Priority | Est. Hours | Status |
|---|-------|----------|-----------|--------|
| 26 | **Bitmaps** — SETBIT, GETBIT, BITCOUNT, BITOP, BITPOS | 🟡 Important | 3h | ⬜ |
| 27 | **Bitmap Use Cases** — daily active users, feature flags, bloom filters | 🟡 Important | 2h | ⬜ |
| 28 | **HyperLogLog** — PFADD, PFCOUNT, PFMERGE | 🟡 Important | 2h | ⬜ |
| 29 | **HyperLogLog Use Cases** — unique count estimation, cardinality | 🟡 Important | 1h | ⬜ |
| 30 | **Streams** — XADD, XREAD, XRANGE, XLEN, consumer groups | 🔴 Critical | 4h | ⬜ |
| 31 | **Stream Use Cases** — event log, message broker, activity stream | 🔴 Critical | 2h | ⬜ |
| 32 | **Geospatial Indexes** — GEOADD, GEOSEARCH, GEODIST | 🟡 Important | 2h | ⬜ |
| 33 | **Geospatial Use Cases** — nearby search, delivery tracking | 🟡 Important | 1h | ⬜ |

```bash
# 🗺️ BITMAPS — Memory-Efficient Boolean Arrays

# A bitmap is a string where each BIT can be 0 or 1.
# Perfect for tracking true/false for millions of items!

# ═══════════════════════════════════════════════
# Track Daily Active Users (DAU)
# ═══════════════════════════════════════════════

# User ID = bit offset, 1 = active, 0 = inactive
SETBIT dau:2025-01-15 101 1        # User 101 was active
SETBIT dau:2025-01-15 102 1        # User 102 was active
SETBIT dau:2025-01-15 103 1        # User 103 was active
SETBIT dau:2025-01-15 999 1        # User 999 was active

GETBIT dau:2025-01-15 101          # 1 (was active)
GETBIT dau:2025-01-15 500          # 0 (was NOT active)

BITCOUNT dau:2025-01-15            # 4 (total active users)

# 💡 MEMORY: Track 1 MILLION users = only 125 KB!
# (1M bits ÷ 8 = 125,000 bytes = 122 KB)
# vs. Set: 1M members × ~50 bytes = ~50 MB
# Bitmaps are 400x more memory efficient!

# ─── Bitwise Operations ─────────────────────
# Users active on BOTH Jan 15 AND Jan 16 (AND)
BITOP AND active:both dau:2025-01-15 dau:2025-01-16
BITCOUNT active:both               # Users active on both days

# Users active on Jan 15 OR Jan 16 (OR)
BITOP OR active:either dau:2025-01-15 dau:2025-01-16
BITCOUNT active:either             # Users active on either day

# ═══════════════════════════════════════════════
# Feature Flags
# ═══════════════════════════════════════════════

# Bit 0 = dark mode, Bit 1 = beta features, Bit 2 = notifications
SETBIT features:user:101 0 1      # Dark mode ON
SETBIT features:user:101 1 0      # Beta OFF
SETBIT features:user:101 2 1      # Notifications ON

GETBIT features:user:101 0        # 1 → dark mode is ON
```

```bash
# 📊 HYPERLOGLOG — Count Unique Items (Approximately)

# Problem: "How many UNIQUE visitors did our website get today?"
# With Sets: SADD + SCARD → exact, but uses ~50 bytes per member
#   10 million visitors = 500 MB of RAM!
# With HyperLogLog: ~12 KB TOTAL, regardless of count!
#   Accuracy: ±0.81% error (close enough for analytics!)

PFADD visitors:2025-01-15 "user:101" "user:102" "user:103"
PFADD visitors:2025-01-15 "user:101"    # Duplicate — handled!
PFADD visitors:2025-01-15 "user:104" "user:105"

PFCOUNT visitors:2025-01-15             # ~5 (approximate unique count)

# Merge multiple days
PFADD visitors:2025-01-16 "user:101" "user:106" "user:107"
PFMERGE visitors:week visitors:2025-01-15 visitors:2025-01-16
PFCOUNT visitors:week                    # ~7 unique visitors across both days

# ┌────────────────────┬──────────────────┬──────────────────┐
# │                    │  Set             │  HyperLogLog     │
# ├────────────────────┼──────────────────┼──────────────────┤
# │  10M unique items  │  ~500 MB         │  ~12 KB          │
# │  Accuracy          │  100% exact      │  ~99.19%         │
# │  List members?     │  ✅ Yes          │  ❌ No           │
# │  Use when          │  Need exact +    │  Need count only │
# │                    │  list members    │  (analytics)     │
# └────────────────────┴──────────────────┴──────────────────┘
```

```bash
# 📡 STREAMS — Append-Only Log (Like Kafka-Lite!)

# Streams are Redis's most powerful data structure for event-driven systems.
# Think: append-only log, message broker, event store.

# ═══════════════════════════════════════════════
# Basic Stream Operations
# ═══════════════════════════════════════════════

# XADD — Append event to stream (* = auto-generate ID)
XADD events:orders * action "order_placed" order_id "ORD-001" amount "1499" user "101"
XADD events:orders * action "payment_received" order_id "ORD-001" status "paid"
XADD events:orders * action "order_shipped" order_id "ORD-001" tracking "TRACK123"

# XLEN — Number of entries
XLEN events:orders                  # 3

# XRANGE — Read range of entries
XRANGE events:orders - +            # All entries (- = min, + = max)
XRANGE events:orders - + COUNT 2    # First 2 entries

# XREAD — Read new entries (can BLOCK like BLPOP!)
XREAD COUNT 10 BLOCK 5000 STREAMS events:orders $
# $ = only NEW entries from now on
# BLOCK 5000 = wait up to 5 seconds for new data
# Perfect for real-time consumers!

# XREVRANGE — Read in reverse (newest first)
XREVRANGE events:orders + - COUNT 5  # Last 5 events

# ═══════════════════════════════════════════════
# Consumer Groups (Multiple Consumers!)
# ═══════════════════════════════════════════════

# Create consumer group
XGROUP CREATE events:orders order-processors $ MKSTREAM

# Consumer 1 reads
XREADGROUP GROUP order-processors consumer-1 COUNT 1 STREAMS events:orders >

# Consumer 2 reads (gets DIFFERENT messages — load balanced!)
XREADGROUP GROUP order-processors consumer-2 COUNT 1 STREAMS events:orders >

# Acknowledge processing
XACK events:orders order-processors 1705312800000-0
```

```
📡 STREAMS vs LISTS vs PUB/SUB — When to Use What?

┌──────────────────┬────────────┬────────────┬──────────────┐
│  Feature         │  List      │  Pub/Sub   │  Stream      │
├──────────────────┼────────────┼────────────┼──────────────┤
│  Persistence     │  ✅ Yes    │  ❌ No     │  ✅ Yes      │
│  History         │  ❌ Pop =  │  ❌ Fire & │  ✅ Full log │
│                  │  gone      │  forget    │  kept        │
│  Consumer Groups │  ❌ No     │  ❌ No     │  ✅ Yes      │
│  Ack/Retry       │  ❌ No     │  ❌ No     │  ✅ Yes      │
│  Blocking Read   │  ✅ BLPOP  │  ✅ SUBSCRIBE│ ✅ XREAD    │
│  Fan-out         │  ❌ One    │  ✅ All    │  ✅ Groups   │
│                  │  consumer  │  subscribers│              │
│  Replay Old Msgs │  ❌ No     │  ❌ No     │  ✅ Yes      │
├──────────────────┼────────────┼────────────┼──────────────┤
│  Use Case        │  Simple    │  Real-time │  Event log,  │
│                  │  job queue │  broadcast │  reliable    │
│                  │            │  chat      │  messaging   │
└──────────────────┴────────────┴────────────┴──────────────┘

💡 Rule of thumb:
   Simple job queue → List (RPUSH + BLPOP)
   Broadcast to many → Pub/Sub
   Reliable, replayable events → Stream ✅
```

```bash
# 🌍 GEOSPATIAL INDEXES — Location-Based Features

# Store latitude/longitude, find nearby items!
# Uses Sorted Sets internally (score = geohash)

# ═══════════════════════════════════════════════
# Store Locations
# ═══════════════════════════════════════════════

# GEOADD key longitude latitude member
GEOADD restaurants 77.2090 28.6139 "delhi:karim"
GEOADD restaurants 72.8777 19.0760 "mumbai:leopold"
GEOADD restaurants 80.2707 13.0827 "chennai:saravana"
GEOADD restaurants 77.5946 12.9716 "bangalore:mtr"
GEOADD restaurants 78.4867 17.3850 "hyderabad:paradise"

# ═══════════════════════════════════════════════
# Find Nearby (Radius Search!)
# ═══════════════════════════════════════════════

# Find restaurants within 1500 km of Delhi
GEOSEARCH restaurants FROMLONLAT 77.2090 28.6139 BYRADIUS 1500 km ASC WITHCOORD WITHDIST
# Returns: hyderabad:paradise (1253 km), delhi:karim (0 km)

# Find restaurants within 500 km of Bangalore
GEOSEARCH restaurants FROMMEMBER "bangalore:mtr" BYRADIUS 500 km ASC WITHDIST
# Returns nearby restaurants sorted by distance

# ═══════════════════════════════════════════════
# Distance Between Two Points
# ═══════════════════════════════════════════════

GEODIST restaurants "delhi:karim" "mumbai:leopold" km
# "1153.xxx" km

GEODIST restaurants "bangalore:mtr" "chennai:saravana" km
# "290.xxx" km

# ═══════════════════════════════════════════════
# Get Coordinates
# ═══════════════════════════════════════════════

GEOPOS restaurants "delhi:karim"
# 1) "77.209..." 2) "28.613..."

# 💡 Use cases:
# • "Find restaurants near me" (Zomato/Swiggy)
# • "Show drivers within 5km" (Uber/Ola)
# • "Nearby ATMs" (banking apps)
# • Store locator
```

---

### Week 8–9: Pub/Sub, Transactions & Lua Scripting

| # | Topic | Priority | Est. Hours | Status |
|---|-------|----------|-----------|--------|
| 34 | **Pub/Sub** — SUBSCRIBE, UNSUBSCRIBE, PUBLISH, pattern subscriptions | 🔴 Critical | 3h | ⬜ |
| 35 | **Pub/Sub Use Cases** — chat, notifications, event broadcasting | 🔴 Critical | 2h | ⬜ |
| 36 | **Transactions** — MULTI, EXEC, DISCARD, WATCH | 🔴 Critical | 3h | ⬜ |
| 37 | **Optimistic Locking** — WATCH + MULTI/EXEC pattern | 🟡 Important | 2h | ⬜ |
| 38 | **Lua Scripting** — EVAL, EVALSHA, atomic multi-command scripts | 🟡 Important | 3h | ⬜ |
| 39 | **Lua Use Cases** — rate limiting, atomic operations, custom logic | 🟡 Important | 2h | ⬜ |

```bash
# 📢 PUB/SUB — Real-Time Messaging

# Pub/Sub is FIRE-AND-FORGET. No persistence. No history.
# If no one is listening when you publish → message is LOST.
# Perfect for real-time features where missing a message is OK.

# ═══════════════════════════════════════════════
# Terminal 1 — SUBSCRIBER (Listener)
# ═══════════════════════════════════════════════

SUBSCRIBE chat:room:general
# Waiting for messages...

# ═══════════════════════════════════════════════
# Terminal 2 — PUBLISHER (Sender)
# ═══════════════════════════════════════════════

PUBLISH chat:room:general "Hello everyone! 👋"
PUBLISH chat:room:general "Who's up for a coding session?"

# Terminal 1 will show:
# 1) "message"
# 2) "chat:room:general"
# 3) "Hello everyone! 👋"

# ═══════════════════════════════════════════════
# Pattern Subscriptions
# ═══════════════════════════════════════════════

# Subscribe to ALL chat rooms
PSUBSCRIBE chat:room:*

# Now receives messages from:
# chat:room:general, chat:room:cse, chat:room:random, etc.

# ─── Multiple Channels ──────────────────────
SUBSCRIBE chat:room:general notifications:user:101 alerts:system
```

```
📢 PUB/SUB — How It Works

  ┌──────────┐     PUBLISH                    ┌──────────┐
  │Publisher 1│──── "Hello!" ──►              │Subscriber│
  └──────────┘              │                 │    1     │
                            │                 └──────────┘
  ┌──────────┐              │    REDIS        ┌──────────┐
  │Publisher 2│──── "Hi!" ──►   CHANNEL  ────►│Subscriber│
  └──────────┘              │  chat:general   │    2     │
                            │                 └──────────┘
                            │                 ┌──────────┐
                            └────────────────►│Subscriber│
                                              │    3     │
                                              └──────────┘
  
  • Publishers don't know WHO is listening
  • Subscribers don't know WHO is sending
  • Multiple publishers → one channel → multiple subscribers
  • Message goes to ALL subscribers (fan-out/broadcast)
  • ⚠️ If subscriber disconnects, messages during downtime are LOST
```

```bash
# 🔐 TRANSACTIONS — Execute Multiple Commands Atomically

# MULTI starts a transaction. Commands are QUEUED (not executed yet).
# EXEC executes ALL queued commands atomically.
# If ANY command fails, the rest still execute (not like SQL transactions!)

# ═══════════════════════════════════════════════
# Basic Transaction
# ═══════════════════════════════════════════════

MULTI                              # Start transaction
SET user:101:balance 5000          # QUEUED
DECRBY user:101:balance 1000       # QUEUED (transfer out)
INCRBY user:102:balance 1000       # QUEUED (transfer in)
EXEC                               # Execute ALL at once, atomically

# No other command can run between these!

# DISCARD — Cancel transaction
MULTI
SET key1 "value1"
DISCARD                            # Cancel everything, nothing executed

# ═══════════════════════════════════════════════
# WATCH — Optimistic Locking (CAS)
# ═══════════════════════════════════════════════

# "Check-and-Set": If the watched key changes between 
# WATCH and EXEC, the transaction is ABORTED.

WATCH user:101:balance             # Watch this key
GET user:101:balance               # Read current value → "5000"

# If another client changes user:101:balance right now...

MULTI
DECRBY user:101:balance 1000       # QUEUED
INCRBY user:102:balance 1000       # QUEUED
EXEC                               
# Returns nil if user:101:balance was modified by someone else!
# → Transaction cancelled. Retry!

# This prevents: "Two servers both transferring money from same account"
```

```bash
# 🧩 LUA SCRIPTING — Run Custom Logic INSIDE Redis

# Lua scripts run ATOMICALLY in Redis (like a transaction but smarter).
# You can use if/else logic, loops, and access multiple keys.
# No other command runs while your script executes.

# ═══════════════════════════════════════════════
# Basic EVAL
# ═══════════════════════════════════════════════

# Syntax: EVAL "script" numkeys key1 key2 ... arg1 arg2 ...
# KEYS[1], KEYS[2] = key names
# ARGV[1], ARGV[2] = arguments

# Simple: Get and delete atomically
EVAL "local val = redis.call('GET', KEYS[1]); redis.call('DEL', KEYS[1]); return val" 1 mykey

# ═══════════════════════════════════════════════
# Rate Limiter (Sliding Window — Atomic!)
# ═══════════════════════════════════════════════

# This is the canonical Lua script use case:
EVAL "
    local key = KEYS[1]
    local limit = tonumber(ARGV[1])
    local window = tonumber(ARGV[2])
    
    local current = redis.call('GET', key)
    if current and tonumber(current) >= limit then
        return 0  -- Rate limit exceeded!
    end
    
    current = redis.call('INCR', key)
    if current == 1 then
        redis.call('EXPIRE', key, window)
    end
    
    return 1  -- Request allowed
" 1 rate:user:101 100 60
-- KEYS[1] = rate:user:101
-- ARGV[1] = 100 (max requests)
-- ARGV[2] = 60 (window in seconds)
-- Returns 1 (allowed) or 0 (rate limited)

# The ENTIRE script is atomic! No race condition possible.

# ═══════════════════════════════════════════════
# Transfer Funds (Atomic!)
# ═══════════════════════════════════════════════

EVAL "
    local from_balance = tonumber(redis.call('GET', KEYS[1]))
    local amount = tonumber(ARGV[1])
    
    if from_balance < amount then
        return redis.error_reply('Insufficient balance!')
    end
    
    redis.call('DECRBY', KEYS[1], amount)
    redis.call('INCRBY', KEYS[2], amount)
    return 'Transfer successful!'
" 2 balance:user:101 balance:user:102 500
-- Transfer ₹500 from user:101 to user:102
```

---

## 🔴 PHASE 3: PERSISTENCE, REPLICATION & SECURITY (Weeks 10–14)

### Week 10–11: Persistence Options

| # | Topic | Priority | Est. Hours | Status |
|---|-------|----------|-----------|--------|
| 40 | **No Persistence** — pure in-memory cache (fastest, data lost on restart) | 🟡 Important | 1h | ⬜ |
| 41 | **RDB Snapshots** — how it works, configuring save intervals, pros/cons | 🔴 Critical | 3h | ⬜ |
| 42 | **AOF (Append-Only File)** — how it works, rewrite/compaction, pros/cons | 🔴 Critical | 3h | ⬜ |
| 43 | **RDB vs AOF Tradeoffs** — when to use which | 🔴 Critical | 2h | ⬜ |
| 44 | **Hybrid Persistence** — RDB + AOF together | 🟡 Important | 1h | ⬜ |
| 45 | **Choosing the Right Strategy** — use case based decision | 🔴 Critical | 1h | ⬜ |

```
💾 PERSISTENCE OPTIONS — How Redis Saves Data to Disk

  ┌──────────────────────────────────────────────────────────────┐
  │                                                              │
  │  Problem: Redis stores data in RAM. RAM is volatile.         │
  │  Power off → data GONE. 💀                                   │
  │  Solution: Periodically save RAM data to DISK.               │
  │                                                              │
  │  THREE OPTIONS:                                              │
  │                                                              │
  │  1️⃣ NO PERSISTENCE                                           │
  │  ──────────────────                                          │
  │  Pure cache. Data lost on restart. Fastest.                  │
  │  Use when: Caching data that can be regenerated from DB.     │
  │  Config: Set no save rules, disable AOF                      │
  │                                                              │
  │                                                              │
  │  2️⃣ RDB (Redis Database Backup) — Point-in-time Snapshots   │
  │  ──────────────────────────────────────────────               │
  │                                                              │
  │  HOW: Fork child process → write ENTIRE dataset to .rdb file │
  │  WHEN: Periodically (e.g., every 5 min if 100+ keys changed)│
  │                                                              │
  │  ┌────────┐          ┌──────────┐         ┌────────┐        │
  │  │  RAM   │──fork──► │  Child   │──save──►│ .rdb   │        │
  │  │ (live) │          │ (copy)   │         │ (disk) │        │
  │  └────────┘          └──────────┘         └────────┘        │
  │                                                              │
  │  ✅ Compact file (good for backups)                          │
  │  ✅ Faster restarts (load .rdb into RAM)                     │
  │  ✅ No performance impact on main process                    │
  │  ❌ Data loss: up to last save interval (5 min of data lost) │
  │  ❌ Fork can use 2x memory momentarily                      │
  │                                                              │
  │  Config (redis.conf):                                        │
  │    save 900 1       # Save if 1 key changed in 900 sec      │
  │    save 300 10      # Save if 10 keys changed in 300 sec    │
  │    save 60 10000    # Save if 10000 keys changed in 60 sec  │
  │                                                              │
  │                                                              │
  │  3️⃣ AOF (Append-Only File) — Write Log                      │
  │  ──────────────────────────────────────                      │
  │                                                              │
  │  HOW: Log EVERY write command to a file. Replay on restart.  │
  │                                                              │
  │  ┌────────┐                    ┌────────────────────┐        │
  │  │  RAM   │──log command──►   │  appendonly.aof     │        │
  │  │ (live) │                   │  SET key1 "hello"   │        │
  │  └────────┘                   │  INCR counter       │        │
  │                               │  LPUSH list "item"  │        │
  │                               └────────────────────┘        │
  │                                                              │
  │  ✅ Minimal data loss (1 second or less with fsync everysec) │
  │  ✅ Human-readable log (can inspect/edit)                    │
  │  ❌ Larger file size (every command logged)                  │
  │  ❌ Slower restarts (must replay all commands)               │
  │  ❌ Slightly slower writes (fsync overhead)                  │
  │                                                              │
  │  fsync policies:                                             │
  │    appendfsync always    → Safest. Every write. Slow.        │
  │    appendfsync everysec  → Good balance. Max 1 sec loss. ✅  │
  │    appendfsync no        → OS decides. Fastest. Risky.       │
  │                                                              │
  │  AOF Rewrite: Periodically compact the AOF file              │
  │    (100 INCRs → one SET with final value)                    │
  │                                                              │
  └──────────────────────────────────────────────────────────────┘


  RDB vs AOF COMPARISON:

  ┌──────────────────────┬──────────────────┬──────────────────┐
  │  Criteria            │  RDB             │  AOF             │
  ├──────────────────────┼──────────────────┼──────────────────┤
  │  Data Safety         │  Minutes of loss │  ≤1 sec of loss  │
  │  File Size           │  Compact ✅      │  Larger           │
  │  Restart Speed       │  Fast ✅         │  Slower           │
  │  Write Performance   │  No impact       │  Slight overhead │
  │  Backup Friendly     │  ✅ Easy         │  ❌ Harder        │
  │  Human Readable      │  ❌ Binary       │  ✅ Text commands │
  │  Best For            │  Backups,        │  Data durability, │
  │                      │  disaster recov. │  financial data   │
  ├──────────────────────┴──────────────────┴──────────────────┤
  │                                                            │
  │  💡 RECOMMENDATION:                                        │
  │  • Just caching? → No persistence                          │
  │  • General use?  → RDB + AOF (hybrid) ✅                   │
  │  • Financial?    → AOF with appendfsync always             │
  │  • Backups only? → RDB                                     │
  │                                                            │
  └────────────────────────────────────────────────────────────┘
```

---

### Week 12–13: Replication, High Availability & Security

| # | Topic | Priority | Est. Hours | Status |
|---|-------|----------|-----------|--------|
| 46 | **Replication Basics** — master-replica, read replicas, sync process | 🔴 Critical | 3h | ⬜ |
| 47 | **Redis Sentinel** — automatic failover, monitoring, notification | 🔴 Critical | 3h | ⬜ |
| 48 | **Clustering** — data sharding, hash slots, cluster architecture | 🔴 Critical | 4h | ⬜ |
| 49 | **Authentication** — ACL, `requirepass`, user management | 🔴 Critical | 2h | ⬜ |
| 50 | **Network Security** — bind, protected-mode, firewall rules | 🟡 Important | 1h | ⬜ |
| 51 | **SSL/TLS Encryption** — encrypted connections | 🟡 Important | 1h | ⬜ |

```
🔄 REPLICATION — Read Scaling & Data Safety

  ┌──────────────────────────────────────────────────────────────┐
  │                                                              │
  │  MASTER-REPLICA Architecture:                                │
  │                                                              │
  │              ┌──────────┐                                    │
  │   Writes ──► │  MASTER  │                                    │
  │              │ (primary)│                                    │
  │              └────┬─────┘                                    │
  │                   │                                          │
  │          ┌────────┼────────┐         ASYNC replication       │
  │          ▼        ▼        ▼                                 │
  │     ┌────────┐ ┌────────┐ ┌────────┐                        │
  │     │Replica │ │Replica │ │Replica │                        │
  │     │   1    │ │   2    │ │   3    │                        │
  │     └────────┘ └────────┘ └────────┘                        │
  │       Reads ◄── Reads ◄── Reads ◄──                         │
  │                                                              │
  │  • Writes go to MASTER only                                  │
  │  • Reads can go to ANY replica (load balancing!)             │
  │  • Replicas are EVENTUALLY consistent                        │
  │  • If master dies → manually promote a replica               │
  │                                                              │
  │  Config (replica):                                           │
  │    replicaof 192.168.1.100 6379                              │
  │                                                              │
  └──────────────────────────────────────────────────────────────┘


  🛡️ REDIS SENTINEL — Automatic Failover

  ┌──────────────────────────────────────────────────────────────┐
  │                                                              │
  │  ┌──────────┐   ┌──────────┐   ┌──────────┐                │
  │  │Sentinel 1│   │Sentinel 2│   │Sentinel 3│  (monitoring)  │
  │  └─────┬────┘   └─────┬────┘   └─────┬────┘                │
  │        │              │              │                      │
  │        └──────────────┼──────────────┘                      │
  │                       │ monitors                            │
  │                       ▼                                     │
  │                ┌──────────┐                                 │
  │                │  MASTER  │                                 │
  │                └────┬─────┘                                 │
  │               ┌─────┼─────┐                                 │
  │               ▼     ▼     ▼                                 │
  │          ┌────────┐ ┌────────┐                              │
  │          │Replica │ │Replica │                              │
  │          │   1    │ │   2    │                              │
  │          └────────┘ └────────┘                              │
  │                                                              │
  │  If Master DIES:                                             │
  │  1. Sentinels detect failure (quorum vote)                  │
  │  2. Automatically promote Replica 1 to new Master           │
  │  3. Reconfigure remaining replicas to follow new Master     │
  │  4. Notify clients of new Master address                    │
  │  → Zero-downtime (or near-zero) failover!                   │
  │                                                              │
  └──────────────────────────────────────────────────────────────┘


  🔀 REDIS CLUSTER — Horizontal Sharding

  ┌──────────────────────────────────────────────────────────────┐
  │                                                              │
  │  Data is split across multiple masters by HASH SLOTS.        │
  │  16,384 hash slots distributed across masters.               │
  │                                                              │
  │  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐         │
  │  │  Master 1   │  │  Master 2   │  │  Master 3   │         │
  │  │ Slots 0-5460│  │Slots 5461-  │  │Slots 10923- │         │
  │  │             │  │    10922    │  │    16383    │         │
  │  │ ┌─────────┐ │  │ ┌─────────┐ │  │ ┌─────────┐ │         │
  │  │ │Replica 1│ │  │ │Replica 2│ │  │ │Replica 3│ │         │
  │  │ └─────────┘ │  │ └─────────┘ │  │ └─────────┘ │         │
  │  └─────────────┘  └─────────────┘  └─────────────┘         │
  │                                                              │
  │  Key "user:101" → CRC16 hash → slot 5532 → Master 2        │
  │  Key "user:102" → CRC16 hash → slot 1234 → Master 1        │
  │                                                              │
  │  ✅ Scale to TERABYTES of data                               │
  │  ✅ Automatic failover per shard                             │
  │  ❌ Multi-key operations limited to same slot                │
  │  ❌ More complex to operate                                  │
  │                                                              │
  │  Use when: Single Redis server can't hold all your data      │
  │            OR you need more write throughput                  │
  │                                                              │
  └──────────────────────────────────────────────────────────────┘
```

---

### Week 14: Monitoring & Performance

| # | Topic | Priority | Est. Hours | Status |
|---|-------|----------|-----------|--------|
| 52 | **INFO command** — server stats, memory, clients, replication info | 🔴 Critical | 2h | ⬜ |
| 53 | **MONITOR command** — real-time command logging | 🟡 Important | 1h | ⬜ |
| 54 | **Slow Log Analysis** — SLOWLOG, identifying slow commands | 🔴 Critical | 2h | ⬜ |
| 55 | **Memory Management** — `maxmemory`, eviction policies | 🔴 Critical | 3h | ⬜ |
| 56 | **redis-benchmark** — performance testing | 🟡 Important | 1h | ⬜ |
| 57 | **RedisInsight / RedisCommander** — GUI monitoring tools | 🟡 Important | 1h | ⬜ |

```bash
# 📊 MONITORING & PERFORMANCE COMMANDS

# ─── INFO — The Swiss Army Knife ─────────────
INFO                              # Everything
INFO server                       # Server info, version, uptime
INFO memory                       # RAM usage, peak, fragmentation
INFO clients                      # Connected clients
INFO stats                        # Hit/miss ratio, ops/sec
INFO replication                  # Master/replica status
INFO keyspace                     # Keys per database

# Key metrics to watch:
# used_memory_human: 45.00M       ← Current RAM usage
# used_memory_peak_human: 60.00M  ← Peak RAM usage
# keyspace_hits: 1000000           ← Cache hits
# keyspace_misses: 50000           ← Cache misses
# Hit ratio = hits / (hits + misses) = 95.2% ← Good!
# connected_clients: 150           ← Current connections
# instantaneous_ops_per_sec: 12500 ← Commands/second

# ─── SLOWLOG — Find Slow Commands ────────────
CONFIG SET slowlog-log-slower-than 10000  # Log commands >10ms
SLOWLOG GET 10                            # Last 10 slow commands
SLOWLOG LEN                               # Number of slow entries
SLOWLOG RESET                              # Clear slow log

# ─── MONITOR — Real-time Command Stream ──────
MONITOR                                    # Shows every command in real-time
# ⚠️ NEVER use in production (kills performance!)

# ─── MEMORY USAGE ────────────────────────────
MEMORY USAGE user:101              # Bytes used by specific key
MEMORY DOCTOR                      # Memory health report
DBSIZE                             # Total keys in current DB
```

```
🧠 MEMORY MANAGEMENT — Eviction Policies

  When Redis reaches maxmemory, it must EVICT (delete) keys.
  The eviction policy determines WHICH keys to remove.

  ┌──────────────────────────┬──────────────────────────────────┐
  │  Policy                  │  Behavior                        │
  ├──────────────────────────┼──────────────────────────────────┤
  │  noeviction              │  Return error on new writes      │
  │  (default)               │  ❌ Writes fail!                 │
  ├──────────────────────────┼──────────────────────────────────┤
  │  allkeys-lru ✅          │  Evict LEAST recently used key   │
  │  (RECOMMENDED for cache) │  from ALL keys. Best for caches! │
  ├──────────────────────────┼──────────────────────────────────┤
  │  volatile-lru            │  Evict LRU, but only keys WITH   │
  │                          │  an expiration set               │
  ├──────────────────────────┼──────────────────────────────────┤
  │  allkeys-lfu             │  Evict LEAST frequently used key │
  │                          │  "Rarely accessed = evict first" │
  ├──────────────────────────┼──────────────────────────────────┤
  │  volatile-lfu            │  LFU only on keys with expiration│
  ├──────────────────────────┼──────────────────────────────────┤
  │  allkeys-random          │  Evict random key                │
  ├──────────────────────────┼──────────────────────────────────┤
  │  volatile-random         │  Evict random key with expiration│
  ├──────────────────────────┼──────────────────────────────────┤
  │  volatile-ttl            │  Evict keys with shortest TTL    │
  │                          │  "About to expire anyway"        │
  └──────────────────────────┴──────────────────────────────────┘

  Config:
    maxmemory 2gb
    maxmemory-policy allkeys-lru

  💡 Recommendation:
     Pure cache → allkeys-lru (most common)
     Mixed cache + persistent data → volatile-lru
     All data equally important → noeviction (fail on full)
```

---

## 🏆 PHASE 4: PRODUCTION — Modules, Config & Enterprise (Weeks 15–18)

### Week 15–16: Redis Modules & Production Config

| # | Topic | Priority | Est. Hours | Status |
|---|-------|----------|-----------|--------|
| 58 | **RedisJSON** — store, query, modify JSON documents natively | 🟡 Important | 2h | ⬜ |
| 59 | **RediSearch** — full-text search, secondary indexes | 🟡 Important | 3h | ⬜ |
| 60 | **RedisTimeSeries** — time-series data, aggregation | 🟢 Good to know | 2h | ⬜ |
| 61 | **RedisBloom** — probabilistic data structures | 🟢 Good to know | 1h | ⬜ |
| 62 | **redis.conf** — important configuration parameters | 🔴 Critical | 3h | ⬜ |
| 63 | **Backup & Recovery** — RDB/AOF file management, restore process | 🔴 Critical | 2h | ⬜ |
| 64 | **Upgrading Redis** — minimizing downtime, version migration | 🟡 Important | 1h | ⬜ |
| 65 | **Disaster Recovery** — failover procedures, backup strategies | 🔴 Critical | 2h | ⬜ |

### Week 17–18: Integration & Real-World Application

| # | Topic | Priority | Est. Hours | Status |
|---|-------|----------|-----------|--------|
| 66 | **Redis with Python** — redis-py, connection pooling, patterns | 🔴 Critical | 4h | ⬜ |
| 67 | **Redis with Node.js** — ioredis, caching middleware | 🟡 Important | 3h | ⬜ |
| 68 | **Caching Patterns** — cache-aside, write-through, write-behind | 🔴 Critical | 3h | ⬜ |
| 69 | **Redis Enterprise** — when to consider, features, pricing | 🟢 Good to know | 1h | ⬜ |
| 70 | **Full Application Project** — integrate Redis into a real app | 🔴 Critical | 6h | ⬜ |

```python
# 🐍 REDIS WITH PYTHON — Complete Integration

# pip install redis

import redis
import json
import time
from functools import wraps

# ═══════════════════════════════════════════════
# Connection
# ═══════════════════════════════════════════════

# Simple connection
r = redis.Redis(host='localhost', port=6379, db=0, decode_responses=True)

# Connection pool (RECOMMENDED for production)
pool = redis.ConnectionPool(host='localhost', port=6379, db=0, 
                           max_connections=20, decode_responses=True)
r = redis.Redis(connection_pool=pool)

# Verify connection
print(r.ping())  # True


# ═══════════════════════════════════════════════
# Cache-Aside Pattern (Most Common!)
# ═══════════════════════════════════════════════

def get_student(student_id: int) -> dict:
    cache_key = f"student:{student_id}"
    
    # 1. Check cache first
    cached = r.get(cache_key)
    if cached:
        print(f"🟢 Cache HIT for {cache_key}")
        return json.loads(cached)
    
    # 2. Cache MISS → query database
    print(f"🔴 Cache MISS for {cache_key}")
    student = query_database(student_id)  # Expensive DB query
    
    # 3. Store in cache for next time (TTL: 5 minutes)
    r.set(cache_key, json.dumps(student), ex=300)
    
    return student

def query_database(student_id):
    """Simulated slow database query"""
    time.sleep(0.1)  # 100ms
    return {"id": student_id, "name": "Rahul", "cgpa": 8.5}


# First call: 🔴 Cache MISS (100ms)
# Second call: 🟢 Cache HIT (<1ms) — 100x faster!


# ═══════════════════════════════════════════════
# Decorator-Based Caching (Reusable!)
# ═══════════════════════════════════════════════

def cached(ttl: int = 300, prefix: str = "cache"):
    """Universal caching decorator"""
    def decorator(func):
        @wraps(func)
        def wrapper(*args, **kwargs):
            # Build cache key from function name + arguments
            key = f"{prefix}:{func.__name__}:{args}:{kwargs}"
            
            # Check cache
            result = r.get(key)
            if result:
                return json.loads(result)
            
            # Cache miss
            result = func(*args, **kwargs)
            r.set(key, json.dumps(result), ex=ttl)
            return result
        return wrapper
    return decorator

@cached(ttl=600)
def get_leaderboard(game: str, limit: int = 10):
    """Expensive computation, cached for 10 minutes"""
    # ... complex query ...
    return {"game": game, "top_players": ["Rahul", "Priya"]}


# ═══════════════════════════════════════════════
# Session Management
# ═══════════════════════════════════════════════

import uuid

def create_session(user_id: int, data: dict) -> str:
    """Create a new session, returns session token"""
    token = str(uuid.uuid4())
    session_key = f"session:{token}"
    
    r.hset(session_key, mapping={
        "user_id": str(user_id),
        "name": data.get("name", ""),
        "role": data.get("role", "user"),
        "created_at": str(time.time()),
    })
    r.expire(session_key, 1800)  # 30 minutes
    
    return token

def get_session(token: str) -> dict | None:
    """Get session data by token"""
    session_key = f"session:{token}"
    data = r.hgetall(session_key)
    
    if data:
        r.expire(session_key, 1800)  # Reset TTL on activity
        return data
    return None

def destroy_session(token: str):
    """Logout — delete session"""
    r.delete(f"session:{token}")


# ═══════════════════════════════════════════════
# Rate Limiter (Sliding Window)
# ═══════════════════════════════════════════════

def is_rate_limited(user_id: int, max_requests: int = 100, window_seconds: int = 60) -> bool:
    """Returns True if user exceeded rate limit"""
    key = f"rate:{user_id}"
    
    # Use Lua script for atomicity
    lua_script = """
    local current = redis.call('GET', KEYS[1])
    if current and tonumber(current) >= tonumber(ARGV[1]) then
        return 1
    end
    current = redis.call('INCR', KEYS[1])
    if current == 1 then
        redis.call('EXPIRE', KEYS[1], tonumber(ARGV[2]))
    end
    return 0
    """
    
    result = r.eval(lua_script, 1, key, max_requests, window_seconds)
    return result == 1


# ═══════════════════════════════════════════════
# Real-Time Leaderboard
# ═══════════════════════════════════════════════

class Leaderboard:
    def __init__(self, name: str):
        self.key = f"leaderboard:{name}"
    
    def add_score(self, player: str, score: float):
        r.zadd(self.key, {player: score})
    
    def increment_score(self, player: str, points: float):
        r.zincrby(self.key, points, player)
    
    def get_rank(self, player: str) -> int:
        rank = r.zrevrank(self.key, player)
        return rank + 1 if rank is not None else None
    
    def get_score(self, player: str) -> float:
        return r.zscore(self.key, player)
    
    def top_n(self, n: int = 10) -> list:
        return r.zrevrange(self.key, 0, n - 1, withscores=True)
    
    def total_players(self) -> int:
        return r.zcard(self.key)


# Usage
lb = Leaderboard("dsa-contest")
lb.add_score("Rahul", 850)
lb.add_score("Priya", 920)
lb.add_score("Amit", 780)
lb.increment_score("Rahul", 100)  # Rahul solved another problem!

print(f"🏆 Top 3: {lb.top_n(3)}")
print(f"Rahul's rank: #{lb.get_rank('Rahul')}")
```

```
🔄 CACHING PATTERNS — When & How to Cache

┌────────────────────────────────────────────────────────────────┐
│                                                                │
│  1. CACHE-ASIDE (Lazy Loading) — MOST COMMON ✅               │
│  ──────────────────────────────────────────────                 │
│  App checks cache → miss → queries DB → stores in cache       │
│                                                                │
│  Client → Cache? → HIT → return cached data                   │
│                 → MISS → DB query → store in cache → return   │
│                                                                │
│  ✅ Only caches what's needed                                  │
│  ❌ First request always slow (cold start)                    │
│  ❌ Stale data possible                                       │
│                                                                │
│                                                                │
│  2. WRITE-THROUGH — Write to Cache AND DB simultaneously      │
│  ────────────────────────────────────────────────────          │
│  App → write to cache AND DB at the same time                 │
│                                                                │
│  ✅ Cache always up-to-date                                   │
│  ❌ Write latency (must write twice)                          │
│  ❌ Caches data that may never be read                        │
│                                                                │
│                                                                │
│  3. WRITE-BEHIND (Write-Back) — Write cache, async DB         │
│  ────────────────────────────────────────────────────          │
│  App → write to cache → queue → async write to DB             │
│                                                                │
│  ✅ Fastest writes                                            │
│  ❌ Risk of data loss if cache crashes before DB write         │
│                                                                │
│                                                                │
│  4. READ-THROUGH — Cache manages DB reads transparently       │
│  ────────────────────────────────────────────────────          │
│  App → ask cache → cache queries DB if needed                 │
│                                                                │
│  ✅ Simple app code                                           │
│  ❌ Requires smart cache layer                                │
│                                                                │
│                                                                │
│  💡 For most apps: Cache-Aside + TTL = best starting point     │
│                                                                │
└────────────────────────────────────────────────────────────────┘

  CACHE INVALIDATION — "The Hardest Problem in CS" 😅

  ┌────────────────────────┬─────────────────────────────────────┐
  │  Strategy              │  How                                │
  ├────────────────────────┼─────────────────────────────────────┤
  │  TTL-based             │  SET key value EX 300               │
  │  (time-to-live)        │  Data expires automatically.        │
  │                        │  Simple, but stale for TTL duration.│
  ├────────────────────────┼─────────────────────────────────────┤
  │  Event-based           │  On DB update → DEL cache key       │
  │  (explicit invalidation│  Immediate consistency.             │
  │                        │  Requires discipline.                │
  ├────────────────────────┼─────────────────────────────────────┤
  │  Version-based         │  cache:v2:user:101 (bump version)  │
  │                        │  Old versions expire naturally.      │
  └────────────────────────┴─────────────────────────────────────┘
```

---

## 📊 COMPLETE TIMELINE OVERVIEW

```
WEEK  1     ████ What is Redis, Install, Basic Commands, SET/GET
WEEK  2     ████ Strings (INCR, MSET, MGET), Lists (LPUSH, RPUSH, BLPOP)
WEEK  3     ████ Sets (SADD, SINTER, SUNION), Hashes (HSET, HGET, HGETALL)
WEEK  4     ████ Sorted Sets (ZADD, ZRANGE, ZREVRANGE, ZINCRBY, leaderboards)
             ──── 🎯 MILESTONE: Master all 5 core data structures ────

WEEK  5     ████ Key Management, Naming, Expiration, Pipelining, Batch Ops
WEEK  6     ████ Bitmaps (DAU tracking), HyperLogLog (unique counts)
WEEK  7     ████ Streams (event log, consumer groups), Geospatial (nearby)
WEEK  8     ████ Pub/Sub (chat, notifications), Transactions (MULTI/EXEC)
WEEK  9     ████ Lua Scripting (EVAL, atomic operations), WATCH/Optimistic Lock
             ──── 🎯 MILESTONE: Use advanced features in real apps ────

WEEK 10     ████ RDB Snapshots — config, backup, restore
WEEK 11     ████ AOF — append-only, rewrite, hybrid persistence
WEEK 12     ████ Replication, Redis Sentinel (auto-failover)
WEEK 13     ████ Clustering, Authentication, SSL/TLS
WEEK 14     ████ Monitoring (INFO, SLOWLOG), Memory Management, Eviction
             ──── 🎯 MILESTONE: Production-ready Redis knowledge ────

WEEK 15     ████ Redis Modules — RedisJSON, RediSearch, TimeSeries, Bloom
WEEK 16     ████ redis.conf, Backup/Recovery, Disaster Recovery
WEEK 17     ████ Redis + Python (redis-py), Caching Patterns
WEEK 18     ████ Full Application Project — Integrate Redis into real app
             ──── 🏆 MILESTONE: Build & deploy Redis-powered apps ────
```

---

## 🏋️ PROJECTS TO BUILD (Phase-wise)

| Phase | Project | Redis Features Used | Resume Value |
|-------|---------|-------------------|-------------|
| 🟢 Week 4 | **CLI Leaderboard System** | Sorted Sets, Strings, Hashes | ⭐⭐ |
| 🟡 Week 7 | **Real-Time Chat App** | Pub/Sub, Lists, Streams | ⭐⭐⭐ |
| 🟡 Week 9 | **API Rate Limiter** | Lua Scripting, Strings, Sorted Sets | ⭐⭐⭐ |
| 🔴 Week 14 | **Session-Based Auth System** | Hashes, Expiration, Replication | ⭐⭐⭐⭐ |
| 🏆 Week 18 | **Full-Stack App with Caching** | All data types, caching patterns, monitoring | ⭐⭐⭐⭐⭐ |

---

## 📚 BEST RESOURCES (Curated)

| Category | Resource | Type | Best For |
|----------|----------|------|----------|
| 🌐 Official | **redis.io/docs** | Documentation | Complete command reference |
| 🌐 Interactive | **try.redis.io** | Online CLI | Practice without installing |
| 📖 Book | **Redis in Action** (Josiah Carlson) | Book | Practical patterns |
| 📖 Book | **Redis Essentials** (Maxwell Da Silva) | Book | Quick start |
| 🎥 YouTube | **TechWorld with Nana** — Redis Crash Course | Video | Best beginner intro |
| 🎥 YouTube | **Fireship** — Redis in 100 Seconds | Video | Quick overview |
| 🎥 YouTube | **Hussein Nasser** — Redis Deep Dives | Video | Architecture concepts |
| 🌐 Website | **roadmap.sh/redis** | Roadmap | Visual learning path |
| 🌐 Tool | **RedisInsight** | GUI | Visual Redis management |
| 🌐 University | **redis.io/university** | Free Course | Official Redis courses (FREE!) |
| 🎥 YouTube | **Redis Official Channel** | Video | Talks, tutorials |

---

## 💼 Interview Angle — Redis Questions Companies Ask

```
┌────────────────────────────────────────────────────────────────────┐
│                TOP REDIS INTERVIEW QUESTIONS                       │
├────────────────────────────────────────────────────────────────────┤
│                                                                    │
│  BEGINNER:                                                         │
│  1. What is Redis? How is it different from a regular database?    │
│  2. Name 5 Redis data types and when to use each.                  │
│  3. What is TTL? How does key expiration work?                     │
│  4. Explain the difference between SET NX and SET XX.              │
│  5. How would you implement a simple cache using Redis?            │
│                                                                    │
│  INTERMEDIATE:                                                     │
│  6. RDB vs AOF — trade-offs? When to use which?                    │
│  7. How would you build a rate limiter with Redis?                 │
│  8. Explain Redis Pub/Sub. When would you use it vs Streams?       │
│  9. What is pipelining? Why does it improve performance?           │
│  10. How does Redis handle concurrent writes? (single-threaded)    │
│                                                                    │
│  ADVANCED:                                                         │
│  11. Design a real-time leaderboard for 10M users.                 │
│  12. Explain Redis Cluster architecture. How do hash slots work?   │
│  13. What are eviction policies? Which would you use for a cache?  │
│  14. How would you implement distributed locking with Redis?       │
│  15. What is cache stampede/thundering herd? How to prevent it?    │
│                                                                    │
│  SYSTEM DESIGN (uses Redis):                                       │
│  16. Design URL shortener (Redis for mapping short→long)           │
│  17. Design Twitter's trending topics (Sorted Sets)                │
│  18. Design a session management system for 1M users               │
│  19. Design a real-time notification system (Streams/Pub-Sub)      │
│  20. Design API rate limiting for a cloud service                  │
│                                                                    │
│  Companies that test Redis:                                        │
│  Almost ALL backend/full-stack interviews.                         │
│  Amazon, Google, Flipkart, Swiggy, Zomato, Razorpay, Uber,       │
│  Twitter, Instagram, Discord, Shopify                              │
└────────────────────────────────────────────────────────────────────┘
```

---

## 🧠 REDIS MENTAL MODEL — The Complete Picture

```
┌─────────────────────────────────────────────────────────────────┐
│                                                                 │
│   REDIS = Your application's HIGH-SPEED MEMORY                  │
│                                                                 │
│   Think of it as:                                               │
│   📝 A giant shared dictionary accessible over the network      │
│   ⚡ Operating at the speed of RAM, not disk                   │
│   🔒 With built-in atomicity (single-threaded execution)        │
│   ⏰ With automatic expiration (set it and forget it)           │
│   📡 With built-in messaging (Pub/Sub + Streams)               │
│   💾 With optional persistence (survive restarts)               │
│   🔄 With replication (data safety + read scaling)             │
│                                                                 │
│   WHEN to reach for Redis:                                      │
│   "I need this data FAST and FREQUENTLY"     → Cache it         │
│   "I need to count things atomically"        → INCR             │
│   "I need real-time rankings"                → Sorted Set       │
│   "I need to broadcast messages"             → Pub/Sub          │
│   "I need reliable event processing"         → Streams          │
│   "I need to rate-limit API calls"           → String + TTL     │
│   "I need session management"                → Hash + TTL       │
│   "I need unique counting at scale"          → HyperLogLog      │
│   "I need nearby location search"            → Geospatial       │
│                                                                 │
│   WHEN NOT to use Redis:                                        │
│   ❌ As primary database (use PostgreSQL/MongoDB)               │
│   ❌ For data larger than RAM                                   │
│   ❌ For complex queries (JOINs, aggregations)                  │
│   ❌ For data that must never be lost (use DB as source of truth)│
│                                                                 │
│   GOLDEN RULE:                                                  │
│   Database = Source of Truth (persistent, queryable)             │
│   Redis = Speed Layer (fast, ephemeral, complementary)          │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
```

---

