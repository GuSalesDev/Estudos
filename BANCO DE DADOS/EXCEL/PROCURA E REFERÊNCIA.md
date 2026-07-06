## PROCV

Procura um valor na primeira coluna de uma tabela e retorna um valor da mesma linha em outra coluna.

> [!info]
> Sintaxe / Fórmula
> 
> `=PROCV(valor_procurado; matriz_tabela; núm_índice_coluna; [procurar_intervalo])`

Exemplo prático

> [!example]
> =PROCV(101; A2:D50; 3; 0) → busca o código 101 e retorna o valor da 3ª coluna

## PROCH

Igual ao PROCV, mas procura horizontalmente (na primeira linha).

> [!info]
> Sintaxe / Fórmula
> 
> `=PROCH(valor_procurado; matriz_tabela; núm_índice_lin; [procurar_intervalo])`

Exemplo prático

> [!example]
> =PROCH("Jan"; A1:M2; 2; 0) → retorna o valor abaixo de Jan

## PROCX

Versão moderna e mais poderosa do PROCV/PROCH. Procura em qualquer direção.

> [!info]
> Sintaxe / Fórmula
> 
> `=PROCX(valor; matriz_proc; matriz_retorno; [se_não_encontrado])`

Exemplo prático

> [!example]
> =PROCX(A2; B2:B100; C2:C100; "Não encontrado")

## ÍNDICE

Retorna o valor de uma célula em uma posição específica de um intervalo.

> [!info]
> Sintaxe / Fórmula
> 
> `=ÍNDICE(matriz; núm_linha; [núm_coluna])`

Exemplo prático

> [!example]
> =ÍNDICE(A1:D10; 3; 2) → retorna o valor na 3ª linha e 2ª coluna

## CORESP

Retorna a posição relativa de um valor dentro de um intervalo.

> [!info]
> Sintaxe / Fórmula
> 
> `=CORRESP(valor_procurado; matriz_procurada; [tipo_correspondência])`

Exemplo prático

> [!example]
> =CORRESP("Banana"; A1:A20; 0) → posição de "Banana" no intervalo

## DESLOC

Retorna uma referência deslocada a partir de uma célula base por linhas e colunas.

> [!info]
> Sintaxe / Fórmula
> 
> `=DESLOC(ref; lins; cols; [altura]; [largura])`

Exemplo prático

> [!example]
> =DESLOC(A1; 2; 3) → valor 2 linhas abaixo e 3 colunas à direita de A1

## INDIRETO

Retorna a referência de uma célula especificada por um texto.

> [!info]
> Sintaxe / Fórmula
> 
> `=INDIRETO(ref_texto; [a1])`
> 

Exemplo prático

> [!example]
> =INDIRETO("B"&A1) → se A1=5, retorna o valor de B5
