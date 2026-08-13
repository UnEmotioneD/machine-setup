# [Biome](https://biomejs.dev/)

Faster linting and formatting tool chain.

## Table of Contents

- [Install](#install)
- [Init](#init)
- [Commands](#commands)
- [Config](#config)
- [Migration](#migration)
- [GitHub Action](#github-action)

---

## Install

- `-D`: `--save-as-dev` - exclude from production
- `-E`: `--save-exact` - **exact version** instead of range

```sh
npm i -D -E @biomejs/biome
```

---

## Init

Creates `biome.json` file with defaults at project root.

```sh
npx @biomejs/biome init
```

> [!TIP]
> File name is also available in `JSONC` and can be prefixed with dot.

---

## Commands

```sh
# format
npx @biomejs/biome format --write

# lint and apply safe fix
npx @biomejs/biome lint --write

# format, organize imports and lint
npx @biomejs/biome check --write
```

---

## Config

[Biome formatter options](https://biomejs.dev/formatter/#options)

My style:

- Space as indent.
- 4-space indent width (only for JS)
- Prefer single quotes.
- 100 line-width (only for JS)

Inside `.biome.jsonc`:

```jsonc
{
  "$schema": "https://biomejs.dev/schemas/2.4.13/schema.json",
  "formatter": {
    "indentStyle": "space",
    "quoteStyle": "single",
  },
  "javascript": {
    "indentWidth": 4,
    "lineWidth": 100,
  },
}
```

> [!NOTE]
> `javascript` in biome includes JSX, TS and TSX.

---

## Migration

<!-- TODO: finish documenting migration -->

### Prettier

### Eslint

---

## GitHub Action

<!-- TODO: finish documenting github action -->
