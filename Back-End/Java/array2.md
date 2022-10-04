# 자바
```java
public class Test01 {

	public static void main(String[] args) {
		int numofStudent = 0;
		int[] scores;
		Scanner sc = new Scanner(System.in);
		numofStudent = sc.nextInt();
		scores = new int[numofStudent];
		for(int i=0;i<numofStudent;i++) {
			scores[i] = sc.nextInt();
		}
		for(int i : scores) {
			System.out.println(i);
		}
	}

}
```