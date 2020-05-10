###스프링 부트가 필요한 이유

스프링 프로젝로, 스프링 어플리케이션 개발 시 , 해야할 설정이 너무 많음

- HibernateDataSource, EntityManager, SessionFactory,TransactionManager

스프링 부트는 스프링의 설정관련 이슈를 해결하는 것

- 자동설정(AutoConfiguration)을 이용하여 어플리케이션 개발에 필요한 디펜던시를 관리함.
- 사용하는 jar라이브러리의 버전을 서로 호환되는것을 따로 선택해줘야함.  boot-starter를 이용해 필요한 기능들을 버전관리 해줌