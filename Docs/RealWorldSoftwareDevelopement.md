## KISS(Keep Is Short and Simple)
    응용프로그램 코드를 한 개의 클래스로 구현

## DRY(Don't Repeat Yourself)
    중복 배제

## 놀람 최소화 원칙(Principle of least surprise)
    어떤 메서드가 다른 메서드와 달리 예상치 못한 방법으로 동작한다면 코드를 이해하기 어려울 것이다. 따라서 누군가가 놀라지 않도록 일관성을 유지하는 범위에서 코드를 구현
    메서드가 수행하는 일을 바로 이해할 수 있도록 자체 문서화를 제공하는 메서드명을 사용한다
    코드의 다른 부분이 파라미터의 상태에 의존할 수 있으므로 파라미터의 상태를 바꾸지 않는다.

## SPR(단일 책임 원칙 | Single Responsibility Principle)
    한 클래스는 한 기능만 책임진다.  
    클래스가 바뀌어야 하는 이유는 오직 하나여야 한다.
    클래스와 메서드에 적용한다.

## 응집도(Cohesion)
    클래스나 메서드의 책임이 서로 얼마나 강하게 연결되어 있는 정도.  
    소프트웨어의 복잡성을 유추하는 데 도움을 줌

### 클래스 수준 응집도

|응집도 수준|장점|단점|
|:--:|:--:|:--:|
|기능(높은 응집도)|이해하기 쉬움|너무 단순한 클래스 생성|
|정보(중간 응집도)|유지보수하기 쉬움|불필요한 의존성|
|순차(중간 응집도)|관련 동작을 찾기 쉬움|SRP를 위배할 수 있음|
|논리(중간 응집도)|높은 수준의 카테고리화 제공|SRP를 위배할 수 있음|
|유틸리티(낮은 응집도)|간단히 추론 가능|클래스의 책임을 파악하기 어려움|
|시간(낮은 응집도)|판단 불가|각 동작을 이해하고 사용하기 어려움|

* 기능  
    기능이 비슷한 메서드를 그룹화
    함께 사용하는 메서드를 그룹화하면 찾기도 쉽고 이해하기도 쉬우므로 응집도를 높인다.  
    한 개의 메서드를 갖는 클래스를 너무 과도하게 만들려는 경향이 발생할 수 있다

* 정보  
    같은 데이터나 도메인 객체를 처리하는 메서드를 그룹화  
    여러 기능을 그룹화 하면서, 필요한 일부 기능을 포함하는 클래스를 전체 의존성으로 추가해야 한다.

* 유틸리티  
    관련성이 없는 메서드를 명확하지 않은 기준으로 그룹화  
    메서드가 서로 연관성이 없으므로 클래스 전체의 기능을 추론하기 어렵다.

* 논리  
    특정한 한 가지 논리 구현한 관련성이 없는 메서드들을 그룹화  
    SRP를 위배 할 수 있어서 권장하지 않음

* 순차  
    입출력이 순차적으로 흐르는 것을 순차 응집이라고 부르며, 순차 응집은 여러 동작이 어떻게 함께 수행되는지 쉽게 이해할 수 있으나, 한 클래스를 바꿔야 할 여러 이유가 존재 하므로 SRP를 위배한다.  
    따라서 각 책임을 개별적으로 응집된 클래스로 분리하는 것이 좋음

* 시간  
    여러 연산 중 시간과 관련되 연산을 그룹화  
    예) 어떤 처리 작업을 시작하기 전과 뒤에 초기화, 뒷정리 작업을 담당하는 메서드를 포함한 클래스

#### 메서드 수준응집도
    메서드가 다양한 기능을 수행할수록  메서드가 어떤 동작을 하는지 이해하기가 점점 어려워진다. 즉 메서드가 연관이 없는 여러 일을 처리한다면 응집도가 낮아진다.
    클래스나 메서드 파라미터의 여러 필드를 바꾸는 if/else/ 블록이 여러 개 포함되어 있다면, 응집도에 문제가 있음을 의미하므로 응집도가 더 높은 작은 메서드로 분리해야됨

## 결합도
    한 기능이 다른 클래스에 얼마나 의존하고 있는지를 가늠.  
    어떤 클래스를 구현하는 데 얼마나 많은 지식(다른 클래스)을 참조한 정도  
    더 많은 클래스를 참조했다면 기능을 변경할 때 그만큼 유연성이 떨어진다.
    어떤 클래스의 코드를 바꾸면 이 클래스에 읜존하는 모든 클래스가 영향을 받는다.
    코드가 어떻게 의존하는지와 관련이 있는 척도

## OCP(개방/폐쇄 원칙 | Open/Closed Principle)
    코드의 변경 없이 확장성은 개방되어야 한다.
    기존 코드를 바꾸지 않으므로 기존 코드의 재사용성이 높아진다.
    코드가 중복되지 않으므로 기존 코드의 재사용성이 높아진다.
    결합도가 낮아지므로 코드 유지보수성이 좋아진다.
     

## 안티패턴
### 과도하게 세밀함
    검증자 클래스를 구현하는 이유
    1. 검증 로직을 재사용해 코드를 중복하지 않는다.
    2. 시스템의 다른 부분도 같은 방법으로 검증할 수 있다.
    3. 로직을 독립적으로 유닛 테스트할 수 있다.
    4. 이 기법은 프로그램 유ㄴ지보수와 이해하기 쉬운 SRP를 따른다.

    각각의 예외에 적합하고 정확한 회복 기법을 구현할 수 있지만 너무 많은 설정 작업이 필요하며 여러 예외를 선언해야하고 모든 예외를 처리해야 하므로 생산성이 떨어진다.

### 과도하게 덤덤함
    모든 예외를 미확인 예외로 지정하는 상황
    전부 동일한 예외로 지정하면 구체적인 회복 로직을 만들 수 없는 문제가 생김
## Notification  

## 유비쿼터스 언어
    개발자와 사용자 모두가 사용할 수 있도록 설계, 공유된 공통 언어를 말한다.

## LSP(리스코프 치환 원칙 | Liskov Substitutuin Principle)
    q(x)는 T형식의 x객체를 증명할 수 있는 공식이다. 그러면 S형식의 객체 y가 있고 S가 T의 하위형식이라면 q(y)는 참이다.
    1. 하위형식에서 선행조건을 더할 수 없음
        부모가 지정한 것보다 더 많은 선행조건을 요구할 수 없음을 의미
    2. 하위형식에서 후행조건을 약화시킬 수 없음
        부모가 부작용을 포함하거나 어떤 값을 반환한다면 자식도 그래야함을 의미
    3. 슈퍼형식의 불변자는 하위형식에서 보존됨
        불변자는 항상 변하지 않는 어떤 것을 의미
        상속 관계의 부모와 자식 클래스가 있을때, 부모 클래스에서 유지되는 모든 불변자는 자식 클래스에서도 유지되어야 한다.
    4. 히스토리 규칙
        자식 클래스는 부모가 허용하지 않은 상태 변화를 허용하지 않아야 한다.

## ISP(인터페이스 분리 원칙 | Interface Segregation Principle)
    어떤 클래스도 사용하지 앟는 메서드에 의존성을 갖지 않아야 한다.

## 플루언트 API
    특정 문제를 더 직관적으로 해결할 수 있도록 특정 도메인에 맞춰진 API

## equals() / hashCode() 계약
    두 객체를 equals() 메서드로 같다고 판단했을 때 hashCode() 메서드 역시 같은 값을 반환해야 한다.

## DIP(의존관계 역전 원칙 | Dependency Inversion Principle)
    높은 수준의 모듈은 낮은 수준의 모듈에 의존하지 않아야 한다. 두 모듈 모두 추상화에 의존해야 한다.  
    추상화는 세부 사항에 의존하지 않아야 한다. 세부 사항은 추상화에 의존해야 한다.