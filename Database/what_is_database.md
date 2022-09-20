# Database

- 여러 사람이 공유하여 사용할 목적으로 체계화해 통합, 관리하는 데이터 집합

## SQL

- 테이블 형식의 database
- excel처럼 column, row가 존재한다
- SQL QUERY

  ex) MYSQL, PostgreSQL, Aurora, SQLite(파일 형태의 아주 작은 database)

## NOSQL

- document 형식의 database → JSON 형식
- database 형식을 쉽게 변경할 수 있다

  ex) MongoDB, DynamoDB

## In Memory DB

- memory 안에다 database를 만든다
- database를 재구성하면 다 날라간다
- 서비스의 향상을 위해 사용한다 → 인증 토큰, session, 자주 사용하는 데이터

  ex) Redis, Memcashed
  <br>
  </br>

# ORM(Object Relational Mapping)

- database를 객체로 추상화한 것
- query를 직접 작성하는 대신 ORM의 method를 데이터로 관리할 수 있다
- 깔끔한 코드 vs 성능 이슈
- node에서 SQL ORM은 `Sequelize`가 있다
  ```sql
  select * from users; → User.findAll()
  ```

## Model

- database 테이블을 ORM으로 추상화한 것
  ```javascript
  sequelize.define(); // define model
  sequelize.sync(); // connect db
  ```

### reference

- https://ko.wikipedia.org/wiki/%EB%8D%B0%EC%9D%B4%ED%84%B0%EB%B2%A0%EC%9D%B4%EC%8A%A4
- https://inf.run/z8CD
