## Stream이란?

장점

- 자바8부터 추가된 스펙으로, **배열 또는 컬렉션 인스턴스에** 함수를 조합해 원하는 결과를 필터링 하고, 가공하는 결과를 얻을 수 있음.
- 병렬처리(Miulti-threading)가 간단해짐 (이건 나중에 해보자)

스트림 사용하기 위한 주요 단계

1. 생성하기 : 스트림 인스턴스 생성
2. 가공하기 : 필터링 및 매핑등으로 원하는 결과 만들기
3. 결과 만들기: 원하는 결과 도달하기



### 1. 생성하기

- 배열스트림 : `Arrays.stream()`사용

  ```java
  String[] arr = new String[]{"a","b","c"};
  Stream<String> stream = Arrays.stream(arr);
  Stream<String> streamOfArrayPart = Arrays.stream(arr,1,3);	//[b,c]
  ```

  - 컬렉션 스트림 : Collection, List, Set은 인터페이스에 추가된 디폴트stream을 사용한다.

  ```java
  List<String> list = Arrays.asList("a","b","c");
  Stream<String> stream = list.stream();
  Stream<String> parallelStream = list.parallelStream();	//병렬 스트림, 스트림 로직 내의 순서 없이 실행한다.
  ```

  - 비어있는 스트림 : 나중에 정리!  null대신 사용가능

**Stream.builder() **: 스트림에 원하는 값을 넣을 수 있음.





### 2. 가공하기

요소(배열 또는 컬렉션 등)에서 원하는 것을 뽑아낼 때 사용함.

스트림을 리턴하기 때문에 체이닝 기법으로 여럿 사용할 수 있다.



**Filtering** 

- 스트림내 요소를 하나씩 평가해 걸러냄

- 인자로 Predicate 를 받음( boolean 을 리턴함.)

  ```java
  Int[] arr = new int[]{1,2,3,4,5};
  //3이상인 값들만 출력
  Arrays.stream(numbers).filter(i->i>=3).forEach(i -> System.out.println(i));
  ```

**Mapping**

- 스트림 내 요소들을 하나씩 특정 값으로 변환해준다.
- 변환을 위해 람다를 인자로 받음.(input -> stream -> output(인자))

