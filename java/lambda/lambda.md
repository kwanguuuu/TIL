## 람다식(Lambda Expression)

이해하는 만큼, 이해한 정도로 정리하기.



### 람다식이란?

- 메서드를 '식(expression)'으로 표현한 것.

- 익명함수라고 할 수도 있음( 메서드 명, 반환값이 없음)

- 인터페이스를 통해 람다식 처럼 사용함.

- 기본문법 : (매개변수목록) -> {실행구문}

  ```java
  int[] arr = new int[5];
  Arrays.setAll(arr, (i) -> (int)(Math.random()*5)+1);
    
  ```

- 메소드의 매개변수로 전달이 가능해짐.

- 결과값으로 반환 가능



### 메서드를 람다식으로 변환한 예

```java
//Ex1
int max(int a, int b) {
  	return a > b ? a : b;
}
//위의 코드를 람다식으로
(int a, int b) -> {return a > b ? a : b;}
(int a, int b) -> a > b ? a : b  //{return ...} 을 없애고 식으로만 표현
(a, b) -> a > b ? a : b		//타입이 추론 가능하면 생략 가능
```

```java
//Ex2
void printVar(String name, int i) {
  System.out.println(name + "=" + i);
}
//Lambda
(String name, int i) -> {System.out.println(name+"="+i);}
(name, i) -> {System.out.println(name+"="+i)}
(name, i) -> System.out.println(name+"="+i)

```

```java

//Ex3
int roll() {
  return (int)(Max.random() * 6);
}
//Lambda
() -> {return (int)(Max.random()*6);}
() -> (int)(Max.random()*6)
```



### 함수형 인터페이스

> 자바에서 모든 메소드는 클래스 내에 포함되어야 하는데, 람다식은 어떤 클래스에 포함되는 것일까?

- 람다식은 익명 클래스의 객체와 동등함.

- 하나의 메소드가 선언된 인터페이스를 정의해서 람다식을 다룰 수 있음

- 인터페이스를 통해 람다식을 다룰 수 있고, 람다식을 다루기 위한 인터페이스를 **함수형 인터페이스(functional interface)** 라고 한다.

  ```java
  @FunctionalInterface
  interface MyFunction(){
    public abstract int max(int a, int b);
  }
  ```

- 오직 _<u>하나의 추상메서드만</u>_ 있어야 **람다식 : 인터페이스메서드가 1:1로 연결됨**

- **static 메서드** 와 **default 메서드**는 제약 없음

  ```java
  //Ex.
  @FunctionalInterface
  interface MyFunction {
    void myMethod();
  }
  
  void aMethod(MyFunction f) {
    f.myMethod();
  }
  ...
  
  MyFunction f = () -> System.out.println("myMethod()");
  aMethod(f);
  ```

  

