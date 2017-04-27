##Java 프로그램 수행시간 확인
- **System.nanoTime( )**을 이용해서 원하는 부분의 수행시간을 구할 수 있다.
- **System.nanoTime( )**의 반환값은 나노초

```java
public class TimeCalc {

	public static void main(String[] args) {
		// TODO Auto-generated method stub

		/*
		 * 1ns * 1000000 = 1ms
		 * 1ms * 1000 = 1s
		 * 1ns * 1000000000 = 1s
		 */
         
		long start = System.nanoTime();
		double sum = 0;
				
		for(int i=0 ; i<2100000000 ; i++) {
			sum += i;
		}
		
		long end = System.nanoTime();
		double time = (end - start) / 1000000000.0;		//나노초를 초로 변환시

		System.out.println(time + "초");
	}

}
```


###결과
2.227739595초

(결과 시간은 컴퓨터 사양마다 다르게 나옴)