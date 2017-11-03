---
layout: post
title: "MEAN stack project setting"
date: 2017-11-01
categories: mean_stack
---

* content
{:toc}

### 윈도우에서 intellij 기반 프로젝트 구축

> [출처 : https://blooom.co.kr](https://blooom.co.kr/%EC%95%B5%EA%B7%A4%EB%9F%AC2-mean-%EC%8A%A4%ED%83%9D-%EC%84%B8%ED%8C%85%ED%95%98%EA%B8%B0/)

- node.js 설치
- angular-cli 설치 (angular2 구축용)
    - -g옵션을 통해 global로 설치해야 어디서나 사용가능
    
```
npm install -g @angular/cli
```
***

- new project > static web > angular cli > finish (angular2 프로젝트가 생성됨)
- express설치

```
npm install --save express body-parser
```
***

- express를 사용하기 위해 프로젝트 루트폴더에 server.js 생성, server폴더 생성
- server폴더에 서버 부분 코드를 작성할 예정이다. (express를 사용해서)
- server.js

```javascript
// config (자신의 환경에 맞게 URI 및 포트 넘버 수정)
var env = process.env.NODE_ENV || 'development';

if (env === 'development') {
 process.env.PORT = 3000;
} else if (env === 'test') {
 process.env.PORT = 3000;
}

// dependencies
const express = require('express');
const path = require('path');
const http = require('http');
const bodyParser = require('body-parser');

// routes 
// 프로젝트 폴더안에 server, server/routes 폴더를 생성
const api = require('./server/routes/api');
const app = express();

// port
const port = process.env.PORT || '3000';
app.set('port', port);

// Parsers
app.use(bodyParser.json());
app.use(bodyParser.urlencoded({ extended: false }));

// Static path to dist
// 차후 ng build 명령을 실행하면 dist 폴더는 자동 생성됨.
app.use(express.static(path.join(__dirname, 'dist')));

// api routes
app.use('/api', api);

// 기타 모든 라우트는 index.html로 돌림
// 위에서 필요한 라우트를 모두 설정하고 마지막에 이 코드가 와야함.
app.get('*', (req, res) => {
 res.sendFile(path.join(__dirname, 'dist/index.html'));
});


// HTTP server 생성
const server = http.createServer(app);

// 모든 네트워크 인터페이스에 설정된 포트 부여
server.listen(port, () => console.log(`Server running on localhost:${port}`));

```
***

- 위 과정에서 arrow function에 에러가 잡힌다면 아래와 같이 ECMAScript6로 변경해준다.
![ecmascript-setting](/media/mean_stack/ecmascript_settng.png)
***

- server폴더 아래 routes폴더 생성
- routes폴더에 api.js생성
- api.js

```javascript
const express = require('express');
const router = express.Router();

/* GET api listing. */
router.get('/', (req, res) => {
 res.send('api works');
});

module.exports = router;
```
***

- 이제 angular를 빌드하고 서버를 띄운다

```
ng build
node server.js
```
***