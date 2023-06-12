# GC의 버전과 특징을 알아보자
 * GC는 자바에서 메모리를 관리하기 위한, 일종의 프로세스이다.
 * GC는 Mark & Sweep 알고리즘으로부터 시작된다.
 * JVM 구조, 시간과 단계에 따른 Major/Minor GC, GC 알고리즘 종류, GC를 튜닝하는 법으로 키워드를 나눠 공부
  * 메타인지를 위하여 키워드 정리, 분류별 정리, 시나리오 정리, 비유 정리 등을 사용
    * JDK 17의 GC?
     * 일단, CPU의 개수마다 GC의 Default가 바뀐다고 하는데 확인이 필요하다.
     * heap에는 * young, old, perm가 나뉘는데 이영역에 따라 GC의 알고리즘이 달라진다.
     * minor gc, major gc는 시간과 단계에 따른 분류일 뿐 알고리즘 자체를 의미하지는 않는다.
     * 하지만 Minor GC가 할당되는 영역은 Young, Major GC는 Old/ Young과 Old의 차이는 객체가 얼마나 오래 살아남았느냐이기 때문에,
       결국 Minor GC의 발생확률이 높다.(Young이 가득찬 경우)
     * stop the world는 major gc와 minor gc 둘다 발생하게 되며, 시간과 단계에 의함.
     * 알고리즘에 의하지 않음.
     * GC 알고리즘 종류와 버젼별 관계를 정리할 필요가 있어보임 