---
description: Extract the complete DNA from the current project — tech stack, design tokens, fonts, colors, architecture, and conventions. Saves to .project-dna/dna.json
---

# Extract Project DNA

Read `../skills/project-dna/SKILL.md` first — it defines the DNA format and extraction rules.

## Extraction Workflow

### Step 1: Discover project type

Scan the root directory for framework indicators:
- `package.json` → Node.js/JavaScript project
- `requirements.txt` / `pyproject.toml` → Python project
- `go.mod` → Go project
- `Cargo.toml` → Rust project
- `pubspec.yaml` → Flutter/Dart project
- `Package.swift` → Swift project

### Step 2: Extract tech stack

Read the primary config file (e.g., `package.json`) and extract:
- Framework + version
- All dependencies grouped by purpose (core, ui, auth, database, testing, tooling)
- Dev dependencies
- Scripts (build, dev, test, lint)

### Step 3: Extract design tokens

Scan for design configuration in order:
1. `tailwind.config.ts` / `tailwind.config.js` → custom theme (colors, fonts, spacing, extend block)
2. `globals.css` / `app/globals.css` / `src/globals.css` → CSS custom properties
3. `theme.ts` / `theme.js` → custom theme files
4. `components.json` → shadcn/ui configuration

Extract ALL custom values — colors, spacing, radius, shadows, animations, breakpoints.

### Step 4: Extract typography

1. Check `layout.tsx` / `layout.js` / `_app.tsx` for font imports
2. Check for Google Fonts, local fonts, or variable fonts
3. Note font families, weights used, and CSS variable names
4. Scan components for typography scale usage (text-xs through text-4xl)

### Step 5: Extract component patterns

Read 5-10 component files to identify:
- UI library (shadcn, MUI, Chakra, Ant Design, custom)
- Button variants and styles
- Card patterns
- Form handling (react-hook-form, formik, native)
- Modal/dialog patterns
- Navigation patterns
- Loading states (skeletons, spinners, shimmer)
- Error handling UI patterns
- Toast/notification patterns

### Step 6: Extract architecture

Analyze the directory structure:
- File organization (feature-based, type-based, flat)
- Naming conventions (kebab-case, camelCase, PascalCase for files)
- Import aliases (@/, ~/, #/)
- State management approach
- Data fetching patterns
- API route structure

### Step 7: Extract backend

Check for:
- Database config (supabase, prisma, drizzle, mongoose)
- Auth config (next-auth, supabase-auth, clerk, lucia)
- API style (REST, GraphQL, tRPC)
- Background jobs (inngest, bullmq, quirrel)
- File storage (s3, supabase-storage, cloudinary)
- Email (resend, sendgrid, postmark)

### Step 8: Extract tooling

Check for config files:
- `.eslintrc.*` → linter config
- `.prettierrc` / `prettier.config.*` → formatter config
- `jest.config.*` / `vitest.config.*` → test config
- `playwright.config.*` → e2e test config
- `tsconfig.json` → TypeScript settings

### Step 9: Compile and save

1. Compile all findings into the DNA JSON format (see SKILL.md)
2. Ask the user to **name their preset** (e.g., "my-saas-style", "minimal-dashboard")
3. Ask for a one-line description
4. Create `.project-dna/` directory
5. Save to `.project-dna/dna.json`
6. Display a summary of what was captured

### Step 10: Offer next steps

- "Run `/project-dna:status` to see your DNA summary"
- "Copy `.project-dna/dna.json` to any new project and run `/project-dna:apply`"
- "Run `/project-dna:export` to save to a global presets directory"

## Rules

- Extract REAL values only. Never insert placeholders or defaults.
- If a category has no data (e.g., no backend), set it to `null` — don't omit it.
- Include dependency versions — they matter for reproducibility.
- Ask the user before saving. Show them the full DNA first.
