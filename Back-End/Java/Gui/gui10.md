# Gui
```java
import java.awt.*;
import javax.swing.*;


public class NoLayoutDemo extends JFrame{
	static int x = 0;
	NoLayoutDemo() {
		setTitle("절대 위치로 배치!");
		
		JPanel p =new JPanel();
		p.setLayout(null);
		
		JButton b1 =new JButton();
		setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
		setSize(350,110);
		setVisible(true);
		while(x<=1900) {
			b1.setBounds(x++, 10, 60, 30);
		
		//JButton b2 = new JButton("버튼 2");
		//b2.setBounds(80, 20, 80, 25);
		
		//JButton b3 = new JButton("button 3");
		//b3.setBounds(150, 30, 100, 30);
		
		//p.add(b1);
		//p.add(b2);
		//p.add(b3);
		add(p);
		try {
			Thread.sleep(12);
		} catch (InterruptedException e) {
			
			e.printStackTrace();
		}
	
		}
		
		
		
	}
	
	
	public static void main(String[] args) {
		
			new NoLayoutDemo();
			

	}

}

```