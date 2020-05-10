### 1. Over View

자바 8의 옵셔널 클래스 사용하는 법 알아보기

옵셔널 클래스의 목적은, type-level을 제공하기 null 참조 대신 선택적(optional한) 값으로 나타내는 유형의 표현을 제공하는 것.

> The purpose of the class is to provide a type-level solution for representing optional values instead of *null* references.



### 2. CreatingOptional Objects

Optional 객체를 만드는 방법

- empty Optional 객체 생성

  ```java
  
  ```

- static 메소드 이용해 생성하는 방법

  ```
  	
  ```

- null 이 가능한 메소드 만드는 방법

### 3. isPresent() , isEmpty()

생성한 Optional 객체의 값이 있는 지 확인하기 위해, isPresent()를 사용함.

- isPresent()
- isEmpty()



### 4. ifPresent()

Optional 객체가 null인지 아닌지 확인 후 실행 (Null 체크 후 작업이라 생각)

```
	
```



### 5. Default Value With or Else()

orElse()는 메소드가 래핑된 값이 있으면, 그 값을 리턴, 아니면 인자값을 반환함

```

```



### 6. orElseGet()

orElse()랑 비슷하다. optional객체가 present 상태가 아니면 orElse 부분을 실행 하지만, orElseGet()은 get에 supplier<String> 인터페이스를 제공함.



**orElse와 orElseGet 의 차이점** 



### 7. orElseThrow()

감싸고 있는 객체의 값이 없으면, exception 을 던진다.

```

```



### 8. get()

Optional 의 값이 Null이 아닐 때 값을 반환함. 값이 없는 경우 Exception





