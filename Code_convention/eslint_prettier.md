# Eslint & Prettier

## Eslint

- `linting`

  - C용 유닉스 유틸리티에서 유래
  - 프로그래밍 및 스타일 오류에 대한 소스 코드 자동 검사
  - linter(정적 코드 분석기)를 사용하여 수행

- 오류를 줄이고 코드의 전반적인 품질 개선 => 개발 가속화 + 비용 절감
- 인터프리터 언어(Python, JavaScript 등)는 컴파일 과정 없이 바로 실행 => 프로그램을 실행시켜야 오류를 알 수 있음
- 이 때 lint를 사용하면 일관된 코딩 스타일을 보장 + 기본 코딩 오류 해결

- `Eslint`: JavaScript lint 도구, TypeScript lint 가능

### Prettier

- 코드 가독성 향상 및 `일관된 코딩 스타일`

```javascript
// pritter 적용 전

foo(
  reallyLongArg(),
  omgSoManyParameters(),
  IShouldRefactorThis(),
  isThereSeriouslyAnotherOne()
);
```

```javascript
// pritter 적용 후

foo(
  reallyLongArg(),
  omgSoManyParameters(),
  IShouldRefactorThis(),
  isThereSeriouslyAnotherOne()
);
```

### reference

- https://www.perforce.com/blog/qac/what-lint-code-and-why-linting-important
- https://helloinyong.tistory.com/325
- https://prettier.io/docs/en/index.html
