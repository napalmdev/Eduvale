#Anotações da Aula de OOP

####20/08/2014

### Conversões em JAVA


#### String para Int

Integer.parseInt();


#### String para Double

Double.parseDouble();

  
Objeto  = Dados + código


###Wrappers(Classes que armazenam um tipo primitivo)

byte -> Byte
short -> Short
int -> Integer
long -> Long
float -> Float
double -> Double
char -> Character
boolean -> Boolean




=========================================




####03/09/2014

### Uso de Datas

####Classes Date, Calendar e GregorianCalendar

  
    import java.util.*;
    public class UsandoDatas{    
      public static void main(String[] args){
        Date momento = new Date();
        System.out.prointln("Exibição de um objeto Date: " + momento);
        
        GregorianCalendar data = new GregorianCalendar();
        int dia = data.get(Calendar.DAY_OF_MONTH);
        int mes = data.get(Calendar.MONTH);
        int ano = data.get(Calendar.YEAR);
        int diaSemana = data.get(Calendar.DAY_OF_WEEK);
        int hora = data.get(Calendar.HOUR_OF_DAY);

        System.out.println("Data: " +dia+ "/" + (mes+1) + "/" + ano);
        System.out.println("Dia da semana: " + diaSemana);
        System.out.println("Hora: " + hora);   
      }
    }


###Exercício

####1. Com base no horário do sistema, exibir uma mensagem de saudação do tipo: Boa noite, Quarta-feira, 3 de setembro de 2014.


    import java.util.*;
    public class UsandoDatas{    
      public static void main(String[] args){
        Date momento = new Date();
        System.out.println("Exibição de um objeto Date: " + momento);

        GregorianCalendar data = new GregorianCalendar();
        int dia = data.get(Calendar.DAY_OF_MONTH);
        int mes = data.get(Calendar.MONTH);
        int ano = data.get(Calendar.YEAR);
        int diaSemana = data.get(Calendar.DAY_OF_WEEK);
        int hora = data.get(Calendar.HOUR_OF_DAY);

        System.out.println("Data: " +dia+ "/" + (mes+1) + "/" + ano);
        System.out.println("Dia da semana: " + diaSemana);
        System.out.println("Hora: " + hora); 
        
        
        String msg = "";
        
        if(hora < 12){
          msg = "Bom dia, ";
        }
        else if(hora < 18){
          msg = "Boa tarde, ";
        }
        else{
          msg = "Boa noite, ";
        }
        
       
        String[] diasDaSemana = {"", "Dom", "Seg", "Ter", "Qua", "Qui", "Sex", "Sab"};
        String[] meses = {"Jan", "Fev", "Mar", "Abr", "Mai", "Jun", "Jul", "Ago", "Set", "Out", "Nov", "Dez"};
        msg += diasDaSemana[diaSemana] + ", ";
        msg += (dia < 10) ? "0"+dia : dia; 
        msg += " de " + meses[mes] + " de " + ano;
        System.out.println(msg);
        
        
      }
    }



####2. Dado um número natural inteiro com no máximo três algarismos, exibir seu extenso. (0-999);


    import java.util.*;

    import javax.swing.JOptionPane;
    public class DescricaoNumeros{    
      public static void main(String[] args){ 
       
        String[] diasDaSemana = {"", "Dom", "Seg", "Ter", "Qua", "Qui", "Sex", "Sab"};
        String[] meses = {"Jan", "Fev", "Mar", "Abr", "Mai", "Jun", "Jul", "Ago", "Set", "Out", "Nov", "Dez"};
        msg += diasDaSemana[diaSemana] + ", ";
        msg += (dia < 10) ? "0"+dia : dia; 
        msg += " de " + meses[mes] + " de " + ano;
        System.out.println(msg);
        
        String numero = JOptionPane.showInputDialog("Digite qualquer numero inteiro");
             
        int n = Integer.parseInt(numero);

        String[] unidade = {"Zero", "Um", "Dois", "Tres", "Quatro", "Cinco", "Seis", "Sete", "Oito", "Nove" , "Dez", "Onze", "Doze", "Treze", "Quatorze", "Quinze", "Dezesseis", "Dezessete", "Dezoito", "Dezenove"};
        String[] dezena = {"", "", "Vinte", "Trinta", "Quarenta", "Cinquenta", "Sessenta", "Setenta", "Oitenta", "Noventa"};
        String[] centena = {"", "Cento", "Duzentos", "Trezentos", "Quatrocentos", "Quinhentos", "Seissentos", "Oitocentos", "Novecentos"};
        
        if(n == 100){
          JOptionPane.showMessageDialog(null, "Cem");
        }
        else
        {
            int u = n % 10;
            int d = n %100 / 10;
            int c = n / 100;      
          if(d == 1){
            d = 0;
            u+=10;
          }
          
          String num1 = "";
          if( c > 0 && (d > 0 || u > 0) )
            num1 += centena[c] + " e ";
          if(d > 0)
            num1 += (u > 0) ? dezena[d] + " e ": dezena[d];
          
          if(u > 0)
            num1 += unidade[u];
          
          JOptionPane.showMessageDialog(null, num1);
        }
        
        
      }
    }




####3. Dado um valor monetário entre R$ 0,00 e R$ 999.999.999,99, exibir seu extenso.












####10/09/2014

### Criação de Métodos

    public class TestaSoma{
        public static void main(String[] args){
            int a = 5;
            int b = 10
            int c = soma(a,b);
            System.out.println("A soma é: "+c);

            public static int soma(int x, int y){
                int z = x+y;
                return z;        
            }           
        }    
    }




 
####Gerar um palpite da MegaSena

>Obs:Classe Math.random() gera numeros randômicos, ela retorna Double e é nativa no Java

    import javax.swing.*;
    public class MegaSena{
        public static voi main(Strin[] args){
            String qtd = JOptionPane.showInputDialog("Quantos números:?");
            int n = Integer.parseInt(qtd);
            int palpite[] = new int[n];
            sorteia(palpite);
            ordena(palpite);
            mostra(palpite);
            }
        }

        public static void sorteia(int[]  num){
            int temp[] = new int [60];
            for(int i = 0; i<60; i++)
                temp[i] = i+1;
        
            for(int i = 1; i<=1000; i++){
                //faz cast de Double para int
                int pos1 = (int)(Math.random()*60);
                int pos2 = (int)(Math.random()*60);
                int aux  = temp[pos1];
                temp[pos1] = tempo[2];
                temp[2] = aux;
            }

            for(int i = 0; i< num.length; i++){
                num[i] = temp[i];
            }    
        }


        public static void ordena(int[] num){
            for(int i = 0; i<num.length-1; i++){
                for(int j = i+1; j < num.length; j++){
                    if(num[i] > num[j]){
                        int aux = num[i];
                        num[i] = num[j];
                        num[j] = aux;
                    }
                }
            }
        }


        public static void mostra(int[] num){
            for(int i = 0; i < num.length; i++){
                System.out.println(" "+num[i]);
            }
        }    
    }    





