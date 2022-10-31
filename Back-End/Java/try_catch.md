# 자바
```java
public class UnChecked2Demo {

	public static void main(String[] args) {
		int[] array = {0,1,2};
		try {
			System.out.println(array[3]);
			System.out.println(array[0]);
		}catch(ArrayIndexOutOfBoundsException e) {
			System.out.println("원소가 없다,");
		}
		System.out.println("어이쿠");
	}

}

```