---
name: project-scaffold
description: "When the user wants to scaffold a brand-new full-stack project from scratch with an opinionated, production-ready stack — Next.js 15 + TypeScript + Tailwind + shadcn/ui + Supabase + Vercel. Also use when the user says 'start a new project,' 'scaffold an app,' 'set up a Next.js project,' 'bootstrap a full-stack app,' or 'new project with Supabase.' Walks through the full setup in order: app creation, dependencies, shadcn, Supabase client/middleware, env, git, and deploy."
metadata:
  version: 1.0.0
---

# Project Scaffold

Scaffold a full-stack project with Next.js 15 + TypeScript + Tailwind + shadcn/ui + Supabase + Vercel.

## Description
Creates a complete, production-ready project from scratch with an opinionated, conventional tech stack.

## When to Use
When starting a brand new project from scratch.

## Instructions

Follow the steps below in order. Stop and report if any step fails.

### Step 1: Create Next.js app
```bash
pnpm create next-app@latest <project-name> --typescript --tailwind --eslint --app --src-dir --import-alias "@/*"
cd <project-name>
```

### Step 2: Install core dependencies
```bash
pnpm add @supabase/supabase-js @supabase/ssr zod
pnpm add -D @types/node prettier prettier-plugin-tailwindcss
```

### Step 3: Install shadcn/ui
```bash
pnpm dlx shadcn@latest init -d
```

### Step 4: Add common shadcn components
```bash
pnpm dlx shadcn@latest add button card input label form toast sonner
```

### Step 5: Initialize Supabase
```bash
supabase init
```

### Step 6: Create Supabase client files
Create:
- `src/lib/supabase/client.ts` — Browser client using `createBrowserClient`
- `src/lib/supabase/server.ts` — Server client using `createServerClient` with cookies
- `src/lib/supabase/middleware.ts` — Middleware helper for auth session refresh

### Step 7: Create utility files
- `src/lib/utils.ts` — cn() helper for Tailwind class merging
- `src/lib/types.ts` — Shared TypeScript types

### Step 8: Set up middleware
Create `src/middleware.ts` for Supabase auth session refresh.

### Step 9: Create .env.example
```
# Supabase
NEXT_PUBLIC_SUPABASE_URL=your-project-url
NEXT_PUBLIC_SUPABASE_ANON_KEY=your-anon-key
SUPABASE_SERVICE_ROLE_KEY=your-service-role-key

# App
NEXT_PUBLIC_APP_URL=http://localhost:3000
```

### Step 10: Set up local secrets
Copy `.env.example` to `.env.local` and fill in your real Supabase project values:
```bash
cp .env.example .env.local
```
Keep production secrets in your deployment platform's environment settings (e.g. Vercel) or a secrets manager — never commit `.env.local`.

### Step 11: Update .gitignore
Ensure these are included:
```
.env.local
.env
node_modules
.vercel
```

### Step 12: Create initial layout
Update `src/app/layout.tsx` with proper metadata and font setup.
Update `src/app/page.tsx` with a clean landing page.

### Step 13: Add Prettier config
Create `.prettierrc`:
```json
{
  "semi": false,
  "singleQuote": true,
  "tabWidth": 2,
  "trailingComma": "es5",
  "plugins": ["prettier-plugin-tailwindcss"]
}
```

### Step 14: Git init and first commit
```bash
git init
git add -A
git commit -m "feat: initial scaffold with Next.js 15, Supabase, shadcn/ui"
```

### Step 15: Add project conventions
Add the conventions your workflow expects, for example:
- An agent instruction file (e.g. `CLAUDE.md`, `AGENTS.md`) documenting the stack and conventions.
- An `.nvmrc` pinning the Node version.
- Any slash-command or editor instruction files your team uses.

### Step 16: Create the GitHub repo and push
```bash
gh repo create <project-name> --public --source=. --push
```
Use `--private` instead if the project should not be public.

### Step 17: Verify
```bash
pnpm dev
```
Open http://localhost:3000 and confirm it loads.

## Post-Scaffold
- Link Vercel: `vercel link`
- Link Supabase: `supabase link --project-ref <ref>`
- Store your Supabase keys in your deployment platform's environment settings or a secrets manager.
- Start your dev environment with secrets loaded, per your local setup.

## Output
Print a summary of everything created:
- Files created
- Dependencies installed
- Next steps for the developer
