---
description: List all saved DNA presets from your global presets directory.
---

# List DNA Presets

## Workflow

### Step 1: Check presets directory

Read `~/.project-dna/presets/` directory.

If directory doesn't exist or is empty:
```
No saved presets yet.

Get started:
  /claude-dna:extract    Capture DNA from your current project
  /claude-dna:export     Save extracted DNA to your global presets
```

### Step 2: List presets

For each `.json` file in the presets directory, read and display:

```
Your DNA Presets
────────────────

1. my-saas-style (v1.0.0)
   "My personal SaaS builder preset"
   From: AIxMinutes | Stack: Next.js 15.1 + Supabase + Tailwind
   Saved: 2026-03-08

2. minimal-dashboard (v1.0.0)
   "Clean dashboard with minimal design"
   From: AdminPanel | Stack: Next.js 14 + Prisma + Tailwind
   Saved: 2026-02-15

3. mobile-first (v2.0.0)
   "React Native + Expo preset"
   From: MyApp | Stack: Expo 51 + Supabase + NativeWind
   Saved: 2026-01-20

Commands:
  /claude-dna:apply {name}     Apply a preset to current project
  /claude-dna:diff {a} {b}     Compare two presets
  /claude-dna:import {path}    Import a preset from file
```

### Step 3: If current project has DNA

Also show:
```
Current project: .project-dna/dna.json → "{name}" v{version}
```
