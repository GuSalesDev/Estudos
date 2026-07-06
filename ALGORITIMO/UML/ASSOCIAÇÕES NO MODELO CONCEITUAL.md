
## INSTÂNCIAS (OBJETOS)

==Uma instância (ou objeto) é uma ocorrência específica de um conceito no mundo real.==

Enquanto um conceito representa uma categoria, uma instância representa um elemento real pertencente a essa categoria.

### Exemplo:

![[Pasted image 20260625185111.png]]

---

## CONCEITO × INSTÂNCIA

É importante distinguir conceito de instância.

### Conceito

Representa um tipo de objeto.

Exemplos:

- Pessoa
- Carro
- Produto
- Cliente

### Instância

Representa um objeto específico daquele conceito.

Exemplos:

Pessoa

- Greg
- John
- Martha

Carro

- Fox 2015
- Van Plus 2017
- Cross Hatch 2014

---

## O QUE É UMA ASSOCIAÇÃO?

==Uma associação é um relacionamento estático entre dois conceitos.==

Ela representa uma ligação existente entre objetos do mundo real.

A associação responde perguntas como:

- Quem comprou este produto?
- Qual cliente realizou este pedido?
- Quem é dono deste carro?
- Qual professor ministra esta disciplina?

### EXEMPLO:

Deseja-se desenvolver um sistema para armazenar informações sobre:

- Pessoas
- Carros
- 
Saber apenas quais pessoas existem e quais carros existem não é suficiente.

Também é necessário responder:

**Quem é o dono de cada carro?**

Essa informação é representada por uma associação.

### EXEMPLO NO MUNDO REAL:

![[Captura de tela 2026-06-25 185930.png]]

A associação conecta objetos pertencentes a conceitos diferentes.

**1- NOME DA ASSOCIAÇÃO

Uma associação pode possuir um nome que descreve seu significado.

Exemplo:

```
Pessoa -------- Tem -------- Carro
```

Neste exemplo:

A Pessoa **tem** um Carro.

O nome da associação deve representar uma ação ou relação existente entre os conceitos.

Exemplos:

- possui
- realiza
- compra
- contém
- trabalhaEm
- ministra
- pertence

**2- PAPEL

==O papel descreve a função que um conceito exerce dentro da associação.==

No exemplo:

```
Pessoa -------- Tem -------- Carro            dono
```

O papel da Pessoa é:

**dono**

Ou seja,

A Pessoa exerce o papel de dona do Carro.

Outro exemplo:

Professor -------- ministra -------- Disciplina

Papel:

Professor → docente

Disciplina → disciplina ministrada

**3- MULTIPLICIDADE

==A multiplicidade indica quantas instâncias de um conceito podem estar associadas a outro conceito.==

Ela responde perguntas como:

- Uma pessoa pode possuir quantos carros?
- Um carro pode possuir quantos donos?

A multiplicidade é representada nas extremidades da associação.

Exemplos comuns:

1

0..1

1..*

0..*

 **4- ASSOCIAÇÕES EXISTEM ENTRE OBJETOS

Uma associação liga objetos.

Exemplo:

```
Pessoa (Greg)        │        │        ▼Carro (Fox)
```

No modelo conceitual, entretanto, representamos essa ligação entre os **conceitos**, e não entre todas as instâncias individualmente.

NÃO TRANSFORME ASSOCIAÇÕES EM ATRIBUTOS

==Relacionamentos entre conceitos devem ser representados por associações, e não por atributos.==

---

## RESUMO

|Conceito|Função|
|---|---|
|Instância (Objeto)|Ocorrência real de um conceito|
|Associação|Relacionamento entre dois conceitos|
|Nome da Associação|Descreve o relacionamento|
|Papel|Função exercida por um conceito na associação|
|Multiplicidade|Quantidade de objetos que podem participar da associação|
|Linha de Associação|Representa o relacionamento entre conceitos|
|Objeto|Instância específica de um conceito|

==As associações representam os relacionamentos existentes entre conceitos do domínio, permitindo modelar como os objetos do mundo real se conectam. No Modelo Conceitual, esses relacionamentos são representados por associações, e não por atributos ou chaves estrangeiras, mantendo o foco no problema e não na implementação.==

## ASSOCIAÇÃO OBRIGATÓRIA

==Uma associação é obrigatória quando o conceito associado desempenha um papel cuja multiplicidade mínima é maior que zero.==

Isso significa que um objeto só pode existir se estiver obrigatoriamente associado a outro objeto.

Em outras palavras:

**A quantidade mínima da multiplicidade deve ser maior que zero.**

> [!example]
> **EXEMPLO**
> 
> Considere a associação:
> 
> ```
> Pessoa -------- dono -------- Carro
> ```
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
> Logo:
> 
> Todo carro obrigatoriamente precisa possuir um dono.

Agora faça a pergunta do outro lado:

> [!example]
> **Uma pessoa pode possuir quantos carros?**
> 
> Resposta:
> 
> Mínimo: **0**
> 
> Máximo: **vários**
> 
> Uma pessoa pode existir sem possuir um carro.
> 
> Portanto:
> 
> - Pessoa → associação não obrigatória.
> - Carro → associação obrigatória.
> 

---

## COMO IDENTIFICAR UMA ASSOCIAÇÃO OBRIGATÓRIA

Basta observar a multiplicidade mínima.

Se:

Mínimo > 0

A associação é obrigatória.

Se:

Mínimo = 0

A associação é opcional.

**ATENÇÃO

==Não confunda associação obrigatória com regras temporárias do negócio.==

Exemplo:

Um pedido normalmente deve possuir um pagamento.

Porém, um pedido pode existir temporariamente antes do pagamento ser realizado.

Nesse caso:

O pagamento faz parte da regra de negócio.

Mas isso **não significa automaticamente** que exista uma associação obrigatória no modelo conceitual.

A associação obrigatória depende exclusivamente da multiplicidade mínima.

## CONCEITO DEPENDENTE

==Um conceito é dependente quando possui pelo menos uma associação obrigatória.==

Isso significa que ele depende da existência de outro conceito para existir.

> [!example]
> **EXEMPLO**
> 
> Modelo:
> 
> ```
> Pessoa -------- dono -------- Carro
> ```
> 
> Pessoa
> 
> Pode existir sozinha.
> 
> Carro
> 
> Só pode existir se existir uma Pessoa proprietária.
> 
> Logo:
> 
> Pessoa → conceito independente.
> 
> Carro → conceito dependente.

**CARACTERÍSTICAS

Um conceito dependente:

- Possui pelo menos uma associação obrigatória.
- Não pode existir sozinho.
- Depende da existência de outro conceito.

Se o conceito do qual depende deixar de existir, o conceito dependente também deixa de existir.

> [!example]
> **EXEMPLO PRÁTICO**
> 
> Sistema de veículos
> 
> Pessoa
> 
> ↓
> 
> Carro
> 
> Se a Pessoa deixar de existir no sistema, o Carro também deixa de existir, pois não existe carro sem proprietário.

---

## ASSOCIAÇÕES MÚLTIPLAS

==Associações múltiplas ocorrem quando existem dois ou mais relacionamentos diferentes entre os mesmos conceitos.==

Não existe nenhuma restrição impedindo isso.

> [!example]
> **EXEMPLO**
> 
> Entre Pessoa e Carro podem existir várias associações.
> 
> Pessoa -------- dono -------- Carro
> 
> Pessoa -------- responsável -------- Carro
> 
> Pessoa -------- motorista -------- Carro
> 
> Cada associação representa um relacionamento diferente.

**REGRA IMPORTANTE**

==Os nomes dos papéis devem ser únicos.==

Não é permitido utilizar dois papéis iguais entre os mesmos conceitos.

Exemplo correto:

- dono
- responsável
- motorista

Cada papel representa uma função diferente.

---

## AUTOASSOCIAÇÃO

==Uma autoassociação ocorre quando um conceito está associado a ele mesmo.==

Nesse caso, a associação liga objetos pertencentes ao mesmo conceito.

> [!example]
> **EXEMPLO**
> 
> Sistema de rede social
> 
> Conceito:
> 
> Usuário
> 
> Perguntas:
> 
> **1 usuário pode ter quantos seguidores?**
> 
> **1 usuário pode seguir quantos usuários?**
> 
> Observe que o conceito continua sendo o mesmo.
> 
> Apenas os papéis mudam.

> [!example]
> **OUTROS EXEMPLOS**
> 
> Funcionário supervisiona Funcionário.
> 
> Pessoa é amiga de Pessoa.
> 
> Professor orienta Professor.
> 
> Categoria possui Subcategoria.
> 
> Todos representam autoassociações.

---

## DIAGRAMA DE OBJETOS DA UML

==O Diagrama de Objetos representa instâncias reais dos conceitos definidos no Diagrama de Classes.==

Enquanto o Diagrama de Classes representa os conceitos, o Diagrama de Objetos mostra objetos específicos existentes em determinado momento.

**OBJETIVO

O Diagrama de Objetos serve para visualizar exemplos reais do modelo conceitual.

Ele mostra:

- Objetos.
- Valores dos atributos.
- Ligações entre objetos.

> [!example]
> **EXEMPLO**
> 
> Conceito:
> 
> Pessoa
> 
> Objeto:
> 
> Greg
> 
> Conceito:
> 
> Carro
> 
> Objeto:
> 
> Fox 2015
> 
> No Diagrama de Objetos, representamos:
> 
> ```
> 2031 : Greg
> ```
> 
> Relacionado com
> 
> ```
> 1001 : Fox 2015
> ```
> 
> Cada objeto possui seus próprios valores.

**POR QUE UTILIZAR?

==Visualizar instâncias ajuda a compreender melhor o modelo conceitual.==

Além disso, facilita identificar erros antes da implementação.

Benefícios:

- Facilita o entendimento.
- Valida regras de negócio.
- Descobre inconsistências.
- Facilita a comunicação com clientes.

---

## DIFERENÇA ENTRE DIAGRAMA DE CLASSES E DIAGRAMA DE OBJETOS

|Diagrama de Classes|Diagrama de Objetos|
|---|---|
|Representa conceitos|Representa objetos reais|
|Mostra classes|Mostra instâncias|
|Define atributos|Mostra valores dos atributos|
|Define associações|Mostra ligações reais entre objetos|
|É um modelo abstrato|É uma fotografia do sistema em um determinado momento|

**RESUMO**

|Conceito|Função|
|---|---|
|Associação Obrigatória|Associação cuja multiplicidade mínima é maior que zero|
|Associação Opcional|Associação cuja multiplicidade mínima é zero|
|Conceito Dependente|Só existe se outro conceito existir|
|Conceito Independente|Pode existir sozinho|
|Associações Múltiplas|Vários relacionamentos entre os mesmos conceitos|
|Autoassociação|Associação de um conceito com ele mesmo|
|Diagrama de Objetos|Representa instâncias reais dos conceitos|
|Objeto (Instância)|Ocorrência específica de um conceito|

==Uma associação obrigatória ocorre quando a multiplicidade mínima é maior que zero, tornando um conceito dependente da existência de outro. Um mesmo par de conceitos pode possuir múltiplas associações, desde que cada papel tenha um nome único. Quando um conceito se relaciona consigo mesmo, temos uma autoassociação. Para visualizar essas relações em situações reais, utiliza-se o Diagrama de Objetos da UML, que representa instâncias concretas dos conceitos definidos no Modelo Conceitual.==