# 자바
```java
public interface Controllable {
	default void repaier() {
		System.out.println("장비를 수리한디.");
	}
	
	static void reset() {
		System.out.println("장비를 초기화한다.");
	}
	
	void turnOn();
	void turnOff();
}
```