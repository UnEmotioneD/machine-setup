# Timezone

Fix time in Windows not matching when dual booting Linux by changing Windows time from
local time to UTC like in Linux.

## Reference

- [Fix time on dual boot - TroubleChute](https://www.youtube.com/watch?v=xO0lPxrtFCw)

---

## 자동 시간 설정 끄기

설정 > `시간 및 언어` > `날짜 및 시간` > `자동으로 시간 설정` 비활성화

---

## 레지스트리 편집기

레지스트리 편집기 경로창:

```txt
HKEY_LOCAL_MACHINE\System\CurrentControlSet\Control\TimeZoneInformation
```

우클릭 > `새로 만들기` > `DWORD(32비트)` 선택 > `RealTimeIsUniversal`이라고 이름 지정

엔터 한번 더 누른 후 값을 `1`로 변경
