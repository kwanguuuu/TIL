### Dirty Checking

- JPA의 Entity Manager가 엔티티를 저장/조회/수정/삭제 할 때,
- EntityManager의 메서드 중에는 update가 없음.
- update는 **DirtyChecking**을 지원하여 사용함.
- 트랜잭션 안의 엔티티 변경이 일어나면, 변경 내용을 자동으로 데이터베이스에 반영하는 JPA의 특징
- **데이터베이스 변경데이터 저장 시점**
  1. Transactional commit
  2. EntityManager flush
  3. JPQL 사용
- 영속성 컨텍스트안에 있는 엔티티를 대상으로 더티체킹이 일어남.

상태변경검사

트랜잭션이 끝나는 시점에 변화가 있는 모든 엔티티 객체를 데이터베이스에 자동으로 반영해줌.

영속성컨텍스트가 관리하는 엔티티에만 적용됨.



@DynamicUpdate

변경된 필드만 update되도록 반영 할 수 있음.

