### 톰캣 OOM 원인 & 처리 관련

톰캣 오류중 PermGen space error 는 가용할 수 있는 메모리보다 어플리케이션이 메모리를 많이 사용해서 그렇다.

### 주요 원인

- tomcat의 힙 메모리가 부족해서



### 다양한 해결방법

- catalina.sh 의 maxPermSize를 수정해줌
- catalina.bat 의 setlocal등의 설정을 지움
- JRE메모리 누수 처리
- Thread pool설정



https://aljjabaegi.tistory.com/218



