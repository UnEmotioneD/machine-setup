# [Nodemon](https://nodemon.io/)

Monitor changes in source code and automatically restarts your program.

---

## Installation

```sh
npm i -g nodemon

nodemon --version
```

---

## Configuration

Inside `nodemon.json`:

```json
{
  "watch": ["chap08"],
  "ext": "py",
  "ignore": [],
  "exec": "python3 ./binary_tree.py",
  "events": {
    "start": "clear"
  }
}
```

- `watch`: Files or directories to monitor.
- `ext`: File extensions to watch.
- `ignore`: Path to exclude.
- `exec`: Command to run on changes.
- `start`: Command to run on start before `exec`.

> [!NOTE]
> On Windows use `cls` instead of `clear` for `events.start`.

---

## Usage

```sh
nodemon
```

Enter `rs` to restart.
