# 자바
```java
class Phone{
	String model;
	int value;
	void print() {
		System.out.println(value+" 만원 짜리"+ model+" 스마트폰");
	}
}
public class PhoneDemo {

	public static void main(String[] args) {
		Phone myPhone = new Phone();
		myPhone.model = "z플립4";
		myPhone.value=150;
		myPhone.print();
		
		
		Phone yourPhone = new Phone();
		yourPhone.model = "z플립4";
		yourPhone.value=150;
		yourPhone.print();
	}

}

```