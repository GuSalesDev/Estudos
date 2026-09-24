
## Como executar

MySQL

```sql
CALL cadastrarUsuario();
```

SQL Server

```sql
EXEC cadastrarUsuario;
```

Oracle

```sql
EXEC cadastrarUsuario;
```

---

# Parâmetros

Uma procedure pode receber informações da aplicação.

**IN

Recebe valores.

```sql
CREATE PROCEDURE buscarUsuario(
    IN p_id INT
)

BEGIN

SELECT *
FROM usuarios
WHERE id = p_id;

END;
```

Uso

```sql
CALL buscarUsuario(5);
```

Resultado

```text
id | nome
------------
5  | Gustavo
```

---

**OUT

Serve para devolver um valor.

```sql
CREATE PROCEDURE contarUsuarios(
    OUT total INT
)

BEGIN

SELECT COUNT(*)
INTO total
FROM usuarios;

END;
```

---

**INOUT

Recebe um valor e também devolve outro.

```sql
CREATE PROCEDURE aumentarValor(
    INOUT preco DECIMAL(10,2)
)

BEGIN

SET preco = preco * 1.10;

END;
```

---

**Variáveis

É possível criar variáveis.

```sql
DECLARE quantidade INT;

SET quantidade = 10;
```

Exemplo

```sql
BEGIN

DECLARE total INT;

SELECT COUNT(*)
INTO total
FROM pedidos;

END;
```

---

# Estruturas de decisão

**IF

```sql
IF total > 100 THEN

    SELECT 'Muitos pedidos';

ELSE

    SELECT 'Poucos pedidos';

END IF;
```

---

**CASE

```sql
CASE

WHEN nota >= 7 THEN
    SELECT 'Aprovado';

WHEN nota >=5 THEN
    SELECT 'Recuperação';

ELSE
    SELECT 'Reprovado';

END CASE;
```

---

# Estruturas de repetição

**WHILE

```sql
DECLARE contador INT;

SET contador = 1;

WHILE contador <= 5 DO

    INSERT INTO numeros(valor)
    VALUES(contador);

    SET contador = contador + 1;

END WHILE;
```

---

**LOOP

```sql
meuLoop: LOOP

    IF contador = 10 THEN
        LEAVE meuLoop;
    END IF;

END LOOP;
```

---

# Transações

Um dos maiores motivos para usar Procedures.

Imagine uma venda.

Precisamos:

1. Inserir pedido
2. Inserir itens
3. Atualizar estoque
4. Atualizar caixa

Se uma dessas operações falhar, tudo deve ser desfeito.

```sql
START TRANSACTION;

INSERT ...

UPDATE ...

INSERT ...

COMMIT;
```

Caso aconteça erro:

```sql
ROLLBACK;
```

---

# Exemplo Real

## Sistema de Vendas

Sem Procedure

Aplicação envia:

```sql
INSERT INTO pedidos...
```

Depois

```sql
INSERT INTO itens...
```

Depois

```sql
UPDATE estoque...
```

Depois

```sql
INSERT INTO historico...
```

São **4 viagens** entre aplicação e banco.

---

Com Procedure

Aplicação envia apenas:

```sql
CALL realizarVenda(...);
```

A Procedure faz tudo.

```text
Java
 │
 ▼
CALL realizarVenda()
 │
 ▼
Banco

Inserir pedido

Inserir itens

Atualizar estoque

Registrar histórico

Commit
```

Muito mais eficiente.

---

# Exemplo Completo

```sql
DELIMITER $$

CREATE PROCEDURE realizarVenda(

    IN p_produto INT,
    IN p_quantidade INT

)

BEGIN

DECLARE estoqueAtual INT;

SELECT estoque
INTO estoqueAtual
FROM produtos
WHERE id = p_produto;

IF estoqueAtual >= p_quantidade THEN

    INSERT INTO vendas(produto,quantidade)
    VALUES(p_produto,p_quantidade);

    UPDATE produtos
    SET estoque = estoque - p_quantidade
    WHERE id = p_produto;

ELSE

    SELECT 'Estoque insuficiente';

END IF;

END$$

DELIMITER ;
```

Uso

```sql
CALL realizarVenda(3,5);
```

---

# Procedures x Functions

|Procedure|Function|
|----------|--------|
|Pode alterar tabelas|Normalmente não altera dados|
|Pode ter vários comandos|Geralmente executa um cálculo|
|Pode retornar vários resultados|Retorna apenas um valor|
|É chamada com CALL ou EXEC|É usada dentro do SELECT|
|Ideal para processos|Ideal para cálculos|

Exemplo de Function

```sql
SELECT calcularDesconto(100);
```

Exemplo de Procedure

```sql
CALL realizarVenda(5,3);
```

---

# Quando utilizar?

## 1. Regras de negócio no banco

Exemplo

- Aprovar empréstimo
- Fechar folha de pagamento
- Processar comissão
- Emitir nota fiscal

---

## 2. Processos grandes

Exemplo

Atualizar milhares de registros.

Ao invés da aplicação enviar centenas de UPDATEs:

```text
Aplicação

↓

Procedure

↓

Banco faz tudo sozinho
```

---

## 3. Segurança

O usuário recebe permissão para executar apenas a procedure.

Ele não pode acessar diretamente as tabelas.

```text
Usuário

↓

CALL cadastrarCliente()

↓

Banco
```

---

## 4. Reutilização

Diversas aplicações utilizam a mesma lógica.

Java

↓

Procedure

Python

↓

Procedure

C#

↓

Procedure

Todos executam exatamente a mesma regra.

---

## 5. Melhor desempenho

Ao invés de:

```text
Java

↓

SELECT

↓

UPDATE

↓

INSERT

↓

DELETE

↓

UPDATE
```

Faz apenas:

```text
Java

↓

CALL procedure()
```

Menos comunicação com o banco.

---

# Quando NÃO utilizar?

## Regras de negócio da aplicação

Exemplo

Login.

JWT.

Validação de CPF.

Integração com APIs.

Essas regras normalmente ficam no Java.

---

## Projetos pequenos

Se apenas um INSERT resolve o problema, criar Procedure aumenta a complexidade.

---

## Sistemas com ORM

Projetos Spring Boot costumam utilizar:

- JPA
- Hibernate
- Spring Data JPA

Grande parte da lógica fica na aplicação.

---

# Vantagens

- Melhor desempenho em operações complexas.
- Reduz o tráfego entre aplicação e banco.
- Centraliza regras de negócio.
- Facilita reutilização.
- Permite controle de permissões.
- Pode utilizar transações.
- Ideal para processamento em lote.

---

# Desvantagens

- Aumenta o acoplamento ao banco de dados.
- Dificulta migração entre bancos (MySQL → PostgreSQL, por exemplo).
- Testes automatizados são mais difíceis.
- Versionamento pode ser mais complexo.
- Debug é menos prático do que em linguagens como Java.

---

# Como isso aparece no mercado?

## Bancos

Muito comum.

Exemplos:

- Itaú
- Bradesco
- Santander
- Banco do Brasil

---

## Grandes empresas

Muito comum em sistemas legados.

Exemplos:

- Oracle
- SQL Server
- SAP
- ERPs

---

## Spring Boot moderno

Normalmente a lógica fica no Java.

A Procedure é usada apenas para:

- Relatórios complexos
- Processamentos em lote
- Migração de dados
- Rotinas administrativas
- Processos financeiros

---

**Exemplo de uso em Java (JDBC)

```java
CallableStatement stmt = connection.prepareCall("{CALL buscarUsuario(?)}");

stmt.setInt(1, 5);

ResultSet rs = stmt.executeQuery();

while (rs.next()) {
    System.out.println(rs.getString("nome"));
}
```

---

**Exemplo de uso em Spring Data JPA

```java
@Repository
public interface UsuarioRepository extends JpaRepository<Usuario, Long> {

    @Procedure("buscarUsuario")
    Usuario buscarUsuario(Long id);

}
```

---

# Resumo

> Uma **Stored Procedure** é um bloco de código SQL armazenado no banco de dados que encapsula operações, regras e processos. Ela é especialmente útil para rotinas complexas, processamento em lote, transações e cenários em que múltiplas aplicações compartilham a mesma lógica de negócio. Em aplicações modernas com Spring Boot, costuma ser utilizada apenas em casos específicos, enquanto a maior parte da lógica permanece na camada de serviço da aplicação.