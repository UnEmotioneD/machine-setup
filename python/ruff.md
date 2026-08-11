# [Ruff](https://docs.astral.sh/ruff/)

An extremely fast Python linter and code formatter, written in Rust.

| Setting      | My Style | [Black](https://black.readthedocs.io/en/stable/) |
| ------------ | -------- | ------------------------------------------------ |
| Line-length  | 100      | 88                                               |
| Quote Style  | Single   | Double                                           |
| Indent Width | 4-Space  | 4-Space                                          |
| Indent Style | Space    | Space                                            |

---

## Configuration

- `ruff.toml`:

```toml
line-length = 100
indent-width = 4

[format]
quote-style = "single"
indent-style = "space"
docstring-code-format = true
```

- `pyproject.toml`:

```toml
[tool.ruff]
line-length = 100
indent-width = 4

[tool.ruff.format]
quote-style = "single"
indent-style = "space"
docstring-code-format = true
```

---

## Command

```sh
ruff format
```
