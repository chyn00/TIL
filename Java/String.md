# String 이란?
 * 문자열을 다루는 클래스로, 불변 객체라는 것이 특징이다.
 * 성능 테스트를 하면, Top 5에 항상 있을 정도로, 많이 사용되는 객체이다.
 
# String +에 대한 고민
  * String +와 StringBuilder는 JAVA 5에서 성능이 거의 동일하도록 개선되기 하였으나 완벽하지 못하였다.
  * JAVA 9 이상 부터는 makeConcatWithConstants라는 방법을 활용하여, 거의 동일한 성능으로 String최적화를 사용한다.
    * 따라서 JAVA 9 이상부터는 사실 +를 사용하나, StringBuilder를 사용하나 큰차이가 없다 한다.(하지만 정확한 원리 파악이 필요하다. 완전 동일한 것은 아니기 때문이다.)
    * 이것을 알려고 하다보니, 자연스럽게 바이트 코드에 대해 공부하게 되었고, 바이트 코드만으로는 성능측정이 완벽하지 않다는 것도 알게 되었다.
    * 코드가 컴파일 되는 과정에 대해서도 중요하게 보인다.
  * 결론 : String + 는 가독성에 이점. StringBuilder는 성능에 이점. 하지만 현재 큰 차이는 없다.
    * 내가 직접 확인한 차이는 String +는 컴파일 단계에서 String 최적화(makeConcatWithConstants)를 사용한다는 것 뿐이다.
    * 어쨋든 컴파일 시점에 최적화가 적용이 되는건데, 이것을 사용할지 말지는 Trade-off 관계를 확인해봐야할 것 같다.(그리고 그 최적화가 과연 StringBuilder를 명시적으로 쓰는 것보다 좋을까?에 대한 <U><B>대답은 런타임 성능측정에 있다.</B></U>)
