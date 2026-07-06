## CONTROLE DE VERSÃO

Controle de versão é uma prática utilizada para registrar e gerenciar as alterações feitas em arquivos ao longo do tempo. Ele permite acompanhar o histórico de modificações de um projeto, identificar quem realizou cada alteração, recuperar versões anteriores e colaborar com outras pessoas sem que o trabalho de um sobrescreva o do outro.

Imagine que você está desenvolvendo um sistema em Java. Em um dia você implementa o cadastro de usuários, no outro adiciona um sistema de login e, depois, cria novas funcionalidades. Se algum erro surgir ou uma alteração causar problemas, o controle de versão permite retornar facilmente a uma versão anterior do projeto. Além disso, ele mantém um histórico completo das mudanças realizadas, facilitando a organização e a manutenção do software.

A ferramenta de controle de versão mais utilizada atualmente é o Git. Com ela, os desenvolvedores criam registros chamados _commits_, que funcionam como fotografias do projeto em determinado momento. Cada commit armazena o estado dos arquivos e uma descrição da alteração realizada, permitindo acompanhar a evolução do sistema.

O controle de versão é amplamente utilizado no desenvolvimento de software, tanto em projetos individuais quanto em equipes. Em ambientes corporativos, ele é considerado uma habilidade essencial, pois possibilita que vários desenvolvedores trabalhem simultaneamente no mesmo projeto de forma organizada e segura. Ferramentas como o Git podem ser integradas a plataformas online, como o [GitHub](https://github.com?utm_source=chatgpt.com), que permitem armazenar repositórios na nuvem, compartilhar código e colaborar com outros profissionais.

Em resumo, o controle de versão é um mecanismo que registra a evolução de um projeto, oferecendo segurança, organização e facilidade para gerenciar alterações, tornando-se indispensável no desenvolvimento moderno de software.

## O QUE É GIT?

O Git é um sistema de controle de versão distribuído criado por Linus Torvalds em 2005 para auxiliar no desenvolvimento do kernel do Linux. Seu principal objetivo é controlar as alterações realizadas em arquivos e permitir que vários desenvolvedores trabalhem simultaneamente em um mesmo projeto de forma eficiente e segura.

Diferentemente de sistemas tradicionais, ==o Git é distribuído. Isso significa que cada desenvolvedor possui uma cópia completa do repositório em sua máquina, incluindo todo o histórico de alterações==. Dessa forma, é possível trabalhar mesmo sem conexão com a internet, criar versões locais do projeto e sincronizar as mudanças posteriormente com um servidor remoto.

O Git funciona por meio de um repositório, que é a estrutura onde ficam armazenados os arquivos do projeto e todo o histórico de modificações. Sempre que um desenvolvedor altera um arquivo, essas mudanças não são registradas automaticamente. ==Primeiro, elas precisam ser adicionadas à área de preparação (_staging area_) utilizando o comando `git add`. Em seguida, é criado um _commit_ com `git commit`, registrando oficialmente as alterações no histórico do projeto.==

Um commit pode ser entendido como uma fotografia do estado do projeto em um determinado momento. Cada commit possui um identificador único (hash), informações sobre o autor, data e uma mensagem descritiva. Isso permite rastrear exatamente o que foi alterado e quando a alteração ocorreu.

Uma das características mais importantes do Git é o conceito de _branches_ (ramificações). Uma branch é uma linha independente de desenvolvimento. ==Em vez de modificar diretamente a versão principal do projeto, o desenvolvedor pode criar uma branch para desenvolver uma nova funcionalidade, corrigir um erro ou testar uma ideia.== Quando o trabalho estiver concluído, as alterações podem ser integradas à branch principal por meio de um processo chamado _merge_.

Por exemplo, imagine que você esteja desenvolvendo um sistema de gerenciamento financeiro. A versão principal contém funcionalidades estáveis. Você deseja implementar um módulo de relatórios. Em vez de alterar diretamente a versão principal, cria uma branch chamada `relatorios`, desenvolve a funcionalidade nela e, após os testes, realiza o merge com a branch principal. Esse processo reduz riscos e mantém o projeto organizado.

Outro conceito fundamental é o repositório remoto. E==mbora o Git funcione localmente, ele geralmente é integrado a plataformas como o [GitHub](https://github.com?utm_source=chatgpt.com), o [GitLab](https://gitlab.com?utm_source=chatgpt.com) e o [Bitbucket](https://bitbucket.org?utm_source=chatgpt.com). Esses serviços permitem armazenar repositórios na nuvem, compartilhar código, realizar backups e colaborar com outros desenvolvedores.==

O fluxo básico de trabalho no Git normalmente segue esta sequência:

```
git clone URL
git status
git add .
git commit -m "Descrição da alteração"
git pullgit push
```

Nesse fluxo, o desenvolvedor obtém uma cópia do projeto (git clone url), realiza alterações (git status), registra as mudanças localmente (git add .) e envia o resultado para o repositório remoto (git commit -m "descrição").

O Git também oferece mecanismos para desfazer alterações. Caso um arquivo seja modificado por engano, é possível restaurá-lo. ==Se um commit apresentar problemas, pode-se voltar a versões anteriores ou criar um novo commit que reverta as mudanças. Essas funcionalidades aumentam significativamente a segurança durante o desenvolvimento.==

Outro aspecto importante é a resolução de conflitos. Quando duas pessoas alteram a mesma parte de um arquivo, o Git identifica o conflito e solicita que o desenvolvedor escolha qual versão deve ser mantida ou como as alterações devem ser combinadas. Esse mecanismo é essencial para o trabalho colaborativo em equipes.

Atualmente, o Git é considerado uma das ferramentas mais importantes para qualquer desenvolvedor de software. Empresas de todos os portes utilizam Git em seus processos de desenvolvimento, integração contínua (CI/CD), revisão de código e gerenciamento de projetos. Para um estudante de Análise e Desenvolvimento de Sistemas ou alguém buscando estágio em desenvolvimento, ==dominar Git é tão importante quanto conhecer uma linguagem de programação==, pois praticamente todos os ambientes profissionais dependem dele para organizar e controlar a evolução dos sistemas.

## O QUE É UM REPOSITORIO?

==Um repositório é a estrutura fundamental utilizada pelo Git para armazenar e gerenciar um projeto. Mais do que uma simples pasta de arquivos, ele contém todo o código-fonte, o histórico de alterações, informações sobre versões, branches, commits, configurações e demais dados necessários para controlar a evolução do software.==

Quando um desenvolvedor cria um repositório, o Git passa a monitorar os arquivos daquele projeto, registrando todas as alterações realizadas. Isso permite que cada mudança fique armazenada no histórico, possibilitando consultar versões anteriores, identificar quem realizou determinada modificação e recuperar estados antigos do projeto caso seja necessário.

### É onde o código será armazenado

O repositório funciona como o local oficial de armazenamento do projeto. Todos os arquivos relacionados ao desenvolvimento ficam organizados dentro dele, incluindo códigos-fonte, documentos, imagens, arquivos de configuração e outros recursos utilizados pela aplicação.

==Além dos arquivos atuais, o repositório também guarda todas as versões anteriores do projeto.== Isso significa que o Git não apenas armazena o estado atual dos arquivos, mas também mantém um histórico completo de sua evolução. Dessa forma, é possível consultar como determinado arquivo era há semanas, meses ou até anos.

Por exemplo, em um sistema de gerenciamento financeiro desenvolvido em Java, o repositório pode armazenar:

- Código das telas;
- Classes Java;
- Banco de dados;
- Arquivos de configuração;
- Documentação do projeto;
- Histórico completo de todas as alterações realizadas.

### Na maioria das vezes, cada projeto tem um repositório

==Em ambientes profissionais, normalmente cada sistema ou aplicação possui seu próprio repositório. Isso facilita a organização e o gerenciamento do código.==

Imagine uma empresa que possui três sistemas:

- Sistema de RH;
- Sistema Financeiro;
- Sistema de Controle de Estoque.

O mais comum é que cada um desses sistemas tenha seu próprio repositório. Dessa forma, as alterações realizadas em um projeto não afetam os demais.

Essa separação também facilita:

- Controle de permissões;
- Organização do código;
- Gerenciamento de versões;
- Controle de acessos da equipe;
- Automatização de deploys e testes.

==Em projetos muito grandes, pode haver até múltiplos repositórios para um mesmo produto, cada um responsável por um componente específico.==

### Quando criamos um repositório estamos iniciando um projeto

Ao executar o comando:

```
git init
```

==o Git cria uma pasta oculta chamada `.git`.==

Essa pasta é o coração do repositório. Ela contém todas as informações necessárias para que o Git funcione corretamente.

Dentro dela são armazenados:

- Histórico de commits;
- Referências de branches;
- Configurações do repositório;
- Tags;
- Objetos do Git;
- Informações de merge;
- Dados de sincronização com servidores remotos.

A partir desse momento, o projeto passa a ser controlado pelo Git.

Mesmo que o diretório contenha apenas um arquivo simples, o Git já consegue registrar alterações, criar versões e acompanhar toda a evolução do projeto.

### O repositório pode ser enviado para servidores especializados

Embora o Git funcione completamente de forma local, é muito comum utilizar servidores remotos para armazenar cópias dos repositórios.

Esses servidores oferecem diversas vantagens:

- Backup do código;
- Compartilhamento entre desenvolvedores;
- Controle de permissões;
- Integração com ferramentas de CI/CD;
- Revisão de código;
- Gerenciamento de tarefas.

Entre os serviços mais conhecidos estão:

- [GitHub](https://github.com?utm_source=chatgpt.com)
- [GitLab](https://gitlab.com?utm_source=chatgpt.com)
- [Bitbucket](https://bitbucket.org?utm_source=chatgpt.com)

Quando utilizamos o comando:

```
git push
```

==as alterações locais são enviadas para o servidor remoto==.

Quando utilizamos:

```
git pull
```

==as alterações do servidor são baixadas para a máquina local.==

Esse mecanismo permite que várias pessoas trabalhem simultaneamente no mesmo projeto.

### Cada desenvolvedor pode baixar o repositório

Uma das características mais importantes do Git é seu modelo distribuído.

Quando um desenvolvedor executa:

```
git clone URL_DO_REPOSITORIO
```

==ele não baixa apenas os arquivos atuais do projeto.==

Ele recebe:

- Todo o código-fonte;
- Todo o histórico de commits;
- Todas as branches;
- Todas as tags;
- Todas as versões do projeto.

Na prática, ele passa a possuir uma cópia completa do repositório.

Isso é diferente de sistemas centralizados, nos quais o servidor possui a única cópia completa do projeto.

### Criando versões diferentes na própria máquina

Após clonar o repositório, cada desenvolvedor pode trabalhar independentemente.

Por exemplo:

- João desenvolve a funcionalidade de login;
- Maria desenvolve o cadastro de clientes;
- Pedro corrige erros encontrados no sistema.

Cada um cria sua própria branch:

```
git switch -c logingit switch -c cadastro-clientesgit switch -c correcao-erros
```

As alterações ficam isoladas até que sejam concluídas.

Quando o desenvolvimento termina, as branches podem ser unidas à principal através do comando:

```
git merge
```

==Esse modelo permite que dezenas ou até centenas de desenvolvedores trabalhem simultaneamente no mesmo sistema sem sobrescrever o trabalho uns dos outros==.

### Por que os repositórios são tão importantes?

==Sem repositórios, o desenvolvimento moderno de software seria extremamente complexo. Seria necessário criar diversas cópias de pastas com nomes como:==

```
Projeto_Final
Projeto_Final_Atualizado
Projeto_Final_Versao2
Projeto_Final_Versao2_Corrigido
Projeto_Final_VersaoFinalAgoraVai
```

O Git elimina esse problema armazenando todo o histórico dentro do repositório e permitindo recuperar qualquer versão a qualquer momento.

Por isso, o repositório é considerado a base do controle de versão. Ele centraliza o código, registra a evolução do projeto, facilita o trabalho em equipe e garante segurança no desenvolvimento de software.

