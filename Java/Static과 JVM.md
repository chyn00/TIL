# Static과 JVM

# Static
 * JVM의 Method Area로 static 선언이 되어있는 클래스, method는 static영역에 할당된다.(이 자원들은 공유된다.)
 * 자바 프로그램이 종료할 때, 할당된 영역이 해제된다.
 * Method단위도 결국 static에 있다는 것은 멀티 쓰레드의 동시성 이슈에서 자유로울 수 없다.(final 변수를 제외하고.)
 * **의문? 그럼에도 불구하고, 유틸성 클래스에 Static을 활용하는 것을 많이 보는데 왜 그런건지?**
   * 심지어, 불변 객체이며, 자바의 default객체인 String의 static에도 indexof와 같은 함수가 static으로 선언되어져있는데, 동시성 이슈가 문제가 없는지.
   * 생각보다, Thread safe하지 않아 보이는데, 이런 동시성에서 쓰레드 관리가 어떻게 되는지.
   * Answer. Static Method 영역(JVM static Area에 할당)에 있는 non-static paramter, 지역변수는 (Thread Stack Area)에 할당되어, Thread safe함. - 출처 : https://kotlinworld.com/3 - **더 찾아보기**
  * 근데 왜 그럼에도 불구하고 쿠폰 이슈같은 것들이 발생하는지?
  -> 동시성 이슈라는 것은 Static이냐 아니냐, 메모리의 공유에서만 발생하는 것이 아니다. DB에 동시에 접근할 때, 시퀀스처리가 되어있지 않아, 동시에 접근한 경우 -1이 순차적으로 일어나지않고, -2가되어야 하는데, -1만 되는 현상이 존재할 수 있다.
# JVM
 * 구조 이미지 첨부.(예정)