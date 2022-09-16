# Makefile

## Make?

- `Makefile`이라는 파일을 읽어 소스 코드에서 실행 가능한 프로그램과 라이브러리를 자동으로 빌드하는 빌드 자동화 도구
- 1976년 4월, Bell Labs의 Stuart Feldman이 '변경 사항이 적용되지 않은 자신의 프로그램을 디버깅한 동료의 (헛된) 경험'을 계기로 만들었다
- 통합 개발 환경 및 언어 별 컴파일러 기능을 사용하여 빌드 프로세스 관리 → Unix 계열 운영체제에서 널리 사용된다

### 장점

- 저장할 필요가 없는 중간 파일(ex. object file)을 재생성, 사용 및 삭제할 수 있다
- 소스 파일이 변경되었지만 변경되지 않았다고 설정할 수 있다 → 헤더 파일에 새 매크로를 추가할 때 유용
- 자유 소프트웨어다

## Makefile?

- Shell에서 컴파일하는 방법 중 하나
- Make의 설정 파일 → 어떤 파일을 어떠한 방식으로 컴파일할지 작성하는 파일

## 구조

```Makefile
target: dependency ...
        commands
        ...
```

- 다음과 같이 `ifndef`를 사용해서 경우에 따라 옵션을 선택하여 실행할 수 있다.

```Makefile
ifndef IS_BONUS
  OBJ = $(OBJS_BONUS)
else
  OBJ = $(OBJS)
```

### reference

- https://en.wikipedia.org/wiki/Make_(software)
- https://www.gnu.org/software/make/
- https://www.gnu.org/software/make/manual/make.html#Overview
