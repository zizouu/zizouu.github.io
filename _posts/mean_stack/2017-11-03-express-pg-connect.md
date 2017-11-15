---
layout: post
title: "Express.js and Postgresql connection"
date: 2017-11-03
categories: mean_stack 
---

* content
{:toc}

### Express.js와 Postgresql연결 (mongoDB 사용하려다가 기존의 진행하던 프로젝트가 pg로 되어있어 변경)
> [출처 : Express.js 공식페이지](http://expressjs.com/ko/guide/database-integration.html)

```javascript
const pgp = require('pg-promise')({});
const db = pgp('postgres://user:password@host:5432/dbname');
db.many('SELECT * FROM stock_item')
.then(function (data) {
  res.send(data);
})
.catch(function(error){
  console.log(error.stack);
});
```
***
위와 같은 방식으로 연결