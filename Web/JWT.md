# JWT(Json Web Token)

- 당사자 간에 정보를 JSON 개체로 안전하게 전송하기 위한 간결하고 자가수용적(self-contained)인 방법을 정의하는 웹 표준([RFC 7519](https://www.rfc-editor.org/rfc/rfc7519)).

  > self-contained?
  >
  > - JWT 안에는 필요한 모든 정보를 자체적으로 지니고 있다.
  >
  >   - 토큰의 기본 정보
  >
  >   - 전달할 정보(유저 정보)
  >
  >   - 토큰이 검증됐다는 것을 증명할 signature
  >
  > - 디지털로 서명되어 있어 증명(verified)할 수 있고 신뢰할 수 있다.

- HTTP 헤더에 넣어 전달하거나 URL의 파라미터로 전달하는 등 쉽게 전달할 수 있다.
- 다양한 프로그래밍 언어에서 지원한다.
- `xxxxx.yyyyy.zzzzz` : 점(`.`)으로 구분하는 세 가지 파트로 구성되어있다.
  - **Header**: 헤더
  - **Payload**: 내용
  - **Signature**: 서명

## 구조

### Header

```json
{
  "alg": "HS256",
  "typ": "JWT"
}
```

- **서명 알고리즘**과 **token 타입**, 두가지 정보로 구성된다.
  - 서명 알고리즘은 보통 HMAC SHA256 또는 RSA가 사용된다. → 이 알고리즘은 Signature 부분에서 사용된다.
  - token 타입은 JWT로 지정된다.
- **Base64Url**로 인코딩을 하면 JSON 객체의 공백/엔터들이 사라지고 다음과 같은 값이 도출된다.

  ```
  eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9
  ```

  > [Base42Url](https://babyprogram.tistory.com/50)? binary-text 인코딩 방식

### Payload

```json
{
  "sub": "1234567890", // registered claims
  "name": "yeslee", // private claims
  "admin": true // public claims
}
```

- token에 담을 정보(claim)을 포함하고 있다.

  > claim(클레임)? 엔티티(보통 사용자)나 추가 데이터에 대한 설명으로 name/value 한 쌍으로 이루어져 있다.

| claim 종류        | 설명                                                                                                                                                               |
| ----------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Registered claims | - (선택 사항) token에 대한 정보를 담기 위해 사전에 정의된 claim 집합.<br> - ex) iss(발행자), expir(만료시간), sub(주제), audit(대상자)                             |
| Public claims     | - JWT 사용자가 직접 정의할 수 있다.<br>- 충돌 방지(collision-resistant)를 위해 IANA JWT 레지스트리에 정의하거나 충돌이 방지된 이름을 포함하는 URI로 정의해야 한다. |
| Private claims    | - (registered claims 또는 public claims가 아닌) 당사자간에 정보를 공유하기 위해 만들어진 사용자 정의 이름.                                                         |

- **Base64Url**로 인코딩을 하면 다음과 같은 값이 도출된다.
  ```
  eyJzdWIiOiIxMjM0NTY3ODkwIiwibmFtZSI6Inllc2xlZSIsImFkbWluIjp0cnVlfQ
  ```

### Signature

- 인코딩된 `header`, 인코딩된 `payload`, `secret`, `header`에 지정된 알고리즘을 가져와 hashing하여 생성한다.
- 위 `header` 예시에서 HMAC SHA256 알고리즘을 사용한다고 했으므로, 다음과 같은 방법으로 hashing한다.

  ```json
  HMACSHA256(
    base64UrlEncode(header) + "." +
    base64UrlEncode(payload),
    secret)
  ```

- **Base64Url**로 인코딩하고, `header`와 `payload`를 조합하면 하나의 token 값을 얻을 수 있다.

  ```
  eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9
  .eyJzdWIiOiIxMjM0NTY3ODkwIiwibmFtZSI6Inllc2xlZSIsImFkbWluIjp0cnVlfQ
  .3CvSOM1JG8ljpLDyPoFsu0DwhyLRBC8na9MPBByojvc
  ```

- **메시지 변경 유무**를 확인할 수 있고 private key로 서명된 token의 경우, 누가 JWT를 보냈는지 알 수 있다.

## 언제 주로 사용하는지?

- **인증**
  - JWT가 가장 보편적으로 사용되는 시나리오다.
  - 시용자가 로그인하면 각 request에 JWT가 포함되어 사용자가 해당 token으로 허용되는 경로, 서비스 및 리소스에 액세스할 수 있다.
- **정보 교환**
  - 당사자 간에 안전하게 정보를 전송할 수 있다.
  - public/private keypair를 사용해 JWT에 서명할 수 있기 때문에 누가 보냈는지 확인할 수 있다.
  - `header`, `payload를` 사용해 `signature`를 생성하므로 콘텐츠 변조 유무를 확인할 수 있다.

### reference

- https://jwt.io/
- https://velopert.com/2389
