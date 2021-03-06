## 	2주차 20200325



클래스 선언 위치 -> 상수, 클래스변수, 인스턴스 변수, 생성자 순으로 위치. equals, hashcode, toString은 하단에 위치.

좋은 코드를 많이 읽어라. ( 오픈된 소스들. ex. java API, Spring API)

로컬 변수도 변경 불가능 함을 명시할 때, final 키워드를 사용해도 좋다.

테스트하기 쉬운 코드 + 테스트하기 어려운 코드 = 테스트 하기 어려운 코드 가 된다.

TDD를 잘 하려면, 테스트 하기 좋은 코드로 분리하는 연습을 해야한다.

---

### 어느 부분을 테스트 해야 할까?

	- 경계 값을 기준으로 테스트
	- assert의 최소화로 모든 case를 테스트 할 수 있게 짜는것이 중요하다.
	- 생성자는 데이터 초기화를 할 때 유용하게 사용할 수 있다.
 - private 메소드를 테스트 할 땐, public으로 우선 변경하고 테스트 한다.
   	- 테스트 후 private으로 변경
   	- 단, private이 너무 커졌을 땐, 이걸 다른 메소드 or 클래스로 변경해야 하는건 아닌지 설계를 생각해볼 의구심을 품자.



---

2주차 과제 목표

- TDD 기반 프로그래밍.
  - 필수 : **반드시 실패하는 테스트 코드를 작성 해야지만, 프로덕션 코드를 작성할 수 있다.**
  - 실패할 것이다. 라고 예측하고 프로덕션 코드를 작성하는 경우가 있는데, 지양하는 습관을 갖자
- 클래스 분리 연습.
- 일급 콜렉션 사용.
- 모든 원시값과 문자열을 포장.



TDD로 개발을 잘 하려면,

	- To-Do List 를 잘 만드는 것이 중요하다
	- To-Do List를 잘 나누는 것도 중요하다.
 - TDD의 주요 관심사는 Model이다.
   	- 연습은 Model을 잘 하려고 노력하자.
 - 구현할 기능목록 작성하기 연습하기
   	- 기능 목록은 향후 추가될 수 있다. 무서워 하지 말것
 - 테스트 하기 어려운 부분을 찾아, 가능한 구조로 개선하기
   	- Object Graph에서 다른 Object와 의존관계를 가지지 않는 마지막 노드를 찾음.
   	- 테스트 하기 어려운 코드의 의존관계를  상위 노드로 옮기라



TDD 과정

	- 잘 구현 헀으면, 컴파일 에러가 난다.
	- 컴파일 에러를 해결하면, 러닝 에러가 발생할 것이다.
	- 테스트를 패스하기 위해서 ,어떤 짓이든 한다.
	- 패스한 테스트 



tip

- 생성자가 많으면, 인자가 적은 곳 -> 인자가 많은 것 을 생성 호출 한당.
- junit 문맥이 달라지는 곳 (given, when, then)을 파악해 보기 쉽게 한다.
- 객체지향 프로그램을 하면, getter 메소드를지양해라. getter가 있으면 메세지를 보낸다 생각해보자.
- 도메인은 반드시 유효성 체크를 하는 것이 맞다.



