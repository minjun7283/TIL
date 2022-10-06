# 자바
```java
class Circle{
	double radius;
	Circle(double radius){
		this.radius=radius;
	}
	double getRadius() {
		return radius;
	}
	double findArea(){
		return radius*radius*3.14;
	} 
}

public class CircleArrayDemo {

	public static void main(String[] args) {
		Circle[] c = new Circle[5];
		for(int i=0;i<c.length;i++) {
		c[i]= new Circle(i+1.0);
		System.out.println(c[i].radius+","+c[i].findArea());
		}
	}

}
```