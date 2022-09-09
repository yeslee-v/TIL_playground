# Raw SQL vs TypeORM

## Raw SQL
- SQL 문을 그대로 삽입
- SQL injection 위험 => TypeORM 사용
    - SQL injection: 공격자가 쿼리에 접근하여 데이터를 수정하거나 삭제하여 동작을 변경할 수 있음
    
## TypeORM
- Node.js에서 실행되고 TS로 작성된 ORM
- N+1 문제
- 복잡한 query 문제 => QueryBuilder 사용


### reference

- https://levelup.gitconnected.com/raw-sql-vs-query-builder-vs-orm-eee72dbdd275
- https://noirstar.tistory.com/264
- https://itchallenger.tistory.com/494
- https://stackoverflow.com/questions/97197/what-is-the-n1-selects-problem-in-orm-object-relational-mapping