# 배열

배열요소 접근시 음수 안된다. 0 부터시작. array.length로 길이 조회 가능하다. 배열 크기는 변경불가 옮겨야한다.

참조형 배열 기본형 배열 둘다 된다.

배열 선언 : int[] iArr   char[] cArr  boolean[] bArr  String[] strArr  Date[] dateArr

배열 생성과 초기화 :

```java
int[] iArr = new int[길이];
int[] iArr2 = new int[] {1, 2, 3, 4}; // 여기는 길이 안쓴다.
int[] iArr3 = {1, 2, 3, 4}; // 반드시 한 줄에 써야한다.

// 덮어쓰기 가능

int[] arr6;
```

기본값 false  0 0L 0.0f 0.0 null(참조형 변수)

배열의 for-each (초기화 : 배열) { }  뒤에서 읽기 하려면 for문 쓰자.

배열 그냥 프린트하기 **Arrays.toString(array)**

**Arrays.copyOf(배열, 새로운 배열크기)**

ArrayIndexOutOfBoundsException : 인덱스가 없다. 음수다.

int[][] iArr  = int[] iArr[] = inti iArr[][] = 2차원 배열
