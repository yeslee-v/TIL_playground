# Design Database

- 데이터베이스의 스키마(schema) 내에 테이블, 인덱스, 뷰 등의 데이터베이스 객체를 정의한다.

  > 스키마 설계? 스키마 내에 정의한다.

- 물리명: `CREATE TABLE`에 지정하는 테이블 이름 또는 열 이름
- 논리명: 설계상의 이름
- 데이터 크기가 크다면 LOB 자료형에 저장한다

  > LOB(Large Object)? 큰 데이터를 다루는 자료형, 인덱스를 지정할 수 없다.

## Entity Relationship Diagram(ERD)

- **개체(테이블, 뷰) 간의 관계**를 명확하게 하기 위해 작성하는 테이블 설계도.

- 관계: 관계형 데이터베이스의 relationship과 다르다.

  - 몇 대 몇의 관계를 가지는지? `1:1`, `1:n`, `n:n`

## Normalization(정규화)

- RDB가 **효율적으로 동작**할 수 있도록 테이블을 올바른 형태로 변경하고 분할한다.
- 보통 데이터베이스 설계 단계에서 행하지만, 경우에 따라 기존 시스템 재검토때 하는 경우도 있다.
- 중복하거나 반복하는 부분을 찾아 테이블을 분할하고 기본키를 작성해 사용한다 → **_하나의 데이터는 한 곳에 있어야 한다_**
- 대부분의 시스템에서는 제 3 정규형까지의 정규화를 채택한다.

  | 정규화               | 정의                                                                                                                                                                     |
  | -------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
  | **제 1 정규형(1NF)** | - RDB의 테이블에는 하나의 셀에 하나의 값만 저장할 수 있다.<br> - 중복되는 부분을 찾아 테이블을 분할하고 기본키(열)를 지정한다.<br> - 반복되는 부분은 행 방향으로 늘린다. |
  | **제 2 정규형(2NF)** | - 기본키 데이터에 중복하는 부분을 찾아 테이블로 분할한다.<br> - 기본키에 의해 특정되는 열과 그렇지 않은 열을 나눈다.                                                     |
  | **제 3 정규형(3NF)** | - 기본키 외의 데이터에 중복이 없는지 조사한다.<br>                                                                                                                       |
  | **제 4 정규형(4NF)** | <br>                                                                                                                                                                     |
  | **제 5 정규형(5NF)** | <br>                                                                                                                                                                     |
