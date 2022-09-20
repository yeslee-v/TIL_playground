# mocha

- 테스트 코드를 돌려주는 test runner
- test suit: 테스트 환경 → `describe()`로 구현
- test case: 실제 테스트 → `it()`으로 구현

- `done()`

  - test callback에 done 추가 → 테스트를 완료하기 위해 이 함수가 호출될 때까지 기다림
  - 이 callback은 오류 인스턴스(또는 해당 하위 클래스) 또는 잘못된 값 모두 수락
  - 한 번만 사용해야 한다 → 2번 이상 사용시 에러 발생

## should

- 노드 assert 말고 서드파티 라이브러리를 사용하라
- should는 검증(assertion) 라이브러리다
- 가독성 높은 테스트 코드를 만들 수 있다

## superTest

- 단위 테스트: 함수의 기능 테스트
- 통합 테스트: API의 기능 테스트
- express 통합 테스트용 라이브러리
- 내부적으로 express 서버를 구동시켜 실제 요청을 보낸 뒤 결과를 검증한다

### reference

- https://mochajs.org/
- https://expressjs.com/en/5x/api.html
- https://github.com/visionmedia/supertest
