# Gui
```java
import java.awt.Color;
import java.awt.Dimension;
import java.awt.Label;

import javax.swing.*;



public class JFrame4Demo extends JFrame{
	JFrame4Demo(){
		setTitle("안녕,스윗!");
		ImageIcon c = new ImageIcon("./Button_Image/image_exitButton.jpg");
		JPanel p =new JPanel();
		Label l =new Label("안녕,스윙!");
		JButton b = new JButton("버튼");
		JButton a = new JButton("버튼");
		b.setPreferredSize(new Dimension(300,100));
		b.setRolloverIcon(c);
		a.setBackground(Color.blue);
		p.add(l);
		p.add(b);
		p.add(a);
		
		add(p);
		
		setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
		setSize(3000, 1000);
		//pack();
		setVisible(true);
	}
	public static void main(String[] args) {
		new JFrame4Demo();
		
		
		
		

	}

}
```