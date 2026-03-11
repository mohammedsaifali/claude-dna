---
description: Audit the current project against its saved DNA preset. Finds drift — colors not in palette, missing patterns, dependency version mismatches, convention violations.
---

# Audit Project DNA

## Workflow

### Step 1: Load DNA

Read `.project-dna/dna.json`. If not found, tell user to run `/claude-dna:extract` first.

### Step 2: Scan current project

For each DNA category, compare the preset against actual project state:

#### Tech Stack Drift
- Compare `package.json` dependencies against DNA versions
- Flag major version bumps or missing packages
- Flag new dependencies not in DNA

#### Design Token Drift
- Read current `globals.css` and compare CSS variables against DNA
- Read current `tailwind.config.*` and compare theme values
- Flag: new colors not in DNA palette, changed spacing, modified radius

#### Typography Drift
- Check if fonts in layout match DNA
- Check if font weights match
- Flag new font families

#### Component Pattern Drift
- Sample components and check against DNA patterns
- Flag: new UI libraries, changed form handling, different modal patterns

#### Architecture Drift
- Check directory structure against DNA
- Flag naming convention violations
- Check import alias consistency

#### Convention Drift
- Check file sizes against max limits
- Flag mutation patterns (if immutability = true in DNA)
- Check error handling patterns

### Step 3: Report

Display findings grouped by severity:

```
DNA Audit: "{name}" v{version}
─────────────────────────────────

DRIFT DETECTED (7 items)

[HIGH] Design Tokens
  - New color #FF6B35 used in 3 files (not in DNA palette)
  - Spacing 18px used in header.tsx (not in 4px scale)

[MEDIUM] Dependencies
  - framer-motion upgraded 11.0 → 12.1 (major bump)
  - New package: @tanstack/react-query (not in DNA)

[LOW] Conventions
  - components/BigForm.tsx is 847 lines (DNA max: 800)
  - lib/helpers.ts uses mutation pattern (line 42)

NO DRIFT
  ✓ Typography (fonts match)
  ✓ Architecture (structure matches)
  ✓ Tooling (configs match)
```

### Step 4: Offer fixes

For each drift item, offer:
- **Fix** — align the code with DNA
- **Accept** — update the DNA to include the new value
- **Skip** — ignore for now

If user accepts changes, update `.project-dna/dna.json` with the new values.
