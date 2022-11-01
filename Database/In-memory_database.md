# In-memory database

- 주 메모리에 데이터를 저장하는 데이터베이스.
- 보조 기억 장치(하드 디스크, SSD; Solid State Drive)를 사용하는 기존 데이터베이스에 비해 **빠르게** 데이터를 읽고(read), 쓸 수(write) 있다.

  > CPU는 주 메모리에 저장된 데이터에만 직접 접속할 수 있다.

## 장점

- [빠른 성능](https://2kindsofcs.tistory.com/40)
- **저장 구조가 간단**하다: 주 메모리에서 데이터를 무작위로 access하는 것이 효율적이다.
- 서비스의 향상 또는 데이터베이스를 빠르게 조작해야 할 때 사용한다.

  - 자주 사용하는 데이터(Caching)
  - sessionStorage
  - 트래픽이 크게 증가하는 응용 프로그램(**실시간** 분석)
  - 보조 기억 장치가 없는 embedded system(전자레인지, ATM, 휴대폰 등)
  - 데이터 요구 사항이 낮은 애플리케이션

## 단점

- 대용량 데이터를 처리하는데 한계가 있다. → 여러 대의 컴퓨터를 연결해서 주 메모리 크기를 늘리거나 멀티 코어 컴퓨터로 랜덤 액세스 메모리의 크기를 확장할 수 있다.
- **휘발성** 메모리: 데이터베이스를 재구성하거나 프로세스 또는 서버 장애시 데이터를 잃을 위험이 있다.

### ACID 중 내구성(Durability)을 보장하기 위한 방법

- **Snapshot**

  > 사진 찍듯이 특정 시점에 스토리지의 파일 시스템을 포착해 보관하는 기술.

  - 데이터베이스의 주기적인 스냅샷으로 디스크 드라이브(비휘발성)에 저장한다.
  - 장애나 데이터 손상시 스냅샷을 생성한 시점으로 데이터를 복구할 수 있지만, 내구성이 보장되지 않을 수 있다.
  - 스냅샷 이후의 모든 변경 사항은 손실된다.
  - [Snapshot vs Backup](https://library.gabia.com/contents/infrahosting/8976/)

- **트랜잭션 로깅(Transaction logging)**

  - 데이터베이스에 대해 진행한 모든 수정 기록을 보관한다.
  - 해당 로그는 데이터베이스를 복구하는데 사용할 수 있는 비휘발성 파일에 저장된다.
  - 시스템의 성능과 저장 용량에 과부하를 제공하는 단점이 있다.
  - 대부분의 In-memory DB는 스냅샷이 만들어질 때까지 트랜잭션 로그를 보관했다가 이후 삭제한다.

- **비휘발성 랜덤 액세스 메모리(NVRAM; Non-volatile random-access memory) 사용**

  - 전원이 꺼져도 데이터를 유지한다.
  - 데이터 내구성을 위해 주로 사용하는 방법이다.

## Redis

- 데이터베이스, 캐시, 메시지 브로커 및 스트리밍 엔진으로 사용되며 오픈소스다.
- string, hash, list, set, sorted set 같은 정렬된 집합을 제공한다.
- 비동기 복제(asynchronous replication)를 지원한다. _→ 무슨 말인지 모르겠으니 직접 써보면서 다시 공부하기_

### reference

- https://www.tibco.com/ko/reference-center/what-is-an-in-memory-database
- https://aws.amazon.com/nosql/in-memory/
- https://www.digi.com/blog/post/examples-of-embedded-systems
- https://redis.io/docs/about/
