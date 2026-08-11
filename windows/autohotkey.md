# [AutoHotkey](https://www.autohotkey.com/)

Software level keyboard remapping program.

> [!NOTE]
> Version 2 syntax

## Table of Contents

- [Capslock](#capslock)
- [ESC](#esc)
- [Run on Startup](#run-on-startup)

---

## CapsLock

`CapsLock` to `ESC` when tapped and `Ctrl` when held

Tap timeout is 0.2 seconds

```ahk
*CapsLock::
{
    if KeyWait("CapsLock", "T0.2")
    {
        Send "{Esc}"
    }
    else
    {
        Send "{Ctrl down}"
        KeyWait "CapsLock"
        Send "{Ctrl up}"
    }
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
