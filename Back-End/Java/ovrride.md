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
class BestGirl extends GoodGirl{
	@Override
	void show() {
		System.out.println("그녀는 자바를 무지하게 잘안다.");
	}
}
public class GielTest {

	public static void main(String[] args) {
		Girl g1 = new Girl();
		Girl g2 = new GoodGirl();
		GoodGirl gg = new BestGirl();
		
		g2.show();
		gg.show();

	}

}
```