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
-----|------------------------------------------------|
CidadeCodigo | int | - | Não | Sim | Sim |   
CidadeNome | VarChar | 50 | Não | Não | Não | 
CidadeUF | VarChar | 2 | Não | Não | Não | 
CidadeIBGE | int | | Sim | Não | Não | 
CidadeCEP | VarChar | 8 | Não | Não | Não | 
CidadeTimeStamp | TimeStamp | | Não | Não | Não | 








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

