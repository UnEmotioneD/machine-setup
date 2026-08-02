# Formatters

Formatters to use `Space` instead of `Tab` for indentation, and the size to `4 spaces`.
And prefer `single quotes` to `double quotes` if possible.

## Table of Contents

- [Editorconfig](#editorconfig)
- [C, CPP](#c-cpp)
- [Java](#java)
- [Python](#python)
- [JavaScript](#javascript)
- [Lua](#lua)
- [SH, BASH](#sh-bash)

---

## Editorconfig

[editorconfig.org](https://editorconfig.org/)

Create `.editorconfig` file at project root.

```editorconfig
root = true

[*]
indent_style = space
indent_size = 4
end_of_line = lf
charset = utf-8
insert_final_newline = true
trim_trailing_whitespace = true

[*.{js,cjs,mjs}]
indent_size = 4

[*.{html,css,md}]
indent_size = 2
```

---

## C, CPP

Formatter: Clang Format

Inside `.clang-format`:

```yaml
BasedOnStyle: LLVM
IndentWidth: 4
UseTab: Never
```

---

## Java

Formatter: [google-java-format](https://github.com/google/google-java-format)

- Format every `Java` with 4 space indent with `--aosp` flag

```sh
google-java-format --aosp -i $(find . -name '*.java')

# for directories
google-java-format --aosp -r --replace .
```

---

## Python

Formatter: [Ruff](https://docs.astral.sh/ruff/formatter/)

Since [Black](https://github.com/psf/black) formatter is not configurable.

By `ruff.toml`

```toml
line-length = 100

[format]
quote-style = "single"
indent-style = "space"
docstring-code-format = true
```

By `pyproject.toml`

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

Check out the [nodejs/prettier](../nodejs/prettier.md)

Create `.prettierrc` file at project root

- For every files

```jsonc
{
  "tabWidth": 4, // default: 2
  "singleQuote": true, // default: false
}
```

- Just the specified files

```jsonc
{
  "overrides": [
    {
      "files": ["*.js", "*.mjs", "*.cjs"],
      "options": {
        "tabWidth": 4,
        "singleQuote": true,
      },
    },
  ],
}
```

### Prettier Command

Format all supported files from current directory including every sub directories

```sh
npx prettier --write .
```

---

## Lua

Formatter: [StyLua](https://github.com/JohnnyMorganz/StyLua)

```toml
indent_type = "Spaces"
quote_style = "AutoPreferSingle"
```

### Stylua Command

```sh
stylua .
```

---

## SH, BASH

Formatter: [shfmt](https://github.com/patrickvane/shfmt)
