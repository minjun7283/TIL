# 자바
```java
class Rect{
	private int width,height;
	public Rect(int width,int height) {
		super();
		this.width = width;
		this.height=height;
	}
	public int getArea() {
		return width*height;
	}
}

class RectArray extends Rect{
	static int i=0;
	static int[] Rect = new int[5];
	public RectArray(int width, int height) {
		super(width, height);
		i++;
		Rect[i] = getArea();
		
	}
	int Show() {
		i=0;
		for(int j = 1;j<5;j++) {
			i+=Rect[j];
		}
		return i;
	}
}

public class Test5 {

	public static void main(String[] args) {
		Scanner sc = new Scanner(System.in);
		System.out.print(1+" 너비와 높이 >>");
		RectArray a = new RectArray(sc.nextInt(), sc.nextInt());
		for(int i=2;i<=4;i++) {
			System.out.print(i+" 너비와 높이 >>");
			RectArray a1 = new RectArray(sc.nextInt(), sc.nextInt());
		}
		System.out.println("사각형의 전체 합은 "+a.Show());
		
		
		
	}

}
```