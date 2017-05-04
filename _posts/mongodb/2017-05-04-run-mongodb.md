---
layout: post
title: "run mongoDB"
date: 2017-05-04
categories: mongoDB
---

* content
{:toc}

## startup mongo-db
- default db path가 C:\data\db 로 지정되어있다. 그대로 사용하려면 해당 경로에 폴더를 생성해줘야한다.
- 경로를 따로 지정해주려면 mongod --dbpath arg 옵션으로 경로를 지정해줘야한다. ()해당경로가 존재해야함)

```

mongod                  // mongo-db server 실행
mongod --dbpath <path>  // 경로지정하여 실행
mongo                   // mongo-db client실행

```
***