##Fundamentos e Modelagem de Bancos de Dados
###Professor Mauro Garcia mauro.avare@gmail.com

------------------------------------------------
#02/02/2015


#Conceito de Banco de Dados
> ####Conjunto de tabelas interrelacionais que armazenam dados de um domínio específico.


### Modelagem de Dados

- #### Documentação
  - DFD - Diagrama de Fluxo de Dados
  - MER - Modelo Entidade Relacionamento
  - Dicionário de Dados


- #### Dependências, formas normais e Cardinalidade

- #### Sistemas Gerenciadores de Banco de Dados SGBD

- #### SQL - Structured Query Language

- #### Softwares para Instalar
  - MySQL
  - Workbench - Oracle



- #### bit = pulso elétrico valor 0 ou 1

- #### Byte = 8 bits

- #### Dado = resultado de uma observação ou medição

- #### Informação = dado dentro de um contexto, com um SIGNIFICADO



------------------------------------------------
#09/02/2015

------------------------------------------------
###Fundamentos e Modelagem de Bancos de Dados

####O que são dados?
 - fatos conhecidos
 - resultado de medição
 - fruto de observação
 - possio significado implícito


####O que é informação?
 - Combinação de dados dentro de um contexto
 - Deve sempre acrescentar algo
	

####Banco de Dados
 - Conjunto de tabelas interrelacionais que armazenam dados de um domínio específico.


####Vantagens
 - Rapidez na manipulação e acesso à informação
 - Redução de esporço humano
 - Compartilhamento de dados
 - Combate à redundância e inconsistência.
 - Disponibilização da informação no tempo necessário


####Propriedades de um BD
 1. Coleção lógica e coerente de dados
 2. Projetado e populado para um fim específico
 3. Possui um conjunto pré-definido de usuários
 4. Representa um aspecto do mundo real
 5. Pode ser manipulado por um conjunto de aplicações



####Tabelas, Campos e Registros
 - Propriedades dos Campos
  - Sem Espaços e caracteres especiais
  - Não Iniciar por números
  - Iniciar o nome com um referência à tabela ex: EstadoCodigo, EstadoNome, EstadoUF

 - Tipos de Campo
  - Inteiro
  - Decimal
  - Data
  - Text
  - Timestamp
  - Hora
  - Data / Hora
  - Varchar
  - Char
  - Blob



------------------------------------------------
#23/02/2015

####Chave Primária( Primary Key - PK )
**Definição:**
 - Campo de uma tabela com o valor exclusivo 
 - Não permite valor duplicado


####Modelando uma tabela para cadastro de cidades

##### Tabela: tblcidades

#####Campos:
Nome | Tipo | Tamanho | Null | A.I | P.K | ValorPadrão
-----|------|---------|------|-----|-----|----------------
CidadeCodigo | int | - | Não | Sim | Sim 
CidadeNome | VarChar | 50 | Não | Não | Não  
CidadeUF | VarChar | 2 | Não | Não | Não  
CidadeIBGE | int | | Sim | Não | Não 
CidadeCEP | VarChar | 8 | Não | Não | Não 
CidadeTimeStamp | TimeStamp | | Não | Não | Não  




------------------------------------------------------



##### Tabela: tblbairros

#####Campos:
Nome | Tipo | Tamanho | Null | A.I | P.K | ValorPadrão
-----|------|---------|------|-----|-----|----------------
BairroCodigo | int | - | Não | Sim | Sim 
BairroCidade | int | - | Não | Não | Não 
BairroNome | VarChar | 50 | Não | Não | Não  
BairroTimeStamp | TimeStamp | | Não | Não | Não  












------------------------------------------------
#02/03/2015

------------------------------------------------
###Modelo de Dados

| Artista ||
|---------|----------|
|IDArtista | int(PK)|
Nome    |  varchar(50)
Ritmo   | varchar(30)




| CD | |
|---------|----------|
IDCD | int(PK)
Titulo    |  varchar(30)
Preco   | decimal(10,2)
Gravadora | varchar(30)
IDArtista | int(FK)




| Musica |  |
|---------|----------|
|IDMusica | int(PK)|
Titulo    |  varchar(50)
Duracao   | int
IDCD    | int(FK)









####SQL - Padrão ANSI

###CRUD

 - C : Create
 - R : Read
 - U : Update
 - D : Delete







------------------------------------------------
#09/03/2015

------------------------------------------------
###XAMP
>#####Pacote de instalação que instala o Apache, PHP, Mysql e PHPMyAdmin

###MySQL
>#####É um SGBD, ou seja, um banco de dados relacional

###PHP
>#####Liguagem de programação voltada pra desenvolvimento Web

###PHPMyAdmin
>#####Conjunto de páginas escritos em PHP para gerenciar visulamente um banco de dados MySQL.



###Cardinalidade

 - ##### 1 - N
 - ##### 1 - 1
 - ##### N - N




------------------------------------------------


#16/03/2015



##Normalização de Dados
 - O que é?
 - O que faz?
 - Como se faz?

------------------------------------------------

###O que é? 
Estabelecer um conjunto de regras de entrada de dados.

------------------------------------------------

###O que faz?
 - Minimiza redundâncias e inconsistências; 
 - Facilita manutenção e manipulação de dados;

------------------------------------------------

###Como faz?



####Banco de Dados não normalizado

Código | Nome | Cargo | Setor | Qtd Funcionarios
-------|------|-------|-------|-----------------
1  |    Maria | Gerente| Administração | 
2  | José     | Repositor | Loja |
3  | Ana      | Tec. Informática | Manutenção | 
4  | Rui      | Repositor | Loja | 
5  | Paulo    | Progrmador | Manutenção
6  | João     |  Tecnico Info | Rede
7  | Paula    |  Repositor  | Loja




####Anomalia de exclusão
Se você exclui o Gerente, excluirá também um Setor listado no memso registro

####Anomalia de Ateração
O que acontece se o setor de redes mudar o nome para setor de T.I?

####Anomalia de Inclusão
O que acontece quando você contratar mais um pessoa para o setor Loja?


-------------------------------------------------

###Como resolver?
Utilizando uma das formas normais.



###Primeira forma normal:  1 - N ( Um pra N )
#####Procedimento
 a - Identificar a Chave Primária da Entidade
 b - Identificar o grupo repetitivo da Entidade
 c - Criar uma nova entidade com o grupo repetitivo e vinculá-lo pela chave primária e secundária 




--------------------------------------
#23/03/2015


##Exercício - 2,0 ponto

Modele uma base de dados QUALQUER com pelo menos 6 tabelas relacionais.

Enviar ao email **mauro.avare@gmail.com** até dia **30/03/2015, as 23:59**.

O que precisa ser enviado?
  . Modo estrutura das tabelas
  . Relacionamento das Entidades

Pode ser em PDF e feito no Workbench ou não.


---------------------------------------
#04/05/2015

###A linguagem SQL(Structured Query Language)
Linguagem universal para manipulação de bancos de dados relacionais.

###Vantagens
. Altamente intuitiva (Inglês Estruturado)
. Pode ser utilizada com a maioria dos SGBD

###Sintaxe Básica
** SELECT** Campo1, Campo2, Campo3
** FROM** Tablea1, Tablea2, Tablea3
** WHERE** (Condicao1 = 'x')
** AND** (Condicao2 = 'y')
** AND** (Condicao3 = 'w')
** OR** (Condicao4 = 'R')
** ORDER BY** Campo ASC/DESC
** LIMIT** 1

== ==
####Exercício
|tblcidades|
|----------|
|CidadeCodigo|
|CidadeNome|
|CidadeUF|
|CidadeCEP|


Dada a tabela estruturada acima, crie um SQL que:


a) -  Liste todas as cidades que tenham Avaré  no nome;
 ```sql
 SELECT CidadeNome FROM tblcidades WHERE CidadeNome LIKE '%avaré%' 
 ```
 
b) - Liste todas as cidades da UF 'SP'
 ```sql
 SELECT CidadeNome FROM tblcidades WHERE CidadeUF = 'SP' 
 ```
 
c) - Liste todas as cidades que começam com 'w'
 ```sql
 SELECT CidadeNome FROM tblcidades WHERE CidadeNome LIKE 'w%' 
 ```
 
d) - Liste as 5 últimas cidades em ordem alfabética
 ```sql
 SELECT CidadeNome FROM tblcidades ORDER BY CidadeNome DESC LIMIT 5 
 ```

e) - Liste o CEP de Manaus
 ```sql
 SELECT CidadeNome, CidadeCEP FROM tblcidades WHERE CidadeNome = 'Manaus' AND CidadeUF = 'AM' 
```

f) - Contar quantas cidades a UF 'PR' tem
 ```sql
 SELECT CidadeUF, COUNT(*) AS Total FROM tblcidades WHERE CidadeUF = 'PR' 
```


g) - Contar todas as cidades por UF
 ```sql
 SELECT CidadeUF, count(*) as Total FROM tblcidades GROUP BY CidadeUF ORDER BY CidadeUF ASC
```

h) - Contar quantas cidades tem na região Sudeste
 ```sql
 SELECT COUNT(*) AS Sudeste FROM tblcidades WHERE CidadeUF IN ('PR', 'SP', 'RJ', 'MG')  
```



---------------------------------------
#25/05/2015

