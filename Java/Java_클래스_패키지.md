# 클래스

메소드 오버로딩  같은 이름의 메소드를 여러개 만드는 것이다. 들어가는 타입과 갯수 등이 다르므로.  이거 리턴은 그대로여야한다.

생성자도 오버로딩이 가능하다. 생성자는 this 로 인스턴스 변수에 접근한다. this는 객체 자기 자신이다!! static은 못쓴다!!!는 건 static변수에서 못쓴다는 것이 아니라 설계도 영역, 생성자가 아닌 곳에서 못쓴다는 것이다. 단 this()이건 가능하다. 생성자 다시 사용하기 ㅋㅋㅋㅋㅋ

# 패키지

폴더 사용하듯 여러 클래스를 다룬다. 접근제어자를 패키지 단위로도 할 수 있다.

import 는 다른 패키지를 가져오는 것. 같은 패키지는 임포트하지 않아도 된다.

import는 패키지명 생략하겠다. 아니면 반드시 풀네임으로 해야한다.

pivate 같은 클래스 protected 같은 패키지 + 상속받은 클래스여야한다. 다른 클래스에서 실행되는 유일한 방법 public 모든 곳에서

이거 한 파일에 하나의 클래스??? 이거 중요? 이게 보통인데 여러개 가능은 하다.

logger 로그를 남기는 것이다.

static이 아닌 innerclass 선언법

```java
public class Child {
    public static void main(String[] args) {

        Child c = new Child();
        Child.Student p = c.new Student("james");
//        Student p = new Child new Student("james");
        System.out.println(p.name);
    }

    public class Student{
        String name;
        Student(String name) {
            this.name = name;
        }
    }
}
```

generate 로 getter setter 자동으로 만들어준다. private을  eclipse는 source, intelliJ 는 generate

사용이유는 조건을 걸 수 있다.
