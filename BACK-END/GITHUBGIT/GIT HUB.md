## COMO CRIAR UM REPÒSITORIO NO GITHUB.

==Criar um **repositório no GitHub** é o primeiro passo para armazenar e compartilhar um projeto utilizando controle de versão.==

Durante a criação do repositório, algumas informações importantes podem ser configuradas para organizar melhor o projeto.

O que é configurado ao criar um repositório?

- Nome do repositório.
- Descrição do projeto.
- Visibilidade (Público ou Privado).
- Arquivo `README.md`.
- Arquivo `.gitignore`.
- Licença de uso.

Como criar um repositório

1. Acesse o GitHub.
2. Clique em **New Repository**.
3. Preencha as informações desejadas.
4. Clique em **Create Repository**.

Após a criação, o GitHub fornecerá instruções para conectar um projeto local ao novo repositório.

> [!example]  
> Exemplo prático
> 
> Suponha que você esteja desenvolvendo um sistema de gerenciamento financeiro.
> 
> Você pode configurar o repositório da seguinte forma:
> 
> ```
> Nome: 
> gestor-financas
> Descrição:
> Sistema para controle de receitas e despesas pessoais.Visibilidade:
> Público
> ```
> 
> Após criar o repositório, será possível conectar seu projeto local utilizando:
> 
> ```
> git remote add origin https://github.com/usuario/gestor-financas.git
> ```

Informações importantes

**Nome do repositório

==É o identificador principal do projeto no GitHub.==

Boas práticas:

- Utilizar nomes curtos e descritivos.
- Evitar espaços e caracteres especiais.
- Preferir letras minúsculas e hífens.

Exemplo:

```
sistema-vendasapi-climagestor-financas
```

 **Descrição

A descrição serve para explicar rapidamente o objetivo do projeto.

Exemplo:

```
API desenvolvida em Java para gerenciamento de tarefas.
```

Ela pode ser alterada a qualquer momento.

### Licença

==A licença define como outras pessoas poderão utilizar, modificar ou distribuir seu projeto.==

Algumas das mais utilizadas são:

- MIT License
- Apache License 2.0
- GNU GPL v3
- BSD License

Caso nenhuma licença seja escolhida, o projeto continua protegido pelos direitos autorais do criador.

**README.md

O arquivo `README.md` normalmente contém:

- Descrição do projeto.
- Tecnologias utilizadas.
- Como executar o sistema.
- Exemplos de uso.
- Informações para contribuição.

É geralmente o primeiro arquivo visualizado por quem acessa o repositório.

 **.gitignore

O `.gitignore` permite definir arquivos e pastas que não devem ser enviados ao Git.

Exemplo:

```
.idea/target/*.log
```

Isso evita o versionamento de arquivos temporários ou gerados automaticamente.

Quando configurar essas informações

- Ao iniciar um novo projeto.
- Ao publicar um portfólio no GitHub.
- Ao criar projetos colaborativos.
- Ao disponibilizar um software open source.

==Embora todas essas configurações possam ser alteradas posteriormente, é importante conhecer sua finalidade para organizar corretamente o projeto desde o início.==

==Nome, descrição, licença, README e `.gitignore` são alguns dos elementos fundamentais para criar um repositório bem estruturado e fácil de manter ao longo do desenvolvimento.==

## ABA CODE

==A aba **Code** é a principal área de um repositório no GitHub, onde é possível visualizar e gerenciar os arquivos do projeto.==

Nela, encontram-se o código-fonte, a documentação, informações sobre a licença e diversas ferramentas para colaboração e gerenciamento do desenvolvimento.

O que a aba Code permite fazer?

- Visualizar o código-fonte do projeto.
- Acessar a documentação através do `README.md`.
- Consultar a licença do projeto.
- Criar e alternar entre branches.
- Adicionar ou enviar novos arquivos.
- Obter o link para clonar o repositório.

Principais recursos

**Código-fonte

A área central da aba exibe todos os arquivos e pastas do projeto.

Ao clicar em um arquivo, é possível visualizar seu conteúdo diretamente pelo navegador.

> [!example]  
> Exemplo prático
> 
> Um projeto Java pode apresentar a seguinte estrutura:
> 
> ```
> 📁 src
> 📁 docs
> 📄 README.md
> 📄 .gitignore
> 📄 pom.xml
> ```
> 
> Todos esses arquivos podem ser acessados e visualizados pela aba **Code**.

**README.md

==O arquivo `README.md` normalmente aparece em destaque na parte inferior da página do repositório.==

Ele costuma conter informações como:

- Objetivo do projeto.
- Tecnologias utilizadas.
- Instruções de instalação.
- Forma de utilização.
- Dados para contribuição.

Na maioria dos projetos open source, o README funciona como a documentação principal.

**Licença

Se o projeto possuir uma licença configurada, ela também poderá ser consultada na aba Code.

Exemplo:

```
MIT License
```

Isso informa aos usuários como o código pode ser utilizado, modificado ou distribuído.

**Branches

==A aba Code também permite visualizar e trocar de branches através do seletor localizado próximo ao topo da página.==

Por exemplo:

```
mainfeature-logincorrecao-bug
```

Essa funcionalidade facilita a navegação entre diferentes versões do projeto.

**Adicionar arquivos

Também é possível adicionar novos arquivos diretamente pelo GitHub.

As opções mais comuns são:

- Upload files
- Create new file

Esses recursos são úteis para pequenas alterações ou inclusão de documentos.

**Clonar o repositório

Na aba Code existe um botão chamado **Code**, que fornece as URLs para clonar o projeto.

Exemplo:

```
HTTPS
SSH
GitHub CLI
```

Esses links são utilizados com comandos como:

```
git clone <url-do-repositorio>
```

Quando utilizar a aba Code

- Navegar pelo código-fonte.
- Ler a documentação do projeto.
- Baixar ou clonar o repositório.
- Criar e alternar entre branches.
- Adicionar arquivos diretamente pelo GitHub.

==A aba Code é a principal interface de um repositório GitHub, reunindo o código-fonte, a documentação, as informações da licença e diversas ferramentas utilizadas no dia a dia do desenvolvimento colaborativo.==

==Além de permitir a visualização dos arquivos do projeto, ela também possibilita criar branches, adicionar arquivos e obter os links necessários para clonar o repositório.==

## ABA ISSUE 

==A aba **Issues** é utilizada para **registrar tarefas, melhorias, dúvidas e possíveis bugs relacionados ao projeto**.==

Ela funciona como um sistema de gerenciamento de atividades, ajudando a equipe a organizar o desenvolvimento e acompanhar o que ainda precisa ser implementado ou corrigido.

O que a aba Issues permite fazer?

- Registrar bugs encontrados no projeto.
- Criar tarefas e novas funcionalidades.
- Organizar o trabalho da equipe.
- Atribuir responsáveis para cada atividade.
- Utilizar labels para categorizar as issues.
- Escrever descrições utilizando Markdown.

Principais recursos

### Criar uma Issue

Para criar uma nova tarefa, basta acessar a aba **Issues** e clicar em:

```
New Issue
```

Durante a criação, normalmente são preenchidos:

- Título.
- Descrição.
- Label.
- Responsável (Assignee).

> [!example]  
> Exemplo prático
> 
> Um usuário encontrou um problema na tela de login.
> 
> A issue pode ser criada da seguinte forma:
> 
> ```
> Título:Erro ao validar senha do usuárioDescrição:Ao inserir uma senha inválida, o sistema encerra inesperadamente.
> ```
> 
> Depois, basta definir uma label e atribuir a tarefa a um desenvolvedor.

### Labels

==As labels servem para categorizar as issues e facilitar sua organização.==

Alguns exemplos comuns:

```
bugenhancementdocumentationhelp wantedquestion
```

Essas categorias ajudam a identificar rapidamente o tipo de atividade.

**Responsável (Assignee)

Cada issue pode ser atribuída a um ou mais membros da equipe.

Isso permite saber quem está encarregado de resolver determinado problema ou implementar uma funcionalidade.

Exemplo:

```
Assignee:Gustavo Sales
```

**Utilização de Markdown

==Assim como no arquivo `README.md`, as descrições das issues aceitam Markdown.==

Exemplo:

```
## ProblemaO botão de login não responde.
### Passos para reproduzir
1. Abrir a aplicação.
2. Inserir usuário e senha.
3. Clicar em Entrar.
```

Isso torna as descrições mais organizadas e fáceis de entender.

**Templates de Issues

Em muitos projetos existe um padrão para criação de novas issues.

Exemplo de template:

```
Descrição do problema:
Passos para reproduzir:
Comportamento esperado:
Informações adicionais:
```

Esses modelos ajudam a equipe a manter um padrão de documentação.

Quando utilizar a aba Issues

- Registrar bugs.
- Organizar tarefas do projeto.
- Planejar novas funcionalidades.
- Acompanhar o progresso da equipe.
- Centralizar discussões sobre melhorias.

==A aba Issues é uma das principais ferramentas de organização do GitHub, permitindo registrar problemas, criar tarefas e acompanhar o desenvolvimento do projeto de forma colaborativa.==

==Normalmente, cada issue possui uma descrição detalhada, uma label para classificação e um responsável pela sua execução, além de permitir o uso de Markdown para uma documentação mais clara e organizada.==

## ABA PULL REQUESTS

==A aba **Pull Requests** é utilizada para **propor a integração de alterações feitas em uma branch ao projeto principal**.==

Ela permite que o código seja revisado antes de ser incorporado à branch principal (`main` ou `master`), tornando o desenvolvimento mais seguro e organizado.

O que a aba Pull Requests permite fazer?

- Enviar novas funcionalidades para revisão.
- Corrigir bugs registrados nas Issues.
- Comparar as diferenças entre branches.
- Discutir alterações com outros desenvolvedores.
- Aprovar ou rejeitar mudanças antes do merge.

Como funciona um Pull Request

Normalmente, o fluxo de trabalho segue estas etapas:

```
Criar uma branch↓Desenvolver a funcionalidade
↓
Realizar commits
↓
Enviar a branch para o GitHub
↓
Abrir um Pull Request
↓
Revisão do código
↓
Merge na branch principal
```

Dessa forma, o código não é enviado diretamente para a `main`, reduzindo o risco de erros no projeto.

> [!example]  
> Exemplo prático
> 
> Um desenvolvedor criou a branch:
> 
> ```
> feature-login
> ```
> 
> Após implementar a funcionalidade, ele executa:
> 
> ```
> git push origin feature-login
> ```
> 
> No GitHub, será possível criar um Pull Request comparando:
> 
> ```
> feature-login → main
> ```
> 
> Outros membros da equipe poderão revisar o código antes da integração.

Principais recursos

**Comparação de código

==Ao criar um Pull Request, o GitHub exibe todas as diferenças entre a branch de origem e a branch de destino.==

É possível visualizar:

- Arquivos modificados.
- Linhas adicionadas.
- Linhas removidas.
- Histórico dos commits envolvidos.

**Revisão de código (Code Review)

Os colaboradores podem:

- Comentar linhas específicas do código.
- Solicitar alterações.
- Aprovar a implementação.
- Discutir possíveis melhorias.

Essa etapa é conhecida como **Code Review** e é uma prática muito comum no desenvolvimento profissional.

**Relacionamento com Issues

Um Pull Request pode estar vinculado a uma Issue.

Exemplo de descrição:

```
Closes #15
```

Quando o Pull Request for aprovado e integrado, a Issue de número 15 será encerrada automaticamente.

**Merge

Após a aprovação, o Pull Request pode ser integrado à branch principal através do botão:

```
Merge Pull Request
```

Com isso, as alterações passam a fazer parte do projeto.

Observação importante

⚠️ **Em equipes de desenvolvimento, normalmente não é permitido realizar commits diretamente na branch principal. Todo novo código deve passar por um Pull Request para ser analisado.**

Esse processo ajuda a manter a qualidade do projeto e reduz a ocorrência de erros.

Quando utilizar a aba Pull Requests

- Adicionar novas funcionalidades.
- Corrigir bugs do projeto.
- Revisar alterações antes do merge.
- Colaborar com outros desenvolvedores.
- Integrar branches de forma segura.

==A aba Pull Requests é uma das ferramentas mais importantes do GitHub, pois permite que novas alterações sejam revisadas antes de serem incorporadas ao projeto principal.==

==Normalmente, um Pull Request é criado a partir de uma branch de desenvolvimento e passa por uma análise da equipe antes de ser aprovado e integrado à branch `main` ou `master`.==

## ABA ACTIONS

==A aba **Actions** é a área do GitHub destinada à **automação de tarefas e fluxos de trabalho (Workflows)**.==

Por meio dela, é possível configurar processos automáticos para testar, compilar, validar e realizar o deploy de aplicações.

O que a aba Actions permite fazer?

- Automatizar tarefas do projeto.
- Executar testes automaticamente.
- Implementar processos de CI/CD.
- Realizar deploys para servidores ou serviços em nuvem.
- Automatizar verificações a cada commit ou Pull Request.

O que é CI/CD?

==CI/CD significa **Continuous Integration (Integração Contínua)** e **Continuous Delivery/Deployment (Entrega ou Implantação Contínua)**.==

Esses conceitos permitem que o código seja testado e disponibilizado automaticamente sempre que houver alterações no repositório.

```
Commit↓Execução automática dos testes↓Build da aplicação↓Deploy (opcional)
```

Esse processo reduz erros e agiliza o desenvolvimento.

> [!example]  
> Exemplo prático
> 
> Um projeto Java utiliza GitHub Actions para executar testes sempre que um Pull Request é criado.
> 
> O fluxo pode ser:
> 
> ```
> Desenvolvedor faz um commit↓Abre um Pull Request↓O GitHub executa os testes automaticamente↓Se todos os testes passarem, o código pode ser aprovado
> ```

Como funcionam as Actions

As automações são definidas em arquivos YAML localizados na pasta:

```
.github/workflows/
```

Exemplo de arquivo:

```
ci.yml
```

Nele são configurados os eventos que iniciarão o fluxo de trabalho, como:

- Push.
- Pull Request.
- Criação de tags.
- Execução agendada.

Exemplo simplificado de um workflow:

```
name: Java CIon: [push]jobs:  build:    runs-on: ubuntu-latest
```

Esse arquivo informa ao GitHub que o processo deve ser executado sempre que ocorrer um `push`.

Principais utilizações

### Integração Contínua (CI)

Permite executar automaticamente:

- Compilação do projeto.
- Testes unitários.
- Análise de qualidade de código.
- Verificação de dependências.

### Entrega ou Deploy Contínuo (CD)

==Além dos testes, é possível configurar a publicação automática da aplicação.==

Por exemplo:

- Publicar um site no GitHub Pages.
- Atualizar um servidor na nuvem.
- Gerar e publicar artefatos de uma nova versão.

Observação importante

⚠️ **Embora seja comum dizer que o GitHub Actions "atualiza a master automaticamente", na prática ele executa tarefas definidas pelo desenvolvedor. Essas tarefas podem incluir testes, builds e até merges ou deploys automáticos, dependendo da configuração do workflow.**

Quando utilizar a aba Actions

- Automatizar testes do projeto.
- Implementar pipelines de CI/CD.
- Realizar deploys automáticos.
- Reduzir tarefas manuais da equipe.
- Integrar o GitHub com outros serviços.

==A aba Actions transforma o GitHub em uma poderosa plataforma de automação, permitindo criar fluxos de trabalho que executam tarefas automaticamente sempre que determinados eventos acontecem no repositório.==

==Ela é amplamente utilizada para implementar processos de CI/CD, automatizando testes, builds e deploys, tornando o desenvolvimento mais rápido, seguro e eficiente.==

## ABA PROJECTS 

==A aba **Projects** é uma ferramenta do GitHub utilizada para **organizar tarefas, acompanhar o progresso do projeto e gerenciar o fluxo de trabalho da equipe**.==

Ela funciona como um quadro de gerenciamento visual, semelhante ao Trello, permitindo criar cartões que podem representar tarefas, bugs ou funcionalidades.

O que a aba Projects permite fazer?

- Criar quadros de gerenciamento de tarefas.
- Organizar o fluxo de desenvolvimento.
- Acompanhar o andamento das atividades.
- Integrar Issues e Pull Requests.
- Facilitar a colaboração entre os membros da equipe.

O método Kanban

==O GitHub Projects utiliza o conceito de **Kanban**, uma metodologia de organização baseada em colunas que representam as etapas do trabalho.==

Um fluxo bastante comum é:

```
Backlog↓Desenvolvimento↓Retorno de Qualidade↓Teste↓Finalizadas
```

À medida que o trabalho avança, os cartões são movidos entre as colunas.

> [!example]  
> Exemplo prático
> 
> Uma equipe está desenvolvendo um sistema de vendas.
> 
> Uma nova funcionalidade é criada como uma tarefa:
> 
> ```
> Criar tela de cadastro de clientes
> ```
> 
> Inicialmente, ela fica na coluna:
> 
> ```
> Backlog
> ```
> 
> Quando um desenvolvedor começa a trabalhar nela, o cartão é movido para:
> 
> ```
> Desenvolvimento
> ```
> 
> Após a implementação:
> 
> ```
> Retorno de Qualidade
> ```
> 
> Depois dos testes:
> 
> ```
> Finalizadas
> ```

Integração com Issues

Uma das grandes vantagens do GitHub Projects é a integração com as Issues.

É possível transformar uma Issue diretamente em um cartão do quadro, facilitando o acompanhamento do trabalho.

Exemplo:

```
Issue #15Corrigir erro de autenticação
```

Essa Issue pode ser adicionada ao Project e movimentada entre as colunas conforme o progresso.

Estrutura recomendada

==Uma organização bastante utilizada em equipes de desenvolvimento é:==

```
BacklogRetorno de QualidadeDesenvolvimentoTesteFinalizadas
```

Cada equipe pode adaptar essa estrutura conforme suas necessidades.

Semelhança com o Trello

A interface do GitHub Projects lembra bastante ferramentas de gerenciamento como o Trello.

Os cartões podem conter:

- Título.
- Descrição.
- Responsável.
- Labels.
- Data de entrega.
- Links para Issues e Pull Requests.

Isso facilita a visualização das atividades em andamento.

Quando utilizar a aba Projects

- Organizar tarefas do projeto.
- Gerenciar equipes de desenvolvimento.
- Acompanhar bugs e melhorias.
- Controlar o fluxo de trabalho utilizando Kanban.
- Centralizar Issues e Pull Requests em um único painel.

==A aba Projects transforma o GitHub em uma ferramenta completa de gerenciamento de projetos, permitindo organizar tarefas através de quadros Kanban e acompanhar o desenvolvimento de forma visual e colaborativa.==

==Sua integração com Issues e Pull Requests facilita a gestão do trabalho da equipe, tornando o fluxo de desenvolvimento muito mais organizado e eficiente.==

## ABA WIKI

==A aba **Wiki** é utilizada para **criar uma documentação mais completa e organizada sobre o projeto**.==

Ela funciona como um repositório de conhecimento, onde a equipe pode registrar informações importantes para desenvolvedores e usuários.

O que a aba Wiki permite fazer?

- Documentar funcionalidades do projeto.
- Registrar bugs conhecidos.
- Criar manuais de utilização.
- Armazenar guias de instalação e configuração.
- Centralizar informações importantes sobre o sistema.

Principais utilizações

### Documentação do projeto

A Wiki pode conter descrições detalhadas sobre o funcionamento da aplicação.

Exemplo:

```
Sistema de autenticação- Cadastro de usuários- Login- Recuperação de senha- Controle de permissões
```

Essa documentação facilita o entendimento do projeto por novos colaboradores.

> [!example]  
> Exemplo prático
> 
> Um projeto possui diversos módulos:
> 
> ```
> UsuáriosProdutosPedidosRelatórios
> ```
> 
> Na Wiki, pode ser criada uma página explicando como cada módulo funciona, quais são suas regras de negócio e como utilizá-lo.

### Bugs conhecidos

==A Wiki também pode armazenar uma lista de problemas já identificados que ainda não possuem solução definitiva.==

Exemplo:

```
Bug conhecido:Ao importar arquivos maiores que 100 MB, o sistema pode apresentar lentidão.
```

Isso ajuda a equipe a evitar retrabalho e informa os usuários sobre limitações conhecidas.

### Guias e tutoriais

Também é comum utilizar a Wiki para criar:

- Guias de instalação.
- Tutoriais de configuração.
- Padrões de desenvolvimento.
- Boas práticas da equipe.

Exemplo:

```
Como executar o projeto localmente1. Clonar o repositório.2. Instalar as dependências.3. Configurar o banco de dados.4. Executar a aplicação.
```

### Utilização de Markdown

==Assim como o `README.md` e as Issues, a Wiki aceita a sintaxe Markdown.==

Isso permite criar:

- Títulos.
- Listas.
- Tabelas.
- Blocos de código.
- Links entre páginas.

Exemplo:

```
# Sistema de Login## Funcionalidades- Cadastro- Autenticação- Recuperação de senha
```

Organização do conhecimento

Uma Wiki bem estruturada pode conter páginas como:

```
Página InicialInstalaçãoArquitetura do SistemaPadrões de CódigoBugs ConhecidosPerguntas Frequentes (FAQ)
```

Essa organização facilita a consulta das informações pela equipe.

Quando utilizar a aba Wiki

- Documentar funcionalidades do sistema.
- Registrar bugs conhecidos.
- Criar manuais técnicos.
- Armazenar padrões e procedimentos da equipe.
- Centralizar o conhecimento do projeto.

==A aba Wiki funciona como uma base de conhecimento do projeto, permitindo criar uma documentação mais extensa e organizada do que a apresentada no `README.md`.==

==Ela é amplamente utilizada para registrar funcionalidades, guias de utilização, bugs conhecidos e outras informações importantes, tornando o compartilhamento de conhecimento muito mais eficiente dentro da equipe.==

## ABA INSIGTHS 

==A aba **Insights** é utilizada para **visualizar estatísticas e informações detalhadas sobre a atividade do repositório**.==

Ela fornece diversos relatórios que ajudam a acompanhar a evolução do projeto e a participação dos colaboradores.

O que a aba Insights permite visualizar?

- Contribuidores do projeto.
- Quantidade de commits realizados.
- Forks do repositório.
- Histórico de atividade.
- Crescimento e evolução do projeto.
- Estatísticas sobre branches e código.

Principais recursos

### Contributors

A seção **Contributors** mostra quem participou do desenvolvimento do projeto.

Ela apresenta informações como:

- Nome dos colaboradores.
- Quantidade de commits.
- Percentual aproximado de contribuição.

> [!example]  
> Exemplo prático
> 
> Um projeto pode apresentar a seguinte estatística:
> 
> ```
> Gustavo Sales     45 commitsMaria Silva       18 commitsJoão Pereira      10 commits
> ```
> 
> Dessa forma, é possível identificar rapidamente a participação de cada desenvolvedor.

### Commit Activity

==A área de atividade de commits exibe gráficos mostrando a frequência das alterações realizadas no projeto ao longo do tempo.==

Esses gráficos ajudam a analisar períodos de maior ou menor desenvolvimento.

Exemplo:

```
Janeiro   ██████Fevereiro ████████Março     ████
```

### Forks

A aba Insights também informa quantas vezes o projeto foi copiado através do recurso de **Fork**.

Isso é especialmente importante em projetos open source, pois indica o interesse da comunidade.

Exemplo:

```
Forks: 120
```

### Network

A visualização de rede (Network) permite acompanhar a relação entre forks, branches e commits do projeto.

Ela mostra como o desenvolvimento evoluiu ao longo do tempo e quais alterações foram incorporadas.

### Traffic

==Alguns repositórios também disponibilizam informações de tráfego, como:==

- Número de visitantes.
- Quantidade de clones.
- Origem dos acessos.

Esses dados ajudam a medir o alcance do projeto.

Importância da aba Insights

Através dessas estatísticas, é possível:

- Acompanhar a produtividade da equipe.
- Entender a evolução do projeto.
- Analisar a participação dos colaboradores.
- Observar o crescimento da comunidade em projetos públicos.

Quando utilizar a aba Insights

- Consultar estatísticas do repositório.
- Verificar a atividade dos colaboradores.
- Acompanhar a evolução do projeto.
- Analisar forks, commits e contribuições.
- Obter uma visão geral do desenvolvimento.

==A aba Insights reúne diversas métricas e relatórios sobre o repositório, permitindo acompanhar sua evolução desde o início e entender como o projeto está sendo desenvolvido.==

==Informações como contribuidores, commits, forks e atividade geral ajudam a equipe a analisar o progresso do projeto e a participação de cada desenvolvedor.==

## ABA SETTINGS

==A aba **Settings** é a área responsável pelas **configurações gerais do repositório no GitHub**.==

Nela é possível alterar informações importantes do projeto, gerenciar recursos disponíveis e controlar o acesso dos colaboradores.

O que a aba Settings permite fazer?

- Alterar o nome do repositório.
- Modificar a descrição do projeto.
- Alterar a visibilidade (Público ou Privado).
- Adicionar ou remover colaboradores.
- Habilitar ou desabilitar recursos do GitHub.
- Excluir o repositório.

Principais recursos

### Informações do repositório

Na seção principal das configurações é possível alterar dados básicos, como:

- Nome do repositório.
- Descrição.
- Site (Website).
- Visibilidade.

> [!example]  
> Exemplo prático
> 
> Um projeto inicialmente chamado:
> 
> ```
> sistema-java
> ```
> 
> pode ser renomeado para:
> 
> ```
> sistema-gerenciamento
> ```
> 
> sem a necessidade de criar um novo repositório.

### Gerenciamento de colaboradores

==A aba Settings também permite adicionar pessoas para colaborar no projeto.==

Ao adicionar um colaborador, ele poderá clonar o repositório, criar branches, abrir Pull Requests e, dependendo das permissões concedidas, realizar outras operações administrativas.

Exemplo:

```
Collaborators+ Gustavo Sales+ Maria Silva
```

Essa funcionalidade é bastante utilizada em projetos privados e trabalhos em equipe.

### Recursos do repositório

Também é possível ativar ou desativar algumas funcionalidades do GitHub, como:

- Issues.
- Wiki.
- Projects.
- Discussions.

Isso permite adaptar o ambiente às necessidades do projeto.

### Alteração de visibilidade

==O proprietário pode definir se o repositório será:==

```
PublicouPrivate
```

- **Public:** qualquer pessoa pode visualizar o código.
- **Private:** apenas usuários autorizados têm acesso.

### Exclusão do repositório

A aba Settings também contém a opção de remover permanentemente o projeto.

⚠️ **A exclusão de um repositório é uma ação irreversível e apaga todo o conteúdo armazenado no GitHub.**

Para confirmar a operação, normalmente é necessário digitar o nome completo do repositório.

Exemplo:

```
usuario/meu-projeto
```

Quando utilizar a aba Settings

- Configurar informações do projeto.
- Adicionar colaboradores.
- Gerenciar recursos do GitHub.
- Alterar a visibilidade do repositório.
- Excluir ou transferir o projeto.

==A aba Settings concentra todas as configurações administrativas do repositório, permitindo personalizar o ambiente de desenvolvimento e controlar o acesso dos colaboradores.==

==É nela que podem ser alterados o nome do projeto, suas funcionalidades disponíveis e as permissões de acesso, além de possibilitar a exclusão do repositório quando necessário.==

## GIST

==Um **Gist** é um recurso do GitHub utilizado para **armazenar e compartilhar pequenos trechos de código ou anotações de forma rápida e organizada**.==

Ele funciona como um mini repositório, sendo muito útil para guardar soluções, exemplos de código, scripts e configurações que podem ser reutilizados futuramente.

O que um Gist permite fazer?

- Armazenar pequenos blocos de código.
- Compartilhar soluções através de um link.
- Salvar anotações e scripts úteis.
- Criar Gists públicos ou privados.
- Versionar alterações automaticamente.

Como criar um Gist

1. Acesse a área de Gists no GitHub.
2. Informe um nome para o arquivo.
3. Cole o código ou texto desejado.
4. Escolha entre Gist público ou secreto.
5. Clique em **Create secret gist** ou **Create public gist**.

> [!example]  
> Exemplo prático
> 
> Você criou uma função em Java para validar CPF e deseja guardá-la para reutilizar em outros projetos.
> 
> Basta criar um Gist contendo:
> 
> ```
> public boolean validarCPF(String cpf){    // implementação}
> ```
> 
> Após salvar, o GitHub gerará um link que poderá ser compartilhado ou acessado posteriormente.

Tipos de Gist

### Public Gist

==Pode ser encontrado e visualizado por qualquer pessoa.==

É indicado para compartilhar exemplos de código, snippets ou soluções com a comunidade.

### Secret Gist

Embora seja chamado de "secreto", ele não é totalmente privado.

Quem possuir o link poderá acessar o conteúdo, mas ele não aparecerá em buscas públicas do GitHub.

Essa opção é bastante utilizada para compartilhar códigos específicos com colegas ou armazenar anotações pessoais.

Versionamento

Assim como um repositório comum, o Gist mantém um histórico das alterações realizadas.

Isso permite visualizar versões anteriores e acompanhar a evolução do código.

Exemplo:

```
Versão 1↓Versão 2↓Versão 3
```

Cada modificação fica registrada automaticamente.

Compartilhamento

==Todo Gist possui uma URL própria, que pode ser enviada para outras pessoas.==

Exemplo:

```
https://gist.github.com/usuario/xxxxxxxxxxxxxxxx
```

Isso facilita o compartilhamento de soluções rápidas sem a necessidade de criar um repositório completo.

Quando utilizar um Gist

- Salvar snippets de código.
- Armazenar scripts pequenos.
- Compartilhar soluções técnicas.
- Guardar configurações ou comandos úteis.
- Criar anotações reutilizáveis.

==O Gist pode ser entendido como um pequeno repositório voltado para trechos de código e anotações, oferecendo versionamento e compartilhamento de forma simples e rápida.==

==Ele é muito utilizado por desenvolvedores para armazenar soluções interessantes, exemplos de implementação e scripts que podem ser reutilizados em diversos projetos.==

## ENCONTRANDO REPÓSITORIOS

==O GitHub não é apenas uma plataforma para armazenar projetos, mas também uma enorme comunidade onde é possível **explorar, estudar e colaborar com repositórios de outros desenvolvedores**.==

Através da busca do GitHub, você pode encontrar projetos open source, aprender novas tecnologias e até contribuir com melhorias.

O que é possível fazer ao encontrar um repositório?

- Visualizar o código-fonte.
- Estudar a estrutura e as boas práticas utilizadas.
- Ler a documentação do projeto.
- Dar uma estrela (Star).
- Criar um Fork para ter uma cópia própria.
- Contribuir através de Pull Requests.

Como encontrar repositórios

O GitHub possui uma barra de pesquisa que permite buscar por:

- Nome do projeto.
- Linguagem de programação.
- Tecnologias específicas.
- Usuários e organizações.

> [!example]  
> Exemplo prático
> 
> Você deseja aprender mais sobre Java e Spring Boot.
> 
> Basta pesquisar por:
> 
> ```
> spring boot
> ```
> 
> ou
> 
> ```
> java api
> ```
> 
> O GitHub exibirá diversos projetos públicos que podem ser explorados e estudados.

Aprendendo com outros desenvolvedores

==Uma das maiores vantagens do GitHub é a possibilidade de analisar o código de desenvolvedores experientes.==

Ao explorar um repositório, você pode observar:

- Organização das pastas.
- Padrões de arquitetura.
- Convenções de código.
- Estrutura do README.
- Fluxo de desenvolvimento.

Essa prática é muito comum entre programadores iniciantes e profissionais.

### Star

O recurso **Star** funciona como um marcador de favoritos.

Ao clicar em **Star**, o projeto é salvo em sua lista de repositórios favoritos para consulta futura.

Exemplo:

```
⭐ Spring Boot Examples
```

Isso não cria uma cópia do projeto, apenas o adiciona à sua coleção de favoritos.

### Fork

==O **Fork** cria uma cópia completa de um repositório na sua própria conta do GitHub.==

Isso permite:

- Estudar o projeto livremente.
- Realizar modificações.
- Desenvolver novas funcionalidades.
- Enviar contribuições ao projeto original através de Pull Requests.

Fluxo simplificado:

```
Repositório Original↓Fork↓Seu Repositório↓Alterações↓Pull Request (opcional)
```

Essa é uma das principais formas de colaboração em projetos open source.

Quando utilizar esses recursos

- Aprender novas tecnologias.
- Estudar boas práticas de programação.
- Salvar projetos interessantes.
- Contribuir com software open source.
- Criar versões próprias de projetos existentes.

==O GitHub é uma grande plataforma de compartilhamento de conhecimento, permitindo encontrar milhares de projetos públicos para estudo e colaboração.==

==Além de visualizar o código-fonte, é possível favoritar projetos com o recurso **Star** ou criar uma cópia própria através do **Fork**, facilitando o aprendizado e a participação na comunidade open source.==

## CI/CD

==**CI/CD** é um conjunto de práticas utilizadas para **automatizar a integração, os testes e a entrega de software**, tornando o desenvolvimento mais rápido, seguro e eficiente.==

A sigla significa:

- **CI (Continuous Integration)** → Integração Contínua.
- **CD (Continuous Delivery ou Continuous Deployment)** → Entrega Contínua ou Implantação Contínua.

O objetivo é reduzir tarefas manuais e garantir que o código esteja sempre funcionando corretamente.

**O que é Continuous Integration (CI)?

A **Integração Contínua** consiste em integrar frequentemente as alterações dos desenvolvedores ao repositório principal.

Sempre que um novo código é enviado (por exemplo, através de um `git push` ou Pull Request), uma série de verificações automáticas pode ser executada.

Essas verificações geralmente incluem:

- Compilação do projeto (Build).
- Execução de testes automatizados.
- Análise de qualidade do código.
- Verificação de dependências.

> [!example]  
> Exemplo prático
> 
> Um desenvolvedor implementa uma nova funcionalidade e executa:
> 
> ```
> git add .git commit -m "Implementa sistema de login"
> git push origin feature-login
> ```
> 
> Automaticamente, o sistema de CI pode:
> 
> ```
> Baixar o código
> ↓
> Compilar o projeto
> ↓
> Executar os testes
> ↓
> Informar se houve sucesso ou falha
> ```

Se algum teste falhar, a equipe é avisada imediatamente.

**O que é Continuous Delivery (CD)?

==A **Entrega Contínua** automatiza a preparação do software para produção.==

Após a aprovação dos testes, o sistema deixa uma nova versão pronta para ser publicada.

Fluxo simplificado:

```
Commit
↓
Build
↓
Testes
↓
Pacote pronto para Deploy
```

A publicação final normalmente ainda depende de uma aprovação manual.

**O que é Continuous Deployment?

Existe uma segunda interpretação para o "CD":

**Continuous Deployment (Implantação Contínua).**

Nesse modelo, após todos os testes serem aprovados, o sistema é publicado automaticamente, sem intervenção humana.

Fluxo:

```
Commit
↓
Build
↓
Testes
↓
Deploy automático em produção
```

Isso é muito comum em grandes empresas e plataformas web.


**Fluxo completo do CI/CD

==Um pipeline de CI/CD normalmente segue a seguinte sequência:==

```
Desenvolvedor faz um commit
↓
git push
↓
Servidor de CI/CD detecta a alteração
↓
Compila o projeto
↓
Executa os testes
↓
Valida a qualidade do código
↓
Prepara a nova versão
↓
Realiza o deploy (opcional)
```

Esse conjunto de etapas automatizadas é chamado de **Pipeline**.

**Ferramentas populares de CI/CD

Algumas das plataformas mais utilizadas são:

- GitHub Actions
- GitLab CI/CD
- Jenkins
- Azure DevOps
- CircleCI
- Travis CI

Essas ferramentas executam os pipelines configurados pelo desenvolvedor.

**Vantagens do CI/CD

- Detecta erros rapidamente.
- Reduz tarefas manuais.
- Facilita o trabalho em equipe.
- Aumenta a qualidade do software.
- Permite entregas mais rápidas e frequentes.
- Diminui o risco de problemas em produção.

**Exemplo do dia a dia

Imagine que uma equipe esteja desenvolvendo um sistema bancário.

Sem CI/CD:

```
Programador faz alteração
↓
Outro programador integra manualmente
↓
Alguém executa os testes
↓
Alguém faz o deploy
```

Com CI/CD:

```
Programador faz um commit
↓
GitHub Actions inicia automaticamente
↓
Sistema compila
↓
Testes são executados
↓
Nova versão é publicada
```

Tudo acontece de forma automática.

**Quando utilizar CI/CD

- Projetos desenvolvidos em equipe.
- Aplicações web.
- APIs.
- Sistemas corporativos.
- Projetos open source.
- Qualquer software que receba atualizações frequentes.

==CI/CD é uma metodologia que automatiza a integração, os testes e a entrega de software, permitindo que novas funcionalidades sejam verificadas e disponibilizadas de maneira rápida e confiável.==

==Na prática, sempre que um desenvolvedor envia código para o repositório, ferramentas como GitHub Actions podem compilar o projeto, executar testes e até realizar o deploy automaticamente, tornando o processo de desenvolvimento muito mais eficiente.==
