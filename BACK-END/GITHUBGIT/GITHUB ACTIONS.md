## O QUE É GITHUB ACTIONS?

==**GitHub Actions** é a ferramenta de automação do GitHub que permite executar tarefas automaticamente quando determinados eventos acontecem no repositório.==

Essas tarefas podem incluir:

- Compilar o projeto.
    
- Executar testes.
    
- Validar código.
    
- Gerar arquivos.
    
- Publicar aplicações (Deploy).
    
- Automatizar processos repetitivos.
    

Na prática, o GitHub Actions é uma plataforma de **CI/CD** integrada ao próprio GitHub.

---

## COMO O GITHUB ACTIONS FUNCIONA?

O funcionamento é baseado em quatro conceitos principais:

```text
Evento (Event)

↓

Workflow

↓

Jobs

↓

Steps
```

## 1. Evento (Event)

É o que dispara a automação.

Exemplos:

- Um `git push`
    
- Um Pull Request
    
- Criação de uma tag
    
- Um horário programado
    
- Um clique manual
    

Exemplo:

```yaml
on:
  push:
```

Isso significa:

> "Sempre que alguém fizer um push, execute este workflow."

---

## 2. Workflow

Um Workflow é o arquivo que descreve toda a automação.

Todos os workflows ficam dentro da pasta:

```text
.github/workflows/
```

Exemplo:

```text
.github/
└── workflows/
    └── ci.yml
```

O arquivo possui extensão `.yml` (YAML).

---

## 3. Jobs

Um Workflow pode possuir um ou vários Jobs.

Cada Job representa um conjunto de tarefas.

Exemplo:

```text
Workflow

├── Job: Build
├── Job: Test
└── Job: Deploy
```

Os Jobs podem executar em paralelo ou em sequência.

---

## 4. Steps

Cada Job é composto por vários Steps.

Exemplo:

```text
Job Build

├── Baixar código
├── Instalar Java
├── Compilar projeto
└── Executar testes
```

---

## COMO CRIAR UM GITHUB ACTIONS

## Passo 1: Criar a estrutura

Dentro do projeto, crie a pasta:

```text
.github/workflows
```

Ficando assim:

```text
MeuProjeto

├── src
├── pom.xml
└── .github
    └── workflows
```

---

## Passo 2: Criar o arquivo YAML

Crie um arquivo chamado:

```text
ci.yml
```

O nome pode ser qualquer um.

Exemplo:

```text
.github/workflows/ci.yml
```

---

## Passo 3: Escrever o Workflow

```yaml
name: Java CI

on:
  push:
    branches:
      - main

jobs:
  build:

    runs-on: ubuntu-latest

    steps:

      - name: Baixar código
        uses: actions/checkout@v4

      - name: Instalar Java
        uses: actions/setup-java@v4
        with:
          distribution: temurin
          java-version: 21

      - name: Dar permissão ao Maven
        run: chmod +x mvnw

      - name: Executar testes
        run: ./mvnw test
```

---

## EXPLICANDO

## Nome do Workflow

```yaml
name: Java CI
```

Esse nome aparecerá na aba **Actions** do GitHub.

Exemplo:

```text
Actions

✔ Java CI
```

---

## Evento

```yaml
on:
  push:
```

Significa:

> Execute este processo sempre que houver um push.

Também poderia ser:

```yaml
on:
  pull_request:
```

ou

```yaml
on:
  workflow_dispatch:
```

Este último cria um botão para execução manual.

---

## Job

```yaml
jobs:
  build:
```

Criamos um Job chamado `build`.

Poderíamos ter vários:

```yaml
jobs:
  build:
  test:
  deploy:
```

---

## Máquina virtual

```yaml
runs-on: ubuntu-latest
```

O GitHub cria uma máquina Linux temporária para executar as tarefas.

É como se ele alugasse um computador por alguns minutos.

Também existem:

```text
windows-latest

macos-latest
```

---

## Step 1

```yaml
- name: Baixar código
  uses: actions/checkout@v4
```

O GitHub cria uma máquina vazia.

Ela não possui seu projeto.

O `checkout` faz o clone automático do repositório.

Equivale aproximadamente a:

```bash
git clone ...
```

---

## Step 2

```yaml
- name: Instalar Java
  uses: actions/setup-java@v4
```

Instala o Java na máquina virtual.

```yaml
with:
  distribution: temurin
  java-version: 21
```

Nesse caso:

- Distribuição: Eclipse Temurin
    
- Versão: Java 21
    

---

## Step 3

```yaml
run: chmod +x mvnw
```

Dá permissão de execução para o Maven Wrapper.

No Linux, arquivos precisam possuir permissão para serem executados.

---

## Step 4

```yaml
run: ./mvnw test
```

Executa:

```bash
mvn test
```

O Maven:

- Baixa dependências.
    
- Compila o projeto.
    
- Executa os testes unitários.
    

Se algum teste falhar:

```text
❌ Workflow Failed
```

Se tudo passar:

```text
✔ Workflow Success
```

---

## O QUE ACONTECE QUANDO VÔCE FAZ UM GIT PUSH?

Imagine este comando:

```bash
git push origin main
```

O GitHub detecta:

```text
Evento detectado:

push
```

Então ele faz:

```text
Cria máquina virtual Ubuntu

↓

Clona seu projeto

↓

Instala Java

↓

Executa Maven

↓

Executa testes

↓

Mostra resultado
```

Tudo isso acontece automaticamente.

---

## VISUALIZANDO A EXECUÇÃO

Depois do push:

Entre no GitHub

↓

Clique em:

```text
Actions
```

Você verá algo parecido com:

```text
✔ Java CI

Commit:
Implementa login

Tempo:
1m 12s
```

Ao clicar na execução, cada Step pode ser expandido:

```text
✔ Baixar código

✔ Instalar Java

✔ Executar testes
```

Também é possível visualizar os logs completos.

---

## EXECUTANDO EM PULL REQUEST

Uma prática muito comum é validar o código antes do merge.

```yaml
on:
  pull_request:
    branches:
      - main
```

Fluxo:

```text
Desenvolvedor cria Branch

↓

Implementa funcionalidade

↓

Abre Pull Request

↓

GitHub Actions executa testes

↓

Se passar:

Pull Request pode ser aprovado
```

---

## EXECUTANDO VÁRIOS JOBS

```yaml
jobs:

  build:
    ...

  test:
    needs: build
    ...

  deploy:
    needs: test
    ...
```

O parâmetro:

```yaml
needs:
```

significa:

> Só execute este Job quando o anterior terminar.

Fluxo:

```text
Build

↓

Testes

↓

Deploy
```

---

## FAZENDO DEPLOY AUTOMÁTICO

Depois dos testes, o GitHub pode:

- Publicar no GitHub Pages.
    
- Atualizar um servidor Linux.
    
- Enviar para AWS.
    
- Enviar para Azure.
    
- Enviar para Google Cloud.
    
- Publicar uma API.
    

Fluxo completo:

```text
git push

↓

GitHub Actions

↓

Compilação

↓

Testes

↓

Build

↓

Deploy

↓

Aplicação atualizada
```

---

## VARIÁVEIS SECRETAS

Senhas e tokens nunca devem ficar no código.

O GitHub possui:

```text
Settings

↓

Secrets and Variables

↓

Actions
```

Exemplo:

```text
AWS_KEY

DATABASE_PASSWORD

API_TOKEN
```

No YAML:

```yaml
env:
  TOKEN: ${{ secrets.API_TOKEN }}
```

Assim, informações sensíveis ficam protegidas.

---

## ESTRUTURA MENTAL

```text
Você faz um Push

↓

GitHub detecta um Evento

↓

Abre um Workflow

↓

Executa Jobs

↓

Cada Job executa vários Steps

↓

Resultado aparece na aba Actions
```

Ou de forma ainda mais resumida:

```text
Evento

↓

Workflow

↓

Job

↓

Step
```

---

## QUANDO USAR

- Executar testes automaticamente.
    
- Validar Pull Requests.
    
- Fazer Build do projeto.
    
- Automatizar Deploy.
    
- Gerar documentação.
    
- Executar tarefas recorrentes.
    
- Implementar pipelines de CI/CD.
    

==O GitHub Actions é a plataforma de automação do GitHub, permitindo que tarefas sejam executadas automaticamente sempre que um evento ocorre no repositório.==

==Através de arquivos YAML armazenados em `.github/workflows`, é possível criar pipelines completos de CI/CD que compilam, testam e até publicam aplicações sem intervenção manual, tornando o desenvolvimento muito mais rápido, seguro e profissional.==