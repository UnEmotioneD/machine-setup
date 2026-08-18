# [AutoHotkey](https://www.autohotkey.com/)

Software level keyboard remapping program.

> [!NOTE]
> Version 2 syntax

## Table of Contents

- [Caps Lock](#caps-lock)
- [ESC](#esc)
- [Run on Startup](#run-on-startup)

---

## Caps Lock

`Caps Lock` to `ESC` when tapped and `Control` when held

- Tap timeout `0.2 sec`.
- Register as `Control` right away when pressed with other keys.

```ahk
*CapsLock::
{
    Send "{Ctrl down}"

    KeyWait "CapsLock"

    Send "{Ctrl up}"

    if A_TimeSinceThisHotkey < 200
        Send "{Esc}"
}
```

---

## ESC

ESC to also change input source to English

```ahk
$Esc::
{
    if (IME_CHECK("A"))
        Send "{vk15}"
    Send "{Escape}"
}

IME_CHECK(WinTitle) {
    hWnd := WinGetID(WinTitle)
    return Send_ImeControl(ImmGetDefaultIMEWnd(hWnd), 0x001, "")
}

Send_ImeControl(DefaultIMEWnd, wParam, lParam) {
    DetectSave := A_DetectHiddenWindows
    DetectHiddenWindows true

    result := SendMessage(0x283, wParam, lParam,, "ahk_id " DefaultIMEWnd)

    if (DetectSave != A_DetectHiddenWindows)
        DetectHiddenWindows DetectSave

    return result
}

ImmGetDefaultIMEWnd(hWnd) {
    return DllCall("imm32\ImmGetDefaultIMEWnd", "Uint", hWnd, "Uint")
}
```

---

## Run On Startup

1. Open Run dialog with `Win + R`
2. Enter `shell:startup`
3. Put the scripts in this folder
