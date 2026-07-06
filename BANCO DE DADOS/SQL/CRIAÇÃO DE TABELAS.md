
## CREATE TABLE

==O comando **CREATE TABLE** é utilizado para criar uma nova tabela dentro de um banco de dados.==

Ao criar uma tabela, definimos:

- Nome da tabela.
- Nome das colunas.
- Tipos de dados.
- Restrições (Constraints).
- Chaves primárias e estrangeiras.

Sintaxe básica:

```
CREATE TABLE nome_tabela (    
	coluna1 tipo_dado,    
	coluna2 tipo_dado,    
	coluna3 tipo_dado
	);
```

Exemplo:

```
CREATE TABLE Clientes (    
	ID_Cliente INT,    
	Nome VARCHAR(100),    
	Email VARCHAR(150)
	);
```

Após a execução, a tabela será criada vazia.

> [!example]  
> Exemplo prático
> 
> Criando uma tabela de produtos:
> 
> ```
> CREATE TABLE Produtos (    
> 	ID_Produto INT,    
> 	Nome VARCHAR(100),    
> 	Preco DECIMAL(10,2),    
> 	Estoque INT
> );
> ```
> 
> Estrutura criada:
> 
> |Coluna|Tipo|
> |---|---|
> |ID_Produto|INT|
> |Nome|VARCHAR(100)|
> |Preco|DECIMAL(10,2)|
> |Estoque|INT|

---

## DEFININDO CHAVE PRIMÁRIA

Uma tabela normalmente possui uma chave primária para identificar cada registro.

Exemplo:

```
CREATE TABLE Clientes (    
	ID_Cliente INT PRIMARY KEY,    
	Nome VARCHAR(100),    
	Email VARCHAR(150)
);
```

A coluna `ID_Cliente` não poderá possuir valores duplicados.

---

## DEFININDO NOT NULL

O `NOT NULL` impede que uma coluna receba valores nulos.

Exemplo:

```
CREATE TABLE Clientes (    
	ID_Cliente INT PRIMARY KEY,    
	Nome VARCHAR(100) NOT NULL,    
	Email VARCHAR(150)
);
```

Nesse caso, todo cliente deverá possuir um nome.

---

## DEFININDO VALORES PADRÃO

O `DEFAULT` define um valor automático quando nenhum valor for informado.

Exemplo:

```
CREATE TABLE Usuarios (    
	ID_Usuario INT PRIMARY KEY,    
	Nome VARCHAR(100),    
	Ativo BOOLEAN DEFAULT TRUE);
```

Se o campo `Ativo` não for informado, ele receberá `TRUE`.

---

## DEFININDO CHAVE ESTRANGEIRA

Uma tabela pode se relacionar com outra através de uma chave estrangeira.

Exemplo:

```
CREATE TABLE Pedidos (    
	ID_Pedido INT PRIMARY KEY,    
	DataPedido DATE,    
	ID_Cliente INT,    
	FOREIGN KEY (ID_Cliente)    
	REFERENCES Clientes(ID_Cliente)
);
```

A coluna `ID_Cliente` deve existir previamente na tabela `Clientes`.

---

## BOAS PRÁTICAS

- Utilizar nomes claros para tabelas e colunas.
- Definir tipos de dados adequados.
- Utilizar PRIMARY KEY sempre que possível.
- Utilizar NOT NULL para campos obrigatórios.
- Criar relacionamentos utilizando FOREIGN KEY.

Exemplo completo:

```
CREATE TABLE Funcionarios (    
	ID_Funcionario INT PRIMARY KEY,    
	Nome VARCHAR(100) NOT NULL,    
	Email VARCHAR(150) UNIQUE,    
	Salario DECIMAL(10,2),    
	DataAdmissao DATE,   
	Ativo BOOLEAN DEFAULT TRUE
);
```

---

## RESUMO

|Elemento|Função|
|---|---|
|CREATE TABLE|Cria uma tabela|
|INT|Armazena números inteiros|
|VARCHAR|Armazena textos|
|PRIMARY KEY|Identifica registros unicamente|
|FOREIGN KEY|Cria relacionamentos|
|NOT NULL|Impede valores nulos|
|DEFAULT|Define valor padrão|

==O comando CREATE TABLE é a base da modelagem de bancos de dados relacionais.==

==Toda estrutura de armazenamento de dados começa pela criação correta das tabelas, colunas, tipos de dados e restrições necessárias para garantir a integridade das informações.==