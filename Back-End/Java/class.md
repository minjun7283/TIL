# 자바
```java
class Demo{
	String name;
	int grade;
	int number;
	char gender;
	void print() {
		System.out.println(grade+"학년"+number+"반 ");
	}
}
public class KimMinJunDemo {

	public static void main(String[] args) {
		Demo mydemo = new Demo();
		mydemo.grade = 1;
		mydemo.number = 3;
		mydemo.print();
		
		

	}

}
```