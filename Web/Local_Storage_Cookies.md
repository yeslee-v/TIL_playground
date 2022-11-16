# Local Storage vs Cookies

## Local Storage

- HTML5에서 도입된 솔루션으로 모든 HTTP 요청에서 데이터를 주고받을 필요가 없다. → 클라이언트가 데이터를 가지고 있다.

  - 클라이언트-서버간의 전체 트래픽과 낭비되는 대역폭량을 줄일 수 있다.
  - 데이터가 유저의 로컬 디스크에 저장되어있으면 **인터넷이 끊겨도 데이터가 지워지지 않는다**.

- **유효기간이 없다**. → JavaScript 코드를 통해 데이터를 삭제하지 않는 이상 자동으로 삭제되지 않는다.
- **최대 5MB**의 용량을 갖고 있다.
- 문자열과 JavaScript의 Primitive(`string`, `number`, `bigint`, `boolean`, `undefined`, `symbol`, `null`), 객체를 저장할 수 있다.

  > localStorage values on Secure(SSL) pages are isolated.

- **XSS 공격**에 취약하다.

  > XSS(Cross-site scripting)?
  >
  > - 공격자가 사용자의 웹사이트의 JavaScript를 실행할 수 있을 때 발생한다.
  >
  > - LocalStorage에 있는 Access Token을 탈취당할 수 있다.

## Cookies

- 사용자 컴퓨터에 저장되는 작은 파일로 HTML5보다 먼저 도입되어 HTTP 요청과 함께 서버 정보를 다시 전달해준다.
- 서버는 **특정 사용자에게 맞춤 페이지**를 전달할 수 있다.
- **유효기간**이 있어 쿠키가 생성될 때 설정할 수 있다.
- **최대 4KB**의 용량을 갖고 있어 서버에 부담을 주지 않는다. → 작은 용량으로 인해 token을 저장하지 못할 수 있다.
- 새 웹페이지가 로드될 때 쿠키의 데이터가 사용되며, **문자열만 저장**할 수 있다.

| 종류               | 특징                                                                                                                                                                        |
| ------------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| persistent cookies | - 만료일이 포함되어 있다.<br>- 만료일까지 사용자의 디스크에 저장되고 만료일이 지나면 삭제된다.<br>-사용자 맞춤 경험을 위해 특정 웹사이트에서 요구할 수 있다.                |
| session cookies    | - 만료일을 포함하지 않는다.<br>- 브라우저나 탭이 열려있는 동안에만 저장되어 브라우저가 닫히면 cookies는 삭제된다.<br>- 은행을 사용하는 사용자의 자격을 증명하는데 사용된다. |

- JavaScript로 접근이 불가능하다.(완전히 안전한 것은 아님) → cookie의 `httpOnly` 또는 `secure` 옵션을 사용하여 예방한다.
- **CSRF 공격**에 취약하다.

  > CSRF(Cross-site request forgery)?
  >
  > - 사용자가 의도하지 않은 요청을 하도록 만드는 공격
  >
  > - `sameSite` 플래그와 `anti-CRSF token`을 사용하면 해결할 수 있다.

### reference

- https://stackoverflow.com/questions/3220660/local-storage-vs-cookies
- https://medium.com/swlh/cookies-vs-localstorage-whats-the-difference-d99f0eb09b44
- https://codeburst.io/localstorage-vs-cookies-all-you-need-to-know-about-storing-jwt-tokens-securely-in-the-front-end-70dc0a9b3ad3
