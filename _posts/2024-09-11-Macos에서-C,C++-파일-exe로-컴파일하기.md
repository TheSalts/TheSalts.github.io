---
layout: post
title: Macos에서 C/C++ 파일 exe로 컴파일하기
---


Macos에서 C언어 코드를 `exe` 파일로 컴파일하는 방법을 알아봅시다.

## 1. Homebrew 설치

```zsh
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

이 코드를 터미널에서 실행하여 Homebrew를 설치합니다.

## 2. [MinGW](https://ko.wikipedia.org/wiki/MinGW) 설치

아래 명령어를 통해 Homebrew를 사용하여 MinGW를 설치합니다.

```zsh
brew install mingw-w64
```

## 3. 파일 생성

아래의 명령어를 사용하여 코드를 exe파일로 컴파일합니다.

- C

```zsh
x86_64-w64-mingw32-gcc -o {실행파일명}.exe {컴파일할 파일명}.c
```

- C++

```zsh
x86_64-w64-mingw32-g++ -o {실행파일명}.exe {컴파일할 파일명}.cpp
```

## 4. 파일 체크

```zsh
file {파일명}.exe
```

위 명령어를 실행했을 때, `program.exe: PE32+ executable (console) x86-64, for MS Windows`라고 나온다면 exe파일로 제대로 변환이 된 것입니다.
