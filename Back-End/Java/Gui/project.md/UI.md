# UI
```java
package java_project;

import java.awt.BorderLayout;
import java.awt.EventQueue;
import java.awt.Frame;

import javax.swing.JFrame;
import javax.swing.JPanel;
import javax.swing.border.EmptyBorder;
import javax.swing.JButton;
import java.awt.event.ActionListener;
import java.awt.event.ActionEvent;
import javax.swing.JLabel;
import javax.swing.ImageIcon;

public class UI extends JFrame {

	private JPanel contentPane;
	static UI frame2 = new UI();

	/**
	 * Launch the application.
	 */
	public static void main(String[] args) {
		EventQueue.invokeLater(new Runnable() {
			public void run() {
				try {
					
					frame2.setSize(3000,1000);
					frame2.setVisible(true);
				} catch (Exception e) {
					e.printStackTrace();
				}
			}
		});
	}

	/**
	 * Create the frame.
	 */
	public UI() {
		setAlwaysOnTop(true);
		setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
		setBounds(0, 0, 1425, 1102);
		contentPane = new JPanel();
		contentPane.setBorder(new EmptyBorder(5, 5, 5, 5));
		contentPane.setLayout(new BorderLayout(0, 0));
		setContentPane(contentPane);
		
		JPanel panel = new JPanel();
		panel.setLayout(null);
		contentPane.add(panel, BorderLayout.CENTER);
		
		JButton btnNewButton = new JButton("시작하기");
		btnNewButton.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent arg0) {
				EventQueue.invokeLater(new Runnable() {
					public void run() {
						try {
							GUI frame = new GUI();
							frame.setSize(3000,1000);
							frame2.setVisible(false);
							frame.setVisible(true);
							
							
						} catch (Exception e) {
							e.printStackTrace();
						}
					}
				});
			}
		});
		btnNewButton.setBounds(870, 600, 200, 100);
		panel.add(btnNewButton);
		
		JButton btnNewButton_1 = new JButton("설명");
		btnNewButton_1.addActionListener(new ActionListener() {
			
			@Override
			public void actionPerformed(ActionEvent e) {
				EventQueue.invokeLater(new Runnable() {
					public void run() {
						try {
							Document frame4 = new Document();
							frame4.setVisible(true);
							frame2.setVisible(false);
						} catch (Exception e) {
							e.printStackTrace();
						}
					}
				});
				
			}
		});
		btnNewButton_1.setBounds(870, 730, 200, 100);
		panel.add(btnNewButton_1);
		
		JLabel lblNewLabel = new JLabel("New label");
		lblNewLabel.setIcon(new ImageIcon("./Image/배경 4.jpg"));
		lblNewLabel.setBounds(0, 0, 3000, 1000);
		panel.add(lblNewLabel);
		
		
	}
}
```