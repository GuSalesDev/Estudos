## SUBQUERY

==Uma **Subquery** (ou Subconsulta) é uma consulta SQL que fica dentro de outra consulta SQL.==

Ela é utilizada quando o resultado de uma consulta precisa ser utilizado por outra consulta.

Em outras palavras, a subquery executa primeiro e seu resultado é utilizado pela consulta principal.

O que uma Subquery pode fazer?

- Filtrar dados com base em outra consulta.
- Comparar valores.
- Buscar informações relacionadas.
- Realizar cálculos intermediários.
- Tornar consultas mais flexíveis.

Sintaxe básica

```
SELECT coluna
FROM tabela
WHERE coluna = (    
	SELECT coluna    
	FROM outra_tabela);
```

A consulta interna é executada primeiro.

O resultado é utilizado pela consulta externa.

> [!example]  
> Exemplo prático
> 
> Considere a tabela Funcionarios:
> 
> |ID|Nome|Salario|
> |---|---|---|
> |1|João|3000|
> |2|Maria|5000|
> |3|Pedro|4000|
> 
> Consulta:
> 
> ```
> SELECT Nome, Salario
> FROM Funcionarios
> WHERE Salario = (    
> 	SELECT MAX(Salario)    
> 	FROM Funcionarios);
> ```
> 
> Resultado:
> 
> |Nome|Salario|
> |---|---|
> |Maria|5000|
> 
> Primeiro a subquery encontra o maior salário.
> 
> Depois a consulta principal retorna o funcionário correspondente.

---

## TIPOS DE SUBQUERY

## Subquery Escalar

==Retorna apenas um único valor.==

Exemplo:

```
SELECT Nome
FROM Funcionarios
WHERE Salario > (    
	SELECT AVG(Salario)    
	FROM Funcionarios);
```

A subquery retorna a média salarial.

A consulta principal retorna os funcionários acima da média.

---

## Subquery com IN

==Retorna vários valores.==

Exemplo:

```
SELECT Nome
FROM Clientes
WHERE ID_Cliente IN (    
	SELECT ID_Cliente    
	FROM Pedidos);
```

Retorna clientes que possuem pedidos cadastrados.

---

## Subquery com EXISTS

==Verifica se a subquery retorna algum registro.==

Exemplo:

```
SELECT Nome
FROM Clientes C
WHERE EXISTS (    
	SELECT *    
	FROM Pedidos P    
	WHERE 
	P.ID_Cliente = C.ID_Cliente);
```

Retorna apenas clientes que possuem pedidos.

---

## Subquery no FROM

==A subquery pode funcionar como uma tabela temporária.==

Exemplo:

```
SELECT *
FROM (    
	SELECT Nome, Salario    
	FROM Funcionarios) AS Dados;
```

Nesse caso, o resultado da subquery é tratado como uma tabela chamada `Dados`.

---

## Subquery no SELECT

==A subquery também pode aparecer dentro da lista de colunas.==

Exemplo:

```
SELECT Nome,(    
	SELECT AVG(Salario)    
	FROM Funcionarios) AS MediaSalarial
FROM Funcionarios;
```

A média salarial será exibida em todas as linhas.

---

## SUBQUERY X JOIN

Muitas consultas feitas com Subquery também podem ser feitas com JOIN.

Exemplo com Subquery:

```
SELECT Nome
FROM Clientes
WHERE ID_Cliente IN (    
	SELECT ID_Cliente    
	FROM Pedidos);
```

Exemplo equivalente com JOIN:

```
SELECT DISTINCT C.Nome
FROM Clientes C
JOIN Pedidos P
ON C.ID_Cliente = P.ID_Cliente;
```

---

## VANTAGENS

- Fácil de entender.
- Boa para consultas complexas.
- Permite dividir problemas em etapas.
- Pode aumentar a legibilidade da consulta.

---

## DESVANTAGENS

- Pode ser mais lenta que um JOIN.
- Consultas muito aninhadas ficam difíceis de manter.
- Em grandes volumes de dados, JOINs costumam apresentar melhor desempenho.

---

## QUANDO UTILIZAR

- Comparar registros com médias ou totais.
- Encontrar maiores ou menores valores.
- Filtrar resultados com base em outra consulta.
- Verificar existência de registros relacionados.
- Criar consultas mais organizadas.

Exemplos comuns:

```
SELECT *FROM ProdutosWHERE Preco > (    SELECT AVG(Preco)    FROM Produtos);
```

```
SELECT *FROM FuncionariosWHERE Salario = (    SELECT MAX(Salario)    FROM Funcionarios);
```

```
SELECT *FROM ClientesWHERE ID_Cliente IN (    SELECT ID_Cliente    FROM Pedidos);
```

---

## RESUMO

|Tipo|Descrição|
|---|---|
|Escalar|Retorna um único valor|
|IN|Retorna vários valores|
|EXISTS|Verifica existência|
|FROM|Cria tabela temporária|
|SELECT|Retorna valor dentro da consulta|

==Uma Subquery é uma consulta dentro de outra consulta, utilizada para fornecer dados intermediários que serão usados pela consulta principal.==

==Ela é uma ferramenta extremamente poderosa para resolver problemas complexos de forma organizada, sendo muito utilizada em conjunto com SELECT, WHERE, IN, EXISTS e funções de agregação.==