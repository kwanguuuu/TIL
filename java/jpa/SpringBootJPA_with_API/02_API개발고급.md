JPA하면서 자주 만나는 이슈들

- N+1 문제
- 컬렉션 최적화 문제
- 페이징 성능 문제
- 오픈세션인뷰(OSIV)

지연로딩과 조회 성능 최적화



@Entity직접 사용시 문제들

- 무한루프
- 무한루프 해결 -> @JsonIgnore
- @JsonIgnore 를 실행 시 오류가 남. ( ByteBuddyInterceptor에 관련된 프록시 기술에 오류가 남.)
- 이를 해결하기 위해서hibernate5module 이 필요함. -> springbean으로 등록해야함



@DTO로 변환 ( 일반. v2)

- 엔티티 직접 호출을 변경함
  - @JsonIgnore같은 엔티티의존 어노테이션
  - 엔티티가 변경되면 api스펙이 변경됨
- DTO로 받아서, @XtoOne을 Lazy로 설정
- lazy로딩으로만 조회 시, 쿼리가 여럿 나가는 문제가 발생
  - 왜?
  - 영속성 컨텍스트에 엔티티 등록 시, lazy 로딩으로 설정하면 엔티티 > 안의 엔티티 연관관계 맺은 필드가 사용될 때 영속성 컨텍스트에 포함되고, 그렇게 되면서 조회를 위한 쿼리가 실행이됨.
  - 쿼리의 실행이 데이터가 많은면 많을 수록 많아져서, 성능상의 이슈를 발생시킴
- N+1 문제 발생



페치 조인으로 최적화

- 페치조인을 통해 Lazy 로딩으로 인해 발생하는 쿼리를 최소화
- 최초 조회시 전부 join해서 가져옴.



JPA에서 DTO로 바로 조회하기

- Entity를 가지고 와서 DTO로 변환했는데, 바로 DTO로 변환하기
- new 명령어를 사용해 JPQL의 결과를 DTO로 바로 변환
- select에서 원하는 데이터를 직접 선택해 애플리케이션 네트웍 용량 최적화 함
- 리포지토리 재사용성이 떨어짐.