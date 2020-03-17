### 람다식의 타입과 형변환

- 함수형 인터페이스로 람다식을 참조 할 수 있지만, 람다식의 타입이 함수형 인터페이스 타입과 일치 하는 것은 아니다.

- 람다식 : 익명객체  & 익명객체 : 타입이 없음.

- 정확히는, 컴파일러가 타입을 임의로 지정하기 때문에, 이름을 알 수 없음

  ```java
  MyFunction f = (MyFunction)(()->{});	//타입이 달라 형변환 필요. 형변환 생략가능
  ```

- 람다식은 Object 타입으로 형변환 할 수 없다.

- 오직 함수형 인터페이스로만 형변환 가능함

  ```	java
  Object obj = (Object)(()->{}); //compile error
  Object obj = (Object)(MyFunction)(()->{});
  String str = ((Object)(MyFunction)(()->{})).toString()
  ```

  

