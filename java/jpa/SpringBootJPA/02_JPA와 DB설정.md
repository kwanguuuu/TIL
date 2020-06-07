테스트 메서드 작성에 필요한 것들

JUnit5 에서 Spring 의존 테스트 하기

- @ExtendWith(SpringExtention.class)
- SpringBootTest(classes = *@SpringBootApplication* 선언된 클래스 )
- JPA테스트 할 메서드에는
  - @Transactional 선언 ( EntityManager는 Transactional에 있을 때 동작하기 때문에)
  - @Rollback(false) : 테스트는 자동 rollback인데, 실제 데이터를 보고 싶다면..

쿼리 로그 관련 팁

- application.yml에 hibernate로그를 trace로 변경시, 파라미터가 어떤게 적용되었는지 알 수 있다.
- 외부 라이브러리를 사용하면 쿼리를 래핑해줘서 더 쉽게 볼 수 있다 ( ex. p6spy 를 build.gradle에 추가해주기)