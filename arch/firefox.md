# Firefox

Type `about:config` in URL to enter advanced config

Accept Warning to proceed

---

## Open Tabs in Background

Middle clicking items in the book mark while staying in current tab

1. Search `browser.tabs.loadBookmarksInBackground`

2. set it to `true`

## Disable Fullscreen Notification

Turn off full screen notification

1. Search `full-screen-api.warning.timeout`

2. set it to `0`

## Disable Menubar

Disable `Alt` key from toggling menubar

1. Search `ui.key.menuAccessKeyFocuses`

2. Set it to `false`

---

## Default Browser

```sh
xdg-settings get default-web-browser
```

example output: `chromium.desktop`

```sh
xdg-settings set default-web-browser firefox.desktop
```
