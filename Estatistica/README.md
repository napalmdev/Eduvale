##Estatística
###Professora Miriam 

------------------------------------------------
#14/05/2015

### Combinações de Evento
Se usarmos certa operações entre conjuntos(eventos), poderemos combinar eventos para formar novos conjuntos(eventos). 

a) A U B
b) A n B
c) A¢

#####Complementar de um Evento
Seja ** A** um evento, então A¢ será também um evento que ocorrerá se, e somente se, A não ocorrer. 
Dizemos que A¢ é o evento complementar de A.

** Exemplo**
U dado é lançado e observado o número da face de cima. Sejam os eventos:

**Espaço Amostral S = {1, 2, 3, 4, 5, 6}**

A: ocorrência de um nº par  **A = {2, 4, 6}**
B: ocorrência de um nº maior ou igual a 4 **A = {4, 5, 6}**
C: ocorrência de um nº ímpar. **A = {1, 3, 5}**

Então faremos:

** A U B:**  ocorrência de um nº par ou nº >= 4 **-> { 2, 4, 6}**
** A n B:**  ocorrência de um nº par e um nº >= 4 **-> { 4, 6}**
** A n C:**  ocorrência de um nº par e um impar **-> {VAZIO}**
** A¢:**  ocorrência de um nº não par **-> { 1, 3, 5}**
** B¢:**  ocorrência de um nº < que 4 **-> { 1, 2, 3}**


######Exercício
** 1)** Uma moeda e um dado são lançados ** 
S = {(k,1), (k,2), (k,3), (k,4), (k,5), (k,6), (c,1), (c,2), (c,3), (c,4), (c,5), (c,6)}**

Descreva os eventos:

**A:** ocorrência de um CARA = {(c,1), (c,2), (c,3), (c,4), (c,5), (c,6)}
**B:** ocorrência de um nº maior ou igual a 4 = { (k,4), (k,5), (k,6), (c,4), (c,5), (c,6) }
**C:** ocorência de um nº 3 = { (k,3), (c,3)}

Resolver
**A)** A U B = { (k,4), (k,5), (k,6), (c,1), (c,2), (c,3), (c,4), (c,5), (c,6)}
**B)** B n C = {VAZIO}
**C)** A¢ = { (k,1), (k,2), (k,3), (k,4), (k,5), (k,6) }
**D)** C¢ = { (k,1), (k,2), (k,4), (k,5), (k,6), (c,1), (c,2), (c,4), (c,5), (c,6) }



** 2)** Um par ordenado(a,b) é escolhido entre os 20 pares ordenados do produto cartesiano A X B, em que A = {1, 2, 3, 4} e B = {1, 2, 3, 4, 5}, considere S = { (a,b) / a C A ^ b C B}, ou seja, **(a,b)** tal que **a** esteja contido em **A**(a C A) *E* **b** esteja contido em **B**(b C B).

Descreva os eventos

**a)** A = { (x,y) / x = y} = {(1,1), (2,2), (3,3), (4,4)}  
**b)** B = { (x,y) / x > y} = { (2,1), (3,1), (3,2), (4,1), (4,2), (4,3)}
**c)** C = { (x,y) / x+y = 2} = { (1,1)}
**d)** D = { (x,y) / y = x²} = { (1,1), (2,4)}
**e)** E = { (x,y) / y = 1} = {(1,1), (2,1), (3,1), (4,1)}
**f)** E = { (x,y) / y = 3} = {(1,3), (2,3), (3,3), (4,3)}

**3)** Sejam os conjuntos A = { a, b, c, d} e B = { a, b, c, 4, 6, 8}, considere: 
S = {(a, b) / V a-C-A ^ b-C-B}     
>V maiúsculo aqui representa o A de ponta-cabeça que significa Qualquer
>Então a,b Tal que Qualquer a pertença ao conjunto A e qualquer b pertença ao conjunto B

**a)** {(a,b) / a = a+1 ^ b = 2²} = {VAZIO}
**b)** {(a,b) / a = 2(a²) ^ b = a} = {VAZIO}
**a)** {(a,b) / a = c ^ b = c} = {(c,c)}