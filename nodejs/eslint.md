# [ESLint](https://eslint.org/)

Find and fix problems in your JavaScript code.

## References

- [ESLint Quickstart - find errors automatically - freeCodeCamp.org](https://www.youtube.com/watch?v=qhuFviJn-es&t=2s)
- [How to Setup ESLint in 2026! (Beginner's Guide) - The Common Coder](https://www.youtube.com/watch?v=eieTlMwCwWU)

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

Initialize a new Node project:

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

> Answer `Where does your code run?` with `node` to not lint `console.log` as an error.

---

## Lint it

```sh
npx eslint
```

### Lint Script

Inside `package.json`, add `lint` inside the `scripts` block:

```json
{
  "scripts": {
    "lint": "eslint"
  }
}
```

Now you can use:

```sh
npm run lint
```

---

## Configure Rules

Inside `eslint.config.mjs` after the `files {}` block inside `defineConfig([])`:

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

Can be fixed with the `--fix` flag:

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

Change the following part from `eslint.config.mjs`:

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

- `...` (`spread operator`): copies all properties from one object into another,
  merging them together
