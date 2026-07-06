## VIEWS

==Uma **View** é uma tabela virtual criada a partir do resultado de uma consulta SQL.==

Ela não armazena os dados fisicamente (na maioria dos casos), apenas a consulta que será executada quando a View for utilizada.

As Views são utilizadas para:

- Simplificar consultas complexas.
- Ocultar detalhes das tabelas.
- Restringir acesso a determinadas colunas.
- Reutilizar consultas frequentemente utilizadas.
- Facilitar relatórios.

Sintaxe básica:

```
CREATE VIEW nome_view ASSELECT colunasFROM tabela;
```

Exemplo:

```
CREATE VIEW vw_clientes ASSELECT ID_Cliente, Nome, EmailFROM Clientes;
```

Após criar a View:

```
SELECT *FROM vw_clientes;
```

A View se comporta como uma tabela.

> [!example]  
> Exemplo prático
> 
> Tabela Clientes:
> 
> |ID_Cliente|Nome|Email|Senha|
> |---|---|---|---|
> |1|João|joao@email.com|123|
> |2|Maria|maria@email.com|456|
> 
> Criando uma View:
> 
> ```
> CREATE VIEW vw_clientes ASSELECT ID_Cliente,       Nome,       EmailFROM Clientes;
> ```
> 
> Consulta:
> 
> ```
> SELECT *FROM vw_clientes;
> ```
> 
> Resultado:
> 
> |ID_Cliente|Nome|Email|
> |---|---|---|
> |1|João|joao@email.com|
> |2|Maria|maria@email.com|
> 
> A coluna Senha não será exibida.

COMO FUNCIONA:

Quando uma consulta é executada:

```
SELECT *FROM vw_clientes;
```

O banco executa automaticamente:

```
SELECT ID_Cliente,       Nome,       EmailFROM Clientes;
```

A View funciona como um atalho para uma consulta.

Ela não duplica os dados da tabela original.

---

## CRIANDO UMA VIEW COM JOIN

Uma das utilizações mais comuns de Views é encapsular consultas com JOIN.

Exemplo:

```
CREATE VIEW vw_pedidos_clientes ASSELECT    C.Nome,    P.Produto,    P.ValorFROM Clientes CJOIN Pedidos PON C.ID_Cliente = P.ID_Cliente;
```

Consulta:

```
SELECT *FROM vw_pedidos_clientes;
```

Assim, não é necessário escrever o JOIN toda vez que a informação for utilizada.

---

## ALTERANDO UMA VIEW

Para modificar uma View existente:

```
CREATE OR REPLACE VIEW vw_clientes ASSELECT Nome,       EmailFROM Clientes;
```

O comando substitui a definição anterior da View.

Também é possível removê-la:

```
DROP VIEW vw_clientes;
```

A remoção da View não afeta as tabelas originais.

---

## SEGURANÇA COM VIEWS

As Views podem ser utilizadas para ocultar informações sensíveis.

Exemplo:

Tabela original:

|Nome|Salario|CPF|
|---|---|---|
|João|5000|11111111111|

View:

```
CREATE VIEW vw_funcionarios ASSELECT Nome,       SalarioFROM Funcionarios;
```

Consulta:

```
SELECT *FROM vw_funcionarios;
```

Resultado:

|Nome|Salario|
|---|---|
|João|5000|

O CPF permanece protegido.

---

## VIEWS ATUALIZÁVEIS

Algumas Views permitem operações de:

- INSERT
- UPDATE
- DELETE

Exemplo:

```
UPDATE vw_clientesSET Nome = 'Carlos'WHERE ID_Cliente = 1;
```

O banco atualizará a tabela original.

Porém, Views que utilizam:

- JOIN
- GROUP BY
- DISTINCT
- Funções de agregação

geralmente não são atualizáveis.

---

## RESUMO

|Comando|Função|
|---|---|
|CREATE VIEW|Cria uma View|
|CREATE OR REPLACE VIEW|Cria ou substitui uma View|
|SELECT|Consulta a View|
|DROP VIEW|Remove uma View|

==Uma View é uma tabela virtual baseada em uma consulta SQL armazenada no banco de dados.==

==Ela é utilizada para simplificar consultas, reutilizar lógica SQL, aumentar a segurança e facilitar a manutenção de sistemas e relatórios.==