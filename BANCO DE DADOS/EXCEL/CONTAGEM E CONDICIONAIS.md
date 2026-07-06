
## CONT.SE

Conta células que atendem a um critério específico.

> [!info]
> Sintaxe / Fórmula
> 
> `=CONT.SE(intervalo; critério)`

Exemplo prático

> [!example]
> =CONT.SE(A2:A50; "Aprovado") → quantos alunos foram aprovados

## CONT.VALORES

Conta células não vazias em um intervalo.

> [!info]
> Sintaxe / Fórmula
> 
> `=CONT.VALORES(valor1; [valor2]; ...)`

Exemplo prático

> [!example]
> =CONT.VALORES(A1:A100) → total de células preenchidas

## CONT.SES

Conta células que atendem a múltiplos critérios simultaneamente.

> [!info]
> Sintaxe / Fórmula
> 
> `=CONT.SES(intervalo1; critério1; intervalo2; critério2)`

Exemplo prático

> [!example]
> =CONT.SES(B2:B50; "SP"; C2:C50; ">1000") → vendas em SP acima de 1000

## SE

Retorna um valor se a condição for verdadeira e outro se for falsa.

> [!info]
> Sintaxe / Fórmula
> 
> `=SE(teste_lógico; valor_se_verdadeiro; valor_se_falso)`

Exemplo prático

> [!example]
> =SE(B2>=7; "Aprovado"; "Reprovado")

## SES

Testa múltiplas condições em sequência, retornando o valor da primeira verdadeira.


> [!info]
> Sintaxe / Fórmula
> 
> `=SES(cond1; val1; cond2; val2; ...)`

Exemplo prático

> [!example]
> =SES(A1>=9;"Ótimo"; A1>=7;"Bom"; A1>=5;"Regular"; VERDADEIRO;"Ruim")

## E

Retorna VERDADEIRO se todas as condições forem verdadeiras.

> [!info]
> Sintaxe / Fórmula
> 
> `=E(lógico1; lógico2; ...)`

Exemplo prático

> [!example]
> =E(A1>5; B1="SP") → VERDADEIRO somente se ambas forem verdadeiras

## OU

Retorna VERDADEIRO se ao menos uma condição for verdadeira.

> [!info]
> Sintaxe / Fórmula
> 
> `=OU(lógico1; lógico2; ...)`

Exemplo prático

> [!example]
> =OU(A1="RJ"; A1="SP") → VERDADEIRO se for RJ ou SP
## NÃO

Inverte um valor lógico: VERDADEIRO vira FALSO e vice-versa.

> [!info]
> Sintaxe / Fórmula
> 
> `=NÃO(lógico)`
> 

Exemplo prático

> [!example]
> =NÃO(A1="Cancelado") → VERDADEIRO se NÃO for cancelado
## SEERRO

Retorna um valor alternativo se a fórmula resultar em erro.

> [!info]
> Sintaxe / Fórmula
> 
> `=SEERRO(valor; valor_se_erro)`

Exemplo prático

> [!example]
> =SEERRO(PROCV(A1;B:C;2;0); "Não encontrado")



## SOMASE

Soma células que atendem a um critério.

> [!info]
> Sintaxe / Fórmula
> 
> `=SOMASE(intervalo; critério; intervalo_soma)`

Exemplo prático

> [!example]
> =SOMASE(A2:A50; "Norte"; B2:B50) → soma vendas da região Norte

## SOMASES

Soma células que atendem a múltiplos critérios.

> [!info]
> Sintaxe / Fórmula
> 
> `=SOMASES(intervalo_soma; intervalo1; critério1; ...)`

Exemplo prático

> [!example]
> =SOMASES(C2:C50; A2:A50; "SP"; B2:B50; "Jan")

## MÉDIASE

Calcula a média de células que atendem a um critério.

> [!info]
> Sintaxe / Fórmula
> 
> `=MÉDIASE(intervalo; critério; [intervalo_média])`

Exemplo prático

> [!example]
> =MÉDIASE(A2:A50; "Vendedor A"; B2:B50)

## MÉDIASES

Calcula a média de células que atendem a múltiplos critérios.

> [!info]
> Sintaxe / Fórmula
> 
> `=MÉDIASES(intervalo_média; intervalo1; critério1; ...)`

Exemplo prático

> [!example]
> =MÉDIASES(D2:D50; B2:B50; "SP"; C2:C50; ">500")


