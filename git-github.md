

# 🗺️ ROADMAP: Git & GitHub — Complete Mastery Plan

---

## 📊 Roadmap Overview

```
⏱️ Total Duration  : 6-8 Weeks (2 hrs/day)
🎯 End Goal        : Confident collaboration, clean Git history,
                      GitHub Actions, open source ready
📈 Difficulty Curve : Beginner → Intermediate → Advanced
💼 Resume Impact    : HIGH (Every tech role requires Git)
```

| Phase | Topic | Duration | Priority |
|---|---|---|---|
| 1 | Git Basics & Local Workflow | Week 1 | 🔴 Critical |
| 2 | Branching & Merging | Week 2 | 🔴 Critical |
| 3 | GitHub Essentials & Remote Collaboration | Week 3 | 🔴 Critical |
| 4 | Collaboration on GitHub (PRs, Issues, Forks) | Week 4 | 🔴 Critical |
| 5 | Intermediate Git (Stash, Rebase, Tags, Hooks) | Week 5 | 🟡 Important |
| 6 | GitHub Workflow (Actions, CLI, Projects) | Week 6 | 🟡 Important |
| 7 | Advanced Git & GitHub Features | Week 7-8 | 🟢 Good to Know |

---

## 🟦 PHASE 1: Git Basics & Local Workflow (Week 1)

> 🧒 **Analogy:** Git is like a **save game system** in a video game. You can save at any point, go back to any save, and even try different paths — all without losing your main progress.

---

### 📌 Day 1-2: Concepts + Setup

#### Topics:
```
✅ What is Version Control?
✅ Why use Version Control?
✅ Git vs Other VCS (SVN, Mercurial)
✅ Installing Git Locally
✅ What is a Repository?
```

#### 🎨 How Version Control Works:

```
WITHOUT VERSION CONTROL:
─────────────────────────
📄 project_final.py
📄 project_final_v2.py
📄 project_final_REAL.py
📄 project_final_FINAL_v3_SUBMIT.py   ← 😭 Disaster

WITH GIT:
─────────────────────────
📁 project/
 └── .git/              ← Git tracks ALL history internally
 └── main.py            ← Always the latest clean version
 
 You can time-travel to ANY version anytime! ⏰
```

#### 💻 Hands-On:
```bash
# Install Git
# Windows: Download from git-scm.com
# Mac: brew install git
# Linux: sudo apt install git

# Verify installation
git --version

# Set up identity (GLOBAL config - one time setup)
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"

# Check your config
git config --list

# LOCAL config (per project - overrides global)
cd my-project
git config user.name "Different Name"     # only for THIS repo
git config user.email "work@company.com"
```

#### 🔑 Key Concept: Local vs Global Config
```
┌─────────────────────────────────────────────────┐
│  GLOBAL (~/.gitconfig)  │  LOCAL (.git/config)  │
├─────────────────────────┼───────────────────────┤
│  Applies to ALL repos   │  Applies to ONE repo  │
│  Set once               │  Set per project      │
│  Default fallback       │  Overrides global     │
│  Your personal identity │  Work/client identity │
└─────────────────────────┴───────────────────────┘
```

---

### 📌 Day 3-4: Core Git Workflow

#### Topics:
```
✅ git init — Initialize a repository
✅ Working Directory → Staging Area → Repository
✅ git add — Stage changes
✅ git commit — Save snapshot
✅ .gitignore — Exclude files
✅ git status — Check state
✅ git log — View commit history
```

#### 🎨 The 3 Stages of Git (MOST IMPORTANT DIAGRAM):

```
  ┌──────────────┐     git add     ┌──────────────┐    git commit   ┌──────────────┐
  │   WORKING    │ ──────────────► │   STAGING    │ ─────────────► │  REPOSITORY  │
  │  DIRECTORY   │                 │    AREA      │                │   (.git/)    │
  │              │                 │  (Index)     │                │              │
  │ You edit     │                 │ "Ready to    │                │ "Permanently │
  │ files here   │                 │  save" zone  │                │  saved"      │
  └──────────────┘                 └──────────────┘                └──────────────┘
        │                                                                │
        │◄──────────────────── git checkout ────────────────────────────┤
        
  🧒 Analogy:
  Working Dir  = Your kitchen (you're cooking / making changes)
  Staging Area = The plate (you've decided WHAT to serve)
  Repository   = The dining table (served & recorded forever)
```

#### 💻 Hands-On Practice:
```bash
# Create a new project
mkdir my-first-repo
cd my-first-repo

# Initialize Git
git init
# Output: Initialized empty Git repository in .../my-first-repo/.git/

# Check status (will say "No commits yet")
git status

# Create a file
echo "# My First Project" > README.md
echo "print('Hello Git!')" > app.py

# Check status again — files are UNTRACKED
git status

# Stage specific file
git add README.md

# Stage all files
git add .
# OR
git add -A

# Check status — files are now STAGED (green)
git status

# Commit with a message
git commit -m "Initial commit: add README and app.py"

# View commit history
git log
git log --oneline           # compact view
git log --oneline --graph   # visual branch graph
```

#### 📄 .gitignore (What to Exclude):
```bash
# Create .gitignore file
touch .gitignore
```

```gitignore
# .gitignore contents

# Compiled files
*.class
*.o
*.pyc
__pycache__/

# IDE files
.vscode/
.idea/
*.swp

# OS files
.DS_Store
Thumbs.db

# Environment & secrets
.env
node_modules/
venv/
*.log

# Build output
dist/
build/
```

```
💡 PRO TIP: Always create .gitignore BEFORE your first commit.
   Use gitignore.io to generate templates for your tech stack.
```

---

### 📌 Day 5: Viewing History & Understanding Commits

```bash
# Different ways to view history
git log                        # Full details
git log --oneline              # Short hash + message
git log --oneline --graph      # Shows branch structure
git log --oneline -5           # Last 5 commits
git log --author="Your Name"   # Filter by author
git log --since="2024-01-01"   # Filter by date
git log -- app.py              # History of specific file

# See what changed in a commit
git show abc1234               # Show specific commit details

# See current changes (not yet staged)
git diff

# See staged changes (ready to commit)
git diff --staged
```

#### 🎨 Anatomy of a Commit:
```
┌──────────────────────────────────────────────────┐
│  Commit: a1b2c3d4e5f6...  (SHA-1 Hash — unique) │
├──────────────────────────────────────────────────┤
│  Author: Your Name <email@example.com>           │
│  Date:   Mon Jan 15 10:30:00 2025 +0530          │
│                                                  │
│  Message: "Add login functionality"              │
│                                                  │
│  Parent:  f6e5d4c3b2a1...  (previous commit)     │
│  Tree:    snapshot of ALL files at this point     │
│                                                  │
│  Changes: +45 lines added, -12 lines removed     │
└──────────────────────────────────────────────────┘

Each commit = a SNAPSHOT of your entire project at that moment.
NOT just the changes — the ENTIRE state (stored efficiently).
```

### ✅ Week 1 Checkpoint:
```
□ Can initialize a repo from scratch
□ Understand Working Dir → Staging → Repo flow
□ Can add, commit, and view history
□ Have a proper .gitignore
□ Can read git log output
□ Understand what a commit contains
```

---

## 🟦 PHASE 2: Branching & Merging (Week 2)

> 🧒 **Analogy:** Branches are like **parallel railway tracks**. The main track (main branch) keeps running. You create a side track to build a new feature. Once tested, you merge it back into the main track.

---

### 📌 Day 1-2: Branching Basics

```bash
# See all branches (* = current branch)
git branch

# Create a new branch
git branch feature-login

# Switch to that branch
git checkout feature-login
# OR (modern way)
git switch feature-login

# Create AND switch in one command
git checkout -b feature-signup
# OR
git switch -c feature-signup

# Rename a branch
git branch -m old-name new-name

# Delete a branch (after merging)
git branch -d feature-login

# Force delete (even if not merged)
git branch -D experimental-branch
```

#### 🎨 Branch Visualization:
```
BEFORE BRANCHING:
─────────────────
main:  C1 ──── C2 ──── C3  (HEAD)

AFTER CREATING BRANCH:
──────────────────────
main:           C1 ──── C2 ──── C3
                                  │
feature-login:                    └──── C4 ──── C5  (HEAD)

BOTH branches share C1, C2, C3 history.
feature-login has NEW commits C4, C5.
main is UNAFFECTED by changes in feature-login.
```

---

### 📌 Day 3-4: Merging Basics

#### Types of Merges:
```
┌───────────────────────────────────────────────────────────┐
│  TYPE              │  WHEN                  │  RESULT     │
├────────────────────┼────────────────────────┼─────────────┤
│  Fast-Forward      │  Main has no new       │  Linear     │
│                    │  commits since branch  │  history    │
├────────────────────┼────────────────────────┼─────────────┤
│  3-Way Merge       │  Both branches have    │  Merge      │
│  (Non-FF)          │  new commits           │  commit     │
├────────────────────┼────────────────────────┼─────────────┤
│  Squash Merge      │  You want to combine   │  Single     │
│                    │  all branch commits    │  commit     │
└────────────────────┴────────────────────────┴─────────────┘
```

#### 🎨 Fast-Forward Merge:
```
BEFORE:
main:     C1 ── C2
                  \
feature:           C3 ── C4    (main has NO new commits)

AFTER git merge feature (from main):
main:     C1 ── C2 ── C3 ── C4    (pointer just moves forward)

No merge commit needed. Clean linear history.
```

#### 🎨 3-Way (Non-Fast-Forward) Merge:
```
BEFORE:
main:     C1 ── C2 ── C5        (main has NEW commits)
                  \
feature:           C3 ── C4

AFTER git merge feature (from main):
main:     C1 ── C2 ── C5 ── M   (M = merge commit)
                  \         /
feature:           C3 ── C4
```

#### 💻 Merge Commands:
```bash
# Step 1: Go to the branch you want to merge INTO
git checkout main

# Step 2: Merge the feature branch into main
git merge feature-login

# Force a merge commit (even if fast-forward possible)
git merge --no-ff feature-login

# Squash merge (combine all commits into one)
git merge --squash feature-login
git commit -m "Add login feature"
```

---

### 📌 Day 5: Handling Merge Conflicts

> 🧒 **Analogy:** Two people editing the same paragraph of a Google Doc at the same time. Google shows both versions — you decide what to keep.

```
WHEN DO CONFLICTS HAPPEN?
─────────────────────────
When TWO branches modify the SAME line in the SAME file.
Git doesn't know which version to keep → asks YOU to decide.
```

#### 💻 Conflict Example:
```bash
# You'll see this in the file:
<<<<<<< HEAD
print("Hello from main branch")
=======
print("Hello from feature branch")
>>>>>>> feature-login

# <<<<<<< HEAD        = Your current branch's version
# =======             = Separator
# >>>>>>> feature     = Incoming branch's version
```

#### How to Resolve:
```bash
# Step 1: Open the conflicted file
# Step 2: Choose what to keep (edit manually):
print("Hello from main branch")    # Keep this? OR
print("Hello from feature branch") # Keep this? OR
print("Hello! Welcome!")            # Write something new?

# Step 3: Remove the conflict markers (<<<, ===, >>>)

# Step 4: Stage the resolved file
git add resolved-file.py

# Step 5: Complete the merge
git commit -m "Resolve merge conflict in resolved-file.py"

# To ABORT a merge (go back to before merge)
git merge --abort
```

---

### 📌 Day 5 (Continued): Cherry-Picking

```bash
# Pick ONE specific commit from another branch
git cherry-pick abc1234

# Use case: You want ONE bug fix from feature branch
# but don't want to merge the ENTIRE branch yet
```

```
main:     C1 ── C2 ── C3 ── C4'    (C4 is cherry-picked)
                  \
feature:           C3 ── C4 ── C5   (C4 = the bug fix)
```

### ✅ Week 2 Checkpoint:
```
□ Can create, switch, rename, delete branches
□ Understand fast-forward vs 3-way merge
□ Can handle merge conflicts confidently
□ Know when to use squash merge
□ Can cherry-pick a commit
□ Understand visual branch diagrams
```

---

## 🟦 PHASE 3: GitHub Essentials & Remote Collaboration (Week 3)

> 🧒 **Analogy:** Git = your personal diary on your desk. GitHub = a shared cloud drive where the whole team can read and write in the diary together.

---

### 📌 Day 1: GitHub Account & Profile Setup

```
✅ Create account at github.com
✅ Choose a professional username (avoid: xX_coder_2005_Xx)
✅ Add profile photo, bio, location
✅ Set up Profile README (special repository)
✅ Understand Private vs Public repos
```

#### 💻 Profile README (the special trick):
```bash
# Create a repo with EXACT SAME name as your username
# e.g., username = "rahul-dev" → create repo "rahul-dev"
# Add a README.md → it shows on your PROFILE page
```

```markdown
# Hey, I'm Rahul 👋

🎓 BTech CSE | XYZ College | 2026 Batch
💻 Full Stack Developer | DSA Enthusiast
🌱 Currently learning: React.js, System Design
🔭 Working on: E-commerce project

## 🛠️ Tech Stack
![C++](https://img.shields.io/badge/-C++-00599C?logo=cplusplus&logoColor=white)
![Python](https://img.shields.io/badge/-Python-3776AB?logo=python&logoColor=white)
![JavaScript](https://img.shields.io/badge/-JavaScript-F7DF1E?logo=javascript&logoColor=black)

## 📊 GitHub Stats
![GitHub Stats](https://github-readme-stats.vercel.app/api?username=rahul-dev&show_icons=true)

## 📫 Connect
[![LinkedIn](https://img.shields.io/badge/-LinkedIn-0A66C2?logo=linkedin)](https://linkedin.com/in/rahul)
```

---

### 📌 Day 2-3: Git Remotes

#### 🎨 Local vs Remote:
```
┌─────────────────┐          ┌──────────────────┐
│  YOUR COMPUTER  │          │     GITHUB       │
│  (Local Repo)   │  ◄────► │  (Remote Repo)   │
│                 │  push/   │                  │
│  .git/          │  pull    │  github.com/     │
│  Working Dir    │  fetch   │  user/repo       │
└─────────────────┘          └──────────────────┘
```

#### 💻 Remote Commands:
```bash
# Connect local repo to GitHub (after creating repo on GitHub)
git remote add origin https://github.com/username/repo-name.git

# Verify remote
git remote -v

# Push local commits to GitHub
git push -u origin main
# -u = set upstream (so next time just "git push" works)

# Pull latest changes from GitHub
git pull origin main

# Fetch changes (download but DON'T merge)
git fetch origin
# Then inspect: git log origin/main
# Then merge if OK: git merge origin/main

# Clone an existing repo from GitHub
git clone https://github.com/username/repo-name.git

# Remove a remote
git remote remove origin

# Rename a remote
git remote rename origin upstream
```

#### 🔑 Push vs Pull vs Fetch:
```
┌────────────────────────────────────────────────────────────┐
│  COMMAND     │  DIRECTION        │  WHAT IT DOES          │
├──────────────┼───────────────────┼────────────────────────┤
│  git push    │  Local → Remote   │  Upload your commits   │
│  git pull    │  Remote → Local   │  Download + merge      │
│  git fetch   │  Remote → Local   │  Download only (safe)  │
│  git clone   │  Remote → Local   │  First-time full copy  │
└──────────────┴───────────────────┴────────────────────────┘

💡 git pull = git fetch + git merge (combined)
   Use git fetch when you want to REVIEW before merging.
```

---

### 📌 Day 4-5: Creating & Managing Repositories on GitHub

```bash
# Two workflows:

# WORKFLOW 1: Start locally, push to GitHub
mkdir new-project && cd new-project
git init
# ... make commits ...
# Create empty repo on GitHub (NO README, NO .gitignore)
git remote add origin https://github.com/user/new-project.git
git branch -M main
git push -u origin main

# WORKFLOW 2: Start on GitHub, clone locally
# Create repo on GitHub (WITH README)
git clone https://github.com/user/new-project.git
cd new-project
# ... start working ...
```

#### SSH vs HTTPS:
```
┌──────────────────────────────────────────────────────┐
│  HTTPS                      │  SSH                   │
├─────────────────────────────┼────────────────────────┤
│  Asks password each time    │  No password needed    │
│  (or use credential manager)│  (uses SSH keys)       │
│  Easier to set up           │  More secure           │
│  Works through firewalls    │  Recommended for daily │
│  Good for beginners         │  use                   │
└─────────────────────────────┴────────────────────────┘
```

```bash
# Set up SSH key (one-time):
ssh-keygen -t ed25519 -C "your.email@example.com"
# Press Enter for defaults
# Copy public key:
cat ~/.ssh/id_ed25519.pub
# Paste in GitHub → Settings → SSH Keys → New SSH Key

# Now clone via SSH:
git clone git@github.com:username/repo.git
```

### ✅ Week 3 Checkpoint:
```
□ GitHub profile is set up with README
□ Can create repos (both workflows)
□ Understand push, pull, fetch, clone
□ Can connect local repo to remote
□ SSH key is configured
□ Know the difference between HTTPS and SSH
```

---

## 🟦 PHASE 4: Collaboration on GitHub (Week 4)

> 🧒 **Analogy:** Forking = taking a photocopy of someone's notebook to try your own solutions. Pull Request = handing back your photocopy and asking them to copy your answer into their original notebook.

---

### 📌 Day 1-2: Forking, Cloning & Pull Requests

#### 🎨 Forking vs Cloning:
```
┌──────────────────────────────────────────────────────────┐
│  CLONING                       │  FORKING               │
├────────────────────────────────┼────────────────────────┤
│  Copy to YOUR COMPUTER         │  Copy to YOUR GITHUB   │
│  Direct collaborator access    │  For external contrib  │
│  Same remote (origin)          │  Your own remote copy  │
│  Use when: you're on the team  │  Use when: open source │
└────────────────────────────────┴────────────────────────┘

FORK WORKFLOW (Open Source):
                                    
  Original Repo ──── Fork ────► Your GitHub Copy
  (upstream)                         │
                                     │ clone
                                     ▼
                              Your Local Copy
                                     │
                                     │ push
                                     ▼
                              Your GitHub Copy
                                     │
                                     │ Pull Request
                                     ▼
                              Original Repo (merged!)
```

#### 💻 Complete Fork → PR Workflow:
```bash
# Step 1: Fork on GitHub (click "Fork" button on repo page)

# Step 2: Clone YOUR fork
git clone https://github.com/YOUR-USERNAME/forked-repo.git
cd forked-repo

# Step 3: Add original repo as "upstream"
git remote add upstream https://github.com/ORIGINAL-OWNER/repo.git
git remote -v
# origin    → YOUR fork
# upstream  → ORIGINAL repo

# Step 4: Create a feature branch (NEVER work on main!)
git checkout -b fix-typo-readme

# Step 5: Make changes, commit
git add .
git commit -m "Fix typo in README.md"

# Step 6: Push to YOUR fork
git push origin fix-typo-readme

# Step 7: Go to GitHub → "Compare & Pull Request" button appears
# Fill in PR title, description → Create Pull Request

# Step 8: Keep fork updated with original
git fetch upstream
git checkout main
git merge upstream/main
git push origin main
```

---

### 📌 Day 3: Issues, Labels, and Collaboration Features

```
GitHub Issues = Task Tracker / Bug Reporter

CREATING GOOD ISSUES:
─────────────────────
Title: Clear, concise, actionable
  ✅ "Login button not responding on mobile"
  ❌ "Bug"

Body:
  - What happened (actual behavior)
  - What should happen (expected behavior)
  - Steps to reproduce
  - Screenshots if applicable
  - Environment (OS, browser, version)
```

#### Labels for Issues/PRs:
```
Common Labels:
  🔴 bug              → Something isn't working
  🟢 enhancement      → New feature request
  🟡 documentation    → Docs improvement
  🔵 good first issue → Great for newcomers
  🟣 help wanted      → Extra attention needed
  ⚪ duplicate         → Already reported
  🟤 wontfix          → Won't be addressed
```

#### Other Collaboration Features:
```
📌 Mentions      → @username to notify someone
👍 Reactions     → 👍 👎 😄 🎉 😕 ❤️ (react to comments)
💬 Commenting    → Discuss on issues & PRs
📋 Saved Replies → Template responses for common situations
🏷️ Milestones    → Group issues into release targets
📌 Pinned Issues → Important issues stay on top
```

---

### 📌 Day 4-5: Pull Request Best Practices

#### Creating a Good PR:
```markdown
## PR Title
feat: Add user authentication with JWT

## Description
- Implemented login/signup API endpoints
- Added JWT token generation and validation
- Password hashing with bcrypt
- Added middleware for protected routes

## Changes Made
- `routes/auth.js` — New file: auth routes
- `middleware/auth.js` — New file: JWT middleware  
- `models/User.js` — New file: User schema
- `package.json` — Added jsonwebtoken, bcrypt

## Testing
- ✅ Login with valid credentials
- ✅ Login with invalid credentials (returns 401)
- ✅ Signup with new user
- ✅ Signup with existing email (returns 409)
- ✅ Access protected route with valid token
- ✅ Access protected route without token (returns 403)

## Screenshots
[attach if UI changes]

## Related Issues
Closes #42
```

#### PR Review Process:
```
  Author creates PR
        │
        ▼
  Reviewer reviews code
        │
  ┌─────┴─────┐
  │            │
Approve    Request 
  │        Changes
  │            │
  ▼            ▼
 Merge     Author fixes
             │
             ▼
        Re-review
             │
             ▼
          Approve → Merge
```

### ✅ Week 4 Checkpoint:
```
□ Can fork a repo and create a PR
□ Can keep fork synced with upstream
□ Know how to write good issues
□ Know how to write good PR descriptions
□ Understand code review process
□ Used labels, mentions, and reactions
□ MAKE YOUR FIRST OPEN SOURCE CONTRIBUTION! 🎉
```

---

## 🟨 PHASE 5: Intermediate Git (Week 5)

---

### 📌 Day 1: Git Stash

> 🧒 **Analogy:** You're cooking biryani (feature work). Suddenly mom says make chai (urgent bug fix). You **stash** the biryani prep aside, make chai, then come back and **pop** your biryani prep back.

```bash
# Save current changes temporarily (without committing)
git stash
# OR with a message
git stash save "WIP: login form validation"

# List all stashes
git stash list
# stash@{0}: On feature: WIP: login form validation
# stash@{1}: On main: quick experiment

# Apply the latest stash (keeps it in stash list)
git stash apply

# Apply AND remove from stash list
git stash pop

# Apply a specific stash
git stash apply stash@{1}

# Delete a stash
git stash drop stash@{0}

# Delete all stashes
git stash clear

# See what's in a stash
git stash show -p stash@{0}
```

---

### 📌 Day 2: Undoing Changes

```
┌────────────────────────────────────────────────────────────────────┐
│  SITUATION                        │  COMMAND                      │
├───────────────────────────────────┼───────────────────────────────┤
│  Undo changes in working dir     │  git checkout -- file.py      │
│  (not yet staged)                │  git restore file.py          │
├───────────────────────────────────┼───────────────────────────────┤
│  Unstage a file (keep changes)   │  git reset HEAD file.py       │
│                                  │  git restore --staged file.py │
├───────────────────────────────────┼───────────────────────────────┤
│  Undo LAST commit (keep changes) │  git reset --soft HEAD~1      │
├───────────────────────────────────┼───────────────────────────────┤
│  Undo last commit (unstage too)  │  git reset --mixed HEAD~1     │
├───────────────────────────────────┼───────────────────────────────┤
│  Undo last commit (DELETE all)   │  git reset --hard HEAD~1      │
│  ⚠️ DANGEROUS                    │                               │
├───────────────────────────────────┼───────────────────────────────┤
│  Create NEW commit that undoes   │  git revert abc1234           │
│  an old commit (SAFE for shared) │                               │
└───────────────────────────────────┴───────────────────────────────┘
```

#### 🎨 Reset vs Revert:
```
git reset  = TIME TRAVEL (erases history — like it never happened)
             ⚠️ NEVER use on commits already pushed to shared repo

git revert = UNDO BUTTON (creates a NEW commit that undoes changes)
             ✅ SAFE for shared repos — history is preserved

RESET (rewrites history):
  C1 ── C2 ── C3 (HEAD)
  After reset --hard HEAD~1:
  C1 ── C2 (HEAD)         ← C3 is GONE

REVERT (adds undo commit):
  C1 ── C2 ── C3 (HEAD)
  After revert C3:
  C1 ── C2 ── C3 ── C3' (HEAD)   ← C3' undoes C3's changes
```

#### Reset Modes:
```
                    Working Dir    Staging Area    Commits
                    ───────────    ────────────    ───────
  --soft            ✅ Kept        ✅ Kept          ❌ Undone
  --mixed (default) ✅ Kept        ❌ Unstaged      ❌ Undone
  --hard            ❌ DELETED     ❌ DELETED        ❌ Undone
```

---

### 📌 Day 3: Rewriting History

```bash
# Amend the last commit (change message or add files)
git commit --amend -m "Better commit message"

# Add forgotten file to last commit
git add forgotten-file.py
git commit --amend --no-edit    # keeps same message

# Interactive rebase — edit, squash, reorder last N commits
git rebase -i HEAD~3
# Opens editor with options:
#   pick   = keep commit as is
#   reword = change commit message
#   edit   = stop and let you amend
#   squash = merge into previous commit
#   drop   = remove commit entirely

# Force push after rewriting history
git push --force
# OR safer:
git push --force-with-lease   # fails if someone else pushed
```

#### 🎨 Rebase vs Merge:
```
MERGE (preserves history):
  main:     A ── B ── C ──── M (merge commit)
                  \         /
  feature:         D ── E ──

REBASE (linear history):
  main:     A ── B ── C
  feature:               D' ── E'  (replayed on top of C)

After rebase + fast-forward merge:
  main:     A ── B ── C ── D' ── E'  (clean linear history!)
```

```bash
# Rebase feature branch onto main
git checkout feature
git rebase main
# Then merge (will be fast-forward)
git checkout main
git merge feature
```

⚠️ **Golden Rule:** Never rebase commits that have been pushed and shared with others.

---

### 📌 Day 4: Tagging & Releases

```bash
# Lightweight tag (just a pointer)
git tag v1.0

# Annotated tag (recommended — has metadata)
git tag -a v1.0 -m "First stable release"

# Tag a specific past commit
git tag -a v0.9 abc1234 -m "Beta release"

# List all tags
git tag
git tag -l "v1.*"     # filter tags

# Push tags to remote
git push origin v1.0        # push one tag
git push origin --tags       # push ALL tags

# Checkout a specific tag
git checkout v1.0
# ⚠️ This puts you in DETACHED HEAD state
# Create a branch from tag to make changes:
git checkout -b hotfix-v1.0 v1.0

# Delete a tag
git tag -d v1.0                    # local
git push origin --delete v1.0      # remote
```

#### GitHub Releases:
```
Tags on GitHub can be turned into RELEASES:
  → Go to repo → Releases → "Create new release"
  → Choose tag → Add release notes → Attach binaries
  → This creates a downloadable release page

Use for: distributing compiled apps, changelogs, versioning
```

---

### 📌 Day 5: Viewing Diffs & Git Hooks (Intro)

#### Diffs:
```bash
# Unstaged changes (working dir vs staging)
git diff

# Staged changes (staging vs last commit)
git diff --staged
git diff --cached        # same thing

# Between two commits
git diff abc123 def456

# Between two branches
git diff main..feature-login

# Just file names (no content)
git diff --name-only

# Stats (files changed, insertions, deletions)
git diff --stat
```

#### Git Hooks (Automation):
```bash
# Hooks = scripts that run automatically on git events
# Located in: .git/hooks/

# Common hooks:
#   pre-commit    → Runs BEFORE commit (lint code, run tests)
#   commit-msg    → Validate commit message format
#   pre-push      → Runs BEFORE push (run full test suite)
#   post-checkout → Runs AFTER checkout (install dependencies)

# Example: pre-commit hook to check for console.log
# File: .git/hooks/pre-commit (make executable: chmod +x)

#!/bin/sh
if grep -rn "console.log" --include="*.js" src/; then
    echo "❌ Remove console.log statements before committing!"
    exit 1
fi
echo "✅ No console.log found. Proceeding with commit."
```

### ✅ Week 5 Checkpoint:
```
□ Can use git stash fluently
□ Understand reset --soft/--mixed/--hard
□ Know when to use reset vs revert
□ Can amend commits and do interactive rebase
□ Understand rebase vs merge tradeoffs
□ Can create and push tags
□ Can read diffs between commits/branches
□ Know what Git hooks are
```

---

## 🟨 PHASE 6: GitHub Workflow & Automation (Week 6)

---

### 📌 Day 1-2: GitHub Actions (CI/CD)

> 🧒 **Analogy:** GitHub Actions is like having a **robot assistant** that automatically tests your code, builds your project, and deploys it every time you push — so you don't have to do it manually.

```yaml
# File: .github/workflows/ci.yml

name: CI Pipeline    # Name of the workflow

on:                  # TRIGGERS — when should this run?
  push:
    branches: [main]
  pull_request:
    branches: [main]
  # schedule:
  #   - cron: '0 0 * * *'    # daily at midnight

jobs:
  test:              # Job name
    runs-on: ubuntu-latest    # Runner (machine)
    
    steps:
      - name: Checkout code
        uses: actions/checkout@v4    # Marketplace action
      
      - name: Set up Python
        uses: actions/setup-python@v5
        with:
          python-version: '3.11'
      
      - name: Install dependencies
        run: pip install -r requirements.txt
      
      - name: Run tests
        run: python -m pytest tests/
      
      - name: Lint code
        run: flake8 src/

  build:
    needs: test      # Only run if 'test' job passes
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - name: Build project
        run: echo "Building..."
```

#### Key GitHub Actions Concepts:
```
┌────────────────────────────────────────────────────┐
│  CONCEPT            │  EXPLANATION                 │
├─────────────────────┼──────────────────────────────┤
│  Workflow           │  Entire automation pipeline  │
│  Event/Trigger      │  What starts the workflow    │
│  Job                │  Group of steps              │
│  Step               │  Individual task             │
│  Runner             │  Machine that executes jobs  │
│  Action             │  Reusable step (marketplace) │
│  Secrets            │  Encrypted env variables     │
│  Artifacts          │  Files produced by workflow  │
│  Cache              │  Speed up by caching deps    │
└─────────────────────┴──────────────────────────────┘
```

#### Secrets & Environment Variables:
```yaml
# Store secrets: Repo → Settings → Secrets → New secret
# Use in workflow:
steps:
  - name: Deploy
    env:
      API_KEY: ${{ secrets.API_KEY }}
      DB_URL: ${{ secrets.DATABASE_URL }}
    run: ./deploy.sh
```

---

### 📌 Day 3: GitHub CLI

```bash
# Install: https://cli.github.com/
gh --version

# Authenticate
gh auth login

# Create repo from terminal
gh repo create my-project --public --clone

# Create issue
gh issue create --title "Bug: login fails" --body "Steps to reproduce..."
gh issue list
gh issue view 42

# Create PR from terminal
gh pr create --title "Add login" --body "Implements #42"
gh pr list
gh pr view 15
gh pr merge 15

# Clone & fork
gh repo clone owner/repo
gh repo fork owner/repo

# View repo in browser
gh repo view --web
```

---

### 📌 Day 4-5: GitHub Projects & Team Collaboration

#### GitHub Projects (Kanban):
```
┌────────────┬────────────┬────────────┬────────────┐
│  📋 TODO   │  🔄 IN     │  👀 REVIEW │  ✅ DONE   │
│            │  PROGRESS  │            │            │
├────────────┼────────────┼────────────┼────────────┤
│ #12 Add    │ #8 Fix     │ #15 Update │ #3 Setup   │
│ dark mode  │ auth bug   │ README     │ CI/CD      │
│            │            │            │            │
│ #18 API    │ #11 Add    │            │ #7 Add     │
│ rate limit │ tests      │            │ .gitignore │
└────────────┴────────────┴────────────┴────────────┘
```

#### GitHub Organizations:
```
Organization
├── Members (different permission levels)
│   ├── Owner — full access
│   ├── Member — standard access
│   └── Outside Collaborator — specific repos only
├── Teams
│   ├── Frontend Team → access to frontend repos
│   ├── Backend Team → access to backend repos
│   └── DevOps Team → access to infra repos
└── Repositories
    ├── Public repos
    └── Private repos (team-restricted)
```

#### GitHub Discussions:
```
Like a forum within your repo:
  → Q&A (Questions & Answers)
  → General (open discussion)
  → Ideas (feature requests)
  → Show and Tell (share what you've built)
  
Unlike Issues: for conversation, not tracking tasks.
```

### ✅ Week 6 Checkpoint:
```
□ Can write a basic GitHub Actions workflow
□ Understand YAML syntax for workflows
□ Can use GitHub CLI for common tasks
□ Know how to use GitHub Projects (Kanban)
□ Understand Organizations & Teams
□ Can set up CI/CD for a project
```

---

## 🟩 PHASE 7: Advanced Git & More GitHub Features (Week 7-8)

---

### 📌 Advanced Git Commands

```bash
# ─── GIT REFLOG ───
# Your safety net — records EVERY HEAD movement
git reflog
# Even if you accidentally delete commits with reset --hard,
# reflog remembers them for ~90 days
git reset --hard HEAD@{3}    # recover to reflog entry

# ─── GIT BISECT ───
# Binary search through commits to find which one introduced a bug
git bisect start
git bisect bad                  # current commit is broken
git bisect good abc1234         # this old commit was working
# Git checks out middle commit, you test:
git bisect good    # or    git bisect bad
# Repeat until Git finds the EXACT commit that broke things
git bisect reset   # go back to normal

# ─── GIT WORKTREE ───
# Work on multiple branches simultaneously WITHOUT stashing
git worktree add ../feature-branch feature-branch
# Creates a new directory linked to feature-branch
# You can have main in one folder, feature in another

# ─── GIT LFS (Large File Storage) ───
# For large files (datasets, models, videos, images)
git lfs install
git lfs track "*.psd"
git lfs track "*.zip"
git lfs track "datasets/**"
git add .gitattributes
git add large-file.psd
git commit -m "Add large file via LFS"

# ─── GIT PATCH ───
# Export changes as a patch file (for email/offline sharing)
git format-patch HEAD~3      # last 3 commits as patch files
git am 0001-fix-bug.patch    # apply a patch

# ─── GIT ATTRIBUTES ───
# .gitattributes file — control how Git handles files
*.jpg binary
*.md linguist-documentation
*.py diff=python
```

---

### 📌 Submodules

```bash
# Include another repo INSIDE your repo
git submodule add https://github.com/user/library.git libs/library

# Clone a repo that has submodules
git clone --recurse-submodules https://github.com/user/project.git

# OR after cloning:
git submodule init
git submodule update

# Update submodule to latest
cd libs/library
git pull origin main
cd ../..
git add libs/library
git commit -m "Update library submodule"
```

---

### 📌 More GitHub Features

```
┌─────────────────────────────────────────────────────────┐
│  FEATURE              │  USE CASE                       │
├───────────────────────┼─────────────────────────────────┤
│  GitHub Pages         │  Free static website hosting    │
│  GitHub Gists         │  Share code snippets            │
│  GitHub Packages      │  Host npm/pip/docker packages   │
│  GitHub Codespaces    │  Cloud-based VS Code (dev env)  │
│  GitHub Sponsors      │  Get paid for open source work  │
│  GitHub Copilot       │  AI pair programmer             │
│  GitHub Security      │  Dependabot, secret scanning    │
│  GitHub Models        │  AI model hosting/inference     │
│  GitHub Marketplace   │  Apps & Actions for your repos  │
│  GitHub Education     │  Student Developer Pack (FREE!) │
└───────────────────────┴─────────────────────────────────┘
```

#### GitHub Pages (Deploy Free Website):
```bash
# Method 1: From main branch /docs folder
# Method 2: From gh-pages branch
# Method 3: Using GitHub Actions

# Quick setup:
# 1. Create repo: username.github.io
# 2. Add index.html
# 3. Push to main
# 4. Visit: https://username.github.io 🎉

# For project sites:
# Repo Settings → Pages → Source → Deploy from branch
# URL: https://username.github.io/repo-name/
```

#### 🎓 GitHub Student Developer Pack:
```
FREE tools worth $200,000+:
  → GitHub Pro (free)
  → JetBrains IDEs (free)
  → Namecheap (.me domain free)
  → DigitalOcean credits ($200)
  → Azure credits ($100)
  → MongoDB Atlas credits
  → Canva Pro
  → And 80+ more tools!

Apply at: education.github.com/pack
Need: College email or ID card
```

---

## 📋 BEST PRACTICES SUMMARY

### Commit Messages:
```
FORMAT:
  <type>: <short description>

  [optional body — explain WHY, not WHAT]

  [optional footer — references, breaking changes]

TYPES:
  feat:     New feature
  fix:      Bug fix
  docs:     Documentation only
  style:    Formatting (no code change)
  refactor: Code restructuring (no feature/fix)
  test:     Adding tests
  chore:    Build/tooling changes

EXAMPLES:
  ✅ feat: add user authentication with JWT
  ✅ fix: resolve null pointer in search function
  ✅ docs: update API documentation for v2 endpoints
  
  ❌ "fixed stuff"
  ❌ "update"
  ❌ "asdfgh"
  ❌ "final commit"
```

### Branch Naming:
```
FORMAT: <type>/<short-description>

EXAMPLES:
  feature/user-auth
  bugfix/login-crash
  hotfix/security-patch
  docs/api-readme
  refactor/database-schema
  test/payment-flow

❌ Avoid: "my-branch", "test123", "asdf"
```

### PR Guidelines:
```
✅ Keep PRs small and focused (one feature/fix per PR)
✅ Write descriptive title and body
✅ Link related issues (Closes #42)
✅ Add screenshots for UI changes
✅ Self-review before requesting review
✅ Respond to review comments promptly
✅ Don't force push after review started
```

### Clean Git History:
```
✅ Use meaningful commit messages
✅ Squash WIP commits before merging
✅ Rebase feature branches on main before PR
✅ Don't commit generated/build files
✅ Use .gitignore properly
✅ One logical change per commit
```

---

## 🎯 COMPLETE WEEK-BY-WEEK PLAN

```
┌──────────┬────────────────────────────────────────────────┬─────────────┐
│  WEEK    │  TOPICS                                       │  MILESTONE  │
├──────────┼────────────────────────────────────────────────┼─────────────┤
│  Week 1  │  Git basics, init, add, commit, log,          │  First      │
│          │  .gitignore, config                           │  local repo │
├──────────┼────────────────────────────────────────────────┼─────────────┤
│  Week 2  │  Branching, merging, conflicts,               │  Branch &   │
│          │  cherry-pick, merge strategies                │  merge      │
├──────────┼────────────────────────────────────────────────┼─────────────┤
│  Week 3  │  GitHub setup, remotes, push/pull/fetch,      │  First push │
│          │  clone, SSH, profile README                   │  to GitHub  │
├──────────┼────────────────────────────────────────────────┼─────────────┤
│  Week 4  │  Fork, clone, PRs, issues, labels,           │  First open │
│          │  collaboration, code review                   │  source PR  │
├──────────┼────────────────────────────────────────────────┼─────────────┤
│  Week 5  │  Stash, reset, revert, rebase, tags,         │  Clean Git  │
│          │  diffs, hooks, amend                          │  workflow   │
├──────────┼────────────────────────────────────────────────┼─────────────┤
│  Week 6  │  GitHub Actions, CI/CD, CLI,                  │  Automated  │
│          │  Projects, Organizations                      │  pipeline   │
├──────────┼────────────────────────────────────────────────┼─────────────┤
│  Week 7  │  Reflog, bisect, worktree, LFS,              │  Advanced   │
│          │  submodules, patches                          │  commands   │
├──────────┼────────────────────────────────────────────────┼─────────────┤
│  Week 8  │  Pages, Codespaces, Security,                │  Full       │
│          │  API, best practices consolidation            │  mastery    │
└──────────┴────────────────────────────────────────────────┴─────────────┘
```

---

## 📚 Best Resources

| Resource | Type | Best For |
|---|---|---|
| [Pro Git Book](https://git-scm.com/book) (free) | 📖 Book | Comprehensive reference |
| Kunal Kushwaha — Git & GitHub | 🎥 YouTube | Beginner (Hindi) |
| The Net Ninja — Git & GitHub | 🎥 YouTube | Beginner (English) |
| Fireship — Git in 100 Seconds | 🎥 YouTube | Quick overview |
| Atlassian Git Tutorials | 📝 Blog | In-depth explanations |
| [learngitbranching.js.org](https://learngitbranching.js.org) | 🎮 Interactive | Visual branch practice |
| GitHub Skills (skills.github.com) | 🎮 Interactive | GitHub-specific |
| Oh My Git! | 🎮 Game | Fun visual learning |
| CodeWithHarry — Git Tutorial (Hindi) | 🎥 YouTube | Hindi, beginner |
| [gitimmersion.com](https://gitimmersion.com) | 🎮 Interactive | Step-by-step lab |

---

## 💼 How This Looks on Resume

```
SKILLS:
  Version Control: Git, GitHub (Actions, Projects, Pages)

PROJECT BULLET POINTS:
  • Collaborated with 5+ developers using Git branching 
    strategy and pull request workflows
  • Set up CI/CD pipeline using GitHub Actions, reducing 
    manual deployment time by 80%
  • Maintained clean Git history with conventional commits 
    and interactive rebasing
  • Contributed to 3 open source projects with 10+ 
    merged pull requests

INTERVIEW TALKING POINTS:
  "I use feature branches, write conventional commit messages,
   squash before merging, and set up automated testing with 
   GitHub Actions."
```


