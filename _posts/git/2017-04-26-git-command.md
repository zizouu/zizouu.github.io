---
layout: post
title: "git 명령어 모음"
date: 2017-04-26
categories: git
---

* content
{:toc}

## 저장소 강제 초기화
.git폴더 삭제<br>
git init 수행
```

git add *
git commit -m 'initial commit'
git remote add origin <url>
git push --force --set-upstream origin master

```
***

## remote

```

git remote -v                       // 원격저장소 확인
git remote set-url origin <git-url> // 원격저장소 수정

```
***

## branch

```

git branch -d <branch>  // 브랜치 삭제
git branch -r           // 브랜치 목록

```
***