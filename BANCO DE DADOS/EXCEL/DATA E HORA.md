
## HOJE

Retorna a data atual. Atualiza automaticamente a cada abertura.

> [!info]
> Sintaxe / Fórmula
> 
> `=HOJE()`

Exemplo prático

> [!example]
> =HOJE() → 24/05/2026

## AGORA

Retorna a data e hora atual.

> [!info]
> Sintaxe / Fórmula
> 
> `=AGORA()`

Exemplo prático

> [!example]
> =AGORA() → 24/05/2026 14:35

## DATA

Cria uma data a partir de ano, mês e dia.

> [!info]
> Sintaxe / Fórmula
> 
> `=DATA(ano; mês; dia)`

Exemplo prático

> [!example]
> =DATA(2026; 12; 31) → 31/12/2026

## DIA

Extrai o dia de uma data.

> [!info]
> Sintaxe / Fórmula
> 
> `=DIA(data)`

Exemplo prático

> [!example]
> =DIA(A1) → se A1 = 24/05/2026, retorna 24

## MÊS

Extrai o mês de uma data.

> [!info]
> Sintaxe / Fórmula
> 
> `=MÊS(data)`
> 

Exemplo prático

> [!example]
> =MÊS(A1) → se A1 = 24/05/2026, retorna 5

## ANO

Extrai o ano de uma data.

> [!info]
> Sintaxe / Fórmula
> 
> `=ANO(data)`

Exemplo prático

> [!example]
> =ANO(A1) → se A1 = 24/05/2026, retorna 2026

## DIATRABALHO

Retorna uma data que está N dias úteis após (ou antes de) uma data inicial.

> [!info]
> Sintaxe / Fórmula
> 
> `=DIATRABALHO(data_inicial; dias; [feriados])`

Exemplo prático

> [!example]
> =DIATRABALHO(HOJE(); 10) → data 10 dias úteis a partir de hoje

## FIMMÊS

Retorna o último dia do mês, N meses a partir de uma data.

> [!info]
> Sintaxe / Fórmula
> 
> `=FIMMÊS(data_inicial; meses)`

Exemplo prático

> [!example]
> =FIMMÊS(HOJE(); 0) → último dia do mês atual