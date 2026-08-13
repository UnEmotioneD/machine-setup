# [ESLint](https://eslint.org/)

Find and fix problems in your JavaScript code.

## References

- [ESLint Quickstart - find errors automatically](https://www.youtube.com/watch?v=qhuFviJn-es&t=2s)
- [The Common Coder - How to Setup ESLint in 2026! (Beginner's Guide)](https://www.youtube.com/watch?v=eieTlMwCwWU)

## Table of Contents

- [Create Project](#create-project)
- [Install](#install)
- [Initialize](#initialize)
- [Lint it](#lint-it)
- [Configure Rules](#configure-rules)
  - [No Unused Vars](#no-unused-vars)
  - [Arrow Body Function](#arrow-body-function)
  - [jQuery](#jquery)

---

## Create Project

initialize new node project

```sh
mkdir node-project
cd node-project
npm init # or with -y flag
```

## Install

```sh
npm install --save-dev eslint
```

---

## Initialize

```sh
./node_modules/.bin/eslint --init

# or with npm
npm init @eslint/config@latest
```

> Answer `Where des your code run?` with `node` to not lint `console.log` as error.

---

## Lint it

```sh
npx eslint
```

### Lint Script

inside `package.json` add `lint` inside `scripts` block

```json
{
  "scripts": {
    "lint": "eslint"
  }
}
```

now you can use:

```sh
npm run lint
```

---

## Configure Rules

Inside `eslint.config.mjs` after the files {} block inside `defineConfig([])`

[no-unused-vars options](https://eslint.org/docs/latest/rules/no-unused-vars#options)

### No Unused Vars

[configure rules](https://eslint.org/docs/latest/use/configure/rules)

- `off`: turn off the rule
- `warn`: do not trigger exit code 1
- `error`: exit code 1 on build / runtime

```json
[
  {
    "rules": {
      "no-unused-vars": "warn"
    }
  }
]
```

### Arrow Body Function

can be fixed with `--fix` flag

```sh
npx eslint --fix
```

[rules reference](https://eslint.org/docs/latest/rules/)

```json
[
  {
    "rules": {
      "arrow-body-style": ["warn", "as-needed"]
    }
  }
]
```

### jQuery

`'$' is not defined`

change the following part from `eslint.config.mjs`:

```js
{
  languageOptions: {
    globals: globals.browser,
  },
}
```

to this:

```js
{
  languageOptions: {
    globals: {
      ...globals.browser,
      ...globals.jquery,
    }
  },
}
```

- `...` (**spread operator**): copies all properties from one object into another,
  merging them together
