# project
```java
import java.awt.*;
import java.awt.event.*;

import javax.swing.JFrame;
import javax.swing.JPanel;
import javax.swing.border.EmptyBorder;
import javax.swing.JLabel;
import javax.swing.ImageIcon;
import javax.swing.JButton;
import javax.swing.BoxLayout;


public class Gui extends JFrame implements ActionListener{
	
	int count = 0;
	
	ImageIcon[] friendly = {new ImageIcon("C:\\Users\\USER\\Desktop\\\uC218\uC5C5 \uC790\uB8CC\\\uC0AC\uC9C4\\boss_-3 (1).png")
			,new ImageIcon("C:\\Users\\USER\\Desktop\\수업 자료\\사진\\화면 캡처 2022-06-09 165231.png")};
	ImageIcon[] enemy = {};
	
	int[] experience = {3,4,5,6,7};
	int[] life = {6,10,20,30,50,100};
	
	int index = ((int)Math.random())*6;
	int level=0,damege = level;
	
	private JPanel contentPane;
	JLabel lblNewLabel = new JLabel("New label");
	JLabel lblNewLabel_2 = new JLabel("New label");
	JPanel panel = new JPanel();

	/**
	 * Launch the application.
	 */
	public static void main(String[] args) {
		EventQueue.invokeLater(new Runnable() {
			public void run() {
				try {
					Gui frame = new Gui();
					frame.setSize(3000,1000);
					frame.setVisible(true);
				} catch (Exception e) {
					e.printStackTrace();
				}
			}
		});
	}

	/**
	 * Create the frame.
	 */
	public Gui() {
		
		setAutoRequestFocus(false);
		setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
		setBounds(100, 100, 1425, 1102);
		contentPane = new JPanel();
		
		contentPane.setBorder(new EmptyBorder(5, 5, 5, 5));
		setContentPane(contentPane);
		contentPane.setLayout(null);
		
		
		panel.setBounds(5, 5, 5000, 5000);
		panel.setLayout(null);
		contentPane.add(panel);
		
		//자신의 케릭터
		lblNewLabel.setIcon(friendly[count]);
		lblNewLabel.setBounds(46, 364, 700, 673);
		panel.add(lblNewLabel);
		
		//적 레이블
		lblNewLabel_2.setIcon(enemy[index]);
		lblNewLabel_2.setBounds(890, 538, 346, 310);
		panel.add(lblNewLabel_2);
		
		//공격 버튼
		JButton btnNewButton = new JButton("공격");
		btnNewButton.addActionListener(this);
		btnNewButton.setBounds(731, 857, 132, 72);
		panel.add(btnNewButton);
		
		//배경
		JLabel lblNewLabel_1 = new JLabel("New label");
		lblNewLabel_1.setIcon(new ImageIcon("C:\\Users\\USER\\Desktop\\\uC218\uC5C5 \uC790\uB8CC\\\uC0AC\uC9C4\\\uBC30\uACBD1.jpg"));
		lblNewLabel_1.setBounds(-100, -500, 5000, 2400);
		panel.add(lblNewLabel_1);
		
		
		
		
		
			
		
			
		
	}
	
	@Override
	public void actionPerformed(ActionEvent e) {
		JButton button = (JButton)e.getSource();
		
		//공격 모션
		try {
			
			Thread.sleep(12);
			
		} catch (InterruptedException e1) {
			e1.printStackTrace();
		}
		
		//적 처치
		if(life[index] >= 0) {
			count+=index;
			index = ((int)Math.random())*6;
			lblNewLabel_2.setIcon(enemy[index]);
			
		}
		//레벨업
		if(experience[level/10]<=count) {
			level++;
			
		}
		//레벨에 따른 모습변환
		if((level+1)%10==0)
			lblNewLabel.setIcon(friendly[level/10]);
		//엔딩
		if(level==49) {
			
		}
		
		
	}
}

```