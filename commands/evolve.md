---
description: Update the current project's DNA preset with changes you've made. Captures your evolved design language without re-extracting everything.
---

# Evolve Project DNA

## Workflow

### Step 1: Load current DNA

Read `.project-dna/dna.json`. If not found, suggest `/claude-dna:extract`.

### Step 2: Detect changes

Run the same scans as `/claude-dna:audit` but instead of flagging drift, present it as evolution:

```
DNA Evolution Detected
──────────────────────

Your project has evolved since the last DNA capture:

Design Tokens
  + Added color: --warning (38 92% 50%)
  ~ Changed radius default: 0.5rem → 0.75rem

Dependencies
  + Added: @tanstack/react-query@5.0
  ↑ Upgraded: framer-motion 11.0 → 12.1

Component Patterns
  + New pattern: Combobox (shadcn Command-based)
  ~ Changed loading: skeleton → shimmer animation
```

### Step 3: Accept evolution

For each change, ask:
- **Accept** — update DNA with this change
- **Reject** — keep the original DNA value (means the project drifted unintentionally)
- **Accept all** — update everything

### Step 4: Save

1. Bump the version (patch for small changes, minor for significant evolution)
2. Update `.project-dna/dna.json`
3. Ask if user wants to also update the global preset (`/claude-dna:export`)

```
DNA evolved: "{name}" v1.0.0 → v1.1.0
  3 tokens updated, 2 dependencies added, 1 pattern changed

Run /claude-dna:export to update your global preset
```
