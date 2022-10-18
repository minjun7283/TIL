# 자바
```java
class Girl{
	private String name;
	void show() {
		System.out.println("그년는 자바 초보자이다.");
	}
	Girl(String name){
		this.name=name;
	}
	Girl() {
		
	}	
	
}
class GoodGirl extends Girl{
	void show() {
		System.out.println("그녀는 자바를 잘 안다.");
	}
}

public class GielTest {

	public static void main(String[] args) {
		Girl g1 = new Girl();
		Girl g2 = new GoodGirl();
		g2.show();
		gg.show();

	}

}
```