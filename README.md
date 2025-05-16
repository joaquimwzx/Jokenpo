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
        //Scanner para poder digita
        Scanner ler = new Scanner(System.in);
        //Entrada de dados
        cV = 0;
        cD = 0;
        cE = 0;
        /*
        Cont entra como falso para quando entrar no while ela
        se tornar verdadeira para manter o loop até digitar 9
        para finalizar o loop
         */
        cont = false;

        while (!cont) {
            System.out.println("0: Pedra");
            System.out.println("1: Papel");
            System.out.println("2: Tesoura");
            System.out.println("9: Sair do jogo");
            System.out.println("Faça sua escolha");
            jog = ler.nextInt();

            //Escolha do jogador
            if (jog == 0) {
                System.out.println("Jogador escolheu pedra");

            } else if (jog == 1) {
                System.out.println("Jogador escolheu papel");

            } else if (jog == 2) {
                System.out.println("Jogador escolheu tesoura");
                /*Quando jogador digitar 9 a variável cont
                vai ser true, mais quando entra no loop tem a
                negação na variável continua que irá entrar como
                false que finalizará o loop
                 */
            } else if (jog == 9) {
                cont = true;
            } else {
                System.out.println("Opção invalida");
                return;
            }
            //Escolha da maquina 
            maq = (int) (Math.random() * 3);
            
            if (maq == 0) {
                System.out.println("Maquina escolheu Pedra");
            } else if (maq == 1) {
                System.out.println("Maquina escolheu Papel");
            } else if (maq == 2) {
                System.out.println("Maquina escolheu Tesoura");
            }

            //Determinando quem venceu
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
        //Mostrar o placar de pontuação
        System.out.println("Pontos");
        System.out.println("Vitorias do jogador:" +  cV);
        System.out.println("Vitorias da maquina:" +  cD);
        System.out.println("Pontos de empate:" +  cE);

```
