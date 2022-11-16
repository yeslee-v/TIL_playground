# ORM(Object Relational Mapping)

- 데이터베이스를 객체로 추상화한 것으로 query를 직접 작성하는 대신 ORM의 **method**를 데이터로 관리할 수 있다.
- 코드가 깔끔해지는 반면 성능상의 이슈가 있다.
  ex) `Sequelize`(node SQL ORM)
  ```sql
  select * from users; → User.findAll()
  ```

## Model

- 데이터베이스 테이블을 ORM으로 추상화한 것이다.
  ```javascript
  sequelize.define(); // define model
  sequelize.sync(); // connect db
  ```
