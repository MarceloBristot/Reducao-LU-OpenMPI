### O que é adecomposicao-LU?

   >*Decomposição LU(lower, upper) é uma forma de transformar uma matriz
   com o produto de uma matriz triangular inferior e uma matriz triangular superior.
                                                   **A = L.U**
   Onde L é uma matriz triangular inferior e U é uma matriz triangular superior,
   e exemplo abaixo representa essa definição.* 
   <br/>
   
![Exemplo](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRx8IW7enwn_rcYaN87CGYril9-S0y38_oD8oGIUIZug52fl3SR "Exemplo matriz triangular")

<br/>

**Algoritmo:**<br/>
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
   4 `./nomeArquivo` <br/>
* <br/>




   Trabalho com o OpenMPI sobre o algoritmo de decomposição LU.
   **Professor: Paulo João Martins - UNESC.**
 
 
 **UTEIS**
 **[*MARKDOWN*](https://github.com/luong-komorebi/Markdown-Tutorial/blob/master/README_pt-BR.md)**
