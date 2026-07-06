## DEFINIÇÃO

==O Modelo Conceitual é um modelo que descreve a estrutura das informações que serão gerenciadas pelo sistema.==

Segundo Wazlawick:

> É um modelo que descreve a estrutura das informações que o sistema vai gerenciar.

Outra definição:

> É o Modelo de Domínio em nível de análise.

Seu objetivo é representar os elementos importantes do negócio antes de pensar em banco de dados, programação ou tecnologia.

---

## CARACTERÍSTICAS

O Modelo Conceitual:

- Pertence ao escopo do problema.
- Não pertence ao escopo da solução.
- É independente de paradigma.
- É independente de tecnologia.
- Foca nas regras e informações do negócio.

O analista deve se preocupar com:

**O que existe no negócio?**

E não com:

**Como isso será implementado?**

---

## ELEMENTOS DO MODELO CONCEITUAL

O Modelo Conceitual é formado por:

- Conceitos.
- Atributos.
- Associações.

Esses elementos representam as informações relevantes para o sistema.

---

## CONCEITOS

==Um conceito é qualquer entidade que possua significado para o negócio e necessite armazenar informações.==

Um conceito representa algo importante para o sistema.

Exemplos:

- Cliente.
- Produto.
- Pedido.
- Fornecedor.
- Funcionário.

Um conceito deve representar uma única ideia do negócio.

### Unidade Coesa

==Um conceito deve ser uma unidade coesa.==

Isso significa que ele deve representar apenas um elemento específico do domínio.

> [!example]
> Exemplo:
> 
> **Bom**
> 
> Cliente
> 
> Produto
> 
> Pedido
> 
> **Ruim**
> 
> ClientePedido
> 
> ProdutoFornecedor
> 
> Misturar responsabilidades dificulta a modelagem.
> 

---

## ATRIBUTOS

==Atributos são informações simples armazenadas em cada conceito.==

Podem representar:

- Textos.
- Números.
- Datas.
- Valores monetários.

Exemplos:

### Cliente

- nome
- email
- telefone
- cpf
- dataNascimento

### Produto

- descricao
- preco

---

## REGRAS PARA ATRIBUTOS (1FN)

A Primeira Forma Normal (1FN) estabelece algumas restrições importantes.

### Não Pode Ser Multivalorado

==Cada atributo deve armazenar apenas um valor.==

Exemplo ruim:

telefone = "21999999999, 21888888888"

O atributo possui vários valores.

Exemplo correto:

telefone

Ou criar uma entidade Telefone separada.

---

### Não Pode Ser Composto

==Um atributo não deve armazenar várias informações diferentes juntas.==

Exemplo ruim:

endereco = "Rua A, 120, Apto 301, Centro"

O atributo contém várias informações.

Exemplo correto:

logradouro

numero

complemento

bairro

cep

Cada informação possui seu próprio atributo.

---


## ESTRUTURA DE UM CONCEITO NA UML

Um conceito é representado por um retângulo dividido em três partes.

### Primeira Seção

Contém o nome do conceito.

Exemplo:

Cliente

---

### Segunda Seção

Contém os atributos.

Formato:

nome : tipo

Exemplos:

nome : String

cpf : String

dataNascimento : Date

Observação:

==O tipo do atributo é opcional no Modelo Conceitual.==

---

### Terceira Seção

Não é utilizada no Modelo Conceitual.

Ela normalmente é usada em diagramas de classes de projeto para representar métodos e operações.

**EXEMPLO COMPLETO:**

![[Captura de tela 2026-06-23 192151.png]]

---

## ATRIBUTO IDENTIFICADOR

==É o atributo responsável por identificar unicamente uma instância de um conceito.==

Exemplos:

Cliente

- cpf

Produto

- codigoProduto

Pedido

- numeroPedido

Não podem existir dois objetos com o mesmo identificador.

---

## VALOR INICIAL

==É um valor atribuído automaticamente a um atributo quando um objeto é criado.==

Exemplo:

status = "Ativo"

Todo novo cliente já inicia com o status definido.

---

## ATRIBUTO DERIVADO

==É um atributo cujo valor pode ser calculado a partir de outros atributos.==

Exemplo:

Pessoa

- dataNascimento
- idade

A idade pode ser calculada com base na data de nascimento.

Portanto:

idade é um atributo derivado.

**EXEMPLO COMPLETO

> [!example]
> Conceito:
> 
> Cliente
> 
> Atributos:
> 
> - cpf : String
> - nome : String
> - email : String
> - telefone : String
> - dataNascimento : Date
> 
> Conceito:
> 
> Produto
> 
> Atributos:
> 
> - codigo : Integer
> - descricao : String
> - preco : Decimal
> 

---

## RESUMO

|Conceito|Função|
|---|---|
|Modelo Conceitual|Descreve as informações do sistema|
|Conceito|Entidade relevante para o negócio|
|Atributo|Informação armazenada em um conceito|
|Unidade Coesa|Representa apenas uma responsabilidade|
|1FN|Evita atributos compostos e multivalorados|
|Atributo Identificador|Identifica unicamente uma instância|
|Valor Inicial|Valor atribuído automaticamente|
|Atributo Derivado|Valor calculado a partir de outros atributos|
|Diagrama de Classes UML|Ferramenta utilizada para representar o modelo|

==O Modelo Conceitual descreve os conceitos, atributos e associações do negócio, focando no problema a ser resolvido e não na tecnologia que será utilizada para implementar a solução.==