# Redução-LU com OpenMPI
<br/>

   Este trabalho fala sobre a redução LU.
   Inicialmente para enterder a redução LU, precisamos falar sobre a decomposição LU.

*******

### O que é a decomposicao-LU?

   >*Decomposição LU(lower, upper) é uma forma de transformar uma matriz
   com o produto de uma matriz triangular inferior e uma matriz triangular superior.
                                                   **A = L.U**
   Onde L é uma matriz triangular inferior e U é uma matriz triangular superior,
   o exemplo abaixo representa essa definição.* 
   <br/>
   
![Exemplo](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRx8IW7enwn_rcYaN87CGYril9-S0y38_oD8oGIUIZug52fl3SR "Exemplo matriz triangular")
<br/>


**Algoritmo:**<br/>

>*A decomposição LU é basicamente uma modificação do método de eliminação de
Gauss. A matriz é transformada em uma matriz triangular superior, eliminando os
valores abaixo da diagonal principal. O algoritmo elimina coluna por coluna, a partir da
esquerda.* 
   <br/>

`PARA K = 1 ATÉ N-1` <br/>
          `PARA I = K+1 ATÉ N` <br/>
                 `L[I][K] = M[I][K] / M[K][K]` <br/>
                 `PARA J = K + 1 ATÉ  N` <br/>
                              `M[I][J] = M[I][J] - L[I][K] * M[K][J]` <br/>
                              

**Como instalar o OpenMPI no Ubuntu**<br/>
>* Abra o terminal e digite o seguinte comando:<br/>
   `sudo apt install gcc-multilib`<br/>
   Para compilar um arquivo (.c)  use estes comandos no terminal: <br/>
   1 `touch nomeArquivo.c,` <br/>
   2 `nano nomeArquivo.c (aqui é onde fica o algoritmo),` <br/>
   3 `gcc nomeArquivo.c -o nomeArquivo -fopenmp` <br/>
   4 `./nomeArquivo`. <br/>
 <br/>                                                      
                              
**Cálculo de Determinante**
>*A decomposição LU pode ser usada para o cálculo de determinante, pois
det(A) = det(L)*det(U), como o determinantes de matrizes triangulares são
simplesmente a multiplicação de sua diagonal principal, a operação é realizada de forma eficiente.*<br/>

**Redução LU**
>*Redução LU é um algoritmo paralelo relacionado à decomposição LU, em geral a
versão paralela distribui a eliminação de cada linha da matriz. A expressão é usada em
geral no contexto de supercomputação.*<br/>

**Estratégias de Paralelização e Limitações**
* Particionamento
>*O algoritmo mostrado anteriormente demonstra a utilização de três loops. Deste modo, deve-se
diagnosticar o problema tendo em mente em qual destes
loops haverá um particionamento para paralelização do programa. Tendo
conhecimento do funcionamento do algoritmo, pode-se perceber que o loop mais
externo não pode ser paralelizado, isso deve-se
ao fato de que, para calcular-se o coeficiente da próxima coluna(k+1), é necessário que
a coluna k já tenha sido eliminada. O segundo e terceiro loop podem naturalmente ser
paralelizados, visto que não existe uma dependência entre as repetições dentro deles mesmos.*

* Mapeamento
>*A abordagem de mapeamento utilizada foi dividir de forma igualitária a carga
de processamento entre as threads disponíveis, já que as partes segmentadas
possuem homogeneidade em relação ao custo computacional.*

* Estrátegia adotada
>*Após analisar sobre a implementação do algoritmo, surgiu a ideia de ao invés
de utilizar três (3) loops, fosse utilizado somente dois (2) loops, fazendo com que o
programa possa ser segmentado em um maior número partes. A seguir segue a implementação final.*

![Algoritmo Redução LU](https://i.imgur.com/p74scc7.png)


**Resultados** <br/>
1- Redução LU OmpSCR vs Redução LU[2] Sequencial.<br/>
![N = 100](https://image.prntscr.com/image/POYkKGG6Rq2xMIfQKuctxA.png) <br/>
![N = 1000](https://image.prntscr.com/image/jPiKz1sdT2Wp09D2ZSZq-Q.png) <br/>

2- Redução LU OMPSCR - Velocidade(speedup) e eficiência.<br/>
![N = 100](https://image.prntscr.com/image/t_ejhIrYTx2WfTgP_oS6Qg.png) <br/>
![N = 2000](https://image.prntscr.com/image/88fFKQUuQH2bFVdxkOomMQ.png) <br/>

3- Redução LU[2] Sequencial - Velocidade(speedup) e eficiência. <br/>
![N = 100](https://image.prntscr.com/image/dP6VhTigSm2YzJ_EgKF3UA.png) <br/>
![N = 1000](https://image.prntscr.com/image/SzFUQwPRRzSb-ML3OwJJmg.png) <br/>
![N = 2000](https://image.prntscr.com/image/nEMPnxqESyupzEwroTmdAA.png) <br/>


**Conclusão**
>*Conclui-se a idéia apresentada demonstrou desempenho baixo mas é válida a medida em que
pode ser mais segmentada. Ela é uma boa alternativa para aumentar 
o desempenho se considerarmos o uso de clusters.*
 
 **Professor: Paulo João Martins - UNESC 2019.**
 
 **Referências** <br/>
 **[*Markdown*](https://github.com/luong-komorebi/Markdown-Tutorial/blob/master/README_pt-BR.md)** <br/>
 **[*Redução-LU*](https://docs.google.com/viewer?a=v&pid=sites&srcid=ZGVmYXVsdGRvbWFpbnxwcGFyYWxlbGEyOHxneDo0M2JmZjQ3ZDE0YmQ3MjI5)**
 
 
 **Variáveis de Ambiente em processamento paralelo**
 >*A variável de ambiente que indica o número de atividade que serpa executada é definida como ```Construção PARALLEL``` *
 
  
