---
description: Apply a saved DNA preset to the current project. Sets up tech stack, design tokens, fonts, and conventions from a previously extracted preset.
---

# Apply Project DNA

Read `../skills/project-dna/SKILL.md` first — it defines the DNA format.

## Apply Workflow

### Step 1: Load the preset

Check for DNA in this order:
1. If `$ARGUMENTS` is provided, treat it as a path to a `dna.json` file
2. Check `.project-dna/dna.json` in current directory
3. Check `~/.project-dna/presets/` for saved global presets
4. If nothing found, tell the user and suggest `/claude-dna:extract` or `/claude-dna:list`

### Step 2: Present the DNA summary

Show the user what will be applied:

```
DNA Preset: "my-saas-style" (v1.0.0)
Exported from: AIxMinutes on 2026-03-08

Tech Stack:
  Framework: Next.js 15.1 (App Router)
  Language: TypeScript
  Deployment: Vercel

Design:
  Colors: 10 CSS variables (light + dark mode)
  Fonts: Inter (sans), JetBrains Mono (mono)
  Spacing: 4px base scale
  Radius: 0.5rem default
  Shadows: Minimal strategy
  Animations: Framer Motion

UI:
  Library: shadcn/ui (default style)
  Components: Button, Card, Dialog, Form, Table, Toast

Backend:
  Database: Supabase (PostgreSQL)
  Auth: Supabase SSR
  Background Jobs: Inngest

Tooling:
  Linter: ESLint
  Formatter: Prettier
  Tests: Jest + Playwright
```

### Step 3: Ask what to apply

Let the user choose:
- **Full DNA** — apply everything (for greenfield projects)
- **Design only** — colors, fonts, spacing, shadows, animations
- **Tech stack only** — framework, dependencies, config
- **Backend only** — database, auth, API patterns
- **Cherry-pick** — let user select specific sections

### Step 4: Apply in order

For a full application:

1. **Initialize project** (if empty directory)
   - Run framework scaffolding command (e.g., `npx create-next-app@{version}`)
   - Apply TypeScript config from DNA

2. **Install dependencies**
   - Install core deps from DNA
   - Install UI deps
   - Install backend deps
   - Install dev deps / tooling

3. **Apply design tokens**
   - Write/merge `tailwind.config.ts` with DNA theme
   - Write/merge `globals.css` with DNA CSS variables
   - Set up fonts in layout file
   - Write `components.json` for shadcn (if used)

4. **Apply architecture**
   - Create directory structure matching DNA patterns
   - Set up import aliases in tsconfig
   - Create utility files (cn, utils)

5. **Apply tooling**
   - Write linter config
   - Write formatter config
   - Write test config

6. **Apply conventions**
   - Save DNA as `.project-dna/dna.json` for future audits

### Step 5: Summary

Show what was applied and what the user should do next.

## Rules

- ALWAYS show what will change before applying. Never silently overwrite existing files.
- If the project already has files, ask before overwriting each one.
- For existing projects, MERGE don't replace — add DNA tokens to existing config rather than overwriting.
- If a dependency version conflicts with an existing one, flag it and let the user decide.
- After applying, suggest running `/claude-dna:audit` to verify.
