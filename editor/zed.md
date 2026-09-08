# [Zed](https://zed.dev/)

Your next last editor.

---

## Shortcuts

<!-- TODO: Finish shortcuts -->

| Action           | macOS           |
| ---------------- | --------------- |
| Command palette  | Cmd + Shift + P |
| Search file      | Cmd + P         |
| Search symbol    |                 |
| Search string    |                 |
| Project panel    | Cmd + Shift + E |
| Diagnostic panel | Cmd + Shift + M |

---

## Java

- [zed.dev languages/java](https://zed.dev/docs/languages/java)

How to get Java path on macOS installed with homebrew and set it up.

Get JDK home registered with macOS:

```sh
/usr/libexec/java_home -v 25
```

Output:

```txt
/opt/homebrew/opt/openjdk@25/libexec/openjdk.jdk/Contents/Home
```

Inside `.zed/settings.json`:

```json
{
  "languages": {
    "Java": {
      "language_servers": ["jdtls"]
    }
  },
  "lsp": {
    "jdtls": {
      "initialization_options": {
        "settings": {
          "java": {
            "home": "/opt/homebrew/opt/openjdk@25/libexec/openjdk.jdk/Contents/Home"
          },
          "lombok_support": true
        }
      }
    }
  }
}
```
