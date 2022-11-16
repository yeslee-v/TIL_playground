# Decorator

- 새 함수를 반환하여 전달된 함수 또는 메서드의 동작을 수정하는 함수
- 앞에 `@`를 붙임 + 꾸미려고 하는 클래스 또한 함수 맨 위에 배치하여 적용
- 클래스, 메서드 또는 프로퍼티에 대해 정의 → 런타임에 호출되는 함수

  ```typescript
  function deco(
    target: any,
    propertyKey: string,
    descriptor: PropertyDescriptor
  ) {
    console.log("evaluate decorator");
  }

  class TestClass {
    @deco
    test() {
      console.log("call function");
    }
  }

  const t = new TestClass();
  t.test();

  // evaluate decorator
  // call function
  ```

- `tsconfig.json`에서 `experimentalDecorators`가 `true`여야 함

  ```json
  {
      "compilerOptions": {
          ...
          "experimentalDecorators": true,
          ...
      }
  }
  ```

- Nest는 HTTP route handler와 함께 사용할 수 있는 매개변수 데코레이터 세트 제공

  ex) @Request, @Req() → req, @Response, @Res() → res

### reference

- https://docs.nestjs.com/custom-decorators
- https://wikidocs.net/158481
