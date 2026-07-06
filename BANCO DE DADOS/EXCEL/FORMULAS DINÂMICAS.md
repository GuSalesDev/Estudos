
## FILTRO

Filtra um intervalo com base em condições e derrama os resultados automaticamente.

> [!info]
> Sintaxe / Fórmula
> 
> `=FILTRO(matriz; incluir; [se_vazio])`

Exemplo prático

> [!example]
> =FILTRO(A2:C50; B2:B50="SP") → retorna todas as linhas onde B é "SP"

## CLASSIFICAR

Ordena os valores de um intervalo ou matriz.

> [!info]
> Sintaxe / Fórmula
> 
> `=CLASSIFICAR(matriz; [índice_classificação]; [ordem]; [por_coluna])`

Exemplo prático

> [!example]
> =CLASSIFICAR(A2:B50; 2; -1) → ordena pela 2ª coluna em ordem decrescente

## ÚNICO

Retorna uma lista de valores únicos (sem duplicatas) de um intervalo.

> [!info]
> Sintaxe / Fórmula
> 
> `=ÚNICO(matriz; [por_coluna]; [exatamente_uma_vez])`

Exemplo prático

> [!example]
> =ÚNICO(A2:A100) → lista de nomes sem repetição

## TRANSPOR

Converte linhas em colunas e vice-versa.

> [!info]
> Sintaxe / Fórmula
> 
> `=TRANSPOR(matriz)`

Exemplo prático

> [!example]
> =TRANSPOR(A1:E1) → converte linha horizontal em coluna vertical

## HIPERLINK

Cria um link clicável para uma URL ou local dentro da planilha.

> [!info]
> Sintaxe / Fórmula
> 
> `=HIPERLINK(local_link; [nome_amigável])`

Exemplo prático

> [!example]
> =HIPERLINK("https://google.com"; "Abrir Google")
