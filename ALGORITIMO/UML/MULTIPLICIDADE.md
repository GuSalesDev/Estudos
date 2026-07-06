
## O QUE É MULTIPLICIDADE?

==Multiplicidade é a quantidade mínima e máxima de objetos que uma associação permite em cada um de seus papéis.==

Ela define quantas instâncias de um conceito podem estar relacionadas com instâncias de outro conceito.

A multiplicidade sempre informa:

- Quantidade mínima.
- Quantidade máxima.

> [!example]
>  **EXEMPLO:**
> 
> Considere a associação:
> 
> Pessoa ---------- dono ---------- Carro
> 
> Pergunta:
> 
> **Um carro pode ter quantos donos?**
> 
> Resposta:
> 
> Mínimo: **1**
> 
> Máximo: **1**
> 
> Ou seja, todo carro deve possuir exatamente um dono.
> 

## COMO ENCONTRAR A MULTIPLICIDADE

==A maneira mais simples é fazer uma pergunta para cada lado da associação, sempre iniciando com "1".==

Pergunta padrão:

**1 {conceito} pode ter quantos {papéis}?**

Sempre analise um lado de cada vez.

> [!example]
> **EXEMPLO**
> 
> Associação:
> 
> Pessoa -------- dono -------- Carro
> 
> Primeira pergunta:
> 
> **1 carro pode ter quantos donos?**
> 
> Resposta:
> 
> Exatamente **1**
> 
> Multiplicidade:
> 
> 1

> [!example]
> **EXEMPLO**
> 
> Segunda pergunta:
> 
> **1 pessoa pode ter quantos carros?**
> 
> Resposta:
> 
> Zero ou vários.
> 
> Multiplicidade:
> 
> 0..*
> 
> Resultado:
> 
> Pessoa **1** -------- **0..*** Carro

---

## COMO LER UMA MULTIPLICIDADE

A multiplicidade é sempre lida do lado oposto.

Exemplo:

```
Pessoa 1 -------- 0..* Carro
```

Significa:

Um **carro** possui exatamente **1 pessoa** como dona.

Uma **pessoa** pode possuir **zero ou vários carros**.

## SÍMBOLOS UTILIZADOS

### Vírgula (,)

==Significa "ou".==

Exemplo:

2,5

Lê-se:

Dois **ou** cinco.

### Dois Pontos (..)

==Significa "até".==

Exemplo:

2..5

Lê-se:

De dois até cinco.

### Asterisco (*)

==Representa uma quantidade indefinida de objetos (vários).==

Não existe limite máximo especificado.

## MULTIPLICIDADES POSSÍVEIS

|Multiplicidade|Significado|
|---|---|
|1|Exatamente um|
|2|Exatamente dois|
|0..1|Zero ou um|
|0..*|Zero ou mais|
|*|Zero ou mais|
|1..*|Um ou mais|
|2..*|Dois ou mais|
|2..5|De dois a cinco|
|2,5|Dois ou cinco|
|2,5..8|Dois ou cinco até oito|

---

## ASSOCIAÇÕES MAIS COMUNS

### UM PARA MUITOS (1:N)

==Uma instância de um conceito pode estar associada a várias instâncias do outro conceito, mas cada uma dessas instâncias pertence a apenas uma do primeiro conceito.==

> [!example]
> **Exemplo:**
> 
> Pessoa -------- Carro
> 
> Perguntas:
> 
> **1 carro pode ter quantos donos?**
> 
> Resposta:
> 
> 1
> 
> **1 pessoa pode ter quantos carros?**
> 
> Resposta:
> 
> 0..*
> 
> Representação:
> 
> ```
> Pessoa 1 -------- 0..* Carro
> ```

> [!example]
> Exemplo:
> 
> Greg → 1 carro
> 
> Martha → 2 carros
> 
> John → nenhum carro
> 

---

### UM PARA UM (1:1)

==Cada instância de um conceito pode estar associada a, no máximo, uma instância do outro conceito.==

> [!example]
> Exemplo:
> 
> Pessoa -------- Responsável -------- Carro
> 
> Perguntas:
> 
> **1 carro pode ter quantos responsáveis?**
> 
> Resposta:
> 
> 1
> 
> **1 pessoa pode ser responsável por quantos carros?**
> 
> Resposta:
> 
> 0..1
> 
> Representação:
> 
> ```
> Pessoa 1 -------- 0..1 Carro
> ```

Nesse relacionamento, ambos os lados possuem no máximo uma associação.

---

### MUITOS PARA MUITOS (N:N)

==Várias instâncias de um conceito podem estar associadas a várias instâncias do outro conceito.==

> [!example]
> Exemplo:
> 
> Pessoa -------- Motorista -------- Carro
> 
> Perguntas:
> 
> **1 carro pode ter quantos motoristas?**
> 
> Resposta:
> 
> 1..*
> 
> **1 pessoa pode dirigir quantos carros?**
> 
> Resposta:
> 
> 0..*
> 
> Representação:
> 
> ```
> Pessoa 1..* -------- 0..* Carro
> ```

---

## RESUMO

|Conceito|Função|
|---|---|
|Multiplicidade|Define a quantidade mínima e máxima de objetos em uma associação|
|Quantidade Mínima|Número mínimo permitido de associações|
|Quantidade Máxima|Número máximo permitido de associações|
|1|Exatamente um|
|0..1|Zero ou um|
|0..*|Zero ou mais|
|1..*|Um ou mais|

- | Vários (sem limite específico)  
    1:N | Um para muitos  
    1:1 | Um para um  
    N:N | Muitos para muitos

==A multiplicidade especifica quantas instâncias de um conceito podem estar associadas a instâncias de outro conceito. Para determiná-la, basta perguntar, para cada lado da associação: "1 conceito pode ter quantos papéis?". Essa análise permite modelar corretamente as regras de negócio do sistema e identificar relacionamentos do tipo um para um, um para muitos ou muitos para muitos.==