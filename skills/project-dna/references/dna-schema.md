# DNA Schema Reference

## Required Fields

| Field | Type | Description |
|-------|------|-------------|
| `name` | string | Preset name (kebab-case, used as filename) |
| `version` | string | Semver version (e.g., "1.0.0") |
| `description` | string | One-line description of this preset |
| `exported_from` | string | Project name this was extracted from |
| `exported_at` | string | ISO date of extraction |

## Optional Sections

All sections are optional. If a category doesn't apply, set it to `null`.

### `tech_stack`
```json
{
  "framework": { "name": "string", "version": "string", "variant": "string|null" },
  "language": "string",
  "runtime": "string",
  "deployment": "string|null",
  "package_manager": "string"
}
```

### `dependencies`
```json
{
  "core": ["package@version"],
  "ui": ["package@version"],
  "icons": "string|null",
  "auth": "string|null",
  "database": "string|null",
  "payments": "string|null",
  "analytics": "string|null",
  "background_jobs": "string|null",
  "email": "string|null",
  "other": ["package@version"]
}
```

### `design_tokens`
```json
{
  "colors": {
    "method": "css-variables|tailwind-config|theme-file",
    "values": { "--variable-name": "value" },
    "dark_mode": true
  },
  "spacing": {
    "base": 4,
    "scale": [0, 1, 2, 3, 4, 6, 8, 12, 16, 24],
    "unit": "px|rem"
  },
  "radius": { "sm": "string", "md": "string", "lg": "string", "default": "string" },
  "shadows": {
    "strategy": "none|minimal|layered",
    "values": { "sm": "string", "md": "string", "lg": "string" }
  },
  "animations": {
    "library": "string|null",
    "duration_default": "string",
    "easing_default": "string",
    "patterns": ["string"]
  }
}
```

### `typography`
```json
{
  "fonts": {
    "sans": { "family": "string", "source": "google|local|variable|system", "variable": "string|null" },
    "mono": { "family": "string", "source": "string", "variable": "string|null" },
    "serif": { "family": "string", "source": "string", "variable": "string|null" }
  },
  "scale": { "xs": "string", "sm": "string", "base": "string", "lg": "string", "xl": "string" },
  "weights_used": [400, 500, 600, 700],
  "line_height_default": 1.5
}
```

### `component_patterns`
```json
{
  "ui_library": "string",
  "config": {},
  "common_patterns": {
    "buttons": "string describing pattern",
    "cards": "string",
    "forms": "string",
    "modals": "string",
    "tables": "string",
    "navigation": "string",
    "loading": "string",
    "errors": "string",
    "toasts": "string"
  }
}
```

### `architecture`
```json
{
  "file_structure": "feature-based|type-based|flat|hybrid",
  "naming": {
    "files": "kebab-case|camelCase|PascalCase",
    "components": "PascalCase",
    "functions": "camelCase",
    "constants": "UPPER_SNAKE_CASE"
  },
  "patterns": {
    "state_management": "string",
    "data_fetching": "string",
    "error_handling": "string",
    "auth_pattern": "string"
  }
}
```

### `backend`
```json
{
  "database": { "provider": "string", "type": "string" },
  "auth": { "provider": "string", "strategy": "string" },
  "api_style": "rest|graphql|trpc",
  "orm": "string|null",
  "background_jobs": "string|null",
  "file_storage": "string|null",
  "email": "string|null",
  "search": "string|null"
}
```

### `tooling`
```json
{
  "linter": "string|null",
  "formatter": "string|null",
  "test_framework": "string|null",
  "ci_cd": "string|null",
  "type_checking": "string|null"
}
```

### `conventions`
```json
{
  "immutability": true,
  "max_file_lines": 800,
  "max_function_lines": 50,
  "explicit_error_handling": true
}
```
