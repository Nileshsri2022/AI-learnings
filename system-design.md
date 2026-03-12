

# 🚀 Complete System Design Mastery Roadmap

---

## Phase 1: Foundation (Weeks 1–3)

### 1.1 — What is System Design?
- Understanding the purpose
- Types: High-Level Design (HLD) vs Low-Level Design (LLD)
- How to approach system design interviews/problems

### 1.2 — Core Trade-offs
```
✅ Performance vs Scalability
✅ Latency vs Throughput
✅ Availability vs Consistency
```

### 1.3 — CAP Theorem
- What it means
- **CP** — Consistency + Partition Tolerance
- **AP** — Availability + Partition Tolerance
- Real-world examples (MongoDB = CP, Cassandra = AP)

### 1.4 — Consistency Patterns
```
→ Strong Consistency
→ Eventual Consistency
→ Weak Consistency
```

### 1.5 — Availability Patterns
```
→ Fail-Over (Active-Active / Active-Passive)
→ Replication (Master-Slave / Master-Master)
→ Availability in Numbers (99.9%, 99.99%)
→ Availability in Parallel vs Sequence
```

**📚 Resources:**
- "Designing Data-Intensive Applications" (Ch. 1–2)
- donnemartin/system-design-primer (GitHub)
- ByteByteGo YouTube

---

## Phase 2: Networking & Communication (Weeks 4–5)

### 2.1 — Protocols
```
✅ HTTP / HTTPS
✅ TCP
✅ UDP
✅ WebSockets
```

### 2.2 — API Design
```
→ REST (methods, status codes, best practices)
→ RPC / gRPC (Protobuf, bi-directional streaming)
→ GraphQL (queries, mutations, subscriptions)
```

### 2.3 — Idempotent Operations
- Why they matter
- Designing idempotent APIs

### 2.4 — DNS (Domain Name System)
- How DNS resolution works
- DNS records (A, CNAME, MX, NS)
- DNS as a load balancer

**📚 Resources:**
- MDN Web Docs (HTTP)
- gRPC official docs
- "Web Scalability for Startup Engineers"

---

## Phase 3: Content Delivery & Load Balancing (Weeks 6–7)

### 3.1 — CDN (Content Delivery Networks)
```
→ Push CDNs
→ Pull CDNs
→ When to use which
```

### 3.2 — Load Balancers
```
→ Layer 4 Load Balancing (Transport)
→ Layer 7 Load Balancing (Application)
→ LB vs Reverse Proxy
→ Load Balancing Algorithms:
    - Round Robin
    - Weighted Round Robin
    - Least Connections
    - IP Hash
    - Consistent Hashing
```

### 3.3 — Horizontal Scaling
- Scaling out vs Scaling up
- Stateless services
- Session management

**📚 Resources:**
- Cloudflare Learning Center
- NGINX documentation
- AWS ELB docs

---

## Phase 4: Databases Deep Dive (Weeks 8–12)

### 4.1 — SQL vs NoSQL
```
When to use SQL:
  → Structured data, ACID, complex queries

When to use NoSQL:
  → Flexible schema, high throughput, horizontal scale
```

### 4.2 — RDBMS (Relational)
- MySQL, PostgreSQL
- ACID properties
- Indexing, Joins, Transactions

### 4.3 — NoSQL Types
```
→ Key-Value Store      (Redis, DynamoDB)
→ Document Store       (MongoDB, CouchDB)
→ Wide Column Store    (Cassandra, HBase)
→ Graph Databases      (Neo4j, Amazon Neptune)
```

### 4.4 — Scaling Databases
```
→ Replication (Master-Slave, Master-Master)
→ Sharding (Hash-based, Range-based, Geo-based)
→ Federation (Functional partitioning)
→ Denormalization (When & why)
```

### 4.5 — SQL Tuning
- Query optimization
- Indexing strategies (B-Tree, Hash, Composite)
- Explain/Analyze plans
- Connection pooling

**📚 Resources:**
- "Designing Data-Intensive Applications" (Ch. 3–7)
- Use The Index, Luke (website)
- Hussein Nasser YouTube (DB internals)

---

## Phase 5: Caching (Weeks 13–14)

### 5.1 — Types of Caching
```
→ Client Caching
→ CDN Caching
→ Web Server Caching
→ Application Caching
→ Database Caching
```

### 5.2 — Caching Strategies
```
→ Cache-Aside       (Lazy loading)
→ Write-Through     (Write to cache + DB)
→ Write-Behind      (Write to cache, async to DB)
→ Refresh-Ahead     (Pre-refresh before expiry)
```

### 5.3 — Tools
- Redis
- Memcached
- Varnish

### 5.4 — Cache Invalidation
- TTL-based
- Event-based
- Cache stampede / thundering herd problem

**📚 Resources:**
- Redis University (free)
- AWS ElastiCache docs
- "Designing Data-Intensive Applications" (Ch. 5)

---

## Phase 6: Asynchronism & Messaging (Weeks 15–17)

### 6.1 — Message Queues
```
→ RabbitMQ
→ Amazon SQS
→ How they decouple services
```

### 6.2 — Task Queues
```
→ Celery
→ Sidekiq
→ Delayed job processing
```

### 6.3 — Event Streaming
```
→ Apache Kafka
→ Amazon Kinesis
→ Event-driven architecture
```

### 6.4 — Back Pressure
- What is it
- How to handle overwhelmed systems

### 6.5 — Background Jobs
```
→ Event-Driven
→ Schedule-Driven (Cron)
→ Returning Results (polling, webhooks, websockets)
```

**📚 Resources:**
- Kafka: The Definitive Guide
- RabbitMQ tutorials
- AWS SQS/SNS docs

---

## Phase 7: Application Architecture (Weeks 18–20)

### 7.1 — Microservices
```
→ Monolith vs Microservices
→ Decomposition strategies
→ Inter-service communication (sync vs async)
→ Data ownership per service
```

### 7.2 — Service Discovery
```
→ Client-side discovery
→ Server-side discovery
→ Tools: Consul, Eureka, Kubernetes DNS
```

### 7.3 — API Gateway
```
→ Routing
→ Rate limiting
→ Authentication
→ Tools: Kong, AWS API Gateway, NGINX
```

**📚 Resources:**
- "Building Microservices" by Sam Newman
- Martin Fowler's blog
- Kubernetes docs

---

## Phase 8: Performance Anti-patterns (Week 21)

Learn what **NOT** to do:

```
❌ Busy Database         — Offload processing
❌ Busy Frontend         — Move work to backend
❌ Chatty I/O            — Batch requests
❌ Extraneous Fetching   — Fetch only what's needed
❌ Improper Instantiation — Reuse expensive objects
❌ Monolithic Persistence — Use polyglot persistence
❌ No Caching            — Cache aggressively
❌ Noisy Neighbor        — Isolate tenants
❌ Synchronous I/O       — Go async where possible
❌ Retry Storm           — Exponential backoff + jitter
```

**📚 Resources:**
- Microsoft Azure Architecture anti-patterns docs

---

## Phase 9: Monitoring & Observability (Weeks 22–23)

### 9.1 — Types of Monitoring
```
→ Health Monitoring
→ Availability Monitoring
→ Performance Monitoring
→ Security Monitoring
→ Usage Monitoring
```

### 9.2 — Instrumentation
```
→ Logging (ELK Stack: Elasticsearch, Logstash, Kibana)
→ Metrics (Prometheus + Grafana)
→ Tracing (Jaeger, Zipkin, OpenTelemetry)
```

### 9.3 — Visualization & Alerts
```
→ Dashboards (Grafana, Datadog)
→ Alerting (PagerDuty, OpsGenie)
→ SLAs, SLOs, SLIs
```

**📚 Resources:**
- "Observability Engineering" by Charity Majors
- Prometheus docs
- Grafana tutorials

---

## Phase 10: Cloud Design Patterns (Weeks 24–28)

### 10.1 — Messaging Patterns
```
→ Async Request-Reply
→ Claim Check
→ Choreography
→ Competing Consumers
→ Pipes and Filters
→ Priority Queue
→ Publisher/Subscriber
→ Queue-Based Load Leveling
→ Scheduling Agent Supervisor
→ Sequential Convoy
```

### 10.2 — Data Management Patterns
```
→ Cache-Aside
→ CQRS (Command Query Responsibility Segregation)
→ Event Sourcing
→ Index Table
→ Materialized View
→ Sharding
→ Static Content Hosting
→ Valet Key
```

### 10.3 — Design & Implementation Patterns
```
→ Ambassador
→ Anti-Corruption Layer
→ Backends for Frontends (BFF)
→ Compute Resource Consolidation
→ CQRS
→ External Config Store
→ Gateway Aggregation
→ Gateway Offloading
→ Gateway Routing
→ Leader Election
→ Pipes & Filters
→ Sidecar
→ Static Content Hosting
→ Strangler Fig (migration pattern)
```

**📚 Resources:**
- Microsoft Cloud Design Patterns (official docs)
- AWS Well-Architected Framework
- Google Cloud Architecture Center

---

## Phase 11: Reliability Patterns (Weeks 29–30)

### 11.1 — Availability
```
→ Deployment Stamps
→ Geodes
→ Health Endpoint Monitoring
→ Queue-Based Load Leveling
→ Throttling
```

### 11.2 — High Availability
```
→ Deployment Stamps
→ Geodes
→ Health Endpoint Monitoring
→ Bulkhead
→ Circuit Breaker
```

### 11.3 — Resiliency
```
→ Bulkhead
→ Circuit Breaker
→ Compensating Transaction
→ Health Endpoint Monitoring
→ Leader Election
→ Queue-Based Load Leveling
→ Retry (with exponential backoff)
→ Scheduler Agent Supervisor
```

### 11.4 — Security
```
→ Federated Identity
→ Gatekeeper
→ Valet Key
```

**📚 Resources:**
- "Release It!" by Michael Nygard
- Netflix Tech Blog
- AWS Resilience Hub docs

---

## Phase 12: Practice — Real System Design Problems (Weeks 31–36)

### Beginner
```
1. Design a URL Shortener (bit.ly)
2. Design a Pastebin
3. Design a Rate Limiter
```

### Intermediate
```
4. Design Twitter / X
5. Design Instagram
6. Design a Chat System (WhatsApp)
7. Design a News Feed
8. Design a Web Crawler
9. Design a Notification System
```

### Advanced
```
10. Design YouTube / Netflix
11. Design Google Drive / Dropbox
12. Design a Search Engine
13. Design a Ticket Booking System (BookMyShow)
14. Design an Online Code Editor
15. Design Google Maps
16. Design a Payment System (Stripe)
17. Design a Distributed Cache
18. Design a Distributed Message Queue
```

**📚 Resources:**
- "System Design Interview" Vol 1 & 2 by Alex Xu
- Gaurav Sen YouTube
- sudoCode YouTube
- Exponent YouTube

---

## 📅 Summary Timeline

```
Phase 1  ➜ Weeks 1-3    ➜ Foundations & Trade-offs
Phase 2  ➜ Weeks 4-5    ➜ Networking & APIs
Phase 3  ➜ Weeks 6-7    ➜ CDN & Load Balancing
Phase 4  ➜ Weeks 8-12   ➜ Databases (Deep Dive)
Phase 5  ➜ Weeks 13-14  ➜ Caching
Phase 6  ➜ Weeks 15-17  ➜ Async & Messaging
Phase 7  ➜ Weeks 18-20  ➜ App Architecture
Phase 8  ➜ Week 21      ➜ Anti-patterns
Phase 9  ➜ Weeks 22-23  ➜ Monitoring
Phase 10 ➜ Weeks 24-28  ➜ Cloud Patterns
Phase 11 ➜ Weeks 29-30  ➜ Reliability Patterns
Phase 12 ➜ Weeks 31-36  ➜ Practice Problems
```

---

## 📚 Top Resources (All-in-One)

| Type | Resource |
|------|----------|
| 📖 Book | *Designing Data-Intensive Applications* — Martin Kleppmann |
| 📖 Book | *System Design Interview Vol 1 & 2* — Alex Xu |
| 📖 Book | *Building Microservices* — Sam Newman |
| 📖 Book | *Release It!* — Michael Nygard |
| 🌐 Website | [github.com/donnemartin/system-design-primer](https://github.com/donnemartin/system-design-primer) |
| 🌐 Website | [roadmap.sh/system-design](https://roadmap.sh) |
| 🎥 YouTube | ByteByteGo, Gaurav Sen, Hussein Nasser, sudoCode |
| 🛠 Practice | [HighScalability.com](http://highscalability.com) real architectures |

---

> **💡 Golden Rule:** Don't just read — **design one system every week** after Phase 6. Whiteboard it, write trade-offs, and defend your decisions. That's how you truly master it.
