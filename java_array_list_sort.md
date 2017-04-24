##ArrayList 정렬
- ArrayList를 오름차순 또는 내리차순 정렬하는 방법
- Collections.sort() 사용(오름차순 정렬)
- 내림차순으로 정렬할 떄는 Comparator<> 인터페이스 구현해서 추가

```java
import java.util.ArrayList;
import java.util.Collections;
import java.util.Comparator;

public class ArrayListSort {

	public static void main(String[] args) {
		// TODO Auto-generated method stub

		ArrayList<Integer> integerList = new ArrayList<Integer>();
		ArrayList<String> stringList = new ArrayList<String>();

		// 입력
		for (int i = 9; i >= 0; i--) {
			integerList.add(i);
		}

		stringList.add("ZZZ");
		stringList.add("YYY");
		stringList.add("XXX");
		stringList.add("WWW");
		stringList.add("VVV");

		// 출력
		System.out.println("<정렬전>");
		print1(integerList);
		print2(stringList);
		System.out.println();

		// 오름차순 정렬
		Collections.sort(integerList);
		Collections.sort(stringList);

		// 출력
		System.out.println("\n<오름차순>");
		print1(integerList);
		print2(stringList);

		// 내림차순 정렬
		Collections.sort(integerList, new AscendingInteger());
		Collections.sort(stringList, new AscendingString());
		
		// 출력
		System.out.println("\n<내림차순>");
		print1(integerList);
		print2(stringList);

	}

	public static void print1(ArrayList<Integer> list) {

		for (int i = 0; i < list.size(); i++) {
			System.out.print(list.get(i) + " ");
		}
		System.out.println();
	}

	public static void print2(ArrayList<String> list) {

		for (int i = 0; i < list.size(); i++) {
			System.out.print(list.get(i) + " ");
		}
		System.out.println();
	}
}

class AscendingInteger implements Comparator<Integer> {

	@Override
	public int compare(Integer a, Integer b) {
		
		return b.compareTo(a);
	}
}

class AscendingString implements Comparator<String> {

	@Override
	public int compare(String a, String b) {
		
		return b.compareTo(a);
	}
}
```

###결과
<정렬전>
9 8 7 6 5 4 3 2 1 0 
ZZZ YYY XXX WWW VVV 


<오름차순>
0 1 2 3 4 5 6 7 8 9 
VVV WWW XXX YYY ZZZ 

<내림차순>
9 8 7 6 5 4 3 2 1 0 
ZZZ YYY XXX WWW VVV