### O que é adecomposicao-LU?

   >*Decomposição LU(lower, upper) é uma forma de transformar uma matriz
   com o produto de uma matriz triangular inferior e uma matriz triangular superior.
                                                   **A = L.U**
   Onde L é uma matriz triangular inferior e U é uma matriz triangular superior,
   e exemplo abaixo representa essa definição.* 
   <br/>
   
![Exemplo](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRx8IW7enwn_rcYaN87CGYril9-S0y38_oD8oGIUIZug52fl3SR "Exemplo matriz triangular")

<br/>

**Algoritmo:**
`PARA K = 1 ATÉ N-1
          PARA I = K+1 ATÉ N
                 L[I][K] = M[I][K] / M[K][K]
                 PARA J = K + 1 ATÉ  N
                              M[I][J] = M[I][J] - L[I][K] * M[K][J]`


   Trabalho com o OpenMPI sobre o algoritmo de decomposição LU.
   **Professor: Paulo João Martins - UNESC.**
 
