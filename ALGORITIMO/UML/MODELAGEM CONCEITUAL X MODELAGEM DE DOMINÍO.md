## MODELAGEM CONCEITUAL

==A modelagem conceitual é uma representação abstrata de um sistema, focada na compreensão do problema e dos conceitos envolvidos no negócio.==

Seu objetivo é identificar os elementos principais do domínio e os relacionamentos existentes entre eles, sem considerar detalhes técnicos ou de implementação.

Características:

Foco no negócio.  
Independente de tecnologia.  
Não considera banco de dados.  
Não considera linguagem de programação.  
Facilita a comunicação entre usuários e desenvolvedores.

---

## MODELAGEM DE DOMÍNIO

==A modelagem de domínio representa os conceitos, entidades e regras de negócio de um sistema utilizando uma visão orientada a objetos.==

Seu objetivo é descrever como os elementos do domínio se relacionam e servir de base para o desenvolvimento do software.

Características:

Foco nas regras de negócio.  
Utiliza conceitos da orientação a objetos.  
Representa entidades do mundo real.  
Pode ser criada utilizando diagramas de classes UML.  
Serve de ponte entre a análise e a implementação.

---

## ELEMENTOS DA MODELAGEM CONCEITUAL

> [!example]
> A modelagem conceitual normalmente identifica:
> 
> Entidades.  
> Relacionamentos.  
> Regras de negócio.  
> Processos do domínio.

> [!example]
> Exemplo em uma biblioteca:
> 
> Livro.  
> Autor.  
> Usuário.  
> Empréstimo.

O objetivo é apenas entender quais conceitos existem e como eles se relacionam.

---

## ELEMENTOS DA MODELAGEM DE DOMÍNIO

Na modelagem de domínio os conceitos são detalhados em classes e atributos.

> [!example]
> Exemplo:
> 
> Classe Livro
> 
> Atributos:
> 
> titulo  
> isbn  
> anoPublicacao
> 
> Classe Usuario
> 
> Atributos:
> 
> nome  
> matricula
> 
> Classe Emprestimo
> 
> Atributos:
> 
> dataEmprestimo  
> dataDevolucao

Além dos atributos, são definidos os relacionamentos entre as classes.

> [!example]
> EXEMPLO PRÁTICO
> 
> Sistema de vendas:
> 
> ### Modelagem Conceitual
> 
> Identifica os conceitos:
> 
> Cliente.  
> Produto.  
> Pedido.  
> Pagamento.
> 
> Relacionamentos:
> 
> Cliente realiza Pedido.  
> Pedido contém Produto.  
> Pedido gera Pagamento.
> 
> ### Modelagem de Domínio
> 
> Classe Cliente
> 
> Atributos:
> 
> id  
> nome  
> email
> 
> Classe Produto
> 
> Atributos:
> 
> id  
> nome  
> preco
> 
> Classe Pedido
> 
> Atributos:
> 
> numero  
> data  
> valorTotal
> 
> Relacionamentos:
> 
> Cliente → Pedido  
> Pedido → Produto

---

## PRINCIPAL DIFERENÇA

### Modelagem Conceitual

Preocupa-se em responder:

**"O que existe no problema?"**

Exemplo:

Cliente.  
Produto.  
Pedido.

Sem detalhar atributos ou implementação.

### Modelagem de Domínio

Preocupa-se em responder:

**"Como os elementos do domínio estão organizados?"**

Exemplo:

Cliente possui nome e email.

Pedido possui data e valor.

Produto possui preço e descrição.

---

## COMPARAÇÃO

|Modelagem Conceitual|Modelagem de Domínio|
|---|---|
|Mais abstrata|Mais detalhada|
|Foco no negócio|Foco no domínio do sistema|
|Não considera implementação|Próxima da implementação|
|Identifica conceitos|Identifica classes e atributos|
|Responde "O que existe?"|Responde "Como funciona?"|
|Pode não utilizar UML|Geralmente utiliza UML|

---

## RELAÇÃO COM A UML

==A UML é amplamente utilizada na modelagem de domínio para representar classes, atributos, relacionamentos e regras de negócio.==

Os diagramas mais utilizados são:

Diagrama de Classes.  
Diagrama de Casos de Uso.  
Diagrama de Sequência.

A modelagem conceitual pode existir antes mesmo da criação dos diagramas UML.

---

## RESUMO

|Conceito|Função|
|---|---|
|Modelagem Conceitual|Identifica os conceitos do negócio|
|Modelagem de Domínio|Organiza os conceitos em classes e relacionamentos|
|Entidade|Elemento importante do domínio|
|Classe|Representação de uma entidade na UML|
|Relacionamento|Associação entre elementos|
|Regra de Negócio|Define comportamentos do sistema|

==A modelagem conceitual busca compreender o problema e identificar seus conceitos principais.==

==A modelagem de domínio detalha esses conceitos em classes, atributos e relacionamentos, servindo como base para o desenvolvimento orientado a objetos e para a criação dos diagramas UML.==