##Rank Algorithm(순위 알고리즘)
- 지정한 범위에서 순위를 구하는 알고리즘
- 1등, 2등, 3등 . . .
- 순위 배열을 1로 초기화 후
- 반복문을 돌면서 나보다 큰 수가 나오면 1증가

```java

public class RankAlg {

	public static void main(String[] args) {
		
		int[] grade = new int[]{47, 98, 56, 33, 85};	//성적
		int[] rank = new int[]{1, 1, 1, 1, 1};			//등수
		
		
		//rank 구하기
		for(int i=0 ; i<rank.length ; i++) {
			
			for(int j=0 ; j<grade.length ; j++) {
				
				if(grade[i] < grade[j]) {
					rank[i]++;
				}
				
			}
		}
		
		//출력
		System.out.println("1. 출력");
		for(int i=0 ; i<grade.length ; i++) {
			System.out.println(rank[i] + "\t" + grade[i]);
		}
		System.out.println();
		
		//1등부터 출력하기
		System.out.println("2. 출력");
		
		int[] index = new int[rank.length];	//rank의 각 index를 저장하는 배열
		
		for(int i=0 ; i<rank.length ; i++) {
			index[rank[i] - 1] = i;
		}
		
		//출력
		for(int i=0 ; i<rank.length ; i++) {
			int t = index[i];
			System.out.println(rank[t] + "\t" + grade[t]);
		}
	}
}
```
---
###결과
1. 출력
4등	47
1등	98
3등	56
5등	33
2등	85

2. 출력
1등	98
2등	85
3등	56
4등	47
5등	33

