---
layout: post
title: "윈도우 CMD 명령어 모음"
date: 2016-05-06
categories: windows
---

* content
{:toc}

### 심볼릭 링크 만들기 및 삭제하기

- 파일에 대한 심볼릭 링크 만들기

```
# Example) foo -> c:\Windows\system32\notepad.exe
mklink foo c:\Windows\system32\notepad.exe
```

- 디렉토리에 대한 심볼릭 링크 만들기

```
# Example) bar -> c:\windows
mklink /d bar c:\windows
```

- 파일 심볼릭 링크 지우기

```
del foo
```

- 디렉토리 심볼릭 링크 지우기

```
rmdir bar
```


### 최대 절전 모드 끄기

```
powercfg -h off
```


### BCD 부트로더 복구

```
bcdboot c:\windows /s c:
bootsect /nt60 c:
```