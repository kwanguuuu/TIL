객체지향 5대원칙의 앞글자로 만든 것

SRP, OCP, LSP, DIP, ISP

1. 단일책임원칙(Single Responsibility Principle)

객체는 단 하나의 책임만 가져야 한다는 원칙

**응집도는 높게, 결합도는 낮게 설계해라**



2. 개방폐쇄원칙(Open Closed Principle)

기존 코드를 변경시키지 않으면서(closed), 기능을 추가할 수 있도록(open)

**확장에 대해선 열려있고, 수정에 대해선 폐쇄적이야함.** 캡슐화 



3. 
4. 리스코프 치환 원칙(Liskov Substitution Principle)

자식클래스는 부모의 클래스에서가능한 행위는 수행할 수 있어야함.

**자식클래스는 부모클래스의 역할을 대신할 수 있어야 함.**

자식 클래스가 부모클래스의 책임을 무시하거나 재정의하지 않고 확장만 한다



4. 인터페이스 분리 원칙(Interface Segregation Principle)

사용하지 않는 인터페이스는 구현하지 말아야 한다.

하나의 큰 인터페이스 보다 여러개의 작은 인터페이스를 작성



5. 의존성 역전 원칙(Dependency Inversion Principle)

상위 클래스(높은 추상성)가 하위 클래스(낮은 추상성)에 의존해서는 안된다.