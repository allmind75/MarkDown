##[Java] HashMap에서 value 값으로 key값 찾기
- **HashMap**에서 **value** 값을 이용해서 **key** 값을 찾아보자
출처 : [http://www.java2s.com/Code/Java/Collections-Data-Structure/GetakeyfromvaluewithanHashMap.htm](http://www.java2s.com/Code/Java/Collections-Data-Structure/GetakeyfromvaluewithanHashMap.htm)

```java
import java.util.HashMap;
/*
 * http://www.java2s.com/Code/Java/Collections-Data-Structure/GetakeyfromvaluewithanHashMap.htm
 */
public class MapGetKeyFromeValue {

	public static void main(String[] args) {

		HashMap<Integer, String> map = new HashMap<Integer, String>();
		
		map.put(1, "피카츄");
		map.put(2, "라이츄");
		map.put(3, "파이리");
		
		System.out.println("map.get(1) : " + map.get(1));
		System.out.println("map.get(2) : " + map.get(2));
		System.out.println("map.get(3) : " + map.get(3));
		System.out.println();
		
		//key값을 object 타입으로 반환
		System.out.println("getKeyFromValue(map, \"피카츄\") : " + getKey(map, "피카츄")); 
		System.out.println("getKeyFromValue(map, \"라이츄\") : " + getKey(map, "라이츄")); 
		System.out.println("getKeyFromValue(map, \"파이리\") : " + getKey(map, "파이리")); 
		System.out.println();

		//int형으로 변환 후 value 값 출력
		System.out.println(map.get( (int) getKey(map, "피카츄") ) ); 	
		System.out.println(map.get( (int) getKey(map, "라이츄") ) ); 	
		System.out.println(map.get( (int) getKey(map, "파이리") ) ); 	
	}

	public static Object getKey(HashMap<Integer, String> m, Object value) {
		
		for(Object o: m.keySet()) {
			
			if(m.get(o).equals(value)) {
				return o;
			}
		}
		return null;
	}
}

```

###결과
map.get(1) : 피카츄
map.get(2) : 라이츄
map.get(3) : 파이리

getKeyFromValue(map, "피카츄") : 1
getKeyFromValue(map, "라이츄") : 2
getKeyFromValue(map, "파이리") : 3

피카츄
라이츄
파이리
