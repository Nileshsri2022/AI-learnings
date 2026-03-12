

# 🐳 COMPLETE DOCKER ROADMAP
### From Zero to Production Containers — Structured & Actionable

---

## 📍 Where You Are → Where You'll Go

```
🟢 BEGINNER            🟡 INTERMEDIATE          🔴 ADVANCED            🏆 PRO
   (Weeks 1-3)            (Weeks 4-7)             (Weeks 8-11)          (Weeks 12-14)
   
   What is Docker?,       Dockerfiles,            Multi-stage builds,   Kubernetes,
   Containers vs VMs,     Volumes, Networks,      Security, CI/CD,      Orchestration,
   Basic CLI              Docker Compose          Optimization          Production Deploy
```

---

## 🧒 ELI5: What Even Is Docker?

```
🍱 The Tiffin Box Analogy:

  THE PROBLEM:
  ─────────────
  You build a Python app on your laptop. It works perfectly. ✅
  You send it to your friend. "It doesn't work on my machine!" ❌
  You deploy to server. "Missing dependency!" ❌
  
  WHY?
  Your laptop has Python 3.11, friend has 3.9.
  Your laptop has libpq installed, server doesn't.
  Your laptop runs Ubuntu, server runs CentOS.
  
  
  THE SOLUTION — Docker:
  ──────────────────────
  Pack your app + ALL its dependencies + the exact OS config
  into a CONTAINER (like a tiffin box 🍱).
  
  The tiffin box contains EVERYTHING needed:
  ┌─────────────────────────────────────┐
  │  🍱 Docker Container                │
  │  ┌─────────────────────────────┐   │
  │  │  Your App Code              │   │
  │  │  Python 3.11                │   │
  │  │  pip packages               │   │
  │  │  System libraries (libpq)   │   │
  │  │  Config files               │   │
  │  │  Ubuntu 22.04 (minimal)     │   │
  │  └─────────────────────────────┘   │
  └─────────────────────────────────────┘
  
  Now this tiffin box runs IDENTICALLY on:
  ✅ Your laptop (Windows)
  ✅ Friend's laptop (Mac)
  ✅ Production server (Linux)
  ✅ Cloud (AWS/GCP/Azure)
  
  "It works on my machine" → "It works on EVERY machine" 🎉
```

```
📊 KEY CONCEPTS — The Restaurant Kitchen Analogy 🍳

  ┌──────────────────────────────────────────────────────────────┐
  │                                                              │
  │  DOCKERFILE = Recipe 📝                                      │
  │  Instructions to build the dish (image)                      │
  │  "Take Ubuntu, install Python, copy code, run app"           │
  │                                                              │
  │  IMAGE = Frozen Meal 🧊                                      │
  │  The prepared, packaged dish. Ready to serve anytime.        │
  │  Immutable — same image always produces same container.      │
  │  Think: "thali plate with everything arranged and sealed"    │
  │                                                              │
  │  CONTAINER = Served Meal 🍽️                                  │
  │  A RUNNING instance of an image.                             │
  │  You can have 10 containers from 1 image.                    │
  │  Think: "10 customers eating from same recipe"               │
  │                                                              │
  │  REGISTRY = Cloud Kitchen Menu (DockerHub) ☁️                 │
  │  Where images are stored and shared.                         │
  │  Think: "Zomato for Docker images"                           │
  │  docker pull nginx = "order nginx from the menu"             │
  │                                                              │
  │  VOLUME = Refrigerator 🧊                                    │
  │  Persistent storage that survives container restarts.        │
  │  Container dies → data in volume SURVIVES.                   │
  │  Think: "ingredients stored in fridge, not on the counter"   │
  │                                                              │
  │  NETWORK = Internal Phone System 📞                          │
  │  How containers talk to each other.                          │
  │  "Backend container, call the database container"            │
  │                                                              │
  └──────────────────────────────────────────────────────────────┘


  FLOW:

  Dockerfile  ──build──►  Image  ──run──►  Container
  (recipe)               (frozen meal)    (served meal)
                              │
                         push/pull
                              │
                         ◄────┘
                      Registry
                      (DockerHub)
```

---

## 🟢 PHASE 1: INTRODUCTION & FOUNDATIONS (Weeks 1–3)

### Week 1: Understanding Containers & Docker

| # | Topic | Priority | Est. Hours | Status |
|---|-------|----------|-----------|--------|
| 1 | **What are Containers?** — process isolation, not mini VMs | 🔴 Critical | 2h | ⬜ |
| 2 | **Why do we need Containers?** — "works on my machine" problem | 🔴 Critical | 1h | ⬜ |
| 3 | **Bare Metal vs VMs vs Containers** — evolution of deployment | 🔴 Critical | 2h | ⬜ |
| 4 | **Docker and OCI** — Open Container Initiative, standards | 🟡 Important | 1h | ⬜ |
| 5 | **Underlying Technologies** — Namespaces, cgroups, Union Filesystems | 🟡 Important | 2h | ⬜ |

```
🖥️ BARE METAL vs VMs vs CONTAINERS — The Evolution

┌──────────────────────────────────────────────────────────────────┐
│                                                                  │
│  ERA 1: BARE METAL (1990s-2000s)                                │
│  ════════════════════════════════                                 │
│  One physical server = One application                           │
│                                                                  │
│  ┌──────────────────────────┐                                   │
│  │        App A             │                                   │
│  │   (entire server for     │                                   │
│  │    one app — wasteful!)  │                                   │
│  ├──────────────────────────┤                                   │
│  │   Operating System       │                                   │
│  ├──────────────────────────┤                                   │
│  │   Physical Hardware      │                                   │
│  └──────────────────────────┘                                   │
│                                                                  │
│  ❌ Expensive: ₹10L server for one app using 10% CPU            │
│  ❌ Slow: Weeks to set up a new server                          │
│  ❌ Wasteful: 90% resources idle                                │
│                                                                  │
│                                                                  │
│  ERA 2: VIRTUAL MACHINES (2000s-2015)                           │
│  ═════════════════════════════════════                            │
│  One physical server = Multiple virtual servers                  │
│                                                                  │
│  ┌──────────┐ ┌──────────┐ ┌──────────┐                        │
│  │  App A   │ │  App B   │ │  App C   │                        │
│  ├──────────┤ ├──────────┤ ├──────────┤                        │
│  │ Guest OS │ │ Guest OS │ │ Guest OS │ ← Each VM has          │
│  │ (Ubuntu) │ │ (CentOS) │ │ (Debian) │   FULL OS (1-2 GB!)   │
│  └──────────┘ └──────────┘ └──────────┘                        │
│  ┌─────────────────────────────────────┐                        │
│  │       Hypervisor (VMware/KVM)       │                        │
│  ├─────────────────────────────────────┤                        │
│  │       Host Operating System         │                        │
│  ├─────────────────────────────────────┤                        │
│  │       Physical Hardware             │                        │
│  └─────────────────────────────────────┘                        │
│                                                                  │
│  ✅ Better utilization                                           │
│  ❌ Each VM = full OS copy (heavy: 1-2 GB per VM)               │
│  ❌ Slow startup (minutes)                                      │
│  ❌ Memory overhead (each OS uses 512MB+ RAM)                   │
│                                                                  │
│                                                                  │
│  ERA 3: CONTAINERS (2013-Present) 🐳                            │
│  ════════════════════════════════════                             │
│  One OS = Multiple isolated processes                            │
│                                                                  │
│  ┌──────────┐ ┌──────────┐ ┌──────────┐                        │
│  │  App A   │ │  App B   │ │  App C   │                        │
│  │  + deps  │ │  + deps  │ │  + deps  │ ← Only app + its deps │
│  │  (50 MB) │ │  (120 MB)│ │  (30 MB) │   SHARES host kernel! │
│  └──────────┘ └──────────┘ └──────────┘                        │
│  ┌─────────────────────────────────────┐                        │
│  │       Container Runtime (Docker)    │                        │
│  ├─────────────────────────────────────┤                        │
│  │       Host Operating System         │                        │
│  ├─────────────────────────────────────┤                        │
│  │       Physical Hardware             │                        │
│  └─────────────────────────────────────┘                        │
│                                                                  │
│  ✅ Lightweight (MBs, not GBs)                                   │
│  ✅ Fast startup (seconds, not minutes)                          │
│  ✅ Consistent across environments                               │
│  ✅ Easy to scale (spin up 100 containers in seconds)            │
│                                                                  │
└──────────────────────────────────────────────────────────────────┘


  COMPARISON TABLE:

  ┌──────────────────┬────────────┬────────────┬────────────────┐
  │  Feature         │ Bare Metal │ VM         │ Container      │
  ├──────────────────┼────────────┼────────────┼────────────────┤
  │ Startup Time     │ Minutes    │ 30s-2min   │ Milliseconds   │
  │ Size             │ Full OS    │ 1-2 GB     │ 10-500 MB      │
  │ Isolation        │ N/A        │ Full (HW)  │ Process-level  │
  │ Performance      │ Best       │ Good       │ Near-native    │
  │ Density          │ 1 per      │ 10-20 per  │ 100s per       │
  │ (per server)     │ server     │ server     │ server         │
  │ OS Independence  │ ❌         │ ✅         │ ❌ (shares     │
  │                  │            │            │  host kernel)  │
  │ Resource Usage   │ Wasteful   │ Moderate   │ Minimal ✅     │
  │ Portability      │ ❌         │ Medium     │ Excellent ✅   │
  └──────────────────┴────────────┴────────────┴────────────────┘
```

```
⚙️ UNDERLYING TECHNOLOGIES — How Docker Actually Works (Under the Hood)

  Docker is NOT a VM. It uses LINUX KERNEL features:

  ┌────────────────────────────────────────────────────────────┐
  │                                                            │
  │  1. NAMESPACES 🏠 — Isolation                              │
  │  ────────────────────────────                               │
  │  Each container gets its own "view" of the system:         │
  │                                                            │
  │  • PID Namespace:  Container sees only ITS processes       │
  │    (PID 1 = your app, not the host's init)                 │
  │  • Network NS:     Container has its own IP, ports         │
  │  • Mount NS:       Container has its own filesystem        │
  │  • User NS:        Container has its own user IDs          │
  │  • UTS NS:         Container has its own hostname          │
  │                                                            │
  │  → Like apartments in a building — each has own address,   │
  │    own door number, can't see inside other apartments      │
  │                                                            │
  │                                                            │
  │  2. CGROUPS 📊 — Resource Limits                           │
  │  ───────────────────────────────                            │
  │  Control HOW MUCH resources each container gets:           │
  │                                                            │
  │  • CPU:    "Container A gets max 2 CPU cores"              │
  │  • Memory: "Container B gets max 512MB RAM"                │
  │  • I/O:    "Container C gets max 100MB/s disk I/O"         │
  │                                                            │
  │  → Like electricity meters — each apartment has a limit    │
  │                                                            │
  │                                                            │
  │  3. UNION FILESYSTEMS 📁 — Layered Images                  │
  │  ─────────────────────────────────────────                  │
  │  Images are built in LAYERS. Each layer is read-only.      │
  │  Container adds a thin WRITABLE layer on top.              │
  │                                                            │
  │  ┌─────────────────────┐  ← Writable (container changes)  │
  │  ├─────────────────────┤                                   │
  │  │ Layer 4: COPY app   │  ← Read-only                     │
  │  ├─────────────────────┤                                   │
  │  │ Layer 3: pip install │  ← Read-only (shared!)           │
  │  ├─────────────────────┤                                   │
  │  │ Layer 2: apt install │  ← Read-only (shared!)           │
  │  ├─────────────────────┤                                   │
  │  │ Layer 1: Ubuntu base │  ← Read-only (shared!)           │
  │  └─────────────────────┘                                   │
  │                                                            │
  │  → 10 containers from same image = share base layers       │
  │    = SAVES disk space massively                            │
  │                                                            │
  └────────────────────────────────────────────────────────────┘
```

---

### Week 2: Prerequisites — Linux Fundamentals

| # | Topic | Priority | Est. Hours | Status |
|---|-------|----------|-----------|--------|
| 6 | **Shell Commands** — `ls`, `cd`, `cp`, `mv`, `chmod`, `ps`, `grep`, `curl` | 🔴 Critical | 3h | ⬜ |
| 7 | **Users/Groups/Permissions** — `chmod`, `chown`, `root`, `sudo` | 🟡 Important | 2h | ⬜ |
| 8 | **Package Managers** — `apt`, `yum`, `apk` | 🟡 Important | 1h | ⬜ |
| 9 | **Shell Scripting** — basic bash scripts, variables, conditionals | 🟡 Important | 2h | ⬜ |
| 10 | **Networking Basics** — ports, IP addresses, DNS, `localhost` | 🟡 Important | 2h | ⬜ |

```bash
# 🐧 Linux Commands You MUST Know for Docker

# ─── File System ─────────────────────────────
ls -la              # List files with permissions
cd /app             # Change directory
mkdir -p /app/data  # Create nested directories
cp -r src/ dest/    # Copy recursively
rm -rf /tmp/cache   # Remove recursively (careful!)
cat Dockerfile      # View file contents
tail -f app.log     # Follow log output in real-time

# ─── Process Management ─────────────────────
ps aux              # List all running processes
ps aux | grep python # Find specific processes
kill -9 <PID>       # Force kill a process
top / htop          # Monitor CPU/Memory usage

# ─── Networking ──────────────────────────────
curl http://localhost:8000       # HTTP request
curl -X POST http://api/data    # POST request
wget https://example.com/file   # Download file
netstat -tlnp                   # List open ports
ping google.com                 # Test connectivity
ip addr                         # Show IP addresses

# ─── Permissions ─────────────────────────────
chmod 755 script.sh   # rwxr-xr-x (owner:all, others:read+exec)
chmod +x script.sh    # Make executable
chown user:group file # Change ownership
whoami                # Current user

# ─── Package Management ─────────────────────
# Debian/Ubuntu:
apt update && apt install -y python3 curl
# Alpine (common in Docker):
apk add --no-cache python3 curl
# CentOS/RHEL:
yum install -y python3 curl

# ─── Text Processing ────────────────────────
grep "error" app.log            # Search in file
grep -r "TODO" src/             # Search recursively
echo $HOME                      # Print environment variable
export API_KEY="abc123"         # Set environment variable
env                             # List all env variables
```

---

### Week 3: Installation & Basic Docker CLI

| # | Topic | Priority | Est. Hours | Status |
|---|-------|----------|-----------|--------|
| 11 | **Installation** — Docker Desktop (Win/Mac) or Docker Engine (Linux) | 🔴 Critical | 1h | ⬜ |
| 12 | **Docker CLI — Images** — `pull`, `images`, `rmi`, `inspect` | 🔴 Critical | 2h | ⬜ |
| 13 | **Docker CLI — Containers** — `run`, `ps`, `stop`, `rm`, `logs`, `exec` | 🔴 Critical | 3h | ⬜ |
| 14 | **Docker CLI — Volumes** — `volume create`, `volume ls`, `volume rm` | 🔴 Critical | 1h | ⬜ |
| 15 | **Docker CLI — Networks** — `network create`, `network ls`, `network connect` | 🟡 Important | 1h | ⬜ |
| 16 | **Using 3rd Party Images** — databases, utilities from DockerHub | 🔴 Critical | 2h | ⬜ |

```bash
# 🐳 DOCKER CLI — The Complete Cheat Sheet

# ═══════════════════════════════════════════════
# 🖼️ IMAGES — Your "frozen meals"
# ═══════════════════════════════════════════════

docker pull nginx                     # Download image from DockerHub
docker pull python:3.11-slim          # Specific version (tag)
docker images                         # List all local images
docker image ls                       # Same as above
docker image inspect nginx            # Detailed info about image
docker image rm nginx                 # Remove image
docker rmi nginx                      # Shorthand for above
docker image prune                    # Remove unused images
docker image prune -a                 # Remove ALL unused images


# ═══════════════════════════════════════════════
# 📦 CONTAINERS — Your "running meals"
# ═══════════════════════════════════════════════

# ─── Running Containers ─────────────────────
docker run nginx                      # Run (foreground, blocks terminal)
docker run -d nginx                   # Run in BACKGROUND (detached)
docker run -d --name my-web nginx     # Run with a custom name
docker run -d -p 8080:80 nginx        # Map host:8080 → container:80
docker run -it ubuntu bash            # Interactive terminal (enter container)
docker run --rm nginx                 # Auto-remove when stopped

# ─── Managing Containers ────────────────────
docker ps                             # List RUNNING containers
docker ps -a                          # List ALL containers (including stopped)
docker stop my-web                    # Gracefully stop
docker start my-web                   # Start a stopped container
docker restart my-web                 # Restart
docker kill my-web                    # Force kill
docker rm my-web                      # Remove stopped container
docker rm -f my-web                   # Force remove (even if running)
docker container prune                # Remove ALL stopped containers

# ─── Inspecting & Debugging ─────────────────
docker logs my-web                    # View container logs
docker logs -f my-web                 # Follow logs (like tail -f)
docker logs --tail 50 my-web          # Last 50 lines
docker exec -it my-web bash           # Open shell INSIDE running container
docker exec my-web cat /etc/hostname  # Run command inside container
docker inspect my-web                 # Full JSON details
docker stats                          # Live CPU/Memory/Network stats
docker top my-web                     # Processes running inside container

# ─── Resource Limits ────────────────────────
docker run -d --memory="512m" --cpus="1.5" nginx  # Limit resources


# ═══════════════════════════════════════════════
# 💾 VOLUMES — Persistent storage
# ═══════════════════════════════════════════════

docker volume create my-data          # Create a named volume
docker volume ls                      # List volumes
docker volume inspect my-data         # Volume details
docker volume rm my-data              # Remove volume
docker volume prune                   # Remove unused volumes


# ═══════════════════════════════════════════════
# 🌐 NETWORKS — Container communication
# ═══════════════════════════════════════════════

docker network create my-network      # Create custom network
docker network ls                     # List networks
docker network inspect my-network     # Network details
docker network connect my-network my-web   # Connect container to network
docker network disconnect my-network my-web


# ═══════════════════════════════════════════════
# 🧹 CLEANUP — Reclaim disk space
# ═══════════════════════════════════════════════

docker system df                      # Show disk usage
docker system prune                   # Remove unused everything
docker system prune -a --volumes      # Nuclear cleanup (careful!)
```

```
🔑 THE MOST IMPORTANT COMMAND: docker run

docker run [OPTIONS] IMAGE [COMMAND]

  OPTIONS you'll use daily:
  ┌──────────────────────┬───────────────────────────────────────┐
  │  Flag                │  What it does                         │
  ├──────────────────────┼───────────────────────────────────────┤
  │  -d                  │  Detached (background)                │
  │  -it                 │  Interactive terminal (enter shell)   │
  │  --name my-app       │  Give container a name                │
  │  -p 8080:80          │  Map port host:container              │
  │  -v data:/app/data   │  Mount volume                         │
  │  -e API_KEY=abc      │  Set environment variable             │
  │  --env-file .env     │  Load env vars from file              │
  │  --rm                │  Auto-remove when stopped             │
  │  --network my-net    │  Connect to specific network          │
  │  --memory 512m       │  Memory limit                         │
  │  --cpus 1.5          │  CPU limit                            │
  │  --restart always    │  Auto-restart on failure              │
  │  -w /app             │  Set working directory                │
  └──────────────────────┴───────────────────────────────────────┘
```

```bash
# 🏋️ HANDS-ON: Run Real Databases in 30 Seconds!

# ─── PostgreSQL ──────────────────────────────
docker run -d \
  --name my-postgres \
  -e POSTGRES_USER=admin \
  -e POSTGRES_PASSWORD=secret123 \
  -e POSTGRES_DB=college_db \
  -p 5432:5432 \
  -v pgdata:/var/lib/postgresql/data \
  postgres:16-alpine

# Connect: psql -h localhost -U admin -d college_db


# ─── MongoDB ─────────────────────────────────
docker run -d \
  --name my-mongo \
  -e MONGO_INITDB_ROOT_USERNAME=admin \
  -e MONGO_INITDB_ROOT_PASSWORD=secret123 \
  -p 27017:27017 \
  -v mongodata:/data/db \
  mongo:7


# ─── Redis ───────────────────────────────────
docker run -d \
  --name my-redis \
  -p 6379:6379 \
  redis:7-alpine


# ─── MySQL ───────────────────────────────────
docker run -d \
  --name my-mysql \
  -e MYSQL_ROOT_PASSWORD=secret123 \
  -e MYSQL_DATABASE=college_db \
  -p 3306:3306 \
  -v mysqldata:/var/lib/mysql \
  mysql:8


# 💡 Without Docker, installing PostgreSQL takes:
#    → Download installer
#    → Configure paths
#    → Set up users
#    → Handle port conflicts
#    → 30+ minutes of pain
#
#    With Docker: ONE COMMAND, 30 seconds. Done. 🚀
```

---

## 🟡 PHASE 2: BUILDING & COMPOSING (Weeks 4–7)

### Week 4: Data Persistence

| # | Topic | Priority | Est. Hours | Status |
|---|-------|----------|-----------|--------|
| 17 | **Ephemeral Container Filesystem** — data disappears when container dies | 🔴 Critical | 1h | ⬜ |
| 18 | **Volume Mounts** — Docker-managed persistent storage | 🔴 Critical | 2h | ⬜ |
| 19 | **Bind Mounts** — map host directory into container | 🔴 Critical | 2h | ⬜ |
| 20 | **tmpfs Mounts** — in-memory storage (secrets, temp data) | 🟢 Good to know | 1h | ⬜ |

```
💾 DATA PERSISTENCE — The 3 Types of Mounts

  WITHOUT any mount:
  ┌────────────────────────┐
  │     Container          │
  │  ┌──────────────────┐  │
  │  │ Writable Layer   │  │ ← Data written here
  │  │ (ephemeral!)     │  │ ← LOST when container is removed!
  │  └──────────────────┘  │
  │  ┌──────────────────┐  │
  │  │ Image Layers     │  │ ← Read-only
  │  │ (read-only)      │  │
  │  └──────────────────┘  │
  └────────────────────────┘


  THREE SOLUTIONS:

  1️⃣ VOLUME MOUNT (Docker-managed) — RECOMMENDED ✅
  ┌─────────────┐       ┌────────────────────┐
  │  Container  │──────►│  Docker Volume     │
  │  /app/data  │       │  /var/lib/docker/  │
  │             │       │  volumes/my-data/  │
  └─────────────┘       └────────────────────┘
  
  docker run -v my-data:/app/data my-image
  
  ✅ Docker manages location and lifecycle
  ✅ Easy to backup, migrate, share between containers
  ✅ Works on all OS
  📍 Best for: databases, persistent app data


  2️⃣ BIND MOUNT (Host directory mapped)
  ┌─────────────┐       ┌────────────────────┐
  │  Container  │──────►│  Host Machine      │
  │  /app       │       │  /home/user/       │
  │             │       │  project/          │
  └─────────────┘       └────────────────────┘
  
  docker run -v $(pwd):/app my-image
  
  ✅ Direct access to host files
  ✅ Changes reflect immediately (hot reload!)
  ❌ Dependent on host OS file structure
  📍 Best for: development (live code editing)


  3️⃣ tmpfs MOUNT (In-memory only)
  ┌─────────────┐       ┌────────────────────┐
  │  Container  │──────►│  Host RAM          │
  │  /tmp/secret│       │  (memory only)     │
  │             │       │  Never touches disk│
  └─────────────┘       └────────────────────┘
  
  docker run --tmpfs /tmp/secrets my-image
  
  ✅ Fast (RAM speed)
  ✅ Secure (never written to disk)
  ❌ Lost when container stops
  📍 Best for: secrets, temp files, caches


  COMPARISON:
  ┌──────────────────┬───────────┬───────────┬────────────┐
  │  Feature         │ Volume    │ Bind Mount│ tmpfs      │
  ├──────────────────┼───────────┼───────────┼────────────┤
  │ Managed by       │ Docker    │ You       │ OS/RAM     │
  │ Persists?        │ ✅ Yes    │ ✅ Yes    │ ❌ No      │
  │ Shareable?       │ ✅ Yes    │ ❌ Risky  │ ❌ No      │
  │ Host access      │ Via Docker│ Direct ✅ │ ❌ No      │
  │ Performance      │ Good      │ Best      │ Fastest    │
  │ Use case         │ Databases │ Dev code  │ Secrets    │
  │                  │ prod data │ config    │ temp files │
  └──────────────────┴───────────┴───────────┴────────────┘
```

---

### Week 5: Building Container Images — Dockerfiles

| # | Topic | Priority | Est. Hours | Status |
|---|-------|----------|-----------|--------|
| 21 | **Dockerfile Basics** — FROM, RUN, COPY, CMD, EXPOSE, WORKDIR | 🔴 Critical | 3h | ⬜ |
| 22 | **Dockerfile Instructions Deep Dive** — ARG, ENV, ENTRYPOINT, ADD, LABEL | 🔴 Critical | 2h | ⬜ |
| 23 | **Efficient Layer Caching** — order matters, cache busting | 🔴 Critical | 2h | ⬜ |
| 24 | **Image Size & Security** — multi-stage builds, slim bases, .dockerignore | 🔴 Critical | 3h | ⬜ |
| 25 | **.dockerignore** — exclude unnecessary files | 🟡 Important | 0.5h | ⬜ |

```dockerfile
# 🐳 DOCKERFILE — Complete Reference

# ═══════════════════════════════════════════════
# Every Dockerfile instruction explained:
# ═══════════════════════════════════════════════

# FROM — Base image (MUST be first instruction)
# Like "Start with this pre-built kitchen"
FROM python:3.11-slim

# LABEL — Metadata (who built this, version, etc.)
LABEL maintainer="rahul@college.edu.in"
LABEL version="1.0"

# ARG — Build-time variables (not available at runtime!)
ARG APP_VERSION=1.0.0

# ENV — Runtime environment variables (available inside container)
ENV PYTHONUNBUFFERED=1 \
    PYTHONDONTWRITEBYTECODE=1 \
    APP_PORT=8000

# WORKDIR — Set working directory (like cd, but creates if missing)
WORKDIR /app

# COPY — Copy files from host to container
# (prefer COPY over ADD — ADD has extra magic that's rarely needed)
COPY requirements.txt .

# RUN — Execute commands during BUILD (creates a new layer)
RUN pip install --no-cache-dir -r requirements.txt

# COPY app code (AFTER pip install — for better caching!)
COPY . .

# EXPOSE — Document which port the app uses (doesn't actually publish!)
EXPOSE 8000

# HEALTHCHECK — Docker checks if container is healthy
HEALTHCHECK --interval=30s --timeout=10s --retries=3 \
    CMD curl -f http://localhost:8000/health || exit 1

# USER — Run as non-root (security best practice!)
RUN adduser --disabled-password --gecos '' appuser
USER appuser

# CMD — Default command when container starts
# (can be overridden at runtime)
CMD ["python", "main.py"]

# ENTRYPOINT — Fixed command (CMD becomes arguments to this)
# ENTRYPOINT ["python"]
# CMD ["main.py"]
# → runs: python main.py
# → docker run myapp other.py → runs: python other.py
```

```
📝 CMD vs ENTRYPOINT — The Confusion Killer

  ┌──────────────────────────────────────────────────────────────┐
  │                                                              │
  │  CMD = "default suggestion" (easily overridden)              │
  │  ──────────────────────────────────────────                   │
  │  CMD ["python", "main.py"]                                   │
  │                                                              │
  │  docker run myapp                    → python main.py        │
  │  docker run myapp python test.py     → python test.py  ✅    │
  │  (CMD is REPLACED)                                           │
  │                                                              │
  │                                                              │
  │  ENTRYPOINT = "fixed command" (not easily overridden)        │
  │  ────────────────────────────────────────────                  │
  │  ENTRYPOINT ["python"]                                       │
  │  CMD ["main.py"]                                             │
  │                                                              │
  │  docker run myapp                    → python main.py        │
  │  docker run myapp test.py            → python test.py  ✅    │
  │  (CMD is appended to ENTRYPOINT)                             │
  │                                                              │
  │                                                              │
  │  💡 Rule of thumb:                                            │
  │  • Use CMD alone for simple apps                             │
  │  • Use ENTRYPOINT + CMD when you want a fixed executable     │
  │    but flexible arguments                                    │
  │                                                              │
  └──────────────────────────────────────────────────────────────┘
```

```dockerfile
# ⚡ EFFICIENT LAYER CACHING — Order Matters!

# ❌ BAD — Cache busted on EVERY code change
FROM python:3.11-slim
WORKDIR /app
COPY . .                          # ← Code changes = this layer invalidated
RUN pip install -r requirements.txt  # ← Must reinstall EVERY time!
CMD ["python", "main.py"]

# Why bad? Any code change → COPY . . changes → ALL subsequent 
# layers are rebuilt → pip install runs again (5+ minutes!)


# ✅ GOOD — Dependencies cached separately from code
FROM python:3.11-slim
WORKDIR /app
COPY requirements.txt .          # ← Only changes when deps change
RUN pip install -r requirements.txt  # ← CACHED if requirements.txt unchanged!
COPY . .                          # ← Code changes only rebuild THIS layer
CMD ["python", "main.py"]

# Why good? Code changes → only COPY . . rebuilds
# pip install uses CACHE → builds in seconds, not minutes!


# LAYER CACHING RULES:
# ┌───────────────────────────────────────────────────────────┐
# │ 1. Put things that change LEAST at the TOP               │
# │ 2. Put things that change MOST at the BOTTOM              │
# │ 3. Separate dependency install from code copy             │
# │ 4. Combine RUN commands to reduce layers                  │
# │ 5. Use .dockerignore to exclude unnecessary files         │
# └───────────────────────────────────────────────────────────┘
```

```dockerfile
# 🏆 MULTI-STAGE BUILD — The Secret to Tiny Images

# ── Stage 1: BUILD (heavy, has compilers) ────
FROM python:3.11 AS builder

WORKDIR /app
COPY requirements.txt .
RUN pip install --user --no-cache-dir -r requirements.txt

COPY . .
# Could run tests here, compile things, etc.


# ── Stage 2: PRODUCTION (minimal, no build tools) ──
FROM python:3.11-slim AS production

WORKDIR /app

# Copy ONLY the installed packages from builder
COPY --from=builder /root/.local /root/.local
COPY --from=builder /app .

# Make sure scripts in .local are usable
ENV PATH=/root/.local/bin:$PATH

# Non-root user
RUN adduser --disabled-password --gecos '' appuser
USER appuser

EXPOSE 8000
CMD ["uvicorn", "main:app", "--host", "0.0.0.0", "--port", "8000"]


# RESULT:
# ┌────────────────────────────────────────────┐
# │  Without multi-stage:  ~1.2 GB  😰         │
# │  python:3.11 (full) + build tools + all    │
# │                                            │
# │  With multi-stage:     ~180 MB  🎉         │
# │  python:3.11-slim + only runtime deps      │
# │                                            │
# │  With alpine:          ~80 MB   🚀         │
# │  python:3.11-alpine + minimal              │
# └────────────────────────────────────────────┘
```

```
📏 IMAGE SIZE COMPARISON — Base Images

  ┌──────────────────────────┬──────────┬──────────────────────┐
  │  Base Image              │  Size    │  Use Case            │
  ├──────────────────────────┼──────────┼──────────────────────┤
  │  ubuntu:22.04            │  ~77 MB  │  General purpose     │
  │  python:3.11             │  ~1 GB   │  Dev/build stage     │
  │  python:3.11-slim        │  ~150 MB │  Production ✅       │
  │  python:3.11-alpine      │  ~50 MB  │  Minimal (⚠️ musl)   │
  │  node:20                 │  ~1 GB   │  Dev/build stage     │
  │  node:20-slim            │  ~200 MB │  Production ✅       │
  │  node:20-alpine          │  ~130 MB │  Minimal             │
  │  golang:1.22             │  ~800 MB │  Build stage only    │
  │  gcr.io/distroless/base  │  ~20 MB  │  Most secure 🔒      │
  │  scratch                 │  0 MB    │  Go/Rust static bins │
  └──────────────────────────┴──────────┴──────────────────────┘

  💡 Recommendation:
     Dev:        Use full image (python:3.11) — has debug tools
     Production: Use slim (python:3.11-slim) — balanced
     Extreme:    Use alpine — but beware musl vs glibc issues
```

```
# 📄 .dockerignore — Must Have!

# .dockerignore
__pycache__
*.pyc
*.pyo
.git
.gitignore
.env
.env.local
node_modules
.vscode
.idea
*.md
docker-compose*.yml
Dockerfile*
.dockerignore
tests/
docs/
*.log
.coverage
htmlcov/
.pytest_cache
venv/
.venv/
```

---

### Week 6–7: Docker Compose & Networking

| # | Topic | Priority | Est. Hours | Status |
|---|-------|----------|-----------|--------|
| 26 | **Docker Compose Basics** — `docker-compose.yml`, services, `up`, `down` | 🔴 Critical | 3h | ⬜ |
| 27 | **Multi-Service Apps** — app + database + cache + reverse proxy | 🔴 Critical | 4h | ⬜ |
| 28 | **Docker Networking** — bridge, host, overlay, service discovery | 🔴 Critical | 3h | ⬜ |
| 29 | **Environment Variables** — `.env` files, secrets management | 🟡 Important | 1h | ⬜ |
| 30 | **Compose Commands** — `up`, `down`, `build`, `logs`, `exec`, `ps` | 🔴 Critical | 1h | ⬜ |
| 31 | **Depends_on & Health Checks** — service startup order | 🟡 Important | 1h | ⬜ |

```
🎼 DOCKER COMPOSE — The Orchestra Conductor

  Without Compose, running a full-stack app:
  ─────────────────────────────────────────
  docker network create myapp-network
  docker run -d --name db --network myapp-network -e POSTGRES_PASSWORD=... postgres
  docker run -d --name redis --network myapp-network redis
  docker run -d --name api --network myapp-network -p 8000:8000 -e DB_HOST=db myapp
  docker run -d --name frontend --network myapp-network -p 3000:3000 myfrontend
  
  → 4 separate commands, easy to mess up, hard to maintain


  With Compose, ONE file describes EVERYTHING:
  ────────────────────────────────────────────
  docker compose up -d     ← One command. Done. 🎉
  docker compose down      ← Tear down everything cleanly
```

```yaml
# 🏗️ docker-compose.yml — Full-Stack Application
# Project: College Management System

version: '3.9'

services:
  # ─── Database ──────────────────────────────
  db:
    image: postgres:16-alpine
    container_name: college-db
    restart: unless-stopped
    environment:
      POSTGRES_USER: admin
      POSTGRES_PASSWORD: ${DB_PASSWORD:-secret123}
      POSTGRES_DB: college_db
    ports:
      - "5432:5432"
    volumes:
      - pgdata:/var/lib/postgresql/data
      - ./init.sql:/docker-entrypoint-initdb.d/init.sql  # Auto-run on first start
    healthcheck:
      test: ["CMD-SHELL", "pg_isready -U admin -d college_db"]
      interval: 10s
      timeout: 5s
      retries: 5

  # ─── Cache ─────────────────────────────────
  redis:
    image: redis:7-alpine
    container_name: college-redis
    restart: unless-stopped
    ports:
      - "6379:6379"
    volumes:
      - redisdata:/data
    command: redis-server --appendonly yes  # Enable persistence

  # ─── Backend API ───────────────────────────
  api:
    build:
      context: ./backend
      dockerfile: Dockerfile
    container_name: college-api
    restart: unless-stopped
    ports:
      - "8000:8000"
    environment:
      DATABASE_URL: postgresql://admin:${DB_PASSWORD:-secret123}@db:5432/college_db
      REDIS_URL: redis://redis:6379/0
      SECRET_KEY: ${SECRET_KEY:-dev-secret-key}
      ENVIRONMENT: ${ENVIRONMENT:-development}
    volumes:
      - ./backend:/app        # Bind mount for hot reload (dev only!)
    depends_on:
      db:
        condition: service_healthy
      redis:
        condition: service_started
    command: uvicorn main:app --host 0.0.0.0 --port 8000 --reload

  # ─── Frontend ──────────────────────────────
  frontend:
    build:
      context: ./frontend
      dockerfile: Dockerfile
    container_name: college-frontend
    restart: unless-stopped
    ports:
      - "3000:3000"
    environment:
      REACT_APP_API_URL: http://localhost:8000
    volumes:
      - ./frontend/src:/app/src  # Hot reload for dev
    depends_on:
      - api

  # ─── Reverse Proxy (Production) ───────────
  nginx:
    image: nginx:alpine
    container_name: college-nginx
    restart: unless-stopped
    ports:
      - "80:80"
      - "443:443"
    volumes:
      - ./nginx/nginx.conf:/etc/nginx/nginx.conf:ro
      - ./nginx/certs:/etc/nginx/certs:ro
    depends_on:
      - api
      - frontend

  # ─── Database Admin UI ────────────────────
  adminer:
    image: adminer
    container_name: college-adminer
    restart: unless-stopped
    ports:
      - "8080:8080"
    depends_on:
      - db

# ─── Named Volumes ───────────────────────────
volumes:
  pgdata:
    driver: local
  redisdata:
    driver: local

# ─── Custom Network (auto-created by compose) ─
networks:
  default:
    name: college-network
```

```bash
# 🎮 DOCKER COMPOSE CLI — Daily Commands

# ─── Lifecycle ───────────────────────────────
docker compose up                     # Start all services (foreground)
docker compose up -d                  # Start in background
docker compose up -d --build          # Rebuild images then start
docker compose up -d api              # Start only specific service
docker compose down                   # Stop and remove containers
docker compose down -v                # Also remove volumes (⚠️ data loss!)
docker compose restart api            # Restart specific service

# ─── Monitoring ──────────────────────────────
docker compose ps                     # List running services
docker compose logs                   # View all logs
docker compose logs -f api            # Follow specific service logs
docker compose logs --tail 50 api     # Last 50 lines
docker compose top                    # Running processes per service

# ─── Building ───────────────────────────────
docker compose build                  # Build all services
docker compose build api              # Build specific service
docker compose build --no-cache api   # Force rebuild (no cache)

# ─── Executing ──────────────────────────────
docker compose exec api bash          # Open shell in running service
docker compose exec db psql -U admin  # Run command in service
docker compose run api pytest         # Run one-off command (new container)

# ─── Scaling ────────────────────────────────
docker compose up -d --scale api=3    # Run 3 instances of api
```

```
🌐 DOCKER NETWORKING — How Containers Talk

  ┌─────────────────────────────────────────────────────────────┐
  │                                                             │
  │  DEFAULT: bridge network                                    │
  │  ─────────────────────                                      │
  │  All compose services auto-join the SAME network.           │
  │  Services can reach each other BY NAME.                     │
  │                                                             │
  │  ┌──────────┐     ┌──────────┐     ┌──────────┐           │
  │  │   api    │────►│   db     │     │  redis   │           │
  │  │          │     │          │     │          │           │
  │  │ DB_HOST= │     │ port:5432│     │ port:6379│           │
  │  │ "db"     │     │          │     │          │           │
  │  └──────────┘     └──────────┘     └──────────┘           │
  │       │                │                │                  │
  │       └────────────────┴────────────────┘                  │
  │                  college-network (bridge)                   │
  │                                                             │
  │                                                             │
  │  KEY INSIGHT:                                               │
  │  Inside Docker network:                                     │
  │    api connects to db at → db:5432 (NOT localhost:5432!)   │
  │    api connects to redis → redis:6379                      │
  │  The SERVICE NAME = hostname inside Docker network.         │
  │                                                             │
  │                                                             │
  │  From HOST machine:                                         │
  │    Browser → localhost:8000 (mapped via -p 8000:8000)      │
  │    psql → localhost:5432 (mapped via -p 5432:5432)         │
  │                                                             │
  └─────────────────────────────────────────────────────────────┘


  NETWORK TYPES:
  ┌──────────────┬──────────────────────────────────────────────┐
  │  Type        │  Use Case                                    │
  ├──────────────┼──────────────────────────────────────────────┤
  │  bridge      │  Default. Containers on same host talk to   │
  │  (default)   │  each other. Most common. ✅                 │
  ├──────────────┼──────────────────────────────────────────────┤
  │  host        │  Container shares host's network directly.  │
  │              │  No port mapping needed. Linux only.         │
  │              │  Best performance but least isolation.       │
  ├──────────────┼──────────────────────────────────────────────┤
  │  overlay     │  Multi-host networking (Docker Swarm).      │
  │              │  Containers across different machines.       │
  ├──────────────┼──────────────────────────────────────────────┤
  │  none        │  No networking at all. Fully isolated.      │
  │              │  Security-critical containers.               │
  └──────────────┴──────────────────────────────────────────────┘
```

---

## 🔴 PHASE 3: PRODUCTION — Security, CI/CD, Optimization (Weeks 8–11)

### Week 8: Container Registries & Image Management

| # | Topic | Priority | Est. Hours | Status |
|---|-------|----------|-----------|--------|
| 32 | **DockerHub** — push, pull, public/private repos | 🔴 Critical | 2h | ⬜ |
| 33 | **Image Tagging Best Practices** — semantic versioning, `latest` dangers | 🔴 Critical | 1h | ⬜ |
| 34 | **Other Registries** — GitHub Container Registry, AWS ECR, Google GCR, Azure ACR | 🟡 Important | 2h | ⬜ |
| 35 | **Private Registry** — self-hosted registry | 🟢 Good to know | 1h | ⬜ |

```bash
# 📦 CONTAINER REGISTRIES — Push & Pull Images

# ─── DockerHub ───────────────────────────────
docker login                                       # Login to DockerHub
docker tag myapp:latest username/myapp:1.0.0      # Tag with your username
docker push username/myapp:1.0.0                   # Push to DockerHub
docker pull username/myapp:1.0.0                   # Pull from DockerHub

# ─── GitHub Container Registry (ghcr.io) ─────
docker login ghcr.io -u USERNAME -p GITHUB_TOKEN
docker tag myapp ghcr.io/username/myapp:1.0.0
docker push ghcr.io/username/myapp:1.0.0

# ─── AWS ECR ─────────────────────────────────
aws ecr get-login-password | docker login --username AWS --password-stdin 123456.dkr.ecr.ap-south-1.amazonaws.com
docker tag myapp 123456.dkr.ecr.ap-south-1.amazonaws.com/myapp:1.0.0
docker push 123456.dkr.ecr.ap-south-1.amazonaws.com/myapp:1.0.0
```

```
🏷️ IMAGE TAGGING BEST PRACTICES

  ❌ BAD:
  docker build -t myapp .            # Tagged as :latest by default
  docker build -t myapp:latest .     # Same thing
  
  Problem: "latest" doesn't mean "latest"!
  It's just a default tag. Not auto-updated.
  "Which version is running in production?" → Nobody knows 😰


  ✅ GOOD: Use semantic versioning + Git SHA
  docker build -t myapp:1.2.3 .           # Semantic version
  docker build -t myapp:1.2.3-abc123f .   # Version + Git commit
  docker build -t myapp:1.2 .             # Major.Minor (floating)
  docker build -t myapp:latest .          # Also tag as latest


  TAGGING STRATEGY:
  ┌─────────────────────────────┬──────────────────────────────┐
  │  Tag                        │  Purpose                     │
  ├─────────────────────────────┼──────────────────────────────┤
  │  myapp:1.2.3                │  Exact version (immutable)   │
  │  myapp:1.2                  │  Latest patch of 1.2         │
  │  myapp:1                    │  Latest minor of v1          │
  │  myapp:latest               │  Most recent build           │
  │  myapp:abc123f              │  Git commit SHA              │
  │  myapp:staging              │  Staging environment         │
  │  myapp:2024-01-15           │  Date-based                  │
  └─────────────────────────────┴──────────────────────────────┘

  💡 In production: ALWAYS use exact version tags.
     Never deploy :latest to production!
```

---

### Week 9: Container Security

| # | Topic | Priority | Est. Hours | Status |
|---|-------|----------|-----------|--------|
| 36 | **Image Security** — scan for vulnerabilities, minimal base images | 🔴 Critical | 3h | ⬜ |
| 37 | **Runtime Security** — non-root user, read-only FS, capabilities | 🔴 Critical | 3h | ⬜ |
| 38 | **Secret Management** — environment variables, Docker secrets | 🔴 Critical | 2h | ⬜ |
| 39 | **Security Scanning** — Trivy, Docker Scout, Snyk | 🟡 Important | 2h | ⬜ |

```
🛡️ CONTAINER SECURITY — Complete Checklist

  ┌────────────────────────────────────────────────────────────────┐
  │                   IMAGE SECURITY                               │
  ├────────────────────────────────────────────────────────────────┤
  │                                                                │
  │  ✅ Use OFFICIAL base images (python:3.11-slim, NOT random)   │
  │  ✅ Use SPECIFIC tags (python:3.11.7-slim, NOT :latest)       │
  │  ✅ Use MINIMAL base images (slim/alpine/distroless)          │
  │  ✅ Scan images for vulnerabilities                            │
  │  ✅ Multi-stage builds (no build tools in production)         │
  │  ✅ Don't store secrets in images (no API keys in Dockerfile!)│
  │  ✅ Update base images regularly                               │
  │  ✅ Pin dependency versions                                    │
  │                                                                │
  ├────────────────────────────────────────────────────────────────┤
  │                   RUNTIME SECURITY                             │
  ├────────────────────────────────────────────────────────────────┤
  │                                                                │
  │  ✅ Run as NON-ROOT user                                       │
  │  ✅ Read-only filesystem where possible                        │
  │  ✅ Drop unnecessary Linux capabilities                        │
  │  ✅ Limit resources (CPU, Memory)                              │
  │  ✅ Don't run with --privileged                                │
  │  ✅ Use health checks                                          │
  │  ✅ Log everything, monitor anomalies                          │
  │                                                                │
  ├────────────────────────────────────────────────────────────────┤
  │                   SECRET MANAGEMENT                            │
  ├────────────────────────────────────────────────────────────────┤
  │                                                                │
  │  ❌ NEVER: ENV API_KEY=sk-1234 in Dockerfile                   │
  │  ❌ NEVER: COPY .env into image                                │
  │  ✅ Use docker secrets (Swarm/Kubernetes)                      │
  │  ✅ Use .env files (NOT committed to git)                      │
  │  ✅ Use secret managers (AWS SSM, HashiCorp Vault)             │
  │  ✅ Pass at runtime: docker run -e API_KEY=$API_KEY            │
  │                                                                │
  └────────────────────────────────────────────────────────────────┘
```

```dockerfile
# 🔒 SECURE Dockerfile — Production Template

FROM python:3.11-slim AS builder

WORKDIR /app
COPY requirements.txt .
RUN pip install --user --no-cache-dir -r requirements.txt


FROM python:3.11-slim AS production

# 1. Install only runtime deps
RUN apt-get update && \
    apt-get install -y --no-install-recommends curl && \
    rm -rf /var/lib/apt/lists/*

# 2. Create non-root user
RUN groupadd -r appgroup && \
    useradd -r -g appgroup -d /app -s /sbin/nologin appuser

WORKDIR /app

# 3. Copy dependencies from builder
COPY --from=builder /root/.local /home/appuser/.local
COPY --chown=appuser:appgroup . .

# 4. Set proper PATH
ENV PATH=/home/appuser/.local/bin:$PATH

# 5. Switch to non-root user
USER appuser

# 6. Read-only filesystem support
# Run with: docker run --read-only --tmpfs /tmp myapp

# 7. Health check
HEALTHCHECK --interval=30s --timeout=10s --retries=3 \
    CMD curl -f http://localhost:8000/health || exit 1

# 8. Document the port
EXPOSE 8000

# 9. Run the application
CMD ["uvicorn", "main:app", "--host", "0.0.0.0", "--port", "8000"]
```

```bash
# 🔍 SECURITY SCANNING

# ─── Trivy (most popular, free) ──────────────
# Install: https://aquasecurity.github.io/trivy/
trivy image myapp:1.0.0
trivy image --severity HIGH,CRITICAL myapp:1.0.0

# ─── Docker Scout (built into Docker) ────────
docker scout cves myapp:1.0.0
docker scout quickview myapp:1.0.0

# ─── Example output ─────────────────────────
# myapp:1.0.0 (debian 12.4)
# 
# Total: 15 (LOW: 5, MEDIUM: 7, HIGH: 2, CRITICAL: 1)
#
# ┌──────────────┬────────────┬──────────┬───────────────────┐
# │   Library    │ Vulnerability│ Severity │ Fixed Version    │
# ├──────────────┼────────────┼──────────┼───────────────────┤
# │   openssl    │ CVE-2024-xx│ CRITICAL │ 3.0.13-1          │
# │   curl       │ CVE-2024-yy│ HIGH     │ 7.88.1-10+deb12u5│
# └──────────────┴────────────┴──────────┴───────────────────┘
```

---

### Week 10–11: Developer Experience & CI/CD

| # | Topic | Priority | Est. Hours | Status |
|---|-------|----------|-----------|--------|
| 40 | **Hot Reloading in Docker** — live code changes without rebuilding | 🔴 Critical | 2h | ⬜ |
| 41 | **Debugging in Containers** — debugger attachment, VS Code integration | 🟡 Important | 2h | ⬜ |
| 42 | **Running Tests in Docker** — consistent test environment | 🔴 Critical | 2h | ⬜ |
| 43 | **CI/CD with Docker** — GitHub Actions, build + push + deploy pipeline | 🔴 Critical | 4h | ⬜ |
| 44 | **Docker in VS Code** — Dev Containers, Docker extension | 🟡 Important | 1h | ⬜ |

```yaml
# 🔥 HOT RELOADING Setup — Dev vs Production

# docker-compose.dev.yml (Development — with hot reload)
version: '3.9'
services:
  api:
    build:
      context: ./backend
      dockerfile: Dockerfile.dev
    volumes:
      - ./backend:/app          # ← Bind mount = code changes reflect instantly!
      - /app/__pycache__        # ← Exclude cache from mount
    command: uvicorn main:app --host 0.0.0.0 --port 8000 --reload
    #                                                      ^^^^^^^^
    #                                            Hot reload enabled!
    ports:
      - "8000:8000"
    environment:
      - DEBUG=true


# docker-compose.prod.yml (Production — no bind mounts, no reload)
version: '3.9'
services:
  api:
    image: ghcr.io/username/myapp:1.2.3    # ← Use built image, not build
    ports:
      - "8000:8000"
    environment:
      - DEBUG=false
    deploy:
      replicas: 3
      resources:
        limits:
          memory: 512M
          cpus: '0.5'


# Usage:
# Development: docker compose -f docker-compose.dev.yml up
# Production:  docker compose -f docker-compose.prod.yml up -d
```

```yaml
# 🔄 CI/CD — GitHub Actions Pipeline (Complete)

# .github/workflows/docker-ci.yml
name: Docker CI/CD Pipeline

on:
  push:
    branches: [main, develop]
  pull_request:
    branches: [main]

env:
  REGISTRY: ghcr.io
  IMAGE_NAME: ${{ github.repository }}

jobs:
  # ─── Step 1: Test ──────────────────────────
  test:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      
      - name: Build test image
        run: docker compose -f docker-compose.test.yml build
      
      - name: Run tests
        run: docker compose -f docker-compose.test.yml run --rm api pytest -v
      
      - name: Run linting
        run: docker compose -f docker-compose.test.yml run --rm api ruff check .

  # ─── Step 2: Build & Push ──────────────────
  build-and-push:
    needs: test
    runs-on: ubuntu-latest
    if: github.event_name == 'push' && github.ref == 'refs/heads/main'
    
    permissions:
      contents: read
      packages: write
    
    steps:
      - uses: actions/checkout@v4
      
      - name: Log in to Container Registry
        uses: docker/login-action@v3
        with:
          registry: ${{ env.REGISTRY }}
          username: ${{ github.actor }}
          password: ${{ secrets.GITHUB_TOKEN }}
      
      - name: Extract metadata (tags)
        id: meta
        uses: docker/metadata-action@v5
        with:
          images: ${{ env.REGISTRY }}/${{ env.IMAGE_NAME }}
          tags: |
            type=sha,prefix=
            type=semver,pattern={{version}}
            type=raw,value=latest
      
      - name: Build and push Docker image
        uses: docker/build-push-action@v5
        with:
          context: ./backend
          push: true
          tags: ${{ steps.meta.outputs.tags }}
          cache-from: type=gha
          cache-to: type=gha,mode=max
      
      - name: Scan image for vulnerabilities
        uses: aquasecurity/trivy-action@master
        with:
          image-ref: ${{ env.REGISTRY }}/${{ env.IMAGE_NAME }}:latest
          severity: 'CRITICAL,HIGH'
          exit-code: '1'

  # ─── Step 3: Deploy ────────────────────────
  deploy:
    needs: build-and-push
    runs-on: ubuntu-latest
    
    steps:
      - name: Deploy to production
        run: |
          # SSH into server and pull new image
          # Or trigger Kubernetes/Railway/Render deployment
          echo "Deploying version ${{ github.sha }}"


# FLOW:
# Push to main → Tests pass → Build image → Scan security
# → Push to registry → Deploy to production 🚀
```

---

## 🏆 PHASE 4: DEPLOYMENT & ORCHESTRATION (Weeks 12–14)

### Week 12–14: Deploying Containers

| # | Topic | Priority | Est. Hours | Status |
|---|-------|----------|-----------|--------|
| 45 | **PaaS Options** — Railway, Render, Fly.io, DigitalOcean App Platform | 🔴 Critical | 3h | ⬜ |
| 46 | **Docker Swarm** — built-in orchestration (simpler alternative to K8s) | 🟡 Important | 3h | ⬜ |
| 47 | **Kubernetes Basics** — pods, services, deployments, namespaces | 🔴 Critical | 6h | ⬜ |
| 48 | **Kubernetes with Docker** — building images for K8s deployment | 🟡 Important | 3h | ⬜ |
| 49 | **HashiCorp Nomad** — alternative orchestrator | 🟢 Good to know | 2h | ⬜ |
| 50 | **Production Best Practices** — logging, monitoring, health checks | 🔴 Critical | 3h | ⬜ |

```
🚀 DEPLOYMENT OPTIONS — Where to Run Your Containers

┌────────────────────┬───────────┬────────────┬──────────┬──────────────┐
│  Platform          │ Complexity│ Cost       │ Scale    │ Best For     │
├────────────────────┼───────────┼────────────┼──────────┼──────────────┤
│ Railway ☁️         │ ⭐        │ Free tier  │ Auto     │ Side projects│
│ Render             │ ⭐        │ Free tier  │ Auto     │ Startups     │
│ Fly.io             │ ⭐⭐      │ Free tier  │ Global   │ Edge deploy  │
│ DigitalOcean App   │ ⭐⭐      │ $5/mo+     │ Auto     │ Small teams  │
│ AWS ECS/Fargate    │ ⭐⭐⭐    │ Pay-per-use│ Auto     │ AWS ecosystem│
│ Docker Swarm       │ ⭐⭐⭐    │ Self-hosted│ Manual   │ Simple orch. │
│ Kubernetes (K8s)   │ ⭐⭐⭐⭐⭐│ Varies     │ Best ✅  │ Enterprise   │
│ AWS EKS / GKE      │ ⭐⭐⭐⭐  │ $70/mo+    │ Best ✅  │ Cloud-native │
└────────────────────┴───────────┴────────────┴──────────┴──────────────┘

💡 Recommendation for students:
   Personal projects → Railway / Render (free, zero config)
   Learning infra    → Docker Swarm (simpler to learn)
   Career investment → Kubernetes (most in-demand skill)
```

```
☸️ KUBERNETES — The 30-Second Overview

  Problem: You have 100 containers to manage. Docker Compose 
  manages them on ONE machine. What about 50 machines?
  What if a container crashes? What about scaling? Rolling updates?

  Solution: Kubernetes — the CONTAINER ORCHESTRATOR.

  ┌─────────────────────────────────────────────────────────────┐
  │                     KUBERNETES CLUSTER                       │
  │                                                             │
  │  ┌─────────────────────────────────────────┐               │
  │  │           CONTROL PLANE (Master)        │               │
  │  │  API Server, Scheduler, Controller Mgr  │               │
  │  └────────────────┬────────────────────────┘               │
  │                   │                                         │
  │         ┌─────────┼─────────┐                               │
  │         ▼         ▼         ▼                               │
  │  ┌──────────┐ ┌──────────┐ ┌──────────┐                   │
  │  │  Node 1  │ │  Node 2  │ │  Node 3  │  (Worker Machines)│
  │  │          │ │          │ │          │                    │
  │  │ ┌──────┐ │ │ ┌──────┐ │ │ ┌──────┐ │                   │
  │  │ │Pod   │ │ │ │Pod   │ │ │ │Pod   │ │  Pod = smallest  │
  │  │ │┌────┐│ │ │ │┌────┐│ │ │ │┌────┐│ │  deployable unit │
  │  │ ││ 🐳 ││ │ │ ││ 🐳 ││ │ │ ││ 🐳 ││ │  (1+ containers) │
  │  │ │└────┘│ │ │ │└────┘│ │ │ │└────┘│ │                   │
  │  │ └──────┘ │ │ └──────┘ │ │ └──────┘ │                   │
  │  │ ┌──────┐ │ │ ┌──────┐ │ │          │                   │
  │  │ │Pod   │ │ │ │Pod   │ │ │          │                   │
  │  │ │┌────┐│ │ │ │┌────┐│ │ │          │                   │
  │  │ ││ 🐳 ││ │ │ ││ 🐳 ││ │ │          │                   │
  │  │ │└────┘│ │ │ │└────┘│ │ │          │                   │
  │  │ └──────┘ │ │ └──────┘ │ │          │                   │
  │  └──────────┘ └──────────┘ └──────────┘                   │
  │                                                             │
  │  K8s handles:                                               │
  │  ✅ Auto-scaling (CPU > 80%? → spin up more pods)          │
  │  ✅ Self-healing (pod crashes? → restart automatically)    │
  │  ✅ Rolling updates (zero-downtime deployments)            │
  │  ✅ Load balancing (distribute traffic across pods)        │
  │  ✅ Service discovery (pods find each other by name)       │
  │  ✅ Secret management (inject secrets into pods)           │
  └─────────────────────────────────────────────────────────────┘
```

---

## 📊 COMPLETE TIMELINE OVERVIEW

```
WEEK  1     ████ Containers vs VMs, Docker concepts, underlying tech
WEEK  2     ████ Linux fundamentals — shell, permissions, networking
WEEK  3     ████ Docker CLI — images, containers, volumes, networks
             ──── 🎯 MILESTONE: Run any app in Docker ────

WEEK  4     ████ Data Persistence — volumes, bind mounts, tmpfs
WEEK  5     ████ Dockerfiles — build images, layer caching, multi-stage
WEEK  6     ████ Docker Compose — multi-service apps, networking
WEEK  7     ████ Full-stack project — API + DB + Cache + Proxy
             ──── 🎯 MILESTONE: Dockerize any full-stack project ────

WEEK  8     ████ Container Registries — DockerHub, GHCR, ECR, tagging
WEEK  9     ████ Container Security — scanning, non-root, secrets
WEEK 10     ████ Developer Experience — hot reload, debugging, testing
WEEK 11     ████ CI/CD — GitHub Actions pipeline, auto-deploy
             ──── 🎯 MILESTONE: Production-ready Docker workflow ────

WEEK 12     ████ PaaS Deployment — Railway, Render, Fly.io
WEEK 13     ████ Kubernetes Basics — pods, services, deployments
WEEK 14     ████ Production Best Practices — logging, monitoring
             ──── 🏆 MILESTONE: Deploy containerized apps to cloud ────
```

---

## 🏋️ PROJECTS TO BUILD (Phase-wise)

| Phase | Project | Skills Covered | Resume Value |
|-------|---------|---------------|-------------|
| 🟢 Week 3 | **Dockerize a Python CLI app** | Dockerfile basics, images | ⭐⭐ |
| 🟢 Week 5 | **Multi-stage build for FastAPI** | Optimized images, caching | ⭐⭐⭐ |
| 🟡 Week 7 | **Full-stack with Compose** — API + Postgres + Redis + Nginx | Compose, networking, volumes | ⭐⭐⭐⭐ |
| 🔴 Week 11 | **CI/CD Pipeline** — auto-build, test, scan, push, deploy | GitHub Actions, security | ⭐⭐⭐⭐ |
| 🏆 Week 14 | **K8s Deployment** — deploy app to Kubernetes cluster | Orchestration, scaling | ⭐⭐⭐⭐⭐ |

---

## 📚 BEST RESOURCES (Curated)

| Category | Resource | Type | Best For |
|----------|----------|------|----------|
| 🎥 YouTube | **TechWorld with Nana** — Docker Crash Course | Video | Best beginner tutorial |
| 🎥 YouTube | **Fireship** — Docker in 100 Seconds + Learn Docker in 7 Steps | Video | Quick overview |
| 🎥 YouTube | **NetworkChuck** — Docker Tutorial | Video | Fun, engaging |
| 🎥 YouTube | **Sid Palas** — DevOps Directive Docker Course | Video | Deep dive (FREE) |
| 📖 Docs | **docs.docker.com** | Official | Complete reference |
| 🌐 Website | **roadmap.sh/docker** | Roadmap | Visual learning path |
| 🌐 Interactive | **Play with Docker** (labs.play-with-docker.com) | Sandbox | Practice without installing |
| 📖 Book | **Docker Deep Dive** (Nigel Poulton) | Book | Most recommended Docker book |
| 🎥 YouTube | **Kunal Kushwaha** — Docker + Kubernetes (Hindi) | Video | Indian context |
| 🌐 Practice | **Docker Labs** (github.com/docker/labs) | Hands-on | Official practice exercises |

---

## 💼 Interview Angle — Docker Questions Companies Ask

```
┌────────────────────────────────────────────────────────────────────┐
│              TOP DOCKER INTERVIEW QUESTIONS                       │
├────────────────────────────────────────────────────────────────────┤
│                                                                    │
│  BEGINNER:                                                         │
│  1. What is Docker? How is it different from a VM?                 │
│  2. What is a Dockerfile? Explain its key instructions.            │
│  3. Difference between CMD and ENTRYPOINT?                         │
│  4. What are Docker volumes? Why are they needed?                  │
│  5. Explain the Docker image layer system.                         │
│                                                                    │
│  INTERMEDIATE:                                                     │
│  6. How do you optimize Docker image size?                         │
│  7. Explain multi-stage builds with an example.                    │
│  8. How do containers communicate with each other?                 │
│  9. What is Docker Compose? When would you use it?                 │
│  10. How do you handle secrets in Docker?                          │
│                                                                    │
│  ADVANCED:                                                         │
│  11. Explain namespaces and cgroups.                               │
│  12. How does Docker layer caching work? How to optimize it?       │
│  13. Docker Swarm vs Kubernetes — differences?                     │
│  14. How would you set up CI/CD with Docker?                       │
│  15. Container security best practices?                            │
│                                                                    │
│  Companies that test Docker knowledge:                             │
│  Almost ALL product companies, DevOps roles, Backend roles         │
│  Amazon, Google, Flipkart, Swiggy, Atlassian, Razorpay            │
└────────────────────────────────────────────────────────────────────┘
```

---

## 🧠 DOCKER MENTAL MODEL — Remember This!

```
┌─────────────────────────────────────────────────────────────────┐
│                                                                 │
│   WRITE CODE                                                    │
│       │                                                         │
│       ▼                                                         │
│   WRITE DOCKERFILE        "How to package my app"               │
│       │                                                         │
│       ▼                                                         │
│   docker build            "Create the package (image)"          │
│       │                                                         │
│       ▼                                                         │
│   docker push             "Upload to registry (DockerHub)"      │
│       │                                                         │
│       ▼                                                         │
│   docker pull             "Download on any machine"             │
│       │                                                         │
│       ▼                                                         │
│   docker run              "Run the app (container)"             │
│       │                                                         │
│       ▼                                                         │
│   docker compose          "Run multi-service apps"              │
│       │                                                         │
│       ▼                                                         │
│   Kubernetes              "Run at scale across servers"         │
│                                                                 │
│   That's it. That's Docker. 🐳                                  │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
```

---


