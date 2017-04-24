## String 비교하기( ==와 equals의 차이 )
- **==** 사용 : 객체의 주소값 비교
- **.equals()** 사용 : 객체의 값을 비교

```java

public class StringCompare {

	public static void main(String[] args) {
		// TODO Auto-generated method stub

		String a = "aa";
		String b = "aa";
		
		String c = new String("aa");
		
		System.out.println("a의 hashCode: " + "@" + Integer.toHexString(System.identityHashCode(a)));
		System.out.println("b의 hashCode: " + "@" + Integer.toHexString(System.identityHashCode(b)));
		System.out.println("c의 hashCode: " + "@" + Integer.toHexString(System.identityHashCode(c)));
		
		System.out.println();
		
		if(a == b) {
			System.out.println("a == b -> a와 b의 주소값이 같음");
		} 
		
		if(a == c) {
			System.out.println("a == c -> a와 c의 주소값이 같음");
		} else {
			System.out.println("a == c -> a와 c의 주소값이 다름");
		}
		System.out.println();
		if(a.equals(b)) {
			System.out.println("a.equals(b) -> a와 b의 문자열이 같음");
		}
		
		if(a.equals(c)) {
			System.out.println("a.equals(c) -> a와 c의 문자열이 같음");
		}
	}
}

```

###결과
a의 hashCode : @7852e922
b의 hashCode : @7852e922
c의 hashCode : @4e25154f

a == b -> a와 b의 주소값이 같음
a == c -> a와 c의 주소값이 다름

a.equals(b) -> a와 b의 문자열이 같음
a.equals(c) -> a와 c의 문자열이 같음

##결론
String 값을 비교할때는 **==** 사용 시 정확하게 비교를 못한다.
따라서 **.equals()**를 이용해서 비교한다.