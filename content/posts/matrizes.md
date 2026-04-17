+++
title = "Como usar 100% da CPU com matrizes"
date = 2026-04-16T16:50:58-05:00
draft = false
author = "Pedrinho"
tags = ["matrizes", "paralelismo", "threads", "process"]
+++

# Entendendo o problema
Nas nossas primeiras aulas de programação, sempre é dito a nós que o código é executado de cima pra baixo e da esquerda pra direita; o que é verdade, porém depende.

Na vida real, quando se usa um código que executa sequencialmente, temos um longo processo tomando tempo de processamento na CPU e devido ao gerenciamento (em termos técnicos "Escalonamento"), esse processo vai ser retirado e reinserido na execução, algo que é chamado de preempção.

Bom, depois de largar essas informações, vamos começar a tratar do objetivo deste post, onde eu vou abordar a cerca de um trabalho que realizei na primeira unidade da disciplina de Sistemas Operacionais na UFRN.

Basicamente, o nosso problema é a multiplicação de matrizes, cálculo bem conhecido, especialmente por aqueles na área de inteligência artificial.

## Mas o que tem de mais com a multiplicação de matrizes?

Vamos começar olhando o código:

```cpp
for(int i = 0; i < n1; i++){
    for(int j = 0; j < m2; j++){
        matrizC[i][j] = 0;
        for(int k = 0; k < m1; k++) {
            matrizC[i][j] += matrizA[i][k] * matrizB[k][j];
        }
    }
}
```

Veja que pra multiplicação de matrizes, usamos 3 laços `for()` para calcular cada elemento, algo que quando trabalhamos com poucos elementos, como por exemplo uma matriz de ordem 100, leva pouquíssimo tempo; considerando a nossa noção de tempo, podemos até dizer que é instantâneo.

>Agora, imagine a multiplicação de uma matriz de ordem 1000, ou 10000, ou 100000

Adicionando um pouco de matemática (pra quem é desses), a complexidade da operação de multiplicação de uma matriz pode ser representada pela fórmula:
$$
C(n) = n^3
$$
Onde n é a ordem da matriz, ou seja, seu tamanho. Também dá pra calcular o tempo que levaria pra calcular isso com matemática, mas eu ainda não cheguei lá, por isso, vamos de C++.
## Como lidar com matrizes grandes?
No caso de matrizes grandes, é possível paralelizar o trabalho, ou seja, dividir o trabalho para que ele possa ser processado simultaneamente.

Trocando em miúdos...
> Se um pedreiro constrói uma casa em 12 meses, 12 pedreiros constroem uma em 1 mês?

De forma simplória, podemos dizer que sim, mas na pratica sabemos que não é bem assim. Claro que 12 pedreiros vão construir uma casa mais rápido, porém há um limite, nem toda tarefa pode ser dividida, e nesse momento não há ganho na paralelização. Algo como:

> 9 grávidas não tem um bebê em um mês

No nosso, caso, podemos sim fatiar a matriz que vamos multiplicar e dividir ela para que sejam calculadas "ao mesmo tempo".

## Processos e Threads

