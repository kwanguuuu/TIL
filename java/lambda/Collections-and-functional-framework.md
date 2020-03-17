### 컬렌션 프레임웍과 함수형 인터페이스

컬렉션 프레임웍에 추가된 default functional interface 정리

| 인터페이스   | 메서드                                        | 설명                             |
| ------------ | --------------------------------------------- | -------------------------------- |
| `Collection` | `boolean` removeIf(Predicate<E> fileter)      | 조건에 맞는 모든 요소를 삭제     |
| `List`       | void replaceAll(UnaryOperator<E> operator)    | 모든 요소를 변환하여 대체        |
| `Iterable`   | void forEach(Consumer<T> action)              | 모든 요소에 작업 action 수행     |
| `Map`        | V compute(K key, BiFuntion<K,V,V> f)          | 지정된 키의 값에 작업 f 수행     |
|              | V computeIfAbsent(K key, Function<K,V> f)     | 키가 없으면, 작업 f 수행 후 추가 |
|              | V computeIfPresent(K key, BiFuntion<K,V,V> f) | 지정된 키가 있을 때, 작업 f 수행 |
|              | V merge(K key, V value, BiFunction<V,V,V> f)  | 모든 요소에 병합작업  f 를 수행  |
|              | void forEach(BiConsumer<K,V> action)          | 모든 요소에 작업 action 수행     |
|              | void replaceAll(BiFunction<K,V,V> f)          | 모든 요소에 치환작업 f 를 수행   |



