# Nested Class
 * Static Nested Class
 * Inner Class
   * Local inner class
   * Anonymous inner class
 * Nested 클래스는 결합도가 높아지는 단점이 있다.
 * Nested Class는 하나의 클래스에서 공통적인 기능을 처리하기 위한 클래스가 필요한데, 다른 클래스에서는 전혀 필요하지 않을 때 사용한다.
   * 테스트 코드의 @BerforeAll같은 것을 생각해보면 알 수 있다.
   * Overriding할때 Comparator 같은거 익명 클래스로 사용하는 익명클래스도 있다.
   * Nested 클래스 특징
    * 언제나 그렇듯, static class는 static 변수만 사용이 가능하다.
    * 하지만 static은 반대로의 참조(즉, 내부에 있는 클래스는 가능하다.)
  * Nested Class는 가독성 증가, 감소 둘 다 가능함. 
