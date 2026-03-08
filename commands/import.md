---
description: Import a DNA preset file from a path, URL, or global presets directory into the current project.
---

# Import Project DNA

## Workflow

### Step 1: Resolve source

Parse `$ARGUMENTS` to determine the source:

1. **Named preset**: Check `~/.project-dna/presets/{ARGUMENTS}.json`
2. **File path**: Check if `$ARGUMENTS` is a valid file path to a `.json` file
3. **URL**: If `$ARGUMENTS` starts with `http`, fetch the JSON from the URL
4. **No arguments**: List available presets from `~/.project-dna/presets/` and ask user to pick

### Step 2: Validate

Read the JSON and verify it has the Project DNA structure:
- Must have `name`, `version`, `tech_stack`, `design_tokens`
- Warn if version is very old (> 6 months)

### Step 3: Save locally

Copy the preset to `.project-dna/dna.json` in the current directory.

### Step 4: Offer next steps

```
Imported "{name}" v{version} (from {source})

Next steps:
  /project-dna:status     See the full DNA summary
  /project-dna:apply      Apply this DNA to your project
  /project-dna:audit      Check how your project compares to this DNA
```

## Rules

- Validate JSON structure before saving
- Never overwrite existing `.project-dna/dna.json` without asking
- Support both relative and absolute file paths
