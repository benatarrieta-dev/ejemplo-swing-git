import java.awt.BorderLayout;
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;

import javax.swing.JButton;
import javax.swing.JFrame;
import javax.swing.JLabel;
import javax.swing.JMenu;
import javax.swing.JMenuBar;
import javax.swing.JMenuItem;
import javax.swing.JPanel;
import javax.swing.JTabbedPane;

public class Formulario extends JFrame{

	private JLabel lbl;
	private JPanel pAbajo;
	private JButton btnSalida;
	public Formulario() {
		setBounds(500,250,600,400);
		setLocationRelativeTo(null);
		setDefaultCloseOperation(DO_NOTHING_ON_CLOSE);
		btnSalida = new JButton("SALIR");
		pAbajo = new JPanel();
		
		
		JMenuBar barraMenu = new JMenuBar();
		setJMenuBar(barraMenu);
		JMenu menuFile = new JMenu("File");
		barraMenu.add(menuFile);
		
		JMenuItem itemMostras = new JMenuItem("Mostrar");
		menuFile.add(itemMostras);
		JMenuItem itemLimpiar = new JMenuItem("Limpiar");
		menuFile.add(itemLimpiar);
		JMenuItem itemSalir = new JMenuItem("Salir");
		menuFile.add(itemSalir);
		
		
		JTabbedPane panelPestanas = new JTabbedPane();
		add(panelPestanas, BorderLayout.CENTER);
		panelPestanas.addTab("Datos Personales", new JPanel());
		panelPestanas.add("Información", new JPanel());
		panelPestanas.add("Comentarios", new JPanel());
		
		
		
		getContentPane().add(pAbajo, BorderLayout.SOUTH);
		pAbajo.add(btnSalida);
		btnSalida.addActionListener(new ActionListener() {
			
			@Override
			public void actionPerformed(ActionEvent e) {
				System.exit(0);
				
			}
		});
		setVisible(true);
		
	}
	public static void main(String[] args) {
		new Formulario();
	}
}
