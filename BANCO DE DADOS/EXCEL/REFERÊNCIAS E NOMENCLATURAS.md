
## REFERÊNCIAS ABSOLUTAS ($A$1)

A célula não muda ao copiar a fórmula. Tanto a coluna quanto a linha são fixas.

> [!info]
> Sintaxe / Fórmula
> 
> `=$A$1`

Exemplo prático

> [!example]
> =B2*$C$1 → ao copiar, C1 sempre se refere ao mesmo lugar (ex: taxa fixa)

## REFERÊNCIAS RELATIVAS (A1)

A célula se ajusta automaticamente ao copiar a fórmula para outras células.

> [!info]
> Sintaxe / Fórmula
> 
> `=A1`

Exemplo prático

> [!example]
> =A2+B2 → ao copiar para baixo, vira A3+B3, A4+B4...

## REFERÊNCIAS MISTAS ($A1/ A$1)

Fixa apenas coluna ($A1) ou apenas linha (A$1) ao copiar a fórmula.

> [!info]
> Sintaxe / Fórmula
> 
> `=$A1 ou =A$1`

Exemplo prático

> [!example]
> =$A2*B$1 → coluna A e linha 1 são fixas, o restante se ajusta

## NOMES DEFINIDOS

Atribui um nome a um intervalo ou valor, tornando fórmulas mais legíveis.

> [!info]
> Sintaxe / Fórmula
> 
> `Guias > Fórmulas > Definir Nome`

Exemplo prático

> [!example]
> Nomeie B2:B100 como 'Vendas' → =SOMA(Vendas) em vez de =SOMA(B2:B100)