# THE ULTIMATE NEXT.JS MASTERY ROADMAP

**From Zero to Production-Ready Next.js Developer in 4-5 Months**

*Every concept, every feature, every tool — nothing skipped*

---

## TABLE OF CONTENTS

```
PART 1:   What is Next.js & Why It Exists
PART 2:   Prerequisites Checklist
PART 3:   Next.js Fundamentals — Setup & Routing (Week 1-2)
PART 4:   Rendering Strategies — SSR, SSG, ISR, CSR (Week 3-4)
PART 5:   Data Fetching & Server Components (Week 5-6)
PART 6:   API Routes & Route Handlers (Week 7-8)
PART 7:   Styling, Fonts & Assets (Week 9)
PART 8:   Authentication in Next.js (Week 10-11)
PART 9:   Database Integration (Week 12-13)
PART 10:  Advanced Next.js Features (Week 14-15)
PART 11:  State Management & Forms (Week 16)
PART 12:  Testing & Performance (Week 17)
PART 13:  Deployment & DevOps (Week 18)
PART 14:  Build 8 Next.js Projects
PART 15:  GitHub Repos + YouTube + Resources
PART 16:  Day-by-Day 30-Day Kickstart Plan
PART 17:  Interview Preparation (Next.js Specific)
PART 18:  What Comes After Next.js
```

---

## PART 1: WHAT IS NEXT.JS & WHY IT EXISTS

### 1.1 The Next.js Architecture

```
HOW A NEXT.JS APP WORKS:

USER (Browser)                     NEXT.JS SERVER                    DATABASE
                                                                      
  React UI        HTTP Request      Node.js Runtime                   
  (Frontend)  ──────────────►      + React Server     Query    ┌─────────────┐
                                    Components    ──────────►  │  PostgreSQL  │
              ◄──────────────       + API Routes               │  MongoDB     │
  - Pages          HTML/JSON        + Middleware               │  Prisma ORM  │
  - Components     Response         + Edge Runtime             └─────────────┘
  - Interactivity                                              
                                                               
PORT 3000                         SAME SERVER                  PORT 5432/27017
```

### WHAT IS NEXT.JS:

```
Next.js is a REACT FRAMEWORK (not just a library) built by Vercel.

React = Library (gives you building blocks)
Next.js = Framework (gives you the complete house)

WHAT REACT GIVES YOU:
  ✓ Components
  ✓ State management (useState, useContext)
  ✓ Virtual DOM
  ✗ No routing (need react-router-dom)
  ✗ No SSR/SSG built-in
  ✗ No API routes
  ✗ No image optimization
  ✗ No code splitting setup
  ✗ No SEO optimization

WHAT NEXT.JS ADDS ON TOP OF REACT:
  ✓ File-based routing (no react-router needed!)
  ✓ Server-Side Rendering (SSR)
  ✓ Static Site Generation (SSG)
  ✓ Incremental Static Regeneration (ISR)
  ✓ API Routes (backend in same project!)
  ✓ React Server Components (RSC)
  ✓ Image optimization (<Image />)
  ✓ Font optimization (next/font)
  ✓ Built-in code splitting & lazy loading
  ✓ Middleware (edge functions)
  ✓ Built-in SEO support (metadata API)
  ✓ Streaming & Suspense
  ✓ Server Actions (mutations without API)
  ✓ Parallel & Intercepting Routes
  ✓ Built-in TypeScript support
  ✓ Turbopack (super fast bundler)

WHY NEXT.JS IS SPECIAL:
  - Full-stack in ONE project (no separate backend)
  - Best SEO of any React solution
  - Fastest performance out of the box
  - Used by: Netflix, Uber, TikTok, Nike, Twitch, Notion, Hulu
  - Created & maintained by Vercel (billions in funding)
  - THE most in-demand React skill in 2024-2025
  - Deploys seamlessly on Vercel (free tier)
```

### 1.2 Rendering Strategies Overview

```
NEXT.JS RENDERING — THE KEY DIFFERENTIATOR:

1. CSR (Client-Side Rendering) — Traditional React
   Browser downloads empty HTML → JS runs → Renders UI
   ❌ Bad SEO, slow initial load
   ✅ Great for dashboards, admin panels

2. SSR (Server-Side Rendering) — On every request
   Server renders HTML → Sends complete HTML to browser
   ✅ Great SEO, fresh data
   ❌ Slower TTFB (Time To First Byte), server load

3. SSG (Static Site Generation) — At build time
   HTML generated once during build → Served as static files
   ✅ Fastest, great SEO, CDN cacheable
   ❌ Data can be stale

4. ISR (Incremental Static Regeneration) — Best of both
   Static pages that revalidate after a time period
   ✅ Fast + fresh data, great SEO
   ✅ Best for most use cases

5. RSC (React Server Components) — Next.js 13+ default
   Components render on server, send HTML (no JS bundle)
   ✅ Smaller bundle, faster, direct DB access
   ✅ The future of React

WHEN TO USE WHAT:
┌─────────────────────┬──────────────────────────────┐
│ Strategy            │ Use Case                     │
├─────────────────────┼──────────────────────────────┤
│ SSG                 │ Blog, docs, marketing pages  │
│ SSR                 │ Social feed, real-time data  │
│ ISR                 │ E-commerce, news, most apps  │
│ CSR                 │ Dashboards, admin panels     │
│ RSC (Server Comp)   │ Default for everything!      │
└─────────────────────┴──────────────────────────────┘
```

### 1.3 Folder Structure (App Router — Next.js 13+)

```
my-nextjs-app/
├── app/                        ← APP ROUTER (Main)
│   ├── layout.tsx              ← Root layout (wraps ALL pages)
│   ├── page.tsx                ← Home page (/)
│   ├── loading.tsx             ← Loading UI for /
│   ├── error.tsx               ← Error UI for /
│   ├── not-found.tsx           ← 404 page
│   ├── globals.css             ← Global styles
│   │
│   ├── about/
│   │   └── page.tsx            ← /about
│   │
│   ├── blog/
│   │   ├── page.tsx            ← /blog
│   │   └── [slug]/
│   │       └── page.tsx        ← /blog/my-post (dynamic)
│   │
│   ├── dashboard/
│   │   ├── layout.tsx          ← Dashboard layout
│   │   ├── page.tsx            ← /dashboard
│   │   ├── settings/
│   │   │   └── page.tsx        ← /dashboard/settings
│   │   └── analytics/
│   │       └── page.tsx        ← /dashboard/analytics
│   │
│   ├── api/                    ← API ROUTES (Backend)
│   │   ├── users/
│   │   │   └── route.ts        ← GET/POST /api/users
│   │   ├── posts/
│   │   │   ├── route.ts        ← GET/POST /api/posts
│   │   │   └── [id]/
│   │   │       └── route.ts    ← GET/PUT/DELETE /api/posts/:id
│   │   └── auth/
│   │       └── [...nextauth]/
│   │           └── route.ts    ← NextAuth catch-all
│   │
│   └── (auth)/                 ← Route group (no URL impact)
│       ├── login/
│       │   └── page.tsx        ← /login
│       └── register/
│           └── page.tsx        ← /register
│
├── components/                 ← Reusable components
│   ├── ui/
│   │   ├── Button.tsx
│   │   ├── Card.tsx
│   │   ├── Modal.tsx
│   │   └── Spinner.tsx
│   ├── layout/
│   │   ├── Navbar.tsx
│   │   ├── Footer.tsx
│   │   └── Sidebar.tsx
│   └── forms/
│       ├── LoginForm.tsx
│       └── PostForm.tsx
│
├── lib/                        ← Utility functions & configs
│   ├── db.ts                   ← Database connection
│   ├── auth.ts                 ← Auth configuration
│   ├── utils.ts                ← Helper functions
│   └── validations.ts          ← Zod schemas
│
├── actions/                    ← Server Actions
│   ├── auth.ts
│   ├── posts.ts
│   └── users.ts
│
├── hooks/                      ← Custom React hooks
│   ├── useAuth.ts
│   └── useDebounce.ts
│
├── types/                      ← TypeScript types
│   └── index.ts
│
├── public/                     ← Static files
│   ├── images/
│   ├── favicon.ico
│   └── robots.txt
│
├── prisma/                     ← Prisma ORM (if using)
│   └── schema.prisma
│
├── middleware.ts                ← Edge middleware
├── next.config.js              ← Next.js configuration
├── tailwind.config.ts          ← Tailwind CSS config
├── tsconfig.json               ← TypeScript config
├── .env.local                  ← Environment variables
├── .gitignore
├── package.json
└── README.md
```

---

## PART 2: PREREQUISITES CHECKLIST

```
BEFORE STARTING NEXT.JS, YOU MUST KNOW:

HTML ✅ (7/10 minimum):
  All tags, forms, semantic HTML

CSS ✅ (7/10 minimum):
  Flexbox, Grid, responsive design
  Tailwind CSS basics (recommended but not required)

JavaScript ✅ (8/10 minimum — CRITICAL):
  ✅ Variables (let, const), data types
  ✅ Functions (arrow, callbacks, closures)
  ✅ Arrays (map, filter, reduce, forEach, find)
  ✅ Objects (destructuring, spread, methods)
  ✅ Async/Await, Promises, Fetch API
  ✅ ES6+ (classes, modules, template literals)
  ✅ Error handling (try/catch)
  ✅ JSON (parse, stringify)

React ✅ (8/10 minimum — CRITICAL):
  ✅ Components (functional)
  ✅ Props & Children
  ✅ useState, useEffect, useRef
  ✅ useContext
  ✅ useReducer (helpful)
  ✅ Custom hooks
  ✅ Conditional rendering
  ✅ Lists & keys
  ✅ Forms (controlled components)
  ✅ React Router basics (understand concepts)

TypeScript ✅ (6/10 minimum — RECOMMENDED):
  ✅ Basic types (string, number, boolean)
  ✅ Interfaces & type aliases
  ✅ Generics basics
  ✅ Function types
  ✅ Union & intersection types
  If weak: Learn alongside Next.js (it's integrated)

Node.js ✅ (5/10 minimum):
  ✅ What it is, how it works
  ✅ npm basics
  ✅ Modules (import/export)
  ✅ Environment variables
  If weak: You'll learn more during API routes

Git & GitHub ✅:
  git init, add, commit, push, pull
  Branching basics

IF REACT IS WEAK → Go back to React first.
Next.js without strong React = Building on sand.
```

---

## PART 3: NEXT.JS FUNDAMENTALS — SETUP & ROUTING (Week 1-2)

### WEEK 1: SETUP & FILE-BASED ROUTING

### 3.1 Project Setup

```bash
# ✅ CREATE NEXT.JS PROJECT (always use this):
npx create-next-app@latest my-app

# It will ask:
# ✔ Would you like to use TypeScript? → YES ✅
# ✔ Would you like to use ESLint? → YES ✅
# ✔ Would you like to use Tailwind CSS? → YES ✅
# ✔ Would you like to use `src/` directory? → No (preference)
# ✔ Would you like to use App Router? → YES ✅ (IMPORTANT!)
# ✔ Would you like to customize import alias? → YES (@/*)

cd my-app
npm run dev
# Opens on http://localhost:3000
```

```typescript
// ✅ UNDERSTANDING THE KEY FILES:

// app/layout.tsx — ROOT LAYOUT (wraps EVERY page)
import type { Metadata } from 'next';
import { Inter } from 'next/font/google';
import './globals.css';

const inter = Inter({ subsets: ['latin'] });

export const metadata: Metadata = {
  title: 'My Next.js App',
  description: 'Built with Next.js 14',
};

export default function RootLayout({
  children,
}: {
  children: React.ReactNode;
}) {
  return (
    <html lang="en">
      <body className={inter.className}>
        {/* Navbar goes here — shows on ALL pages */}
        <nav>My App</nav>
        <main>{children}</main>
        {/* Footer goes here */}
        <footer>© 2025</footer>
      </body>
    </html>
  );
}

// app/page.tsx — HOME PAGE (/)
export default function HomePage() {
  return (
    <div>
      <h1>Welcome to Next.js!</h1>
      <p>This is the home page</p>
    </div>
  );
}
```

### 3.2 File-Based Routing (THE Core of Next.js)

```typescript
// ✅ ROUTING = FOLDER STRUCTURE

// app/page.tsx            →  /
// app/about/page.tsx      →  /about
// app/contact/page.tsx    →  /contact
// app/blog/page.tsx       →  /blog
// app/blog/[slug]/page.tsx → /blog/my-first-post (dynamic)
// app/shop/[...slug]/page.tsx → /shop/a/b/c (catch-all)

// ✅ STATIC ROUTES
// app/about/page.tsx:
export default function AboutPage() {
  return <h1>About Us</h1>;
}

// app/services/page.tsx:
export default function ServicesPage() {
  return <h1>Our Services</h1>;
}

// app/pricing/page.tsx:
export default function PricingPage() {
  return <h1>Pricing</h1>;
}

// ✅ DYNAMIC ROUTES ⭐
// app/blog/[slug]/page.tsx:
interface BlogPostPageProps {
  params: { slug: string };
}

export default function BlogPostPage({ params }: BlogPostPageProps) {
  return <h1>Blog Post: {params.slug}</h1>;
}
// /blog/hello-world → params.slug = "hello-world"
// /blog/nextjs-guide → params.slug = "nextjs-guide"

// ✅ MULTIPLE DYNAMIC SEGMENTS
// app/shop/[category]/[productId]/page.tsx:
interface ProductPageProps {
  params: { category: string; productId: string };
}

export default function ProductPage({ params }: ProductPageProps) {
  return (
    <div>
      <h1>Category: {params.category}</h1>
      <p>Product ID: {params.productId}</p>
    </div>
  );
}
// /shop/electronics/123 → category="electronics", productId="123"

// ✅ CATCH-ALL ROUTES
// app/docs/[...slug]/page.tsx:
interface DocsPageProps {
  params: { slug: string[] };
}

export default function DocsPage({ params }: DocsPageProps) {
  return <h1>Docs: {params.slug.join(' / ')}</h1>;
}
// /docs/getting-started → slug = ["getting-started"]
// /docs/api/reference/auth → slug = ["api", "reference", "auth"]

// ✅ OPTIONAL CATCH-ALL ROUTES
// app/docs/[[...slug]]/page.tsx:
// Also matches /docs (without any segments)

// ✅ SEARCH PARAMS (Query Parameters)
// app/search/page.tsx:
interface SearchPageProps {
  searchParams: { q?: string; page?: string; sort?: string };
}

export default function SearchPage({ searchParams }: SearchPageProps) {
  const query = searchParams.q || '';
  const page = parseInt(searchParams.page || '1');
  
  return (
    <div>
      <h1>Search results for: {query}</h1>
      <p>Page: {page}</p>
    </div>
  );
}
// /search?q=nextjs&page=2 → q="nextjs", page="2"
```

### 3.3 Layouts, Templates & Special Files

```typescript
// ✅ LAYOUTS (Shared UI between pages) ⭐⭐⭐
// Layouts PERSIST across page navigations (don't re-render!)

// app/layout.tsx — ROOT LAYOUT (required, wraps everything):
export default function RootLayout({ children }: { children: React.ReactNode }) {
  return (
    <html lang="en">
      <body>
        <Navbar />
        {children}
        <Footer />
      </body>
    </html>
  );
}

// app/dashboard/layout.tsx — NESTED LAYOUT:
export default function DashboardLayout({ children }: { children: React.ReactNode }) {
  return (
    <div className="flex">
      <Sidebar /> {/* Shows on all /dashboard/* pages */}
      <main className="flex-1 p-6">{children}</main>
    </div>
  );
}
// Result: /dashboard → RootLayout > DashboardLayout > page
// Result: /dashboard/settings → RootLayout > DashboardLayout > page

// ✅ TEMPLATES (Like layouts, but RE-MOUNT on navigation)
// app/dashboard/template.tsx:
export default function DashboardTemplate({ children }: { children: React.ReactNode }) {
  return <div>{children}</div>;  // Re-creates state on every navigation
}
// Use when: You need fresh state on each page, animations on enter

// ✅ LOADING.TSX (Automatic loading UI) ⭐
// app/dashboard/loading.tsx:
export default function Loading() {
  return (
    <div className="flex items-center justify-center h-screen">
      <div className="animate-spin rounded-full h-12 w-12 border-b-2 border-blue-500" />
      <p className="ml-3">Loading...</p>
    </div>
  );
}
// Next.js automatically shows this while page.tsx is loading!
// Works with React Suspense under the hood

// ✅ ERROR.TSX (Error boundary) ⭐
// app/dashboard/error.tsx:
'use client'; // Error components MUST be Client Components

import { useEffect } from 'react';

export default function Error({
  error,
  reset,
}: {
  error: Error & { digest?: string };
  reset: () => void;
}) {
  useEffect(() => {
    console.error(error);
  }, [error]);

  return (
    <div className="text-center py-10">
      <h2 className="text-2xl font-bold text-red-500">Something went wrong!</h2>
      <p className="text-gray-600 mt-2">{error.message}</p>
      <button
        onClick={reset}
        className="mt-4 px-4 py-2 bg-blue-500 text-white rounded"
      >
        Try again
      </button>
    </div>
  );
}

// ✅ NOT-FOUND.TSX (Custom 404)
// app/not-found.tsx:
import Link from 'next/link';

export default function NotFound() {
  return (
    <div className="text-center py-20">
      <h2 className="text-4xl font-bold">404</h2>
      <p className="text-gray-600 mt-2">Page not found</p>
      <Link href="/" className="text-blue-500 underline mt-4 inline-block">
        Go home
      </Link>
    </div>
  );
}

// Trigger programmatically:
import { notFound } from 'next/navigation';

export default async function BlogPost({ params }: { params: { slug: string } }) {
  const post = await getPost(params.slug);
  
  if (!post) {
    notFound(); // ← Shows the not-found.tsx component
  }
  
  return <article>{post.title}</article>;
}
```

### 3.4 Navigation

```typescript
// ✅ LINK COMPONENT (Client-side navigation — NO full page reload!) ⭐
import Link from 'next/link';

export default function Navbar() {
  return (
    <nav className="flex gap-4 p-4 bg-gray-800 text-white">
      <Link href="/">Home</Link>
      <Link href="/about">About</Link>
      <Link href="/blog">Blog</Link>
      <Link href="/dashboard" prefetch={false}>Dashboard</Link>
      
      {/* Dynamic links */}
      <Link href={`/blog/${post.slug}`}>Read Post</Link>
      <Link href={{ pathname: '/search', query: { q: 'nextjs' } }}>Search</Link>
      
      {/* With styles */}
      <Link 
        href="/contact" 
        className="bg-blue-500 px-4 py-2 rounded hover:bg-blue-600"
      >
        Contact
      </Link>
      
      {/* Replace instead of push (no back button) */}
      <Link href="/login" replace>Login</Link>
      
      {/* Scroll to top disabled */}
      <Link href="/posts" scroll={false}>Posts</Link>
    </nav>
  );
}

// ✅ ACTIVE LINKS (NavLink equivalent)
'use client';
import Link from 'next/link';
import { usePathname } from 'next/navigation';

export default function NavLink({ href, children }: { href: string; children: React.ReactNode }) {
  const pathname = usePathname();
  const isActive = pathname === href;

  return (
    <Link
      href={href}
      className={`px-3 py-2 rounded ${
        isActive ? 'bg-blue-500 text-white' : 'text-gray-600 hover:text-gray-900'
      }`}
    >
      {children}
    </Link>
  );
}

// ✅ PROGRAMMATIC NAVIGATION ⭐
'use client';
import { useRouter } from 'next/navigation';

export default function LoginForm() {
  const router = useRouter();

  const handleLogin = async () => {
    // ... login logic
    router.push('/dashboard');        // Navigate to route
    router.replace('/dashboard');     // Replace current in history
    router.back();                    // Go back
    router.forward();                 // Go forward
    router.refresh();                 // Refresh current route (re-fetch data)
    router.prefetch('/dashboard');    // Prefetch a route
  };

  return <button onClick={handleLogin}>Login</button>;
}

// ✅ REDIRECT (Server-side) ⭐
import { redirect } from 'next/navigation';

export default async function ProtectedPage() {
  const session = await getSession();
  
  if (!session) {
    redirect('/login'); // ← Server-side redirect (works in Server Components!)
  }
  
  return <Dashboard user={session.user} />;
}

// ✅ PERMANENT REDIRECT
import { permanentRedirect } from 'next/navigation';
permanentRedirect('/new-url'); // 308 status code
```

### 3.5 Route Groups & Parallel Routes

```typescript
// ✅ ROUTE GROUPS — Organize without affecting URL ⭐
// Wrap folder name in parentheses: (groupName)

// app/(marketing)/page.tsx       → /
// app/(marketing)/about/page.tsx → /about
// app/(marketing)/layout.tsx     → Marketing layout

// app/(dashboard)/dashboard/page.tsx    → /dashboard
// app/(dashboard)/dashboard/layout.tsx  → Dashboard layout

// app/(auth)/login/page.tsx      → /login
// app/(auth)/register/page.tsx   → /register
// app/(auth)/layout.tsx          → Auth layout (centered form)

// WHY? Different layouts for different sections!
// Marketing pages: Navbar + Footer
// Dashboard pages: Sidebar + Header
// Auth pages: Centered card

// ✅ PARALLEL ROUTES (Render multiple pages simultaneously)
// app/@analytics/page.tsx
// app/@team/page.tsx
// app/layout.tsx:
export default function Layout({
  children,
  analytics,
  team,
}: {
  children: React.ReactNode;
  analytics: React.ReactNode;
  team: React.ReactNode;
}) {
  return (
    <div>
      {children}
      <div className="grid grid-cols-2 gap-4">
        {analytics}
        {team}
      </div>
    </div>
  );
}

// ✅ INTERCEPTING ROUTES (Modal pattern)
// Show a modal when navigating, full page on direct URL
// app/feed/page.tsx                    → Feed page
// app/feed/@modal/(.)photo/[id]/page.tsx → Modal overlay
// app/photo/[id]/page.tsx              → Full photo page

// (.) = same level, (..) = one level up, (...) = root
```

---

## PART 4: RENDERING STRATEGIES (Week 3-4)

### 4.1 Server Components vs Client Components ⭐⭐⭐

```typescript
// ✅ SERVER COMPONENTS (Default in Next.js 13+) ⭐⭐⭐
// Every component is a Server Component by default!

// WHAT SERVER COMPONENTS CAN DO:
// ✅ Fetch data directly (async/await)
// ✅ Access backend resources (DB, filesystem)
// ✅ Keep secrets on server (API keys)
// ✅ Reduce client JS bundle
// ✅ Use Node.js APIs

// WHAT SERVER COMPONENTS CANNOT DO:
// ❌ useState, useEffect, useRef (no hooks!)
// ❌ onClick, onChange (no event handlers!)
// ❌ Browser APIs (window, document, localStorage)
// ❌ Class components

// app/users/page.tsx — SERVER COMPONENT (default):
import { prisma } from '@/lib/db';

export default async function UsersPage() {
  // ✅ Direct database access — no API needed!
  const users = await prisma.user.findMany();
  
  // ✅ Access environment variables (secrets)
  const apiKey = process.env.SECRET_API_KEY;
  
  return (
    <div>
      <h1>Users ({users.length})</h1>
      {users.map(user => (
        <div key={user.id}>{user.name} - {user.email}</div>
      ))}
    </div>
  );
}
// This component sends ZERO JavaScript to the browser!
// Only HTML is sent. Super fast! ⚡

// ✅ CLIENT COMPONENTS (opt-in with 'use client') ⭐⭐⭐
// Add 'use client' directive at the TOP of the file

'use client'; // ← This makes it a Client Component

import { useState, useEffect } from 'react';

export default function Counter() {
  const [count, setCount] = useState(0); // ✅ Can use hooks now
  
  return (
    <div>
      <p>Count: {count}</p>
      <button onClick={() => setCount(count + 1)}>+</button> {/* ✅ Event handlers */}
    </div>
  );
}

// ✅ THE GOLDEN RULE: WHEN TO USE WHICH? ⭐⭐⭐
// 
// Server Component (default):
//   - Fetching data
//   - Accessing backend (DB, filesystem)
//   - Displaying content (no interactivity)
//   - Using server-only packages
//
// Client Component ('use client'):
//   - useState, useEffect, useRef (any hook)
//   - onClick, onChange (any event handler)
//   - Browser APIs (window, localStorage)
//   - Interactive UI (forms, buttons, modals)
//   - Third-party client libraries (charting, maps)

// ✅ COMPOSITION PATTERN ⭐⭐⭐ (Server + Client together)
// BEST PRACTICE: Keep Server Components at the top,
// push Client Components to the LEAVES of the tree

// app/dashboard/page.tsx (SERVER):
import { getAnalytics } from '@/lib/data';
import Chart from '@/components/Chart';        // Client Component
import StatsCards from '@/components/StatsCards'; // Server Component

export default async function DashboardPage() {
  const data = await getAnalytics(); // ✅ Fetch on server
  
  return (
    <div>
      <StatsCards data={data.stats} />     {/* Server Component */}
      <Chart chartData={data.chartData} /> {/* Client Component (interactive) */}
    </div>
  );
}

// components/Chart.tsx (CLIENT — needs interactivity):
'use client';
import { useState } from 'react';

export default function Chart({ chartData }: { chartData: number[] }) {
  const [timeRange, setTimeRange] = useState('7d');
  // ... interactive chart
  return <div>Chart with {chartData.length} points</div>;
}

// components/StatsCards.tsx (SERVER — no interactivity):
export default function StatsCards({ data }: { data: Stats }) {
  return (
    <div className="grid grid-cols-4 gap-4">
      <div>Revenue: ${data.revenue}</div>
      <div>Users: {data.users}</div>
    </div>
  );
}
```

### 4.2 Static vs Dynamic Rendering

```typescript
// ✅ STATIC RENDERING (Default — at build time)
// Pages with no dynamic data are automatically static

// This page is STATIC (rendered at build time):
export default function AboutPage() {
  return <h1>About Us</h1>; // No data fetching = static
}

// ✅ DYNAMIC RENDERING (At request time)
// Next.js automatically switches to dynamic when you use:
// - Dynamic functions: cookies(), headers(), searchParams
// - Uncached data fetching

// This page is DYNAMIC (rendered per request):
import { cookies } from 'next/headers';

export default async function ProfilePage() {
  const cookieStore = cookies();
  const theme = cookieStore.get('theme');
  
  return <div>Theme: {theme?.value}</div>;
}

// ✅ FORCE STATIC OR DYNAMIC
// Force static:
export const dynamic = 'force-static';       // Always static
export const revalidate = 3600;               // ISR: revalidate every hour

// Force dynamic:
export const dynamic = 'force-dynamic';       // Always server-rendered
export const revalidate = 0;                  // No caching

// ✅ generateStaticParams (SSG for dynamic routes) ⭐
// Pre-render dynamic pages at build time

// app/blog/[slug]/page.tsx:
export async function generateStaticParams() {
  const posts = await fetch('https://api.example.com/posts').then(r => r.json());
  
  return posts.map((post: { slug: string }) => ({
    slug: post.slug,
  }));
}
// This pre-generates pages for ALL blog slugs at build time!
// /blog/first-post, /blog/second-post, etc.

export default async function BlogPost({ params }: { params: { slug: string } }) {
  const post = await getPost(params.slug);
  return <article><h1>{post.title}</h1><p>{post.content}</p></article>;
}
```

---

## PART 5: DATA FETCHING & SERVER COMPONENTS (Week 5-6)

### 5.1 Data Fetching in Server Components ⭐⭐⭐

```typescript
// ✅ FETCHING DATA IN SERVER COMPONENTS
// Next.js extends the native fetch() with caching & revalidation

// app/posts/page.tsx:

// 1. DEFAULT — Cached (like SSG) ⭐
async function getPosts() {
  const res = await fetch('https://api.example.com/posts');
  // Next.js caches this by default!
  
  if (!res.ok) throw new Error('Failed to fetch posts');
  return res.json();
}

// 2. REVALIDATE — ISR (cached + refreshed periodically) ⭐
async function getPosts() {
  const res = await fetch('https://api.example.com/posts', {
    next: { revalidate: 3600 }, // Revalidate every hour
  });
  return res.json();
}

// 3. NO CACHE — SSR (fresh on every request) ⭐
async function getPosts() {
  const res = await fetch('https://api.example.com/posts', {
    cache: 'no-store', // Always fresh
  });
  return res.json();
}

// 4. TAGS — On-demand revalidation ⭐⭐
async function getPosts() {
  const res = await fetch('https://api.example.com/posts', {
    next: { tags: ['posts'] }, // Tag for on-demand revalidation
  });
  return res.json();
}

// Revalidate by tag (in Server Action or Route Handler):
import { revalidateTag } from 'next/cache';
revalidateTag('posts'); // All fetches with 'posts' tag are revalidated!

// Revalidate by path:
import { revalidatePath } from 'next/cache';
revalidatePath('/posts'); // Revalidate the /posts page

// ✅ USING THE DATA IN PAGES
export default async function PostsPage() {
  const posts = await getPosts(); // ✅ Async/await in component!

  return (
    <div className="grid gap-4">
      <h1>Blog Posts</h1>
      {posts.map((post: Post) => (
        <article key={post.id} className="border p-4 rounded">
          <h2 className="text-xl font-bold">{post.title}</h2>
          <p className="text-gray-600">{post.excerpt}</p>
        </article>
      ))}
    </div>
  );
}

// ✅ DIRECT DATABASE QUERIES (No API needed!) ⭐⭐⭐
import { prisma } from '@/lib/db';

export default async function UsersPage() {
  const users = await prisma.user.findMany({
    include: { posts: true },
    orderBy: { createdAt: 'desc' },
    take: 10,
  });

  return (
    <ul>
      {users.map(user => (
        <li key={user.id}>
          {user.name} — {user.posts.length} posts
        </li>
      ))}
    </ul>
  );
}
// NO API route needed! Server Component accesses DB directly!

// ✅ PARALLEL DATA FETCHING (Faster!) ⭐
export default async function DashboardPage() {
  // ❌ SLOW — Sequential (waterfall):
  // const users = await getUsers();
  // const posts = await getPosts();
  // const analytics = await getAnalytics();

  // ✅ FAST — Parallel (all at once):
  const [users, posts, analytics] = await Promise.all([
    getUsers(),
    getPosts(),
    getAnalytics(),
  ]);

  return (
    <div>
      <UserList users={users} />
      <PostList posts={posts} />
      <AnalyticsChart data={analytics} />
    </div>
  );
}

// ✅ STREAMING WITH SUSPENSE ⭐⭐
import { Suspense } from 'react';

export default function DashboardPage() {
  return (
    <div>
      <h1>Dashboard</h1>
      
      {/* Show immediately */}
      <WelcomeMessage />
      
      {/* Stream in when ready — shows loading.tsx while waiting */}
      <Suspense fallback={<CardSkeleton />}>
        <RevenueChart /> {/* Slow data fetch */}
      </Suspense>
      
      <Suspense fallback={<TableSkeleton />}>
        <LatestOrders /> {/* Another slow data fetch */}
      </Suspense>
    </div>
  );
}

// RevenueChart is an async Server Component:
async function RevenueChart() {
  const data = await getRevenue(); // Takes 3 seconds
  return <Chart data={data} />;
}
// User sees the page immediately with skeletons,
// then charts stream in as they load! ⚡
```

### 5.2 Server Actions ⭐⭐⭐ (Mutations without API Routes)

```typescript
// ✅ SERVER ACTIONS — Call server functions directly from components!
// No need to create API routes for mutations!

// Option 1: Inline Server Action
// app/posts/new/page.tsx:
export default function NewPostPage() {
  
  async function createPost(formData: FormData) {
    'use server'; // ← This makes it a Server Action!
    
    const title = formData.get('title') as string;
    const content = formData.get('content') as string;
    
    await prisma.post.create({
      data: { title, content },
    });
    
    revalidatePath('/posts');
    redirect('/posts');
  }
  
  return (
    <form action={createPost}> {/* ← form action = Server Action! */}
      <input name="title" placeholder="Title" required />
      <textarea name="content" placeholder="Content" required />
      <button type="submit">Create Post</button>
    </form>
  );
}

// Option 2: Separate Server Action file (RECOMMENDED) ⭐
// actions/posts.ts:
'use server';

import { prisma } from '@/lib/db';
import { revalidatePath } from 'next/cache';
import { redirect } from 'next/navigation';
import { z } from 'zod';

const PostSchema = z.object({
  title: z.string().min(3).max(100),
  content: z.string().min(10),
});

export async function createPost(formData: FormData) {
  const rawData = {
    title: formData.get('title') as string,
    content: formData.get('content') as string,
  };

  // Validate
  const validatedData = PostSchema.safeParse(rawData);
  if (!validatedData.success) {
    return { error: validatedData.error.flatten().fieldErrors };
  }

  // Create
  await prisma.post.create({ data: validatedData.data });

  revalidatePath('/posts');
  redirect('/posts');
}

export async function deletePost(id: string) {
  await prisma.post.delete({ where: { id } });
  revalidatePath('/posts');
}

export async function toggleLike(postId: string, userId: string) {
  const existingLike = await prisma.like.findFirst({
    where: { postId, userId },
  });

  if (existingLike) {
    await prisma.like.delete({ where: { id: existingLike.id } });
  } else {
    await prisma.like.create({ data: { postId, userId } });
  }

  revalidatePath('/posts');
}

// ✅ USING SERVER ACTIONS IN CLIENT COMPONENTS ⭐
'use client';
import { createPost } from '@/actions/posts';
import { useFormStatus } from 'react-dom';
import { useActionState } from 'react';

// Submit button with loading state:
function SubmitButton() {
  const { pending } = useFormStatus(); // ⭐ Built-in loading state!
  
  return (
    <button type="submit" disabled={pending}>
      {pending ? 'Creating...' : 'Create Post'}
    </button>
  );
}

// Form with Server Action:
export default function CreatePostForm() {
  return (
    <form action={createPost}>
      <input name="title" placeholder="Title" required />
      <textarea name="content" placeholder="Content" required />
      <SubmitButton />
    </form>
  );
}

// ✅ SERVER ACTION WITH useActionState (for error handling) ⭐
'use client';
import { useActionState } from 'react';
import { createPost } from '@/actions/posts';

export default function CreatePostForm() {
  const [state, formAction, isPending] = useActionState(createPost, null);
  
  return (
    <form action={formAction}>
      <input name="title" />
      {state?.error?.title && <p className="text-red-500">{state.error.title}</p>}
      
      <textarea name="content" />
      {state?.error?.content && <p className="text-red-500">{state.error.content}</p>}
      
      <button disabled={isPending}>
        {isPending ? 'Saving...' : 'Create'}
      </button>
    </form>
  );
}

// ✅ SERVER ACTION WITHOUT FORMS (programmatic) ⭐
'use client';
import { deletePost } from '@/actions/posts';
import { useTransition } from 'react';

export default function DeleteButton({ postId }: { postId: string }) {
  const [isPending, startTransition] = useTransition();
  
  const handleDelete = () => {
    startTransition(async () => {
      await deletePost(postId);
    });
  };
  
  return (
    <button onClick={handleDelete} disabled={isPending}>
      {isPending ? 'Deleting...' : 'Delete'}
    </button>
  );
}
```

---

## PART 6: API ROUTES & ROUTE HANDLERS (Week 7-8)

### 6.1 Route Handlers (API Routes in App Router)

```typescript
// ✅ API ROUTES (Route Handlers) ⭐⭐⭐
// Create API endpoints right in your Next.js app!
// File: app/api/[endpoint]/route.ts

// app/api/posts/route.ts:
import { NextRequest, NextResponse } from 'next/server';
import { prisma } from '@/lib/db';

// GET /api/posts
export async function GET(request: NextRequest) {
  try {
    const { searchParams } = new URL(request.url);
    const page = parseInt(searchParams.get('page') || '1');
    const limit = parseInt(searchParams.get('limit') || '10');
    const search = searchParams.get('search') || '';

    const where = search ? {
      OR: [
        { title: { contains: search, mode: 'insensitive' as const } },
        { content: { contains: search, mode: 'insensitive' as const } },
      ],
    } : {};

    const [posts, total] = await Promise.all([
      prisma.post.findMany({
        where,
        include: { author: { select: { name: true, image: true } } },
        orderBy: { createdAt: 'desc' },
        skip: (page - 1) * limit,
        take: limit,
      }),
      prisma.post.count({ where }),
    ]);

    return NextResponse.json({
      data: posts,
      pagination: {
        page,
        limit,
        total,
        pages: Math.ceil(total / limit),
      },
    });
  } catch (error) {
    return NextResponse.json(
      { error: 'Failed to fetch posts' },
      { status: 500 }
    );
  }
}

// POST /api/posts
export async function POST(request: NextRequest) {
  try {
    const body = await request.json();
    const { title, content } = body;

    if (!title || !content) {
      return NextResponse.json(
        { error: 'Title and content are required' },
        { status: 400 }
      );
    }

    const post = await prisma.post.create({
      data: { title, content, authorId: 'user-id' },
    });

    return NextResponse.json(post, { status: 201 });
  } catch (error) {
    return NextResponse.json(
      { error: 'Failed to create post' },
      { status: 500 }
    );
  }
}

// ✅ DYNAMIC API ROUTES
// app/api/posts/[id]/route.ts:
import { NextRequest, NextResponse } from 'next/server';

interface RouteParams {
  params: { id: string };
}

// GET /api/posts/:id
export async function GET(request: NextRequest, { params }: RouteParams) {
  try {
    const post = await prisma.post.findUnique({
      where: { id: params.id },
      include: {
        author: true,
        comments: { include: { author: true } },
      },
    });

    if (!post) {
      return NextResponse.json({ error: 'Post not found' }, { status: 404 });
    }

    return NextResponse.json(post);
  } catch (error) {
    return NextResponse.json({ error: 'Server error' }, { status: 500 });
  }
}

// PUT /api/posts/:id
export async function PUT(request: NextRequest, { params }: RouteParams) {
  try {
    const body = await request.json();

    const post = await prisma.post.update({
      where: { id: params.id },
      data: body,
    });

    return NextResponse.json(post);
  } catch (error) {
    return NextResponse.json({ error: 'Failed to update' }, { status: 500 });
  }
}

// DELETE /api/posts/:id
export async function DELETE(request: NextRequest, { params }: RouteParams) {
  try {
    await prisma.post.delete({ where: { id: params.id } });
    return NextResponse.json({ message: 'Post deleted' });
  } catch (error) {
    return NextResponse.json({ error: 'Failed to delete' }, { status: 500 });
  }
}

// ✅ ACCESSING REQUEST DATA
export async function POST(request: NextRequest) {
  // JSON body:
  const body = await request.json();
  
  // Form data:
  const formData = await request.formData();
  const name = formData.get('name');
  
  // Headers:
  const authHeader = request.headers.get('authorization');
  
  // Cookies:
  const token = request.cookies.get('token');
  
  // Query params:
  const { searchParams } = new URL(request.url);
  const page = searchParams.get('page');
  
  // Set cookies in response:
  const response = NextResponse.json({ success: true });
  response.cookies.set('token', 'abc123', {
    httpOnly: true,
    secure: true,
    maxAge: 60 * 60 * 24 * 30, // 30 days
  });
  
  return response;
}

// ✅ CORS HEADERS
export async function GET() {
  const data = { message: 'Hello' };
  
  return NextResponse.json(data, {
    headers: {
      'Access-Control-Allow-Origin': '*',
      'Access-Control-Allow-Methods': 'GET, POST, PUT, DELETE',
    },
  });
}

// ✅ STREAMING RESPONSE
export async function GET() {
  const encoder = new TextEncoder();
  const stream = new ReadableStream({
    async start(controller) {
      for (let i = 0; i < 10; i++) {
        controller.enqueue(encoder.encode(`data: ${i}\n\n`));
        await new Promise(resolve => setTimeout(resolve, 1000));
      }
      controller.close();
    },
  });
  
  return new Response(stream, {
    headers: { 'Content-Type': 'text/event-stream' },
  });
}
```

### 6.2 Middleware ⭐⭐

```typescript
// ✅ MIDDLEWARE (Runs BEFORE every request)
// middleware.ts (at ROOT of project):

import { NextResponse } from 'next/server';
import type { NextRequest } from 'next/server';

export function middleware(request: NextRequest) {
  const { pathname } = request.nextUrl;
  const token = request.cookies.get('token')?.value;

  // ✅ PROTECT ROUTES
  const protectedPaths = ['/dashboard', '/profile', '/settings'];
  const isProtected = protectedPaths.some(path => pathname.startsWith(path));
  
  if (isProtected && !token) {
    const loginUrl = new URL('/login', request.url);
    loginUrl.searchParams.set('callbackUrl', pathname);
    return NextResponse.redirect(loginUrl);
  }

  // ✅ REDIRECT LOGGED IN USERS FROM AUTH PAGES
  const authPaths = ['/login', '/register'];
  if (authPaths.includes(pathname) && token) {
    return NextResponse.redirect(new URL('/dashboard', request.url));
  }

  // ✅ ADD CUSTOM HEADERS
  const response = NextResponse.next();
  response.headers.set('x-custom-header', 'my-value');
  
  // ✅ GEOLOCATION / LOCALE REDIRECT
  const country = request.geo?.country || 'US';
  response.headers.set('x-country', country);

  return response;
}

// ✅ SPECIFY WHICH ROUTES MIDDLEWARE RUNS ON
export const config = {
  matcher: [
    // Match all routes except static files and API
    '/((?!api|_next/static|_next/image|favicon.ico).*)',
    
    // Or specific paths:
    // '/dashboard/:path*',
    // '/api/:path*',
  ],
};
```

---

## PART 7: STYLING, FONTS & ASSETS (Week 9)

### 7.1 Styling Options

```typescript
// ✅ TAILWIND CSS (RECOMMENDED — comes pre-installed!) ⭐⭐⭐
export default function Card({ title, description }: CardProps) {
  return (
    <div className="max-w-sm rounded-lg shadow-lg bg-white p-6 
                    hover:shadow-xl transition-shadow duration-300
                    dark:bg-gray-800 dark:text-white">
      <h3 className="text-xl font-bold text-gray-800 dark:text-white mb-2">
        {title}
      </h3>
      <p className="text-gray-600 dark:text-gray-300">{description}</p>
      <button className="mt-4 px-4 py-2 bg-blue-500 text-white rounded-lg
                         hover:bg-blue-600 transition-colors">
        Read More
      </button>
    </div>
  );
}

// ✅ CSS MODULES (Scoped CSS — built-in)
// components/Button.module.css:
// .button { padding: 8px 16px; border-radius: 4px; }
// .primary { background: blue; color: white; }

import styles from './Button.module.css';

export default function Button({ children }: { children: React.ReactNode }) {
  return (
    <button className={`${styles.button} ${styles.primary}`}>
      {children}
    </button>
  );
}

// ✅ GLOBAL CSS
// app/globals.css — imported in root layout

// ✅ CSS-IN-JS (Styled Components, etc.)
// Requires configuration for Server Components
```

### 7.2 Font Optimization

```typescript
// ✅ NEXT/FONT — Automatic font optimization ⭐
// No layout shift, self-hosted, zero external requests!

// Google Fonts:
import { Inter, Roboto_Mono, Poppins } from 'next/font/google';

const inter = Inter({ 
  subsets: ['latin'],
  display: 'swap',
  variable: '--font-inter',  // CSS variable
});

const poppins = Poppins({ 
  subsets: ['latin'],
  weight: ['400', '500', '600', '700'],
  variable: '--font-poppins',
});

// Use in layout:
export default function RootLayout({ children }: { children: React.ReactNode }) {
  return (
    <html lang="en" className={`${inter.variable} ${poppins.variable}`}>
      <body className={inter.className}>{children}</body>
    </html>
  );
}

// Local Fonts:
import localFont from 'next/font/local';

const myFont = localFont({
  src: './fonts/MyFont.woff2',
  display: 'swap',
});
```

### 7.3 Image Optimization

```typescript
// ✅ NEXT/IMAGE — Automatic image optimization ⭐⭐
import Image from 'next/image';

// Local image:
import heroImage from '@/public/images/hero.jpg';

export default function Hero() {
  return (
    <Image
      src={heroImage}
      alt="Hero image"
      width={1200}
      height={600}
      priority           // Load immediately (above the fold)
      placeholder="blur"  // Blur placeholder while loading ⭐
    />
  );
}

// Remote image:
export default function Avatar({ user }: { user: User }) {
  return (
    <Image
      src={user.avatar}  // External URL
      alt={user.name}
      width={40}
      height={40}
      className="rounded-full"
    />
  );
}

// next.config.js — Allow external image domains:
/** @type {import('next').NextConfig} */
const nextConfig = {
  images: {
    remotePatterns: [
      {
        protocol: 'https',
        hostname: 'images.unsplash.com',
      },
      {
        protocol: 'https',
        hostname: 'avatars.githubusercontent.com',
      },
      {
        protocol: 'https',
        hostname: '*.cloudinary.com',
      },
    ],
  },
};

module.exports = nextConfig;

// Fill container:
<div className="relative w-full h-64">
  <Image
    src="/hero.jpg"
    alt="Hero"
    fill                    // Fill parent container
    className="object-cover" // CSS for filling
    sizes="(max-width: 768px) 100vw, 50vw" // Responsive sizes
  />
</div>
```

### 7.4 Metadata & SEO ⭐⭐

```typescript
// ✅ STATIC METADATA
// app/layout.tsx or any page.tsx:
import type { Metadata } from 'next';

export const metadata: Metadata = {
  title: {
    default: 'My App',
    template: '%s | My App',  // "About | My App"
  },
  description: 'A Next.js application',
  keywords: ['Next.js', 'React', 'TypeScript'],
  authors: [{ name: 'Your Name' }],
  openGraph: {
    title: 'My App',
    description: 'A Next.js application',
    url: 'https://myapp.com',
    siteName: 'My App',
    images: [
      {
        url: 'https://myapp.com/og-image.jpg',
        width: 1200,
        height: 630,
      },
    ],
    type: 'website',
  },
  twitter: {
    card: 'summary_large_image',
    title: 'My App',
    description: 'A Next.js application',
    images: ['https://myapp.com/og-image.jpg'],
  },
  robots: {
    index: true,
    follow: true,
  },
};

// ✅ DYNAMIC METADATA
// app/blog/[slug]/page.tsx:
export async function generateMetadata({ params }: { params: { slug: string } }): Promise<Metadata> {
  const post = await getPost(params.slug);
  
  return {
    title: post.title,
    description: post.excerpt,
    openGraph: {
      title: post.title,
      description: post.excerpt,
      images: [post.coverImage],
    },
  };
}

// ✅ ROBOTS.TXT
// app/robots.ts:
import type { MetadataRoute } from 'next';

export default function robots(): MetadataRoute.Robots {
  return {
    rules: { userAgent: '*', allow: '/', disallow: '/dashboard/' },
    sitemap: 'https://myapp.com/sitemap.xml',
  };
}

// ✅ SITEMAP
// app/sitemap.ts:
import type { MetadataRoute } from 'next';

export default async function sitemap(): Promise<MetadataRoute.Sitemap> {
  const posts = await prisma.post.findMany({ select: { slug: true, updatedAt: true } });

  const postUrls = posts.map(post => ({
    url: `https://myapp.com/blog/${post.slug}`,
    lastModified: post.updatedAt,
    changeFrequency: 'weekly' as const,
    priority: 0.8,
  }));

  return [
    { url: 'https://myapp.com', lastModified: new Date(), priority: 1 },
    { url: 'https://myapp.com/about', lastModified: new Date(), priority: 0.5 },
    ...postUrls,
  ];
}
```

---

## PART 8: AUTHENTICATION IN NEXT.JS (Week 10-11)

### 8.1 NextAuth.js (Auth.js) ⭐⭐⭐

```typescript
// ✅ NEXTAUTH.JS — THE standard auth for Next.js
// npm install next-auth @auth/prisma-adapter

// lib/auth.ts:
import { NextAuthOptions } from 'next-auth';
import { PrismaAdapter } from '@auth/prisma-adapter';
import CredentialsProvider from 'next-auth/providers/credentials';
import GoogleProvider from 'next-auth/providers/google';
import GitHubProvider from 'next-auth/providers/github';
import bcrypt from 'bcryptjs';
import { prisma } from '@/lib/db';

export const authOptions: NextAuthOptions = {
  adapter: PrismaAdapter(prisma),
  providers: [
    // ✅ GOOGLE OAUTH
    GoogleProvider({
      clientId: process.env.GOOGLE_CLIENT_ID!,
      clientSecret: process.env.GOOGLE_CLIENT_SECRET!,
    }),
    
    // ✅ GITHUB OAUTH
    GitHubProvider({
      clientId: process.env.GITHUB_ID!,
      clientSecret: process.env.GITHUB_SECRET!,
    }),
    
    // ✅ CREDENTIALS (Email/Password)
    CredentialsProvider({
      name: 'credentials',
      credentials: {
        email: { label: 'Email', type: 'email' },
        password: { label: 'Password', type: 'password' },
      },
      async authorize(credentials) {
        if (!credentials?.email || !credentials?.password) {
          throw new Error('Invalid credentials');
        }
        
        const user = await prisma.user.findUnique({
          where: { email: credentials.email },
        });
        
        if (!user || !user.hashedPassword) {
          throw new Error('Invalid credentials');
        }
        
        const isCorrectPassword = await bcrypt.compare(
          credentials.password,
          user.hashedPassword
        );
        
        if (!isCorrectPassword) {
          throw new Error('Invalid credentials');
        }
        
        return user;
      },
    }),
  ],
  pages: {
    signIn: '/login',
  },
  session: {
    strategy: 'jwt',
  },
  callbacks: {
    async jwt({ token, user }) {
      if (user) {
        token.id = user.id;
        token.role = user.role;
      }
      return token;
    },
    async session({ session, token }) {
      if (session.user) {
        session.user.id = token.id as string;
        session.user.role = token.role as string;
      }
      return session;
    },
  },
};

// app/api/auth/[...nextauth]/route.ts:
import NextAuth from 'next-auth';
import { authOptions } from '@/lib/auth';

const handler = NextAuth(authOptions);
export { handler as GET, handler as POST };

// ✅ GET SESSION IN SERVER COMPONENTS
import { getServerSession } from 'next-auth';
import { authOptions } from '@/lib/auth';

export default async function ProfilePage() {
  const session = await getServerSession(authOptions);
  
  if (!session) {
    redirect('/login');
  }
  
  return <div>Welcome, {session.user?.name}</div>;
}

// ✅ GET SESSION IN CLIENT COMPONENTS
'use client';
import { useSession, signIn, signOut } from 'next-auth/react';

export default function AuthButton() {
  const { data: session, status } = useSession();
  
  if (status === 'loading') return <div>Loading...</div>;
  
  if (session) {
    return (
      <div>
        <p>Welcome, {session.user?.name}</p>
        <button onClick={() => signOut()}>Sign Out</button>
      </div>
    );
  }
  
  return (
    <div>
      <button onClick={() => signIn('google')}>Sign in with Google</button>
      <button onClick={() => signIn('github')}>Sign in with GitHub</button>
    </div>
  );
}

// ✅ WRAP APP WITH SESSION PROVIDER
// app/providers.tsx:
'use client';
import { SessionProvider } from 'next-auth/react';

export default function Providers({ children }: { children: React.ReactNode }) {
  return <SessionProvider>{children}</SessionProvider>;
}

// app/layout.tsx:
import Providers from './providers';

export default function RootLayout({ children }: { children: React.ReactNode }) {
  return (
    <html>
      <body>
        <Providers>{children}</Providers>
      </body>
    </html>
  );
}
```

---

## PART 9: DATABASE INTEGRATION (Week 12-13)

### 9.1 Prisma ORM ⭐⭐⭐ (THE ORM for Next.js)

```bash
# Install Prisma
npm install prisma @prisma/client
npx prisma init
```

```prisma
// prisma/schema.prisma:
generator client {
  provider = "prisma-client-js"
}

datasource db {
  provider = "postgresql"  // or "mysql", "mongodb", "sqlite"
  url      = env("DATABASE_URL")
}

model User {
  id             String    @id @default(cuid())
  name           String?
  email          String    @unique
  emailVerified  DateTime?
  image          String?
  hashedPassword String?
  role           Role      @default(USER)
  createdAt      DateTime  @default(now())
  updatedAt      DateTime  @updatedAt
  
  posts          Post[]
  comments       Comment[]
  likes          Like[]
  accounts       Account[]
  sessions       Session[]
}

model Post {
  id          String   @id @default(cuid())
  title       String
  slug        String   @unique
  content     String
  excerpt     String?
  coverImage  String?
  published   Boolean  @default(false)
  createdAt   DateTime @default(now())
  updatedAt   DateTime @updatedAt
  
  author      User     @relation(fields: [authorId], references: [id], onDelete: Cascade)
  authorId    String
  
  comments    Comment[]
  likes       Like[]
  tags        Tag[]
  
  @@index([authorId])
  @@index([slug])
}

model Comment {
  id        String   @id @default(cuid())
  content   String
  createdAt DateTime @default(now())
  
  author    User     @relation(fields: [authorId], references: [id], onDelete: Cascade)
  authorId  String
  post      Post     @relation(fields: [postId], references: [id], onDelete: Cascade)
  postId    String
}

model Like {
  id     String @id @default(cuid())
  user   User   @relation(fields: [userId], references: [id], onDelete: Cascade)
  userId String
  post   Post   @relation(fields: [postId], references: [id], onDelete: Cascade)
  postId String
  
  @@unique([userId, postId])
}

model Tag {
  id    String @id @default(cuid())
  name  String @unique
  posts Post[]
}

enum Role {
  USER
  ADMIN
  MODERATOR
}
```

```bash
# Push schema to database:
npx prisma db push

# Generate client:
npx prisma generate

# Open Prisma Studio (GUI for database):
npx prisma studio

# Create migration:
npx prisma migrate dev --name init

# Seed database:
npx prisma db seed
```

```typescript
// ✅ PRISMA CLIENT SINGLETON
// lib/db.ts:
import { PrismaClient } from '@prisma/client';

const globalForPrisma = globalThis as unknown as {
  prisma: PrismaClient | undefined;
};

export const prisma = globalForPrisma.prisma ?? new PrismaClient();

if (process.env.NODE_ENV !== 'production') globalForPrisma.prisma = prisma;

// ✅ USE PRISMA IN SERVER COMPONENTS
// app/posts/page.tsx:
import { prisma } from '@/lib/db';

export default async function PostsPage() {
  const posts = await prisma.post.findMany({
    where: { published: true },
    include: {
      author: { select: { name: true, image: true } },
      _count: { select: { likes: true, comments: true } },
    },
    orderBy: { createdAt: 'desc' },
    take: 20,
  });

  return (
    <div className="grid gap-4">
      {posts.map(post => (
        <PostCard key={post.id} post={post} />
      ))}
    </div>
  );
}

// ✅ USE PRISMA IN SERVER ACTIONS
// actions/posts.ts:
'use server';
import { prisma } from '@/lib/db';

export async function createPost(formData: FormData) {
  const session = await getServerSession(authOptions);
  if (!session) throw new Error('Unauthorized');

  const title = formData.get('title') as string;
  const content = formData.get('content') as string;
  const slug = title.toLowerCase().replace(/\s+/g, '-');

  const post = await prisma.post.create({
    data: {
      title,
      slug,
      content,
      authorId: session.user.id,
    },
  });

  revalidatePath('/posts');
  redirect(`/posts/${post.slug}`);
}
```

### 9.2 Other Database Options

```
DATABASE OPTIONS FOR NEXT.JS:

✅ PostgreSQL + Prisma (RECOMMENDED)
   - Most popular combo with Next.js
   - Vercel Postgres, Neon, Supabase, Railway

✅ MongoDB + Prisma or Mongoose
   - Good for flexible schemas
   - MongoDB Atlas (free tier)

✅ Supabase (PostgreSQL + Auth + Storage + Realtime)
   - Firebase alternative
   - Built-in auth, storage, real-time
   - Free tier available

✅ PlanetScale (MySQL)
   - Serverless MySQL
   - Branching (like git for databases)

✅ Drizzle ORM (Alternative to Prisma)
   - Lighter, SQL-like syntax
   - Growing in popularity

✅ Turso (SQLite at the edge)
   - Fastest, cheapest
   - Good for read-heavy workloads

FREE DATABASE HOSTING:
  - Vercel Postgres (Neon) — Free tier
  - Supabase — 500MB free
  - PlanetScale — 5GB free
  - MongoDB Atlas — 512MB free
  - Railway — $5/month free credit
  - Neon — 512MB free
```

---

## PART 10: ADVANCED NEXT.JS FEATURES (Week 14-15)

### 10.1 Caching (Deep Dive) ⭐⭐

```typescript
// ✅ NEXT.JS 4 CACHING LAYERS:

// 1. REQUEST MEMOIZATION (same request in same render = one fetch)
// Automatic! If you call the same fetch twice, it runs once.

// 2. DATA CACHE (fetch results cached on server)
// Default: cached forever (opt out with cache: 'no-store')
fetch(url);                              // Cached indefinitely
fetch(url, { cache: 'no-store' });       // Not cached
fetch(url, { next: { revalidate: 60 } }); // Cached for 60 seconds

// 3. FULL ROUTE CACHE (rendered HTML cached on server)
// Static routes cached at build time
// Dynamic routes not cached

// 4. ROUTER CACHE (client-side cache for navigation)
// Previously visited routes cached in browser
// Automatic! Prefetched routes cached for 30 seconds

// ✅ UNSTABLE_CACHE (Cache non-fetch data)
import { unstable_cache } from 'next/cache';

const getCachedUser = unstable_cache(
  async (userId: string) => {
    return prisma.user.findUnique({ where: { id: userId } });
  },
  ['user'], // Cache key
  { revalidate: 3600, tags: ['users'] } // Options
);

// Usage:
const user = await getCachedUser('user-123');
```

### 10.2 Internationalization (i18n)

```typescript
// ✅ BASIC I18N SETUP
// middleware.ts:
import { NextRequest, NextResponse } from 'next/server';

const locales = ['en', 'es', 'fr', 'de'];
const defaultLocale = 'en';

export function middleware(request: NextRequest) {
  const { pathname } = request.nextUrl;
  
  const pathnameHasLocale = locales.some(
    locale => pathname.startsWith(`/${locale}/`) || pathname === `/${locale}`
  );
  
  if (pathnameHasLocale) return;
  
  // Detect locale from Accept-Language header
  const locale = request.headers.get('accept-language')?.split(',')[0]?.split('-')[0] || defaultLocale;
  
  request.nextUrl.pathname = `/${locale}${pathname}`;
  return NextResponse.redirect(request.nextUrl);
}

// app/[locale]/page.tsx:
// Different pages per locale
```

### 10.3 Environment Variables

```bash
# .env.local (NEVER commit!):
# Server-only (default):
DATABASE_URL="postgresql://..."
NEXTAUTH_SECRET="your-secret"
GOOGLE_CLIENT_ID="..."
GOOGLE_CLIENT_SECRET="..."

# Client-accessible (prefix with NEXT_PUBLIC_):
NEXT_PUBLIC_APP_URL="http://localhost:3000"
NEXT_PUBLIC_STRIPE_PUBLIC_KEY="pk_test_..."
NEXT_PUBLIC_GA_ID="G-..."

# .env files loading order:
# .env.local (highest priority, gitignored)
# .env.development / .env.production
# .env (lowest priority)
```

```typescript
// Access in code:
// Server:
const dbUrl = process.env.DATABASE_URL;           // ✅ Works in Server Components
const secret = process.env.NEXTAUTH_SECRET;        // ✅ Works in Route Handlers

// Client:
const appUrl = process.env.NEXT_PUBLIC_APP_URL;    // ✅ Available in client
const key = process.env.NEXT_PUBLIC_STRIPE_PUBLIC_KEY; // ✅ Available in client

// ❌ This WON'T work in client:
const secret = process.env.DATABASE_URL; // undefined in client!
```

### 10.4 next.config.js

```javascript
/** @type {import('next').NextConfig} */
const nextConfig = {
  // ✅ Images
  images: {
    remotePatterns: [
      { protocol: 'https', hostname: 'images.unsplash.com' },
      { protocol: 'https', hostname: '*.cloudinary.com' },
    ],
  },
  
  // ✅ Redirects
  async redirects() {
    return [
      {
        source: '/old-blog/:slug',
        destination: '/blog/:slug',
        permanent: true, // 301
      },
    ];
  },
  
  // ✅ Rewrites (proxy/URL masking)
  async rewrites() {
    return [
      {
        source: '/api/external/:path*',
        destination: 'https://api.example.com/:path*', // Proxy
      },
    ];
  },
  
  // ✅ Headers
  async headers() {
    return [
      {
        source: '/api/:path*',
        headers: [
          { key: 'Access-Control-Allow-Origin', value: '*' },
        ],
      },
    ];
  },
  
  // ✅ Experimental features
  experimental: {
    serverActions: {
      bodySizeLimit: '2mb',
    },
  },
};

module.exports = nextConfig;
```

---

## PART 11: STATE MANAGEMENT & FORMS (Week 16)

### 11.1 State Management in Next.js

```typescript
// ✅ STATE MANAGEMENT OPTIONS IN NEXT.JS:

// 1. SERVER STATE (Preferred!) ⭐⭐⭐
//    - Server Components fetch data directly
//    - Server Actions mutate data
//    - No client-side state needed for server data!
//    → Most apps need LESS client state with Next.js

// 2. URL STATE (searchParams) ⭐
//    - Filters, pagination, search queries
//    - Shareable, bookmarkable
import { useSearchParams, useRouter, usePathname } from 'next/navigation';

function Filters() {
  const searchParams = useSearchParams();
  const router = useRouter();
  const pathname = usePathname();
  
  const updateFilter = (key: string, value: string) => {
    const params = new URLSearchParams(searchParams.toString());
    params.set(key, value);
    router.push(`${pathname}?${params.toString()}`);
  };
  
  return (
    <select onChange={(e) => updateFilter('category', e.target.value)}>
      <option value="all">All</option>
      <option value="tech">Tech</option>
    </select>
  );
}

// 3. REACT CONTEXT (Small global state) ⭐
//    - Theme, user preferences, UI state

// 4. ZUSTAND (Client-side global state) ⭐
// npm install zustand
import { create } from 'zustand';

interface CartStore {
  items: CartItem[];
  addItem: (item: CartItem) => void;
  removeItem: (id: string) => void;
  clearCart: () => void;
  totalPrice: () => number;
}

export const useCartStore = create<CartStore>((set, get) => ({
  items: [],
  addItem: (item) => set((state) => ({ items: [...state.items, item] })),
  removeItem: (id) => set((state) => ({ items: state.items.filter(i => i.id !== id) })),
  clearCart: () => set({ items: [] }),
  totalPrice: () => get().items.reduce((sum, item) => sum + item.price, 0),
}));

// 5. TANSTACK QUERY (Server state caching on client) ⭐
//    - When you need client-side data fetching (CSR)
//    - Polling, real-time updates, infinite scroll
```

### 11.2 Form Libraries

```typescript
// ✅ REACT HOOK FORM + ZOD (Best combo for Next.js) ⭐⭐
// npm install react-hook-form @hookform/resolvers zod

'use client';
import { useForm } from 'react-hook-form';
import { zodResolver } from '@hookform/resolvers/zod';
import { z } from 'zod';
import { createPost } from '@/actions/posts';

const postSchema = z.object({
  title: z.string().min(3, 'Title must be at least 3 characters'),
  content: z.string().min(10, 'Content must be at least 10 characters'),
  category: z.enum(['tech', 'lifestyle', 'business']),
  published: z.boolean().default(false),
});

type PostFormData = z.infer<typeof postSchema>;

export default function PostForm() {
  const {
    register,
    handleSubmit,
    formState: { errors, isSubmitting },
  } = useForm<PostFormData>({
    resolver: zodResolver(postSchema),
  });

  const onSubmit = async (data: PostFormData) => {
    const formData = new FormData();
    Object.entries(data).forEach(([key, value]) => {
      formData.append(key, String(value));
    });
    await createPost(formData);
  };

  return (
    <form onSubmit={handleSubmit(onSubmit)} className="space-y-4">
      <div>
        <input {...register('title')} placeholder="Title" className="input" />
        {errors.title && <p className="text-red-500">{errors.title.message}</p>}
      </div>
      
      <div>
        <textarea {...register('content')} placeholder="Content" className="textarea" />
        {errors.content && <p className="text-red-500">{errors.content.message}</p>}
      </div>
      
      <div>
        <select {...register('category')}>
          <option value="tech">Tech</option>
          <option value="lifestyle">Lifestyle</option>
          <option value="business">Business</option>
        </select>
      </div>
      
      <button type="submit" disabled={isSubmitting}>
        {isSubmitting ? 'Creating...' : 'Create Post'}
      </button>
    </form>
  );
}
```

---

## PART 12: TESTING & PERFORMANCE (Week 17)

### 12.1 Testing

```typescript
// ✅ TESTING STACK FOR NEXT.JS:
// npm install -D jest @testing-library/react @testing-library/jest-dom
// npm install -D @types/jest ts-jest
// npm install -D playwright  (for E2E)

// Unit test example:
import { render, screen } from '@testing-library/react';
import HomePage from '@/app/page';

describe('HomePage', () => {
  it('renders the heading', () => {
    render(<HomePage />);
    expect(screen.getByRole('heading')).toBeInTheDocument();
  });
});

// E2E test with Playwright:
import { test, expect } from '@playwright/test';

test('should navigate to about page', async ({ page }) => {
  await page.goto('/');
  await page.click('text=About');
  await expect(page).toHaveURL('/about');
  await expect(page.locator('h1')).toContainText('About');
});
```

### 12.2 Performance Optimization

```typescript
// ✅ PERFORMANCE BEST PRACTICES:

// 1. USE SERVER COMPONENTS (default — less JS shipped)

// 2. DYNAMIC IMPORTS (lazy loading) ⭐
import dynamic from 'next/dynamic';

const HeavyChart = dynamic(() => import('@/components/Chart'), {
  loading: () => <div>Loading chart...</div>,
  ssr: false, // Only load on client
});

// 3. IMAGE OPTIMIZATION (always use next/image)
import Image from 'next/image';

// 4. FONT OPTIMIZATION (always use next/font)
import { Inter } from 'next/font/google';

// 5. ROUTE PREFETCHING (automatic with <Link>)
<Link href="/dashboard" prefetch={true}>Dashboard</Link>

// 6. PARALLEL DATA FETCHING
const [users, posts] = await Promise.all([getUsers(), getPosts()]);

// 7. STREAMING WITH SUSPENSE
<Suspense fallback={<Skeleton />}>
  <SlowComponent />
</Suspense>

// 8. ANALYZE BUNDLE SIZE
// npm install @next/bundle-analyzer
// next.config.js:
const withBundleAnalyzer = require('@next/bundle-analyzer')({
  enabled: process.env.ANALYZE === 'true',
});
module.exports = withBundleAnalyzer(nextConfig);
// Run: ANALYZE=true npm run build
```

---

## PART 13: DEPLOYMENT (Week 18)

```
DEPLOYMENT OPTIONS:

✅ VERCEL (BEST for Next.js — created by same team!) ⭐⭐⭐
   - Push to GitHub → Auto deploys
   - Free tier (generous!)
   - Edge functions, serverless
   - Preview deployments for PRs
   - Analytics built-in
   - Custom domains
   STEPS:
   1. Push code to GitHub
   2. Go to vercel.com
   3. Import repository
   4. Set environment variables
   5. Deploy! (automatic on every push)
   
✅ Netlify
   - Similar to Vercel
   - Good for static/hybrid sites

✅ AWS Amplify
   - Full AWS integration
   - More complex, more control

✅ Railway / Render
   - If you need a traditional server

✅ Docker
   - For custom infrastructure
   - Dockerfile included in Next.js docs

✅ Self-hosted (Node.js server)
   npm run build
   npm start      # Starts production server on port 3000

PRODUCTION CHECKLIST:
  ✅ Environment variables set
  ✅ Database connected and migrated
  ✅ Images domains configured
  ✅ Metadata/SEO configured
  ✅ Error pages (404, 500) created
  ✅ Loading states implemented
  ✅ Security headers (middleware)
  ✅ Analytics tracking added
  ✅ Performance tested (Lighthouse)
  ✅ Mobile responsive
  ✅ robots.txt and sitemap.xml
```

---

## PART 14: BUILD 8 NEXT.JS PROJECTS

```
BUILD IN THIS ORDER (increasing complexity):

PROJECT 1 — Personal Portfolio (Week 3-4) ⭐ STARTER
  ✅ Static pages (About, Projects, Contact)
  ✅ Responsive design with Tailwind
  ✅ SEO metadata
  ✅ Image optimization
  ✅ Dark mode
  ✅ Contact form with Server Action
  Skills: Routing, layouts, metadata, Image, fonts
  Time: 2-3 days

PROJECT 2 — Blog Platform with MDX (Week 5-6) ⭐⭐
  ✅ Markdown/MDX blog posts
  ✅ Static generation (SSG)
  ✅ Dynamic routes ([slug])
  ✅ Categories & tags
  ✅ Search functionality
  ✅ RSS feed
  ✅ Syntax highlighting
  Skills: SSG, generateStaticParams, metadata, MDX
  Time: 4-5 days

PROJECT 3 — Full-Stack Todo App (Week 8-9) ⭐⭐
  ✅ CRUD operations
  ✅ Server Actions
  ✅ Prisma + PostgreSQL
  ✅ Authentication (NextAuth)
  ✅ Optimistic updates
  ✅ Loading & error states
  Skills: Server Actions, database, auth basics
  Time: 3-4 days

PROJECT 4 — E-Commerce Store (Week 10-13) ⭐⭐⭐ BEST FOR RESUME
  ✅ Product listing with filters & search
  ✅ Product detail pages (ISR)
  ✅ Shopping cart (Zustand)
  ✅ Checkout with Stripe
  ✅ User authentication
  ✅ Order history
  ✅ Admin dashboard
  ✅ Image upload (Cloudinary)
  ✅ Reviews & ratings
  Skills: ISR, payments, admin, file upload
  Time: 10-14 days

PROJECT 5 — SaaS Dashboard (Week 14-15) ⭐⭐⭐
  ✅ Multi-tenant architecture
  ✅ Subscription billing (Stripe)
  ✅ Role-based access control
  ✅ Analytics dashboard with charts
  ✅ Team management
  ✅ Settings page
  ✅ Parallel routes (modals)
  Skills: Complex auth, subscriptions, parallel routes
  Time: 7-10 days

PROJECT 6 — Social Media / Reddit Clone (Week 16-17) ⭐⭐⭐
  ✅ Posts with upvotes/downvotes
  ✅ Nested comments
  ✅ Subreddits/communities
  ✅ Infinite scroll
  ✅ Real-time updates
  ✅ User profiles
  Skills: Complex data, infinite scroll, real-time
  Time: 7-10 days

PROJECT 7 — AI-Powered App (Week 18) ⭐⭐⭐
  ✅ OpenAI API integration
  ✅ Streaming responses
  ✅ Chat interface
  ✅ Prompt management
  ✅ Usage tracking
  ✅ Rate limiting
  Skills: AI APIs, streaming, edge functions
  Time: 5-7 days

PROJECT 8 — Full-Stack Marketplace (Week 19-20) ⭐⭐⭐⭐
  ✅ Multi-vendor marketplace
  ✅ Real-time messaging (Pusher/Socket.io)
  ✅ Map integration
  ✅ Image gallery
  ✅ Payment split
  ✅ Search with filters
  ✅ Favorites/wishlists
  ✅ Notifications
  Skills: Everything combined, production-ready
  Time: 10-14 days

PORTFOLIO MUST-HAVES:
  Minimum: Project 1 + Project 4 + one more
  Best combo: Portfolio + E-Commerce + SaaS Dashboard
  ALL projects must be:
    ✅ Deployed on Vercel (live URLs)
    ✅ On GitHub with good README
    ✅ Mobile responsive
    ✅ Have demo screenshots/video
```

---

## PART 15: RESOURCES

### 15.1 YouTube Channels

```
TIER 1 — PRIMARY (Follow for Next.js):

  1. Vercel (Official) ⭐⭐⭐
     → Next.js Conf talks, official tutorials
     → @vercel

  2. Lee Robinson ⭐⭐⭐
     → VP of Product at Vercel
     → Best Next.js content, deep dives
     → @laborb

  3. Theo (t3.gg) ⭐⭐
     → T3 stack (Next.js + tRPC + Prisma + Tailwind)
     → Modern full-stack opinions
     → @t3dotgg

  4. JavaScript Mastery ⭐⭐
     → Full project-based Next.js tutorials
     → @javascriptmastery

  5. Code With Antonio ⭐⭐⭐
     → BEST full-stack Next.js project tutorials
     → E-commerce, SaaS, LMS — complete projects
     → @codewithantonio

  6. Josh tried coding ⭐⭐
     → Next.js projects and patterns
     → @joshtriedcoding

TIER 2 — TOPIC-SPECIFIC:

  7. Web Dev Simplified → React/Next.js concepts
  8. Fireship → Quick overviews
  9. Dave Gray → Complete Next.js course (free)
  10. Sonny Sangha → Full-stack Next.js projects
  11. Hamed Bahram → Next.js deep dives
  12. Colby Fayock → Next.js tutorials
```

### 15.2 GitHub Repositories

```
NEXT.JS:
  github.com/vercel/next.js ⭐⭐⭐
  → Official Next.js repo (check /examples folder!)
  → 400+ example projects!

  github.com/vercel/next.js/tree/canary/examples
  → with-prisma, with-auth, with-tailwind, etc.

  github.com/shadcn-ui/taxonomy ⭐⭐⭐
  → Full-stack Next.js 13 app (blog, auth, billing)
  → By the creator of shadcn/ui

  github.com/steven-tey/dub ⭐⭐
  → Open-source link shortener (production Next.js)
  → Used by 50K+ users

  github.com/calcom/cal.com ⭐⭐
  → Open-source Calendly alternative
  → Production Next.js + Prisma

  github.com/sadmann7/skateshop ⭐⭐
  → Full-stack e-commerce with Next.js 14

  github.com/t3-oss/create-t3-app ⭐⭐
  → T3 Stack: Next.js + tRPC + Prisma + Tailwind + NextAuth

  github.com/AntonioErdeljac (all repos) ⭐⭐
  → Code With Antonio — many production Next.js projects

UI COMPONENTS:
  github.com/shadcn-ui/ui ⭐⭐⭐
  → THE most popular React/Next.js UI library
  → Copy-paste components, Tailwind-based
  → Used by everyone in 2024-2025

DOCUMENTATION:
  nextjs.org/docs ⭐⭐⭐
  → Official docs (excellent, always start here)
  
  nextjs.org/learn ⭐⭐⭐
  → Official interactive tutorial (FREE, BEST starting point)
```

### 15.3 Official Resources

```
MUST-READ DOCUMENTATION:
  nextjs.org/docs           → Complete API reference
  nextjs.org/learn          → Interactive tutorial ⭐⭐⭐ (do this first!)
  nextjs.org/blog           → Release notes, new features
  
  prisma.io/docs            → Prisma ORM docs
  next-auth.js.org          → NextAuth.js docs
  tailwindcss.com/docs      → Tailwind CSS docs
  ui.shadcn.com             → shadcn/ui components
  zod.dev                   → Zod validation docs
  
PAID COURSES (if you want structured learning):
  "Next.js 14 & React" by Maximilian Schwarzmüller (Udemy) ⭐⭐
  "Build a SaaS" by Code With Antonio (YouTube — Free!) ⭐⭐⭐
  "Total TypeScript" by Matt Pocock ⭐⭐
```

---

## PART 16: 30-DAY KICKSTART PLAN

### WEEK 1: FUNDAMENTALS (Days 1-7)

```
DAY 1: Next.js Setup + File-Based Routing
  ✅ Create Next.js project (npx create-next-app@latest)
  ✅ Understand folder structure
  ✅ Create 5 static pages (Home, About, Blog, Contact, Pricing)
  ✅ Learn: page.tsx, layout.tsx, Link component
  ⏱️ 3-4 hours

DAY 2: Dynamic Routes + Layouts
  ✅ Create dynamic route: /blog/[slug]/page.tsx
  ✅ Create nested layout: /dashboard/layout.tsx
  ✅ Create route group: (auth)/login, (auth)/register
  ✅ Learn: params, searchParams
  ⏱️ 3-4 hours

DAY 3: Special Files + Navigation
  ✅ Create loading.tsx (loading states)
  ✅ Create error.tsx (error boundaries)
  ✅ Create not-found.tsx (404 page)
  ✅ Practice: Link, useRouter, redirect
  ✅ Active NavLinks with usePathname
  ⏱️ 3-4 hours

DAY 4: Server Components vs Client Components
  ✅ Understand the difference (THE most important concept!)
  ✅ Build a page that fetches data (Server Component)
  ✅ Build an interactive component (Client Component)
  ✅ Practice composition: Server parent, Client child
  ⏱️ 4 hours

DAY 5: Data Fetching in Server Components
  ✅ Fetch from external API in Server Component
  ✅ Learn: cache, no-store, revalidate options
  ✅ Parallel data fetching (Promise.all)
  ✅ Streaming with Suspense
  ⏱️ 4 hours

DAY 6: Image, Fonts & Metadata
  ✅ Use next/image (local + remote images)
  ✅ Set up next/font (Google Fonts)
  ✅ Add metadata (static + dynamic)
  ✅ Style with Tailwind CSS
  ⏱️ 3 hours

DAY 7: Build Mini Project — Portfolio Site
  ✅ 5-page portfolio with everything learned
  ✅ Responsive design
  ✅ Deploy on Vercel
  ✅ Push to GitHub
  ⏱️ 5-6 hours
```

### WEEK 2: SERVER ACTIONS + DATABASE (Days 8-14)

```
DAY 8: API Route Handlers
  ✅ Create GET, POST, PUT, DELETE route handlers
  ✅ app/api/posts/route.ts
  ✅ app/api/posts/[id]/route.ts
  ✅ Test with Postman/Thunder Client
  ⏱️ 4 hours

DAY 9: Server Actions (Part 1)
  ✅ Create inline Server Actions
  ✅ Create separate Server Action files
  ✅ Form handling with Server Actions
  ✅ revalidatePath, redirect
  ⏱️ 4 hours

DAY 10: Server Actions (Part 2)
  ✅ useFormStatus (loading states)
  ✅ useActionState (error handling)
  ✅ Optimistic updates with useOptimistic
  ✅ Server Actions without forms (useTransition)
  ⏱️ 4 hours

DAY 11: Prisma Setup + Database
  ✅ Install Prisma, init, configure
  ✅ Create schema (User, Post, Comment)
  ✅ Push to database
  ✅ Use Prisma Studio
  ✅ CRUD operations in Server Components
  ⏱️ 4-5 hours

DAY 12: Prisma Advanced
  ✅ Relations (one-to-many, many-to-many)
  ✅ Queries: findMany, findUnique, create, update, delete
  ✅ Filtering, sorting, pagination
  ✅ Include, select
  ⏱️ 4 hours

DAY 13: Authentication Setup
  ✅ Install NextAuth.js
  ✅ Configure Google + GitHub OAuth
  ✅ Configure credentials (email/password)
  ✅ Prisma adapter
  ✅ Protected routes with middleware
  ⏱️ 5-6 hours

DAY 14: Auth Integration + Review
  ✅ Login/Register pages
  ✅ Session in Server + Client Components
  ✅ Protected dashboard
  ✅ Logout functionality
  ✅ Review all Week 2 concepts
  ⏱️ 5 hours
```

### WEEK 3: BUILD FULL-STACK PROJECT (Days 15-21)

```
DAY 15: Project Planning — Blog/Todo/Notes App
  ✅ Define features, pages, database schema
  ✅ Setup project with all tools
  ✅ Create Prisma schema, push to DB
  ✅ Set up auth (NextAuth)
  ⏱️ 4-5 hours

DAY 16: Backend — Server Actions & API
  ✅ Create all Server Actions (CRUD)
  ✅ Validation with Zod
  ✅ Error handling
  ⏱️ 4-5 hours

DAY 17: Frontend — Pages & Components
  ✅ Build all pages (Home, Dashboard, Create, Edit)
  ✅ Build reusable components (Card, Form, Button)
  ✅ Loading states, error states
  ⏱️ 5-6 hours

DAY 18: Frontend — Forms & Interactivity
  ✅ Create forms (Create Post, Edit Post)
  ✅ Delete with confirmation
  ✅ Search functionality
  ✅ Pagination
  ⏱️ 4-5 hours

DAY 19: Polish — Styling & UX
  ✅ Complete Tailwind styling
  ✅ Mobile responsive
  ✅ Dark mode (optional)
  ✅ Toast notifications
  ⏱️ 4-5 hours

DAY 20: SEO & Performance
  ✅ Add metadata to all pages
  ✅ Optimize images
  ✅ Add sitemap & robots.txt
  ✅ Lighthouse audit
  ⏱️ 3-4 hours

DAY 21: Deploy & Document
  ✅ Deploy on Vercel
  ✅ Set environment variables
  ✅ Write README with screenshots
  ✅ Push to GitHub
  ⏱️ 3-4 hours
```

### WEEK 4: ADVANCED + NEXT PROJECT (Days 22-30)

```
DAY 22: Middleware Deep Dive
  ✅ Auth middleware (protect routes)
  ✅ Rate limiting concepts
  ✅ Locale detection
  ✅ A/B testing pattern
  ⏱️ 3-4 hours

DAY 23: Caching & Revalidation
  ✅ Understand all 4 caching layers
  ✅ On-demand revalidation (tags, paths)
  ✅ ISR (Incremental Static Regeneration)
  ✅ Practice with real examples
  ⏱️ 3-4 hours

DAY 24: shadcn/ui Setup
  ✅ Install shadcn/ui
  ✅ Add components (Button, Card, Dialog, Form)
  ✅ Customize theme
  ✅ Build a page with shadcn components
  ⏱️ 3 hours

DAY 25-28: BUILD E-COMMERCE PROJECT ⭐⭐⭐
  Day 25: Schema + Auth + Layout
  Day 26: Product listing + detail pages
  Day 27: Cart + Checkout (Stripe)
  Day 28: Admin dashboard + orders
  ⏱️ 5-6 hours each day

DAY 29: Deploy + Polish E-Commerce
  ✅ Deploy on Vercel
  ✅ Set all environment variables
  ✅ Test entire flow
  ✅ Write README
  ⏱️ 4-5 hours

DAY 30: Review + Plan Next Steps
  ✅ Review everything learned
  ✅ Update GitHub profile
  ✅ Plan next project
  ✅ Start TypeScript deep dive
  ✅ Celebrate! 🎉
  ⏱️ 3 hours
```

---

## PART 17: NEXT.JS INTERVIEW QUESTIONS

```
MOST ASKED NEXT.JS INTERVIEW QUESTIONS:

FUNDAMENTALS:
  ✅ What is Next.js? How is it different from React?
  ✅ What is the App Router? How does it differ from Pages Router?
  ✅ Explain file-based routing in Next.js
  ✅ What are the special files in Next.js? (page, layout, loading, error, etc.)
  ✅ What is the difference between Link and <a> tag?
  ✅ How does prefetching work in Next.js?
  ✅ What are route groups? When would you use them?
  ✅ What are dynamic routes? How do catch-all routes work?

SERVER vs CLIENT COMPONENTS:
  ✅ What is the difference between Server and Client Components?
  ✅ When would you use 'use client'?
  ✅ Can a Server Component import a Client Component? (Yes)
  ✅ Can a Client Component import a Server Component? (No, but can receive as children)
  ✅ What is the composition pattern?
  ✅ What can't you do in Server Components?
  ✅ Why are Server Components the default?

RENDERING:
  ✅ Explain SSR, SSG, ISR, and CSR
  ✅ When would you use each rendering strategy?
  ✅ What is Incremental Static Regeneration?
  ✅ How does streaming work in Next.js?
  ✅ What is generateStaticParams?
  ✅ How does Next.js decide between static and dynamic rendering?
  ✅ What is the difference between revalidatePath and revalidateTag?

DATA FETCHING:
  ✅ How does data fetching work in Server Components?
  ✅ What caching options does fetch() have in Next.js?
  ✅ What are Server Actions?
  ✅ How do Server Actions differ from API routes?
  ✅ When would you use Server Actions vs API routes?
  ✅ Explain parallel data fetching
  ✅ What is request memoization?

API & MIDDLEWARE:
  ✅ How do Route Handlers work in the App Router?
  ✅ What is middleware in Next.js?
  ✅ What can you do in middleware?
  ✅ What is Edge Runtime vs Node.js Runtime?

PERFORMANCE & SEO:
  ✅ How does Image optimization work?
  ✅ How does Font optimization work?
  ✅ How do you handle metadata/SEO?
  ✅ What is dynamic metadata?
  ✅ How does code splitting work in Next.js?
  ✅ What are the caching layers in Next.js?
  ✅ How to use dynamic imports for lazy loading?

AUTHENTICATION:
  ✅ How does authentication work in Next.js?
  ✅ What is NextAuth.js?
  ✅ How to protect routes in Next.js?
  ✅ Difference between middleware auth and layout auth?

DEPLOYMENT:
  ✅ How to deploy Next.js on Vercel?
  ✅ What is the difference between npm run build and npm run dev?
  ✅ How do environment variables work?
  ✅ What is the output mode (standalone)?

ADVANCED:
  ✅ What are Parallel Routes?
  ✅ What are Intercepting Routes?
  ✅ How does i18n work?
  ✅ What is the Edge Runtime?
  ✅ How to handle error boundaries in Next.js?
```

---

## PART 18: WHAT COMES AFTER NEXT.JS

```
AFTER MASTERING NEXT.JS, LEARN THESE:

IMMEDIATE NEXT (High priority):
  ✅ TypeScript (Deep) — Required everywhere
  ✅ Prisma (Advanced) — Complex queries, migrations
  ✅ shadcn/ui — THE UI library for Next.js
  ✅ Zod — Schema validation everywhere
  ✅ tRPC — Type-safe API layer (T3 stack)
  
  Time: 2-3 weeks each

MEDIUM PRIORITY:
  ✅ Drizzle ORM — Lighter Prisma alternative
  ✅ Stripe/Payments — Required for SaaS
  ✅ Uploadthing/Cloudinary — File uploads
  ✅ Resend/React Email — Transactional emails
  ✅ Pusher/Socket.io — Real-time features
  ✅ Redis/Upstash — Caching, rate limiting
  ✅ Docker — Containerization
  ✅ CI/CD — GitHub Actions

THE T3 STACK (Most popular full-stack combo):
  Next.js + TypeScript + tRPC + Prisma + Tailwind + NextAuth
  → create.t3.gg

ALTERNATIVE FRAMEWORKS TO EXPLORE:
  Remix — React alternative to Next.js
  Astro — Content-focused sites
  SvelteKit — Svelte's framework
  Nuxt — Vue.js framework

CAREER PATH:
  Junior Next.js Developer → 0-2 years
  Mid Full-Stack (Next.js) → 2-4 years
  Senior Full-Stack → 4-7 years
  Lead/Staff Engineer → 7+ years

SALARY RANGE (India, 2025):
  Fresher (Next.js): 5-10 LPA
  1-2 years: 10-18 LPA
  3-5 years: 18-35 LPA
  5+ years: 35-70 LPA

SALARY RANGE (US/Remote):
  Junior: $70-100K
  Mid: $100-150K
  Senior: $150-220K
  Staff: $200K+
```

---

## MONTH-BY-MONTH OVERVIEW

```
MONTH   FOCUS                              OUTCOME
─────   ─────                              ───────
  1     Fundamentals + Routing             Build static & 
        Server/Client Components           dynamic pages
        Data Fetching + Rendering          
        
  2     Server Actions + Database          Full CRUD apps
        Authentication (NextAuth)          with auth
        API Routes + Middleware            
        
  3     Advanced Features + Projects       Build 2-3
        Caching, ISR, Streaming            full apps
        E-Commerce Project                 
        
  4     SaaS / Complex Projects            Production-
        Payments, Real-time                ready apps
        Performance Optimization           
        
  5     TypeScript Deep + Portfolio         JOB
        Deploy all projects                READY! 🚀
        Interview Preparation              
```

**Next.js is THE most in-demand React framework in 2025.**
**Full-stack in ONE project. Server Components are the future.**
**Build projects. Deploy on Vercel. Get hired.**
**Every project teaches you more than 10 tutorials.** 🚀
