## Java.lang.function

일반적으로 자주 쓰이는 형식의 메서드를 함수형 인터페이스로 미리 정의해 놓음.



### 1. 매개변수가 한개인 함수형 인터페이스.

### Runnable

- void run()
- 매개변수도 없고, 반환값도 없음

### Supplier<T>

- T get()
- 매개변수는 없고, 반환값(T)만 있음

### Consumer<T>

- void accept(T t)
- 매개변수만 있고, 반환값은 없음. (Supplier와 반대)

### Function<T, R>

- R apply(T t)
- 하나의 매개변수를 받아서, 결과를 받음 _( 일반적인 형태 )_

### Predicate<T>

- boolean test(T t)

- 매개변수는 하나, 반환타입은 boolean _(조건식을 표현하는데 사용)_ 

  ```java
  //ex
  Predicate<String> isEmptyStr = s -> s.length()==0;
  String s = "";
  
  if(isEmptyStr.test(s))
    System.out.println("this is empty string");
  ```

  

### 2. 매개변수가 두 개인 함수형 인터페이스

두개는 접두사 '**Bi**'가 붙는다

### BiConsumer<T, U>

- void accept(T t, U u)
- 두개의 매개변수만 있고, 반환값이 없음

### BiPredicate<T, U>

- boolean test(T t, U u)
- 매개변수 둘, 반환값은 boolean (조건식 표현으로 사용됨)

### BiFunction<T, U, R>

- R apply(T t, U u)
- 두개의 매개변수를 받아서 하나의 결과값을 반환함

두 개 이상의 매개변수를 갖는 함수형 인터페이스는 직접 구현해야함.

```java
@FunctionalInterface	//어노테이션이 필수는 아님, 하지만 선언해주면 funtional interface인지 아닌지 구분해줌.
interface TriFunction<T,U,V,R> {
  R apply(T t, U u, V v, R r);
}
```



### 3. UnaryOperator 와 BinaryOperator

Function 인터페이스의 변형으로, **매개변수의 타입과 반환타입이 일치함**.

### UnaryOperater<T>

- T apply(T t)
- function 의 자손,
- 매개변수와 결과 타입이 같음. -> 체이닝 가능!?

### BinaryOperator<T>

- T apply(T t, T t)
- UnaryOperator와 동일하나, 매개변수가 2개
- 3개 이상은 직접 구현해야해



