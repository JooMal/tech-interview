### JVM

일단 자바 이전에는 모든 운영체제에 맞추어 다르게 컴파일이 되어야 했었다. 임베디드 가전이 생겨나던 시절에 OS가 다르다보니 OS에 맞춰서 코드도 달라지고 그랬겠지? 이게 너무 불편하니까 OS에 구애받지 않고 코드가 도는 자바 라는 언어를 만들게 된 거임. OS에 구애받지 않도록 중간에서 컴파일을 해주는 게 JVM이구요.

-> OS에 맞춰서 구구절절 바꾸기 싫어서 만든게 자바



### 그럼 JVM은 어떻게 동작할까?

JVM은 하나의 작은 가상 OS라고 생각하면 된다. 자바 컴파일러가 자바 소스코드를 읽어들인 후 자바 바이트코드(.class)로 변환하고, class파일들은 jvm의 class loader를 통해 로딩된다. 로딩된 클래스 파일들은 다시 내부 엔진을 통해 해석된 후 Runtime Data Areas에 배치되어 실행되게 됨.

![image-20210601011758142](../../../JooMal.github.io/assets/img/image-20210601011758142.png)

긍까... 음 일단 우리의 메모리 상에는 가령 CODE.java 라는 자바 언어로 작성된 코드가 존재하는 거임. 그러면 그걸 어떤 IDE를 통해서 실행시키는 순간, 

JAVA 컴파일러가 실행되면서 .java 파일을 .class 파일로 변환하고,

.class 파일을 이제 JVM에서 실행을 하는데,

- Class Loader라는 JVM 내부의 어떤 로더가 클래스 파일들을 엮어서 Runtime Data Area에 로딩한다.

- Execution Engine은 이제 실행을 진짜로 시켜 주는 엔진이고, 얘는 메모리에 적재된 클래스들을 기계어로 변경해 명령어 단위로 실행해준다.

  JVM 내부에서 Execution Engine이 기계어로 변환할 때 사용하는 두 가지 방식

  1. 인터프리터 : 바이트 코드 명령어를 하나씩 읽어서 해석하고 실행한다. 하나하나의 해석은 빠르지만 실행이 느리다.

  2. JIT(Just-In-Time) 컴파일러 : 인터프리터 방식으로 실행하다가 적절한 시점에 바이트 코드 전체를 컴파일하여 네이티브 코드로 변환시킨다.

- 짱 중요한 GC가 있음. 동적 메모리 영역인 Heap에 생성된 객체들 중에 Reachablity를 잃은 객체를 탐색 후 제거하는 역할을 해준다. 얘는 엄청 중요해서 따로 폴더를 파서 작성하겠음.



### Java Heap

모든 스레드에서 공유되기 때문에 동기화 문제가 수반되고, GC가 메모리 해제를 해주므로 자바 개발자들은 GC를 신경써야하는 듯.



### HotSpot JVM

일반적인 JVM 중 하나. Hot한 Spot을 찾아내서 JIT(Just-In-Time) 컴파일러를 사용하는 방법! 네이티브 코드를 생성할 때에 두 가지 방법이 있다고 한다.

1. 클라이언트 모드 : 프로그램 시작 시간 최소화하려고 사용.
2. 서버 모드 : 전체적인 성능 최적화를 신경쓰는 모드. 컴파일러 최적화 기술들을 이용해 코드를 최적화한다. 정확히는 모르겠지만 중복되고 불필요한 기계어들을 정리해주거나 하는 듯 하다.