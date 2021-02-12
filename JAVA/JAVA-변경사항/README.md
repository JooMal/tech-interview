# JAVA 변경사항

### JAVA 8
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

### JAVA 10
1. 지역변수 자료형 추론 기능
	- var 타입을 사용하여 자료형을 명시하지 않고 변수를 사용할 수 있게 되었다. lombok의 var 기능이 공식으로 들어왔다.
2. 가비지 콜렉터 인터페이스 추가 : 서로 다른 가비지 콜렉터들의 코드를 분리시킬 수 있게 되었습니다.
3. Application Class-Data Sharing : 기존의 Class-Data Sharing 기능을 확장하여 애플리케이션 클래스를 공유 아카이브에 배치하고, 서로 다른 자바 프로세스들이 공유할 수 있도록 개선.

### JAVA 11
1. Nest-based Access Controls : 물리적으로 다른 자바 파일로 떨어진 클래스를 논리적으로 같은 클래스로 묶어주는 기술
2. New Garbage Collector : 새로운 가비지 콜렉터 방식 도입

### JAVA 11
1. 화살표(->) 사용 가능 : switch 문의 작서법의 변화. 콜론과 break 문의 조합이 아니라, 람다식과 비슷한 화살표로 구분이 가능해졌다. 뿐만 아니라 리턴 값을 받을 수도 있다.
```java
int numLetters = switch(day) {
	case MON, FRI, SUN -> 6;
	case TUE -> 7;
	case THU, SAT -> 8;
	case WED -> 9;
}
```

### JAVA 13
- Text Blocks : 2차원 텍스트 블럭. 3개의 쌍따옴표를 이용하여 문자열 작성이 가능해졌다.
- Switch 문법 : break를 통한 반환이 없어지고, 그 대안으로 yield가 사용됨.
- Scoket API : 디버깅 및 유지관리가 편하도록 새롭게 디자인 됨.

### JAVA 14
- instance of : 연산자의 패턴 매칭을 통해 간결한 코드 설명을 가능하게 한다.
- Switch Expression 정식 추가
- NullPointerExceptions 에러 메세지가 구체적으로 출력되도록 변경

