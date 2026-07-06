
## ASSOCIAÇÕES TODO-PARTE

**DEFINIÇÃO

==Uma associação todo-parte representa um relacionamento em que um conceito faz parte de outro conceito que representa um todo.==

Esse tipo de associação é utilizado para modelar estruturas compostas por partes.

Na UML, essa relação é representada por um **diamante** no lado do conceito que representa o todo.

### TIPOS DE ASSOCIAÇÕES TODO-PARTE

Existem dois tipos:

- Agregação.
- Composição.

A principal diferença entre elas está na exclusividade da parte.

---

## AGREGAÇÃO

**DEFINIÇÃO

==Agregação é uma associação todo-parte em que a parte pode existir independentemente do todo.==

Na UML, é representada por um **diamante branco**.

A parte pode pertencer a outro todo ou continuar existindo mesmo que o todo deixe de existir.

 **CARACTERÍSTICAS:

- Diamante branco.
- Relação mais fraca.
- A parte possui vida própria.
- A parte pode ser compartilhada.

> [!example]
> #### EXEMPLO
> 
> Carro ◇──── Pneu
> 
> O pneu faz parte do carro.
> 
> Porém, um pneu pode ser retirado e utilizado em outro carro.
> 
> Logo:
> 
> O pneu não depende exclusivamente daquele carro.
> 
> **OUTRO EXEMPLO
> 
> Curso ◇──── Disciplina
> 
> Uma disciplina pode fazer parte de um curso.
> 
> Dependendo da instituição, ela também pode ser utilizada em outros cursos.
> 
> Assim, a disciplina não é exclusiva de um único curso.

---

## COMPOSIÇÃO

**DEFINIÇÃO

==Composição é uma associação todo-parte em que a parte pertence exclusivamente ao todo.==

Na UML, é representada por um **diamante preto**.

A parte não pode existir separadamente nem pertencer simultaneamente a outro todo.

**CARACTERÍSTICAS

- Diamante preto.
- Relação mais forte.
- A parte depende do todo.
- A parte é exclusiva.

> [!example]
> #### EXEMPLO
> 
> Estado ◆──── Cidade
> 
> Uma cidade pertence a apenas um estado.
> 
> Ela não pode pertencer simultaneamente a dois estados.
> 
> Portanto:
> 
> Cidade é uma parte exclusiva do Estado.
> 

---

## EXCLUSIVIDADE

==Na composição, a parte pertence exclusivamente a um único todo.==

Por isso, a multiplicidade no lado do diamante sempre será:

- **1**
- **0..1**

Nunca será:

- 1..*
- 2..*

A exclusividade impede que uma parte pertença a vários objetos ao mesmo tempo.

> [!example]
> #### EXEMPLO
> 
> Estado ◆──── Cidade
> 
> Cada cidade pertence a exatamente um estado.
> 
> Ou, dependendo da regra do negócio:
> 
> Cada cidade pertence a zero ou um estado.

---

## EXEMPLOS DE AGREGAÇÃO

> [!example]
> #### Exemplo 1
> 
> Carro ◇──── Pneu
> 
> Um carro possui vários pneus.
> 
> Cada pneu pode ser substituído ou utilizado em outro carro.

> [!example]
> #### Exemplo 2
> 
> Pedido ◇──── Item
> 
> Um pedido é composto por diversos itens.
> 
> Cada item representa um produto e sua quantidade naquele pedido.
> 
> O Item faz a ligação entre:
> 
> - Pedido.
> - Produto.
> 
> Além disso, um Item pode estar associado a uma Venda.

> [!example]
> #### Exemplo 3
> 
> Curso ◇──── Disciplina
> 
> Um curso é formado por disciplinas.
> 
> Dependendo da regra de negócio, uma disciplina pode ser utilizada em diferentes cursos.

---

## QUANDO UTILIZAR AGREGAÇÃO OU COMPOSIÇÃO

Antes de utilizar um diamante, faça a pergunta:

**A parte pode existir independentemente do todo?**

Se a resposta for:

**Sim**

→ Agregação.

Se a resposta for:

**Não**

→ Composição.

---

## ATENÇÃO

==Utilize diamantes apenas quando realmente existir uma relação todo-parte.==

Nem toda associação deve ser representada por agregação ou composição.

Exemplo incorreto:

Pessoa ◇──── Carro

Uma pessoa **não é formada** por carros.

Ela apenas possui carros.

Nesse caso, deve ser utilizada apenas uma associação comum.

==O diamante preto (composição) não representa deleção em cascata.==

Muitas pessoas acreditam que composição significa:

"Quando o objeto principal é removido, todos os outros serão removidos automaticamente."

Isso não é verdade.

A exclusão em cascata é uma decisão da implementação (por exemplo, no banco de dados) e não da modelagem conceitual.

O que realmente caracteriza a composição é a **exclusividade da parte**, e não o comportamento de exclusão.

---

## COMPARAÇÃO

| Agregação                    | Composição                                     |
| ---------------------------- | ---------------------------------------------- |
| Diamante branco              | Diamante preto                                 |
| Relação fraca                | Relação forte                                  |
| Parte pode existir sozinha   | Parte depende do todo                          |
| Parte pode ser compartilhada | Parte é exclusiva                              |
| Multiplicidade livre         | Multiplicidade no lado do diamante é 1 ou 0..1 |

---

## COMO IDENTIFICAR

Pergunte:

**O objeto representa uma parte de outro objeto?**

Se não:

Use apenas uma associação comum.

Se sim:

Pergunte:

**Essa parte pode existir sem o todo?**

Se sim:

Agregação.

Se não:

Composição.

---

## RESUMO

| Conceito              | Função                                        |
| --------------------- | --------------------------------------------- |
| Associação Todo-Parte | Representa que um conceito faz parte de outro |
| Agregação             | Relação todo-parte fraca (diamante branco)    |
| Composição            | Relação todo-parte forte (diamante preto)     |
| Parte Exclusiva       | Só pode pertencer a um único todo             |
| Diamante Branco       | Representa agregação                          |
| Diamante Preto        | Representa composição                         |
| Exclusividade         | Multiplicidade 1 ou 0..1 no lado do diamante  |

==As associações todo-parte representam relações em que um conceito é parte de outro. Quando a parte pode existir independentemente do todo, utiliza-se a agregação (diamante branco). Quando a parte é exclusiva e depende do todo para existir, utiliza-se a composição (diamante preto). Esses símbolos devem ser usados apenas em verdadeiras relações todo-parte e não indicam, por si só, exclusão em cascata.==