# Markdown Lint

Configure markdown linter.

---

## Line Length

Inside `.markdownlint.json` or `.markdownlint.jsonc`

- disable linting

```json
{
  "MD013": false
}
```

- or set it to different value

```json
{
  "MD013": { "line_length": 100 }
}
```

---

## Line Change

Inside `.prettierrc`:

```json
{
  "proseWrap": "never" // "always" | "never" | "preserve"
}
```

- `always`: wrap exceeding line
- `never`: paragraph into single line
- `preserve`: no tempering
