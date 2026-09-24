## O QUE É?

Uma **Trigger** é um mecanismo do banco de dados que executa **automaticamente uma ação quando um determinado evento acontece** em uma tabela.

> **Trigger = "Quando X acontecer, faça Y automaticamente."**

---

## QUANDO UMA TRIGGER É UTILIZADA?

Os eventos mais comuns são:

- `INSERT` → quando um registro é inserido
- `UPDATE` → quando um registro é atualizado
- `DELETE` → quando um registro é excluído

Ela também pode ser configurada para executar:

- `BEFORE` → antes da operação
- `AFTER` → depois da operação

### Exemplo

AFTER INSERT

Significa:

> Depois que um registro for inserido, execute a Trigger.

---

## PARA QUE SERVE?

Triggers são utilizadas principalmente para:

- Registrar logs
- Atualizar outras tabelas automaticamente
- Manter dados sincronizados
- Validar determinadas operações
- Registrar histórico de alterações
- Automatizar regras no banco

---

## EXEMPLO

Imagine uma tabela de clientes:

clientes

----------------

id

nome

email

E uma tabela de logs:

logs

----------------

id

mensagem

data

Podemos criar uma Trigger que registre automaticamente quando um cliente for cadastrado.

CREATE TRIGGER registrar_cliente

AFTER INSERT ON clientes

FOR EACH ROW

BEGIN

    INSERT INTO logs (mensagem, data)

    VALUES ('Novo cliente cadastrado', NOW());

END;

Agora, quando executarmos:

INSERT INTO clientes (nome, email)

VALUES ('Gustavo', 'gustavo@email.com');

O banco automaticamente executará a Trigger e adicionará um registro em `logs`.

---

