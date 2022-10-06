# 자바
```java
public class ArratListDemo {

	public static void main(String[] args) {
		Scanner sc = new Scanner(System.in);
		ArrayList<Integer> score = new ArrayList<Integer>();
		int data,sum=0;
		while((data=sc.nextInt())>=0) {
			score.add(data);
		}
		for(int i=0;i<score.size();i++) {
			sum+=score.get(i);
		}
		System.out.println((double)sum/score.size());
	}

}
```