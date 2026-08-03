# [Grep](https://man7.org/linux/man-pages/man1/grep.1.html)

Searches for patterns in each file.

## Find String Inside Files

```sh
grep -r "<string>" .
```

---

## Options

| Option                         | Description                |
| ------------------------------ | -------------------------- |
| `-r`                           | Recursive search           |
| `-i`                           | Case-insensitive           |
| `-n`                           | Show line numbers          |
| `-l`                           | Show only filenames        |
| `--include="*.txt"`            | Search specific file types |
| `--binary-files=without-match` | Exclude binary files       |
| `--exclude-dir=node_modules`   | Exclude a directory        |

```sh
grep -rin "foobar" --include="*.js" --exclude-dir=node_modules
```
