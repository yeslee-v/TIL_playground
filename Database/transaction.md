# Transaction

- 묶어서 실행하고 싶은 SQL 명령 또는 단계적으로 처리해야할 때 트랜잭션 내에서 실행한다.
- MySQL 클라이언트에서 명령을 실행할 때에는 자동커밋이 켜져있어 트랜잭션을 사용하여 데이터를 추가할 때는 다음 명령어를 사용해 **자동커밋을 꺼야**한다.

  > MySQL: `START TRANSACTION`
  >
  > SQL Server, PostgreSQL: `BEGIN TRANSACTION`

  > 자동커밋? 클라이언트 툴의 기능으로 말 그대로 자동으로 커밋해주는 기능이다.

- 커밋(commit): 트랜잭션 내에 실행한 (변경된)명령을 적용하고 종료한다.
- 롤백(rollback): 트랙잭션 내에 실행한 명령을 파기하고 종료하므로 변경한 내용이 적용되지 않는다.

```sql
START TRANSACTION
COMMIT
ROLLBACK
```
