## @Transactional

트랜잭션에 관련된 ACID 원칙을 지키기 위해 사용.

트랜잭션 : 데이터베이스 상태를 변화시키는 **논리적 작업단위**

ACID 

- Atomicity ( 원자성 ) : 실행되다 중단되지 않는 것. ( 시작 -> 끝 / 중간까지만 시작 -> 중간이후 실패 는 없음)
- Consistency ( 일관성 ) : 성공 & 실패하면 성공&실패 상태로 유지해야함
- Isolation ( 독립성 ) : 다른 트랜잭션이 끼어들지 못하도록
- Duration ( 지속성 ) : 성공한 트랜잭션은 영원히 반영디어야



회사에서 왜 @Transactional 안 썻을까? TransactionManager를 AOP로 persistence 있는 것들을 사용해서 그런것인가



https://itjava.tistory.com/118