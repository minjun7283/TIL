# 자바
```java
class Circle{
	private int radius;
	public Circle(int radius) {
		this.radius=radius;
	}
	public int getRadius() {
		return radius; 
	}
	
}

class NamedCircle extends Circle{
	String a;
	public NamedCircle(int radius,String a) {
		super(radius);
		this.a=a;
	}
	void show(){
		System.out.println(a+", 반지름 = "+getRadius());
	}
}

public class Test01 {

	public static void main(String[] args) {
		NamedCircle w = new NamedCircle(5, "Waffle");
		w.show();

	}

}
```