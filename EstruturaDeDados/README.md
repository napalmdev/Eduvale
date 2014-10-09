#Anotações Estrutura de Dados

####28/08/2014

### Variáveis Compostas Homogêneas

==================================

####VETORES: São matrizes unidimensionais

Em linguagem C o primeiro vetor utilizado é a variável **Char** para mais de um caracter, que
é declarada e manipulada como um vetor de caracteres do tamanho indicado na declaração.

Para declarar uma variável que guardará uma String de 20 letras no máximo usamos o código:

`char cidade[20];` 

onde **cidade** é o nome do vetor, char é o tipo e 20 é a quantidade de elementos.

"String" = Vetor de Char

`char nome[nº de Elementos]`

Ex: `char nome[10];`

Acesso ao Elemento do vetor:
	Nome do vetor seguido do índice do elemento.

	printf("Cidade Natal= %s", cidade);

	printf("Primeira letra do Nome = %s", nome[0])

	int umid[24];`  

	for(i = 0; i<24; i++) 
		
		umid[i] = read(equipamento);

	

##Exercícios


###1. 
#####Criar um programa que leia o valor de 100 produtos, e guarde em um vetor, numm segundo vetor guarde o valor do ICMS de cada produto, baseando-se numa alíquota de 13%.


	float prodVal[100], prodICMS[100], prodFinal[100];

 	for(i = 0; i<100; i++){
	
		printf("Entre com o valor do produto");
	
	 	scanf("%f",&prodVal[i]);
	
	 	prodICMS[i] = prodVal[i]* 0.13;
	
	 	prodFinal[i] = prodVal[i] + prodICMS[i];

 	}



###2.
#####Faça um programa que alimente um vetor de 1000 elementos somente com números pares(0 a 2000). Alimente um segundo vetor com os valores negativos do primeiro vetor. Mostre o segundo vetor em ordem crescente de valor. 

	int i, c = 0, v1[1000], v2[1000];
	//Atribuindo valores
    for(i = 0; i<20; i++){
		v1[i] = c;
		v2[i] = -c;
        printf("V1 = %d  -  V2 = %d\n", v1[i],v2[i]);                                                  
		c+=2;
	} 
    
    //Ordenando vetor v2 por ordem crescente
    
    for(i = 19; i>=0; i--){
          printf("V2 = %d\n", v2[i]);
    }



===============================================================================
####MATRIZ: São vetores Multi-Dimensionais

Estrutura semelhante ao vetor porém com pelo menos duas dimensões. Acompanha o conceito matemático de matriz. Consiste em uma estrutura composta por linhas e colunas, dadas em duas dimensões.

Declarações em C:

	tipo nome[dim1][dim2][dim...];

O mais comum é utilizar matriz de 2 dimensões.


Ex:
	
	int mat[10][4];
	float tab[5][5];
	
A martriz tem X elementos, sendo X a multiplicação da quantidade de elementos de suas dimensões. Ex:

	int trid[5][5][5];

Possui 125 elementos. 


**Atribuição de valores em um elemento da matriz:**

	int mat[10][4];
	mat[2][2] = 5;
	mat[0][0] = 1;
	mat[3][3] = 40;





##Exercícios


####1. Criar uma matriz quadrada de 100 elementos e alimetá-la com valores de 1 a 100 após imprimir na ordem decrescente.


####2. Converter o exercício do Produto, ICMS e valor em estrutura de matriz.





=========================================


####04/09/2014

### Vetores e Matrizes

São as estruturas de dados mais simples e clássicas da ciência da computação.

**VETOR:**  É uma matriz unidimensional, em linha ou coluna.

**Abaixo um Vetor de 6 elementos(ou Matriz Coluna)**
<table>
	<tr><td>0</td></tr>
	<tr><td>1</td></tr>
	<tr><td>2</td></tr>
	<tr><td>3</td></tr>
	<tr><td>4</td></tr>
	<tr><td>5</td></tr>
</table> 



**Abaixo um Vetor de 4 elementos(ou Matriz Linha)**
<table>
	<tr>
		<td>0</td>
		<td>1</td>
		<td>2</td>
		<td>3</td>
	</tr>
</table> 

Os vetores são preenchidos ou cessados através de seu identificador(nome) e o índice de seu elemento, que vai de 0 ao n-1, sendo n o número de elementos do vetor.


**MATRIZ:** termo utilizado para designar a estrutura de dados com mais de uma dimensão(geralmente duas). Seus valores são atribuidos e acessados de fora análoga ao vetores, porém indicando-se dois valores como endereço do elemento, já que uma Matriz é formada por linhas e colunas.


**Matriz Quadrada:** número de Linhas = número de Colunas

Ex: 

<table>
	<tr>
		<td>0</td>
		<td>1</td>
		<td>2</td>
		<td>3</td>
	</tr>
	<tr>
		<td>1</td>
		<td></td>
		<td></td>
		<td></td>
	</tr>
	<tr>
		<td>2</td>
		<td></td>
		<td></td>
		<td></td>
	</tr>
	<tr>
		<td>3</td>
		<td></td>
		<td></td>
		<td></td>
	</tr>
</table> 

Matrizes Bidimensionais(Linhas e Colunas) são as mais normais.


####Em linguagem C


Declaração de Matrizes(Vetores):

-Sintaxe:

	tipo identificador[i][j];

	//onde i = numero de elementosda dimensão 1
	//e j = numero de elementosda dimensão 2


Exemplos Vetores:

matriz: m[5][10]
Declara Matriz de 50 elementos

	//declara matriz quadrada de 100 elementos
	float m1[10][10];
	


	//Declara Vetor de inteiros com 1000 elementos
	int v1[1000];



	//Declara Vetor de Reais com 3 elementos
	float v2[3];



	//Declara Vetor de Caracteres com 80 elementos
	char c[80];
	



####Rotinas para Manipulação de Matriz Bidimensional

	int m[4][4], i, j ,c = 1;
	for(i = 0; i<4; i++)
		for(j = 0; j<4; j++){
			m[i][j] = c;
			c++;
		}
	for(i = 0; i<4; i++)
		for(j = 0; j<4; j++)
			printf("%d", m[i][j]);





####Matriz de String

Em linguagem C o armazenamento de texto faz uso de Vetores. Porém cada vetor guarde um conjunto de caracteres. Ex:

	char nome[10];
	nome[] = "Mandrake";
	printf("%s", nome);


Seguindo essa lógica, para guardarmos vários nomes na mesma variável não conseguiríamos com vetores. Temos que usar Matriz de Char.

Ex: Para uma Matriz que manipule até 10 nomes de no máximo 50 caracteres terímos.

	char nomes[10][50];
	nomes[3] = "Jose Lua";
	printf("%s", &nomes[3]);//Exibe Jose Lua




####Ordenar esse vetor em 
	
	int v[5] = {7,3,1,8,2};

	for(i)







####25/09/2014

### Exercícios com Matrizes

####Função para gerar números randômicos em C
	srand(time(NULL));
	variavel = rand() % 100;
	