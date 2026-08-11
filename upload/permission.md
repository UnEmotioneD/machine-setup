# Permission

What is `chmod` with numbers.

```sh
sudo chmod 644 /usr/share/keyrings/wezterm-fury.gpg
```

---

| Permission | Value |
| ---------- | ----- |
| Read       | 4     |
| Write      | 2     |
| Execute    | 1     |

> [!TIP]
> `0`: No permission at all.

| Digit | Applies to |
| ----- | ---------- |
| 1st   | Owner      |
| 2nd   | Group      |
| 3rd   | Others     |

`6` = 4(read) + 2(write) = owner can **read and write**.
`4` = group can only **read**.
`4` = others can only **read**.

Do `ls -l` to see permission for each files:

```sh
-rw-r--r--
```

`744` is also common.

```sh
-rwx-rw-rw-
```

---

## First Character

The very first character indicates files types.

- `-`: regular file
- `d`: directory
- `l`: symbolic link
- `c`: character device - **stream** transfer data one character/byte at a time
- `b`: block device - **storage device**
- `s`: socket - communication between processes
- `p`: named pipe (FIFO) - methods for processes to send data to each other
