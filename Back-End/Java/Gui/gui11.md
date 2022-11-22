# Gui
```java
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;

import javax.swing.JFrame;
import javax.swing.JMenu;
import javax.swing.JMenuBar;
import javax.swing.JMenuItem;
import javax.swing.JPanel;

public class MenuDemo extends JFrame implements ActionListener{
	JMenuBar menuBar;
	JMenu menu1,menu2;
	JMenuItem item1,item2,item3,item4;
	
	JPanel mainPanel = new JPanel();
	Panel1 panel1 = new Panel1();	
	Panel2 panel2 = new Panel2();
	
	
	public MenuDemo() {
		menuBar = new JMenuBar();
		menu1 = new JMenu("file");
		menu2 = new JMenu("Edit");
		menuBar.add(menu1);
		menuBar.add(menu2);
		
		item1 = new JMenuItem("new");
		item2 = new JMenuItem("Open File");
		item3 = new JMenuItem("Undo Typing");
		item4 = new JMenuItem("Redo");
		
		menu1.add(item1);
		menu1.add(item2);
		menu2.add(item3);
		menu2.add(item4);
		
		
		
		setJMenuBar(menuBar);
		add(mainPanel);
		mainPanel.add(panel1);
		mainPanel.add(panel2);
		
		item1.addActionListener(this);
		item2.addActionListener(this);
		item3.addActionListener(this);
		item4.addActionListener(this);
		
		setSize(400,500);
		setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
		setVisible(true);
		
		
	}
	
	public static void main(String[] args) {
		MenuDemo frame = new MenuDemo();

	}

	@Override
	public void actionPerformed(ActionEvent e) {
		if(e.getSource()==item1) {
			switching(0);
		}else if(e.getSource()==item2) {
			switching(1);
		}else if(e.getSource()==item3) {
			System.out.println("파일 삭제");
		}else if(e.getSource()==item4) {
			System.out.println("파일 저장");
		}
		
		
	}
	void switching(int selected) {
		JPanel[] ary = {panel1,panel2};
		for(int i =0;i<ary.length;i++) {
			ary[i].setVisible(false);
			if(i==selected)
				ary[i].setVisible(true);
		}
	}

}
```