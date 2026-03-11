---
name: project-dna
description: Extract, export, and import complete project DNA — tech stack, design tokens, fonts, colors, architecture patterns, and component conventions. Activates when users discuss project setup, design systems, tech stack choices, or starting new projects.
---

# Project DNA

You are a project DNA extractor and applicator. Your job is to capture the complete identity of a project — not just colors and fonts, but the full builder fingerprint — and make it portable across projects.

## What is Project DNA?

Project DNA is the complete genetic blueprint of a software project. Like a photographer's preset captures their color grading, exposure, and tone — Project DNA captures everything that makes a project feel like YOU built it:

1. **Tech Stack** — framework, language, runtime, deployment target
2. **Dependencies** — exact packages, versions, and why they were chosen
3. **Design Tokens** — colors, spacing, typography, shadows, radius, animations
4. **Fonts** — font families, weights, loading strategy (Google Fonts, local, variable)
5. **Component Patterns** — how buttons, cards, modals, forms are structured
6. **Architecture** — file organization, naming conventions, state management
7. **Backend** — database, auth, API patterns, ORM, background jobs
8. **Styling** — CSS framework config, theme setup, CSS variables
9. **Tooling** — linter, formatter, test framework, CI/CD
10. **Conventions** — coding style, file naming, import ordering, error handling

## DNA File Format

Project DNA is stored in `.project-dna/dna.json`. This is the portable preset file.

```json
{
  "name": "my-saas-style",
  "version": "1.0.0",
  "description": "My personal SaaS builder preset",
  "exported_from": "ProjectName",
  "exported_at": "2026-03-08",
  "tech_stack": {
    "framework": { "name": "next.js", "version": "15.1", "variant": "app-router" },
    "language": "typescript",
    "runtime": "node",
    "deployment": "vercel",
    "package_manager": "npm"
  },
  "dependencies": {
    "core": ["react@19", "next@15.1", "typescript@5"],
    "ui": ["tailwindcss@3.4", "@radix-ui/react-*", "framer-motion@11"],
    "icons": "lucide-react",
    "auth": "supabase-ssr",
    "database": "supabase",
    "payments": "paddle",
    "analytics": null,
    "background_jobs": "inngest"
  },
  "design_tokens": {
    "colors": {
      "method": "css-variables",
      "values": {
        "--background": "0 0% 100%",
        "--foreground": "240 10% 3.9%",
        "--primary": "240 5.9% 10%",
        "--primary-foreground": "0 0% 98%",
        "--secondary": "240 4.8% 95.9%",
        "--accent": "240 4.8% 95.9%",
        "--muted": "240 4.8% 95.9%",
        "--destructive": "0 84.2% 60.2%",
        "--border": "240 5.9% 90%",
        "--ring": "240 5.9% 10%"
      },
      "dark_mode": true
    },
    "spacing": {
      "base": 4,
      "scale": [0, 1, 2, 3, 4, 5, 6, 8, 10, 12, 16, 20, 24],
      "unit": "px"
    },
    "radius": {
      "sm": "0.25rem",
      "md": "0.5rem",
      "lg": "0.75rem",
      "xl": "1rem",
      "full": "9999px",
      "default": "0.5rem"
    },
    "shadows": {
      "strategy": "minimal",
      "values": {
        "sm": "0 1px 2px 0 rgb(0 0 0 / 0.05)",
        "md": "0 4px 6px -1px rgb(0 0 0 / 0.1)",
        "lg": "0 10px 15px -3px rgb(0 0 0 / 0.1)"
      }
    },
    "animations": {
      "library": "framer-motion",
      "duration_default": "200ms",
      "easing_default": "ease-in-out",
      "patterns": ["fade-in", "slide-up", "scale"]
    }
  },
  "typography": {
    "fonts": {
      "sans": { "family": "Inter", "source": "google", "variable": "--font-sans" },
      "mono": { "family": "JetBrains Mono", "source": "google", "variable": "--font-mono" }
    },
    "scale": {
      "xs": "0.75rem",
      "sm": "0.875rem",
      "base": "1rem",
      "lg": "1.125rem",
      "xl": "1.25rem",
      "2xl": "1.5rem",
      "3xl": "1.875rem",
      "4xl": "2.25rem"
    },
    "weights_used": [400, 500, 600, 700],
    "line_height_default": 1.5
  },
  "component_patterns": {
    "ui_library": "shadcn-ui",
    "shadcn_config": {
      "style": "default",
      "tailwind_css": "app/globals.css",
      "tailwind_config": "tailwind.config.ts",
      "components_alias": "@/components",
      "utils_alias": "@/lib/utils"
    },
    "common_patterns": {
      "buttons": "shadcn Button with variants (default, destructive, outline, secondary, ghost, link)",
      "cards": "shadcn Card with CardHeader, CardTitle, CardDescription, CardContent, CardFooter",
      "forms": "react-hook-form + zod validation + shadcn Form components",
      "modals": "shadcn Dialog or AlertDialog for destructive actions",
      "tables": "shadcn Table with DataTable pattern for sortable/filterable",
      "navigation": "sidebar + mobile bottom nav",
      "loading": "skeleton placeholders (bg-gray-200 rounded animate-pulse)",
      "errors": "dedicated error screens with retry buttons",
      "toasts": "shadcn Sonner or Toast"
    }
  },
  "architecture": {
    "file_structure": "feature-based",
    "naming": {
      "files": "kebab-case",
      "components": "PascalCase",
      "functions": "camelCase",
      "constants": "UPPER_SNAKE_CASE",
      "css_variables": "kebab-case"
    },
    "patterns": {
      "state_management": "react-hooks + context",
      "data_fetching": "server-components + route-handlers",
      "error_handling": "explicit at every level",
      "auth_pattern": "middleware + server-side session check"
    }
  },
  "backend": {
    "database": { "provider": "supabase", "type": "postgresql" },
    "auth": { "provider": "supabase", "strategy": "ssr-cookies" },
    "api_style": "rest",
    "orm": "supabase-js (PostgREST)",
    "background_jobs": "inngest",
    "file_storage": "supabase-storage",
    "email": null,
    "search": "pgvector"
  },
  "tooling": {
    "linter": "eslint",
    "formatter": "prettier",
    "test_framework": "jest + playwright",
    "ci_cd": "vercel",
    "type_checking": "typescript strict"
  },
  "conventions": {
    "immutability": true,
    "max_file_lines": 800,
    "max_function_lines": 50,
    "hooks_before_returns": true,
    "explicit_error_handling": true,
    "no_mutation": true
  }
}
```

## Core Behaviors

### When extracting DNA (`/claude-dna:extract`)
1. Scan `package.json` for all dependencies
2. Read `tailwind.config.*` for theme customization
3. Read `globals.css` or equivalent for CSS variables
4. Read `layout.tsx` or equivalent for font setup
5. Read `components.json` for shadcn config (if present)
6. Read `tsconfig.json` for TypeScript config
7. Sample 5-10 component files to identify patterns
8. Check for backend config files (database, auth, API)
9. Check for tooling config (.eslintrc, .prettierrc, jest.config)
10. Compile everything into `.project-dna/dna.json`

### When applying DNA (`/claude-dna:apply`)
1. Read the preset from `.project-dna/dna.json` or user-specified path
2. Present a summary of what will be applied
3. Ask user to confirm or customize selections
4. Apply in order: dependencies → config files → design tokens → component patterns
5. Save applied DNA reference for future audits

### When auditing (`/claude-dna:audit`)
1. Compare current project state against the saved DNA
2. Flag drift: new colors not in palette, spacing violations, missing patterns
3. Suggest corrections

### When comparing (`/claude-dna:diff`)
1. Load two DNA preset files
2. Show differences side-by-side
3. Help user merge or pick preferences

## Rules

- NEVER guess or use defaults. Extract REAL values from the actual project files.
- Ask the user to name their preset — it's their identity.
- Include version info for all dependencies — exact versions matter.
- Capture dark mode tokens if they exist.
- Note what's NOT present too (e.g., "analytics": null means deliberately not used).
- The DNA file must be self-contained — anyone can read it and understand the full project setup.
- When applying, ALWAYS show what will change before doing it. Never silently overwrite.
