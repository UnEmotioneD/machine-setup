# Word Count

Find files and directories with [fd](https://github.com/sharkdp/fd) and pipe it
to [wc](https://man7.org/linux/man-pages/man1/wc.1.html) to count them.

## Table of Contents

- [Words in File](#words-in-file)
- [Files and Directories](#files-and-directories)

---

## Words in File

### Bytes

- `-c`, `--bytes`

```sh
wc -c file.txt
```

### Characters

- `-m`, `--chars`

```sh
wc -m file.txt
```

### Words

- `-w`, `--words`

```sh
wc -w file.txt
```

### Lines

- `-l`, `--lines`

```sh
wc -l file.txt
```

---

## Files and Directories

`fd` handles file names with spaces better compared to `ls`.

```sh
fd | wc -l
```

This will sum up all the files and directories.

### Include Hidden

- Hidden
- No ignore (ex: `.gitignore`, `.fdignore`)

```sh
fd --hidden --no-ignore | wc -l
```

### Specify Type

```sh
# directory only
fd --type d | wc -l

# file only
fd --type f | wc -l
```

### Max Depth

```sh
# only from current directory
fd --max-depth 1 | wc -l
```

### Go To

- Count every files and files only from current directory.

```sh
fd --max-depth 1 --type f --hidden --no-ignore | wc -l
```
