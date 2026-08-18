# [Visual Studio Code](https://code.visualstudio.com/)

Microsoft에서 [Typescript](https://www.typescriptlang.org/)로 만든 무료 텍스트 편집기.
[GitHub](https://github.com/) 계정을 연동해서 설정, 확장프로그램 등을 연동할 수 있음.

> [!TIP]
> 보통 `VSCode`라고 하며 `Visual Studio`하고는 다른거임.

## Table of Contents

- [터미널 명령어](#터미널-명령어)
- [키보드 단축키](#키보드-단축키)
  - [폴더/파일 열기/닫기](#폴더파일-열기닫기)
  - [탭 관리](#탭-관리)
  - [패널 관리](#패널-관리)
  - [텍스트 편집](#텍스트-편집)
  - [커서](#커서)
  - [심볼](#심볼)
  - [좋은거](#좋은거)
- [검색](#검색)
- [확장 프로그램](#확장-프로그램)
  - [ESLint](#eslint)
  - [Prettier](#prettier)
  - [테마](#테마)
  - [폰트](#폰트)
- [유용한 설정](#유용한-설정)
- [Keybindings](#keybindings)

---

## 터미널 명령어

VSCode 터미널 또는 **PowerShell** 명령어.

### 폴더 보기

```powershell
# list
ls
```

### 폴더 이동

```powershell
# change directory(경로)
cd <폴더이름>

# 예시
cd basic/ch01
```

### 폴더 생성

```powershell
# make directory
mkdir <폴더이름>
```

### 파일 생성

```powershell
New-Item -Path "<파일이름>" -ItemType File

# 또는
ni <파일이름>
```

### VSCode로 열기

```powershell
# 현재 경로에 대하여 새로운 창을 연다
code .

# 이미 열려 있는 창에서 파일을 연다
code -r hello.js
```

**-r**: `--reuse-window`

---

## 키보드 단축키

- [Windows](https://code.visualstudio.com/shortcuts/keyboard-shortcuts-windows.pdf)
- [macOS](https://code.visualstudio.com/shortcuts/keyboard-shortcuts-macos.pdf)
- [Linux](https://code.visualstudio.com/shortcuts/keyboard-shortcuts-linux.pdf)

윈도우 용 단축키 정리

### 폴더/파일 열기/닫기

| Shortcut    | Action              |
| ----------- | ------------------- |
| Ctrl + O    | 파일 열기           |
| Ctrl + K, O | 폴더 열기           |
| Ctrl + R    | 최근 폴더/파일 열기 |
| Ctrl + K, F | 폴더 닫기           |

### 탭 관리

| Shortcut                | Action                    |
| ----------------------- | ------------------------- |
| Ctrl + W                | 탭 닫기                   |
| Ctrl + Shift + W        | 모든 탭 닫기              |
| Ctrl + Shift + T        | 닫은 탭 다시 열기         |
| Ctrl + Alt + Left/Right | 탭을 여러 패인으로 나누기 |
| Ctrl + \                | 현재 탭을 좌우로 복사     |
| Ctrl + Tab              | 열린 탭에서 이동          |
| Ctrl + 1/2/3...         | 패널 선택                 |

### 패널 관리

| Shortcut         | Action          |
| ---------------- | --------------- |
| Ctrl + `(grave)  | 터미널          |
| Ctrl + ~(tilde)  | 새 터미널       |
| Ctrl + Shift + P | Command Palette |
| Ctrl + B         | 사이드바 토글   |
| Ctrl + Shift + E | 파일 트리       |
| Ctrl + Shift + M | Problems 패널   |
| Ctrl + Shift + U | Output 패널     |

### 텍스트 편집

| Shortcut                       | Action                                |
| ------------------------------ | ------------------------------------- |
| Ctrl + /                       | 주석 처리                             |
| Ctrl + Shift + Z 또는 Ctrl + Y | 뒤로가기 취소                         |
| Ctrl + D                       | 커서의 문자와 일치하는 모든 문자 선택 |
| Tab                            | 들어쓰기 + (줄의 가장 앞에서)         |
| Shift + Tab                    | 들여쓰기 - (줄의 가장 앞에서)         |
| Ctrl + Shift + K               | 현재 줄 삭제                          |
| Ctrl + Enter                   | 줄 아래 새로운 줄                     |
| Ctrl + Shift + Enter           | 줄 위에 새로운 줄                     |
| Alt + Up/Down                  | 줄 이동                               |
| Alt + Shift + Up/Down          | 줄 복사                               |
| Ctrl + .(dot)                  | Quickfix                              |
| Alt + Shift + F                | 파일 포맷                             |
| Ctrl + F                       | 문자열 찾기                           |
| Ctrl + H                       | 찾은 문자열 바꾸기                    |
| Ctrl + Shift + F               | 워크스페이스에서 문자열 찾기          |
| Ctrl + Shift + H               | 워크스페이스에서 찾은 문자열 바꾸기   |

### 커서

| Shortcut                  | Action                  |
| ------------------------- | ----------------------- |
| Home                      | 줄 가장 앞으로          |
| End                       | 줄 가장 뒤로            |
| Ctrl + Left/Right         | 단어 단위로 이동        |
| Ctrl + Shift + Left/Right | 단어 단위로 이동 + 선택 |
| Ctrl + Alt + Up/Down      | 위/아래 커서 추가       |
| Alt + Left Click          | 커서 추가               |
| Alt + F8                  | 코드에서 다음 문제 위치 |
| Alt + Shift + F8          | 코드에서 이전 문제 위치 |

### 심볼

| Shortcut          | Action                        |
| ----------------- | ----------------------------- |
| F2                | 이름 변경                     |
| Ctrl + Shift + O  | 현재 파일에서 검색            |
| Ctrl + T          | Workspace에서 검색            |
| F12               | 선언된 위치로 가기            |
| Alt + F12         | 선언된 부분 훔쳐보기          |
| Shift + F12       | 변수/함수 사용된 곳으로 이동  |
| Alt + Shift + F12 | 변수/함수 사용된 곳 전부 표시 |

### 좋은거

| Shortcut                                       | Action              |
| ---------------------------------------------- | ------------------- |
| Ctrl + K, Z                                    | 에디터 창만 보기    |
| Command Palette → View: Toggle Centered Layout | Editor 창 중앙 정렬 |
| Command Palette → Developer: Reload Window     | 새로고침            |

---

## 검색

`Command Palette`를 이용해서 프로젝트 내에서 검색하기.

| Shortcut       | Action                               |
| -------------- | ------------------------------------ |
| Ctrl + P       | 파일 검색                            |
| Ctrl + P, `@`  | 현재 파일의 심볼(변수/함수) 검색     |
| Ctrl + P, `@:` | 현재 파일의 심볼을 그룹화해서 보여줌 |
| Ctrl + P, `#`  | 프로젝트 전체 심볼                   |

---

## 확장 프로그램

확장프로그램 사이드바 단축키: `ctrl + shift + x`

### CSS Peek

- HTML에서 정의 되어 있는 CSS를 확인 할 수 있음

### Code Runner

- 파일 실행: `ctrl + alt + n`

### Code Spell Checker

- 오타 검사

```jsonc
// Preference: Open User Settings (JSON)
{
  // 문제 창에 뜨지 않게
  "cSpell.diagnosticLevel": "Hint",
}
```

### Error Lense

- 문제가 있는 코드의 줄에 뭐가 문제인지 보여줌

### ESLint

- JavaScript, TypeScript 등 문법 검사

#### 설치

프로젝트 root 경로(VSCode를 여는 위치)에서

```powershell
# 노드 프로젝트 생성
npm init -y

# ESLinst 설치
npm install --save-dev eslint

# ESLinst 기본 설정 생성
npm init @eslint/config@latest
```

화살표로 움직이고 스페이스로 선택

- What do you want to lint? `javascript`
- how would you like to use ESlint?
- What type of modules does your project use?
- Which framework does your project use? `none`
- Does your project use TypeScript? `No`
- Where does your code run? `node`
- Would you like to install them now? `Yes`
- Which package manager do you want to use? `npm`

> [!TIP]
> `Where des your code run?`에서 `node`를 선택해야 `console.log`를 에러라고 하지 않음

더 자세한거는 [nodejs/eslint.md](https://github.com/unemotioned/tistory/blob/main/nodejs/eslint.md) 참고.

### JavaScript(ES6) code snippets

- JavaScript 추가 자동완성 제공

### Live Server (Five Server)

- HTML 파일을 localhost에서 열 수 있음

### Material Icon Theme

- 파일 트리의 폴더/파일 아이콘 변경

### Prettier

HTML, CSS, JavaScript, MD, JSON ... 파일 포멧

프로젝트 루트에 `.prettierrc` 파일 생성

`JavaScript`에만 적용:

```json
{
  "overrides": [
    {
      "files": ["*.js", "*.mjs", "*.cjs"],
      "options": {
        "tabWidth": 4,
        "singleQuote": true
      }
    }
  ]
}
```

- 4 스페이스 들여쓰기
- 쌍따옴표 대신 작은 따옴표

더 자세한거는 [nodejs/prettier.md](https://github.com/unemotioned/tistory/blob/main/nodejs/prettier.md) 참고.

### Quokka.js

Command palette에서 `Quokka.js: Start on Current File`를 선택하면 editor창에서
inline으로 결과를 보여줌

### Tabout

- 자동으로 닫히는 괄호/따옴표를 Tab키 넘어갈 수 있게 해줌

### npm Intellisense

- Node 패키지 자동완성 제공

---

### 테마

[vscodethemes.com](https://vscodethemes.com/)

다음 테마중 하나 선택

- Catppuccin for VSCode (+ Catppuccin Icons for VSCode)
- GitHub Theme
- Nord
- One Dark Pro
- Rose Pine
- tokyo-night
- Vague Theme (Windsurf)

### 폰트

[nerdfonts.com](https://www.nerdfonts.com/)에서 다운로드 후 설치

Nerd font icons, Ligature 지원

#### D2CodingLigature Nerd Font

- 네이버에서 만듬. 한글, 영어, 특수문자간의 구별에 용이

#### JetBrainsMono Nerd Font

- 네모 반듯

#### Iosevka Nerd Font

발음: `요쎄브카`

- 세로로 길쭉

#### ETC

- [Fira Code](https://github.com/tonsky/FiraCode)
- [GeistMono](https://github.com/vercel/geist-font)
- [Hack](https://github.com/source-foundry/Hack)
- [Input](https://input.djr.com/)
- [Monaspace](https://monaspace.githubnext.com/)
- [RobotoMono](https://github.com/powerline/fonts/tree/master/RobotoMono)
- [ZedMono](https://github.com/zed-industries/zed-fonts)

---

## 유용한 설정

**Command palette**에서 설정 이름을 검색해서 설정하거나
`Preference: Open User Settings (Json)`을 검색, `settings.json`에서 직접 편집 할 수 있다

```jsonc
{
  // HTML, CSS, JS 파일에서의 기본 들여쓰기 크기
  "editor.tabSize": 2,
  // 특정 파일의 포메터, 들여쓰기
  "[javascript]": {
    "editor.defaultFormatter": "esbenp.prettier-vscode",
    "editor.tabSize": 4,
  },

  /* Tab키 만으로 자동완성 */
  // .(온점) 자동완성 선택 비활성화
  "editor.acceptSuggestionOnCommitCharacter": false,
  // Enter키 자동완성 선택 비활성화
  "editor.acceptSuggestionOnEnter": "off",

  // != <= >= ==> 등을 더 재밋게 보여줌
  "editor.fontLigatures": true,
  "editor.fontFamily": "Iosevka Nerd Font",
  "terminal.integrated.fontFamily": "Iosevka Nerd Font",

  // 저장할때 자동으로 포멧
  "editor.formatOnSave": true,
  // 저장할때 동작
  "editor.codeActionsOnSave": {
    "source.fixAll": "explicit",
    "source.organizeImports": "explicit",
  },
  // 자동 저장 활성화
  "files.autoSave": "afterDelay",

  // 파일 트리 들여쓰기 크기
  "workbench.tree.indent": 16,
}
```

---

## Keybindings

Command palette: `Preferences: Open Keyboard Shortcuts (JSON)`

- Select suggestions with `ctrl + j, k` (down/up)
- Accept with `ctrl + y`
- Disable `up/down arrow` keys for selecting suggestions

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
