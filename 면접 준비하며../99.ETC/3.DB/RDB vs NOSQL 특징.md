RDB랑 NoSQL 개념, 적절히 사용하는 방법 등 물어 볼 수 있을듯

### RDM

일반적인 관계형 데이터베이스

**테이블 마다 스키마를 정의(스키마 정의는 DDL) 해야함**

데이터 타입과 제약을 통해 정확성을 보장함

SQL문으로 처리함.

확장성이 좋지 않다



### NOSQL

Documents형, Key-Value형, Table형 등

RDB 확장성의 이슈를 해결하기 위해 나옴

분산 컴퓨팅을 목적으로, 스케일 아웃 하기가 쉬움

큰 테이블 하나를 사용함.

key-value방식의 테이블 많이 사용함(레디스)

**schema less**함. (구조변경 용이, 데이터 형식 다양, 바꾸기쉬움, 정확성보단 양이 중요)

---

### 데이터 확장에 대한 이슈

RDM -> 일반적으로 수직적확장(서버의 성능을 향상 시키는 것)으로 가능함 (샤딩이 있지만, 개발자가 다루기 어려운 점)

Nosql -> 기본적으로 수평적 확장을 제공



### SQL과 NoSql 사용 시점

데이터의 값이 자주 변경(수정)되는 어플리케이션 -> SQL

- NoSQL은 데이터의 모든 컬렉션에서 업데이트를 해줘야함(무결성을 보장하지 않는 경우기 많아서)

스키마가 명확하고, 변경될 여지가 없는 경우, 데이터의 정확성이 시스템&사용자 모두에게 중요한 경우 -> SQL

정확한 데이터를 알 수 없거나 초기 변경이 많은 경우 -> NoSQL (하지만 결정을 미루게 될 여지도 있다)

읽기를 자주 하지만, 데이터의 값을 자주ㅡ 변경하지 않는경우 -> NoSQL

데이터베이스 수평적으로 확장하는 경우 



### NoSQL 사용 기능 예

- 구매내역, 시스템 로그 등



