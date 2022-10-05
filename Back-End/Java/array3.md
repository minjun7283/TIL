# 자바
```java
public class VarArgsDemo {

	public static void main(String[] args) {
		printsum(1,2,3,4,5);
		printsum(10,20,30);
		System.out.println(String.join(",","one","two","three"));
	}

	private static void printsum(int... v) {
		int sum=0;
		for(int i:v) {
			sum+=i;
		}
		System.out.println(sum);
		
	}

}
```