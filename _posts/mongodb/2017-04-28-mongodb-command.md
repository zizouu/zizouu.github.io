---
layout: post
title: "MongoDB command"
date: 2017-04-28
categories: mongoDB
---

* content
{:toc}

## 기본
1. RDBMS와 비교
* 완전 일치하는건 아니지만 개념적으로는
* table >> collection
* row >> document
* column >> field
* pk >> object id

2. Capped
* true : collection을 생성시 정해진 size만큼의 공간을 모두 사용하면 처음 썼던 데이터를 덥어쓰는 방식으로 기록
* false : 추가로 공간을 할당 
***

## Shell Command
```

use <db>                                                    // db사용
show collections                                            // collection list
db.<collection-name>.validate()                             // 해당 collection의 상태를 확인
db.createCollection("name", {capped:true, size:100000})     // Collection 생성

```
***