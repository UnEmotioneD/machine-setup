# Markdown Lint

Configure markdown linter.

---

## Line Length

Inside `.markdownlint.json` or `.markdownlint.jsonc`:

- Disable linting:

```json
{
  "MD013": false
}
```

- Or set it to a different value:

```json
{
  "MD013": { "line_length": 100 }
}
```

---

## Line Change

Inside `.prettierrc`:

```jsonc
{
  "proseWrap": "never", // "always" | "never" | "preserve"
}
```

- `always`: wrap exceeding line
- `never`: paragraph into single line
- `preserve`: no tempering
