# Key Repeat Speed

Key `repeat` and `delay` times shorter then that can be set from **Settings**.

---

## Commands

```sh
# Set delay before repeat starts (lower = faster)
defaults write -g InitialKeyRepeat -int 10

# Set delay between each repeat (lower = faster)
defaults write -g KeyRepeat -int 1
```

> [!Important]
> Log out and back in for changes to take effect.

---

## Checking Current Values

```sh
defaults read -g InitialKeyRepeat

defaults read -g KeyRepeat
```

---

## Revert to Defaults

```sh
defaults delete -g InitialKeyRepeat
defaults delete -g KeyRepeat
```

---

## Values

### InitialKeyRepeat

**Formula:** `time (ms) = (value + 1) × 16.67 ms`

| Value | Time     |
| ----- | -------- |
| 10    | ~183 ms  |
| 15    | ~267 ms  |
| 30    | ~517 ms  |
| 120   | ~2017 ms |

### KeyRepeat

**Formula:** `time (ms) = value × 15 ms`

| Value | Time    |
| ----- | ------- |
| 1     | 15 ms   |
| 2     | 30 ms   |
| 6     | 90 ms   |
| 120   | 1800 ms |
