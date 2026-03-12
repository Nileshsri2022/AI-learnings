

# 🔌 COMPLETE API DESIGN & BUILDING ROADMAP
### From Zero to Production-Ready APIs — Structured & Actionable

---

## 📍 Where You Are → Where You'll Go

```
🟢 BEGINNER            🟡 INTERMEDIATE          🔴 ADVANCED            🏆 PRO
   (Weeks 1-4)            (Weeks 5-10)             (Weeks 11-16)         (Weeks 17-20)
   
   What is API?,          RESTful Design,          Security, Auth,       Microservices,
   HTTP, Methods,         CRUD, Pagination,        Performance,          Real-time APIs,
   Status Codes           Error Handling           Caching, Testing      Compliance
```

---

## 🧒 ELI5: What Even Is an API?

```
🍕 The Restaurant Analogy:

  YOU (Client/Frontend)
    │
    │  "I want a Paneer Pizza"  ← REQUEST
    │
    ▼
  WAITER (API)  ← The middleman. Takes your order,
    │               knows the menu (endpoints),
    │               talks to the kitchen.
    │
    ▼
  KITCHEN (Server/Database)
    │
    │  🍕 Here's your pizza   ← RESPONSE
    │
    ▼
  YOU get your pizza + bill (status: 200 OK)
  
  ─────────────────────────────────────
  If pizza is unavailable → 404 Not Found
  If you didn't say which pizza → 400 Bad Request
  If kitchen is on fire → 500 Internal Server Error
  If you haven't paid membership → 401 Unauthorized
```

---

## 🟢 PHASE 1: THE BASICS — Understanding APIs & HTTP (Weeks 1–4)

### Week 1: What Are APIs + HTTP Fundamentals

| # | Topic | Priority | Est. Hours | Status |
|---|-------|----------|-----------|--------|
| 1 | **What are APIs** — definition, types (Web, OS, Library, Hardware) | 🔴 Critical | 2h | ⬜ |
| 2 | **HTTP Protocol** — request/response cycle, client-server model | 🔴 Critical | 2h | ⬜ |
| 3 | **HTTP Versions** — HTTP/1.0 → 1.1 → 2.0 → 3.0 (QUIC) | 🟡 Important | 1h | ⬜ |
| 4 | **Understand TCP/IP** — how data travels over the internet | 🟡 Important | 2h | ⬜ |
| 5 | **Basics of DNS** — domain resolution, how URLs become IP addresses | 🟡 Important | 1h | ⬜ |

```
📡 HTTP Request/Response — What Actually Happens

  Client (Browser/App)                    Server (Backend)
  ─────────────────────                   ─────────────────
         │                                       │
         │  ──── HTTP REQUEST ──────────────►    │
         │  │ Method: GET                   │    │
         │  │ URL: /api/students/101        │    │
         │  │ Headers:                      │    │
         │  │   Authorization: Bearer xyz   │    │
         │  │   Content-Type: application/  │    │
         │  │                  json         │    │
         │  │ Body: (empty for GET)         │    │
         │  └───────────────────────────────┘    │
         │                                       │
         │                          Processing...│
         │                          DB Query...  │
         │                                       │
         │  ◄──── HTTP RESPONSE ────────────     │
         │  │ Status: 200 OK                │    │
         │  │ Headers:                      │    │
         │  │   Content-Type: application/  │    │
         │  │                  json         │    │
         │  │ Body:                         │    │
         │  │ {                             │    │
         │  │   "name": "Rahul",            │    │
         │  │   "roll_no": 101,             │    │
         │  │   "cgpa": 8.5                 │    │
         │  │ }                             │    │
         │  └───────────────────────────────┘    │
         │                                       │
```

```
🔄 HTTP Versions — Evolution at a Glance

┌──────────┬───────────────────────────────────────────────────┐
│ Version  │ Key Feature                                       │
├──────────┼───────────────────────────────────────────────────┤
│ HTTP/1.0 │ One request per connection (slow!)                │
│          │ Like calling a shop, asking one thing, hanging up │
├──────────┼───────────────────────────────────────────────────┤
│ HTTP/1.1 │ Keep-alive connections (reuse connection)         │
│          │ Like staying on the phone for multiple questions  │
│          │ ⚠️ Head-of-line blocking                         │
├──────────┼───────────────────────────────────────────────────┤
│ HTTP/2   │ Multiplexing (many requests on one connection)    │
│          │ Binary framing, header compression                │
│          │ Like a highway with multiple lanes 🛣️             │
├──────────┼───────────────────────────────────────────────────┤
│ HTTP/3   │ Uses QUIC (UDP-based, not TCP)                    │
│          │ Faster handshakes, no head-of-line blocking       │
│          │ Like a bullet train — minimal stops 🚄            │
└──────────┴───────────────────────────────────────────────────┘
```

---

### Week 2: HTTP Methods, Status Codes & Headers

| # | Topic | Priority | Est. Hours | Status |
|---|-------|----------|-----------|--------|
| 6 | **HTTP Methods** — GET, POST, PUT, PATCH, DELETE, OPTIONS, HEAD | 🔴 Critical | 2h | ⬜ |
| 7 | **HTTP Status Codes** — 1xx, 2xx, 3xx, 4xx, 5xx families | 🔴 Critical | 2h | ⬜ |
| 8 | **HTTP Headers** — request headers, response headers, custom headers | 🔴 Critical | 2h | ⬜ |
| 9 | **HTTP Caching** — `Cache-Control`, `ETag`, `Last-Modified`, `Expires` | 🟡 Important | 2h | ⬜ |

```
🔧 HTTP Methods — The CRUD Mapping

┌──────────┬───────────┬─────────────────────┬───────────┬────────────┐
│  Method  │  CRUD     │  Example            │ Body?     │ Idempotent?│
├──────────┼───────────┼─────────────────────┼───────────┼────────────┤
│  GET     │  Read     │ GET /students       │ ❌ No     │ ✅ Yes     │
│          │           │ GET /students/101   │           │            │
├──────────┼───────────┼─────────────────────┼───────────┼────────────┤
│  POST    │  Create   │ POST /students      │ ✅ Yes    │ ❌ No      │
│          │           │ Body: {name, cgpa}  │           │            │
├──────────┼───────────┼─────────────────────┼───────────┼────────────┤
│  PUT     │  Replace  │ PUT /students/101   │ ✅ Yes    │ ✅ Yes     │
│          │  (Full)   │ Body: {ALL fields}  │           │            │
├──────────┼───────────┼─────────────────────┼───────────┼────────────┤
│  PATCH   │  Update   │ PATCH /students/101 │ ✅ Yes    │ ❌ No*     │
│          │  (Partial)│ Body: {cgpa: 9.0}   │           │            │
├──────────┼───────────┼─────────────────────┼───────────┼────────────┤
│  DELETE  │  Delete   │ DELETE /students/101│ ❌ No     │ ✅ Yes     │
├──────────┼───────────┼─────────────────────┼───────────┼────────────┤
│  OPTIONS │  Preflight│ OPTIONS /students   │ ❌ No     │ ✅ Yes     │
│          │  (CORS)   │                     │           │            │
├──────────┼───────────┼─────────────────────┼───────────┼────────────┤
│  HEAD    │  Meta only│ HEAD /students      │ ❌ No     │ ✅ Yes     │
│          │  (no body)│ (returns headers)   │           │            │
└──────────┴───────────┴─────────────────────┴───────────┴────────────┘

* PATCH can be idempotent depending on implementation

💡 Idempotent = calling it 10 times has the same effect as calling once
   Like pressing elevator button — pressing 50 times doesn't call 50 lifts
```

```
📊 HTTP Status Codes — The Complete Cheat Sheet

┌───────┬───────────────────────┬────────────────────────────────────────┐
│ Code  │ Name                  │ Real-Life Analogy 🇮🇳                  │
├───────┼───────────────────────┼────────────────────────────────────────┤
│       │    🟢 2xx SUCCESS     │                                        │
├───────┼───────────────────────┼────────────────────────────────────────┤
│ 200   │ OK                    │ Order delivered successfully ✅        │
│ 201   │ Created               │ New account banaya — welcome! 🎉      │
│ 204   │ No Content            │ Deleted successfully, nothing to show  │
├───────┼───────────────────────┼────────────────────────────────────────┤
│       │    🟡 3xx REDIRECT    │                                        │
├───────┼───────────────────────┼────────────────────────────────────────┤
│ 301   │ Moved Permanently     │ Shop shifted to new location forever   │
│ 302   │ Found (Temporary)     │ Shop temporarily at different address  │
│ 304   │ Not Modified          │ Menu hasn't changed, use cached copy   │
├───────┼───────────────────────┼────────────────────────────────────────┤
│       │    🔴 4xx CLIENT ERR  │                                        │
├───────┼───────────────────────┼────────────────────────────────────────┤
│ 400   │ Bad Request           │ "Ek plate hawa lao" — makes no sense  │
│ 401   │ Unauthorized          │ VIP lounge without pass — kaun ho tum?│
│ 403   │ Forbidden             │ Pass hai but entry allowed nahi        │
│ 404   │ Not Found             │ "Ye dish hamre menu mein nahi hai"     │
│ 405   │ Method Not Allowed    │ "Yahan delivery nahi hoti, dine-in hi"│
│ 409   │ Conflict              │ Two people booking same seat           │
│ 422   │ Unprocessable Entity  │ Form filled but email format galat     │
│ 429   │ Too Many Requests     │ "Bhai, thoda ruk! Itna order mat de!" │
├───────┼───────────────────────┼────────────────────────────────────────┤
│       │    💀 5xx SERVER ERR  │                                        │
├───────┼───────────────────────┼────────────────────────────────────────┤
│ 500   │ Internal Server Error │ Kitchen mein aag lag gayi 🔥           │
│ 502   │ Bad Gateway           │ Delivery boy ne galat address se laya  │
│ 503   │ Service Unavailable   │ Restaurant band hai — maintenance 🔧  │
│ 504   │ Gateway Timeout       │ Order diya but kitchen ne reply nahi   │
└───────┴───────────────────────┴────────────────────────────────────────┘
```

```
📨 Important HTTP Headers

┌─────────────────────────────┬──────────────────────────────────────┐
│  Header                     │  Purpose                             │
├─────────────────────────────┼──────────────────────────────────────┤
│  REQUEST HEADERS            │                                      │
├─────────────────────────────┼──────────────────────────────────────┤
│  Authorization              │  Credentials (Bearer token, Basic)   │
│  Content-Type               │  What format I'm sending (JSON, XML) │
│  Accept                     │  What format I want back             │
│  User-Agent                 │  Which browser/app is calling        │
│  Cookie                     │  Session data from previous visits   │
│  Cache-Control              │  Caching preferences                 │
│  X-Request-ID               │  Unique ID for tracking/debugging    │
├─────────────────────────────┼──────────────────────────────────────┤
│  RESPONSE HEADERS           │                                      │
├─────────────────────────────┼──────────────────────────────────────┤
│  Content-Type               │  Format of response body             │
│  Set-Cookie                 │  Store data in browser               │
│  Cache-Control              │  How long to cache this response     │
│  ETag                       │  Version hash of the resource        │
│  X-RateLimit-Remaining      │  How many requests you have left     │
│  Access-Control-Allow-Origin│  CORS — who can call this API        │
│  Retry-After                │  Wait this long before retrying      │
└─────────────────────────────┴──────────────────────────────────────┘
```

---

### Week 3: URLs, Cookies, CORS & Content Negotiation

| # | Topic | Priority | Est. Hours | Status |
|---|-------|----------|-----------|--------|
| 10 | **URL, Query & Path Parameters** — anatomy of a URL, when to use which | 🔴 Critical | 2h | ⬜ |
| 11 | **Cookies** — session cookies, persistent cookies, secure flags | 🟡 Important | 2h | ⬜ |
| 12 | **Content Negotiation** — `Accept`, `Content-Type`, format handling | 🟡 Important | 1h | ⬜ |
| 13 | **CORS** — Same-Origin Policy, preflight requests, configuration | 🔴 Critical | 3h | ⬜ |

```
🔗 Anatomy of a URL

https://api.college.edu:8080/v2/students/101/marks?semester=5&subject=dsa#section2
└─┬──┘ └──────┬───────┘└┬──┘└┬┘└───────┬────────┘ └──────────┬──────────┘ └───┬──┘
  │          │          │   │         │                      │                │
scheme     host       port ver   path params            query params      fragment
                                                        (filters/options)


📌 Path Parameters vs Query Parameters:

┌──────────────────────────────────────────────────────────────────┐
│  Type        │  Example                │  When to Use           │
├──────────────┼─────────────────────────┼────────────────────────┤
│  Path Param  │  /students/101          │  Identify a SPECIFIC   │
│              │  /courses/CS301         │  resource (required)   │
├──────────────┼─────────────────────────┼────────────────────────┤
│  Query Param │  /students?branch=CSE   │  Filter, sort, search  │
│              │  /students?page=2&      │  paginate (optional)   │
│              │    limit=10&sort=cgpa   │                        │
├──────────────┼─────────────────────────┼────────────────────────┤
│  Body Param  │  POST /students         │  Send data to create/  │
│              │  Body: {"name":"Rahul"} │  update (complex data) │
└──────────────┴─────────────────────────┴────────────────────────┘
```

```
🌐 CORS — Why Your Frontend Can't Call Your Backend

  Frontend (localhost:3000)          Backend (localhost:8000)
  ─────────────────────────          ──────────────────────────
         │                                     │
         │── GET /api/data ───────────────►    │
         │                                     │
         │   🚫 BLOCKED by browser!            │
         │   "Different origin = not allowed"  │
         │                                     │
  
  WHY? Browser's Same-Origin Policy:
  ┌─────────────────────────────────────────────────────┐
  │  Origin = Protocol + Host + Port                    │
  │                                                     │
  │  http://localhost:3000  ≠  http://localhost:8000     │
  │       same       same        DIFFERENT PORT → 🚫    │
  │                                                     │
  │  FIX: Server must send:                             │
  │  Access-Control-Allow-Origin: http://localhost:3000  │
  │  Access-Control-Allow-Methods: GET, POST, PUT       │
  │  Access-Control-Allow-Headers: Authorization        │
  └─────────────────────────────────────────────────────┘
```

```python
# 🔧 CORS Fix in FastAPI (30 seconds)
from fastapi import FastAPI
from fastapi.middleware.cors import CORSMiddleware

app = FastAPI()

app.add_middleware(
    CORSMiddleware,
    allow_origins=["http://localhost:3000"],  # or ["*"] for all
    allow_credentials=True,
    allow_methods=["*"],
    allow_headers=["*"],
)
```

---

### Week 4: Different API Styles

| # | Topic | Priority | Est. Hours | Status |
|---|-------|----------|-----------|--------|
| 14 | **RESTful APIs** — principles, constraints, resource-based design | 🔴 Critical | 3h | ⬜ |
| 15 | **Simple JSON APIs** — lightweight, no strict REST rules | 🟡 Important | 1h | ⬜ |
| 16 | **GraphQL APIs** — query language, schema, resolvers, when to use | 🟡 Important | 3h | ⬜ |
| 17 | **gRPC APIs** — Protocol Buffers, streaming, high performance | 🟢 Good to know | 2h | ⬜ |
| 18 | **SOAP APIs** — XML-based, WSDL, legacy enterprise systems | 🟢 Good to know | 1h | ⬜ |

```
🎯 API Styles Comparison — When to Use What?

┌─────────────┬──────────────┬───────────────┬──────────────┬────────────┐
│  Criteria   │  REST        │  GraphQL      │  gRPC        │  SOAP      │
├─────────────┼──────────────┼───────────────┼──────────────┼────────────┤
│ Data Format │ JSON         │ JSON          │ Protobuf     │ XML        │
│             │              │               │ (binary)     │            │
├─────────────┼──────────────┼───────────────┼──────────────┼────────────┤
│ Protocol    │ HTTP         │ HTTP          │ HTTP/2       │ HTTP/SMTP  │
├─────────────┼──────────────┼───────────────┼──────────────┼────────────┤
│ Learning    │ Easy ✅      │ Medium        │ Hard         │ Hard       │
│ Curve       │              │               │              │            │
├─────────────┼──────────────┼───────────────┼──────────────┼────────────┤
│ Best For    │ Public APIs, │ Complex UIs,  │ Microservice │ Enterprise,│
│             │ CRUD apps,   │ mobile apps,  │ internal     │ banking,   │
│             │ web services │ multi-source  │ comms, IoT   │ legacy     │
├─────────────┼──────────────┼───────────────┼──────────────┼────────────┤
│ Over/Under  │ Over-fetching│ ✅ Get exact  │ N/A (schema) │ Over-      │
│ Fetching    │ common       │ data needed   │              │ engineered │
├─────────────┼──────────────┼───────────────┼──────────────┼────────────┤
│ Performance │ Good         │ Good          │ Fastest 🚀   │ Slow       │
├─────────────┼──────────────┼───────────────┼──────────────┼────────────┤
│ Caching     │ Easy (HTTP)  │ Complex       │ Manual       │ Manual     │
├─────────────┼──────────────┼───────────────┼──────────────┼────────────┤
│ Industry    │ 80% of APIs  │ Facebook,     │ Google,      │ Banks,     │
│ Usage       │ worldwide    │ GitHub, Shopify│ Netflix     │ Insurance  │
├─────────────┼──────────────┼───────────────┼──────────────┼────────────┤
│ Jobs 2025   │ Highest 📈   │ Growing       │ Growing      │ Declining  │
└─────────────┴──────────────┴───────────────┴──────────────┴────────────┘

💡 Recommendation for BTech students: Master REST first → Then GraphQL → 
   Then gRPC. Skip SOAP unless you're joining a bank/insurance company.
```

```
📌 REST vs GraphQL — The Buffet Analogy 🍽️

  REST = Fixed Thali 🍱
  ─────────────────────
  You order "South Indian Thali" 
  → You get: dosa + sambhar + chutney + rice + rasam
  → Even if you just wanted dosa, you get EVERYTHING
  → Want dosa AND pizza? TWO separate orders (two API calls)
  
  
  GraphQL = Build-Your-Own-Plate 🍽️
  ──────────────────────────────────
  You say: "I want dosa, pizza, and just the rasam"
  → You get EXACTLY what you asked for
  → ONE order (one API call), custom selection
  → But the kitchen (server) works harder
```

---

## 🟡 PHASE 2: BUILDING RESTful APIs (Weeks 5–10)

### Week 5–6: REST Principles & URI Design

| # | Topic | Priority | Est. Hours | Status |
|---|-------|----------|-----------|--------|
| 19 | **REST Principles** — 6 constraints (client-server, stateless, etc.) | 🔴 Critical | 3h | ⬜ |
| 20 | **URI Design** — naming conventions, resource hierarchy, best practices | 🔴 Critical | 2h | ⬜ |
| 21 | **Versioning Strategies** — URI, header, query param versioning | 🟡 Important | 2h | ⬜ |
| 22 | **Handling CRUD Operations** — mapping HTTP methods to database ops | 🔴 Critical | 3h | ⬜ |
| 23 | **Idempotency** — safe vs unsafe methods, retry logic | 🟡 Important | 1h | ⬜ |
| 24 | **HATEOAS** — Hypermedia as the Engine of Application State | 🟢 Good to know | 1h | ⬜ |

```
🏗️ REST — 6 Architectural Constraints

┌──────────────────────┬──────────────────────────────────────────┐
│  Constraint          │  Meaning (ELI5)                          │
├──────────────────────┼──────────────────────────────────────────┤
│ 1. Client-Server     │ Waiter ≠ Chef. Frontend and backend are │
│                      │ separate, can evolve independently.      │
├──────────────────────┼──────────────────────────────────────────┤
│ 2. Stateless         │ Waiter doesn't remember your last visit.│
│                      │ Every request must carry ALL info needed.│
│                      │ (No "same as last time" — send token     │
│                      │  every time)                             │
├──────────────────────┼──────────────────────────────────────────┤
│ 3. Cacheable         │ Menu card is cached — don't ask chef     │
│                      │ every time. Responses should say if they │
│                      │ can be cached.                           │
├──────────────────────┼──────────────────────────────────────────┤
│ 4. Uniform Interface │ Every restaurant uses same format:       │
│                      │ menu → order → bill. Standard methods,   │
│                      │ standard status codes, standard URLs.    │
├──────────────────────┼──────────────────────────────────────────┤
│ 5. Layered System    │ You don't know if chef is cooking or     │
│                      │ ordering from another restaurant. Load   │
│                      │ balancers, proxies can sit in between.   │
├──────────────────────┼──────────────────────────────────────────┤
│ 6. Code on Demand    │ Restaurant gives you recipe to cook at   │
│    (Optional)        │ home. Server can send executable code    │
│                      │ (JavaScript) to client.                  │
└──────────────────────┴──────────────────────────────────────────┘
```

```
📐 URI Design — Best Practices (This Gets Asked in Interviews!)

  ✅ GOOD URIs                        ❌ BAD URIs
  ──────────────                      ────────────
  GET    /students                    GET    /getStudents
  GET    /students/101                GET    /student/getById?id=101
  POST   /students                    POST   /createStudent
  PUT    /students/101                POST   /updateStudent
  DELETE /students/101                GET    /deleteStudent?id=101
  GET    /students/101/courses        GET    /getCoursesOfStudent
  GET    /students?branch=CSE&        GET    /searchStudent
           year=3&sort=cgpa
  
  
  ┌────────────────────────────────────────────────────────────┐
  │                   URI DESIGN RULES                         │
  ├────────────────────────────────────────────────────────────┤
  │ 1. Use NOUNS, not verbs          │ /students ✅            │
  │    (HTTP method IS the verb)     │ /getStudents ❌         │
  ├──────────────────────────────────┼─────────────────────────┤
  │ 2. Use PLURAL nouns              │ /students ✅            │
  │                                  │ /student ❌             │
  ├──────────────────────────────────┼─────────────────────────┤
  │ 3. Use kebab-case                │ /course-materials ✅    │
  │                                  │ /courseMaterials ❌     │
  │                                  │ /course_materials ❌    │
  ├──────────────────────────────────┼─────────────────────────┤
  │ 4. Nest for relationships        │ /students/101/courses ✅│
  │    (max 2-3 levels deep)         │                         │
  ├──────────────────────────────────┼─────────────────────────┤
  │ 5. Use query params for          │ /students?page=2&       │
  │    filtering, sorting, paging    │   limit=10&sort=name ✅ │
  ├──────────────────────────────────┼─────────────────────────┤
  │ 6. No trailing slashes           │ /students ✅            │
  │                                  │ /students/ ❌           │
  ├──────────────────────────────────┼─────────────────────────┤
  │ 7. No file extensions            │ /students ✅            │
  │                                  │ /students.json ❌       │
  └──────────────────────────────────┴─────────────────────────┘


  API Versioning Strategies:
  
  ┌──────────────────────────────────────────────────────────────┐
  │ Strategy        │ Example                │ Used By           │
  ├─────────────────┼────────────────────────┼───────────────────┤
  │ URI Path (Best) │ /v1/students           │ Twitter, Google   │
  │                 │ /v2/students           │ Most companies    │
  ├─────────────────┼────────────────────────┼───────────────────┤
  │ Query Param     │ /students?version=2    │ Amazon, Google    │
  ├─────────────────┼────────────────────────┼───────────────────┤
  │ Header          │ X-API-Version: 2       │ GitHub, Stripe    │
  │                 │ Accept: app/vnd.api.v2 │                   │
  └─────────────────┴────────────────────────┴───────────────────┘
  
  💡 For beginners: Use URI Path versioning. It's the most common
     and easiest to understand.
```

---

### Week 7–8: Pagination, Rate Limiting & Error Handling

| # | Topic | Priority | Est. Hours | Status |
|---|-------|----------|-----------|--------|
| 25 | **Pagination** — offset, cursor, keyset pagination | 🔴 Critical | 3h | ⬜ |
| 26 | **Rate Limiting** — token bucket, sliding window, implementation | 🔴 Critical | 2h | ⬜ |
| 27 | **Error Handling** — RFC 7807, consistent error format, error codes | 🔴 Critical | 3h | ⬜ |

```
📄 Pagination — 3 Strategies

1️⃣ OFFSET-BASED (Simple, most common)
   GET /students?page=3&limit=10
   → Skip first 20, return next 10
   
   ✅ Simple, easy to implement
   ❌ Slow on large datasets (OFFSET 1000000 is expensive)
   ❌ Inconsistent if data changes between pages

2️⃣ CURSOR-BASED (Modern, recommended)
   GET /students?cursor=eyJpZCI6MTAxfQ==&limit=10
   → "Give me 10 students after this cursor"
   → Cursor = encoded last item ID
   
   ✅ Consistent, no skipping issues
   ✅ Fast even on large datasets
   ❌ Can't jump to page 50 directly
   ❌ Slightly complex to implement

3️⃣ KEYSET-BASED (Best performance)
   GET /students?after_id=100&limit=10
   → WHERE id > 100 LIMIT 10
   
   ✅ Fastest (uses DB indexes)
   ❌ Only works with sortable fields
```

```python
# 🔧 Pagination Implementation (FastAPI + Cursor-Based)
from fastapi import FastAPI, Query
from pydantic import BaseModel
import base64
import json

app = FastAPI()

# Simulated DB
students_db = [
    {"id": i, "name": f"Student_{i}", "cgpa": round(6 + (i % 40) / 10, 1)}
    for i in range(1, 501)  # 500 students
]

class PaginatedResponse(BaseModel):
    data: list
    next_cursor: str | None
    has_more: bool
    total_count: int

def encode_cursor(student_id: int) -> str:
    return base64.b64encode(json.dumps({"id": student_id}).encode()).decode()

def decode_cursor(cursor: str) -> int:
    return json.loads(base64.b64decode(cursor))["id"]

@app.get("/students", response_model=PaginatedResponse)
def list_students(
    cursor: str | None = Query(None, description="Pagination cursor"),
    limit: int = Query(10, ge=1, le=100, description="Items per page")
):
    # Find starting point
    if cursor:
        last_id = decode_cursor(cursor)
        filtered = [s for s in students_db if s["id"] > last_id]
    else:
        filtered = students_db
    
    # Get page
    page = filtered[:limit]
    has_more = len(filtered) > limit
    
    return PaginatedResponse(
        data=page,
        next_cursor=encode_cursor(page[-1]["id"]) if page and has_more else None,
        has_more=has_more,
        total_count=len(students_db)
    )

# Response:
# {
#   "data": [{"id": 1, "name": "Student_1", "cgpa": 6.1}, ...],
#   "next_cursor": "eyJpZCI6IDEwfQ==",
#   "has_more": true,
#   "total_count": 500
# }
```

```python
# ⚠️ Error Handling — RFC 7807 Format (Industry Standard)
from fastapi import FastAPI, HTTPException, Request
from fastapi.responses import JSONResponse
from pydantic import BaseModel

app = FastAPI()

class ProblemDetail(BaseModel):
    """RFC 7807 - Problem Details for HTTP APIs"""
    type: str          # URI reference for error type
    title: str         # Short human-readable summary
    status: int        # HTTP status code
    detail: str        # Human-readable explanation
    instance: str      # URI of the specific request
    errors: list = []  # Validation errors (optional)

@app.exception_handler(HTTPException)
async def http_exception_handler(request: Request, exc: HTTPException):
    return JSONResponse(
        status_code=exc.status_code,
        content=ProblemDetail(
            type=f"/errors/{exc.status_code}",
            title=exc.detail if isinstance(exc.detail, str) else "Error",
            status=exc.status_code,
            detail=str(exc.detail),
            instance=str(request.url),
        ).model_dump()
    )

@app.get("/students/{roll_no}")
def get_student(roll_no: int):
    if roll_no < 0:
        raise HTTPException(
            status_code=400,
            detail="Roll number must be positive"
        )
    if roll_no > 500:
        raise HTTPException(
            status_code=404,
            detail=f"Student with roll_no {roll_no} not found"
        )
    return {"id": roll_no, "name": f"Student_{roll_no}"}

# ❌ Error Response (Clean & Standardized):
# {
#   "type": "/errors/404",
#   "title": "Student with roll_no 999 not found",
#   "status": 404,
#   "detail": "Student with roll_no 999 not found",
#   "instance": "/students/999",
#   "errors": []
# }
```

---

### Week 9–10: Build a Complete CRUD API (Hands-On Project)

| # | Topic | Priority | Est. Hours | Status |
|---|-------|----------|-----------|--------|
| 28 | **Full CRUD API Project** — design → implement → test → document | 🔴 Critical | 10h | ⬜ |
| 29 | **Database Integration** — PostgreSQL/MongoDB with ORM | 🔴 Critical | 4h | ⬜ |
| 30 | **Input Validation** — Pydantic models, request validation | 🔴 Critical | 2h | ⬜ |
| 31 | **API Documentation** — Swagger/OpenAPI auto-generation | 🟡 Important | 2h | ⬜ |

```python
# 🏗️ COMPLETE CRUD API — College Management System
# Tech: FastAPI + Pydantic + SQLite (upgradeable to PostgreSQL)

from fastapi import FastAPI, HTTPException, Query, Path
from pydantic import BaseModel, Field, validator
from datetime import datetime
from enum import Enum
from typing import Optional

app = FastAPI(
    title="🏫 College Management API",
    description="REST API for managing students, courses, and enrollments",
    version="1.0.0"
)

# ─── Enums ───────────────────────────────────
class Branch(str, Enum):
    CSE = "CSE"
    ECE = "ECE"
    ME = "ME"
    CE = "CE"
    EE = "EE"

# ─── Schemas (Pydantic Models) ───────────────
class StudentCreate(BaseModel):
    name: str = Field(..., min_length=2, max_length=50, example="Rahul Sharma")
    roll_no: int = Field(..., gt=0, example=101)
    branch: Branch = Field(..., example="CSE")
    cgpa: float = Field(..., ge=0.0, le=10.0, example=8.5)
    email: str = Field(..., example="rahul@college.edu.in")
    
    @validator('email')
    def validate_email(cls, v):
        if '@' not in v:
            raise ValueError("Invalid email format")
        return v.lower()

class StudentUpdate(BaseModel):
    name: Optional[str] = Field(None, min_length=2, max_length=50)
    cgpa: Optional[float] = Field(None, ge=0.0, le=10.0)
    email: Optional[str] = None

class StudentResponse(BaseModel):
    id: int
    name: str
    roll_no: int
    branch: Branch
    cgpa: float
    email: str
    created_at: str
    links: dict  # HATEOAS

# ─── In-Memory DB (replace with real DB) ─────
db: dict[int, dict] = {}
counter = 0

# ─── CRUD Endpoints ──────────────────────────

@app.post("/api/v1/students", response_model=StudentResponse, status_code=201)
def create_student(student: StudentCreate):
    """Create a new student record"""
    global counter
    
    # Check duplicate roll_no
    for s in db.values():
        if s["roll_no"] == student.roll_no:
            raise HTTPException(409, f"Student with roll_no {student.roll_no} already exists")
    
    counter += 1
    record = {
        "id": counter,
        **student.model_dump(),
        "created_at": datetime.now().isoformat(),
        "links": {
            "self": f"/api/v1/students/{counter}",
            "courses": f"/api/v1/students/{counter}/courses",
            "collection": "/api/v1/students"
        }
    }
    db[counter] = record
    return record

@app.get("/api/v1/students")
def list_students(
    branch: Optional[Branch] = Query(None, description="Filter by branch"),
    min_cgpa: Optional[float] = Query(None, ge=0, le=10, description="Minimum CGPA"),
    sort_by: Optional[str] = Query("name", regex="^(name|cgpa|roll_no)$"),
    order: Optional[str] = Query("asc", regex="^(asc|desc)$"),
    page: int = Query(1, ge=1),
    limit: int = Query(10, ge=1, le=100)
):
    """List all students with filtering, sorting & pagination"""
    results = list(db.values())
    
    # Filter
    if branch:
        results = [s for s in results if s["branch"] == branch]
    if min_cgpa:
        results = [s for s in results if s["cgpa"] >= min_cgpa]
    
    # Sort
    reverse = (order == "desc")
    results.sort(key=lambda s: s.get(sort_by, ""), reverse=reverse)
    
    # Paginate
    total = len(results)
    start = (page - 1) * limit
    results = results[start:start + limit]
    
    return {
        "data": results,
        "pagination": {
            "page": page,
            "limit": limit,
            "total": total,
            "total_pages": (total + limit - 1) // limit,
            "has_next": start + limit < total,
            "has_prev": page > 1
        }
    }

@app.get("/api/v1/students/{student_id}", response_model=StudentResponse)
def get_student(student_id: int = Path(..., gt=0)):
    """Get a specific student by ID"""
    if student_id not in db:
        raise HTTPException(404, f"Student {student_id} not found")
    return db[student_id]

@app.put("/api/v1/students/{student_id}", response_model=StudentResponse)
def replace_student(student_id: int, student: StudentCreate):
    """Replace entire student record (PUT = full replacement)"""
    if student_id not in db:
        raise HTTPException(404, f"Student {student_id} not found")
    
    db[student_id].update({
        **student.model_dump(),
        "links": db[student_id]["links"]
    })
    return db[student_id]

@app.patch("/api/v1/students/{student_id}", response_model=StudentResponse)
def update_student(student_id: int, updates: StudentUpdate):
    """Partially update student record (PATCH = partial update)"""
    if student_id not in db:
        raise HTTPException(404, f"Student {student_id} not found")
    
    update_data = updates.model_dump(exclude_unset=True)
    if not update_data:
        raise HTTPException(400, "No fields to update")
    
    db[student_id].update(update_data)
    return db[student_id]

@app.delete("/api/v1/students/{student_id}", status_code=204)
def delete_student(student_id: int):
    """Delete a student record"""
    if student_id not in db:
        raise HTTPException(404, f"Student {student_id} not found")
    del db[student_id]

# Run: uvicorn main:app --reload
# Docs: http://localhost:8000/docs (auto-generated Swagger!)
```

---

## 🔴 PHASE 3: SECURITY, AUTH & PERFORMANCE (Weeks 11–16)

### Week 11–12: Authentication & Authorization

| # | Topic | Priority | Est. Hours | Status |
|---|-------|----------|-----------|--------|
| 32 | **Basic Auth** — username:password in header (Base64) | 🟡 Important | 1h | ⬜ |
| 33 | **Session-Based Auth** — cookies, server-side sessions | 🟡 Important | 2h | ⬜ |
| 34 | **Token-Based Auth** — bearer tokens, stateless | 🔴 Critical | 2h | ⬜ |
| 35 | **JWT (JSON Web Tokens)** — structure, signing, verification, refresh tokens | 🔴 Critical | 4h | ⬜ |
| 36 | **OAuth 2.0** — flows, providers, social login | 🔴 Critical | 4h | ⬜ |
| 37 | **API Keys** — generation, rotation, scoping | 🟡 Important | 2h | ⬜ |
| 38 | **RBAC** — Role-Based Access Control | 🔴 Critical | 2h | ⬜ |
| 39 | **ABAC** — Attribute-Based Access Control | 🟢 Good to know | 1h | ⬜ |

```
🔐 Authentication Methods — Complete Comparison

┌──────────────┬────────────────────┬───────────┬───────────┬──────────┐
│  Method      │  How it Works      │ Security  │ Stateless?│ Use Case │
├──────────────┼────────────────────┼───────────┼───────────┼──────────┤
│ Basic Auth   │ username:password  │ ⭐        │ ✅        │ Internal │
│              │ in Base64 header   │ (Low)     │           │ tools    │
├──────────────┼────────────────────┼───────────┼───────────┼──────────┤
│ API Key      │ Unique key in      │ ⭐⭐      │ ✅        │ 3rd party│
│              │ header/query param │           │           │ APIs     │
├──────────────┼────────────────────┼───────────┼───────────┼──────────┤
│ Session      │ Cookie with        │ ⭐⭐⭐    │ ❌        │ Web apps │
│ Based        │ session ID, server │           │ (server   │ with     │
│              │ stores state       │           │  memory)  │ browsers │
├──────────────┼────────────────────┼───────────┼───────────┼──────────┤
│ JWT          │ Signed token with  │ ⭐⭐⭐⭐  │ ✅        │ SPAs,    │
│              │ payload, self-     │           │           │ Mobile   │
│              │ contained          │           │           │ APIs     │
├──────────────┼────────────────────┼───────────┼───────────┼──────────┤
│ OAuth 2.0    │ Delegated auth via │ ⭐⭐⭐⭐⭐│ ✅        │ Social   │
│              │ authorization      │           │           │ login,   │
│              │ server + tokens    │           │           │ 3rd party│
└──────────────┴────────────────────┴───────────┴───────────┴──────────┘
```

```
🎫 JWT — How It Actually Works

  ┌─────────────────────────────────────────────────────────────┐
  │                    JWT STRUCTURE                             │
  │                                                             │
  │  eyJhbGciOiJIUzI1NiJ9                   ← HEADER (algo)    │
  │  .                                                          │
  │  eyJ1c2VyX2lkIjoxMDEsInJvbGUiOiJhZG1pbiJ9 ← PAYLOAD      │
  │  .                                                          │
  │  SflKxwRJSMeKKF2QT4fwpMeJf36POk6yJV   ← SIGNATURE         │
  │                                                             │
  │  Decoded:                                                   │
  │  HEADER:  {"alg": "HS256", "typ": "JWT"}                   │
  │  PAYLOAD: {"user_id": 101, "role": "admin", "exp": 17199}  │
  │  SIGNATURE: HMAC-SHA256(header + "." + payload, SECRET_KEY) │
  └─────────────────────────────────────────────────────────────┘
  
  
  FLOW:
  
  Client                              Server
  ──────                              ──────
    │                                    │
    │── POST /login ────────────────►   │
    │   {email, password}               │ Verify credentials
    │                                    │ Generate JWT
    │   ◄── 200 OK ─────────────────   │
    │   {access_token: "eyJhb...",      │
    │    refresh_token: "eyJhb...",     │
    │    expires_in: 3600}              │
    │                                    │
    │── GET /students ──────────────►   │
    │   Header: Authorization:          │ Decode JWT
    │           Bearer eyJhb...         │ Verify signature
    │                                    │ Check expiry
    │   ◄── 200 OK ─────────────────   │ Extract user info
    │   {data: [...]}                   │ (No DB lookup needed!)
    │                                    │
```

```python
# 🔐 JWT Auth Implementation (FastAPI)
from fastapi import FastAPI, Depends, HTTPException, status
from fastapi.security import HTTPBearer, HTTPAuthorizationCredentials
from pydantic import BaseModel
import jwt
from datetime import datetime, timedelta
from passlib.context import CryptContext

app = FastAPI()
security = HTTPBearer()
pwd_context = CryptContext(schemes=["bcrypt"])

SECRET_KEY = "your-super-secret-key-change-in-production"
ALGORITHM = "HS256"
ACCESS_TOKEN_EXPIRE_MINUTES = 30

# ─── Fake User DB ────────────────────────────
users_db = {
    "rahul@college.edu.in": {
        "name": "Rahul Sharma",
        "email": "rahul@college.edu.in",
        "hashed_password": pwd_context.hash("password123"),
        "role": "student"
    }
}

# ─── Models ──────────────────────────────────
class LoginRequest(BaseModel):
    email: str
    password: str

class TokenResponse(BaseModel):
    access_token: str
    token_type: str = "bearer"
    expires_in: int

# ─── Token Functions ─────────────────────────
def create_token(data: dict, expires_delta: timedelta) -> str:
    payload = data.copy()
    payload["exp"] = datetime.utcnow() + expires_delta
    payload["iat"] = datetime.utcnow()
    return jwt.encode(payload, SECRET_KEY, algorithm=ALGORITHM)

def verify_token(credentials: HTTPAuthorizationCredentials = Depends(security)):
    try:
        payload = jwt.decode(credentials.credentials, SECRET_KEY, algorithms=[ALGORITHM])
        email = payload.get("sub")
        if email is None or email not in users_db:
            raise HTTPException(401, "Invalid token")
        return users_db[email]
    except jwt.ExpiredSignatureError:
        raise HTTPException(401, "Token expired")
    except jwt.InvalidTokenError:
        raise HTTPException(401, "Invalid token")

# ─── Auth Endpoints ──────────────────────────
@app.post("/auth/login", response_model=TokenResponse)
def login(request: LoginRequest):
    user = users_db.get(request.email)
    if not user or not pwd_context.verify(request.password, user["hashed_password"]):
        raise HTTPException(401, "Invalid email or password")
    
    token = create_token(
        {"sub": request.email, "role": user["role"]},
        timedelta(minutes=ACCESS_TOKEN_EXPIRE_MINUTES)
    )
    return TokenResponse(
        access_token=token,
        expires_in=ACCESS_TOKEN_EXPIRE_MINUTES * 60
    )

# ─── Protected Endpoint ─────────────────────
@app.get("/me")
def get_profile(current_user: dict = Depends(verify_token)):
    return {
        "name": current_user["name"],
        "email": current_user["email"],
        "role": current_user["role"]
    }

# ─── Role-Based Access (RBAC) ───────────────
def require_role(allowed_roles: list):
    def checker(current_user: dict = Depends(verify_token)):
        if current_user["role"] not in allowed_roles:
            raise HTTPException(403, "Insufficient permissions")
        return current_user
    return checker

@app.delete("/admin/students/{student_id}")
def admin_delete_student(
    student_id: int,
    admin: dict = Depends(require_role(["admin"]))
):
    return {"message": f"Student {student_id} deleted by {admin['name']}"}
```

```
🔑 OAuth 2.0 — The "Login with Google" Flow

  ┌──────────┐      ┌──────────┐      ┌──────────────┐
  │  User's   │      │  Your    │      │  Google's     │
  │  Browser  │      │  Server  │      │  Auth Server  │
  └────┬──────┘      └────┬─────┘      └──────┬────────┘
       │                   │                    │
  1.   │ Click "Login      │                    │
       │ with Google"      │                    │
       │──────────────────►│                    │
       │                   │                    │
  2.   │   Redirect to     │                    │
       │   Google login    │                    │
       │◄──────────────────│                    │
       │                   │                    │
  3.   │   User logs in    │                    │
       │   at Google       │                    │
       │──────────────────────────────────────►│
       │                   │                    │
  4.   │   Google sends    │                    │
       │   authorization   │                    │
       │   code back       │                    │
       │◄──────────────────────────────────────│
       │──────────────────►│                    │
       │                   │                    │
  5.   │                   │ Exchange code for  │
       │                   │ access token       │
       │                   │───────────────────►│
       │                   │                    │
  6.   │                   │ Access token +     │
       │                   │ user info          │
       │                   │◄───────────────────│
       │                   │                    │
  7.   │   Welcome Rahul!  │ Create session/JWT │
       │   You're logged in│                    │
       │◄──────────────────│                    │
```

---

### Week 13–14: API Security & Best Practices

| # | Topic | Priority | Est. Hours | Status |
|---|-------|----------|-----------|--------|
| 40 | **Common Vulnerabilities** — OWASP API Top 10, injection, BOLA | 🔴 Critical | 4h | ⬜ |
| 41 | **Input Validation** — sanitization, schema validation | 🔴 Critical | 2h | ⬜ |
| 42 | **Rate Limiting Implementation** — token bucket, sliding window | 🔴 Critical | 3h | ⬜ |
| 43 | **HTTPS/TLS** — why HTTP is insecure, SSL certificates | 🟡 Important | 1h | ⬜ |
| 44 | **Security Headers** — HSTS, CSP, X-Content-Type-Options | 🟡 Important | 1h | ⬜ |
| 45 | **API Security Best Practices** — checklist | 🔴 Critical | 2h | ⬜ |

```
🛡️ OWASP API Security Top 10 (2023) — Know These for Interviews!

┌────┬──────────────────────────┬──────────────────────────────────┬──────────────────────┐
│ #  │ Vulnerability            │ ELI5                             │ Prevention           │
├────┼──────────────────────────┼──────────────────────────────────┼──────────────────────┤
│ 1  │ Broken Object Level     │ User A can see/edit User B's     │ Always check: "Does  │
│    │ Authorization (BOLA)     │ data by changing ID in URL       │ THIS user own THIS   │
│    │                          │ /students/102 → /students/999   │ resource?"           │
├────┼──────────────────────────┼──────────────────────────────────┼──────────────────────┤
│ 2  │ Broken Authentication   │ Weak passwords, no rate limit    │ Strong auth, MFA,    │
│    │                          │ on login, token not expiring     │ token rotation       │
├────┼──────────────────────────┼──────────────────────────────────┼──────────────────────┤
│ 3  │ Broken Object Property  │ API returns sensitive fields     │ Whitelist response   │
│    │ Level Authorization     │ (password hash, SSN) or allows   │ fields, restrict     │
│    │                          │ updating admin-only fields       │ writable fields      │
├────┼──────────────────────────┼──────────────────────────────────┼──────────────────────┤
│ 4  │ Unrestricted Resource   │ No pagination limit → dump       │ Enforce max limit,   │
│    │ Consumption             │ entire DB. No file size limit.   │ rate limiting,       │
│    │                          │                                  │ timeouts             │
├────┼──────────────────────────┼──────────────────────────────────┼──────────────────────┤
│ 5  │ Broken Function Level   │ Regular user accessing           │ RBAC, deny by        │
│    │ Authorization            │ /admin/delete-all-users          │ default              │
├────┼──────────────────────────┼──────────────────────────────────┼──────────────────────┤
│ 6  │ Server Side Request     │ API fetches URLs from user       │ Whitelist allowed    │
│    │ Forgery (SSRF)          │ input → accesses internal infra  │ domains, validate    │
├────┼──────────────────────────┼──────────────────────────────────┼──────────────────────┤
│ 7  │ Security Misconfiguration│ Debug mode ON in production,    │ Security checklist,  │
│    │                          │ default passwords, verbose errors│ automated scanning   │
├────┼──────────────────────────┼──────────────────────────────────┼──────────────────────┤
│ 8  │ Lack of Protection from │ No inventory of APIs,            │ API gateway,         │
│    │ Automated Threats       │ bots scraping data               │ CAPTCHA, behavioral  │
│    │                          │                                  │ analysis             │
├────┼──────────────────────────┼──────────────────────────────────┼──────────────────────┤
│ 9  │ Improper Inventory      │ Old API v1 still running with    │ Deprecate old        │
│    │ Management              │ vulnerabilities                  │ versions, document   │
├────┼──────────────────────────┼──────────────────────────────────┼──────────────────────┤
│ 10 │ Unsafe API Consumption  │ Trusting data from 3rd-party     │ Validate ALL         │
│    │                          │ APIs without validation          │ external input       │
└────┴──────────────────────────┴──────────────────────────────────┴──────────────────────┘
```

```python
# 🛡️ API Security — Practical Implementation Checklist

from fastapi import FastAPI, Request, HTTPException
from fastapi.middleware.trustedhost import TrustedHostMiddleware
from slowapi import Limiter
from slowapi.util import get_remote_address
import re

app = FastAPI()

# ─── 1. Rate Limiting ────────────────────────
limiter = Limiter(key_func=get_remote_address)
app.state.limiter = limiter

@app.get("/api/data")
@limiter.limit("100/minute")  # Max 100 requests per minute per IP
async def get_data(request: Request):
    return {"data": "sensitive info"}

# ─── 2. Input Sanitization ───────────────────
def sanitize_input(text: str) -> str:
    """Prevent SQL injection, XSS"""
    # Remove potential SQL injection patterns
    dangerous_patterns = [
        r"('|--|;|/\*|\*/|xp_|exec|execute|insert|select|delete|update|drop|union)",
        r"(<script|javascript:|on\w+=)"  # XSS
    ]
    for pattern in dangerous_patterns:
        if re.search(pattern, text, re.IGNORECASE):
            raise HTTPException(400, "Potentially malicious input detected")
    return text.strip()

# ─── 3. Response Filtering (Never expose sensitive data) ─
class UserPublic(BaseModel):
    """Only expose safe fields"""
    id: int
    name: str
    email: str
    # ❌ Never include: password_hash, internal_id, session_token

# ─── 4. Security Headers Middleware ──────────
@app.middleware("http")
async def add_security_headers(request: Request, call_next):
    response = await call_next(request)
    response.headers["X-Content-Type-Options"] = "nosniff"
    response.headers["X-Frame-Options"] = "DENY"
    response.headers["X-XSS-Protection"] = "1; mode=block"
    response.headers["Strict-Transport-Security"] = "max-age=31536000"
    response.headers["Cache-Control"] = "no-store"  # For sensitive data
    return response
```

```
✅ API SECURITY CHECKLIST (Save This!)

  Authentication:
  □ Use HTTPS everywhere (never HTTP for APIs)
  □ Use JWT with short expiry (15-30 min) + refresh tokens
  □ Hash passwords with bcrypt (never store plaintext!)
  □ Implement MFA for admin endpoints
  □ Rate limit login attempts (5 per minute)
  
  Authorization:
  □ Check resource ownership on EVERY request (prevent BOLA)
  □ Implement RBAC (admin, user, viewer roles)
  □ Deny by default, whitelist allowed actions
  □ Validate JWT signature AND expiry AND claims
  
  Input/Output:
  □ Validate ALL input (type, length, format, range)
  □ Use allowlist, not blocklist for validation
  □ Sanitize against SQL injection and XSS
  □ Never expose stack traces in production
  □ Use response schemas (don't return raw DB objects)
  □ Paginate all list endpoints (prevent data dumps)
  
  Infrastructure:
  □ Rate limiting (per user AND per IP)
  □ Request size limits (prevent DoS)
  □ Timeouts on all external calls
  □ Log all auth failures (detect attacks)
  □ Use API gateway in production
  □ Rotate secrets/keys regularly
  □ CORS: only allow known origins (never "*" in production)
```

---

### Week 15–16: API Performance

| # | Topic | Priority | Est. Hours | Status |
|---|-------|----------|-----------|--------|
| 46 | **Performance Metrics** — latency, throughput, TTFB, P95/P99 | 🟡 Important | 2h | ⬜ |
| 47 | **Caching Strategies** — HTTP cache, Redis, CDN, cache invalidation | 🔴 Critical | 4h | ⬜ |
| 48 | **Load Balancing** — round-robin, least connections, health checks | 🟡 Important | 2h | ⬜ |
| 49 | **Rate Limiting / Throttling** — algorithms, implementation | 🔴 Critical | 2h | ⬜ |
| 50 | **Profiling & Monitoring** — APM tools, logging, metrics | 🟡 Important | 2h | ⬜ |
| 51 | **Performance Testing** — load testing with k6/Locust | 🟡 Important | 2h | ⬜ |

```
⚡ Caching — The 4 Layers

  Client ──► CDN ──► API Gateway ──► App Server ──► Database
    │          │          │               │              │
    │     Layer 1    Layer 2         Layer 3         Layer 4
    │     CDN        Gateway         App Cache       Query
    │     Cache      Cache           (Redis)         Cache
    │                                                
  Browser                                            
  Cache                                              
  (Layer 0)                                          


  ┌──────────────┬──────────────────┬─────────────┬──────────────┐
  │  Cache Layer │  Tool            │  TTL        │  Use Case    │
  ├──────────────┼──────────────────┼─────────────┼──────────────┤
  │  Browser     │  Cache-Control   │  Minutes-   │  Static      │
  │              │  ETag headers    │  Days       │  assets, GET │
  ├──────────────┼──────────────────┼─────────────┼──────────────┤
  │  CDN         │  Cloudflare/     │  Hours-Days │  Global      │
  │              │  CloudFront      │             │  users       │
  ├──────────────┼──────────────────┼─────────────┼──────────────┤
  │  Application │  Redis /         │  Seconds-   │  Frequent    │
  │              │  Memcached       │  Hours      │  DB queries  │
  ├──────────────┼──────────────────┼─────────────┼──────────────┤
  │  Database    │  Query cache /   │  Auto       │  Repeated    │
  │              │  Materialized    │             │  queries     │
  │              │  Views           │             │              │
  └──────────────┴──────────────────┴─────────────┴──────────────┘
```

```python
# ⚡ Redis Caching Implementation
from fastapi import FastAPI
import redis
import json
from functools import wraps

app = FastAPI()
cache = redis.Redis(host='localhost', port=6379, db=0, decode_responses=True)

def cached(ttl_seconds: int = 300):
    """Cache API response in Redis"""
    def decorator(func):
        @wraps(func)
        async def wrapper(*args, **kwargs):
            # Build cache key from function name + args
            cache_key = f"api:{func.__name__}:{str(args)}:{str(kwargs)}"
            
            # Check cache
            cached_result = cache.get(cache_key)
            if cached_result:
                print(f"🟢 Cache HIT: {cache_key}")
                return json.loads(cached_result)
            
            # Cache MISS — call actual function
            print(f"🔴 Cache MISS: {cache_key}")
            result = await func(*args, **kwargs)
            
            # Store in cache
            cache.setex(cache_key, ttl_seconds, json.dumps(result))
            return result
        return wrapper
    return decorator

@app.get("/students/{student_id}")
@cached(ttl_seconds=60)  # Cache for 60 seconds
async def get_student(student_id: int):
    # Expensive DB query
    import asyncio
    await asyncio.sleep(1)  # Simulating slow DB
    return {"id": student_id, "name": f"Student_{student_id}", "cgpa": 8.5}

# First call:  🔴 Cache MISS → 1 second (DB query)
# Next calls:  🟢 Cache HIT  → <1ms (from Redis) 🚀
```

---

## 🏆 PHASE 4: ADVANCED — INTEGRATION, TESTING & REAL-TIME (Weeks 17–20)

### Week 17–18: API Testing & Documentation

| # | Topic | Priority | Est. Hours | Status |
|---|-------|----------|-----------|--------|
| 52 | **Unit Testing** — test individual functions/endpoints | 🔴 Critical | 3h | ⬜ |
| 53 | **Integration Testing** — test full request-response cycle | 🔴 Critical | 3h | ⬜ |
| 54 | **Load Testing** — k6, Locust, stress testing | 🟡 Important | 2h | ⬜ |
| 55 | **Mocking APIs** — mock external services for testing | 🟡 Important | 2h | ⬜ |
| 56 | **Contract Testing** — Pact, ensure API changes don't break clients | 🟢 Good to know | 2h | ⬜ |
| 57 | **Swagger / OpenAPI** — write & generate API docs | 🔴 Critical | 2h | ⬜ |
| 58 | **Postman** — collections, environments, automated testing | 🔴 Critical | 2h | ⬜ |

```python
# 🧪 API Testing with pytest + FastAPI TestClient
from fastapi.testclient import TestClient
import pytest

# Assume 'app' is imported from main.py
client = TestClient(app)

# ─── Unit Tests ──────────────────────────────
class TestStudentAPI:
    
    def test_create_student_success(self):
        response = client.post("/api/v1/students", json={
            "name": "Rahul Sharma",
            "roll_no": 101,
            "branch": "CSE",
            "cgpa": 8.5,
            "email": "rahul@college.edu.in"
        })
        assert response.status_code == 201
        data = response.json()
        assert data["name"] == "Rahul Sharma"
        assert data["roll_no"] == 101
        assert "id" in data
        assert "links" in data  # HATEOAS links
    
    def test_create_student_invalid_cgpa(self):
        response = client.post("/api/v1/students", json={
            "name": "Test",
            "roll_no": 999,
            "branch": "CSE",
            "cgpa": 11.0,  # Invalid! Max is 10
            "email": "test@college.edu.in"
        })
        assert response.status_code == 422  # Validation error
    
    def test_create_duplicate_student(self):
        # Create first
        client.post("/api/v1/students", json={
            "name": "Priya", "roll_no": 102, "branch": "CSE",
            "cgpa": 9.0, "email": "priya@college.edu.in"
        })
        # Create duplicate
        response = client.post("/api/v1/students", json={
            "name": "Priya Copy", "roll_no": 102, "branch": "ECE",
            "cgpa": 7.0, "email": "priya2@college.edu.in"
        })
        assert response.status_code == 409  # Conflict
    
    def test_get_student_not_found(self):
        response = client.get("/api/v1/students/99999")
        assert response.status_code == 404
    
    def test_list_students_pagination(self):
        response = client.get("/api/v1/students?page=1&limit=5")
        assert response.status_code == 200
        data = response.json()
        assert "data" in data
        assert "pagination" in data
        assert data["pagination"]["limit"] == 5
    
    def test_update_student_partial(self):
        # Create
        create_resp = client.post("/api/v1/students", json={
            "name": "Amit", "roll_no": 103, "branch": "CSE",
            "cgpa": 7.0, "email": "amit@college.edu.in"
        })
        student_id = create_resp.json()["id"]
        
        # Patch (only cgpa)
        response = client.patch(f"/api/v1/students/{student_id}", json={
            "cgpa": 8.5
        })
        assert response.status_code == 200
        assert response.json()["cgpa"] == 8.5
        assert response.json()["name"] == "Amit"  # Unchanged
    
    def test_delete_student(self):
        create_resp = client.post("/api/v1/students", json={
            "name": "Delete Me", "roll_no": 999, "branch": "ME",
            "cgpa": 5.0, "email": "delete@college.edu.in"
        })
        student_id = create_resp.json()["id"]
        
        response = client.delete(f"/api/v1/students/{student_id}")
        assert response.status_code == 204
        
        # Verify deletion
        get_response = client.get(f"/api/v1/students/{student_id}")
        assert get_response.status_code == 404

# Run: pytest test_api.py -v --tb=short
```

---

### Week 19: Integration Patterns & Real-Time APIs

| # | Topic | Priority | Est. Hours | Status |
|---|-------|----------|-----------|--------|
| 59 | **Sync vs Async APIs** — when to use which | 🟡 Important | 2h | ⬜ |
| 60 | **Webhooks vs Polling** — push vs pull models | 🔴 Critical | 2h | ⬜ |
| 61 | **Event-Driven Architecture** — pub/sub, message brokers | 🟡 Important | 3h | ⬜ |
| 62 | **API Gateways** — Kong, AWS API Gateway, routing, throttling | 🟡 Important | 2h | ⬜ |
| 63 | **Messaging Queues** — RabbitMQ, Kafka basics | 🟡 Important | 3h | ⬜ |
| 64 | **WebSockets** — real-time bidirectional communication | 🔴 Critical | 3h | ⬜ |
| 65 | **Server-Sent Events (SSE)** — one-way real-time streaming | 🟡 Important | 2h | ⬜ |

```
🔄 Webhooks vs Polling — The Delivery Analogy 📦

  POLLING (Pull Model):
  ═══════════════════════
  You keep calling Flipkart:
    "Has my order shipped?" → "No"     (5 min later)
    "Has my order shipped?" → "No"     (5 min later)
    "Has my order shipped?" → "No"     (5 min later)
    "Has my order shipped?" → "YES!"   (Finally!)
  
  → Wastes bandwidth, many unnecessary calls
  → Simple to implement
  → Good when: updates are frequent, or no webhook support
  

  WEBHOOKS (Push Model):
  ═══════════════════════
  You give Flipkart your phone number:
    "Call me when it ships"
    
    ... (you do other things)
    
    📱 Flipkart calls: "Your order shipped!"
  
  → Efficient, real-time, no wasted calls
  → Slightly harder (need a public endpoint to receive)
  → Good when: events are infrequent, need instant notification


  ┌──────────────┬───────────────────────┬──────────────────────┐
  │              │  Polling              │  Webhooks            │
  ├──────────────┼───────────────────────┼──────────────────────┤
  │ Direction    │  Client → Server      │  Server → Client     │
  │ Efficiency   │  Low (many useless    │  High (only when     │
  │              │  requests)            │  needed)             │
  │ Real-time?   │  Near real-time       │  True real-time ✅   │
  │ Complexity   │  Simple               │  Need public URL     │
  │ Reliability  │  High (you control)   │  Need retry logic    │
  │ Use Case     │  Dashboard refresh    │  Payment callbacks,  │
  │              │                       │  GitHub events       │
  └──────────────┴───────────────────────┴──────────────────────┘
```

```
📡 Real-Time APIs — When to Use What?

┌─────────────────┬──────────────────┬──────────────────┬──────────────────┐
│                 │ WebSockets       │ SSE (Server-Sent │ Long Polling     │
│                 │                  │ Events)          │                  │
├─────────────────┼──────────────────┼──────────────────┼──────────────────┤
│ Direction       │ Bi-directional   │ Server → Client  │ Client → Server  │
│                 │ ↔                │ →                │ ← (with delay)   │
├─────────────────┼──────────────────┼──────────────────┼──────────────────┤
│ Protocol        │ WS (ws://)       │ HTTP (text/      │ HTTP             │
│                 │                  │ event-stream)    │                  │
├─────────────────┼──────────────────┼──────────────────┼──────────────────┤
│ Use Case        │ Chat, Gaming,    │ Live scores,     │ Simple           │
│                 │ Live collab      │ Stock tickers,   │ notifications    │
│                 │                  │ Notifications    │                  │
├─────────────────┼──────────────────┼──────────────────┼──────────────────┤
│ Complexity      │ High             │ Low              │ Medium           │
├─────────────────┼──────────────────┼──────────────────┼──────────────────┤
│ Example         │ WhatsApp Web     │ Twitter feed     │ Email client     │
│                 │                  │ updates          │ checking         │
└─────────────────┴──────────────────┴──────────────────┴──────────────────┘
```

```python
# 📡 WebSocket — Real-Time Chat (FastAPI)
from fastapi import FastAPI, WebSocket, WebSocketDisconnect
from typing import List

app = FastAPI()

class ConnectionManager:
    def __init__(self):
        self.active_connections: List[WebSocket] = []
    
    async def connect(self, websocket: WebSocket):
        await websocket.accept()
        self.active_connections.append(websocket)
        await self.broadcast(f"📢 New user joined! ({len(self.active_connections)} online)")
    
    def disconnect(self, websocket: WebSocket):
        self.active_connections.remove(websocket)
    
    async def broadcast(self, message: str):
        for connection in self.active_connections:
            await connection.send_text(message)

manager = ConnectionManager()

@app.websocket("/ws/chat/{username}")
async def chat_endpoint(websocket: WebSocket, username: str):
    await manager.connect(websocket)
    try:
        while True:
            data = await websocket.receive_text()
            await manager.broadcast(f"💬 {username}: {data}")
    except WebSocketDisconnect:
        manager.disconnect(websocket)
        await manager.broadcast(f"👋 {username} left the chat")

# Connect via: ws://localhost:8000/ws/chat/Rahul
```

---

### Week 20: Standards, Compliance & API Lifecycle

| # | Topic | Priority | Est. Hours | Status |
|---|-------|----------|-----------|--------|
| 66 | **API Lifecycle Management** — design, build, deploy, deprecate | 🟡 Important | 2h | ⬜ |
| 67 | **GDPR** — data privacy, right to deletion, consent | 🟡 Important | 1h | ⬜ |
| 68 | **PII (Personally Identifiable Information)** — handling, masking | 🟡 Important | 1h | ⬜ |
| 69 | **CCPA, HIPAA, PCI DSS** — industry-specific compliance overview | 🟢 Good to know | 1h | ⬜ |
| 70 | **Microservices Architecture** — API design at scale | 🟡 Important | 3h | ⬜ |

```
🔄 API LIFECYCLE

  ┌─────────┐    ┌─────────┐    ┌─────────┐    ┌──────────┐
  │ DESIGN  │───►│  BUILD  │───►│  TEST   │───►│  DEPLOY  │
  │         │    │         │    │         │    │          │
  │ • Schema│    │ • Code  │    │ • Unit  │    │ • CI/CD  │
  │ • OpenAPI│   │ • Auth  │    │ • Load  │    │ • Gateway│
  │ • Review│    │ • Docs  │    │ • Contract│   │ • Monitor│
  └─────────┘    └─────────┘    └─────────┘    └──────┬───┘
                                                       │
                                                       ▼
  ┌──────────┐    ┌──────────┐    ┌─────────┐    ┌──────────┐
  │  RETIRE  │◄───│ DEPRECATE│◄───│ VERSION │◄───│ MONITOR  │
  │          │    │          │    │         │    │          │
  │ • Remove │    │ • Sunset │    │ • v2    │    │ • Logs   │
  │ • Migrate│    │   headers│    │ • Break │    │ • Metrics│
  │   users  │    │ • Notice │    │   change│    │ • Alerts │
  └──────────┘    └──────────┘    └─────────┘    └──────────┘
```

---

## 📊 COMPLETE TIMELINE OVERVIEW

```
WEEK  1  ████ What is API?, HTTP Protocol, TCP/IP, DNS
WEEK  2  ████ HTTP Methods, Status Codes, Headers, Caching
WEEK  3  ████ URLs, Query/Path Params, Cookies, CORS
WEEK  4  ████ REST vs GraphQL vs gRPC vs SOAP
          ──── 🎯 MILESTONE: Understand & consume any API ────

WEEK  5  ████ REST Principles, 6 Constraints
WEEK  6  ████ URI Design, Versioning, Idempotency, HATEOAS
WEEK  7  ████ Pagination (offset, cursor), Rate Limiting
WEEK  8  ████ Error Handling (RFC 7807), Input Validation
WEEK  9  ████ Full CRUD API Project — Part 1
WEEK 10  ████ Full CRUD API Project — Part 2 + Swagger Docs
          ──── 🎯 MILESTONE: Build & document a REST API ────

WEEK 11  ████ Auth: Basic, Session, Token, JWT
WEEK 12  ████ OAuth 2.0, API Keys, RBAC, ABAC
WEEK 13  ████ API Security: OWASP Top 10, Input Sanitization
WEEK 14  ████ Security Best Practices, HTTPS, Security Headers
WEEK 15  ████ Caching (HTTP, Redis, CDN), Performance Metrics
WEEK 16  ████ Load Balancing, Rate Limiting, Profiling
          ──── 🎯 MILESTONE: Secure & performant API ────

WEEK 17  ████ API Testing: Unit, Integration, Load
WEEK 18  ████ Mocking, Contract Testing, Postman Automation
WEEK 19  ████ WebSockets, SSE, Webhooks, Message Queues
WEEK 20  ████ API Lifecycle, Compliance, Microservices
          ──── 🏆 MILESTONE: Production-Ready API Engineer ────
```

---

## 🏋️ PROJECTS TO BUILD (Phase-wise)

| Phase | Project | Skills Covered | Resume Value |
|-------|---------|---------------|-------------|
| 🟢 Week 4 | **API Consumer App** — consume a public API (weather/news) | HTTP, methods, status codes | ⭐⭐ |
| 🟡 Week 10 | **CRUD REST API** — Student/Blog management with docs | REST design, pagination, error handling | ⭐⭐⭐ |
| 🔴 Week 14 | **Authenticated API** — JWT + OAuth + RBAC | Security, auth, roles | ⭐⭐⭐⭐ |
| 🔴 Week 16 | **High-Performance API** — with Redis caching + rate limiting | Caching, performance | ⭐⭐⭐⭐ |
| 🏆 Week 20 | **Real-Time API Platform** — chat/notifications with WebSockets | Full-stack API design | ⭐⭐⭐⭐⭐ |

---

## 📚 BEST RESOURCES (Curated)

| Category | Resource | Type | Best For |
|----------|----------|------|----------|
| 🌐 Roadmap | **roadmap.sh/api-design** | Website | Visual learning path |
| 🎥 YouTube | **Traversy Media** — REST API Crash Course | Video | Quick start |
| 🎥 YouTube | **Hussein Nasser** — Backend Engineering | Video | Deep networking/API concepts |
| 🎥 YouTube | **Fireship** — 100 seconds series | Video | Quick overviews |
| 📖 Book | **Designing Web APIs** (Brenda Jin) | Book | API design patterns |
| 📖 Book | **RESTful Web APIs** (Leonard Richardson) | Book | REST deep dive |
| 🌐 Docs | **FastAPI Official Docs** | Documentation | Best API framework docs |
| 🌐 Tool | **Postman Learning Center** | Interactive | API testing practice |
| 🌐 Tool | **Swagger Editor** (editor.swagger.io) | Tool | Design APIs visually |
| 🌐 Practice | **JSONPlaceholder** | Fake API | Practice consuming APIs |
| 🌐 Practice | **httpbin.org** | Tool | Test HTTP methods/headers |

---

## 💼 Interview Angle — API Design Questions Companies Ask

```
┌────────────────────────────────────────────────────────────────────┐
│                TOP API DESIGN INTERVIEW QUESTIONS                  │
├────────────────────────────────────────────────────────────────────┤
│                                                                    │
│  BEGINNER:                                                         │
│  1. What is REST? Explain its constraints.                         │
│  2. Difference between PUT and PATCH?                              │
│  3. What are idempotent methods? Why does it matter?               │
│  4. Explain status codes: 401 vs 403? 400 vs 422?                 │
│  5. How do you version an API?                                     │
│                                                                    │
│  INTERMEDIATE:                                                     │
│  6. Design a URL shortener API (endpoints, schemas)                │
│  7. How would you implement pagination for 10M records?            │
│  8. JWT vs Session-based auth — when to use which?                 │
│  9. How do you handle rate limiting?                               │
│  10. REST vs GraphQL — trade-offs?                                 │
│                                                                    │
│  ADVANCED (System Design):                                         │
│  11. Design Twitter's API (tweets, followers, timeline)            │
│  12. How would you design Razorpay's payment API?                  │
│  13. Design a real-time notification system                        │
│  14. How do you handle API backward compatibility?                 │
│  15. Design an API gateway for a microservices architecture        │
│                                                                    │
│  Companies that heavily test API design:                           │
│  Amazon, Flipkart, Razorpay, Swiggy, Zomato,                     │
│  Stripe, PayPal, Google, Microsoft, Uber                           │
└────────────────────────────────────────────────────────────────────┘
```

---

