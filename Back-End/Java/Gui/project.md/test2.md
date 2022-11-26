# Gui
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
import javax.swing.UIManager;

public class GUI extends JFrame implements ActionListener {

	int count = 0;

	ImageIcon[][] friendly = { { new ImageIcon("./Image/char0-1max1.png"), new ImageIcon("./Image/char0-1max2.png"),
			new ImageIcon("./Image/char0-1max3.png") }, {new ImageIcon("./Image/char1-1max2.png")} };
	ImageIcon[] enemy = { new ImageIcon("./Image/1.png"), new ImageIcon("./Image/2.png"),
			new ImageIcon("./Image/monster.png"), new ImageIcon("./Image/monster2.png"),
			new ImageIcon("./Image/boss1-1.png"), new ImageIcon("./Image/boss1-2.png"),
			new ImageIcon("./Image/boss_-2-1.png"), new ImageIcon("./Image/boss_-2-2.png") };
	ImageIcon[] background = { new ImageIcon("./Image/배경 4.jpg") };
	ImageIcon[] Hp = { new ImageIcon("./Image/Hp-5.png"), new ImageIcon("./Image/Hp-4.png"),
			new ImageIcon("./Image/Hp-3.png"), new ImageIcon("./Image/Hp-2.png"), new ImageIcon("./Image/Hp-1.png")

			
	};
	int[] experience = { 3, 4, 5, 6, 7 };

	int index = (int) (Math.random() * 8);
	int[] life = { 5, 10, 20, 30, 40, 50, 75, 100, index };
	int level = 0, damege = 1;
	int sumhp = life[index];
	private JPanel contentPane;
	JLabel friendlylabel = new JLabel();
	JLabel enemylabel = new JLabel();
	JPanel panel = new JPanel();
	static GUI frame = new GUI();
	JLabel label = new JLabel();
	JLabel back = new JLabel();
	JLabel hp = new JLabel();
	JButton attack = new JButton();
	/**
	 * Launch the application.
	 */
	public static void main(String[] args) {
		EventQueue.invokeLater(new Runnable() {
			public void run() {
				try {

					frame.setSize(3000, 1000);
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
	public GUI() {

		setAutoRequestFocus(false);
		setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
		setBounds(0, 0, 1425, 1102);
		contentPane = new JPanel();

		contentPane.setBorder(new EmptyBorder(5, 5, 5, 5));
		setContentPane(contentPane);
		contentPane.setLayout(null);

		panel.setBounds(5, 5, 5000, 5000);
		panel.setLayout(null);
		contentPane.add(panel);
		
		
		friendlylabel.setIcon(new ImageIcon("./Image/char0-1max1.png"));
		friendlylabel.setBounds(188, 277, 700, 673);
		panel.add(friendlylabel);

		// 적 HP
		hp.setIcon(new ImageIcon("./Image/Hp-1.png"));
		hp.setBounds(1179, 234, 192, 132);
		panel.add(hp);

		// 적 레이블
		enemylabel.setIcon(enemy[index]);
		enemylabel.setBounds(1008, 477, 346, 310);
		panel.add(enemylabel);

		// 공격 버튼
		
		attack.setIcon(new ImageIcon("./Image/attack.png"));
		attack.addActionListener(this);
		attack.setBounds(865, 845, 122, 73);
		panel.add(attack);

		label.setBounds(36, 26, 122, 36);
		panel.add(label);

		// 배경
		back.setIcon(background[count]);
		back.setBounds(0, 0, 3000, 1000);
		panel.add(back);

	}

	@Override
	public void actionPerformed(ActionEvent e) {
		JButton button = (JButton) e.getSource();

		boolean check = false;
		if(e.getSource() == attack) {
			check = true;
		}

		System.out.println(sumhp);
		
		 //공격 모션
		
		
		if(check) {
			try { 
				friendlylabel.setIcon(friendly[level/9][1]); 
				Thread.sleep(0);
				friendlylabel.setIcon(friendly[level/9][2]); 
				Thread.sleep(0);
				friendlylabel.setIcon(friendly[level/9][2]);
		 	
			} catch (InterruptedException e1) {
				e1.printStackTrace(); 
		 	}finally { 
			 	sumhp -= damege;
			 	
			 	
			 	hp.setIcon(Hp[sumhp / (life[index] / 5)]);
			 	
			 	
		 	}
		}
		 
		 
		 
		// 적 처치
		if (sumhp <= 0) {
			count += index;
			index = (int) (Math.random() * 8);
			life[8] = life[index];
			sumhp = life[index];
			hp.setIcon(Hp[4]);
			enemylabel.setIcon(enemy[index]);

		}
		// 레벨업
		if (experience[level / 10] <= count) {
			level++;
			count -= experience[level / 10];
			

		}
		// 레벨에 따른 모습변환
		if (level % 10 == 0) {
			friendlylabel.setIcon(friendly[level / 10][0]);
			back.setIcon(background[level / 10]);
			damege++;

		}
		// 엔딩
		if (level == 49) {
			try {
				Ending frame3 = new Ending();
				frame.setVisible(false);
				frame3.setVisible(true);
			} catch (Exception e2) {
				e2.printStackTrace();
			}
		}

	}
}

```