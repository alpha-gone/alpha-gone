## SOLID
* Single Responsibility Principle (단일책임의 원칙)
* Open Closed Principle (개방폐쇄의 원칙)
* Liskov Substitution Principle (리스코브 치환의 원칙)
* Interface Segregation Principle (인터페이스 분리의 원칙)
* Dependency Inversion Principle (의존관계 역전의 원칙)

### Single Responsibility Principle
    모든 클래스는 하나의 책임만 가지며, 클래스는 그 책임을 완전히 캡슐화 해야 한다

### Open closed Principle
    소프트웨어의 개체는 확장에 대해 열려 있고, 변경에는 닫혀 있어야 한다.

### Liskov Substitution Principle
    자료형 S가 자료형 T의 하위형 이라면, 프로그램에서 자료형 T의 객체는 프로그램의 속성(정확성, 수행 업무 등)을 변경하지 않고 자료형 S의 객체로 교체 할 수 있다.

### Interface Segregation Principle
    클라이언트가 자신이 이용하지 않는 메서드에 의존하지 않아야 한다.
    큰 덩어리의 인터페이스들을 구체적이고 작은 단위 들로 분리시킴으로써 클라이언트들이 꼭 필요한 메서드들만 이요할 수 있게 한다.

###  Dependency Inversion Principle
    상위 모듈은 하위 모듈에 의존해서는 안된다. 상위 모듈과 하위 모듈 모두 추상화에 의존해야 한다.
    추상화는 세부 사항에 의존해서는 안된다. 세부사항이 추상화에 의존해야 한다.