Java Persistence Query Language

- 테이블을 대상으로 쿼리하는 것이 아니라, 엔티티 객체를 대상으로 쿼리 한다
- SQ



TypeQuery, Query

- TypeQuery : 반환 타입이 명확할 떄
- Query : 반환 타입이 명확하지 않을 때 사용



결과조회 API

- query.getResultList() : 결과가 하나 이상 일 때, 리스트 반환
  - 결과 없으면 빈 리스트 반환
- query.getSingleResult() : 결과가 정확히 하나. 단일 객체 반환
  - 결과가 없으면 javax.persistence.NoResultException
  - 둘 이상이면 javax.persistence.NomUniqueResultException

### 파라미터 바인딩 - 이름 기준, 위치기준

```java
//이름 기준
SELECT m FROM Member M where m.username=:username
query.setParameter("username",usernameParam);

//위치기준
SELECT m from Member m where m.username=?1
  query.setParameter(1,usernameParam);
```



