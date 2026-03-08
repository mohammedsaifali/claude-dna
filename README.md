<h1 align="center">🧬 Claude DNA</h1>

<p align="center">
  <strong>Extract, export, and import your complete project DNA.</strong><br/>
  Like a photographer's preset — but for your entire builder identity.
</p>

<p align="center">
  <a href="#installation"><img src="https://img.shields.io/badge/Claude_Code-Plugin-7c3aed?style=for-the-badge&logo=anthropic&logoColor=white" alt="Claude Code Plugin" /></a>
  <a href="https://opensource.org/licenses/MIT"><img src="https://img.shields.io/badge/License-MIT-22c55e?style=for-the-badge" alt="MIT License" /></a>
  <a href="#commands"><img src="https://img.shields.io/badge/Commands-9-3b82f6?style=for-the-badge" alt="9 Commands" /></a>
  <a href="#what-gets-captured"><img src="https://img.shields.io/badge/Captures-10_Categories-f59e0b?style=for-the-badge" alt="10 Categories" /></a>
</p>

<br/>

<p align="center">
  <em>Every time you start a new project, you re-make the same decisions.<br/>
  Framework. Colors. Fonts. Component library. File structure. Auth. Database.<br/><br/>
  <strong>What if you could capture all of that once — and replay it everywhere?</strong></em>
</p>

---

## The Problem

You've built a great project. Your design language is dialed in — the colors, the fonts, the spacing, the animations. Your tech stack works. Your architecture makes sense.

Then you start a new project. And you do it all again from scratch.

- Re-pick the same framework, same version
- Re-configure Tailwind with the same custom theme
- Re-set up the same CSS variables
- Re-install the same 30 packages
- Re-create the same button variants, card styles, navigation patterns
- Re-configure the same linter, formatter, test setup

**Claude DNA solves this.** One command to extract. One command to apply. Your builder identity, portable.

## How It Works

```
┌─────────────────┐         ┌──────────────┐         ┌─────────────────┐
│  Your Project    │  ──►    │   dna.json   │  ──►    │  New Project     │
│                  │ extract │              │  apply  │                  │
│  • Tech stack    │         │  Portable    │         │  Same fonts      │
│  • Design tokens │         │  preset      │         │  Same colors     │
│  • Fonts & colors│         │  file        │         │  Same patterns   │
│  • Components    │         │              │         │  Same stack      │
│  • Architecture  │         │  ~4KB JSON   │         │  Same YOU        │
│  • Backend       │         │              │         │                  │
│  • Tooling       │         │              │         │                  │
└─────────────────┘         └──────────────┘         └─────────────────┘
```

Think of it like:
- **Lightroom presets** — but for code
- **Figma design tokens** — but including your entire stack
- **Boilerplate generators** — but extracted from YOUR actual projects, not generic templates

---

## Installation

### From Marketplace (recommended)

```bash
# Step 1: Add the marketplace
/plugin marketplace add cp-saif/claude-dna

# Step 2: Install the plugin
/plugin install claude-dna

# Step 3: Restart Claude Code
```

### Local Development

```bash
git clone https://github.com/cp-saif/claude-dna.git
claude --plugin-dir ./claude-dna
```

### Requirements

- [Claude Code](https://claude.com/code) v1.0.33+
- That's it. No dependencies.

---

## Quick Start

### 1. Extract DNA from your best project

```bash
cd ~/projects/my-awesome-app
```

```
> /claude-dna:extract

Scanning project...

✓ Tech Stack:    Next.js 15.1 (App Router) + TypeScript
✓ Design Tokens: 35 CSS variables (light + dark mode)
✓ Typography:    Geist Sans + Geist Mono + Instrument Serif
✓ Components:    shadcn/ui (new-york) — 8 button variants, cards, dialogs
✓ Architecture:  Feature-based, kebab-case files, @/* aliases
✓ Backend:       Supabase + Inngest + Paddle
✓ Tooling:       ESLint + Vitest + Playwright

What would you like to name this preset? > my-saas-style

✓ Saved to .project-dna/dna.json
```

### 2. Export to your global preset library

```
> /claude-dna:export

✓ Exported "my-saas-style" v1.0.0 to ~/.project-dna/presets/my-saas-style.json
```

### 3. Start a new project with your DNA

```bash
mkdir ~/projects/new-idea && cd ~/projects/new-idea
```

```
> /claude-dna:apply my-saas-style

DNA Preset: "my-saas-style" v1.0.0
Exported from: my-awesome-app on 2026-03-08

Apply: [Full DNA] [Design only] [Tech stack only] [Cherry-pick]
> Full DNA

✓ Scaffolded Next.js 15.1 with TypeScript
✓ Installed 30 dependencies
✓ Applied 35 CSS variables (light + dark)
✓ Set up Geist Sans + Geist Mono + Instrument Serif
✓ Configured shadcn/ui (new-york style)
✓ Created directory structure
✓ Applied conventions

Done! Your project has your DNA.
```

### 4. Evolve your style over time

```
> /claude-dna:evolve

DNA Evolution Detected:
  + Added color:   --warning (38 92% 50%)
  ↑ Upgraded:      framer-motion 11.0 → 12.1
  ~ Changed:       radius default 0.5rem → 0.75rem
  + New pattern:   Combobox (command-based)

Accept all? > yes

✓ DNA evolved: "my-saas-style" v1.0.0 → v1.1.0
```

---

## Commands

| Command | Description |
|:--------|:------------|
| `/claude-dna:extract` | Scan the current project and capture its complete DNA into `.project-dna/dna.json` |
| `/claude-dna:apply` | Apply a saved DNA preset to the current project — full, design-only, or cherry-pick |
| `/claude-dna:status` | Display the current project's DNA summary in a formatted view |
| `/claude-dna:export` | Save DNA to your global presets directory (`~/.project-dna/presets/`) |
| `/claude-dna:import` | Import a preset from a file path, URL, or named global preset |
| `/claude-dna:list` | List all saved presets with metadata |
| `/claude-dna:audit` | Check for drift between the current project and its saved DNA |
| `/claude-dna:diff` | Compare two DNA presets side-by-side |
| `/claude-dna:evolve` | Detect intentional changes and update the DNA to match |

---

## What Gets Captured?

Claude DNA doesn't just capture colors. It captures **everything** that makes your project feel like you built it.

<table>
<tr>
<td width="50%">

### Design & Frontend

| Category | What's Captured |
|:---------|:----------------|
| **Design Tokens** | CSS variables, color scales (light + dark), spacing base & scale, border radius, shadow strategy |
| **Typography** | Font families, sources (Google/local/package), CSS variables, weight scale, line heights |
| **Animations** | Library (Framer Motion, GSAP), keyframes, durations, easing, delay scales, patterns |
| **Effects** | Glass morphism, gradients, glow effects, shimmer, section separators |
| **Components** | UI library config, button variants, card patterns, form handling, modals, navigation, loading states, toast patterns |

</td>
<td width="50%">

### Stack & Architecture

| Category | What's Captured |
|:---------|:----------------|
| **Tech Stack** | Framework + version + variant, language, runtime, deployment target, package manager |
| **Dependencies** | All packages with versions, grouped by purpose (core, UI, auth, DB, payments, etc.) |
| **Architecture** | File structure pattern, naming conventions, import aliases, state management, data fetching |
| **Backend** | Database, auth provider + strategy, API style, ORM, background jobs, file storage, email, search |
| **Tooling** | Linter, formatter, test framework, CI/CD, type checking, analytics |
| **Conventions** | Immutability rules, file size limits, error handling patterns, coding standards |

</td>
</tr>
</table>

---

## DNA File Format

Your DNA is stored as a single, portable JSON file at `.project-dna/dna.json`. It's human-readable, version-controlled, and self-documenting.

<details>
<summary><strong>View example dna.json</strong> (click to expand)</summary>

```json
{
  "name": "my-saas-style",
  "version": "1.0.0",
  "description": "Modern SaaS preset — glass morphism, purple accent, Geist fonts",
  "exported_from": "AIxMinutes",
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
    "ui": ["tailwindcss@3.4", "framer-motion@12", "lucide-react@0.475"],
    "auth": "@supabase/ssr@0.8",
    "database": "@supabase/supabase-js@2.48",
    "payments": "@paddle/paddle-js@1.6",
    "background_jobs": "inngest@3.52",
    "analytics": "@vercel/analytics@1.6"
  },

  "design_tokens": {
    "colors": {
      "method": "css-variables",
      "light": {
        "--background": "0 0% 100%",
        "--foreground": "0 0% 3.9%",
        "--primary": "0 0% 9%",
        "--brand": "267 100% 67%"
      },
      "dark": {
        "--background": "220 20% 7%",
        "--foreground": "210 20% 96%",
        "--primary": "210 20% 96%",
        "--brand": "280 100% 75%"
      },
      "dark_mode": true
    },
    "spacing": { "base": 4, "unit": "px" },
    "radius": { "default": "0.5rem" },
    "shadows": { "strategy": "minimal with glow accents" }
  },

  "typography": {
    "fonts": {
      "sans": { "family": "Geist Sans", "source": "package" },
      "mono": { "family": "Geist Mono", "source": "package" },
      "accent": { "family": "Instrument Serif", "source": "google" }
    }
  },

  "component_patterns": {
    "ui_library": "shadcn-ui",
    "shadcn_config": { "style": "new-york" }
  },

  "backend": {
    "database": { "provider": "supabase", "type": "postgresql" },
    "auth": { "provider": "supabase", "strategy": "ssr-cookies" },
    "background_jobs": "inngest"
  }
}
```

</details>

See the [full schema reference](skills/project-dna/references/dna-schema.md) for all supported fields.

---

## Use Cases

### For Solo Builders

> *"I build SaaS products. Every one uses the same stack — Next.js, Supabase, Tailwind, shadcn. I use the same purple brand color, the same Geist font, the same glass morphism navbar. Claude DNA lets me start every project with MY identity already baked in."*

### For Agencies & Teams

> *"Our agency has a house style. Every client project starts with our design system — our colors, our component library, our architecture conventions. Claude DNA standardizes our starting point."*

### For Open Source

> *"I maintain a component library. Claude DNA lets users import our design language into their projects with one command. No manual setup."*

### For Design System Migration

> *"We're migrating from MUI to shadcn. Extract DNA from the old project, diff it against the new one, cherry-pick what to keep."*

---

## Workflow Diagram

```
                    ┌─────────────┐
                    │  Project A  │
                    │  (mature)   │
                    └──────┬──────┘
                           │
                    /claude-dna:extract
                           │
                    ┌──────▼──────┐
                    │  dna.json   │ ◄── Your builder fingerprint
                    └──────┬──────┘
                           │
              ┌────────────┼────────────┐
              │            │            │
     /claude-dna:export    │    /claude-dna:diff
              │            │            │
    ┌─────────▼──────┐     │     ┌──────▼──────┐
    │  ~/.project-dna │     │     │  Compare    │
    │  /presets/      │     │     │  presets    │
    └─────────┬──────┘     │     └─────────────┘
              │            │
              │    /claude-dna:apply
              │            │
    ┌─────────▼────────────▼──────────┐
    │         New Projects            │
    │  Project B  │  Project C  │ ... │
    └─────────────────────────────────┘
              │
     /claude-dna:evolve
              │
    ┌─────────▼──────┐
    │  dna.json      │ ◄── Updated with your evolved style
    │  v1.0 → v1.1   │
    └────────────────┘
```

---

## Plugin Structure

```
claude-dna/
├── .claude-plugin/
│   ├── plugin.json              # Plugin manifest
│   └── marketplace.json         # Marketplace config
├── commands/
│   ├── extract.md               # /claude-dna:extract
│   ├── apply.md                 # /claude-dna:apply
│   ├── status.md                # /claude-dna:status
│   ├── export.md                # /claude-dna:export
│   ├── import.md                # /claude-dna:import
│   ├── list.md                  # /claude-dna:list
│   ├── audit.md                 # /claude-dna:audit
│   ├── diff.md                  # /claude-dna:diff
│   └── evolve.md                # /claude-dna:evolve
├── skills/
│   └── project-dna/
│       ├── SKILL.md             # Core DNA extraction/application logic
│       └── references/
│           └── dna-schema.md    # Full JSON schema reference
├── reference/
│   └── presets/                 # Example preset files
├── README.md
├── LICENSE                      # MIT
└── .gitignore
```

---

## Philosophy

| Principle | What It Means |
|:----------|:-------------|
| **Your DNA, not someone else's** | Extract from YOUR projects, not generic templates. Your presets reflect your taste, your stack, your conventions. |
| **Complete, not partial** | Not just colors. The full stack — framework, backend, tooling, architecture, conventions. Everything. |
| **Portable** | One JSON file. Copy it, email it, commit it, share it. No vendor lock-in. |
| **Evolvable** | Your style changes over time. Your preset should too. Evolve incrementally, never start over. |
| **Non-destructive** | Always shows what will change before applying. Never silently overwrites. Merge, don't replace. |
| **Framework-agnostic** | Works with Next.js, React, Vue, Svelte, Go, Python — any project with config files. |

---

## Comparison

| Feature | Claude DNA | Boilerplate Repos | Figma Tokens | interface-design |
|:--------|:----------:|:-----------------:|:------------:|:----------------:|
| Extracts from YOUR project | Yes | No (generic) | No (design only) | Partial |
| Captures tech stack | Yes | Static | No | No |
| Captures design tokens | Yes | Sometimes | Yes | Yes |
| Captures backend config | Yes | Sometimes | No | No |
| Captures architecture | Yes | Static | No | No |
| Export/import presets | Yes | Git clone | Plugin sync | File-based |
| Evolve over time | Yes | Manual | Manual | No |
| Drift detection (audit) | Yes | No | No | Yes |
| Side-by-side diff | Yes | No | No | No |
| Cherry-pick application | Yes | No | Partial | No |

---

## Supported Ecosystems

Claude DNA extracts from any project. The extraction is AI-powered — Claude reads your actual config files and builds the DNA.

| Ecosystem | Detected From |
|:----------|:-------------|
| **Next.js / React** | `package.json`, `next.config.*`, `tailwind.config.*`, `components.json` |
| **Vue / Nuxt** | `package.json`, `nuxt.config.*`, `tailwind.config.*` |
| **Svelte / SvelteKit** | `package.json`, `svelte.config.*`, `tailwind.config.*` |
| **Python / Django / Flask** | `requirements.txt`, `pyproject.toml`, `settings.py` |
| **Go** | `go.mod`, project structure |
| **Rust** | `Cargo.toml`, project structure |
| **Flutter / Dart** | `pubspec.yaml`, theme files |
| **Swift / SwiftUI** | `Package.swift`, asset catalogs |

---

## Contributing

Contributions are welcome! Here's how:

1. **Fork** this repository
2. **Create** a feature branch (`git checkout -b feat/my-feature`)
3. **Commit** your changes (`git commit -m 'feat: add my feature'`)
4. **Push** to the branch (`git push origin feat/my-feature`)
5. **Open** a Pull Request

### Ideas for Contribution

- [ ] Community preset gallery (share your DNA publicly)
- [ ] Visual diff viewer (HTML report for `/claude-dna:diff`)
- [ ] Preset marketplace integration
- [ ] Framework-specific apply templates (Vue, Svelte, etc.)
- [ ] DNA merge tool (combine best parts of multiple presets)
- [ ] VS Code extension for previewing DNA

---

## Acknowledgments

- Inspired by [interface-design](https://github.com/Dammyjay93/interface-design) by Damola Akinleye — the craft, memory, and consistency approach
- Built on the [Claude Code Plugin System](https://code.claude.com/docs/en/plugins) by Anthropic
- Concept: design presets for code, like Lightroom presets for photography

---

## License

[MIT](LICENSE) — use it, fork it, share it, sell it. Just keep the license.

---

<p align="center">
  <strong>Build once. Apply everywhere.</strong><br/>
  <sub>Made with Claude DNA by <a href="https://github.com/cp-saif">Saif</a></sub>
</p>
