# OCP
  * Open Closed 원칙
  * 변경에는 닫혀있고, 확장에는 열려있는 원칙
  * 사용부 / 구성부를 나누어, 사용부의 변경이 전혀없이. 
  * 새로운 정책이 추가 된다면, 사용부 코드의 변경없이 코드가 교체되어 정상작동(사용영역에 대한 변경은 닫혀있음.)


# DIP
  * 의존 관계 역전 원칙
  * 추상화에 의존해야지, 구체화에 의존하면 안된다.(의존성 주입은 이 원칙을 따르는 방법 중 하나이다.)
  * 구현체에 전혀 의존하지 않고, 구성부(Appconfig, DI container)의 변경만으로, 호출부(사용부)의 정책이 변경되도록 하는것.
  * 사용부는 전혀 코드변경없이, 정책변경이 가능함.

# SRP
  * 같은 method더라도, 사용 actor나, 이해관계자에 따라, 각각의 method가 구현되는 것이 맞음.
  * 클래스, 메서드 단위에서의 원칙
  * 하나가 여러책임을 두고 있는 것 자체가 좋지 않음.
  * 책임을 명확히 하는 것이 좋음
  * 관심사를 분리

# ISP
  * 인터페이스 분리원칙
  * 클라이언트를 사용하지도 않는 메서드에 의존하지 않도록, 인터페이스를 더 세분화해서 나누어야한다.(위키)
  * 사용자(호출부)의 관점에서 필요한 인터페이스만 분리하여 만들어 놓는것

# LSP
  * 리스코프 치환 원칙
  * 상위 타입, 하위타입이 있다면, 속성(정확성, 수행업무)에 관계없이, 서브타입으로 치환이 가능하여야함.
  * 다른 서브타입을 객체로 치환하도록 허용한다면 LSP 위반이다. 따라서, 리스코프 치환 원칙에 맞게 설계를 해야. 다형성을 사용할 때 편하고, 유지보수가 편해진다.


# IOC
  * 제어의 역전
  * 구현객체가 스스로 필요한 서버 객체 흐름, 등을 직접 호출하고 사용하지만, 컨테이너가 이런 구현, 할당 등을 처리함.