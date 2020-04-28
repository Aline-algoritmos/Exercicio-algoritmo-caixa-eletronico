// # Exercicio-algoritmo-caixa-eletronico
  import java.util.Scanner;
  
  class Main {
  public static void main(String[] args) {
    System.out.println("Welcome");

    Scanner util = new Scanner(System.in);

  
    String cpf ;
    int num1 = 1, num2 =2, num3=3,num4=4,num5=5,num6=6,num7=7,num8=8,num9=9,num10 =0,num11=0;
    String sair;
    int calculo1;
    int calculo2;
    int resultado1;
    int resultado2;
    int menu;
  
    int senhacad = 10120304;
    int senhadig;

    double saldo = 1000.00;
    double saque = 1000.00;
    double deposito ;

    System.out.println("Digite seu cpf");
    cpf= util.next();

    
    //calculuando o primeiro digito verificador do cpf
    calculo1 = num1 * 10 + num2 * 9 + num3 * 8 + num4 * 7 + num5 * 6 + num6 * 5 + num7 * 4 + num8 * 3 + num9 * 2;

    resultado1 = (calculo1 * 10 / 11 ) % 2;

    //Calculando o segundo digito verificador do cpf
    calculo2 = num1 * 11 + num2 *10 + num3* 9 + num4 * 8 + num5 * 7 + num6 * 6 + num7 * 5 + num8 * 4 + num9 * 3 + num10 * 2;

    resultado2 = (calculo2 * 10 / 11) % 2;

   // Validando os dois ultimos digitos do cpf
    if( resultado1 != num10 && resultado2 != num11){
      System.out.println("Acesso não permitido");
      System.exit(0);
    }
    
    //Se o cpf for validado na condicao anterior (if), solicite ao usuário a senha
   else { System.out.println("Digite a sua senha");  }
   senhadig = util.nextInt();
   
   //Se senha digitada for diferente da senha cadastrada
    if( senhadig != senhacad){
    
   // Permita mais duas tentativas de digitação
    for( int i = 0; i< 2; i++){
    System.out.println( "senha incorreta. Digite a sua senha");
    senhadig = util.nextInt();
    }
    // Se a senha for incorreta, exibir mensagem na tela : conta bloqueada com orientação devida
    if( senhadig != senhacad) {System.out.println( "Conta bloqueada. Procure uma agencia ou entre em contato com a central da sua conta"); }
    }
 
    // Se senha for confirmada ,exibir menu de opções
    if(senhadig == senhacad){ System.out.println(" Digite o número da opção desejada ");  
    
       System.out.println("1- Saldo ");
       System.out.println("2- Depósito "); 
       System.out.println("3- Saque");
       System.out.println("0 -Sair ");
    }
    
    // lendo opção digitada pelo usuário
    menu =util.nextInt();
    switch(menu){
    
    case 1:
    System.out.println("1- Saldo ");
    break;
       
    case 2:
    System.out.println("2-Depósito "); 
    break;

    case 3:
    System.out.println("3- Saque");
    break;

    case 0:
    System.out.println("0 -Sair ");
    break;
     
    }
   // condições e leitura das opções exibidas anteriormente
    if ( menu == 1) { System.out.println("Saldo = "    +saldo);}

    if ( menu == 2) { System.out.println("Digite o valor a ser depositado ");
    deposito = util.nextDouble();
    System.out.println( saldo += deposito);  }

    if ( menu == 3) { System.out.println("Digite o valor a ser sacado");
    saque = util.nextDouble(); 
    System.out.println(saldo -= saque ); }

    if ( menu == 0 || menu >= 5) {  main(args);  } 
    
  }


}

  
