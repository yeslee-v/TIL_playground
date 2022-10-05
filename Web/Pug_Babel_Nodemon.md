# Pug & Babel & Nodemon

- HTML 특징 중 하나인 정적인 단점 개선

  - 반복문, 조건문, 변수 사용 및 동적인 페이지를 작성할 수 있다.
  - PHP, JSP와 유사하다.

## Pug

- Jade로 알려진 자바스크립트 라이브러리(상표 문제로 Jade라는 이름에서 Pug로 변경되었다.)
- HTML을 보다 가독성이 좋은 **템플릿 엔진**이다.

  > 💡 Template engine?
  >
  > - 서로 다른 요소로 분할된 웹 애플리케이션을 빠르게 빌드할 때 사용된다.
  >
  > - 서버 사이드 데이터를 빠르게 렌더링할 수 있다.

- Pug 컴파일러는 HTML 코드로 컴파일된다.

  ```javascript
  <!--pug-->
  ul each fruit in ['apple', 'banana', 'peach'] li = fruit

  <!--html-->
  <ul>
    <li>apple</li>
    <li>banana</li>
    <li>peach</li>
  </ul>
  ```

- `include`를 통해 Pug 파일(또는 일반 텍스트)을 다른 Pug 파일에 삽입할 수 있다.

  - 공통으로 쓰이는 head, footer는 파일로 분리해 관리할 수 있다.

  ```javascript
  // index.pug
  doctype html
  html
    include includes/head.pug
    body
      h1 My Site
      p Welcome to my site.
      script
        include script.js
      include includes/foot.pug

  // includes/head.pug
  head
    title My Site
    script(src='/javascripts/jquery.js')
    script(src='/javascripts/app.js')


  // script.js
  console.log("You are awesome");

  // includes/foot.pug
  footer#footer
    p Copyright (c) foober
  ```

- express에서 `app.set`으로 pug를 불러올 수 있다.

## Babel.js

- 모든 브라우저는 최신 버전의 자바스크립트를 사용하는 것이 아니다.(모든 브라우저가 개발 버전과 동일한 버전이 아닐 수 있음)
- **자바스크립트 변환 컴파일러(JavaScript Transform Compiler)**로 작성한 자바스크립트 코드를 해당 브라우저의 버전에 맞게 변환해준다.

## Nodemon

- 코드가 변경됐을 때마다 서버를 재실행하는 것은 귀찮다.
- 변경 사항이 생겼을 때 서버가 자동으로 재실행된다.

<br>
</br>

### reference

- https://www.educative.io/answers/what-are-template-engines
- https://pugjs.org
