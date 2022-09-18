# What is express.js

- Node.js를 위한 빠르고, 의견 없는, 미니멀리스트 웹 프레임워크

## 어플리케이션

- express 인스턴스
- 서버에 필요한 기능인 미들 웨어를 어플리케이션에 추가
- 라우팅을 설정할 수 있다
- 서버를 요청 대기 상태로 만들 수 있다

## 미들웨어

- 함수들의 연속
- 기능을 추가하고 싶을 때마다 미들웨어 사용
- 일반 미들웨어 vs 에러 미들웨어

  ```javascript
  const express = require("express");
  const app = express();

  // 일반 미들웨어
  function logger(req, res, next) {
    console.log("logger!");
    next();
  }

  // error 미들웨어
  function commonmw(req, res, next) {
    console.log("commonmw");
    next(new Error("error!"));
  }

  function errormx(err, req, res, next) {
    console.log(err.message);
    next();
  }

  app.use(logger);
  app.use(commonmw);
  app.use(errormx);

  app.listen(3000, function () {
    console.log("Server is running");
  });
  ```

## 라우팅

- 요청 uri에 대해 적절한 핸들러 함수로 연결해주는 기능
- 어플리케이션의 `get()`, `post()` method로 구현할 수 있다
- 라우팅을 위한 전용 Router 클래스를 사용할 수도 있다

  ```javascript
  var express = require("express");
  var app = express();

  // respond with "hello world" when a GET request is made to the homepage
  app.get("/", function (req, res) {
    res.send("hello world");
  });
  ```

### 응답 method

- `res.json()`: JSON 응답 전송
- `res.end()`: 응답 프로세스 종료

## 요청 객체 & 응답 객체

- 클라이언트의 요청/응답 정보 담은 객체
- http 모듈의 request/response 객체 래핑

- 요청 객체: `req.params()`, `req.query()`, `res.body()`
- 응답 객체: `req.send()`, `req.status()`, `res.json()`

### reference

- https://expressjs.com/
- https://inf.run/z8CD
