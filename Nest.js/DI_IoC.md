# DI & IoC

## Injection

- token에 의해 다른 구성 요소에 주입
    ```typescript
    @Inject('ASYNC_CONNECTION')
    ```


## @Injectable() decorator

- metadata를 첨부하여 해당 서비스가 Nest IOC 컨테이너에서 관리할 수 있는 클래스임을 선언
- Nest의 경우, Nest.js 런타임 시스템


## @InjectRepository()

- 아무 것도 inject 하지 않음 → custom provider와 일치하도록 Nest의 metadata 설정


## IoC(Invision of Control)
- 제어의 역전 → `inject()` 사용
- 기존 제어 흐름과 비교해 제어 흐름 반전 → 외부(프레임워크)에서 제어함
    - 제어 흐름: 명령형 프로그램의 개별 명령문 또는 함수 호출이 실행되거나 평가되는 순서
    - 명시적 제어 흐름에 따라 명령형 프로그래밍 언어(how), 선언적 프로그래밍 언어(what) 구별
- 객체의 흐름을 외부에서 제어하면?
    - 객체의 LifeCycle을 프레임워크에서 도맡음 → 개발자는 비즈니스 로직 작성에만 집중할 수 있다
- 객체 지향 원칙을 잘 지키기 위해 + 역할과 관심 분리 → 응집도를 높이면서 결합도를 낮춘다 → 유지보수성 높은 코드화
- `Hollywood Principle`: Don’t call us, we’ll call you → 주도권은 외부에게 


## DIP(Dependency Inversion Principle)
- 의존성 주입
- 상위 레벨의 모듈은 절대 하위 레벨 모듈에 의존하지 않는다 → 둘 다 추상화(abstract)에 의존
- 저수준 모듈이 고수준 모듈에 의존
    ```typescript
    // 고수준 모듈                                   // 저수준 모듈
    sandwich  --------> Interface Bread <-------- white, wheat, flatbread..
    ```


### IoC + DIP 적용
- 둘 다 같은 목적을 가지고 있으므로 동시에 사용하는 것 추천
- 둘 다 클래스간 결합을 느슨하게 하기 위함 → 한 클래스의 변경에 따라 다른 클래스들의 영향 최소화 → 어플리케이션을 지속 가능하고 확장성있게 만든다  

- 예시
    - [적용 전] 만약 빵을 다른 종류로 바꾸고 싶을 때 문제 발생 → 샌드위치 재료가 이미 다 정해져 있기 때문에

        ```typescript
        public class Sandwich {    // 고수준 모듈
            WhiteBread whiteBread;   // 저수준 모듈
            Avocado avocado;
            ChiliSauce chiliSauce;
            OnionSauce onionSauce ;

            public Sandwich() {
                this.whiteBread = new WhiteBread();
                this.avocado= new AddOption ();
                this.chiliSauce= new ChiliSauce ();
                this.onionSauce = new OnionSauce ();
            }
        }
        ```
    - [적용 후] 샌드위치를 만드는데 빵, 아보카도 유무, 소스 종류를 외부에서 선택(생성시 인자로 받는다)
    - 종류에 의존하지 않음 → 주도권이 외부에 있어 유연하다

        ```typescript
        public class Sandwich {
            Bread bread;
            Avocado avocado;
            List<Sauce> sauces;

            public Sandwich(Bread bread, addOption avocado, List<Sauce> sauces) {
                this.bread = bread;
                this.addOption = avocado;
                this.sauces = sauces;
            }
        }
        ```


## DI(Dependency Injection)

- 의존성을 다른 곳으로부터 주입 → IoC를 달성하는 디자인 패턴
- 클래스 간에 의존 관계가 있다는 것 = 한 클래스가 바뀔 때 다른 클래스가 영향을 받는다
- 장점
    - 의존성이 줄어들고 가독성이 높아진다
    - 재사용성이 높고 테스트하기 좋은 코드
- 패턴
    1. 생성자 주입
        - Ioc + DIC 처럼 외부로부터 인자를 받아 생성자에 의존성 주입
    2. setter 주입
        - 각 인자당 setter를 만들어 호출
    3. interface 주입
        - interface를 만들어 override
        - DI 메소드를 빠트릴 수 있는 setter와는 다르게 override를 통한 메서드 구현을 강제할 수 있음
            ```typescript
            public class Sandwich implements RecipeInjection {
                WhiteBread whiteBread;
                Avocado avocado;
                ChiliSauce chiliSauce;
                OnionSauce onionSauce ;

                @Override
                public void inject(WhiteBread whiteBread, Avocado avocado, ChiliSauce chiliSauce,	OnionSauce onionSauce) {
                    this.whiteBread = whiteBread;
                    this.avocado = avocado;
                    this.chiliSauce= chiliSauce;
                    this.onionSauce = onionSauce;
                }
            }

            interface RecipeInjection {
                inject(WhiteBread whiteBread, Avocado avocado, ChiliSauce chiliSauce,	OnionSauce onionSauce);
            }
            ```
        - `의존성 분리`
            - DI를 이용해 의존 관계를 분리시킨다
            - 상위 계층이 하위 계층에 의존하는 상황을 Interface를 이용해 반전 → 하위 계층의 구현으로부터 독립시킨다


### reference

- https://tecoble.techcourse.co.kr/post/2021-04-27-dependency-injection/
- https://iborymagic.tistory.com/73
- https://www.youtube.com/watch?v=8lp_nHicYd4
- https://day0404.tistory.com/48
- https://ganzicoder.tistory.com/163