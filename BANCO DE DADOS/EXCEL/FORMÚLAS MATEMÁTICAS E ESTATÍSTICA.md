## SOMA

Soma todos os valores de um intervalo.

> [!info]
> Sintaxe / Fórmula
> 
> `=SOMA(A1:A10)`

Exemplo prático:

> [!example]
> =SOMA(B2:B20) → soma as vendas de B2 até B20

## MÉDIA

Calcula a média aritmética de um intervalo.

> [!info]
> Sintaxe / Fórmula
> 
> `=MÉDIA(A1:A10)`
> 

Exemplo prático

> [!example]
> =MÉDIA(C2:C30) → média das notas dos alunos

## MÁXIMO

Retorna o maior valor de um intervalo.

> [!info]
> Sintaxe / Fórmula
> 
> `=MÁXIMO(A1:A10)`
> 

Exemplo prático

> [!example]
> =MÁXIMO(E2:E100) → maior venda do mês

## MINÍMO

Retorna o menor valor de um intervalo.

> [!info]
> Sintaxe / Fórmula
> 
> `=MÍNIMO(A1:A10)`

Exemplo prático

> [!example]
> =MÍNIMO(D2:D50) → menor temperatura registrada

## ARRED

Arredonda um número para uma quantidade específica de casas decimais.

> [!info]
> Sintaxe / Fórmula
> 
> `=ARRED(número; núm_dígitos)`

Exemplo prático

> [!example]
> =ARRED(3,14159; 2) → 3,14

## ARRENDONDAR.PARA.CIMA

Arredonda sempre para cima, afastando do zero.

> [!info]
> Sintaxe / Fórmula
> 
> `=ARREDONDAR.PARA.CIMA(número; núm_dígitos)`

Exemplo prático

> [!example]
> =ARREDONDAR.PARA.CIMA(2,31; 1) → 2,4

## ARRENDONDAR.PARA.BAIXO

Arredonda sempre para baixo, em direção ao zero.

> [!important]
> Sintaxe / Fórmula
> 
> `=ARREDONDAR.PARA.BAIXO(número; núm_dígitos)`
> 

Exemplo prático

> [!example]
> =ARREDONDAR.PARA.BAIXO(2,99; 1) → 2,

## ALEATÓRIO

Gera um número aleatório entre 0 e 1.

> [!info]
> Sintaxe / Fórmula
> 
> `=ALEATÓRIO()`

Exemplo prático

> [!example]
> =ALEATÓRIO() → 0,4572 (muda a cada cálculo)

## ALEATÓRIOENTRE

Gera um número inteiro aleatório entre dois valores.

> [!info]
> Sintaxe / Fórmula
> 
> `=ALEATÓRIOENTRE(inferior; superior)`

Exemplo prático

> [!example]
> =ALEATÓRIOENTRE(1; 100) → 4

## SUBTOTAL

Aplica uma função (soma, média, etc.) ignorando linhas ocultas por filtros.

> [!info]
> Sintaxe / Fórmula
> 
> `=SUBTOTAL(núm_função; ref1)`

Exemplo prático

> [!example]
> =SUBTOTAL(9; B2:B100) → soma apenas linhas visíveis (9 = SOMA)

## AGREGAR

Similar ao SUBTOTAL, mas com mais funções e opções para ignorar erros e ocultos.

> [!info]
> Sintaxe / Fórmula
> 
> `=AGREGAR(núm_função; opções; ref)`

Exemplo prático

> [!example]
> =AGREGAR(1; 5; C2:C50) → média ignorando erros e ocultos



