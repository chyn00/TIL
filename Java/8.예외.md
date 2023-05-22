# 예외
 * 예외란 무엇인가?
  * 사용자가 정의해두었던, 정상적인 흐름 외의 동작을 예외라고 한다.
 * 예외를 사용하는 방법
  * JAVA에서 다루는 예외 -> Spring에서 다루는 예외 등 예외를 처리하는 다양한 방법에 대해 알아보자
  * JAVA에서의 예외
   * 오라클 공식 문서에서 말하는 예외 https://docs.oracle.com/javase/tutorial/essential/exceptions/index.html
   * Object -> Throwable -> Exception & Error
    * 여기서 주의할점이 Exception아래에 있지만, Unchecked Exception은 또 다시 Error를 묶을 수 있다.(Error & Runtime Exception(Null pointer Exception))
     * Unchecked인 Error는 핸들링이 불가하면, Uncheked Exception인 Runtime Exception은 어떻게든 핸들링이 되긴 한다.(하지만 에러처럼 근본적 원인을 처리하는 것이 더 유리하다.)
      (출처 : 자바 튜토리얼(oracle))
   * 예외 문법
    * Try, catch, Finally
     * Try - catch는 짝이다.
     * finally는 반드시 실행해야하는 경우에 사용한다.
     * Try는 블럭단위 구조이기 때문에, 지역변수가 내부에서만 관리된다.(Catch로 전달안됨)
   * 예외 핸들링 방법 In JAVA -> 추후에 스프링에서 다루는 예외 처리까지 볼 수 있다는 생각을 가지자.
     * <B>예외를 던지기(예외 연결 - 정의된 예외로 연결 Chaning, 예외 클래스 만들기 - 자신이 만든 예외를 래핑, 특정 예외 던지기)</B>
     * 예외를 Try catch(1 ~ 다수)로 처리하기
   * 클라이언트가 던지는 것으로 Runtime이 잘못 실행될 수 있다면, uncheck Exception이 적절하다.
