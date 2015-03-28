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