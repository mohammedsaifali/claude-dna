---
description: Export the current project's DNA to your global presets directory (~/.project-dna/presets/) so it can be applied to any future project.
---

# Export Project DNA

## Workflow

### Step 1: Check for DNA

Read `.project-dna/dna.json` in the current directory.
If not found, tell the user to run `/project-dna:extract` first.

### Step 2: Validate

Ensure all required fields are present:
- `name` (used as filename)
- `version`
- `tech_stack`
- `design_tokens`

### Step 3: Export

1. Create `~/.project-dna/presets/` directory if it doesn't exist
2. Copy `.project-dna/dna.json` to `~/.project-dna/presets/{name}.json`
3. If a preset with the same name exists, ask user:
   - **Overwrite** — replace the existing preset (version bump)
   - **Rename** — save under a new name
   - **Cancel** — abort

### Step 4: Confirm

Display:
```
Exported "{name}" v{version} to ~/.project-dna/presets/{name}.json

Use in any project:
  /project-dna:apply {name}

Share with others:
  Copy ~/.project-dna/presets/{name}.json to their project as .project-dna/dna.json
```

## Rules

- Never export without user confirmation
- Always show the full path where the file was saved
- Suggest sharing methods (copy file, git, or include in plugin marketplace)
