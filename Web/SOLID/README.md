# SOLID 원칙
이렇게 만들면 유지보수와 확장이 쉬우니까 최대한 SOLID하게 만들기로 약속~

1. SRP 단일책임
2. OCP 개방폐쇄
3. LSP 리스코프치환
4. ISP 인터페이스 분리
5. DIP 의존역전

### SRP 단일책임
Single Responsibility Principle
책임이 하나. 하나의 컴포넌트가 디비에도 다녀오고 파싱도 하고 비즈니스 로직 처리도 해주면 결합도가 높아져서 레고처럼 뺐다 꼈다 하기가 어려워지니까. 

### OCP 개방폐쇄
Open-Closed Principle
열린 교회 닫힘.. 기존의 코드는 변경하지 않고, 기능을 수정하거나 추가할 수 있어야 한다. 인터페이스만 받아오고 구현체만 바꿔끼는 걸 의미하는 것 같다.

### LSP 리스코프 치환
리스코프 씨가 제안했다고 한다. 부모 클래스와 자식 클래스 사이의 행위에는 일관성이 있어야 한다. 부모 클래스의 인스턴스 대신 자식 클래스의 인스턴스를 사용해도 문제가 없어야 한다. 그러니까.. 부모가 불가능한 행위를 자식이 하면 안된다. 

### DIP 의존역전
Dependency Inversion Principle
변화하기 어려운 놈에게 의존해야 한다. 그러니까.. 언제든 바뀔 수 있는 구현체 대신에 바뀔 일 없는 인터페이스를 의존하고, 구현체는 어디에선가 따로 받아와야 한다. 이 일을 스프링 컨테이너가 싱글톤으로 구현체를 만들어 갖고있다가 요청할 때 넣어주는 방식으로 잘 동작시켜준다.
 
### ISP 인터페이스 분리
Interface Segregation Principle
자신이 사용하지 않는 인터페이스는 구현하지 말아야 한다. 
