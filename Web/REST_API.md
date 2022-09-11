# REST API

- Representational State Transfer
- 분산 하이퍼미디어 시스템을 위한 아키텍처 스타일 → web의 장점을 최대한 활용할 수 있는 아키텍처
- 자원(Resource, URI), 행위(HTTP Method), 표현(Representations)으로 이루어져 있다

## RESTful 아키텍처의 6가지 제약 조건

- 다음 6가지 조건을 따르는 API를 `RESTful API`라고 한다

### Uniform interface

- 시스템의 리소스에는 하나의 논리적 URI만 있어야 → 리소스는 웹페이지와 동의어로 사용하는 것이 좋다

### Client - Server

- 클라이언트 - 서버 응용 프로그램이 서로에 대한 종속성없이 별도로 발전해야

### Stateless

- 서버는 클라이언트가 만든 최신 HTTP 요청에 대해 아무 것도 저장하지 않는다
- 쿠키 또는 세션 정보를 별도로 저장하거나 관리하지 않음 → API 서버는 들어오는 요청만을 단순 처리한다
- 서비스의 자유도가 높아지고 구현이 단순해진다

### Cacheable

- REST는 HTTP에서 영감을 얻었기 때문에 그대로 사용
- 웹에서 사용하는 기존 인프라를 그대로 활용함 → HTTP가 가진 캐싱 기능이 적용 가능함
- 부하 감소 → 클라이언트 측의 성능 + 서버의 확장성 범위 향상

### Layered system

- 다중 계층으로 구성
- 서버 A에 API 배포, 서버 B에 데이터 저장, 서버 C에서 요청을 인증하는 계층화된 시스템 아키텍처 사용

### Code on demand(optional)

- 서버는 클라이언트가 실행할 수 있는 로직 전송하여 기능 확장할 수 있다

## REST API 디자인 가이드

- URI(Uniform Resource Identifier)는 정보의 자원을 표현해야 한다
- 자원에 대한 행위는 HTTP Method(GET, POST, PUT, PATCH, DELETE)로 표현한다

### reference

- https://restfulapi.net/
- https://meetup.toast.com/posts/92
- https://spoqa.github.io/2012/02/27/rest-introduction.html
