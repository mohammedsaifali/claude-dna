<div align="center">

<br/>

# 🧬 Claude DNA

### Your builder identity. Extracted. Portable. Replayable.

<br/>

<p>
  <a href="#installation"><img src="https://img.shields.io/badge/Claude_Code-Plugin-7c3aed?style=for-the-badge&logo=anthropic&logoColor=white" alt="Claude Code Plugin" /></a>
  &nbsp;
  <a href="https://opensource.org/licenses/MIT"><img src="https://img.shields.io/badge/License-MIT-22c55e?style=for-the-badge" alt="MIT License" /></a>
  &nbsp;
  <a href="#commands"><img src="https://img.shields.io/badge/9_Commands-3b82f6?style=for-the-badge" alt="9 Commands" /></a>
  &nbsp;
  <a href="#-what-gets-captured"><img src="https://img.shields.io/badge/10_Categories-f59e0b?style=for-the-badge" alt="10 Categories" /></a>
</p>

<br/>

**Every time you start a new project, you remake the same 50 decisions.**<br/>
Framework. Colors. Fonts. Components. Auth. Database. File structure. Conventions.<br/><br/>
**What if you could capture all of that once — and replay it everywhere?**

<br/>

<img src="https://capsule-render.vercel.app/api?type=waving&color=7c3aed&height=2&section=header" width="100%" />

</div>

<br/>

## 💡 The Problem

You've perfected your stack. Your design language is dialed in. Then you start a new project — and do it all over again.

<table>
<tr>
<td>

```diff
- Re-pick the same framework, same version
- Re-configure Tailwind with the same custom theme
- Re-set up the same CSS variables (light + dark)
- Re-install the same 30 packages
- Re-create the same button variants, card styles, nav
- Re-configure the same linter, formatter, test setup
```

</td>
<td>

```diff
+ One command to extract your DNA
+ One command to apply it anywhere
+ Your taste. Your stack. Your conventions.
+ Portable as a single JSON file
+ Evolves with you over time
+ Never start from scratch again
```

</td>
</tr>
</table>

<br/>

## 🔬 How It Works

<div align="center">

```
  YOUR PROJECT                    DNA PRESET                    NEW PROJECT
 ┌──────────────┐              ┌──────────────┐              ┌──────────────┐
 │              │   extract    │              │    apply     │              │
 │  Tech Stack  │ ──────────► │              │ ───────────► │  Same Stack  │
 │  Design      │              │   dna.json   │              │  Same Design │
 │  Typography  │              │              │              │  Same Fonts  │
 │  Components  │              │   ~4KB JSON  │              │  Same Code   │
 │  Backend     │              │   Portable   │              │  Same YOU    │
 │  Tooling     │              │              │              │              │
 │  Conventions │              │              │              │              │
 └──────────────┘              └──────────────┘              └──────────────┘
```

</div>

<table>
<tr>
<td align="center" width="33%">
<br/>
<img src="https://img.shields.io/badge/Like-Lightroom_Presets-e879f9?style=flat-square" /><br/>
<sub>but for code</sub>
<br/><br/>
</td>
<td align="center" width="33%">
<br/>
<img src="https://img.shields.io/badge/Like-Figma_Tokens-a78bfa?style=flat-square" /><br/>
<sub>but with your entire stack</sub>
<br/><br/>
</td>
<td align="center" width="33%">
<br/>
<img src="https://img.shields.io/badge/Like-Boilerplates-818cf8?style=flat-square" /><br/>
<sub>but from YOUR real projects</sub>
<br/><br/>
</td>
</tr>
</table>

<br/>

<div align="center">
<img src="https://capsule-render.vercel.app/api?type=waving&color=7c3aed&height=2&section=header" width="100%" />
</div>

<br/>

## 🎬 See It In Action

> We extracted DNA from **AIxMinutes** (a production SaaS) and applied it to **FitPulse** (a fitness app). Different product. Identical design language. Zero manual CSS.

<br/>

<div align="center">

### 🔵 Source — AIxMinutes

<img src="assets/source-aixminutes.png" alt="AIxMinutes — source project" width="720" />

<br/>

<sub>Purple brand &nbsp;·&nbsp; Instrument Serif italics &nbsp;·&nbsp; Glass morphism navbar &nbsp;·&nbsp; Geist fonts &nbsp;·&nbsp; shadcn/ui</sub>

<br/><br/>

### 🟣 DNA Applied — FitPulse

<img src="assets/applied-fitpulse.png" alt="FitPulse hero — DNA applied" width="720" />

<br/><br/>

<img src="assets/applied-fitpulse-2.png" alt="FitPulse sections — DNA applied" width="720" />

<br/>

<sub>Same purple brand &nbsp;·&nbsp; Same italic serif accents &nbsp;·&nbsp; Same button styles &nbsp;·&nbsp; Same section patterns</sub><br/>
<sub>Footer reads: <em>"Built with DNA from AIxMinutes."</em></sub>

<br/><br/>

**`/claude-dna:extract` → `dna.json` → `/claude-dna:apply` → Done.**

</div>

<br/>

<div align="center">
<img src="https://capsule-render.vercel.app/api?type=waving&color=7c3aed&height=2&section=header" width="100%" />
</div>

<br/>

## 📦 Installation

### Option 1: Plugin Marketplace

```bash
/plugin marketplace add mohammedsaifali/claude-dna
```

### Option 2: Clone Locally

```bash
git clone https://github.com/mohammedsaifali/claude-dna.git ~/.claude/plugins/claude-dna
claude --plugin-dir ~/.claude/plugins/claude-dna
```

### Option 3: Copy Into Project

```bash
# Copy skills + commands into any project's .claude/ directory
cp -r claude-dna/skills/project-dna your-project/.claude/skills/
cp -r claude-dna/commands your-project/.claude/commands/
```

> **Requirements:** [Claude Code](https://claude.com/code) v1.0.33+ &nbsp;·&nbsp; No other dependencies.

<br/>

## 🚀 Quick Start

<details open>
<summary><strong>1. Extract DNA from your best project</strong></summary>

<br/>

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

</details>

<details>
<summary><strong>2. Export to your global preset library</strong></summary>

<br/>

```
> /claude-dna:export

✓ Exported "my-saas-style" v1.0.0 to ~/.project-dna/presets/my-saas-style.json
```

</details>

<details>
<summary><strong>3. Apply to a new project</strong></summary>

<br/>

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

</details>

<details>
<summary><strong>4. Evolve your style over time</strong></summary>

<br/>

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

</details>

<br/>

## 🛠 Commands

| Command | What It Does |
|:--------|:------------|
| **`/claude-dna:extract`** | Scan the current project and capture its complete DNA |
| **`/claude-dna:apply`** | Apply a DNA preset — full, design-only, tech-only, or cherry-pick |
| **`/claude-dna:status`** | Display formatted DNA summary for the current project |
| **`/claude-dna:export`** | Save DNA to global presets (`~/.project-dna/presets/`) |
| **`/claude-dna:import`** | Import a preset from file path, URL, or named preset |
| **`/claude-dna:list`** | List all saved presets with metadata |
| **`/claude-dna:audit`** | Detect drift between project and its saved DNA |
| **`/claude-dna:diff`** | Compare two DNA presets side-by-side |
| **`/claude-dna:evolve`** | Accept intentional changes and bump the preset version |

<br/>

## 🧩 What Gets Captured

> Claude DNA doesn't just capture colors. It captures **everything** that makes a project feel like *you* built it.

<table>
<tr>
<td width="50%" valign="top">

### 🎨 Design & Frontend

| | Category | Captures |
|:-:|:---------|:---------|
| 🎨 | **Design Tokens** | CSS variables, color scales (light + dark), spacing, radius, shadows |
| 🔤 | **Typography** | Font families, sources, CSS variables, weights, line heights |
| ✨ | **Animations** | Library (Framer Motion/GSAP), keyframes, easing, patterns |
| 🌊 | **Effects** | Glass morphism, gradients, glow, shimmer, separators |
| 🧱 | **Components** | UI library, button variants, cards, forms, modals, nav, toasts |

</td>
<td width="50%" valign="top">

### ⚙️ Stack & Architecture

| | Category | Captures |
|:-:|:---------|:---------|
| 📦 | **Tech Stack** | Framework + version, language, runtime, deployment, pkg manager |
| 📚 | **Dependencies** | All packages grouped by purpose (UI, auth, DB, payments) |
| 🏗 | **Architecture** | File structure, naming, aliases, state mgmt, data fetching |
| 🔧 | **Backend** | Database, auth, API style, ORM, jobs, storage, email, search |
| 🧪 | **Tooling** | Linter, formatter, tests, CI/CD, type checking, analytics |
| 📏 | **Conventions** | Immutability, file limits, error handling, coding standards |

</td>
</tr>
</table>

<br/>

## 📄 DNA File Format

Your DNA is a single, portable, human-readable JSON file at `.project-dna/dna.json`.

<details>
<summary><strong>View example dna.json</strong></summary>

<br/>

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

<br/>

> See the [full schema reference](skills/project-dna/references/dna-schema.md) for all supported fields.

<br/>

<div align="center">
<img src="https://capsule-render.vercel.app/api?type=waving&color=7c3aed&height=2&section=header" width="100%" />
</div>

<br/>

## 🎯 Use Cases

<table>
<tr>
<td width="50%">

### Solo Builders

> *"I build SaaS products. Every one uses the same stack — Next.js, Supabase, Tailwind, shadcn. Claude DNA lets me start every project with MY identity already baked in."*

### Agencies & Teams

> *"Our agency has a house style. Every client project starts with our design system. Claude DNA standardizes our starting point."*

</td>
<td width="50%">

### Open Source Maintainers

> *"I maintain a component library. Claude DNA lets users import our design language with one command. No manual setup."*

### Design System Migration

> *"We're migrating from MUI to shadcn. Extract DNA from the old project, diff it against the new, cherry-pick what to keep."*

</td>
</tr>
</table>

<br/>

## 🔄 Lifecycle

<div align="center">

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
               ┌────────────────┼────────────────┐
               │                │                │
      /claude-dna:export        │       /claude-dna:diff
               │                │                │
     ┌─────────▼──────┐        │        ┌───────▼──────┐
     │  ~/.project-dna │        │        │   Compare    │
     │  /presets/      │        │        │   presets    │
     └─────────┬──────┘        │        └──────────────┘
               │                │
               │       /claude-dna:apply
               │                │
     ┌─────────▼────────────────▼───────────────┐
     │            New Projects                  │
     │   Project B  │  Project C  │  Project D  │
     └──────────────────────────────────────────┘
               │
      /claude-dna:evolve
               │
     ┌─────────▼──────┐
     │  dna.json      │ ◄── Style evolved
     │  v1.0 → v1.1   │
     └────────────────┘
```

</div>

<br/>

## 📊 Comparison

| Feature | Claude DNA | Boilerplate Repos | Figma Tokens | interface-design |
|:--------|:----------:|:-----------------:|:------------:|:----------------:|
| Extracts from YOUR project | ✅ | ❌ Generic | ❌ Design only | ⚠️ Partial |
| Captures tech stack | ✅ | ⚠️ Static | ❌ | ❌ |
| Captures design tokens | ✅ | ⚠️ Sometimes | ✅ | ✅ |
| Captures backend config | ✅ | ⚠️ Sometimes | ❌ | ❌ |
| Captures architecture | ✅ | ⚠️ Static | ❌ | ❌ |
| Export / import presets | ✅ | Git clone | Plugin sync | File-based |
| Evolve over time | ✅ | ❌ Manual | ❌ Manual | ❌ |
| Drift detection (audit) | ✅ | ❌ | ❌ | ✅ |
| Side-by-side diff | ✅ | ❌ | ❌ | ❌ |
| Cherry-pick application | ✅ | ❌ | ⚠️ Partial | ❌ |

<br/>

## 🌍 Supported Ecosystems

> Claude DNA extracts from **any** project. The extraction is AI-powered — Claude reads your actual config files and builds the DNA.

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

<br/>

## 📂 Plugin Structure

```
claude-dna/
├── .claude-plugin/
│   ├── plugin.json              # Plugin manifest
│   └── marketplace.json         # Marketplace distribution config
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
│       ├── SKILL.md             # Core extraction & application brain
│       └── references/
│           └── dna-schema.md    # Full JSON schema reference
├── assets/                      # Screenshots & visual proof
├── README.md
├── LICENSE                      # MIT
└── .gitignore
```

<br/>

<div align="center">
<img src="https://capsule-render.vercel.app/api?type=waving&color=7c3aed&height=2&section=header" width="100%" />
</div>

<br/>

## 🧭 Philosophy

| Principle | Meaning |
|:----------|:--------|
| **Your DNA, not someone else's** | Extract from YOUR projects. Your presets reflect your taste, your stack, your conventions. |
| **Complete, not partial** | Not just colors. The full stack — framework, backend, tooling, architecture, conventions. |
| **Portable** | One JSON file. Copy it, email it, commit it, share it. No vendor lock-in. |
| **Evolvable** | Your style changes. Your preset should too. Evolve incrementally, never start over. |
| **Non-destructive** | Shows what will change before applying. Never silently overwrites. |
| **Framework-agnostic** | Next.js, React, Vue, Svelte, Go, Python — any project with config files. |

<br/>

## 🤝 Contributing

Contributions welcome! Fork it, branch it, PR it.

```bash
git checkout -b feat/my-feature
git commit -m 'feat: add my feature'
git push origin feat/my-feature
```

**Ideas:**
- [ ] Community preset gallery
- [ ] Visual diff viewer (HTML report)
- [ ] Framework-specific apply templates (Vue, Svelte, etc.)
- [ ] DNA merge tool (combine best parts of multiple presets)
- [ ] VS Code extension for previewing DNA

<br/>

## 🙏 Acknowledgments

- Inspired by [interface-design](https://github.com/Dammyjay93/interface-design) by Damola Akinleye
- Built on the [Claude Code Plugin System](https://docs.anthropic.com/en/docs/claude-code) by Anthropic
- Concept: design presets for code, like Lightroom presets for photography

<br/>

## 📜 License

[MIT](LICENSE) — use it, fork it, share it, sell it. Just keep the license.

<br/>

<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=7c3aed&height=100&section=footer" width="100%" />

**Build once. Apply everywhere.**

<sub>Made by <a href="https://github.com/mohammedsaifali">Saif</a> &nbsp;·&nbsp; Powered by Claude Code</sub>

</div>
