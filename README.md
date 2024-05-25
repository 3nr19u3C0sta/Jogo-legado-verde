import java.util.Scanner;

public class Jogar extends PrimeiraFase{
	//Formei uma herança em sequencia, para que a classe Jogar acesse todos os metodos das classes das respectivas fases
	static int escolha;

	public static void main(String[] args) {
		Interiorano objInteriorano = new Interiorano();
		Civil objCivil = new Civil();
		Scanner objsc = new Scanner(System.in);
		//Criei um Scanner para que o jogador possa escolher quais falas darão andamento na historia
		//Em seguida permito que o jogador possa escolher o nome e idade do personagem
		PrimeiraFase objPrimeiraFase = new PrimeiraFase();
		System.out.println("Por favor insira seu nome");
		objPrimeiraFase.setNome(objsc.nextLine());
		System.out.println("Por favor insira sua idade");
		objPrimeiraFase.setIdade(objsc.nextInt());
		
		//permito o jogador escolher um passado como classe de seu personagem, lhe dando uma vantagem que não havera na outra classe
		System.out.println("Escolha de onde veio\n"
				+ "Digite  o numero 1 ou o numero 2 para escolher"
				+ "1. Do interior\n"
				+ "2. Da cidade");
		Jogar.escolha = objsc.nextInt();
		//utilizo o polimorfismo para que o mesmo metodo possa ser usado pelas duas classes
		if (escolha == 1) {
			objInteriorano.passado();
		}
		else if (escolha == 2) {
			objCivil.passado();
		}
		//Dou inicio a historia trazendo os metodos das classes com o enredo
		introdução();
		falaIntrodução();
		//Utilizo if e else if, para que possa ser seguido um caminho, tambem utilizo os atributos escolha, para filtrar qual caminho de escolhas sera seguido, e não ter risco
		//de um caminho indesejado aparecer
		PrimeiraFase.escolha1 = objsc.nextInt();
		if (escolha1 == 1 && escolha2 == 0 && escolha3 == 0 && escolha4 ==0) {
			escolhaIndio();
			PrimeiraFase.escolha2= objsc.nextInt();
			if(escolha1 == 1&&escolha2 == 1 && escolha3 == 0 && escolha4 == 0) {
				escolhaIndioi1();
				PrimeiraFase.escolha3= objsc.nextInt();
				if(escolha1 == 1 && escolha2 == 1 && escolha3 ==1 && escolha4 == 0) {
					escolhaIndioi2();
					PrimeiraFase.escolha4= objsc.nextInt();
					
				}
				else if(escolha1 == 1 && escolha2 == 1 && escolha3 ==2 && escolha4 == 0) {
					escolhaIndioi2();
					
				}
			}
			else if(escolha1 == 1&&escolha2 == 2 && escolha3 == 0 && escolha4 == 0) {
				escolhaIndioi1();
				PrimeiraFase.escolha3= objsc.nextInt();
				if(escolha1 == 1 && escolha2 == 2 && escolha3 ==1 && escolha4 == 0) {
					escolhaIndioi2();
					
				}
				else if(escolha1 == 1 && escolha2 == 2 && escolha3 ==2 && escolha4 == 0) {
					escolhaIndioi2();
				}
			}
			
		}
		else if(escolha1 == 2 && escolha2 == 0 && escolha3 == 0 && escolha4 == 0) {
			escolhaSolo();
			PrimeiraFase.escolha2= objsc.nextInt();
			if(escolha1 == 2&&escolha2 == 1 && escolha3 == 0 && escolha4 == 0) {
				escolhaSolo1();
				PrimeiraFase.escolha3 = objsc.nextInt();
				if(escolha1 == 2 &&escolha2 == 1&&escolha3 ==1 && escolha4 == 0) {
					escolhaSolo11();
					PrimeiraFase.escolha4 = objsc.nextInt();
					if(escolha1 == 2 && escolha2 == 1&& escolha3 == 1 && escolha4 == 1) {
						escolhaSolo121();
					}
					if(escolha1 == 2 && escolha2 == 1 && escolha3 == 1 && escolha4 == 2) {
						escolhaSolo121();
					}
				}
				if(escolha1 == 2&&escolha2 == 1&&escolha3 ==2 && escolha4 == 0) {
					escolhaSolo12();
				}
			}
			else if(escolha1 == 2&& escolha2 == 2 && escolha3 == 0 && escolha4 == 0) {
				escolhaSolo2();
			}	
		}
		conversaChefe();
		SegundaFase.segundaescolha1 = objsc.nextInt();
		if (segundaescolha1 == 1&& segundaescolha2 == 0 && segundaescolha3 == 0 && segundaescolha4 == 0) {
			conversapacifica();
			conversapacifica1();
			SegundaFase.segundaescolha2 = objsc.nextInt();
			if (segundaescolha1 == 1 && segundaescolha2 == 1 && segundaescolha3 == 0 && segundaescolha4 == 0) {
				investigacaopescador();
				SegundaFase.segundaescolha3 = objsc.nextInt();
				if (segundaescolha1 == 1 && segundaescolha2 == 1 && segundaescolha3 == 1 && segundaescolha4 == 0) {
					investigacaopescador1();
				}
				else if (segundaescolha1 == 1 && segundaescolha2 == 1 && segundaescolha3 == 2 && segundaescolha4 == 0) {
					investigacaopescador2();
				}
			}
			else if (segundaescolha1 == 2 && segundaescolha2 == 1) {
				investigacaosolo();
				SegundaFase.segundaescolha3 = objsc.nextInt();
				if (segundaescolha1 == 2 && segundaescolha2 == 1 && segundaescolha3 == 1 && segundaescolha4 == 0)  {
					investigacaosolo1();
				}
				else if (segundaescolha1 == 2 && segundaescolha2 == 2 && segundaescolha3 == 2 && segundaescolha4 == 0) {
					investigacaosolo2();
				}
			}
		}
		
		else if(segundaescolha1 == 2&& segundaescolha2 == 0 && segundaescolha3 == 0 && segundaescolha4 == 0) {
			investigacaosolo();
			if (segundaescolha1 == 2 && segundaescolha2 == 1 && segundaescolha3 == 0 && segundaescolha4 == 0) {
				investigacaosolo1();
			}
			else if (segundaescolha1 == 2 && segundaescolha2 == 2 && segundaescolha3 == 0 && segundaescolha4 == 0) {
				investigacaosolo2();
				if (segundaescolha1 == 2 && segundaescolha2 == 2 && segundaescolha3 == 1 && segundaescolha4 == 0) {
					investigacaosolofimrapdio();
				}
				else if (segundaescolha1 == 2 && segundaescolha2 == 2 &&segundaescolha3 == 1 && segundaescolha4 == 0) {
					investigacaosolo2();
					if (segundaescolha1 == 2 && segundaescolha2 == 2 && segundaescolha3 == 1 && segundaescolha4 == 1) {
						investigacaosolofimbom();
					}
					else if (segundaescolha1 == 2 && segundaescolha2 == 2 && segundaescolha3 == 2 && segundaescolha4 == 2) {
						investigacaosolofimruim();
					}
				}
			}	
		}
		conversaFinal();
		TerceiraFase.escolhafinal1 = objsc.nextInt();
		if (escolhafinal1 == 1) {
			conversaFinal1();
		}
		else if (escolhafinal1 == 2) {
			conversaFinal2();
		}
		
	}

}
