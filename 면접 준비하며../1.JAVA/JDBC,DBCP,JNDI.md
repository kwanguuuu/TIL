JDBC DBCP JNDI 의 차이



### 1. JDBC(Java Database Connectivity)

데이터베이스 커넥션 인터페이스

자바 프로그래밍의 일반적인 데이터 엑세스를 제공함

JDBC API로 DBMS를 사용하려면, JDBC 기반의 DBMS 드라이버가 필요하다.



JDBC - DB에서 정보를 가져올 때 매번 디비를 열고 닫는다.

디비풀을 사용하지 않고, db통신이 필요한 부분은 db객체 생성, 커넥션 연결, 커넥션 종료 등을 반복해 효율이 나쁘다.

때문에, 상용 어플리케이션은 JDBC방식이 아닌 Pool방식을 사용한다.

Pool 방식을 사용하기 떄문에, DBCP인터페이스가 필요하다.



DBCP는 어플리케이션 시작 시 원하는 만큼 커넥션 객체를 만들고 pool에 보유했다가, 필요할 때 마다 가져다 쓰고 반납하는 방식으로 운영한다.

다중 스레드를 스레드 풀로 관리하는 것과 비슷



JNDI는 WAS에 데이터베이스 커넥션 객체를 네이밍 해두는 방식. was에 데이터베이스 풀을 미리 네이밍 해 둠

WAS풀을 사용 시 이점

1. DB 설정 정보를 파악하기 쉽다
2. DB 커넥션 풀을 효율적으로 사용할 수 있다.

