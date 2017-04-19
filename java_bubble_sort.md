##Bubble Sort

>거품 정렬(Bubble sort)은 두 인접한 원소를 검사하여 정렬하는 방법이다. 시간 복잡도가 O(n<sup>2</sup>)로 상당히 느리지만, 코드가 단순하기 때문에 자주 사용된다. 원소의 이동이 거품이 수면으로 올라오는 듯한 모습을 보이기 때문에 지어진 이름이다.
> [위키백과-거품정렬](https://ko.wikipedia.org/wiki/%EA%B1%B0%ED%92%88_%EC%A0%95%EB%A0%AC)



```java
import java.util.Scanner;

public class BubbleSort {

	public static void main(String[] args) {
		// TODO Auto-generated method stub
		
		Scanner sc = new Scanner(System.in);
		int N;
		int[] array;
		
		N = sc.nextInt();
		array = new int[N];
		
		for(int i=0 ; i<N ; i++) {
			array[i] = sc.nextInt();
		}
				
		for(int i=N-1 ; i>0 ; i--) {
			System.out.print("\n Bubble Sort " + (N-i) + "단계");
			for(int j=0 ; j<i ; j++) {
				if(array[j] > array[j+1]) {
					int temp = array[j];
					array[j] = array[j+1];
					array[j+1] = temp;
				}
				System.out.printf("\n\t");
				for(int n: array) {
					System.out.printf("%3d ", n);
				}
			}
			System.out.println();			
		}
		
		System.out.print("\nBubble Sort Result : ");
		for(int i=0 ; i<N ; i++) {
			System.out.print(array[i] + " ");
		}
		System.out.println();
		sc.close();
	}

}
```
---
###결과

 Bubble Sort 1단계
	-10   5  33   0  29 
	-10   5  33   0  29 
	-10   5   0  33  29 
	-10   5   0  29  33 

 Bubble Sort 2단계
	-10   5   0  29  33 
	-10   0   5  29  33 
	-10   0   5  29  33 

 Bubble Sort 3단계
	-10   0   5  29  33 
	-10   0   5  29  33 

 Bubble Sort 4단계
	-10   0   5  29  33 

Bubble Sort Result : -10 0 5 29 33 
