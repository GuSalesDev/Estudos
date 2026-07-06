## CONTROLE DE ACESSO E SEGURANÇA EM BANCO DE DADOS

==O controle de acesso é o conjunto de mecanismos utilizados para definir quais usuários podem acessar o banco de dados e quais operações cada um pode realizar.==

Seu principal objetivo é proteger as informações contra acessos não autorizados, alterações indevidas e vazamento de dados.

A segurança em bancos de dados é baseada principalmente em:

- Usuários.
- Papéis (Roles).
- Privilégios.
- Autenticação.
- Auditoria.

---

## USUÁRIOS

==Um usuário é uma conta utilizada para acessar o banco de dados.==

Cada usuário possui:

- Nome de usuário.
- Senha.
- Permissões específicas.

Exemplo no MySQL:

```
CREATE USER 'joao'@'localhost'IDENTIFIED BY 'Senha123';
```

Exemplo no PostgreSQL:

```
CREATE USER joao
WITH PASSWORD 'Senha123';
```

Após a criação, o usuário existe, mas ainda não possui permissões.

---

## PRIVILÉGIOS

==Privilégios definem quais ações um usuário pode executar no banco de dados.==

Os privilégios mais comuns são:

|Privilégio|Função|
|---|---|
|SELECT|Consultar dados|
|INSERT|Inserir registros|
|UPDATE|Alterar registros|
|DELETE|Remover registros|
|CREATE|Criar objetos|
|ALTER|Modificar estruturas|
|DROP|Excluir objetos|
|ALL PRIVILEGES|Todas as permissões|

Exemplo:

```
GRANT SELECTON Clientes
TO joao;
```

O usuário poderá apenas consultar a tabela.

---

## GRANT

==O comando GRANT é utilizado para conceder permissões a usuários ou grupos.==

Exemplo:

```
GRANT SELECT, INSERT
ON Clientes
TO joao;
```

Permissões concedidas:

- Consultar registros.
- Inserir registros.

Não poderá:

- Atualizar.
- Excluir.
- Alterar a estrutura da tabela.

---

## REVOKE

==O comando REVOKE remove permissões concedidas anteriormente.==

Exemplo:

```
REVOKE INSERT
ON Clientes
FROM joao;
```

O usuário perderá a permissão de inserir dados.

---

## ROLES (PAPÉIS)

==Roles permitem agrupar permissões e atribuí-las a vários usuários.==

Ao invés de conceder permissões individualmente, cria-se um papel.

Exemplo:

```
CREATE ROLE analista;
```

Concedendo permissões:

```
GRANT SELECT
ON Clientes
TO analista;
```

Associando usuário à role:

```
GRANT analista TO joao;
```

Agora João herda todas as permissões do papel analista.

---

## PRINCÍPIO DO MENOR PRIVILÉGIO

==Um usuário deve possuir apenas as permissões necessárias para executar seu trabalho.==

Exemplo:

|Cargo|Permissões|
|---|---|
|Analista|SELECT|
|Operador|SELECT, INSERT|
|Supervisor|SELECT, INSERT, UPDATE|
|DBA|Todas|

Isso reduz riscos de erros e ataques.

---

## SENHAS SEGURAS

Boas práticas:

- Utilizar senhas fortes.
- Misturar letras, números e símbolos.
- Evitar senhas previsíveis.
- Alterar senhas periodicamente.

Exemplo inadequado:

```
123456
```

Exemplo adequado:

```
M3u@Banc0#2026
```

---

## AUDITORIA

==A auditoria registra ações realizadas pelos usuários no banco de dados.==

Permite identificar:

- Quem acessou.
- O que foi alterado.
- Quando ocorreu a alteração.

Exemplos de eventos auditados:

- Login.
- INSERT.
- UPDATE.
- DELETE.
- ALTER TABLE.

A auditoria é fundamental em ambientes corporativos.

---

## BACKUP

==Backup é a cópia de segurança dos dados do banco.==

Objetivos:

- Recuperação após falhas.
- Recuperação após exclusões acidentais.
- Recuperação após ataques.

Boas práticas:

- Realizar backups periódicos.
- Testar restaurações.
- Armazenar cópias em locais seguros.

---

## CRIPTOGRAFIA

==A criptografia protege informações sensíveis armazenadas ou transmitidas.==

Pode ser utilizada para:

- Senhas.
- Dados pessoais.
- Informações financeiras.

Exemplos:

- Hash de senhas.
- SSL/TLS nas conexões.
- Criptografia de disco.

---

## EXEMPLO DE CENÁRIO REAL

Sistema de vendas:

### Vendedor

Pode:

- Consultar produtos.
- Registrar vendas.

Não pode:

- Excluir registros.
- Alterar estrutura do banco.

Permissões:

```
SELECTINSERT
```

### Gerente

Pode:

- Consultar.
- Inserir.
- Atualizar.

Permissões:

```
SELECTINSERTUPDATE
```

### DBA

Pode:

- Administrar o banco completo.

Permissões:

```
ALL PRIVILEGES
```

---

## RESUMO

|Conceito|Função|
|---|---|
|User|Conta de acesso|
|Password|Autenticação|
|Privilege|Permissão específica|
|GRANT|Concede permissões|
|REVOKE|Remove permissões|
|ROLE|Agrupa permissões|
|Backup|Recuperação de dados|
|Auditoria|Registro de ações|
|Criptografia|Proteção de informações|

==A segurança em bancos de dados consiste em controlar quem pode acessar as informações e quais operações cada usuário está autorizado a realizar.==

==O uso adequado de usuários, permissões, roles, auditoria, backups e criptografia é essencial para garantir a confidencialidade, integridade e disponibilidade dos dados.==