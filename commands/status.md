---
description: Display the current project's DNA summary — tech stack, design tokens, fonts, architecture, and conventions.
---

# Project DNA Status

## Workflow

### Step 1: Check for DNA file

Look for `.project-dna/dna.json` in the current directory.

### If DNA exists:

Read and display a formatted summary:

```
Project DNA: "{name}" v{version}
Exported from: {exported_from} on {exported_at}
─────────────────────────────────────────────

Tech Stack
  Framework:    {framework.name}@{framework.version} ({framework.variant})
  Language:     {language}
  Deployment:   {deployment}
  Pkg Manager:  {package_manager}

Design Tokens
  Colors:       {count} variables ({dark_mode ? "light + dark" : "light only"})
  Spacing:      {base}px base ({scale.length} steps)
  Radius:       {default} default
  Shadows:      {strategy} strategy
  Animations:   {library}, {duration_default} default

Typography
  Sans:         {fonts.sans.family} ({fonts.sans.source})
  Mono:         {fonts.mono.family} ({fonts.mono.source})
  Scale:        {Object.keys(scale).length} sizes
  Weights:      {weights_used.join(", ")}

Components
  UI Library:   {ui_library}
  Config:       {shadcn_config.style} style
  Patterns:     {Object.keys(common_patterns).length} defined

Architecture
  Structure:    {file_structure}
  Naming:       {naming.files} files, {naming.components} components

Backend
  Database:     {database.provider} ({database.type})
  Auth:         {auth.provider} ({auth.strategy})
  API:          {api_style}
  Jobs:         {background_jobs}

Tooling
  Linter:       {linter}
  Formatter:    {formatter}
  Tests:        {test_framework}
```

### If no DNA exists:

Display:
```
No Project DNA found in this directory.

Get started:
  /project-dna:extract    Scan this project and capture its DNA
  /project-dna:apply      Apply a preset from another project
  /project-dna:list       See your saved presets
```
