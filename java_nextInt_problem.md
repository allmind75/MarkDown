## [Java] nextInt( ) 사용 후 nextLine( ) 사용시 문제점 해결 방법

- **Scanner.nextInt** 메소드는 사용자 입력의 가장 마지막 **개행문자(엔터, newline)**를 제거하지 않음
개행문자(엔터) 전까지만 숫자로 입력 받음
개행문자(엔터)는 다음에 호출된 **Scanner.nextLine( )** 메소드의 입력으로 처리되서 문제 발생</br></br>


####**Scanner.nextInt( ) 문제 발생하는 경우**

```java
import java.util.Scanner;

public class ScannerNextIntProblem {

	public static void main(String[] args) {
		
		Scanner scan = new Scanner(System.in);
		
		int num;
		String str;
		
		System.out.print("num 입력> ");
		num = scan.nextInt();
        
		//문제발생 : 개행문자(엔터)가  str에 저장됨
		System.out.print("str 입력> ");
		str = scan.nextLine();
		
		System.out.println();
		System.out.println("num : " + num);
		System.out.println("str : " + str);
		scan.close();
	}
}

```
결과
num 입력> 50
str 입력> 
num : 50
str : 

---
####해결방법 1 : Scanner.nextLine() 추가

```java
import java.util.Scanner;

public class ScannerNextIntProblem {

	public static void main(String[] args) {
		
		Scanner scan = new Scanner(System.in);
		
		int num;
		String str;
		
		System.out.print("num 입력> ");
		num = scan.nextInt();
		scan.nextLine();	//개행문자(엔터)를 제거하기위해 추가
	
		System.out.print("str 입력> ");
		str = scan.nextLine();
		
		System.out.println();
		System.out.println("num : " + num);
		System.out.println("str : " + str);
		scan.close();
	}
}
```
###결과
num 입력> 50
str 입력> abc

num : 50
str : abc

---

####해결방법 2 : **Scanner.nextLine( )**으로 입력받고 **Integer.parseInt( )**로 변환

```java
import java.util.Scanner;

public class ScannerNextIntProblem {

	public static void main(String[] args) {
		
		Scanner scan = new Scanner(System.in);
		
		int num = 0;
		String str;
		
		System.out.print("num 입력> ");
//		num = scan.nextInt();
//		scan.nextLine();
		try {
			num = Integer.parseInt(scan.nextLine());
		} catch(NumberFormatException e) {
			e.printStackTrace();
		}
		
		System.out.print("str 입력> ");
		str = scan.nextLine();
		
		System.out.println();
		System.out.println("num : " + num);
		System.out.println("str : " + str);
		scan.close();
	}
}

```
###결과
num 입력> 50
str 입력> abc

num : 50
str : abc


