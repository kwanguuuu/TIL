## 엔티티 매핑

JPA에서 제일 중요하게 봐야하는 것 두개중 하나.

1. JPA 메카니즘 측면 (영속성 컨텍스트 등)
2. 설계적 측면 ( 엔티티 매핑이 설계에 포함된다.)



관계형 DB 설계 할 때 보면,

테이블 생성 -> 테이블 컬럼 설정 -> 키 설정 -> 연관관계 설정

을 JPA에선

@Entity -> @Column -> @Id -> @manyToOne, @JoinColumn

으로 진행된다. 해당 목적에 맞는 어노테이션들을 생각해야함.

---

### 객체와 테이블 매핑

**1. @Entity**

정의

- @Entity가 붙은 클래스는 JPA가 관리함. 엔티티라고 부른다
- JPA사용해 테이블과 매핑할 클래스는 @Entity로 해야함.
  - 기본생성자(public, protected) 로 사용함
  - final, enum, interface, inner 클래스 등 사용할 수 없음
  - 저장할 필드에 final 사용 못함.

@Entity 속성 정리

- 속성: @name
  - JPA 사용할 엔티티 지정함.
  - 기본값 : 클래스명 ( 안쓰면 헷갈려서 그냥 기본값 씀 -> @Name잘 안씀)



### 필드와 컬럼 매핑 어노테이션들

```text
ex. 
	회원은 일반회원, 관리자로 구분해야 한다.
	회원은 가입일과 수정일이 있어야한다.
	회원을 설명할 수 있는 필드가 있어야한다. 필드 길이는 제한이 없다.
```

- @Column : 컬럼 매핑
- @Enumerated : enum 매핑
- @ Temporal : 날짜 매핑
- @Lob : blob, clob 매핑
- @Transient : db와 상관없이.

1. @Column

| 속성             | 설명                                                         | 기본값          |
| ---------------- | ------------------------------------------------------------ | --------------- |
| name             | 필드와 매핑할 테이블의 컬럼 이름                             | 클래스의 필드명 |
| updatable        |                                                              |                 |
| nullable         | Null값 허용 여부 설정. false 설정 하면 not null 제약조건이 됨 |                 |
| unique           | 유니크 제약조건 씀. (이름 반영이 어려워서, Column에 안쓰고, @Table에 쓰는걸 선호) |                 |
| columnDefinition | 컬럼 정보를 직접 줄 수 있음.                                 |                 |
| length           | 문자 길이 제약조건. String타입에만 사용한다                  |                 |
| precision        | BigDecimal에 사용함.                                         |                 |



2. @Enumerate

| 속성     | 설명                                                         | 기본값           |
| -------- | ------------------------------------------------------------ | ---------------- |
| EnumType | EnumTYpe.ORDINAL : enum순서를 데이터베이스에 저장<br />EnumType.STRING : 이름을 데이터베이스에 저장 | EnumType.ORDINAL |



3. @Temporal

옛날엔 필요했는데 지금(java8)은 필요없음

LocalDate, LocalDateTime을 사용하면 사용할 필요가 없음.





4. @Lob

문자 : CLOB으로 매핑, 나머지는 BLOB으로 매핑됨

