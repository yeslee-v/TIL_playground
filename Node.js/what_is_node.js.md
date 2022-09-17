# What is Node.js

- Chrome의 V8 엔진을 기반으로 만들어진 JavaScript 런타임 → 브라우저 밖에서 JavaScript 코드를 실행할 수 있다

## 이벤트 기반의 비동기 I/O 프레임워크

## CommonJS 모듈 시스템이 존재한다

- 브라우저에서는 window context를 사용하거나 Require JS 같은 의존성 로더를 사용한다
- node는 파일 형태로 모듈을 관리할 수 있는 CommonJS로 구현한다

  - 기본 모듈

    ```javascript
    const http = require("http");

    http.createServer();
    ```

  - 써드파티 모듈
  - 사용자 정의 모듈

    ```javascript
    // math.js
    function sum(a, b) {
      return a + b;
    }

    module.exports = {
      sum: sum,
    };

    // index.js

    const math = require("./math");

    const result = math.sum(1, 2);

    console.log(result); // 3
    ```

## 기본적으로 비동기로 동작한다

- `readFile()`: async

  ```javascript
  const fs = require("fs");

  const data = fs.readFile("./data.txt", "utf-8", function (err, data) {
    console.log(data);
  });

  // data.txt 파일을 다 읽을 때까지 기다리지 않고 바로 다음 명령이 실행된다
  // 파일을 다 읽으면 function(err, data)가 실행된다
  console.log("hi");
  ```

- `readFileSync()`: sync

  ```javascript
  // data.txt
  this is data file

  // index.js
  const fs = require('fs');

  const data = fs.readFileSync('./data.txt', 'utf-8'); // utf-8 옵션을 붙이지 않으면 버퍼 크기가 출력된다

  console.log(data) // this is data file

  ```

### reference

- https://nodejs.org/dist/latest-v16.x/docs/api/fs.html
- https://inf.run/z8CD
