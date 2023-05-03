# GC란?
  * Heap 영역에 할당된 메모리를 자동으로 수거하는 기능.
# JVM의 구조
  * Heap
    * Shared Memory이다. Class instance, Array 등이 여기에 속한다.
  * None Heap
    * Method영역 : 런타임 상수 풀, 메서드 데이터, 메서드와 생성자 코드
    * JVM 스택 : 스레드 관련된 지역 변수, 메서드 수행과 리턴 정보
    * 네이티브 메서드 스택 : -
    * PC 레지스터 : JVM의 인스트럭션 주소를 PC 레지스터에 저장
# GC는 JVM의 Heap과 관련이 있다.
  * Heap영역
    * New/Young : Minor GC
    * Old : Full GC
# Minor, Full 외의 다양한 GC 알고리즘
  * Parallel GC, Concurrent GC 등
# 실무에서 GC에 대한 이해가 왜 필요한가?
  * GC 튜닝, 에러 원인 분석 등을 할 수 있다.
  * GC를 이해한 상태로 개발하면, 메모리까지 신경쓰면서 코드를 작성할 수 있다.
# 결론
  * GC를 바로 알면, 비용을 절약하는 개발자가된다.(코드를 작성할 때, 유지보수를 할 때 모두)
# TODO
  * JDK Version 별 GC의 특징을 알아보자.(특히, 17)
  * None Heap에서의 Out of Memory는 어떻게 해결할까?
    * A. GC는 결국 메모리랑 관련이 있다. GC의 상위 개념은 메모리 인데, None-heap도 메모리에 포함 되는 영역이기 때문에, 메모리를 모니터링 할 수 있는 기능을 찾아야한다.
    * Spring actuator는 heap dump 뿐만아니라, 메모리 자체에 대한 사용량을 확인 할 수 있다.