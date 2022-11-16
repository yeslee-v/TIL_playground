# Database(DB)

- 여러 사람이 공유하여 사용할 목적으로 체계화해 통합, 관리하는 데이터 집합

## Database Management System(DBMS)

- 데이터베이스 관리 시스템으로 데이터베이스를 효율적으로 관리하는 소프트웨어.
- 시스템 개발 과정에서의 **생산성 향상**: 데이터 검색, 추가, 삭제, 갱신 등의 처리 기능을 제공한다.
- **복수 유저의 요청 또는 대용량 데이터 저장 및 검색** 기능을 제공한다.
- 많은 요청에 대응하기 위해 하드웨어를 여러 대 구성, **신뢰성 및 성능을 향상**시킨다.
  - 클러스터 구성(스케일 아웃): 일부 DBMS는 컴퓨터를 여러 대 두고, 소프트웨어를 통해 확장성(Scalability) 및 부하 분산(Load balancing)구현

### SQL

- IBM에서 개발한 SEQUEL이라는 관계형 데이터베이스 관리 시스템(RDBMS; Relational Database Management System) 조작용 언어를 기반으로 만들어진 언어.
- SQL 명령 종류

  - **DML(Data Manipulation Language)**: SQL의 가장 기본이 되는 명령어 셋(Set)으로 데이터를 조작할 때 사용한다.
  - **DDL(Data Definition Language)**: 데이터를 정의하는 명령어로 데이터베이스 객체(object)를 생성, 삭제할 때 사용한다.
  - **DCL(Data Control Language)**: 데이터를 제어하는 명령어로 트랜젝션을 제어하거나 데이터 접근권한을 제어하는 명령이 포함되어 있다.

- **RDB(Relational Database)**: SQL로 데이터를 다루는 데이터베이스

## Database 종류

- 데이터 저장 방법에 따라 분류한다.

| 종류                                       | 특징                                                                                                                                                                                                                                                                                                  |
| ------------------------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 계층형 데이터베이스                        | - 폴더와 파일 등의 계층 구조로 데이터를 저장한다.<br>- 오래된 역사에 비해 현재는 DBMS로서 채택되는 경우가 많지 않다.                                                                                                                                                                                  |
| 관계형 데이터베이스                        | - 관계 대수(relational algebra)에서 고안한 데이터베이스로 행과 열을 가지는 표 형식 데이터(2차원 데이터)를 저장한다.<br>&nbsp; ex) MYSQL, PostgreSQL, Aurora, SQLite(파일 형태의 아주 작은 데이터베이스)                                                                                               |
| 객체지향 데이터베이스                      | - 객체(object) 그대로 데이터베이스의 데이터로 저장한다.                                                                                                                                                                                                                                               |
| XML 데이터베이스                           | - XML 자료 형식으로 기록된 데이터를 저장한다.<br>- SQL 명령 대신 XQuery 전용 명령어를 사용한다.                                                                                                                                                                                                       |
| 열 지향 데이터베이스(KVS; Key-value store) | - 키와 그에 대응하는 값(value)라는 단순한 형태의 데이터를 저장한다.<br>- 연상배열(associative array) 또는 해시 테이블(hash table)에서 자주 볼 수 있다.<br> **NOSQL(Not only SQL)**<br>&nbsp;- document 형식의 데이터베이스로 데이터베이스 형식을 쉽게 변경할 수 있다.<br> &nbsp;ex) MongoDB, DynamoDB |

> ⚠️ _모바일의 경우, [한정된 자원과 컴퓨터에 비해 낮은 CPU 성능](https://edmblackbox.tistory.com/614)으로 Oracle, MySQL 대신 SQLite를 사용한다._

### MySQL vs PostgreSQL

| 기준                                                                           | MySQL                                       | PostgreSQL                                                                |
| ------------------------------------------------------------------------------ | ------------------------------------------- | ------------------------------------------------------------------------- |
| 탄생 배경                                                                      | 1995년 스웨덴 MySQL AB 에서 개발            | 캘리포니아대 컴퓨터 과학과에서 개발                                       |
| 구현 언어                                                                      | C, C++                                      | C                                                                         |
| DBMS                                                                           | 관계형                                      | 객체기반 관계형                                                           |
| GUI                                                                            | MySQL Workbench                             | PgAdmin                                                                   |
| MView, 테이블 상속 지원 여부                                                   | X                                           | O                                                                         |
| 지원하는 데이터 타입                                                           | Standard data type만 지원                   | Advanced data type(`array`, `hstore`, `user-defined type`) 지원           |
| [MVCC(Multi-Version Concurrency Control)](http://www.gurubee.net/lecture/2398) | InnoDB에서만 지원                           | [전체 MVVC 지원](https://www.postgresql.org/docs/current/mvcc-intro.html) |
| 속도                                                                           | 간단하고 빠르며 신뢰할 수 있다.             | 느리고 복잡하다.                                                          |
| trouble shooting                                                               | 쉽다.                                       | 어렵다.                                                                   |
| 연산                                                                           | `read`, `write`같은 간단한 연산에 적합하다. | 크고 복잡한 연산에 쓰인다.                                                |

### reference

- https://www.geeksforgeeks.org/difference-between-mysql-and-postgresql/
