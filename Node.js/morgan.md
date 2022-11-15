# morgan

## Middleware

- `request`와 `response` 사이에 있는 **middle software**로 `request`에 응답하지 않고 `next`메서드를 통해 **다음 함수로 연결**한다.
- 설계 프로세스를 **단순화**한다. → 동일한 기능을 묶어 사용할 수 있다.
- **모든 controller는 middleware** 다.

  ```js
  // next 함수를 호출해야 middleware를 알 수 있다.
  const gossipMiddleware = (req, res, next) => {
    console.log("I'm middleware");
    next();
  };
  ```

  > **app.use()**? global middleware를 만드는 함수 → 어떤 url이 들어가도 사용할 수 있다.

## morgan

- node.js용 HTTP 요청 로거 미들웨어(request logger middleware)
- logger: 에러를 추적한다.
