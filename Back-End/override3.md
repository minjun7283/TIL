# 자바
```java
class Vehicle{
	String color;
	int speed;
	public Vehicle(String color, int speed) {
		super();
		this.color = color;
		this.speed = speed;
	}
	void show() {
		System.out.println(color+speed);
	}
}
class Car extends Vehicle{
	int displacement,gears;
	public Car(String color, int speed,int displacement,int gears) {
		super(color, speed);
		this.displacement = displacement;
		this.gears=gears;
		
	}
	@Override
	void show() {
		System.out.println(super.color+super.speed+displacement+gears);
	}
}

public class Test06 {

	public static void main(String[] args) {
		Car c =new Car("파랑",200,1000,5);
		c.show();
		
		System.out.println();
		Vehicle v =c;
		v.show();

	}

}
```