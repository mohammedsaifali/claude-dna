---
description: Compare two DNA presets side-by-side to see differences in tech stack, design, and architecture choices.
---

# Diff Project DNA

## Workflow

### Step 1: Load two presets

Parse `$ARGUMENTS` for two sources. Accepts:
- Two preset names: `/project-dna:diff my-saas-style minimal-dashboard`
- Two file paths: `/project-dna:diff ./project-a/dna.json ./project-b/dna.json`
- One argument + current: `/project-dna:diff my-saas-style` (compares against current `.project-dna/dna.json`)

If only one or no arguments, ask the user to specify what to compare.

### Step 2: Compare

Walk through each DNA section and show differences:

```
DNA Diff: "my-saas-style" vs "minimal-dashboard"
─────────────────────────────────────────────────

Tech Stack
  Framework:     Next.js 15.1 (both)
  Deployment:    vercel vs cloudflare-pages  ← DIFFERENT

Design Tokens
  Colors:        10 vars vs 6 vars  ← DIFFERENT
    + my-saas-style has: --accent, --muted, --ring, --destructive
  Spacing:       4px base (both)
  Radius:        0.5rem vs 0.25rem  ← DIFFERENT
  Shadows:       minimal vs none  ← DIFFERENT

Typography
  Sans:          Inter vs Geist  ← DIFFERENT
  Mono:          JetBrains Mono (both)

Backend
  Database:      supabase vs planetscale  ← DIFFERENT
  Auth:          supabase-ssr vs clerk  ← DIFFERENT
```

### Step 3: Offer merge

Ask if user wants to:
- **Merge** — create a new preset combining the best of both
- **Pick one** — use one preset as the base
- **Done** — just wanted to see the diff
