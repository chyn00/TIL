# Annotation
 * JDK 5에서부터, @Override, @Deprecated, @SupressWarnings 이렇게 3가지 경우이다.
    * 컴파일러에게 정보를 알려줄 때
    * 컴파일할 때와 설치 시의 작업을 지정하거나
    * 실행할 때 별도의 처리가 필요할 때
 * 특히 @Override는 내가 Overriding을 했는데, 틀리면 컴파일러에게 알려달라고 할 때.

# Meta Annotation
 * @Target
    * ElementType.METHOD -> 메소드에서만 사용
 * @Retention(RetentionPolicy.RUNTIME)
    * 어노테이션 정보가 얼마나 오래 유지되는지, -> Runtime에서 사용가능
 * @Documented
    * JAVA Docs에 포함된다는 것
 * @Inherited
    * 모든 자식 클래스에서, 부모 클래스의 어노테이션을 사용 가능하다.
 * @Interface
    * 이 어노테이션은 어노테이션을 선언할 때 사용한다.
 * <B>어노테이션은 상속이 되지 않는다.</B>