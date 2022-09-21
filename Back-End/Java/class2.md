# 자바
```java
class Printer{
	private int numOfpapers;
	private boolean duplex;
	public Printer(int numOfpapers,boolean duplex) {
		this.numOfpapers=numOfpapers;
		this.duplex=duplex;
	}
	public void print(int amount) {
		
		if(numOfpapers==0) {
			System.out.println("용지 없습니다.");
		}
		else if(duplex) {
			int num=amount/2;
			if(numOfpapers<num) {
				int num2=numOfpapers-num;
				System.out.println("양면으로 모두 출력하려면 용지가"+num2+" 매 부족합니다.현재"+num+"장만 출력합니다.");
				numOfpapers=0;
			}
			else if(amount%2==0) {
				numOfpapers-=num;
				System.out.println("양면으로"+num+"장 출력했습니다."+"현재 "+numOfpapers+"장 남아 있습니다.");
			}
			else {
				num +=1;
				numOfpapers-=num;
				System.out.println("양면으로"+num+"장 출력했습니다."+"현재 "+numOfpapers+"장 남아 있습니다.");
			}
		}
		else {
			if(amount>numOfpapers) {
				int num2=amount-numOfpapers;
				System.out.println("단면으로 모두 출력하려면 용지가"+num2+" 매 부족합니다.현재"+numOfpapers+"장만 출력합니다.");
				numOfpapers=0;
			}
			else if(amount%2==0) {
				
				System.out.println("단면으로"+amount+"장 출력했습니다."+"현재 "+numOfpapers+"장 남아 있습니다.");
			}
			else {
				System.out.println("단면으로"+amount+"장 출력했습니다."+"현재 "+numOfpapers+"장 남아 있습니다.");
			}
		}
	}
	
	public boolean getDuplex() {
		return duplex;
	}
	public void setDuplex(boolean duplex) {
		this.duplex=duplex;
	}
}

public class PritnerTest {

	public static void main(String[] args) {
		Printer p = new Printer(20,true);
		p.print(25);
		p.setDuplex(false);
		p.print(10);
		

	}

}
```