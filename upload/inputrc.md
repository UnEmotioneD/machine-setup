# Bash 대소문자 구분없는 자동완성

## 설정

Neovim으로 `~/.inputrc`를 생성하면서 편집:

```sh
nvim ~/.inputrc
```

다음 설정을 추가:

```sh
set completion-ignore-case on
```

---

## 적용

변경사항을 현재 shell에 적용:

```sh
bind -f ~/.inputrc
```

또는 터미널을 재시작

---

## 추가 설정

```sh
# 아무입력이 없어도 가능한 목록을 즉시 표시
set show-all-if-unmodified on

# 자동완성 목록을 컬러로 표시
set colored-stats on

# 파일 타입별로 다른 색상 사용
set colored-completion-prefix on

# 자동완성시 / * @ 등의 접미사를 표시
set visible-stats on
```

---

## 사용

Documents로 자동완성됨

```sh
cd docu<Tab>
```

---

## 한방에 설정

`cat`을 이용해서 파일에 내용을 삽입하기:

```sh
cat >> ~/.inputrc << 'EOF'
#
# ~/.inputrc
#

set completion-ignore-case on
set show-all-if-ambiguous on
set colored-stats on
EOF
```
