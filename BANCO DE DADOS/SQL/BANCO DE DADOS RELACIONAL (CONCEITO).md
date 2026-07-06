
## TABLE (TABELA)

==Uma **Table (Tabela)** é a estrutura utilizada para armazenar dados em um banco de dados relacional.==

Os dados são organizados em linhas e colunas, permitindo o armazenamento e a manipulação eficiente das informações.

O que compõe uma tabela?

- Colunas (Columns).
- Linhas (Rows).
- Valores de dados (Data Values).
- Chave Primária (Primary Key).
- Chaves Estrangeiras (Foreign Keys).

Exemplo de tabela:

|ID|Nome|Email|
|---|---|---|
|1|João Silva|[joao@email.com](mailto:joao@email.com)|
|2|Maria Souza|[maria@email.com](mailto:maria@email.com)|
> [!example]  
> Exemplo prático
> 
> Imagine um sistema de cadastro de clientes.
> 
> A tabela **Clientes** pode armazenar:
> 
> ```
> ID
> Nome
> Email
> Telefone
> ```
> 
> Cada cliente cadastrado será armazenado em uma nova linha da tabela.

Informações importantes

**Organização dos dados**

==Uma tabela representa uma entidade do sistema.==

Exemplos:

- Clientes
- Produtos
- Funcionários
- Pedidos

Cada entidade normalmente possui sua própria tabela.

**Finalidade**

As tabelas permitem:

- Armazenar informações.
- Consultar registros.
- Atualizar dados.
- Relacionar informações entre diferentes tabelas.

==Toda a estrutura de um banco de dados relacional é baseada em tabelas.==

## COLUMN (COLUNA)

==Uma **Column (Coluna)** representa um atributo ou característica dos dados armazenados em uma tabela.==

Cada coluna possui um nome e um tipo de dado específico.

Exemplo:

|ID|Nome|Email|
|---|---|---|
As colunas da tabela são:

- ID
- Nome
- Email

> [!example]  
> Exemplo prático
> 
> Na tabela Clientes:
> 
> ```
> ID
> Nome
> Email
> DataNascimento
> ```
> 
> Cada coluna armazena um tipo específico de informação sobre o cliente.

Informações importantes:

**Tipos de dados**

Uma coluna pode armazenar:

- Texto.
- Números.
- Datas.
- Valores lógicos.

Exemplo:

```
Nome VARCHAR(100)
Idade INT
DataCadastro DATE
```

==As colunas definem quais informações poderão ser armazenadas em uma tabela.==

## ROW (LINHA)

==Uma **Row (Linha)** representa um registro completo dentro de uma tabela.==

Cada linha contém os valores correspondentes a todas as colunas da tabela.

Exemplo:

|ID|Nome|Email|
|---|---|---|
|1|João Silva|[joao@email.com](mailto:joao@email.com)|
A linha acima representa um cliente completo.

> [!example]  
> Exemplo prático
> 
> Considerando a tabela:
> 
> |ID|Nome|Email|
> |---|---|---|
> |1|João|joao@email.com|
> 
> A linha inteira corresponde a um único registro do banco de dados.

Informações importantes

**Função da linha**

Uma linha representa:

- Um cliente.
- Um produto.
- Um pedido.
- Um funcionário.

Dependendo da finalidade da tabela.

==Cada nova informação cadastrada gera uma nova linha na tabela.==

## DATA VALUE (VALOR DE DADO)

==Um **Data Value (Valor de Dado)** é a informação armazenada em uma célula da tabela.==

Ele corresponde ao cruzamento entre uma linha e uma coluna.

Exemplo:

|ID|Nome|Email|
|---|---|---|
|1|João Silva|[joao@email.com](mailto:joao@email.com)|
Data Values:

- 1
- João Silva
- joao@email.com

> [!example]  
> Exemplo prático
> 
> Na tabela:
> 
> |ID|Nome|
> |---|---|
> |1|João|
> 
> Os valores "1" e "João" são exemplos de Data Values.

Informações importantes

**Características**

- Representam os dados reais armazenados.
- Possuem um tipo definido pela coluna.
- São utilizados em consultas e operações do banco de dados.

==Todo registro é formado por um conjunto de Data Values.==

## PRIMARY KEY (CHAVE PRIMÁRIA)

==A **Primary Key (Chave Primária)** é uma coluna ou conjunto de colunas que identifica de forma única cada registro de uma tabela.==

Características:

- Não pode conter valores duplicados.
- Não pode conter valores nulos.
- Deve identificar exclusivamente cada registro.

Exemplo:

|ID|Nome|
|---|---|
|1|João|
|2|Maria|
|3|Pedro|

O campo **ID** é a Primary Key.

> [!example]  
> Exemplo prático
> 
> Em uma tabela de clientes:
> 
> ```
> ID_ClienteNomeEmail
> ```
> 
> O campo `ID_Cliente` pode ser utilizado para identificar cada cliente de forma única.

Exemplo SQL:

```

CREATE TABLE Clientes (
    ID_Cliente INT PRIMARY KEY,
    Nome VARCHAR(100),
    Email VARCHAR(100)
);
```

Informações importantes

**Vantagens**

- Evita registros duplicados.
- Facilita consultas.
- Permite relacionamentos com outras tabelas.

==Toda tabela deve possuir uma forma de identificar unicamente seus registros.==

## FOREIGN KEY (CHAVE ESTRANGEIRA)

==A **Foreign Key (Chave Estrangeira)** é uma coluna responsável por criar relacionamentos entre tabelas.==

Ela referencia a Primary Key de outra tabela.

Exemplo:

Tabela Clientes:

| ID_Cliente | Nome  |
| ---------- | ----- |
| 1          | João  |
| 2          | Maria |
Tabela Pedidos:

| ID_Pedido | ID_Cliente | Produto  |
| --------- | ---------- | -------- |
| 101       | 1          | Notebook |
| 102       | 2          | Mouse    |
| 103       | 1          | Teclado  |

Neste exemplo:

- `ID_Cliente` da tabela Clientes é a Primary Key.
- `ID_Cliente` da tabela Pedidos é a Foreign Key.
- O relacionamento permite identificar qual cliente realizou cada pedido.

> [!example]  
> Exemplo prático
> 
> Um cliente pode realizar vários pedidos.
> 
> Para conectar as tabelas:
> 
> ```
> ClientesID_Cliente (PK)PedidosID_Pedido (PK)ID_Cliente (FK)
> ```
> 
> A Foreign Key cria o vínculo entre elas.

Exemplo SQL

```
CREATE TABLE Clientes (    
ID_Cliente INT PRIMARY KEY,    
Nome VARCHAR(100)
);
CREATE TABLE Pedidos (    
ID_Pedido INT PRIMARY KEY,
ID_Cliente INT,    
Produto VARCHAR(100),    
FOREIGN KEY (ID_Cliente)        
REFERENCES Clientes(ID_Cliente)
);
```

Informações importantes

**Funções da Foreign Key**

- Criar relacionamentos entre tabelas.
- Garantir integridade referencial.
- Evitar registros órfãos.
- Facilitar consultas envolvendo múltiplas tabelas.

==A Foreign Key é um dos principais mecanismos utilizados para conectar informações em bancos de dados relacionais.==

