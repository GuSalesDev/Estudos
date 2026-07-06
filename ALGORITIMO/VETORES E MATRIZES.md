
## VETOR

Um **vetor** é uma lista de elementos do mesmo tipo, organizados em sequência.

por exemplo:

[10, 20, 30, 40, 50]

Cada valor tem uma posição (índice):

Índice:   0   1   2   3   4
Valores: 10  20  30  40  50

em java:

```
int[] numeros = {10, 20, 30, 40, 50};

System.out.println(numeros[2]); 
```


## MATRIZ

Uma **matriz** é basicamente um conjunto de vetores.

por exemplo:

[ [1, 2, 3],
  [4, 5, 6],
  [7, 8, 9] ]

Aqui você acessa usando dois índices:

- linha
- coluna

em java:

```
int[][] matriz = {
    {1, 2, 3},
    {4, 5, 6},
    {7, 8, 9}
};

// acessando um valor
System.out.println(matriz[1][2]); // 6
```

Características:

- Estrutura em linhas e colunas
- Também tem tamanho fixo
- Muito usada para tabelas, jogos, grids, etc.

## DIFERENÇA

|Conceito|Vetor|Matriz|
|---|---|---|
|Dimensão|1D|2D|
|Estrutura|Contígua|Array de arrays|
|Índices|1|2|
|Flexibilidade|Baixa|Alta|
|Uso comum|listas|tabelas, grids|


### Vetores

- Lista de usuários
- Dados de entrada
- APIs (JSON vira lista)
- Algoritmos (ordenar, buscar)

### Matrizes

- Jogos (mapa 2D)
- Sistemas de assentos (cinema, avião)
- Planilhas
- Imagens (pixels = matriz)








