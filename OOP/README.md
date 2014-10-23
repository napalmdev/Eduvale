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

    public class Extenso{
            
        public static String parte(int n){
            String numero = JOptionPane.showInputDialog("Qual o numero?");
            int n = Integer.parseInt(numero);
            String[] unidades = {"zero", "um", "dois", "tres", "quatro", "cinco", "seis", "sete", "oito", "nove", "dez", "onze", "doze", "treze", "quatoze", "quinze", "dezeseis", "dezesete", "dezoito", "dezenove"};
            String[] dezenas = {"", "", "vinte", "trinta", "quarenta", "cinquenta", "sessenta", "setenta", "oitenta", "noventa"};
            String[] centenas = {"","cento", "duzentos", "trezentos", "quatrocentos", "quinhentos", "seiscentos", "oitocentos", "novecentos"};
            
            if(n==100){
                JOptionPane.showMessageDialog(null, "cem");
            }
            else
            {
                int u = n%10;
                int d = n/10%10;
                int c = n/100;
                
                if (d==1){
                    d=0;
                    u+=10;
                }
                
                String texto = centenas[c];
                if(c>0&&(d>0||u>0))
                    texto+=" e ";
                texto+=dezenas[d];
                if(u*d>0)
                    texto+=" e ";
                
                texto+=unidades[u];
                JOptionPane.showMessageDialog(null, texto);
            }   
        
        }
           

    }









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







####08/10/2014

### OOP - Object Oriented Program


####Objeto = Estrutura de Dados + Algoritmos


####Conceitos Básicos

###1.Herança
Criar uma Classe com base em outra já existente.    

###2.Encapsulamento
Proteger/Ocultar uma parte da aplicação(tanto dados como código) do restante da aplicação.
(Facilidade de manutenção)    

###3.Polimorfismo
Implementar a mesma ação(Método) de formas diferentes.



###Exercícios OOP

####1. Em java o que significa um pacote?
Um pacote(package) a grosso modo é uma pasta no Sistema Operacional e serve para organizar a aplicação, nele podemos guardar arquivos de classes de mesma categoria e são essenciais para o conceito de Encapsulamento, se por exemplo precisarmos de alguma classe é só pesquisar no pacote daquela categoria.
Ainda assim para determinar que uma classe pertence à certo pacote, devemos informar na primeira linha do arquivo da mesma o seguinte código:
    
    package nome_do_pacote;  

Um exemplo de pacote é o **javax** do qual utilizamos a o subpacote **swing**.

<hr>



####2. Por que as classes devem ser organizadas em pacotes?
Como em Java é possível criar e importar várias classes de terceiros para a aplicação, se não houver um forma de separar fisicamente tais classes, ocorrerá um problema de nome de arquivo, pois o Sistema Operacional não permite mais de um arquivo com mesmo nome no mesmo diretório, e é aí que entra o pacote, para separar tais arquivos de forma organizada e intuitiva, tem ainda a questão do Encapsulamento que será abordada abaixo.

<hr>



####3. Com relação a visibilidade de uma classe (permissão para instanciação de seus objetos) e com relação aos membros de uma classe (atributos e métodos), quais são os modificadores de acesso possíveis? Explique sua utilização.
Para poder controlar o acesso devido e indevido à Classes, métodos e atributos, utilizamos o conceito de Encapsulamento que é possível em Java através dos Modificadores de Acesso, que são eles:
<br>
#####Public: 
Toda a aplicação pode acessar o que for definido como **public**, este modificador de acesso pode ser definido tanto para atributos e métodos quanto para a própria Classe. <br>
Quando a Classe é definida como public tanto as classes do mesmo pacote quanto as de outros pacotes podem instanciá-la normamente sem nenhuma restrição.
<br>
#####Protected
O modificador de acesso **Protected** permite o acesso à métodos e atributos da Classe por todas as classes do mesmo pacote e por qualquer classe que a estenda(conceito de Herança), mesmo que estas não estejam no mesmo pacote.<br>
Este modificador não pode ser usado para a Classe, somente para seus métodos e atributos.
<br>
#####Padrão(sem nenhum modificador de acesso) ou Default:
Caso nenhum modificador de acesso seja definido, as classes do mesmo pacote terão acesso à Classe, métodos e atributos.
<br>
#####Private
Este modificador permite acesso à métodos e atributos somente pela própria classe.<br> 
Ele só pode ser definido para métodos e atributos, nunca para a Classe.
<hr>



####4. O que é UML e como uma classe e seus membros são representados?
A UML (Unified Modeling Language), em português Linguagem Unificada de Modelagem é uma linguagem padrão para modelagem orientada a objetos. Ela tem como papel auxiliar a visualizar o desenho e a comunicação entre objetos e permite que desenvolvedores visualizem os produtos de seu trabalho em diagramas padronizados, ela é muito usada para criar modelos de sistemas de software.<br>
A Linguagem Unificada de Modelagem possui diagramas (representações gráficas do modelo parcial de um sistema) que são usados em combinação, com a finalidade de obter todas as visões e aspectos do sistema.


A Classe e seus membros são representados pelo **Diagrama De Classe**, este diagrama é fundamental e o mais utilizado na UML e serve de apoio aos outros diagramas. O Diagrama de Classe mostra o conjunto de classes com seus atributos e métodos e os relacionamentos entre classes.<br>
Através de várias figuras geométricas o Diagrama de Classe consegue representar tudo o que há de mais necessário no planejamento de uma aplicação orientada a objetos, tais como:

As Classes com seus atributos e métodos;<br>
Os Modificadores de Acesso dos mesmos;<br>
As relações intrinsicas entre as classes tais como: Herança, Associação, Agregação, Composição e etc.<br>

Entre várias outras relações que tornam extremamente mais fácil e encorajador, primeiro criar e documentar seus modelos e somente depois partir para a codificação.



<hr>



####22/10/2014

### UML



####(-) - Private
####(~) - Default
####(#) - Protected
####(+) - Public

<br><br>


####Abstract 
#####Classe:
Uma classe abstrata não pode ser instanciada. Não possui uma parte de sua funcionalidade, pois esta deverá ser implementadas por suas subclasses.

#####Método:
Não possui implementação. Deve ser implementado por uma subclasse.




####Static
#####Atributo:
Existe uma única cópia do atributo para todos os objetos da classe.
#####Método:
Pode ser executado diretamente pela classe, sem a necessidade de criar objetos.




####Final
#####Classe:
Não pode ser derivada(extendida).
#####Atributo:
Não pode ter seu valor alterado, pois ele é uma **Constante**.
#####Método:
Não pode ser sobrescrito.


<br><br>

###Exemplos

|  Pessoa  |
|----------|
|-nome:String| 
|-rg: String |
|+setNome(): void |
|+getRg(): String |
|+setRg(): void |





    public class Pessoa{
        private String nome;
        private String rg;

        
        public Pessoa(String nome){
            this.nome = nome;
        }
       
       //Polimorfismo por sobrecarga(Overload) 
        public Pessoa(String nome, String rg){
            this.nome = nome;
            this.rg = rg;
        }

        
        public Pessoa(){
        }
      

        public String getNome(){
            return nome;
        }

        public void setNome(String nome){
            this.nome = nome;
        }


        public String getRg(){
            return rg;
        }

        public void setRg(String rg){
            this.rg = rg;
        }
        
        //Polimorfismo por Sobrescrita(Overwrite)
        //Acontece porque o metodo toString() esta sendo sobrescrito da Classe Object
        public String toString(){
            String texto = getNome() + " - " + getRg();
            return texto;
        }
        
    }





    public class TestaPessoa{

        public static void main(String[] args){

            Pessoa p = new Pessoa("Zuero", "34244343242");
            System.out.println("Nome: " + p.getNome());
            System.out.println("RG: " + p.getRg());        
            p.setNome("Denis");
            p.setRg("43656789-3");
            System.out.println("Nome: " + p.getNome());
            System.out.println("RG: " + p.getRg());
            System.out.println(p);
        
        }
    }
