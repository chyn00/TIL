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


실무관점에서, 에러메세지를 내려달라는 니즈가 있었다.
Exception 처리는 예측된 상황을 처리하는 것이기 떄문에, Exception 자체에 Message를 모두 내려 줄 필요는 없다.
개발자가 결함을 확인하기위해서는, 오히려 응답 메세지보다 로그로 보는 것으로 해결해야한다.
한마디로, 로그를 보는 것과 Exception의 메세지로 확인하는 것은 다른거다.
그리고 예외 처리 에러코드는 DIP관점에서, Errorcode Enum으로 관리하는게 더 객체지향 적이어서 편하다.(이 중에도 무엇이 맞다 말고 Trade-off가 있을까?)
그리고 보안때문에, Exception message를 리턴 하지 않는다고 한다. - 타프로젝트 경험 경력자
