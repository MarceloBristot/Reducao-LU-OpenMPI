# Redução-LU com OpenMPI
<br/>

Este trabalho fala sobre o algoritmo de decomposição LU.

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
 
 **Possivel Algoritmo em C**
 ```
int k, n, i;
int L[0][0], M[0][0];

for(K=1; k<=n-1; k++){
   for(i=k+1; i<=n; k++){
      L[i][k] = M[i][k] / M[k][k];
    }
   for(j=k+1; j<=n; j++){
      M[i][j] = M[i][j] * M[K][J];
    }
}
```


   Trabalho com o OpenMPI sobre o algoritmo de decomposição LU.
   **Professor: Paulo João Martins - UNESC.**
 
 
 **UTEIS** <br/>
 **[*MARKDOWN*](https://github.com/luong-komorebi/Markdown-Tutorial/blob/master/README_pt-BR.md)** <br/>
  **[*Decomposição-LU*](https://docs.google.com/viewer?a=v&pid=sites&srcid=ZGVmYXVsdGRvbWFpbnxwcGFyYWxlbGEyOHxneDo0M2JmZjQ3ZDE0YmQ3MjI5)**

