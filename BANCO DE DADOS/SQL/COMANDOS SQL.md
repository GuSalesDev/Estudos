
## USE

==O comando **USE** é utilizado para selecionar qual banco de dados será utilizado durante a sessão atual.==

Após executar esse comando, todos os comandos SQL serão executados dentro do banco escolhido.

Sintaxe básica

```
USE nome_do_banco;
```

> [!example]  
> Exemplo prático
> 
> Suponha que exista um banco de dados chamado:
> 
> ```
> SistemaVendas
> ```
> 
> Para utilizá-lo:
> 
> ```
> USE SistemaVendas;
> ```
> 
> A partir desse momento, todas as consultas e comandos serão executados nesse banco.

Informações importantes

**Finalidade**

O comando USE permite:

- Selecionar o banco ativo.
- Alternar entre diferentes bancos de dados.
- Evitar a necessidade de informar o banco em cada consulta.

Exemplo:

```
USE Empresa;SELECT * FROM Funcionarios;
```

Sem o comando USE, pode ser necessário informar o banco explicitamente:

```
SELECT *FROM Empresa.Funcionarios;
```

**Troca de banco**

É possível mudar para outro banco a qualquer momento:

```
USE LojaVirtual;
```

Depois:

```
USE RecursosHumanos;
```

Cada comando altera o banco atualmente selecionado.

Quando utilizar o USE

- Ao iniciar uma sessão no banco de dados.
- Ao trabalhar com múltiplos bancos.
- Antes de criar tabelas.
- Antes de executar consultas e operações.

==O comando USE não cria nem modifica bancos de dados. Sua única função é definir qual banco será utilizado durante a sessão atual.==

==Selecionar corretamente o banco de dados com USE é uma das primeiras etapas antes de executar qualquer comando SQL.==
## SELECT

==O comando **SELECT** é utilizado para consultar e visualizar dados armazenados em tabelas de um banco de dados.==

Ele é um dos comandos mais utilizados da linguagem SQL, pois permite recuperar informações específicas de uma ou mais tabelas.

O que o comando SELECT pode fazer?

- Consultar todos os registros de uma tabela.
- Consultar colunas específicas.
- Filtrar dados.
- Ordenar resultados.
- Realizar cálculos.
- Combinar informações de múltiplas tabelas.

Sintaxe básica: 

```
SELECT coluna1, coluna2FROM tabela;
```

Para exibir todas as colunas:

```
SELECT * FROM tabela;
```

> [!example]  
> Exemplo prático
> 
> Considere a tabela Clientes:
> 
> |ID|Nome|Cidade|
> |---|---|---|
> |1|João|Rio de Janeiro|
> |2|Maria|São Paulo|
> 
> Para visualizar todos os registros:
> 
> ```
> SELECT * FROM Clientes;
> ```

Informações importantes

**Selecionando colunas específicas**

É possível exibir apenas os dados desejados.

Exemplo:

```
SELECT Nome, Cidade 
FROM Clientes;
```

Resultado:

|Nome|Cidade|
|---|---|
|João|Rio de Janeiro|
|Maria|São Paulo|

**Utilizando filtros**

O comando SELECT pode ser combinado com o `WHERE`.

Exemplo:

```
SELECT * 
FROM Clientes
WHERE Cidade = 'Rio de Janeiro';
```

**Ordenando resultados**

Exemplo:

```
SELECT *
FROM Clientes
ORDER BY Nome;
```

==O SELECT apenas consulta os dados. Ele não altera, remove ou adiciona informações ao banco de dados.==

Quando utilizar o SELECT

- Consultar registros.
- Gerar relatórios.
- Buscar informações específicas.
- Validar dados armazenados.
- Realizar análises.

==Praticamente toda interação com um banco de dados envolve o uso do comando SELECT.==

## ORDER BY

==O comando **ORDER BY** é utilizado para ordenar os resultados retornados por uma consulta SQL.==

Ele permite organizar os dados em ordem crescente ou decrescente com base em uma ou mais colunas.

O que o comando ORDER BY pode fazer?

- Ordenar registros em ordem crescente.
- Ordenar registros em ordem decrescente.
- Ordenar por uma ou mais colunas.
- Melhorar a visualização dos resultados.
- Facilitar análises e relatórios.

Sintaxe básica

```
SELECT coluna1, coluna2FROM tabelaORDER BY coluna;
```

Ordem crescente (padrão):

```
SELECT *FROM tabelaORDER BY coluna;
```

Ordem decrescente:

```
SELECT *FROM tabelaORDER BY coluna DESC;
```

> [!example]  
> Exemplo prático
> 
> Considere a tabela Clientes:
> 
> |ID|Nome|Idade|
> |---|---|---|
> |3|Pedro|30|
> |1|João|22|
> |2|Maria|25|
> 
> Para ordenar pelo nome:
> 
> ```
> SELECT *FROM ClientesORDER BY Nome;
> ```
> 
> Resultado:
> 
> |ID|Nome|Idade|
> |---|---|---|
> |1|João|22|
> |2|Maria|25|
> |3|Pedro|30|

Informações importantes

**Ordem Crescente (ASC)**

A palavra-chave `ASC` significa **Ascending (Crescente)**.

Exemplo:

```
SELECT *FROM ClientesORDER BY Idade ASC;
```

Resultado:

|Nome|Idade|
|---|---|
|João|22|
|Maria|25|
|Pedro|30|

Como `ASC` é o padrão do SQL, ele pode ser omitido.

---

**Ordem Decrescente (DESC)**

A palavra-chave `DESC` significa **Descending (Decrescente)**.

Exemplo:

```
SELECT *FROM ClientesORDER BY Idade DESC;
```

Resultado:

|Nome|Idade|
|---|---|
|Pedro|30|
|Maria|25|
|João|22|

---

**Ordenando por múltiplas colunas**

É possível ordenar por mais de uma coluna.

Exemplo:

```
SELECT *FROM ClientesORDER BY Cidade ASC, Nome ASC;
```

Nesse caso:

1. Os registros serão organizados pela cidade.
2. Em caso de empate, serão organizados pelo nome.

---

**Ordenando valores numéricos**

Exemplo:

```
SELECT *FROM ProdutosORDER BY Preco DESC;
```

Os produtos mais caros aparecerão primeiro.

---

**Ordenando datas**

Exemplo:

```
SELECT *FROM PedidosORDER BY DataPedido DESC;
```

Os pedidos mais recentes serão exibidos primeiro.

Quando utilizar o ORDER BY

- Organizar relatórios.
- Exibir dados em ordem alfabética.
- Exibir valores do maior para o menor.
- Exibir valores do menor para o maior.
- Ordenar datas cronologicamente.

==O ORDER BY é aplicado após a seleção dos dados e antes da exibição do resultado ao usuário.==

==A utilização do ORDER BY torna as consultas mais organizadas, facilitando a leitura, análise e interpretação das informações armazenadas no banco de dados.==

## WHERE

==O comando **WHERE** é utilizado para filtrar registros em uma consulta SQL, retornando apenas os dados que atendem a uma condição específica.==

Ele é frequentemente utilizado em conjunto com o comando `SELECT`, mas também pode ser usado com `UPDATE`, `DELETE` e outros comandos SQL.

O que o comando WHERE pode fazer?

- Filtrar registros específicos.
- Comparar valores.
- Combinar múltiplas condições.
- Buscar informações precisas.
- Reduzir a quantidade de dados retornados.

Sintaxe básica

```
SELECT coluna1, coluna2FROM tabelaWHERE condição;
```

Exemplo:

```
SELECT *FROM ClientesWHERE Cidade = 'Rio de Janeiro';
```

> [!example]  
> Exemplo prático
> 
> Considere a tabela Clientes:
> 
> |ID|Nome|Cidade|
> |---|---|---|
> |1|João|Rio de Janeiro|
> |2|Maria|São Paulo|
> |3|Pedro|Rio de Janeiro|
> 
> Para visualizar apenas os clientes do Rio de Janeiro:
> 
> ```
> SELECT *FROM ClientesWHERE Cidade = 'Rio de Janeiro';
> ```
> 
> Resultado:
> 
> |ID|Nome|Cidade|
> |---|---|---|
> |1|João|Rio de Janeiro|
> |3|Pedro|Rio de Janeiro|

Informações importantes

**Operadores de comparação**

Os operadores mais utilizados com o WHERE são:

|Operador|Significado|
|---|---|
|=|Igual|
|<> ou !=|Diferente|
|>|Maior que|
|<|Menor que|
|>=|Maior ou igual|
|<=|Menor ou igual|

Exemplo:

```
SELECT *
FROM ProdutosWHERE Preco > 100;
```

---

**Utilizando AND**

O operador `AND` exige que todas as condições sejam verdadeiras.

Exemplo:

```
SELECT *
FROM Clientes
WHERE Cidade = 'Rio de Janeiro' AND Idade >= 18;
```

---

**Utilizando OR**

O operador `OR` exige que pelo menos uma condição seja verdadeira.

Exemplo:

```
SELECT *
FROM Clientes
WHERE Cidade = 'Rio de Janeiro'
OR Cidade = 'São Paulo';
```

---

**Utilizando NOT**

O operador `NOT` inverte uma condição.

Exemplo:

```
SELECT *
FROM Clientes
WHERE NOT Cidade = 'Rio de Janeiro';
```

---
**Utilizando IN*

O operador `IN` procura uma condição dentro da lista

Exemplo:

```
SELECT *
FROM Clients
WHERE CIDADE ('Rio de Janeiro', 'São Paulo', 'Santa Catarina');
```

---
**Utilizando BETWEEN

O operador `BETWEEN` seleciona valores entre um e outro.

Exemplo:

```
SELECT *
FROM Clients
WHERE Idade BETWEEN 18 AND 24
```

---
**Utilizando LIKE

O operador `LIKE` permite encontrar dados que contenham, comecem ou terminem com determinados caracteres.

Exemplo:

```
SELECT *
FROM Clientes
WHERE Primeiro_Nome LIKE 'A%'
```

Serão filtrados apenas os nomes que começam com a letra A no primeiro nome. Para ser ao contrário apenas inverta a condição para o lado esquerdo.

---
**Utilizando IS NULL

O Operador `IS NULL` é utilizado para filtrar dados que contenham um valor nulo

Exemplo:
```
SELECT *
FROM Clientes
WHERE Endereço IS NULL
```

Retornara aqueles que estão com os endereços não forma preenchidos.

---
**Filtrando textos**

Exemplo:

```
SELECT *
FROM Clientes
WHERE Nome = 'João';
```

---

**Filtrando números**

Exemplo:

```
SELECT *
FROM Produtos
WHERE Estoque <= 10;
```

---

**Filtrando datas**

Exemplo:

```
SELECT *
FROM Pedidos
WHERE DataPedido = '2026-06-17';
```

Quando utilizar o WHERE

- Buscar registros específicos.
- Criar relatórios filtrados.
- Encontrar produtos, clientes ou pedidos.
- Atualizar registros específicos.
- Excluir registros específicos.

==O WHERE é responsável por determinar quais registros serão considerados em uma operação SQL.==

==Sem o WHERE, comandos como SELECT, UPDATE e DELETE podem afetar todos os registros da tabela, tornando seu uso fundamental para consultas precisas e seguras.

## LIMIT

==O comando **LIMIT** é utilizado para restringir a quantidade de registros retornados por uma consulta SQL.==

Ele é muito útil quando uma tabela possui muitos registros e deseja-se visualizar apenas uma parte dos resultados.

O que o comando LIMIT pode fazer?

- Limitar a quantidade de registros exibidos.
- Melhorar o desempenho de consultas.
- Facilitar a paginação de resultados.
- Exibir apenas os primeiros registros encontrados.

Sintaxe básica

```
SELECT *
FROM tabela
LIMIT quantidade;
```

Exemplo:

```
SELECT *
FROM Clientes
LIMIT 5;
```

A consulta retornará apenas os 5 primeiros registros da tabela.

> [!example]  
> Exemplo prático
> 
> Considere a tabela Clientes:
> 
> |ID|Nome|
> |---|---|
> |1|João|
> |2|Maria|
> |3|Pedro|
> |4|Ana|
> |5|Lucas|
> |6|Carla|
> 
> Consulta:
> 
> ```
> SELECT *
> FROM Clientes
> LIMIT 3;
> ```
> 
> Resultado:
> 
> |ID|Nome|
> |---|---|
> |1|João|
> |2|Maria|
> |3|Pedro|

Informações importantes

**Limitando a quantidade de registros**

Exemplo:

```
SELECT *
FROM Produtos
LIMIT 10;
```

A consulta exibirá apenas os 10 primeiros produtos.

---

**Utilizando LIMIT com ORDER BY**

Uma prática muito comum é combinar `LIMIT` com `ORDER BY`.

Exemplo:

```
SELECT *
FROM Produtos
ORDER BY Preco 
DESC
LIMIT 5;
```

Resultado:

- Os produtos serão ordenados do mais caro para o mais barato.
- Apenas os 5 primeiros serão exibidos.

---

**Utilizando OFFSET**

O LIMIT pode ser combinado com um deslocamento (offset).

Sintaxe:

```
SELECT *
FROM tabela
LIMIT inicio, quantidade;
```

Exemplo:

```
SELECT *
FROM Clientes
LIMIT 5, 3;
```

Resultado:

- Ignora os 5 primeiros registros.
- Exibe os próximos 3 registros.

---

**Paginação de resultados**

Exemplo:

Primeira página:

```
SELECT *
FROM Clientes
LIMIT 10;
```

Segunda página:

```
SELECT *
FROM Clientes
LIMIT 10, 10;
```

Terceira página:

```
SELECT *
FROM Clientes

LIMIT 20, 10;
```

Essa técnica é amplamente utilizada em sistemas web.

Quando utilizar o LIMIT

- Exibir poucos registros.
- Testar consultas.
- Criar sistemas com paginação.
- Melhorar a visualização de tabelas grandes.
- Obter os primeiros ou últimos registros de uma consulta.

==O LIMIT não altera os dados da tabela. Ele apenas restringe a quantidade de registros exibidos no resultado da consulta.==

==O uso combinado de ORDER BY e LIMIT é uma das formas mais comuns de obter rankings, listas dos maiores valores, produtos mais vendidos ou registros mais recentes em um banco de dados.==

## REGEXP

==O operador **REGEXP** é utilizado para realizar buscas utilizando expressões regulares (Regular Expressions) em consultas SQL.==

Ele permite encontrar padrões específicos dentro de textos, oferecendo uma forma de pesquisa mais avançada do que operadores como `LIKE`.

O que o operador REGEXP pode fazer?

- Procurar padrões em textos.
- Validar formatos.
- Buscar palavras específicas.
- Encontrar números ou letras em posições determinadas.
- Realizar pesquisas complexas.

Sintaxe básica

```
SELECT *
FROM tabela
WHERE coluna 
REGEXP 'padrao';
```

Exemplo:

```
SELECT *
FROM Clientes
WHERE Nome 
REGEXP '^J';
```

A consulta retornará todos os nomes que começam com a letra **J**.

> [!example]  
> Exemplo prático
> 
> Considere a tabela Clientes:
> 
> |ID|Nome|
> |---|---|
> |1|João|
> |2|Maria|
> |3|José|
> |4|Pedro|
> 
> Consulta:
> 
> ```
> SELECT *FROM ClientesWHERE Nome REGEXP '^J';
> ```
> 
> Resultado:
> 
> |ID|Nome|
> |---|---|
> |1|João|
> |3|José|

Informações importantes

**Símbolo ^ (início do texto)**

O símbolo `^` indica que a busca deve começar no início da string.

Exemplo:

```
SELECT *
FROM Clientes
WHERE Nome 
REGEXP '^M';
```

Retorna todos os nomes que começam com "M".

---

**Símbolo $ (fim do texto)**

O símbolo `$` indica o final da string.

Exemplo:

```
SELECT *
FROM Clientes
WHERE Nome 
REGEXP 'o$';
```

Retorna nomes que terminam com a letra "o".

---

**Ponto (.)**

O ponto representa qualquer caractere.

Exemplo:

```
SELECT *
FROM Clientes
WHERE Nome 
REGEXP 'J....';
```

Retorna nomes iniciados por "J" seguidos de quatro caracteres.

---

**Colchetes []**

Permitem definir um conjunto de caracteres aceitos.

Exemplo:

```
SELECT *
FROM Clientes
WHERE Nome 
REGEXP '^[JM]';
```

Retorna nomes iniciados por:

- J
- M

---

**Intervalos**

Exemplo:

```
SELECT *
FROM Clientes
WHERE Nome 
REGEXP '^[A-Z]';
```

Retorna registros iniciados por qualquer letra maiúscula.

---

**Operador | (OU)**

Permite procurar múltiplos padrões.

Exemplo:

```
SELECT *
FROM Clientes
WHERE Nome 
REGEXP 'João|Maria';
```

Retorna registros contendo:

- João
- Maria

---

**Buscando números**

Exemplo:

```
SELECT *
FROM Produtos
WHERE Codigo 
REGEXP '[0-9]';
```

Retorna registros que possuem números.

---

**Buscando apenas números**

Exemplo:

```
SELECT *
FROM Produtos
WHERE Codigo 
REGEXP '^[0-9]+$';
```

Retorna registros formados exclusivamente por números.

---

**Diferença entre LIKE e REGEXP**

|LIKE|REGEXP|
|---|---|
|Busca simples|Busca avançada|
|Usa `%` e `_`|Usa expressões regulares|
|Menor flexibilidade|Maior flexibilidade|
|Mais fácil de utilizar|Mais poderoso|

Exemplo com LIKE:

```
SELECT *
FROM Clientes
WHERE Nome 
LIKE 'J%';
```

Exemplo equivalente com REGEXP:

```
SELECT *
FROM Clientes
WHERE Nome 
REGEXP '^J';
```

Quando utilizar o REGEXP

- Validar formatos de texto.
- Procurar padrões complexos.
- Filtrar códigos e identificadores.
- Pesquisar nomes específicos.
- Realizar validações avançadas.

==O REGEXP permite pesquisas muito mais sofisticadas do que o operador LIKE, sendo uma ferramenta poderosa para filtragem de dados textuais.==

==Sempre que for necessário encontrar padrões específicos dentro de uma coluna de texto, o REGEXP pode ser uma excelente solução.==

## INNER JOIN

==O comando **INNER JOIN** é utilizado para combinar dados de duas ou mais tabelas com base em uma condição de relacionamento.==

Ele retorna apenas os registros que possuem correspondência em ambas as tabelas.

O que o INNER JOIN pode fazer?

- Relacionar tabelas.
- Combinar informações de diferentes fontes.
- Exibir dados relacionados.
- Evitar duplicação de informações.
- Facilitar consultas complexas.

Sintaxe básica

```
SELECT colunas
FROM tabela1
INNER JOIN tabela2 ON tabela1.coluna = tabela2.coluna;
```

> [!example]  
> Exemplo prático
> 
> Tabela Clientes:
> 
> |ID_Cliente|Nome|
> |---|---|
> |1|João|
> |2|Maria|
> 
> Tabela Pedidos:
> 
> |ID_Pedido|ID_Cliente|Produto|
> |---|---|---|
> |101|1|Notebook|
> |102|2|Mouse|
> |103|1|Teclado|
> 
> Consulta:
> 
> ```
> SELECT Clientes.Nome, Pedidos.Produto
> FROM Clientes
> INNER JOIN Pedidos ON Clientes.ID_Cliente = Pedidos.ID_Cliente;
> ```
> 
> Resultado:
> 
> |Nome|Produto|
> |---|---|
> |João|Notebook|
> |Maria|Mouse|
> |João|Teclado|

Informações importantes

**Cláusula ON**

A cláusula `ON` define a condição de relacionamento entre as tabelas.

Exemplo:

```
ON Clientes.ID_Cliente = Pedidos.ID_Cliente
```

---

**Utilizando Alias**

Para facilitar a escrita da consulta:

```
SELECT C.Nome, P.Produto
FROM Clientes C INNER JOIN Pedidos P ON C.ID_Cliente = P.ID_Cliente;
```

---

**INNER JOIN com múltiplas tabelas**

Exemplo:

```
SELECT C.Nome, P.Produto, F.NomeFornecedor
FROM Clientes CINNER JOIN Pedidos P ON C.ID_Cliente = P.ID_Cliente INNER JOIN Fornecedores F ON P.ID_Fornecedor = F.ID_Fornecedor;
```

---

**Como funciona**

O INNER JOIN retorna apenas os registros que possuem correspondência nas tabelas relacionadas.

Se um cliente não possuir pedidos cadastrados, ele não aparecerá no resultado.

Quando utilizar o INNER JOIN

- Relacionar clientes e pedidos.
- Relacionar produtos e categorias.
- Relacionar funcionários e departamentos.
- Consultar dados distribuídos em várias tabelas.

==O INNER JOIN é o tipo de JOIN mais utilizado em bancos de dados relacionais.==

==Seu principal objetivo é reunir informações de tabelas relacionadas por meio de chaves primárias e estrangeiras.==

## UNION

==O comando **UNION** é utilizado para combinar os resultados de duas ou mais consultas SELECT em um único conjunto de resultados.==

Ele empilha os resultados de uma consulta abaixo da outra.

O que o UNION pode fazer?

- Combinar resultados de múltiplas consultas.
- Unificar dados de diferentes tabelas.
- Eliminar registros duplicados.
- Criar relatórios consolidados.

Sintaxe básica

```
SELECT colunaFROM tabela1UNIONSELECT colunaFROM tabela2;
```

> [!example]  
> Exemplo prático
> 
> Tabela ClientesRJ:
> 
> |Nome|
> |---|
> |João|
> |Maria|
> 
> Tabela ClientesSP:
> 
> |Nome|
> |---|
> |Pedro|
> |Ana|
> 
> Consulta:
> 
> ```
> SELECT NomeFROM ClientesRJUNIONSELECT NomeFROM ClientesSP;
> ```
> 
> Resultado:
> 
> |Nome|
> |---|
> |João|
> |Maria|
> |Pedro|
> |Ana|

Informações importantes

**Mesma quantidade de colunas**

As consultas devem retornar a mesma quantidade de colunas.

Exemplo válido:

```
SELECT Nome FROM ClientesRJ UNION
SELECT Nome FROM ClientesSP;
```

Exemplo inválido:

```
SELECT Nome, Cidade FROM ClientesRJ UNION SELECT Nome FROM ClientesSP;
```

---

**Tipos de dados compatíveis**

As colunas correspondentes devem possuir tipos compatíveis.

Exemplo:

```
SELECT Nome FROM ClientesRJ UNION SELECT Nome FROM ClientesSP;
```

---

**Remoção de duplicados**

Por padrão, o UNION remove registros repetidos.

Exemplo:

Tabela A:

|Nome|
|---|
|João|
|Maria|

Tabela B:

|Nome|
|---|
|João|
|Pedro|

Resultado:

|Nome|
|---|
|João|
|Maria|
|Pedro|

O nome "João" aparece apenas uma vez.

---

**UNION ALL**

Se desejar manter os registros duplicados:

```
SELECT Nome FROM ClientesRJ UNION ALL SELECT Nome FROM ClientesSP;
```

Resultado:

|Nome|
|---|
|João|
|Maria|
|João|
|Pedro|

---

**Ordenando resultados do UNION**

Exemplo:

```
SELECT Nome FROM ClientesRJ UNION SELECT Nome FROM ClientesSP ORDER BY Nome;
```

Quando utilizar o UNION

- Unificar dados de várias tabelas.
- Consolidar relatórios.
- Combinar resultados semelhantes.
- Exibir registros provenientes de diferentes fontes.

==O UNION combina resultados verticalmente, enquanto o JOIN combina informações horizontalmente através de relacionamentos entre tabelas.==

==A principal diferença é que o INNER JOIN relaciona tabelas por chaves, enquanto o UNION apenas une os resultados de consultas compatíveis.==

## INSERT INTO

==O comando **INSERT INTO** é utilizado para adicionar novos registros em uma tabela de um banco de dados.==

Sempre que um novo dado precisa ser armazenado, o comando INSERT é utilizado para inserir as informações nas colunas da tabela.

O que o comando INSERT INTO pode fazer?

- Adicionar novos registros.
- Inserir dados em todas as colunas.
- Inserir dados em colunas específicas.
- Inserir múltiplos registros de uma só vez.

Sintaxe básica

```
INSERT INTO tabela
VALUES (valor1, valor2, valor3);
```

Exemplo:

```
INSERT INTO Clientes
VALUES (1, 'João Silva', 'joao@email.com');
```

> [!example]  
> Exemplo prático
> 
> Considere a tabela:
> 
> ```
> CREATE TABLE Clientes (    
> ID INT,    
> Nome VARCHAR(100),    
> Email VARCHAR(100)
> );
> ```
> 
> Para adicionar um cliente:
> 
> ```
> INSERT INTO ClientesVALUES (
> 1, 
> 'João Silva', 
> 'joao@email.com');
> ```

Informações importantes

**Inserindo em colunas específicas**

Nem sempre é necessário informar todas as colunas.

Exemplo:

```
INSERT INTO Clientes (Nome, Email)
VALUES ('Maria Souza', 'maria@email.com');
```

Nesse caso:

- Apenas as colunas  Nome e Email receberão valores.
- As demais colunas utilizarão NULL ou valores padrão (DEFAULT).

---

**Ordem das colunas**

Quando os nomes das colunas não são informados, os valores devem seguir exatamente a ordem da tabela.

Exemplo:

```
INSERT INTO Clientes
VALUES (2, 'Pedro', 'pedro@email.com');
```

Uma ordem incorreta pode gerar erro ou inserir dados errados.

---

**Inserindo múltiplos registros**

É possível inserir vários registros em uma única consulta.

Exemplo:

```
INSERT INTO Clientes (
ID, Nome, Email)
VALUES (1, 'João', 'joao@email.com'),
(2, 'Maria', 'maria@email.com'),
(3, 'Pedro', 'pedro@email.com');
```

Essa abordagem é mais eficiente do que executar vários INSERTs separados.

---

**Utilizando valores padrão (DEFAULT)**

Exemplo:

```
INSERT INTO Clientes (Nome)
VALUES ('Lucas');
```

Se existir um valor padrão definido na coluna, ele será utilizado automaticamente.

---

**Inserindo datas**

Exemplo:

```
INSERT INTO Funcionarios(Nome, DataAdmissao)
VALUES('Ana', '2026-06-18');
```

---

**Inserindo valores booleanos**

Exemplo:

```
INSERT INTO Usuarios(Nome, Ativo)
VALUES('Carlos', TRUE);
```

---

**Inserindo resultado de outra consulta**

Também é possível inserir dados obtidos por um SELECT.

Exemplo:

```
INSERT INTO ClientesBackup
SELECT *
FROM Clientes;
```

Todos os registros da tabela Clientes serão copiados para ClientesBackup.

Quando utilizar o INSERT INTO

- Cadastrar clientes.
- Registrar pedidos.
- Adicionar produtos.
- Armazenar informações de usuários.
- Popular tabelas com dados iniciais.

Erros comuns

**Quantidade de valores diferente da quantidade de colunas**

Exemplo incorreto:

```
INSERT INTO ClientesVALUES (1, 'João');
```

Se a tabela possuir três colunas, ocorrerá erro.

---

**Tipo de dado incompatível**

Exemplo incorreto:

```
INSERT INTO Clientes (ID)
VALUES ('João');
```

Uma coluna INT deve receber um número inteiro.

---

**Violação de chave primária**

Exemplo:

```
INSERT INTO ClientesVALUES (1, 'Maria', 'maria@email.com');
```

Se o ID 1 já existir, o banco retornará um erro de chave primária duplicada.

==O comando INSERT INTO é responsável por adicionar novos registros às tabelas do banco de dados.==

==Toda informação armazenada em um banco de dados relacional é inserida inicialmente através de comandos INSERT ou por aplicações que executam esse comando automaticamente.==

## UPDATE

==O comando **UPDATE** é utilizado para modificar dados já existentes em uma tabela do banco de dados.==

Sempre que for necessário corrigir, alterar ou atualizar informações armazenadas, utiliza-se o comando UPDATE.

O que o comando UPDATE pode fazer?

- Alterar valores existentes.
- Atualizar uma ou mais colunas.
- Atualizar um ou vários registros.
- Modificar dados com base em condições específicas.

Sintaxe básica

```
UPDATE tabela
SET coluna = valor
WHERE condição;
```

Exemplo:

```
UPDATE Clientes
SET Nome = 'João Silva'
WHERE ID = 1;
```

> [!example]  
> Exemplo prático
> 
> Considere a tabela:
> 
> |ID|Nome|Cidade|
> |---|---|---|
> |1|João|Rio de Janeiro|
> |2|Maria|São Paulo|
> 
> Para alterar a cidade de João:
> 
> ```
> UPDATE Clientes
> SET Cidade = 'Niterói'
> WHERE ID = 1;
> ```
> 
> Resultado:
> 
> |ID|Nome|Cidade|
> |---|---|---|
> |1|João|Niterói|
> |2|Maria|São Paulo|

Informações importantes

**Utilizando WHERE**

O `WHERE` define quais registros serão atualizados.

Exemplo:

```
UPDATE Clientes
SET Cidade = 'Belo Horizonte'
WHERE ID = 2;
```

Sem o WHERE, todos os registros serão modificados.

---

**Atualizando múltiplas colunas**

É possível alterar várias colunas simultaneamente.

Exemplo:

```
UPDATE Clientes
SET Nome = 'Pedro Silva',    Cidade = 'Curitiba'
WHERE ID = 3;
```

---

**Atualizando todos os registros**

Exemplo:

```
UPDATE Clientes
SET Ativo = TRUE;
```

Nesse caso, todos os registros da tabela serão atualizados.

---

**Utilizando operadores matemáticos**

O UPDATE pode realizar cálculos.

Exemplo:

```
UPDATE Produtos
SET Preco = Preco + 10;
```

Todos os preços receberão um aumento de R$ 10.

---

**Atualizando com porcentagem**

Exemplo:

```
UPDATE Produtos
SET Preco = Preco * 1.10;
```

Aumenta os preços em 10%.

---

**Atualizando datas**

Exemplo:

```
UPDATE Funcionarios
SET DataAtualizacao = NOW()
WHERE ID = 5;
```

Atualiza a data para o momento atual.

---

**Atualizando utilizando múltiplas condições**

Exemplo:

```
UPDATE Clientes
SET Categoria = 'Premium'
WHERE Cidade = 'Rio de Janeiro'
AND Compras > 1000;
```

Apenas os registros que atenderem às duas condições serão alterados.

Quando utilizar o UPDATE

- Corrigir informações cadastradas.
- Atualizar preços de produtos.
- Alterar status de pedidos.
- Modificar dados de usuários.
- Atualizar registros após operações do sistema.

Erros comuns

**Esquecer o WHERE**

Exemplo perigoso:

```
UPDATE Clientes
SET Cidade = 'São Paulo';
```

Todos os registros da tabela serão alterados.

---

**Atualizar coluna incorreta**

Exemplo:

```
UPDATE Clientes
SET ID = 5
WHERE ID = 1;
```

Alterações em chaves primárias devem ser feitas com cuidado.

---

**Utilizar tipos incompatíveis**

Exemplo:

```
UPDATE Produtos
SET Preco = 'ABC';
```

Uma coluna numérica deve receber valores numéricos.

Boas práticas

- Sempre utilizar `WHERE` quando possível.
- Executar um `SELECT` antes para verificar os registros que serão alterados.
- Fazer backup dos dados importantes.
- Testar consultas em ambiente de desenvolvimento.

Exemplo de validação:

```
SELECT *
FROM Clientes
WHERE ID = 1;
```

Depois:

```
UPDATE Clientes
SET Cidade = 'Niterói'
WHERE ID = 1;
```

==O comando UPDATE é responsável por modificar registros já existentes no banco de dados.==

==Por ser um comando que altera permanentemente os dados armazenados, seu uso exige atenção especial, principalmente em relação à cláusula WHERE para evitar modificações indesejadas em massa.==

## DELETE

==O comando **DELETE** é utilizado para remover registros existentes de uma tabela.==

Diferentemente do `UPDATE`, que modifica dados, o `DELETE` remove permanentemente os registros selecionados.

O que o comando DELETE pode fazer?

- Excluir registros específicos.
- Excluir múltiplos registros.
- Excluir todos os registros de uma tabela.
- Remover dados que não são mais necessários.

Sintaxe básica

```
DELETE FROM tabela
WHERE condição;
```

Exemplo:

```
DELETE FROM Clientes
WHERE ID = 1;
```

> [!example]  
> Exemplo prático
> 
> Considere a tabela:
> 
> |ID|Nome|
> |---|---|
> |1|João|
> |2|Maria|
> |3|Pedro|
> 
> Consulta:
> 
> ```
> DELETE FROM Clientes
> WHERE ID = 2;
> ```
> 
> Resultado:
> 
> |ID|Nome|
> |---|---|
> |1|João|
> |3|Pedro|
> 
> O registro da Maria foi removido.

Informações importantes

**Utilizando WHERE**

O `WHERE` define quais registros serão excluídos.

Exemplo:

```
DELETE FROM Produtos
WHERE Preco < 10;
```

Todos os produtos com preço menor que 10 serão removidos.

---

**Excluindo múltiplos registros**

Exemplo:

```
DELETE FROM Clientes
WHERE Cidade = 'Rio de Janeiro';
```

Todos os clientes do Rio de Janeiro serão removidos.

---

**Excluindo todos os registros**

Exemplo:

```
DELETE FROM Clientes;
```

Resultado:

- Todos os registros serão removidos.
- A estrutura da tabela permanecerá intacta.

---

**DELETE com múltiplas condições**

Exemplo:

```
DELETE FROM PedidosWHERE Status = 'Cancelado'AND DataPedido < '2026-01-01';
```

Apenas os pedidos cancelados antes da data informada serão removidos.

---

**DELETE e Foreign Keys**

Se uma tabela possuir relacionamentos com outras tabelas, o banco pode impedir a exclusão.

Exemplo:

```
DELETE FROM Clientes
WHERE ID_Cliente = 1;
```

Caso existam pedidos associados ao cliente, pode ocorrer erro de integridade referencial.

---

**DELETE dentro de transações**

Exemplo:

```
START TRANSACTION;
DELETE FROM Clientes
WHERE ID = 5;
ROLLBACK;
```

Resultado:

- O registro não será removido definitivamente.
- O `ROLLBACK` desfaz a operação.

---

**DELETE com COMMIT**

Exemplo:

```
START TRANSACTION;
DELETE FROM Clientes
WHERE ID = 5;
COMMIT;
```

Resultado:

- A exclusão torna-se permanente.

Quando utilizar o DELETE

- Remover registros incorretos.
- Excluir dados antigos.
- Limpar tabelas.
- Remover informações desnecessárias.
- Excluir cadastros cancelados.

Erros comuns

**Esquecer o WHERE**

Exemplo perigoso:

```
DELETE FROM Clientes;
```

Todos os registros da tabela serão removidos.

---

**Excluir registros sem verificar antes**

Boa prática:

```
SELECT *
FROM Clientes
WHERE Cidade = 'Rio de Janeiro';
```

Depois:

```
DELETE FROM Clientes
WHERE Cidade = 'Rio de Janeiro';
```

---

**Ignorar relacionamentos**

Antes de excluir um registro, verifique se ele está sendo utilizado por outras tabelas através de chaves estrangeiras.

Diferença entre DELETE e TRUNCATE

|DELETE|TRUNCATE|
|---|---|
|Remove registros selecionados|Remove todos os registros|
|Pode utilizar WHERE|Não utiliza WHERE|
|Pode ser revertido em transações|Geralmente não pode ser revertido|
|Mais lento para grandes volumes|Mais rápido|

Exemplo de TRUNCATE:

```
TRUNCATE TABLE Clientes;
```

Todos os registros serão removidos instantaneamente.

Boas práticas

- Sempre utilizar `WHERE` quando possível.
- Executar um `SELECT` antes da exclusão.
- Utilizar transações para operações críticas.
- Manter backups atualizados.

==O comando DELETE remove registros de uma tabela de forma permanente, exigindo cuidado para evitar perda de dados importantes.==

==Uma das práticas mais importantes ao utilizar DELETE é verificar previamente os registros afetados utilizando um SELECT com a mesma condição do WHERE.==