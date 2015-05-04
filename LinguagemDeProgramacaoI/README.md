##Linguagem de Programação I
###Professor Marcos profmarcosmendes@gmail.com

------------------------------------------------
#10/02/2015


##Sobre o operador **&**
```c
	scanf("%d", &a);
```
> #####O *&* na instrução acima indica o endereço de memória a qual a variável **a** pertence. 






------------------------------------------------
#10/03/2015



####Criar um programa que leia 3 números e os exiba em ordem inversa a de entrada.

**Entrada:** 1, 2, 3, 4, 5
**Saída:** 5, 4, 3, 2, 1


```c
ìnt i, a[5];

for( i = 0; i < 5; i++ ){
	printf("Digite o %d número: ", i+1);
	scanf("%d", a[i]);
}	
//exibindo o vetor
for( i = 4; i >= 0; i-- ){
	printf("%d\t", a[i]);
}	
```



####Criar um programa que leia 10 números inteiros armazenando-os em um array. Após a leitura, ler um número e informar se este número está contido no array.

```c
int i, num, numeros[10], inicio = 0, findPos = -1, find = 0, meio, fim = 9;
for( i = 0; i < 10; i++ ){
	printf("Digite o %d numero: ", i+1);
	scanf("%d", &numeros[i]);
}
printf("\n\nDigite um numero para busca no vetor: ");
scanf("%d", &num);


//Busca Sequencial/Linear
for( i = 0; i < 10; i++){
	if(num == numeros[i]){
		find = 1;
		findPos = i;
		break;
	}
}
if( find == 1){
	printf("Achou com a Busca Sequencial na Posicao %d - no Indice %d do Vetor\n\n", i+1, i);	
}
else{
	printf("Nao Achou com a Busca Sequencial");
}





//Busca Binaria
find = 0;
while(inicio <= fim && find == 0){
    meio = ((inicio + fim) / 2);
    if(numeros[meio] == num)
        find = 1;    
    else if(numeros[meio] > num)
        fim = meio - 1;
    else
        inicio = meio + 1;           
}        
if(find == 1)
    printf("SEU VALOR FOI ENCONTRADO NA POSICAO %d - INDICE %d DO VETOR\n\n", meio+1, meio);
else
    printf("SEU VALOR NAO FOI ENCONTRADO NO VETOR\n\n");
```






####Criar um programa que leia 10 números inteiros armazenando-os em um array. Após a leitura, exibí-los em ordem não decrescente.

```c
int i, j, aux, numeros[10];
for( i = 0; i < 10; i++ ){
	printf("Digite o %d numero: ", i+1);
	scanf("%d", &numeros[i]);
}

//Algoritmo de Ordenacao
for( i = 0; i < 9; i++){
	for( j = i+1; j < 10; j++){
		if( numeros[j] < numeros[i]){
			aux = numeros[j];
			numeros[j] = numeros[i];
			numeros[i] = aux;
		}
	}
}

for( i = 0; i < 10; i++ ){
	printf("%d\n", numeros[i]);
}

```




####Criar um programa que leia 10 números inteiros armazenando-os em um array. Após a leitura, classifique-os em ordem não decrescente, leia um valor inteiro e informe se o mesmo se encontra no array.

```c
int i, j, aux, num, numeros[10], inicio = 0, findPos = -1, find = 0, meio, fim = 9;
for( i = 0; i < 10; i++ ){
	printf("Digite o %d numero: ", i+1);
	scanf("%d", &numeros[i]);
}

//Algoritmo de Ordenacao
for( i = 0; i < 9; i++){
	for( j = i+1; j < 10; j++){
		if( numeros[j] < numeros[i]){
			aux = numeros[j];
			numeros[j] = numeros[i];
			numeros[i] = aux;
		}
	}
}


printf("\n\n");


for( i = 0; i < 10; i++ ){
	printf("%d\t", numeros[i]);
}


printf("\n\nDigite um numero para busca no vetor: ");
scanf("%d", &num);

//Busca Binaria
find = 0;
while(inicio <= fim && find == 0){
    meio = ((inicio + fim) / 2);
    if(numeros[meio] == num)
        find = 1;    
    else if(numeros[meio] > num)
        fim = meio - 1;
    else
        inicio = meio + 1;           
}        
if(find == 1)
    printf("SEU VALOR FOI ENCONTRADO NA POSICAO %d - INDICE %d DO VETOR\n\n", meio+1, meio);
else
    printf("SEU VALOR NAO FOI ENCONTRADO NO VETOR\n\n");

```



>####Obs: Somente utilizar a Busca Binária se o vetor já estiver ordenado, pois caso precise ordená-lo utilizando um algoritmo de ordenação o tempo das rotinas será maior que apenas utilizar a Busca Sequencial.







1.Criar uma função contaA() que recebe uma string texto e retorna a quantidade de letras ‘a’ nessa string;

2.Criar uma função inverte() que recebe uma string texto e essa função inverte a posição de seus caracteres.

3.Ler 10 nomes e exibi-los em ordem alfabética.

--------------------------------------
#17/03/2015

##Criação de subrotinas(funções)

```c
#include <stdio.h>
#include <stdio.h>
int soma(int, int);
void main(){
  int a, b;
  a = 5;
  b = 10;
  printf("A soma é %d", soma(a,b));

  int soma(int x, int y){
    int total = x + y;
    return total;
  }
}
```


####Criar um programa que exiba um palpite da MegaSena.

**Requisitos Funcionais**
 - Palpite com 6 números.
 - Inteiros entre 1 e 60.
 - Exibição dos números em ordem crescente.
 - Não pode haver números repetidos.



--------------------------------------
#24/03/2015



##Strings – Cadeias de Caracteres
###1.Introdução
Em linguagem C, uma string é representada por um array de caracteres.
```Char nome[30] ;```
Como o "conteúdo útil" da string pode ser menor que o tamanho do array, a string é finalizada com o caracter '\0' .

###2.Algumas funções
```
gets()
fgets()								

puts() 
printf(“%s”)											

strlen() – Retorna o comprimento da string.
strcpy(s1,s2) – Copia uma string s2 na string s1.
strcmp(s1,s2) – Compara lexigraficamente duas strings.
		Retorna = 0 se são iguais;
			 < 0 se s1 vem antes que s2;
			 > 0 se s1 vem depois que s2.

```
**Exemplo:**
``` 
strcpy(s1,“Ana”);
strcpy(s2,”Maria”);
strcat(s1,s2) – Concatena S2 em S1; (AnaMaria)
```

###3.Exercícios
		



--------------------------------------
#31/03/2015

####Exercício
Dado N natural entre 0 e 999, exibir seu extenso.

```c
#include <stdio.h>
#include <stdlib.h>
#include <string.h>


int main(int argc, char *argv[])
{
  char unidade[][10] = {"","Um","Dois", "Tres", "Quatro", "Cinco", "Seis", "Sete", "Oito", "Nove", "Dez", "Onze", "Doze", "Treze", "Quatorze", "Quinze", "Dezesseis", "Dezessete", "Dezoito", "Dezenove"};
  char dezena[][10] = {"","","Vinte","Trinta","Quarenta","Cinquenta","Sessenta","Setenta","Oitenta","Noventa"};
  char centena[][15] = {"","Cento","Duzentos","Trezentos","Quatrocentos","Quinhentos","Seissentos", "Setessentos", "Oitossentos", "Novessentos"};
  char ext[255];
  int n, c, d, u; 
  printf("Digite um numero: ");
  scanf("%d",&n);
  c = n/100;
  d = n/10 % 10;
  u = n % 10;
  
  if(d == 1){
    u+= 10;
    d = 0;
  }
  strcpy(ext, centena[c]);
  if(n == 100){
       puts("Cem");
  }
  else{
      if(c > 0 && (d > 0 || u > 0)){
        strcat(ext, " e ");
      }
      strcat(ext, dezena[d]);
      if(c*d*u > 0){
        strcat(ext, " e ");
      }
      strcat(ext, unidade[u]);
      puts(ext);
  
  }
  
  system("PAUSE");	
  return 0;
}
```


####Exercício
Criar uma função igual() que recebe duas Strings S1 e S2 e retorna 1 se forem iguais ou 0 caso o contrário.




####Exercício
Criar uma função somaPar() que recebe um array de inteiros num[] e um inteiro n representando a quantidade de elementos.
Retornar a soma dos elementos pares.

```c
#include <stdio.h>
#include <stdlib.h>

int main(int argc, char *argv[])
{
  srand(time(NULL));
  int i, num[2];
  for(i = 0; i < 2; i++){
      num[i] = rand() % 100;
      printf("%d\t",num[i]);  
  }
  
  int somaPar(int n,int num[n]){
    int i, soma = 0;
    for( i = 0; i < n; i++){
      if(num[i] % 2 == 0){
        soma+= num[i];
      }
    }
    
    return soma;
  }
  
  printf("%d\n\n", somaPar(2,num));
  
  system("PAUSE");	
  return 0;
}

``` 




####Exercício
Criar uma função contaMaiusculas() que recebe uma String texto e retorna a quantidade de letras maiusculas.





-------------------------------------------------------------------
#14/04/2015


##Agregados Heterogêneos - Structs


####Definindo uma Struct
```c
struct Pessoa{
  char nome[30];
  int idade;
}
```


####Utilizando uma Struct
```c
struct Pessoa p1;
p1.nome = "Joao";
p1.idade = 12;
```


####Exemplo do uso de Struct
```c
#include <stdio.h>
#include <stdlib.h>

struct Pessoa{
  char  nome[30];
  int idade;
};

void main(){
  struct Pessoa p1;
  
  printf("Qual o nome?");
  gets(p1.nome);
  
  printf("\nQual a idade?");
  scanf("%d", &(p1.idade));

  printf("\n-----------------");
  printf("\nDados digitados: ");
  printf("\nNome:%s", p1.nome);
  printf("\nIdade:%d\n", p1.idade);
  
  system("PAUSE");
}
```



####Exemplo 2 do uso de Struct
```c
#include <stdio.h>
#include <stdlib.h>

struct Pessoa{
  char  nome[30];
  int idade;
};

void main(){
  struct Pessoa pessoas[3];
  int i;  
  for(i = 0; i < 3; i++){
    printf("Qual o nome?");
    gets(pessoas[i].nome);
    printf("\nQual a idade?");
    scanf("%d", &(pessoas[i].idade));
    fflush(stdin);
  }

  printf("\nDados digitados: ");

  for(i = 0; i < 3; i++){
    printf("\n-----------------");
    printf("\nNome:%s", pessoas[i].nome);
    printf("\nIdade:%d\n", pessoas[i].idade);
  }
  
  system("PAUSE");
  
}

```
###Obs:
>####A função do *fflush* é limpar o buffer, no caso de *fflush(stdin)* limpa o buffer de entrada de dados(teclado ou outros periféricos de entrada).




-------------------------------------------------------------------
#28/04/2015

## Passagem de parâmetros por referência

### Por Valor: 
É feita uma cópia do valor do argumento para o parâmetro da função.

### Por Referência: 
É passado o endereço de memória para o parâmetro da função. 

###Ponteiro:
Variável que armazena o endereço de memória.

```c
#include <stdio.h>
#include <stdlib.h>

void troca(int*, int*);
int main(int argc, char *argv[])
{
  int a = 5, b = 10;
  
  printf("A: %d\tB: %d\n\n", a,b) ; 
  
  troca(&a, &b); //Passagem de parâmetro por referência
  
  printf("A: %d\tB: %d\n\n", a,b) ; 
  
  system("PAUSE");	
  return 0;
}

void troca(int* a, int* b){ //recebe os ponteiros como parâmetros
  int aux;
  aux = *a;
  *a = *b;
  *b = aux;
}
```



##Definição de Array
>####Array é um agregado homogênio, sua estrutura de dados é estática, ou seja, sua quantidade de elementos é fixa.



#Alocação Dinâmica de Memória
É a reserva de uma área de memória em tempo de execução.

**void\* malloc(tamanho)** - Aloca uma área de memória baseado no parâmetro tamanho e retorna um ponteiro genérico

**free(endereco)** - Libera a área de memória informada no parâmetro endereço, endereço este que é retornado pela função malloc.

** Exemplo:**
```c
 int* primos = (int*)malloc(sizeof(int) * 5); 
```

** Obs: sizeof(int)**: retorna o tamanho em bytes de um determinado tipo de dado.


```c
#include <stdio.h>
#include <stdlib.h>
#include <malloc.h>

int* adiciona(int, int*, int);
int main(int argc, char *argv[])
{
  int* primos;
  int numeros[] = { 2, 3, 5, 7, 11};
  primos = &numeros[0];
  primos = adiciona(13, primos, 5);
  
  int cont;
  for(cont = 0; cont < 6; cont++){
    printf("\n%d\n", primos[cont]);
  }
  
  
  system("PAUSE");	
  
  return 0;
}

int* adiciona(int valor, int* matriz, int qtd){
  int* aux = (int*)malloc(sizeof(int) *(qtd+1));
  int i;
  for(i = 0; i < qtd; i++){
    aux[i] = matriz[i];
  }
  aux[qtd] = valor; 
  
  return aux;
}

```
