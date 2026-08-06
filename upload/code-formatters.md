# Code Formatters

My formatter style:

- `Spaces` for indentation instead of **Tabs**.
- `4-space` indentation width.
- Prefer `single quotes` when supported.

## Table of Contents

- [Editorconfig](#editorconfig)
- [C / C++](#c--c)
- [Python](#python)
- [JavaScript](#javascript)
- [Lua](#lua)
- [Shell](#shell)

---

## Editorconfig

Reference: [editorconfig.org](https://editorconfig.org/)

`.editorconfig`:

```editorconfig
root = true

[*]
indent_style = space
indent_size = 4
end_of_line = lf
charset = utf-8
insert_final_newline = true
trim_trailing_whitespace = true

[*.{html,css,md}]
indent_size = 2
```

---

## C / C++

Formatter: [ClangFormat](https://clang.llvm.org/docs/ClangFormat.html)

`.clang-format`:

```yaml
BasedOnStyle: LLVM
IndentWidth: 4
UseTab: Never
```

---

## Python

Formatter: [Black](https://github.com/psf/black), [Blue](https://blue.readthedocs.io/en/latest/), [Ruff](https://docs.astral.sh/ruff/formatter/)

- `ruff.toml`:

```toml
line-length = 100

[format]
quote-style = "single"
indent-style = "space"
docstring-code-format = true
```

- `pyproject.toml`:

```toml
[tool.ruff]
line-length = 100

[tool.ruff.format]
quote-style = "single"
indent-style = "space"
docstring-code-format = true
```

### Black, Blue, Ruff Command

```sh
black .

blue .

ruff format .
```

---

## JavaScript

Formatter: [Prettier](https://prettier.io/)

`.prettierrc`:

- every files:

```json
{
  "tabWidth": 4,
  "singleQuote": true
}
```

- specific files only:

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

### Prettier Command

```sh
npx prettier --write .
```

---

## Lua

Formatter: [StyLua](https://github.com/JohnnyMorganz/StyLua)

`.stylua.toml`:

```toml
indent_type = "Spaces"
quote_style = "AutoPreferSingle"
```

### Stylua Command

```sh
stylua .
```

---

## Shell

Formatter: [shfmt](https://github.com/patrickvane/shfmt)

### Shfmt Command

```sh
# follow .editorconfig
shfmt -w .

# 4-space indent
shfmt -w -i 4 .
```
