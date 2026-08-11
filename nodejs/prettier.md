# Prettier

Formatter for HTML, CSS, JavaScript, Markdown, JSON ETC.

## Reference

- [prettier.io](https://prettier.io/)

---

## Configuration

- 4-space indent
- prefer single quote

Inside `.prettierrc`:

```json
{
  "tabWidth": 4,
  "singleQuote": true
}
```

[Overrides](https://prettier.io/docs/configuration#configuration-overrides) for specific files:

```json
{
  "overrides": [
    {
      "files": ["*.js", "*.mjs", "*.cjs"],
      "options": {
        "tabWidth": 4,
        "singleQuote": true
      }
    }
  ]
}
```

---

### Command

Recursively format every files. Follow `.prettierrc` if exists.

```sh
npx prettier --write .
```
