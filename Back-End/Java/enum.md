# 자바
```java
class Exaple1 {

	public static void main(String[] args) {
		for(Direction d : Direction.values()) {
			System.out.print(d+" ");
		}

	}
	
}
enum Direction{
	동,서,님,북
}
```