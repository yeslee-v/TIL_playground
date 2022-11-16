# What is TypeScript?

- 2012년 10월, Microsoft에서 개발

- 대규모 응용 프로그램을 개발하기 위한 객체 지향 [무료 오픈 소스 프로그래밍 언어](https://github.com/microsoft/TypeScript)

- 클라이언트 측 프로그래밍 언어인 JavaScript가 서버 측 언어로 사용하기에 한계(OOP 요구 사항을 충족하지 못함)

- JavaScript의 상위 집합 → JavaScript로 변환되어 컴파일(Transpiled)

- 정적 타이핑 기능 지원(JavaScript는 미지원)

  - 정적 타이핑(Static typing): 코드를 작성할 때 컴퓨터적 구조 명시
    ```c
    int a = 42;
    ```

- 쉬운 유지 관리 및 프로젝트 생산성 향상

- 컴파일 오류로 문제를 찾기 쉬움 → 런타임 오류 발생 적음

- 코드 컴파일하는데 시간이 걸림

- Nest.js는 TypeScript로 기본 언어로 채택

## Type System

- 프로그램을 실행하기 전에 표시 오류가 발생하지 않을 것인지 자동으로 결정한다.

- 정확성: 논리적 오류(컴파일 에러, 런타임 오류 등)를 감지한다.
- 성능: 컴파일러 최적화를 허용한다.
- 문서화: 변수, 매개변수 및 반환 값의 의미론적 의미 전달 → 개발자에게 추상화(abstract)를 제공한다.
- [타입 호환성](https://toss.tech/article/typescript-type-compatibility)

### reference

- https://en.wikipedia.org/wiki/TypeScript
- https://www.geeksforgeeks.org/difference-between-typescript-and-javascript/
- https://radixweb.com/blog/typescript-vs-javascript
- https://ahnheejong.name/articles/types-intro/
- https://www.quora.com/Why-do-programming-languages-use-type-systems
