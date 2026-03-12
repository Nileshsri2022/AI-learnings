

# 🧭 ROADMAP: Kubernetes — Complete Learning Path

---

> ⚠️ **Profile Note:** You still haven't filled in your `[brackets]`. I'll deliver this roadmap generically. Once you fill your profile, I'll personalize pace, depth, and priority (placement-focused? DevOps career? project portfolio?).

---

## 📍 Where Kubernetes Sits in the Big Picture

```
Write Code → Containerize (Docker) → Orchestrate (✨ Kubernetes ✨) → Deploy at Scale
                                           ↑ YOU ARE HERE
```

> 🧒 **ELI5:** You know how Swiggy manages 1000s of delivery drivers — assigning orders, replacing sick drivers, balancing load across areas? **Kubernetes does exactly that, but for your application containers.** It decides which server runs what, restarts crashed apps, and scales up during peak traffic — all automatically.

---

## 🗺️ FULL ROADMAP — 8 Phases

```
┌─────────────────────────────────────────────────────────────────┐
│                   KUBERNETES ROADMAP                            │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│  PHASE 0 ➜ Prerequisites (2-3 weeks)                           │
│     ↓                                                           │
│  PHASE 1 ➜ Introduction & Concepts (1 week)                    │
│     ↓                                                           │
│  PHASE 2 ➜ Setting Up & First Deploy (1 week)                  │
│     ↓                                                           │
│  PHASE 3 ➜ Running Applications — Core Workloads (2-3 weeks)   │
│     ↓                                                           │
│  PHASE 4 ➜ Networking, Config & Security (2-3 weeks)           │
│     ↓                                                           │
│  PHASE 5 ➜ Observability, Scaling & Storage (2-3 weeks)        │
│     ↓                                                           │
│  PHASE 6 ➜ Deployment Patterns & CI/CD (2 weeks)               │
│     ↓                                                           │
│  PHASE 7 ➜ Advanced Topics & Cluster Ops (2-3 weeks)           │
│                                                                 │
│  ⏱️ Total: ~14-20 weeks (3.5-5 months at 2 hrs/day)            │
└─────────────────────────────────────────────────────────────────┘
```

---

## PHASE 0: Prerequisites 🟢
**⏱️ 2-3 weeks | Priority: 🔴 CRITICAL — Do NOT skip**

Kubernetes without these foundations = guaranteed confusion.

| # | Topic | What to Learn | Priority | Est. Hours |
|---|-------|---------------|----------|------------|
| 1 | **Linux Basics** | File system, processes, permissions, systemd, SSH, package managers | 🔴 Critical | 10-15 hrs |
| 2 | **Networking Fundamentals** | IP addresses, ports, DNS, HTTP, TCP/UDP, load balancers, firewalls | 🔴 Critical | 8-10 hrs |
| 3 | **Docker / Containers** | Images, containers, Dockerfile, docker-compose, volumes, networking | 🔴 Critical | 15-20 hrs |
| 4 | **YAML** | Syntax, nesting, lists, multi-line strings — K8s lives in YAML | 🔴 Critical | 2-3 hrs |
| 5 | **Basic Backend Dev** | How a web app runs, REST APIs, environment variables, ports | 🟡 Important | 5-8 hrs |
| 6 | **Git & Terminal** | CLI proficiency, Git basics | 🟡 Important | 3-4 hrs |

### ✅ Checkpoint — You're ready when you can:

```bash
# Write a Dockerfile
FROM node:18-alpine
WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .
EXPOSE 3000
CMD ["node", "server.js"]

# Build & run it
docker build -t my-app:v1 .
docker run -d -p 3000:3000 --name my-app my-app:v1

# Check logs, exec into container
docker logs my-app
docker exec -it my-app sh

# Write docker-compose.yml comfortably
# Understand bridge networking, volumes, env vars
```

AND you're comfortable with:
```bash
# Linux / Terminal
ssh user@server
ls -la /etc/nginx/
curl http://localhost:3000/api/health
ps aux | grep node
cat /etc/resolv.conf
ping google.com
netstat -tlnp    # or ss -tlnp
```

### 📚 Resources — Phase 0
| Resource | Type | Cost |
|----------|------|------|
| Docker Roadmap — roadmap.sh | 🗺️ Roadmap | Free |
| TechWorld with Nana — Docker Tutorial | 🎥 YouTube | Free |
| KodeKloud — Linux Basics | 🎥 YouTube | Free |
| NetworkChuck — Networking | 🎥 YouTube | Free |
| "Learn YAML in 18 mins" — TechWorld with Nana | 🎥 YouTube | Free |

---

## PHASE 1: Introduction & Core Concepts 🧠
**⏱️ 1 week | Priority: 🔴 CRITICAL**

### 📗 1A: What is Kubernetes & Why?

> 🧒 **ELI5 — The Dabbawala Analogy:**
> Mumbai's dabbawalas deliver 200,000 lunch boxes daily. They don't need a boss micro-managing each delivery. The **system** handles routing, replacement (if a dabbawala is sick), and load distribution. **Kubernetes is that system for your containers.** You just describe "I need 5 copies of my app running" and K8s handles the rest — where to run them, restarting crashed ones, distributing traffic.

#### Why not just Docker?

| Problem | Docker Alone | With Kubernetes |
|---------|-------------|-----------------|
| Container crashes at 3 AM | 💀 App is down until you fix it | ✅ Auto-restarts in seconds |
| Traffic spike (10x users) | 😰 Manually start more containers | ✅ Auto-scales to handle load |
| Deploy new version | 🛑 Downtime during update | ✅ Zero-downtime rolling updates |
| Run across 50 servers | 🤯 Manually manage each server | ✅ K8s distributes automatically |
| Server hardware fails | 💀 All containers on that server die | ✅ Reschedules to healthy servers |
| Load balancing | 🔧 Set up nginx/HAProxy manually | ✅ Built-in service discovery & LB |

### 📘 1B: Key Concepts & Terminology

```
┌──────────────────────────────────────────────────────────────────┐
│                  KUBERNETES ARCHITECTURE                         │
│                                                                  │
│  ┌────────────────── CONTROL PLANE ──────────────────┐           │
│  │                                                    │           │
│  │  ┌──────────┐  ┌───────────┐  ┌────────────────┐ │           │
│  │  │ API      │  │ Scheduler │  │ Controller     │ │           │
│  │  │ Server   │  │           │  │ Manager        │ │           │
│  │  └────┬─────┘  └───────────┘  └────────────────┘ │           │
│  │       │                                           │           │
│  │  ┌────┴─────┐                                     │           │
│  │  │  etcd    │  (key-value store — the "brain")    │           │
│  │  └──────────┘                                     │           │
│  └───────────────────────┬───────────────────────────┘           │
│                          │                                       │
│  ┌───── WORKER NODE 1 ───┼───── WORKER NODE 2 ─────┐            │
│  │                       │                          │            │
│  │  ┌─────────┐    ┌─────┴───┐    ┌─────────┐      │            │
│  │  │ kubelet │    │  kube-  │    │ kubelet │      │            │
│  │  │         │    │  proxy  │    │         │      │            │
│  │  └────┬────┘    └─────────┘    └────┬────┘      │            │
│  │       │                             │            │            │
│  │  ┌────┴────┐                   ┌────┴────┐      │            │
│  │  │  Pod    │                   │  Pod    │      │            │
│  │  │ ┌─────┐│                   │ ┌─────┐│      │            │
│  │  │ │Cont.││                   │ │Cont.││      │            │
│  │  │ └─────┘│                   │ └─────┘│      │            │
│  │  └─────────┘                   └─────────┘      │            │
│  └──────────────────────────────────────────────────┘            │
└──────────────────────────────────────────────────────────────────┘
```

#### Glossary — Learn These Like Your Name

| Term | What It Is | Real-World Analogy |
|------|-----------|-------------------|
| **Cluster** | The entire K8s system (control plane + workers) | The whole restaurant chain |
| **Node** | A physical/virtual machine in the cluster | A single restaurant kitchen |
| **Pod** | Smallest deployable unit (1+ containers) | A single dish being prepared |
| **Container** | Your actual application running | The food inside the dish |
| **Deployment** | Manages pod replicas, updates, rollbacks | The recipe + staffing plan |
| **Service** | Stable network endpoint to access pods | The restaurant's phone number (never changes even if chefs change) |
| **Namespace** | Virtual cluster within a cluster | Different departments in a company |
| **kubectl** | CLI tool to talk to K8s | The manager's walkie-talkie |
| **etcd** | Key-value store holding all cluster state | The restaurant's master record book |
| **API Server** | Front door — all requests go through it | The reception desk |
| **Scheduler** | Decides which node runs a new pod | The manager who assigns tables |
| **Controller Manager** | Ensures desired state = actual state | The supervisor checking everything's running |
| **kubelet** | Agent on each node, manages pods | The chef in each kitchen |
| **kube-proxy** | Handles networking on each node | The waiter routing orders |

### 📕 1C: Kubernetes vs Alternatives

| Tool | What It Is | When to Use | vs K8s |
|------|-----------|-------------|--------|
| **Docker Swarm** | Docker's built-in orchestrator | Small-scale, simple setups | Much simpler but far less powerful |
| **Docker Compose** | Multi-container on single host | Development/testing | Not for production at scale |
| **Nomad** (HashiCorp) | Lightweight orchestrator | Mixed workloads (containers + VMs + jobs) | Simpler, less ecosystem |
| **Amazon ECS** | AWS-specific container orchestrator | Already all-in on AWS | Vendor lock-in, but simpler |
| **Serverless** (Lambda etc.) | No servers at all | Event-driven, simple functions | Different paradigm entirely |

> **Bottom line:** Kubernetes is the **industry standard**. ~90% of companies using containers use K8s. Learn this one.

### ✅ Checkpoint — Phase 1:
- [ ] You can draw the K8s architecture from memory
- [ ] You can explain Pod, Deployment, Service, Node to a friend
- [ ] You understand WHY Kubernetes exists (not just WHAT it is)
- [ ] You know the difference between control plane and worker nodes

### 📚 Resources — Phase 1
| Resource | Type |
|----------|------|
| TechWorld with Nana — "Kubernetes Crash Course" | 🎥 YouTube (Best starting point) |
| KodeKloud — Kubernetes for Beginners | 🎥 YouTube + Labs |
| Official K8s Docs — Concepts Overview | 📖 kubernetes.io |
| "Kubernetes in 100 Seconds" — Fireship | 🎥 YouTube (Quick overview) |

---

## PHASE 2: Setting Up & First Deployment 🚀
**⏱️ 1 week | Priority: 🔴 CRITICAL**

### 📗 2A: Installing a Local Cluster

| Tool | Best For | OS Support | Difficulty |
|------|----------|------------|------------|
| **Minikube** | Learning, single-node cluster | All | 🟢 Start here |
| **kind** (K8s in Docker) | CI/CD testing, lightweight | All | 🟢 Easy |
| **k3s** | Lightweight K8s, edge/IoT | Linux | 🟡 Medium |
| **Docker Desktop** | Has built-in K8s | Mac/Windows | 🟢 Easiest |
| **kubeadm** | Production-like multi-node | Linux | 🔴 Advanced |

```bash
# ── OPTION 1: Minikube (Recommended for learning) ──
# Install minikube (Linux/Mac)
curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
sudo install minikube-linux-amd64 /usr/local/bin/minikube

# Start cluster
minikube start --driver=docker

# Verify
minikube status
kubectl cluster-info
kubectl get nodes

# ── OPTION 2: kind (Kubernetes in Docker) ──
# Install kind
go install sigs.k8s.io/kind@latest
# OR
brew install kind

# Create cluster
kind create cluster --name my-cluster

# Verify
kubectl get nodes
```

### 📘 2B: kubectl — Your Swiss Army Knife

```bash
# ═══════════════════════════════════════════════════
#          kubectl CHEAT SHEET (Save This!)
# ═══════════════════════════════════════════════════

# ── Cluster Info ──
kubectl cluster-info                  # Cluster details
kubectl get nodes                     # List all nodes
kubectl get nodes -o wide             # Detailed node info

# ── Namespaces ──
kubectl get namespaces                # List namespaces
kubectl create namespace dev          # Create namespace

# ── Pods ──
kubectl get pods                      # List pods (default namespace)
kubectl get pods -A                   # ALL namespaces
kubectl get pods -o wide              # Show node assignment
kubectl describe pod <pod-name>       # Detailed pod info
kubectl logs <pod-name>               # View pod logs
kubectl logs <pod-name> -f            # Follow/stream logs
kubectl exec -it <pod-name> -- sh     # Shell into pod
kubectl delete pod <pod-name>         # Delete pod

# ── Deployments ──
kubectl get deployments               # List deployments
kubectl describe deployment <name>    # Details
kubectl scale deployment <name> --replicas=5   # Scale
kubectl rollout status deployment <name>       # Status
kubectl rollout undo deployment <name>         # Rollback

# ── Services ──
kubectl get services                  # List services
kubectl get svc                       # Short form
kubectl expose deployment <name> --port=80 --type=LoadBalancer

# ── Apply/Delete YAML ──
kubectl apply -f <file.yaml>          # Create/update from YAML
kubectl delete -f <file.yaml>         # Delete from YAML

# ── Debugging ──
kubectl get events                    # Cluster events
kubectl top pods                      # Resource usage
kubectl top nodes                     # Node resource usage
```

### 📕 2C: Deploying Your First Application!

```yaml
# ═══════════════════════════════════════════════════
#    my-first-app.yaml — Your First K8s Deployment
# ═══════════════════════════════════════════════════

# --- DEPLOYMENT: Manages your app pods ---
apiVersion: apps/v1
kind: Deployment
metadata:
  name: hello-app
  labels:
    app: hello
spec:
  replicas: 3                    # Run 3 copies of your app!
  selector:
    matchLabels:
      app: hello
  template:
    metadata:
      labels:
        app: hello
    spec:
      containers:
      - name: hello-container
        image: nginx:alpine      # Using nginx as example
        ports:
        - containerPort: 80
        resources:
          requests:
            memory: "64Mi"
            cpu: "50m"
          limits:
            memory: "128Mi"
            cpu: "100m"

---
# --- SERVICE: Exposes your app to the network ---
apiVersion: v1
kind: Service
metadata:
  name: hello-service
spec:
  type: NodePort               # Makes it accessible outside cluster
  selector:
    app: hello                 # Connects to pods with label app=hello
  ports:
  - port: 80                  # Service port
    targetPort: 80             # Container port
    nodePort: 30080            # External port (30000-32767)
```

```bash
# Deploy it!
kubectl apply -f my-first-app.yaml

# Watch pods come alive
kubectl get pods -w

# Check everything
kubectl get all

# Access your app
minikube service hello-service    # Opens in browser (minikube)
# OR
curl http://localhost:30080       # Direct access

# Scale up to 5 replicas
kubectl scale deployment hello-app --replicas=5
kubectl get pods                  # See 5 pods running!

# Kill a pod — watch K8s auto-restart it
kubectl delete pod <any-pod-name>
kubectl get pods                  # New pod already created!

# Clean up
kubectl delete -f my-first-app.yaml
```

### 🔍 Dry Run — What Just Happened:

```
YOU: "I want 3 copies of nginx running"
                    ↓
API SERVER: Receives request, stores in etcd
                    ↓
SCHEDULER: "Node 1 has space, Node 2 has space..."
           Assigns pods to nodes
                    ↓
KUBELET (on each node): Pulls nginx image, starts containers
                    ↓
CONTROLLER MANAGER: Constantly checks "Are there 3 pods?"
                    If one dies → "Only 2! Create another!"
                    ↓
SERVICE: Routes traffic across all 3 pods
         (load balancing automatically)
```

### 📗 2D: Managed Kubernetes Providers (Cloud)

| Provider | Service Name | Free Tier? | Best For |
|----------|-------------|------------|----------|
| **Google Cloud** | GKE (Google Kubernetes Engine) | $300 free credits | Best K8s experience |
| **AWS** | EKS (Elastic Kubernetes Service) | Free tier limited | Most used in industry |
| **Azure** | AKS (Azure Kubernetes Service) | $200 free credits | Microsoft ecosystem |
| **DigitalOcean** | DOKS | $200 free credits | Simplest, cheapest |
| **Linode/Akamai** | LKE | $100 free credits | Budget-friendly |

> 💡 **For learning:** Use Minikube/kind locally. For portfolio projects, use DigitalOcean or GKE with free credits.

### ✅ Checkpoint — Phase 2:
- [ ] You have a running local K8s cluster
- [ ] You've deployed an app using a YAML file
- [ ] You can use kubectl to get, describe, logs, exec, scale
- [ ] You've killed a pod and watched K8s auto-heal it
- [ ] You can access your app from a browser

---

## PHASE 3: Running Applications — Core Workloads 📦
**⏱️ 2-3 weeks | Priority: 🔴 CRITICAL**

This is where you learn the **building blocks** of everything in Kubernetes.

### 📗 3A: Pods (The Atom of Kubernetes)

```
┌──────────────── POD ────────────────────┐
│                                         │
│  ┌───────────┐    ┌───────────┐         │
│  │ Container │    │ Container │ (Sidecar│
│  │  (main    │    │  (logs/   │  — rare │
│  │   app)    │    │  proxy)   │  for    │
│  └─────┬─────┘    └─────┬─────┘  now)   │
│        │                │               │
│    ┌───┴────────────────┴───┐           │
│    │   Shared Network       │           │
│    │   (localhost, same IP) │           │
│    ├────────────────────────┤           │
│    │   Shared Storage       │           │
│    │   (volumes)            │           │
│    └────────────────────────┘           │
│                                         │
│  IP: 10.244.1.5 (cluster-internal)     │
└─────────────────────────────────────────┘
```

| Key Fact | Detail |
|----------|--------|
| Pod = 1+ containers | Usually just 1 container per pod |
| Pods are **ephemeral** | They can die and be replaced anytime |
| Each pod gets its own IP | But IP changes when pod restarts |
| Containers in a pod share network | They talk via `localhost` |
| **Never create pods directly** | Always use Deployments (which create pods for you) |

```yaml
# pod-example.yaml (for learning only — don't use bare pods in production)
apiVersion: v1
kind: Pod
metadata:
  name: my-pod
  labels:
    app: demo
spec:
  containers:
  - name: web
    image: nginx:alpine
    ports:
    - containerPort: 80
    
  - name: log-sidecar           # Sidecar pattern
    image: busybox
    command: ['sh', '-c', 'while true; do echo "logging..."; sleep 10; done']
```

### 📘 3B: ReplicaSets

```
"I want EXACTLY 3 copies of this pod running at all times"

  ReplicaSet
  ├── Pod 1  ✅ Running
  ├── Pod 2  ✅ Running
  └── Pod 3  💀 Crashed → 🔄 Auto-creating Pod 3 (new)
```

> ⚠️ You rarely create ReplicaSets directly. **Deployments** create and manage ReplicaSets for you.

### 📕 3C: Deployments (The Workhorse — MOST IMPORTANT)

```
┌──────────────────── DEPLOYMENT ─────────────────────────┐
│                                                         │
│  Strategy: RollingUpdate                                │
│  Replicas: 3                                            │
│                                                         │
│  ┌─── ReplicaSet (v2 — current) ───┐                    │
│  │                                  │                    │
│  │  Pod 1 (v2)  Pod 2 (v2)  Pod 3 (v2)                 │
│  │                                  │                    │
│  └──────────────────────────────────┘                    │
│                                                         │
│  ┌─── ReplicaSet (v1 — previous, scaled to 0) ───┐     │
│  │  (kept for rollback)                            │     │
│  └─────────────────────────────────────────────────┘     │
└─────────────────────────────────────────────────────────┘
```

Deployments give you:
- ✅ **Declarative updates** — "I want version 2" → K8s handles the rest
- ✅ **Rolling updates** — Zero-downtime deployments
- ✅ **Rollbacks** — Instantly go back to previous version
- ✅ **Scaling** — Change replica count anytime
- ✅ **Self-healing** — Dead pods auto-replaced

```yaml
# deployment-example.yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: webapp
spec:
  replicas: 3
  strategy:
    type: RollingUpdate        # Zero-downtime updates
    rollingUpdate:
      maxSurge: 1              # Max extra pods during update
      maxUnavailable: 0        # Never go below desired count
  selector:
    matchLabels:
      app: webapp
  template:
    metadata:
      labels:
        app: webapp
        version: v2
    spec:
      containers:
      - name: webapp
        image: myapp:v2        # Update this to deploy new version
        ports:
        - containerPort: 8080
        
        # Health checks (critical for production)
        livenessProbe:         # "Is the container alive?"
          httpGet:
            path: /health
            port: 8080
          initialDelaySeconds: 10
          periodSeconds: 5
          
        readinessProbe:        # "Is it ready to serve traffic?"
          httpGet:
            path: /ready
            port: 8080
          initialDelaySeconds: 5
          periodSeconds: 3
        
        resources:
          requests:
            memory: "128Mi"
            cpu: "100m"
          limits:
            memory: "256Mi"
            cpu: "200m"
```

```bash
# Deploy
kubectl apply -f deployment-example.yaml

# Update to new version (just change image)
kubectl set image deployment/webapp webapp=myapp:v3

# Watch the rolling update
kubectl rollout status deployment/webapp

# Something went wrong? Rollback!
kubectl rollout undo deployment/webapp

# Check rollout history
kubectl rollout history deployment/webapp

# Scale
kubectl scale deployment/webapp --replicas=10
```

### 📗 3D: StatefulSets (For Databases & Stateful Apps)

| Feature | Deployment | StatefulSet |
|---------|-----------|-------------|
| Pod names | Random (webapp-abc123) | Ordered (mysql-0, mysql-1, mysql-2) |
| Storage | Shared/ephemeral | Each pod gets its own persistent volume |
| Scaling | All at once | One at a time, in order |
| Use case | Stateless apps (web servers, APIs) | Databases, message queues, Kafka |

```yaml
# statefulset-example.yaml
apiVersion: apps/v1
kind: StatefulSet
metadata:
  name: mysql
spec:
  serviceName: "mysql"          # Required for StatefulSets
  replicas: 3
  selector:
    matchLabels:
      app: mysql
  template:
    metadata:
      labels:
        app: mysql
    spec:
      containers:
      - name: mysql
        image: mysql:8.0
        ports:
        - containerPort: 3306
        env:
        - name: MYSQL_ROOT_PASSWORD
          valueFrom:
            secretKeyRef:
              name: mysql-secret
              key: password
        volumeMounts:
        - name: mysql-data
          mountPath: /var/lib/mysql
  volumeClaimTemplates:          # Each pod gets its own volume
  - metadata:
      name: mysql-data
    spec:
      accessModes: ["ReadWriteOnce"]
      resources:
        requests:
          storage: 10Gi
```

### 📘 3E: Jobs & CronJobs

| Type | What It Does | Example |
|------|-------------|---------|
| **Job** | Runs a task to completion, then stops | Database migration, batch processing |
| **CronJob** | Runs a Job on a schedule | Nightly backups, hourly reports |

```yaml
# job-example.yaml
apiVersion: batch/v1
kind: Job
metadata:
  name: db-migration
spec:
  backoffLimit: 3                 # Retry up to 3 times
  template:
    spec:
      containers:
      - name: migration
        image: myapp:migrate
        command: ["python", "manage.py", "migrate"]
      restartPolicy: Never        # Don't restart on completion

---
# cronjob-example.yaml
apiVersion: batch/v1
kind: CronJob
metadata:
  name: nightly-backup
spec:
  schedule: "0 2 * * *"          # 2 AM every day
  jobTemplate:
    spec:
      template:
        spec:
          containers:
          - name: backup
            image: backup-tool:latest
            command: ["./backup.sh"]
          restartPolicy: OnFailure
```

### 📊 Summary Table — When to Use What

| Workload Type | Use Case | Examples |
|--------------|----------|---------|
| **Deployment** | Stateless apps, web servers, APIs | Nginx, Node.js apps, REST APIs |
| **StatefulSet** | Stateful apps needing stable identity | MySQL, PostgreSQL, MongoDB, Kafka |
| **Job** | One-time tasks | DB migration, data import, ML training |
| **CronJob** | Scheduled recurring tasks | Backups, cleanup, report generation |
| **DaemonSet** | Run one pod per node | Log collectors, monitoring agents |

### ✅ Checkpoint — Phase 3:
- [ ] You can create Deployments with health checks
- [ ] You've done a rolling update and a rollback
- [ ] You understand Deployment vs StatefulSet vs Job
- [ ] You can scale deployments up and down
- [ ] You've written all YAML from memory (not just copying)

---

## PHASE 4: Networking, Configuration & Security 🔒
**⏱️ 2-3 weeks | Priority: 🔴 CRITICAL**

### 📗 4A: Services & Networking

```
┌────────────────── SERVICES ──────────────────────────────┐
│                                                          │
│  ┌──────────────┐   Pods are ephemeral (IPs change).     │
│  │   SERVICE     │   Services give you a STABLE endpoint. │
│  │  (stable IP)  │                                       │
│  └──────┬───────┘                                        │
│         │ routes to                                      │
│    ┌────┼────┐                                           │
│    ↓    ↓    ↓                                           │
│  Pod1  Pod2  Pod3  (IPs keep changing — doesn't matter)  │
│                                                          │
└──────────────────────────────────────────────────────────┘
```

#### Service Types:

| Type | Access From | Use Case | How It Works |
|------|------------|----------|--------------|
| **ClusterIP** | Inside cluster only | Internal services (DB, cache) | Default. Gets internal IP |
| **NodePort** | Outside via `<NodeIP>:<Port>` | Development, testing | Exposes on port 30000-32767 |
| **LoadBalancer** | Internet via cloud LB | Production web apps | Cloud provider creates real LB |
| **ExternalName** | DNS alias | Linking to external services | CNAME record |

```yaml
# ── ClusterIP (internal only) ──
apiVersion: v1
kind: Service
metadata:
  name: backend-api
spec:
  type: ClusterIP              # Default
  selector:
    app: backend
  ports:
  - port: 80                   # Other pods call backend-api:80
    targetPort: 3000           # Container listens on 3000

---
# ── LoadBalancer (external access) ──
apiVersion: v1
kind: Service
metadata:
  name: frontend
spec:
  type: LoadBalancer
  selector:
    app: frontend
  ports:
  - port: 80
    targetPort: 3000
```

#### Ingress — The Smart Router:

```
                    Internet
                       │
                  ┌────┴─────┐
                  │ INGRESS  │ (like nginx reverse proxy)
                  │CONTROLLER│
                  └────┬─────┘
                       │
          ┌────────────┼────────────┐
          ↓            ↓            ↓
   /api/*         /app/*        /docs/*
   ┌──────┐      ┌──────┐      ┌──────┐
   │API   │      │WebApp│      │Docs  │
   │Svc   │      │Svc   │      │Svc   │
   └──────┘      └──────┘      └──────┘
```

```yaml
# ingress-example.yaml
apiVersion: networking.k8s.io/v1
kind: Ingress
metadata:
  name: my-ingress
  annotations:
    nginx.ingress.kubernetes.io/rewrite-target: /
spec:
  rules:
  - host: myapp.example.com
    http:
      paths:
      - path: /api
        pathType: Prefix
        backend:
          service:
            name: backend-api
            port:
              number: 80
      - path: /
        pathType: Prefix
        backend:
          service:
            name: frontend
            port:
              number: 80
```

#### Pod-to-Pod Communication:

```
┌────────────────────────────────────────────────────────┐
│                 K8s NETWORKING RULES                   │
│                                                        │
│  1. Every pod gets its own IP address                  │
│  2. Pods can talk to ANY other pod directly (no NAT)   │
│  3. Nodes can talk to any pod directly                 │
│  4. Use SERVICE NAMES not IPs:                         │
│                                                        │
│     curl http://backend-api:80/users     ← Same NS    │
│     curl http://backend-api.prod.svc:80  ← Cross NS   │
│                                                        │
│  DNS: <service>.<namespace>.svc.cluster.local          │
└────────────────────────────────────────────────────────┘
```

### 📘 4B: Configuration Management

#### ConfigMaps — Non-Sensitive Configuration:

```yaml
# configmap.yaml
apiVersion: v1
kind: ConfigMap
metadata:
  name: app-config
data:
  DATABASE_HOST: "mysql-service"
  DATABASE_PORT: "3306"
  LOG_LEVEL: "info"
  APP_MODE: "production"
  
  # You can even store entire config files!
  nginx.conf: |
    server {
      listen 80;
      location / {
        proxy_pass http://backend:3000;
      }
    }

---
# Using ConfigMap in a Deployment
apiVersion: apps/v1
kind: Deployment
metadata:
  name: myapp
spec:
  replicas: 2
  selector:
    matchLabels:
      app: myapp
  template:
    metadata:
      labels:
        app: myapp
    spec:
      containers:
      - name: myapp
        image: myapp:v1
        
        # Method 1: Individual env vars
        env:
        - name: DB_HOST
          valueFrom:
            configMapKeyRef:
              name: app-config
              key: DATABASE_HOST
        
        # Method 2: All keys as env vars
        envFrom:
        - configMapRef:
            name: app-config
        
        # Method 3: Mount as file
        volumeMounts:
        - name: config-volume
          mountPath: /etc/nginx/nginx.conf
          subPath: nginx.conf
      
      volumes:
      - name: config-volume
        configMap:
          name: app-config
```

#### Secrets — Sensitive Data:

```bash
# Create secret from command line
kubectl create secret generic db-credentials \
  --from-literal=username=admin \
  --from-literal=password=SuperSecret123
```

```yaml
# secret.yaml (values are base64 encoded — NOT encrypted!)
apiVersion: v1
kind: Secret
metadata:
  name: db-credentials
type: Opaque
data:
  username: YWRtaW4=            # echo -n "admin" | base64
  password: U3VwZXJTZWNyZXQxMjM=  # echo -n "SuperSecret123" | base64

---
# Using in pod
spec:
  containers:
  - name: myapp
    env:
    - name: DB_USERNAME
      valueFrom:
        secretKeyRef:
          name: db-credentials
          key: username
    - name: DB_PASSWORD
      valueFrom:
        secretKeyRef:
          name: db-credentials
          key: password
```

> ⚠️ **Important:** K8s Secrets are base64-encoded, NOT encrypted. For real security, use tools like **Sealed Secrets**, **HashiCorp Vault**, or **SOPS**.

### 📕 4C: Security

#### RBAC (Role-Based Access Control):

```
┌─────────────────────────────────────────────────────────┐
│                    RBAC Model                           │
│                                                         │
│  WHO          WHAT          WHERE                       │
│  ────         ────          ─────                       │
│  User/        Role/         Namespace/                  │
│  ServiceAcc   ClusterRole   Cluster                     │
│       │            │            │                        │
│       └──── RoleBinding ───────┘                        │
│             (ties them together)                        │
│                                                         │
│  Example: "developer" user can "get, list"              │
│           pods in "dev" namespace                       │
└─────────────────────────────────────────────────────────┘
```

```yaml
# Role — defines WHAT actions are allowed
apiVersion: rbac.authorization.k8s.io/v1
kind: Role
metadata:
  namespace: dev
  name: pod-reader
rules:
- apiGroups: [""]
  resources: ["pods"]
  verbs: ["get", "list", "watch"]     # Read-only

---
# RoleBinding — assigns role to WHO
apiVersion: rbac.authorization.k8s.io/v1
kind: RoleBinding
metadata:
  name: read-pods
  namespace: dev
subjects:
- kind: User
  name: developer1
roleRef:
  kind: Role
  name: pod-reader
  apiGroup: rbac.authorization.k8s.io
```

#### Network Policies (Firewall for Pods):

```yaml
# Only allow backend pods to talk to database pods
apiVersion: networking.k8s.io/v1
kind: NetworkPolicy
metadata:
  name: db-access
  namespace: production
spec:
  podSelector:
    matchLabels:
      app: database
  policyTypes:
  - Ingress
  ingress:
  - from:
    - podSelector:
        matchLabels:
          app: backend         # Only backend can access DB
    ports:
    - protocol: TCP
      port: 5432
```

#### Pod Security:

```yaml
# Security context — restrict container privileges
spec:
  containers:
  - name: myapp
    image: myapp:v1
    securityContext:
      runAsNonRoot: true          # Don't run as root
      runAsUser: 1000             # Specific user ID
      readOnlyRootFilesystem: true # Can't write to filesystem
      allowPrivilegeEscalation: false
      capabilities:
        drop:
        - ALL                      # Drop all Linux capabilities
```

### ✅ Checkpoint — Phase 4:
- [ ] You can create ClusterIP, NodePort, LoadBalancer services
- [ ] You understand Ingress and can configure path-based routing
- [ ] You can use ConfigMaps and Secrets in pods
- [ ] You can explain RBAC (Role, RoleBinding, ServiceAccount)
- [ ] You understand NetworkPolicies

---

## PHASE 5: Observability, Autoscaling & Storage 📊
**⏱️ 2-3 weeks | Priority: 🟡 IMPORTANT**

### 📗 5A: Monitoring & Logging

```
┌──────────────── OBSERVABILITY ──────────────────────────┐
│                                                         │
│  Three Pillars:                                         │
│                                                         │
│  📝 LOGS         📊 METRICS       🔗 TRACES             │
│  "What happened" "How is it       "How do requests     │
│                   performing?"     flow across           │
│                                    services?"           │
│                                                         │
│  Tools:          Tools:           Tools:                │
│  • kubectl logs  • Prometheus     • Jaeger              │
│  • Fluentd/Bit   • Grafana        • Zipkin              │
│  • ELK Stack     • kube-state-    • OpenTelemetry       │
│  • Loki            metrics                              │
│                                                         │
│  ┌─────────────────────────────────────────────┐        │
│  │  Most Common Stack:                         │        │
│  │  Prometheus (collect) → Grafana (visualize)  │        │
│  └─────────────────────────────────────────────┘        │
└─────────────────────────────────────────────────────────┘
```

```bash
# Basic monitoring commands
kubectl top nodes                  # Node CPU/memory usage
kubectl top pods                   # Pod CPU/memory usage
kubectl get events --sort-by='.lastTimestamp'  # Recent events
kubectl logs <pod> --previous      # Logs from crashed container

# Install metrics-server (required for `kubectl top`)
minikube addons enable metrics-server   # minikube
```

#### Resource Health:

```yaml
# Liveness Probe → "Is it alive?" → Restart if not
livenessProbe:
  httpGet:
    path: /healthz
    port: 8080
  initialDelaySeconds: 15
  periodSeconds: 10
  failureThreshold: 3          # Restart after 3 failures

# Readiness Probe → "Is it ready for traffic?" → Remove from service if not
readinessProbe:
  httpGet:
    path: /ready
    port: 8080
  periodSeconds: 5

# Startup Probe → "Has it finished starting?" → For slow-starting apps
startupProbe:
  httpGet:
    path: /healthz
    port: 8080
  failureThreshold: 30
  periodSeconds: 10            # Give 300s to start up
```

### 📘 5B: Autoscaling

```
┌────────────────── AUTOSCALING ──────────────────────────┐
│                                                         │
│  ┌─────────────────────────────────────────┐            │
│  │  HPA (Horizontal Pod Autoscaler)        │            │
│  │  "Add more pods when load increases"    │            │
│  │                                         │            │
│  │  CPU > 70%?                             │            │
│  │  3 pods ──→ 5 pods ──→ 10 pods          │            │
│  └─────────────────────────────────────────┘            │
│                                                         │
│  ┌─────────────────────────────────────────┐            │
│  │  VPA (Vertical Pod Autoscaler)          │            │
│  │  "Give each pod more CPU/memory"        │            │
│  │                                         │            │
│  │  Pod: 256Mi → 512Mi → 1Gi              │            │
│  └─────────────────────────────────────────┘            │
│                                                         │
│  ┌─────────────────────────────────────────┐            │
│  │  Cluster Autoscaler                     │            │
│  │  "Add more NODES when needed"           │            │
│  │                                         │            │
│  │  3 nodes → 5 nodes → 10 nodes           │            │
│  │  (cloud provider adds VMs)              │            │
│  └─────────────────────────────────────────┘            │
└─────────────────────────────────────────────────────────┘
```

```yaml
# HPA — Most commonly used
apiVersion: autoscaling/v2
kind: HorizontalPodAutoscaler
metadata:
  name: webapp-hpa
spec:
  scaleTargetRef:
    apiVersion: apps/v1
    kind: Deployment
    name: webapp
  minReplicas: 2                  # Never go below 2
  maxReplicas: 20                 # Never exceed 20
  metrics:
  - type: Resource
    resource:
      name: cpu
      target:
        type: Utilization
        averageUtilization: 70    # Scale up if CPU > 70%
  - type: Resource
    resource:
      name: memory
      target:
        type: Utilization
        averageUtilization: 80    # Scale up if memory > 80%
```

```bash
# Quick HPA creation
kubectl autoscale deployment webapp --min=2 --max=20 --cpu-percent=70

# Monitor HPA
kubectl get hpa -w
```

### 📕 5C: Resource Management

```yaml
# Resource requests and limits
spec:
  containers:
  - name: app
    resources:
      requests:               # GUARANTEED resources (scheduling)
        memory: "128Mi"       # 128 Mebibytes
        cpu: "250m"           # 250 millicores (0.25 CPU)
      limits:                 # MAXIMUM allowed
        memory: "256Mi"       # OOMKilled if exceeded
        cpu: "500m"           # Throttled if exceeded

# ⚠️ KEY DIFFERENCE:
# - requests: Used by scheduler to PLACE pods
# - limits: Enforced at runtime, pod killed/throttled if exceeded
```

```yaml
# ResourceQuota — Limit resources per namespace
apiVersion: v1
kind: ResourceQuota
metadata:
  name: dev-quota
  namespace: dev
spec:
  hard:
    pods: "20"
    requests.cpu: "4"
    requests.memory: "8Gi"
    limits.cpu: "8"
    limits.memory: "16Gi"
```

### 📗 5D: Storage & Volumes

```
┌────────────────── STORAGE ──────────────────────────────┐
│                                                         │
│  Problem: Containers are EPHEMERAL                      │
│           Data is lost when container restarts           │
│                                                         │
│  Solution: VOLUMES                                      │
│                                                         │
│  ┌─────────────┐     ┌──────────────────────────────┐   │
│  │   emptyDir   │     │  Created with pod, dies with │   │
│  │              │     │  pod. Temp storage only.     │   │
│  └─────────────┘     └──────────────────────────────┘   │
│                                                         │
│  ┌─────────────┐     ┌──────────────────────────────┐   │
│  │  hostPath    │     │  Maps to folder on the node. │   │
│  │              │     │  Data survives pod restart.  │   │
│  └─────────────┘     └──────────────────────────────┘   │
│                                                         │
│  ┌─────────────┐     ┌──────────────────────────────┐   │
│  │  PV + PVC    │     │  PERSISTENT storage.         │   │
│  │              │     │  Cloud disks, NFS, etc.      │   │
│  │              │     │  Survives pod AND node death. │   │
│  └─────────────┘     └──────────────────────────────┘   │
│                                                         │
│  PV  = PersistentVolume (the actual disk)               │
│  PVC = PersistentVolumeClaim (pod's request for storage)│
│  SC  = StorageClass (defines HOW to provision PVs)      │
│                                                         │
│  Pod ──→ PVC ──→ PV ──→ Actual Disk                    │
│    "I need     "Give    "Here's                         │
│     10Gi"      me a     an AWS                          │
│                disk"    EBS vol"                         │
└─────────────────────────────────────────────────────────┘
```

```yaml
# PersistentVolumeClaim
apiVersion: v1
kind: PersistentVolumeClaim
metadata:
  name: postgres-data
spec:
  accessModes:
  - ReadWriteOnce            # One node can mount read-write
  resources:
    requests:
      storage: 20Gi
  storageClassName: standard  # Use default storage class

---
# Use PVC in a pod
spec:
  containers:
  - name: postgres
    image: postgres:15
    volumeMounts:
    - name: data
      mountPath: /var/lib/postgresql/data
  volumes:
  - name: data
    persistentVolumeClaim:
      claimName: postgres-data
```

### ✅ Checkpoint — Phase 5:
- [ ] You can set up HPA for auto-scaling
- [ ] You understand resource requests vs limits
- [ ] You can set up PVCs for persistent storage
- [ ] You've used liveness/readiness probes
- [ ] You know the Prometheus + Grafana monitoring stack

---

## PHASE 6: Deployment Patterns & CI/CD 🚀
**⏱️ 2 weeks | Priority: 🟡 IMPORTANT**

### 📗 6A: Deployment Strategies

```
┌───────────────── DEPLOYMENT STRATEGIES ─────────────────┐
│                                                         │
│  1. ROLLING UPDATE (Default)                            │
│     Old: ■ ■ ■ ■           Gradual replacement          │
│     New:         □ □ □ □    Zero downtime                │
│                                                         │
│  2. BLUE-GREEN                                          │
│     Blue (v1): ■ ■ ■ ■    ← traffic here               │
│     Green(v2): □ □ □ □    ← test, then switch           │
│     Switch: All traffic → Green instantly               │
│                                                         │
│  3. CANARY                                              │
│     v1: ■ ■ ■ ■ (90% traffic)                          │
│     v2: □        (10% traffic) ← test with real users   │
│     Gradually shift: 10% → 25% → 50% → 100%            │
│                                                         │
│  4. RECREATE (Downtime OK)                              │
│     Kill all old: ✗ ✗ ✗ ✗                              │
│     Start all new:        □ □ □ □                       │
│     Simple but causes downtime                          │
└─────────────────────────────────────────────────────────┘
```

### 📘 6B: Helm Charts (Package Manager for K8s)

> 🧒 **ELI5:** Helm is like `apt install` for Kubernetes. Instead of writing 10 YAML files manually, you run `helm install` and it sets up everything.

```bash
# Install Helm
curl https://raw.githubusercontent.com/helm/helm/main/scripts/get-helm-3 | bash

# Add a chart repository
helm repo add bitnami https://charts.bitnami.com/bitnami
helm repo update

# Install an app (e.g., WordPress)
helm install my-wordpress bitnami/wordpress

# List installed releases
helm list

# Upgrade with custom values
helm upgrade my-wordpress bitnami/wordpress \
  --set wordpressUsername=admin \
  --set wordpressPassword=secret123 \
  --set service.type=LoadBalancer

# Rollback
helm rollback my-wordpress 1

# Create your OWN chart
helm create my-app
# Creates:
# my-app/
# ├── Chart.yaml          # Chart metadata
# ├── values.yaml         # Default configuration
# ├── templates/          # YAML templates
# │   ├── deployment.yaml
# │   ├── service.yaml
# │   ├── ingress.yaml
# │   └── _helpers.tpl
# └── charts/             # Dependencies
```

### 📕 6C: CI/CD Integration

```
┌─────────────── CI/CD PIPELINE ──────────────────────────┐
│                                                         │
│  Developer                                              │
│     │                                                   │
│     ├─→ git push                                        │
│     │                                                   │
│     ↓                                                   │
│  CI Pipeline (GitHub Actions / GitLab CI / Jenkins)     │
│     │                                                   │
│     ├─→ Run tests                                       │
│     ├─→ Build Docker image                              │
│     ├─→ Push to Container Registry                      │
│     ├─→ Update K8s manifests (image tag)                │
│     │                                                   │
│     ↓                                                   │
│  CD Pipeline                                            │
│     │                                                   │
│     ├─→ OPTION A: kubectl apply (imperative)            │
│     ├─→ OPTION B: Helm upgrade (package-based)          │
│     └─→ OPTION C: GitOps (ArgoCD / Flux) ← BEST ✅     │
│                                                         │
└─────────────────────────────────────────────────────────┘
```

#### GitOps Pattern:

```
┌──────────────────── GitOps ─────────────────────────────┐
│                                                         │
│  Git Repository = Single Source of Truth                │
│                                                         │
│  Developer ─→ Updates YAML in Git                       │
│                       ↓                                 │
│  ArgoCD/Flux ─→ Watches Git repo                        │
│                       ↓                                 │
│  Detects change ─→ Syncs to K8s cluster automatically   │
│                                                         │
│  Benefits:                                              │
│  ✅ Version controlled infrastructure                   │
│  ✅ Easy rollback (git revert)                          │
│  ✅ Audit trail (git log)                               │
│  ✅ No manual kubectl apply needed                      │
└─────────────────────────────────────────────────────────┘
```

### ✅ Checkpoint — Phase 6:
- [ ] You can explain Rolling vs Blue-Green vs Canary deployments
- [ ] You can use Helm to install and manage applications
- [ ] You understand CI/CD pipeline for K8s
- [ ] You know what GitOps is (ArgoCD/Flux)

---

## PHASE 7: Advanced Topics & Scheduling 🧙
**⏱️ 2-3 weeks | Priority: 🟢 GOOD TO KNOW (🟡 for DevOps careers)**

### 📗 7A: Scheduling

| Concept | What It Does | Use Case |
|---------|-------------|----------|
| **Node Selector** | Schedule pod on specific nodes | "Run ML pods on GPU nodes" |
| **Taints & Tolerations** | Repel pods from nodes (unless tolerated) | "Only critical pods on master node" |
| **Node Affinity** | Advanced node selection rules | "Prefer nodes in us-east-1a" |
| **Pod Affinity** | Co-locate pods together | "Run cache near the app" |
| **Pod Anti-Affinity** | Keep pods apart | "Spread replicas across nodes" |
| **Topology Spread** | Even distribution across zones | "Spread across availability zones" |
| **Pod Priorities & Evictions** | Preempt low-priority pods | "Critical pods evict batch jobs" |

```yaml
# Taints and Tolerations example
# Taint a node (command line)
# kubectl taint nodes gpu-node gpu=true:NoSchedule

# Pod that tolerates the taint
spec:
  tolerations:
  - key: "gpu"
    operator: "Equal"
    value: "true"
    effect: "NoSchedule"
  containers:
  - name: ml-training
    image: ml-model:v1
```

### 📘 7B: Custom Resource Definitions (CRDs)

> Extend Kubernetes with your own custom resource types!

```yaml
# Define a custom resource
apiVersion: apiextensions.k8s.io/v1
kind: CustomResourceDefinition
metadata:
  name: databases.mycompany.com
spec:
  group: mycompany.com
  names:
    kind: Database
    plural: databases
    singular: database
  scope: Namespaced
  versions:
  - name: v1
    served: true
    storage: true
    schema:
      openAPIV3Schema:
        type: object
        properties:
          spec:
            type: object
            properties:
              engine:
                type: string
                enum: ["postgres", "mysql"]
              size:
                type: string

---
# Now you can create custom objects!
apiVersion: mycompany.com/v1
kind: Database
metadata:
  name: user-db
spec:
  engine: postgres
  size: "50Gi"
```

### 📕 7C: Cluster Operations (Self-Managed Clusters)

| Topic | What It Is | When Needed |
|-------|-----------|-------------|
| **Installing Control Plane** | Setting up master node with kubeadm | Self-managed clusters |
| **Adding Worker Nodes** | Joining nodes to cluster | Scaling infrastructure |
| **Multi-Cluster Management** | Running multiple K8s clusters | Large organizations |
| **Cluster Upgrades** | Upgrading K8s version safely | Maintenance |
| **Disaster Recovery** | etcd backups, cluster restore | Production ops |

> 💡 **For most BTech students:** Use managed K8s (GKE/EKS/AKS). Learning self-managed is valuable for DevOps roles but not required initially.

---

## 📅 Week-by-Week Schedule (at 2 hrs/day)

```
┌──────────┬───────────────────────────────────────────────────┐
│  WEEK    │  WHAT TO DO                                       │
├──────────┼───────────────────────────────────────────────────┤
│  1-2     │  Linux CLI, Networking basics, YAML               │
│  3-4     │  Docker deep-dive (build, run, compose, network)  │
│  5       │  K8s concepts, architecture, install minikube     │
│  6       │  First deployment! Pods, kubectl mastery          │
│  7       │  Deployments, ReplicaSets, rolling updates        │
│  8       │  StatefulSets, Jobs, CronJobs                     │
│  9       │  Services (ClusterIP, NodePort, LB), Ingress      │
│  10      │  ConfigMaps, Secrets, Namespaces                  │
│  11      │  RBAC, NetworkPolicies, Pod Security              │
│  12      │  Monitoring: Probes, metrics-server, Prometheus   │
│  13      │  HPA autoscaling, Resource mgmt, Quotas           │
│  14      │  PVs, PVCs, StorageClasses, Stateful apps         │
│  15      │  Helm charts (install, create, upgrade)           │
│  16      │  CI/CD pipeline, GitOps concepts, ArgoCD          │
│  17-18   │  🏗️ Portfolio Project (full app on K8s)           │
│  19-20   │  Advanced: Scheduling, CRDs, cluster ops          │
└──────────┴───────────────────────────────────────────────────┘
```

---

## 🏗️ Portfolio Project Ideas

| Level | Project | What You'll Demonstrate |
|-------|---------|------------------------|
| 🟢 Beginner | **Deploy a 3-tier app** (React + Node + Postgres) on K8s with Deployments, Services, ConfigMaps, PVC | Core K8s skills |
| 🟡 Medium | **CI/CD Pipeline** — GitHub Actions builds Docker image → pushes to registry → deploys to K8s with Helm + rolling updates | DevOps pipeline |
| 🔴 Advanced | **Microservices Platform** — 4-5 services with Ingress routing, HPA autoscaling, Prometheus/Grafana monitoring, GitOps with ArgoCD | Production-grade K8s |

---

## 💼 How This Helps in Placements & Career

| Where | How Kubernetes Helps |
|-------|---------------------|
| **DevOps/SRE Roles** | K8s is THE #1 required skill — ₹8-25 LPA for freshers |
| **Backend Roles** | "Deployed on K8s" in resume = strong signal |
| **System Design Interviews** | "I'd use K8s for orchestration with HPA for auto-scaling..." |
| **Certifications** | CKA (Certified Kubernetes Administrator) — highly valued |
| **Freelancing** | K8s consulting: ₹2000-5000/hr |
| **Startups** | Most startups run on K8s — instant value add |

### 🏆 Certifications Worth Getting:

| Cert | Level | Cost | Value |
|------|-------|------|-------|
| **CKA** (Certified Kubernetes Administrator) | Intermediate | ~$395 | 🔴 Very High |
| **CKAD** (Certified K8s App Developer) | Intermediate | ~$395 | 🟡 High |
| **CKS** (Certified K8s Security Specialist) | Advanced | ~$395 | 🟡 High (security roles) |

---

## 📚 Complete Resource Bank

### 🎥 YouTube (Free)
| Channel | What It Covers | Language |
|---------|---------------|----------|
| **TechWorld with Nana** | Best K8s beginner course (2.5 hrs) | English |
| **KodeKloud** (Mumshad) | Full K8s course + hands-on labs | English |
| **Abhishek Veeramalla** | K8s Zero to Hero, DevOps | English/Hindi |
| **Piyush Garg** | K8s for developers | Hindi |
| **NetworkChuck** | Networking + K8s fun intro | English |
| **That DevOps Guy** | Real-world K8s patterns | English |

### 📖 Documentation & Courses
| Resource | Type | Cost |
|----------|------|------|
| kubernetes.io/docs | Official Docs | Free |
| roadmap.sh/kubernetes | Interactive Roadmap | Free |
| KodeKloud Labs | Hands-on browser labs | Free tier / Paid |
| Killer.sh | CKA exam simulator | Paid (worth it for cert) |
| "Kubernetes Up & Running" (Book) | Textbook | ~₹700 |

### 🛠️ Practice Platforms
| Platform | What It Offers |
|----------|---------------|
| **Play with Kubernetes** (labs.play-with-k8s.com) | Free K8s in browser |
| **KillerCoda** | Interactive K8s scenarios | Free |
| **Minikube** | Local cluster on your laptop | Free |
| **KodeKloud Playgrounds** | Pre-configured environments | Free/Paid |

---

## 🎯 What Should You Do RIGHT NOW?

```
IF you know Docker well:
  → Jump to Phase 1, install Minikube, deploy your first app TODAY

IF you don't know Docker:
  → Start Phase 0. Docker is NON-NEGOTIABLE.
  → Spend 2 weeks mastering Docker, then come here.

IF you're targeting DevOps placements:
  → This is your HIGHEST priority skill
  → Aim for CKA certification within 6 months

IF you're a backend developer:
  → Learn Phases 1-4 (enough to deploy your apps)
  → Skip advanced cluster ops unless interested
```

---

