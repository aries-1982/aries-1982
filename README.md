package Gui;

import java.awt.Color;

public class FarolTeste {

	
	GuiFarol farol,farol1;
	Temporizador temp;
	Color verm,amare,verd,verm2,amare2,verd2;
	
	
	FarolTeste(){
		
		
		inicializacao();
		
		
	}
	
	public void inicializacao(){
		
		
		
		farol=new GuiFarol();      // criando um objeto guifarol
		farol1=new GuiFarol();	   // criando mais um objeto guifarol	
		temp=new Temporizador();   // criando uma estancia
		
		
		new Thread(temp).start();     // iniciando o temporizador 
		new Thread(farol).start();	  // rodando semafaro 1	
		new Thread(farol1).start();	 // rodando semafaro2	
		
		
		while(true){
			
			this.obterCoresTemp(temp.getVermelho(),temp.getAmarelo(),temp.getVerde());   // metodo recebe as cores do temporizador
			this.obterCoresTemp2(temp.getVermelho2(),temp.getAmarelo2(),temp.getVerde2());
			farol.trocaCor(amare,verd,verm);												// metodo recebe a cor do farolteste
			farol1.trocaCor(amare2,verd2,verm2);
		}
	
	}
	
	
	public void obterCoresTemp(Color red,Color yelow,Color green){  // metodo obtem as cores do temporizador
		
		this.verm=red;
		this.amare=yelow;
		this.verd=green;
		
		
		
	}
	
public void obterCoresTemp2(Color red,Color yelow,Color green){  // metodo obtem as cores do temporizador
		
		this.verm2=red;
		this.amare2=yelow;
		this.verd2=green;
		
		
		
	}
	
	
	
	public static void main(String[] args) {
		
		new FarolTeste();
		
	}

}

