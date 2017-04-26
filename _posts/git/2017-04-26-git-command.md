---
layout: post
title: "git 명령어 모음"
date: 2017-04-26
categories: git
---

* content
{:toc}
## 저장소 강제 초기화
### 기존 Local git 초기화
- .git폴더 삭제
- git init 수행

```
...
git add *
git commit -m 'initial commit'
git remote add origin <url>
...
```
- 강제 Push
```
...
git push --force --set-upstream origin master
...
```
