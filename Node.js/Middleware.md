# Middleware

- `request`와 `response` 사이에 있는 **middle software**.
- **모든 controller는 middleware** 다.

  ```js
  // next 함수를 호출해야 middleware를 알 수 있다.
  const gossipMiddleware = (req, res, next) => {
    console.log("I'm middleware");
    next();
  };
  ```

- `request`에 응답하지 않는다.

  > **app.use()**? global middleware를 만드는 함수 → 어떤 url이 들어가도 사용할 수 있다.
