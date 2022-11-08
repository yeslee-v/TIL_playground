# Framework vs Library

## Framework

- 뼈대, 구조
- 더 많은 동작이 내장된 추상적인 디자인을 구현한다.
- 전체적인 흐름을 스스로 쥐고 있어 유저는 그 안에 필요한 코드를 넣는다.

  > 다른 곳으로 이동할 때 '도구'인 버스를 타고 이동하는데, '버스'가 컨트롤하고 나는 가만히 앉아 있는다.

- [IoC](../Nest.js/DI_IoC.md)와 연관지어 생각해보자.

  > _Hollyword principle: Don't call us, we'll call you._

  ex) Spring, Nest.js, Django

## Library

- 기본적으로 호출할 수 있는 함수 집합
- 유저가 전체적인 흐름을 만들면서 라이브러리를 가져다 사용한다. → 클라이언트에게 제어권 반환

  > 무언가를 적을 때 '도구'인 '펜'을 사용하여 '내가' 직접 컨트롤하여 쓴다.

  ex) Network protocols, C++ STL, npm & pip module

## **제어의 흐름이 어디에 있는가**에 따라 분류한다.

![Diagram: Framework vs Library](../Pics/framework_library.jpeg)

### reference

- https://martinfowler.com/bliki/InversionOfControl.html
- https://kldp.org/node/124237
- https://webclub.tistory.com/458
