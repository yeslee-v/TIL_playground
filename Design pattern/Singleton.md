# Singleton

- 하나의 클래스는 오직 하나의 인스턴스만을 가진다
- 생성자를 여러 번 호출해도 실제로 생성되는 객체는 하나

> - **Nest.js에서 Singleton pattern 사용하는 이유?**
>
>   - Node.js는 `single thread`로 동작한다.
>   - 각각의 클래스 인스턴스들이 singleton으로 관리되어도 성능의 문제가 없고 안전하다.
>   - instance를 직접 생성하지 않고 module을 통해 Injection하는 패턴을 권장한다.

### reference

- https://refactoring.guru/design-patterns/singleton
- https://ganzicoder.tistory.com/163
- https://www.youtube.com/watch?v=-oy5jOd5PBg&t=8s
