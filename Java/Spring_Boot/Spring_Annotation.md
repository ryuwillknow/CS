# Annotation

@Documented ⇒ api문서에 저장한다. metadata에 저장하는 의미

@Target(ElementType.METHOD) ⇒ 메서드에만 적용가능하다.

@Rentation(RentationPolicy.RUNTIME) ⇒ 어노테이션이 유지되는 기간을 의미한다. 다음 세가지 옵션이 있다.

1. **`RetentionPolicy.SOURCE`**: 컴파일 전까지만 유지되며, 클래스 파일에 포함되지 않습니다.
2. **`RetentionPolicy.CLASS`**: 컴파일된 클래스 파일에는 포함되지만, 런타임 시에는 유지되지 않습니다.
3. **`RetentionPolicy.RUNTIME`**: 컴파일된 클래스 파일에 포함되고, 런타임 시에도 유지됩니다. 따라서 리플렉션을 통해 런타임 시에 어노테이션 정보를 확인할 수 있습니다.

public @interface Authority {

AuthorityType authorityType();

}

메서드 시그니처(Method Signature)란 메서드의 이름, 매개변수 리스트, 그리고 해당 메서드의 반환 타입을 의미합니다. int func( int a)  이거

getDeclaredAnnotation이라는 메서드로 가져올 수 있다. 

@RequiredArgsConstructor ⇒ 생성자 자동 주입
