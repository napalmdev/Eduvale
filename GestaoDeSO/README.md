##Gestão de S.O
###Professor Gustavo Montanha gmontanha@gmail.com

------------------------------------------------
#11/02/2015


### AULA 1

- #### Processos
- #### BCP
- #### Estados de Processos

------------------------------------------------
#### 1. INTRODUÇÃO
A gerência de um ambiente multiprogramável é função exclusiva do sistema operacional que deve controlar a execução dos diversos programas e o uso concorrente dos recursos. Para isso um programa para ser executado deve estar sempre associado a um processo. 



#### 2. PROCESSO
-> Programa em execução ?

-> Conjunto de informações necessárias para que o S.O implemente a concorrência entre os programas.

-> O S.O não executa somente o programa que visualizamos e sim seus diversos comandos e instruções via processos.

-> Todos os softwares que podem ser executados em um computador, inclusive o S.O em alguns casos, são organizados em vários processos.

Exemplo de ambientes de Processos: 
<img src="img/Processos01.jpg" alt="" />
>#####Quando uma instrução é interrompida um registrador específico grava o endereço de memória de onde a instrução foi interrompida para quando retornar a este ambiente ele saber de qual instrução continuar executando.


#### 2.1 DEFINIÇÃO DE PROCESSO
Ambiente onde programas são executados, sendo que para sua especificação completa, deve-se incluir o próprio programa a ser executado como outras informações tais como valores de variáveis, registradores, contador de programa e outros necessários para definição completa de seu estado.


#### 2.2 EXEMPLO


Processador  -  Programa  -  Dados  -  Processo
 		?							 ?					 ?					?

>######Um cientista está preparando um experimento para sua empresa. Ele possui um manual do experimento, um laboratório equipado com todas as ferramentas tais como: Anéis de alumínio, fitas de vedação e componentes químicos.



#### 3. BCP - Bloco de Controle de Processo (PCB - Process Control Block)
Todos os processos são implementados pelo S.O através da estrutura BCP. A partir do BCP o S.O mantém todas informações necessárias para sua execução.

#### 3.1 Contexto de Software
- São especificadas características e limites dos recursos que podem ser alocados pelos processos como por exemplo nº máximo de arquivos abertos, prioridades de execução, etc.

- Muitas dessas características são determinafdas no momento da criação do processo enquanto outras podem ser alteradas durante sua existência. 

- Composto por 3 grupos de informações 
	- IDENTIFICAÇÃO
   - Cada processo criado recebe um identificação única (PID - Process Identification).
   - Identificação do usuário (UID - User Identification) atribuída ao processo no momento de sua criação.

	- QUOTAS: São os limites de cada recurso do sistema que um processo pode alocar como por exemplo: Tamanho máximo de memória, número máximo de operações de E/S, etc.

	- PRIVILÉGIOS: Definem as ações que o processo pode fazer em relação a ele mesmo e outros processos.


#### 3.2 Contexto de Hardware
- Armazena o conteúdo dos registradores gerais e específicos da CPU
- Exemplo de Registradores:
	- REGISTRADOR PC: é o registrador contador de programa que indica o endereço na memória da próxima instrução a ser executada
	
	- REGISTRADOR PSW: Que fornece informações sobre a execução da instração e o estado do sistema em relação ao programa em execução 


#### 3.3 Contexto de Endereçamento
 - É a área de memória pertinente ao processo onde as instruções e os dados do programa são armazenados para execução.

 - Cada processo possui seu próprio espaço de endereçamento que deve ser protegido do acesso aos demais processos.


<br>
*Exemplo dos três Contextos citados acima*

<img src="./img/Contextos01.jpg" />


####Exercício

1. Por que o conceito de processo é tão importante no projeto de sistemas operacionais multiprogramáveis?
2. O que é contexto de Hardware no processo? E como funciona a implementação da troca de contexto?
3. Qual a função do contexto de Software? Cite e explique uma informação importante de cada grupo.
4. Defina processo.







------------------------------------------------
#25/02/2015

###AULA3
 - ESTADOS DE PROCESSOS
 - PROCESSOS INDEPENDENTES, SUB-PROCESSOS E THREADS
 - PROCESSOS CPU-BOUND     IO/BOUND



##ESTADOS DE PROCESSOS 
Durante a sua existência, os processos podem se apresentar em diferentes estados.
 - Criação (New)
 - Pronto (Ready)
 - Execução (Running)
 - Espera (Waiting)
 - Terminado (Exit)


####Criação:
Nesse estado o S.O crou seu BCP mas não pôde colocá-lo na lista de pronto.

####Pronto:
Um processo está pronto quando aguarda apenas para ser executado pela CPU(contexto de Software).

####Execução:
Momento em que efetivamente o processo usa a CPU.

####Espera:
Estão todos processos que sofreram algum tipo de interrupção(E/S).

####Terminado:
Não pode mais ter nenhum programa executado em seu contexto. O término pode ocorrer por razões como: 
 - Término normal de execução;
 - Eliminação forçada;
 - Ou eliminação por outro processo;

<img src="img/FluxoProcessos.jpg" alt="">



##Mudança de Estado de Processos
 - Criação - Pronto
 - Pronto - Execução
 - Execução - Pronto
 - Execução - Espera
 - Espera - Pronto
 - Execução - Terminado


####Criação - Pronto
O processo foi criado, tem seus recursos alocados, está apto a fazer uso da CPU de acordo com o **Escalonamento**.  


####Pronto - Execução
O processo é o primeiro da fila de pronto e a CPU fica disponível para sua execução.


####Execução - Pronto
O processo foi interrompido pela determinação da sua fatia de tempo ou prioridade.


####Execução - Espera
Essa transição acontece quando o processo foi interrompido por **Entrada/Saída** ou eventos externos.


####Espera - Pronto
Um processo está em Esprera, passa para Pronto quando a operação de **Entrada/Saída** solicitada é atendida. Um processo em Espera terá sempre que, passar para Pronto antes de ser novamente executado.


####Execução - Terminado
Nesta mudança o processo não mais disputará o uso da CPU. 



##PROCESSOS INDEPENDENTES
Maneira mais simples de implementar a concorrência não existindo vínculo do processo criado com seu criador.

##SUBPROCESSOS
São processos criados a partir de um processo pai dentro de uma estrutura hierárquica. Os subprocessos, assim como os processos independentes, possuem sua própria BCP.

<img src="img/ArvoreProcessos.jpg" alt="">



##Problemas
 - Uso de processos independentes e subprocessos demanda consumo de recursos do sistema.
 - Sempre que um processo é criado o sistema aloca a BCP(Bloco de Controle de Processo), consumindo tempo da CPU.
 - Falta de eficiência na comunicação entre processos.



##Threads
Surgiu na tentativa de reduzir o tempo gasto na criação, eliminação e comunicação de processos.
Neste ambiente um único processo pode suportar **Múltiplos Threads**.
Cada thread possui seu próprio contexto de hardware, porém compartilham o mesmo contexto de software e espaço de endereçamento.

<img src="img/Thread01.jpg" alt="">


###Processos Foreground X Background

 a - Foreground - permite comunicação direta entre usuário e processo.
 b - Background - não existe a comunicação direta processo-usuário



###Processos CPU-Bound X I/O Bound

<img src="img/CPU-IO-Bound.jpg" alt="">
