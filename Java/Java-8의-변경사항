# JAVA 8에서의 변경사항
2014년도에 발표된 Java SE 8버전에서 변경되고 추가된 사항
1. 람다 표현식
	- **함수형 프로그래밍**을 위함.
	- 기존의 불필요한 코드를 줄이고, 가독성을 높일 수 있다.
2. 스트림 api
	- 매번 반복문이나 반복자를 사용하여 순차형 자료구조에 접근하는 방법 -> 길이가 너무 길고, 코드의 재사용이 어려움. 이를 보완하고자 스트림 api 도입
	- 데이터를 추상화하여 다루므로, 다양한 방식으로 저장된 데이터를 읽고 쓰기 위한 공통된 방법을 제공
	- 외부 반복을 통해 작업하는 컬렉션과는 달리 **내부 반복**을 통해 작업을 수행한다. 단 한 번만 사용할 수 있으며, 원본 데이터를 변경하지 않는다. parallelStream 메소드를 통해 손쉬운 **병렬처리**를 제공하기도 한다.
3. java.time 패키지
4. 나즈혼Nashhorn : 자바스크립트의 기본 스크립트 엔진으로, 모질라의 리노Rhino 대신 오라클의 나즈혼Nashorn을 도입함.

스트림의 예시
```java
// 배열에서 스트림 생성
Stream<String> stream1 = Arrays.stream(arr);
stream1.forEach(e -> System.out.print(e + “ “));

// 배열의 특정 부분만을 이용한 스트림 생성
Stream<String> stream2 = Arrays.stream(arr, 1, 3);
stream2.forEach(e -> System.out.print(e + “ “));
```
