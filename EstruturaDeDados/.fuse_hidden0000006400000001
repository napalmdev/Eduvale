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
	










####04/10/2014

### Métodos de Busca

A disciplina de Estrutura de Dados na ciência da computação estuda algoritmos para, além da ordenação de dados em listas, busca de dados.
 Métodos de busca em E.D nada mais é que algoritmos para varrer listas de dados em busca de um determinado valor, sendo este valor encontrado ou não. O que determina a efetividade de um método é o tempo que o mesmo leva para retornar se o o dado existe ou não na lista e, existindo, sua loclização na lista, ou seja, os índices da posição no vetor uni ou multi dimensional.

 Lembrando que uma lista de dados é um conjunto de dados de correlacionados e armazenados em uma estrutura de dados básicos como os vetores e matrizes.

 **Dado o Conjunto de Dados: {7, 15, 32, 0, -1, 18, 36, 9, 25, 7}**

Crie um programa em C que carregue esses dados em memória e em seguida busque um valor informado pelo usuário retornando se o vlor existe e qual sua posição.

	
	int i,n,pos=-1,v[10] = {7, 15, 32, 0, -1, 18, 36, 9, 25, 7};

	printf("Digita um numero inteiro ae modafoka: ");
	scanf("%d",&n);
	i = 0;
	do{
		if(v[i] == n){
			n == i;
			pos = i;	
		}
		i++;
	}while(v[i] != n && i<10);

	if(pos == -1)
		printf("O numero %d que vc digitou nao foi encontrado");
	else
		printf("O numero %d que vc digitou foi encontrado na posicao %d do vetor.", n,pos);



###Busca Sequencial

É um método de Busca Padrão estudado e consolidado em ED. Ele consiste em varrer a lista de dados até encontrar o valor procurado, registrando o índice do elemento caso exista.
Na melhor das hipóteses o valor estará na primeira posição da lista, e a rotina de repetição será executada apenas uma vez;
Na pior das hipóteses o valor não existe, executando a rotina **n** vezes, sendo **n** o número de elementos da lista.
	Esse método é efetivo em **listas não ordenadas**. Para listas de dados que encontram-se ordenadas existem métodos mais adequados e eficientes. 


###Busca Binária  
####Pesquise sobre, descrevendo seu funcionamento e crie o algoritmo C para aplicação do método em uma lista de 100 elementos.






####03/11/2014

### Listas
Em ciência da computação uma lista é uma estrutura de dado que implementa um conjunto de valores, onde os mesmos podem se repetir várias vezes. Uma instância de uma lista é uma representação computacional do conceito matemático de "sequência finita". Cada instância de um valor na lista é chamado comumente de item de entrada ou **elemento** da lista. Se ocorrer várias vezes um mesmo valor, cada ocorrência é considerada um item distinto.
O nome lista também é usado para especificar Estruturas de Dados concretas, como o exemplo do vetor.


####Características de Listas
- Possuem Tamanho, que significa o número de elementos presentes na lista.
	. Lista Estática possui tamanho fixo
	. Lista Dinâmica possui tamanho mutável.
- Possui índice, cada elemento da lista possui um índice, que é um valor que indica a posição do elemento na lista.
	.Este índice é usado para encontrar ou remover um elemento na lista.


####Tipos de listas em ED:

 - Lista encadeada( ou ligada )
 - Lista FIFO, ou Fila
 - Lista LIFO, ou Pilha


####Listas FIFO - Filas
Em ciência da computação FIFO é, acrônimo de **First In , First Out**, que em português quer dizer, Primeiro que entra - Primeiro que sai.
A idéia da fila é que um elemento só pode ser inserido no finl da lista e só ser retirado do início.



####Listas LIFO - Pilha
Em ciência da computação LIFO é acrônimo do inglês **Last In , First Out**, que em português significa Último que Entra, Primeiro que Sai, e refere-se a estrutura de dados do tipo pilha. Um novo elemento só pode ser inserido no topo da pilha e uma remoção será executada também em seu topo, ou seja, o último elemento a entrar na pilha será o primeiro a ser removido.
Usa-se o termo **Push** e **Pop** para inserção e remoção na pilha. 


####Aplicações Comuns:
As Filas(FIFO) são amplamente aplicadas em filas de processos pelos sistemas operacionais, os processos são executados conforme entram na fila. Em programação são aplicados em listas de espera.

As Pilhas(LIFO), são implementadas pelos compiladores e S.O para manipularem variáveis Locais. Também é utilizado para guardar o endereço de retorno de uma trecho de programa que chamou uma função que esteja em execução.


####Listas Encadeadas
São  estruturas de dados não lineares e dinâmicas, ou seja, possuem tamanho mutável ao longo da execução do programa.
Esse tipo de lista caracteriza-se pela utilização de dois componentes por posição da lista , um guarda o valor e o outro guarda o endereço do próximo elemento.     





###Exercício(Entregar Manuscrito próxima Aula)

1. Criar um vetor de 100 elementos alimentado automaticamente com valores inteiros aleatórios, liste-o na tela  
2. Implemente uma busca Sequencial no mesmo, de valor fornecido pelo usuário.
3. Em seguida ordene o vetor com Bubble Sort, liste-o.
4. Implemente Busca Binária(idem 2º).
5. Remova um valor da lista usando FIFO.
6. Remova uma valor da lista usando LIFO.