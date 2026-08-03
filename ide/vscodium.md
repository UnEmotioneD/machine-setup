# Visual Studio Codium

Microsoft VSCode with no telemetry feature

---

## Keybindings.json

Command palette: `Preferences: Open Keyboard Shortcuts (JSON)`

- Select suggestions with `ctrl + j, k`
- Accept with `ctrl + y`
- Disable `up/down arrow` keys

```jsonc
// Place your key bindings in this file to override the defaults
[
  // select suggestions with ctrl + j and K
  {
    "key": "ctrl+j",
    "command": "selectNextSuggestion",
    "when": "suggestWidgetMultipleSuggestions && suggestWidgetVisible && textInputFocus",
  },
  {
    "key": "ctrl+k",
    "command": "selectPrevSuggestion",
    "when": "suggestWidgetMultipleSuggestions && suggestWidgetVisible && textInputFocus",
  },
  // accept suggestion with ctrl + y
  {
    "key": "ctrl+y",
    "command": "acceptSelectedSuggestion",
    "when": "suggestWidgetVisible && textInputFocus",
  },
  // disable arrow keys from selecting suggestions
  {
    "key": "down",
    "command": "runCommands",
    "args": { "commands": ["hideSuggestWidget", "cursorDown"] },
    "when": "suggestWidgetVisible && textInputFocus",
  },
  {
    "key": "up",
    "command": "runCommands",
    "args": { "commands": ["hideSuggestWidget", "cursorUp"] },
    "when": "suggestWidgetVisible && textInputFocus",
  },
]
```
