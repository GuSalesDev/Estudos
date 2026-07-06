
## CONCAT

Une dois ou mais textos em um só (versão moderna).

> [!info]
> Sintaxe / Fórmula
> 
> `=CONCAT(texto1; texto2; ...)`

Exemplo prático

> [!example]
> =CONCAT(A2; " "; B2) → "João Silva"

## CONCATENAR

Une dois ou mais textos (versão antiga, substituída por CONCAT).

> [!info]
> Sintaxe / Fórmula
> 
> `=CONCATENAR(texto1; texto2; ...)`

Exemplo prático

> [!example]
> =CONCATENAR("Olá, "; A1; "!") → "Olá, Maria!"

## TEXTO

Formata um número como texto com máscara de formatação.

> [!info]
> Sintaxe / Fórmula
> 
> `=TEXTO(valor; formato)`
> 

Exemplo prático

> [!example]
> =TEXTO(1234,5; "R$ #.##0,00") → "R$ 1.234,50"

## ESQUERDA

Extrai caracteres do início (esquerda) de um texto.

> [!info]
> Sintaxe / Fórmula
> 
> `=ESQUERDA(texto; [núm_caract])`

Exemplo prático

> [!example]
> =ESQUERDA("Excel 2024"; 5) → "Excel"

## DIREITA

Extrai caracteres do final (direita) de um texto.

> [!info]
> Sintaxe / Fórmula
> 
> `=DIREITA(texto; [núm_caract])`

Exemplo prático

> [!example]
> =DIREITA("Código-001"; 3) → "001"

## EXT.TEXTO

Extrai um número específico de caracteres a partir de uma posição no texto.

> [!info]
> Sintaxe / Fórmula
> 
> `=EXT.TEXTO(texto; núm_inicial; núm_caract)`

Exemplo prático

> [!example]
> =EXT.TEXTO("SP-12345"; 4; 5) → "12345"

## LOCALIZAR

Encontra a posição de um texto dentro de outro (não diferencia maiúsculas).

> [!info]
> Sintaxe / Fórmula
> 
> `=LOCALIZAR(texto_procurado; no_texto; [núm_inicial])`

Exemplo prático

> [!example]
> =LOCALIZAR("@"; "joao@email.com") → 5

## SUBSTITUIR

Substitui uma parte do texto por outro texto.

> [!info]
> Sintaxe / Fórmula
> 
> `=SUBSTITUIR(texto; texto_antigo; novo_texto; [núm_ocorrência])`

Exemplo prático

> [!example]
> =SUBSTITUIR("01/01/2024"; "/"; "-") → "01-01-2024"

## ARRUMAR

Remove espaços extras do texto, deixando apenas um espaço entre palavras.

> [!info]
> Sintaxe / Fórmula
> 
> `=ARRUMAR(texto)`
> 

Exemplo prático

> [!example]
> =ARRUMAR(" João Silva ") → "João Silva"

## MAIÚSCULA

Converte todo o texto para letras maiúsculas.

> [!info]
> Sintaxe / Fórmula
> 
> `=MAIÚSCULA(texto)`

Exemplo prático

> [!example]
> =MAIÚSCULA("excel") → "EXCEL"

## MINÚSCULA

Converte todo o texto para letras minúsculas.

> [!info]
> Sintaxe / Fórmula
> 
> `=MINÚSCULA(texto)`

Exemplo prático

> [!example]
> =MINÚSCULA("EXCEL") → "excel"

## PRI.MAIÚSCULA

Coloca a primeira letra de cada palavra em maiúscula.

> [!info]
> Sintaxe / Fórmula
> 
> `=PRI.MAIÚSCULA(texto)`

Exemplo prático

> [!example]
> =PRI.MAIÚSCULA("joão da silva") → "João Da Silva"

## NÚM.CARACT

Retorna o número de caracteres de um texto.

> [!info]
> Sintaxe / Fórmula
> 
> `=NÚM.CARACT(texto)`

Exemplo prático

> [!example]
> =NÚM.CARACT("Excel") → 5

## VALOR

Converte um texto que representa número em um número real.

> [!info]
> Sintaxe / Fórmula
> 
> `=VALOR(texto)`
> 

Exemplo prático

> [!example]
> =VALOR("1234,56") → 1234,56 (número)