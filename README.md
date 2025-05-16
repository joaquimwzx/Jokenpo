# Jokenpo
```java
package jokenpo;

import java.util.Scanner;

public class Jokenpo {

    /**
     * @author Joaquim Alves
     */
    public static void main(String[] args) {
        //Declaração de variáveis
        int jog, sairJogo, cV, cD, cE, maq;
        boolean cont;
        //Scanner para o jogador poder digitar
        Scanner ler = new Scanner(System.in);
        //Entrada de dados
        cV = 0;
        cD = 0;
        cE = 0;
        /*
        Continua entra como false para quando entrar no while ela
        se tornar true para manter o loop até o jogador digitar 9
        para finalizar o loop
         */
        cont = false;

        while (!cont) {
            System.out.println("0. Pedra");
            System.out.println("1. Papel");
            System.out.println("2. Tesoura");
            System.out.println("9. Sair do jogo");
            System.out.println("Digite a opção desejada");
            jog = ler.nextInt();

            //Escolha do jogador
            if (jog == 0) {
                System.out.println("Jogador escolheu pedra");

            } else if (jog == 1) {
                System.out.println("Jogador escolheu papel");

            } else if (jog == 2) {
                System.out.println("Jogador escolheu tesoura");
                /*Quando jogador digitar 9 a variável continua
                vai ser true, porém quando entra no loop tem a
                negação na variável continua que irá entrar como
                false que finalizará o loop
                 */
            } else if (jog == 9) {
                cont = true;
            } else {
                System.out.println("Opção invalida");
                return;
            }
            //Gerando escolha random da maquina 
            maq = (int) (Math.random() * 3);
            //Escolha da maquina
            if (maq == 0) {
                System.out.println("Maquina escolheu Pedra");
            } else if (maq == 1) {
                System.out.println("Maquina escolheu Papel");
            } else if (maq == 2) {
                System.out.println("Maquina escolheu Tesoura");
            }

            //Determinar vencedor
            if (jog == maq) {
                System.out.println("Empate");
                cE++;
            } else {
                if (jog == 0 && maq == 2 || jog == 1 && maq == 0 || jog == 2 && maq == 1) {
                    System.out.println("Você venceu");
                    cV++;
                } else {
                    System.out.println("Você perdeu");
                    cD++;
                }

            }
        }
        //Placar de pontuação
        System.out.println("Placar de pontos");
        System.out.println("Vitorias do jogador:" + cV);
        System.out.println("Vitorias da maquina:" + cD);
        System.out.println("Pontos de empate:" + cE);

    }

}
```
