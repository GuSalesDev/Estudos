## O QUE É UMA BRENCH?

==Uma **Branch** é um recurso do Git que permite criar uma linha de desenvolvimento separada dentro de um projeto.==

Ela é utilizada para desenvolver novas funcionalidades, corrigir bugs ou testar alterações sem modificar a versão principal do sistema.

O que uma Branch faz?

- Cria uma cópia independente do projeto.
- Permite trabalhar em novas funcionalidades sem afetar o código principal.
- Facilita o trabalho em equipe, pois cada desenvolvedor pode utilizar sua própria branch.
- Após a conclusão das alterações, a branch pode ser unida à principal através do processo de **merge**.

Como funciona

Quando um repositório Git é criado, ele inicia com uma branch principal.

==Antigamente essa branch era chamada de `master`, porém atualmente a maioria dos projetos utiliza o nome `main`.==

Enquanto o projeto evolui, novas branches podem ser criadas para desenvolver recursos específicos.

> [!example]  
> Exemplo prático
> 
> Imagine que um sistema possui a branch principal:
> 
> ```
> main
> ```
> 
> Você precisa desenvolver uma tela de login.
> 
> Em vez de alterar diretamente a branch principal, cria uma nova branch:
> 
> ```
> login
> ```
> 
> Todo o desenvolvimento será realizado nela.
> 
> Após concluir e testar a funcionalidade, ela poderá ser integrada à branch principal.

Criando uma branch

```
git branch nome-da-branch
```

> [!example]
> Exemplo:
> 
> ```
> git branch login
> ```
> 
> Listando as branches existentes
> 
> ```
> git branch
> ```
> 
> O Git exibirá algo semelhante a:
> 
> ```
> * main  login
> ```

O símbolo `*` indica a branch em que você está trabalhando no momento.

A importância das Branches

==Em projetos profissionais, é muito comum que cada nova funcionalidade (feature), correção de bug (bugfix) ou melhoria seja desenvolvida em uma branch separada.==

Essa estratégia traz diversas vantagens:

- Evita conflitos no código principal.
- Permite que várias pessoas trabalhem simultaneamente.
- Facilita testes antes da publicação.
- Torna o controle de versões mais organizado e seguro.

==Após a finalização das alterações, as branches são unidas à branch principal através do comando `git merge`, formando a versão final do projeto.==

## GIT BRANCH

==O comando **`git branch`** é utilizado para visualizar, criar e gerenciar as branches de um repositório Git.==

As branches permitem que novas funcionalidades sejam desenvolvidas de forma isolada, sem alterar a versão principal do projeto.

O que o `git branch` faz?

- Lista todas as branches existentes no repositório.
- Cria novas branches para desenvolvimento.
- Identifica em qual branch você está trabalhando.
- Auxilia na organização do fluxo de desenvolvimento.

Como utilizar:

Visualizar as branches disponíveis

```
git branch
```

O Git exibirá algo semelhante a:

```
* main  login  cadastro
```

O símbolo `*` indica a branch atualmente ativa.

Criar uma nova branch

```
git branch nome-da-branch
```

Exemplo:

```
git branch feature-login
```

Após a execução do comando, a nova branch será criada, mas você continuará na branch atual.

> [!example]  
> Exemplo prático
> 
> Você está trabalhando na branch principal:
> 
> ```
> * main
> ```
> 
> E precisa desenvolver uma funcionalidade de cadastro de usuários.
> 
> Crie uma nova branch:
> 
> ```
> git branch cadastro-usuarios
> ```
> 
> Agora, ao executar:
> 
> ```
> git branch
> ```
> 
> O resultado será:
> 
> ```
> * main  cadastro-usuarios
> ```
> 
> A branch foi criada, mas você ainda está na `main`.

Observação importante

==O comando `git branch` apenas cria ou lista branches. Para começar a trabalhar em uma nova branch, é necessário acessá-la utilizando o comando `git switch` ou `git checkout`.==

Exemplo:

```
git switch cadastro-usuarios
```

ou

```
git checkout cadastro-usuarios
```

==No dia a dia de um desenvolvedor, os comandos `git branch` e `git switch` são utilizados constantemente para organizar o desenvolvimento de novas funcionalidades e manter o código principal estável.==
## GIT BRANCH -D

==O comando **`git branch -d`** é utilizado para **deletar uma branch que não será mais utilizada**.==

Normalmente, uma branch é removida após suas alterações terem sido incorporadas à branch principal.

⚠️ **Atenção:** não é possível excluir a branch em que você está trabalhando no momento. Antes, é necessário trocar para outra branch.

O que o `git branch -d` faz?

- Remove uma branch local do repositório.
- Ajuda a manter o projeto organizado.
- Exclui apenas a referência da branch, não afetando outras branches.
- Impede a exclusão caso a branch ainda possua alterações não mescladas.

Como utilizar

Deletar uma branch

```
git branch -d nome-da-branch
```

Exemplo:

```
git branch -d feature-login
```

> [!example]  
> Exemplo prático
> 
> Suponha que você tenha as seguintes branches:
> 
> ```
> * main  
> * feature-login
> ```
> 
> Após finalizar e unir a funcionalidade de login à branch principal, você pode remover a branch:
> 
> ```
> git branch -d feature-login
> ```
> 
> Ao executar:
> 
> ```
> git branch
> ```
> 
> O resultado será:
> 
> ```
> * main
> ```

Exclusão forçada

==Caso a branch ainda não tenha sido mesclada e você realmente queira removê-la, é possível utilizar a flag `-D` (maiúscula).==

```
git branch -D nome-da-branch
```

⚠️ **Essa operação pode causar perda de trabalho, pois descarta commits que existem apenas naquela branch.**

Quando utilizar

- Quando uma branch foi criada por engano.
- Quando uma funcionalidade já foi integrada ao projeto.
- Para manter o repositório mais organizado.

==No desenvolvimento profissional, não é muito comum apagar branches importantes, pois elas ajudam a preservar o histórico do trabalho realizado. Geralmente, a exclusão acontece quando uma branch foi criada incorretamente ou quando seu ciclo de vida já terminou.==
## GIT CHECKOUT (BRANCHS)

==O comando **`git checkout`** pode ser utilizado para **trocar de branch** e também para **restaurar arquivos**, dependendo dos parâmetros utilizados.==

⚠️ **Atenção:** ao trocar de branch, alterações que ainda não foram commitadas podem ser levadas para a nova branch, desde que não haja conflitos.

O que o `git checkout` faz?

- Permite alternar entre branches existentes.
- Pode criar e acessar uma nova branch com uma única instrução.
- Também pode restaurar arquivos para o último estado salvo no Git.
- Facilita a navegação entre diferentes versões do projeto.

Como utilizar

Trocar para uma branch existente

```
git checkout nome-da-branch
```

Exemplo:

```
git checkout feature-login
```

Criar e acessar uma nova branch

```
git checkout -b nome-da-branch
```

Exemplo:

```
git checkout -b cadastro-usuarios
```

Esse comando equivale a executar:

```
git branch cadastro-usuarios
git checkout cadastro-usuarios
```

> [!example]  
> Exemplo prático
> 
> Você está na branch:
> 
> ```
> * main
> ```
> 
> E deseja desenvolver uma funcionalidade de cadastro.
> 
> Execute:
> 
> ```
> git checkout -b cadastro
> ```
> 
> Ao verificar as branches:
> 
> ```
> git branch
> ```
> 
> O resultado será:
> 
> ```
>   main* cadastro
> ```
> 
> A nova branch foi criada e você já estará trabalhando nela.

Alterações não commitadas

⚠️ **Se houver arquivos modificados e ainda não commitados, o Git poderá levar essas alterações para a branch de destino.**

Exemplo:

```
git statusgit checkout feature-login
```

Caso as alterações sejam compatíveis com a outra branch, elas continuarão presentes após a troca.

Versões mais recentes do Git

==Atualmente, é mais comum utilizar o comando `git switch`, criado especificamente para alternar entre branches.==

Trocar para uma branch existente:

```
git switch nome-da-branch
```

Criar e acessar uma nova branch:

```
git switch -c nome-da-branch
```

==Hoje em dia, em projetos profissionais, você verá com mais frequência os comandos `git switch` e `git restore`, pois eles tornam as operações do Git mais intuitivas e evitam a sobrecarga de funções que existia no `git checkout`.==
## GIT MERGE 

==O comando **`git merge`** é utilizado para **unir o histórico e as alterações de duas branches diferentes**.==

Ele permite integrar uma funcionalidade desenvolvida em uma branch secundária à branch principal do projeto.

O que o `git merge` faz?

- Une o código de duas branches.
- Incorpora commits de uma branch em outra.
- Mantém o histórico de desenvolvimento do projeto.
- É amplamente utilizado para integrar o trabalho de diferentes desenvolvedores.

Como utilizar

Primeiro, acesse a branch que receberá as alterações:

```
git switch main
```

Em seguida, execute o comando:

```
git merge nome-da-branch
```

Exemplo:

```
git merge feature-login
```

Nesse caso, todas as alterações da branch `feature-login` serão incorporadas à branch `main`.

> [!example]  
> Exemplo prático
> 
> Suponha que você tenha as seguintes branches:
> 
> ```
> * main  feature-login
> ```
> 
> Após concluir o desenvolvimento da funcionalidade de login, mude para a branch principal:
> 
> ```
> git switch main
> ```
> 
> Depois execute:
> 
> ```
> git merge feature-login
> ```
> 
> Agora, a branch `main` passará a conter todas as alterações desenvolvidas na `feature-login`.

Conflitos de merge

⚠️ **Caso duas branches tenham modificado a mesma parte de um arquivo, o Git poderá gerar um conflito de merge.**

Nessa situação, será necessário editar o arquivo manualmente, escolher quais alterações devem permanecer e, em seguida, finalizar o merge.

Exemplo de fluxo após resolver um conflito:

```
git add .git commit
```

Uso no dia a dia

==O `git merge` é um dos comandos mais utilizados no desenvolvimento profissional, pois é através dele que novas funcionalidades são incorporadas ao projeto principal e que as alterações realizadas por outros desenvolvedores são integradas ao seu código.==

Normalmente, o fluxo de trabalho é:

```
Criar Branch → Desenvolver → Commitar → Merge → Continuar o projeto
```

==Em equipes de desenvolvimento, é muito comum receber atualizações de outros desenvolvedores por meio de merges, mantendo todo o código centralizado e atualizado.==
## GIT STASH

==O comando **`git stash`** é utilizado para **salvar temporariamente alterações que ainda não foram commitadas**, permitindo que você trabalhe em outra tarefa sem perder o progresso atual.==

Após executar esse comando, o diretório de trabalho volta ao estado do último commit, como se as alterações nunca tivessem sido feitas.

O que o `git stash` faz?

- Salva alterações não commitadas em uma área temporária.
- Limpa o diretório de trabalho.
- Permite trocar de branch ou resolver outra tarefa rapidamente.
- Possibilita recuperar as alterações posteriormente.

Como utilizar

Salvar as alterações atuais

```
git stash
```

Após a execução, os arquivos modificados deixarão de aparecer no `git status`.

> [!example]  
> Exemplo prático
> 
> Imagine que você está desenvolvendo uma funcionalidade no arquivo:
> 
> ```
> Login.java
> ```
> 
> Ao executar:
> 
> ```
> git status
> ```
> 
> O Git exibe:
> 
> ```
> modified: Login.java
> ```
> 
> Porém, surge a necessidade de corrigir um bug urgente em outra branch.
> 
> Para guardar seu trabalho temporariamente:
> 
> ```
> git stash
> ```
> 
> Agora, ao executar:
> 
> ```
> git status
> ```
> 
> O resultado será:
> 
> ```
> nothing to commit, working tree clean
> ```
> 
> Seu código foi armazenado e poderá ser recuperado depois.

Recuperando as alterações

Para reaplicar o último stash salvo:

```
git stash pop
```

Esse comando restaura as alterações e remove o stash da lista.

Caso queira apenas restaurar sem removê-lo:

```
git stash apply
```

Visualizando os stashes salvos

```
git stash list
```

Exemplo de saída:

```
stash@{0}: WIP on main: 8f4c2d1 Ajustando tela de login
stash@{1}: WIP on feature-api: 5b7a9e3 Correção de bug
```

Quando utilizar

- Para interromper temporariamente uma tarefa.
- Para trocar de branch sem realizar um commit incompleto.
- Para testar uma abordagem diferente sem perder o código atual.
- Para resolver uma correção urgente e depois voltar ao trabalho original.

==O `git stash` é muito utilizado no dia a dia de um desenvolvedor, principalmente quando surge uma demanda inesperada e é necessário guardar rapidamente as alterações em andamento.==

==Após executar o comando, a branch é restaurada para o estado do último commit do repositório, enquanto suas modificações ficam armazenadas de forma segura até serem recuperadas.==
## GIT STASH LIST

==O comando **`git stash list`** é utilizado para **visualizar todas as stashes armazenadas no repositório**.==

Cada stash representa um conjunto de alterações temporariamente salvas, permitindo que o desenvolvimento seja retomado posteriormente.

O que o `git stash list` faz?

- Lista todas as stashes existentes.
- Exibe um identificador para cada stash.
- Permite selecionar qual conjunto de alterações será recuperado.
- Auxilia na organização de trabalhos temporariamente pausados.

Como utilizar

Listar as stashes salvas

```
git stash list
```

Exemplo de saída:

```
stash@{0}: WIP on main: 8f4c2d1 Ajustando tela de loginstash@{1}: WIP on feature-api: 5b7a9e3 Correção de bug
```

Cada stash recebe um identificador, como `stash@{0}` ou `stash@{1}`.

Recuperando uma stash específica

==Para restaurar uma stash, utiliza-se o comando `git stash apply`.==

```
git stash apply stash@{0}
```

Esse comando recupera as alterações armazenadas, mas mantém a stash na lista.

Caso queira recuperar e remover a stash ao mesmo tempo, utilize:

```
git stash pop
```

ou uma stash específica:

```
git stash pop stash@{0}
```

> [!example]  
> Exemplo prático
> 
> Você salvou um trabalho utilizando:
> 
> ```
> git stash
> ```
> 
> Mais tarde, ao executar:
> 
> ```
> git stash list
> ```
> 
> O Git retorna:
> 
> ```
> stash@{0}: WIP on main: Ajustando sistema de login
> ```
> 
> Para continuar exatamente de onde parou:
> 
> ```
> git stash apply stash@{0}
> ```
> 
> Todos os arquivos e modificações armazenados nessa stash serão restaurados.

Observação importante

⚠️ **Em algumas apostilas ou materiais antigos, pode aparecer a sintaxe:**

```
git stash <nome>
```

==Porém, nas versões atuais do Git, os comandos mais utilizados para recuperar uma stash são `git stash apply` e `git stash pop`.==

A principal diferença é:

- `git stash apply` → restaura a stash e a mantém salva.
- `git stash pop` → restaura a stash e a remove da lista.

==Utilizando `git stash list` em conjunto com `git stash apply` ou `git stash pop`, é possível interromper uma tarefa, trabalhar em outra demanda e depois continuar exatamente do ponto onde o desenvolvimento foi pausado.==
## GIT TAG

==O comando **`git tag`** é utilizado para **criar marcações (tags) em commits específicos do projeto**, funcionando como pontos de referência importantes no histórico.==

As tags são muito utilizadas para identificar versões, releases ou etapas importantes do desenvolvimento.

⚠️ **Uma tag é diferente de uma stash.** Enquanto a stash armazena alterações temporárias, a tag apenas cria uma marca permanente em um commit já existente.

O que o `git tag` faz?

- Cria um ponto de referência no histórico do Git.
- Permite identificar versões importantes do projeto.
- Facilita a localização de commits específicos.
- É muito utilizada para marcar releases, como `v1.0`, `v2.0`, etc.

Como utilizar

Criar uma tag anotada

```
git tag -a nome-da-tag -m "mensagem"
```

Exemplo:

```
git tag -a v1.0 -m "Primeira versão estável"
```

Nesse exemplo, a tag `v1.0` será criada apontando para o commit atual.

> [!example]  
> Exemplo prático
> 
> Imagine que você acabou de finalizar uma funcionalidade importante e realizou o commit:
> 
> ```
> Implementação completa do sistema de login
> ```
> 
> Para marcar esse momento do projeto, execute:
> 
> ```
> git tag -a v1.0 -m "Versão inicial do sistema"
> ```
> 
> Agora, sempre que precisar localizar essa versão, a tag estará disponível como um checkpoint do desenvolvimento.

Visualizando as tags existentes

```
git tag
```

Exemplo de saída:

```
v1.0v1.1v2.0-beta
```

Informações detalhadas de uma tag

```
git show v1.0
```

Esse comando exibe o commit associado à tag e sua mensagem.

Quando utilizar

- Marcar versões estáveis do sistema.
- Identificar releases para produção.
- Criar checkpoints importantes durante o desenvolvimento.
- Facilitar o controle de versões distribuídas para clientes ou equipes.

==No desenvolvimento profissional, as tags são amplamente utilizadas para demarcar versões do software, como `v1.0`, `v1.1` e `v2.0`, permitindo que qualquer versão importante seja facilmente localizada no histórico do projeto.==

==Diferentemente do `git stash`, que salva alterações temporárias, a `tag` funciona como um checkpoint permanente de um commit específico do branch.==
## GIT SHOW

==O comando **`git show`** é utilizado para **visualizar as informações de uma tag, commit ou outro objeto do Git**.==

Quando utilizado com uma tag, ele exibe o commit associado e todos os seus detalhes.

O que o `git show` faz?

- Exibe informações sobre uma tag.
- Mostra o commit associado àquela marcação.
- Permite visualizar autor, data, mensagem e alterações realizadas.
- Facilita a consulta de versões importantes do projeto.

Como utilizar

Visualizar uma tag

```
git show nome-da-tag
```

Exemplo:

```
git show v1.0
```

O Git exibirá informações semelhantes a:

```
tag v1.0Tagger: Gustavo <gustavo@email.com>Primeira versão estávelcommit 8f4c2d1...Author: GustavoDate: ...Implementação completa do sistema de login
```

> [!example]  
> Exemplo prático
> 
> Você possui as seguintes tags:
> 
> ```
> v1.0v1.1v2.0
> ```
> 
> Para visualizar os detalhes da versão `v1.0`:
> 
> ```
> git show v1.0
> ```
> 
> O Git mostrará todas as informações relacionadas àquele checkpoint do projeto.

Navegando para uma tag

==Também é possível acessar o estado do projeto em uma determinada tag utilizando o comando `git checkout`.==

```
git checkout nome-da-tag
```

Exemplo:

```
git checkout v1.0
```

Ao fazer isso, o projeto voltará exatamente para o estado em que a tag foi criada.

⚠️ **Ao utilizar `git checkout` em uma tag, o Git entra no estado chamado _Detached HEAD_. Isso significa que você não estará trabalhando em uma branch.**

Caso deseje realizar alterações a partir dessa versão, é recomendado criar uma nova branch:

```
git switch -c nova-branch
```

ou, em versões antigas:

```
git checkout -b nova-branch
```

Quando utilizar

- Revisar versões antigas do projeto.
- Testar uma release específica.
- Recuperar um estado anterior do código.
- Navegar entre checkpoints importantes do desenvolvimento.

==As tags funcionam como marcos no histórico do projeto. Utilizando `git show` e `git checkout`, é possível consultar ou retornar para qualquer checkpoint criado anteriormente.==

==Dessa forma, você pode avançar ou retroceder entre versões importantes do branch sem alterar o histórico do desenvolvimento.==
## TAGS

==As **tags** também podem ser enviadas para o repositório remoto, permitindo que outros desenvolvedores tenham acesso aos mesmos checkpoints do projeto.==

⚠️ **Ao contrário dos commits, as tags não são enviadas automaticamente com o `git push`. É necessário enviá-las explicitamente.**

O que o `git push` para tags faz?

- Envia uma tag específica para o repositório remoto.
- Compartilha versões importantes com toda a equipe.
- Permite distribuir releases e checkpoints do projeto.
- Mantém o histórico de versões sincronizado entre os desenvolvedores.

Como utilizar

Enviar uma tag específica

```
git push origin nome-da-tag
```

Exemplo:

```
git push origin v1.0
```

Nesse caso, apenas a tag `v1.0` será enviada para o servidor remoto.

Enviar todas as tags

```
git push origin --tags
```

Esse comando envia todas as tags locais que ainda não existem no repositório remoto.

> [!example]  
> Exemplo prático
> 
> Você criou duas tags:
> 
> ```
> v1.0v1.1
> ```
> 
> Para enviar apenas a primeira versão:
> 
> ```
> git push origin v1.0
> ```
> 
> Caso queira compartilhar todas as versões criadas:
> 
> ```
> git push origin --tags
> ```
> 
> Agora, todos os desenvolvedores que acessarem o repositório poderão visualizar essas tags.

Visualizando as tags recebidas

Após executar um `git fetch` ou clonar o repositório, as tags enviadas também estarão disponíveis localmente.

Para listá-las:

```
git tag
```

Exemplo de saída:

```
v1.0v1.1v2.0-beta
```

Quando utilizar

- Compartilhar versões estáveis do sistema.
- Publicar releases para a equipe.
- Marcar entregas importantes do projeto.
- Sincronizar checkpoints entre os desenvolvedores.

==Em projetos profissionais, é muito comum utilizar tags para identificar versões oficiais do software, como `v1.0`, `v2.0` ou `v3.1`. Após criá-las, elas são enviadas para o repositório remoto para que toda a equipe trabalhe com as mesmas referências.==

==Utilize `git push origin <nome-da-tag>` para enviar uma única tag ou `git push origin --tags` para enviar todas as tags criadas localmente.==


## GIT FETCH

==O comando **`git fetch`** é utilizado para **buscar atualizações do repositório remoto**, como novas branches, tags e commits, sem alterar o seu trabalho local.==

Ele sincroniza as informações do repositório remoto com o seu Git, permitindo que você visualize novos recursos criados por outros desenvolvedores.

O que o `git fetch` faz?

- Busca novas branches do repositório remoto.
- Atualiza as referências das branches existentes.
- Baixa novas tags criadas por outros desenvolvedores.
- Não altera a branch em que você está trabalhando.
- Não faz merge automático das alterações.

Como utilizar

Buscar atualizações do repositório remoto

```
git fetch
```

Após a execução, seu Git reconhecerá novas branches e tags que ainda não existiam localmente.

> [!example]  
> Exemplo prático
> 
> Imagine que outro desenvolvedor criou uma branch chamada:
> 
> ```
> feature-pagamento
> ```
> 
> No seu computador, ao executar:
> 
> ```
> git branch
> ```
> 
> Essa branch ainda não aparecerá.
> 
> Execute então:
> 
> ```
> git fetch
> ```
> 
> Agora, o Git atualizará suas referências e você poderá acessar essa nova branch.

Visualizando as branches remotas

Após o `fetch`, é possível listar as branches do servidor com:

```
git branch -r
```

Exemplo de saída:

```
origin/mainorigin/feature-loginorigin/feature-pagamento
```

Para começar a trabalhar em uma dessas branches:

```
git switch feature-pagamento
```

Caso ela ainda não exista localmente, o Git normalmente criará a branch automaticamente a partir da referência remota.

Diferença entre `git fetch` e `git pull`

==O `git fetch` apenas baixa as atualizações, enquanto o `git pull` baixa e já tenta integrar essas alterações ao seu branch atual.==

```
git fetch → Baixa as atualizações.
git pull  → Baixa + faz merge das atualizações.
```

Quando utilizar

- Verificar se novos branches foram criados.
- Obter novas tags compartilhadas pela equipe.
- Atualizar as referências do repositório remoto.
- Trabalhar em branches criadas por outros desenvolvedores.

==No desenvolvimento em equipe, novas branches são criadas constantemente. O comando `git fetch` é muito utilizado para manter seu repositório local atualizado e reconhecer branches e tags que ainda não estavam mapeados no seu ambiente.==

==Esse comando é especialmente útil quando você precisa acessar ou colaborar em uma branch criada por outro desenvolvedor do time.==

## PRIVATE BRANCH

==Uma **Private Branch** (branch privada) é uma branch que **existe apenas no seu repositório local e ainda não foi enviada para o repositório remoto**.==

Ela permite que um desenvolvedor trabalhe em uma funcionalidade sem que os demais membros da equipe tenham acesso às alterações.

O que uma Private Branch faz?

- Mantém o desenvolvimento isolado na máquina do desenvolvedor.
- Evita que alterações incompletas sejam compartilhadas.
- Permite testar novas funcionalidades com segurança.
- Só se torna visível para a equipe após um `git push`.

Como utilizar

Criar uma nova branch local

```
git switch -c feature-login
```

ou, em versões mais antigas do Git:

```
git checkout -b feature-login
```

Enquanto essa branch não for enviada ao servidor, ela permanecerá privada.

> [!example]  
> Exemplo prático
> 
> Você deseja desenvolver uma nova funcionalidade sem que outros desenvolvedores a visualizem.
> 
> Crie uma branch:
> 
> ```
> git switch -c nova-feature
> ```
> 
> Realize seus commits normalmente:
> 
> ```
> git add .git commit -m "Inicia desenvolvimento da nova funcionalidade"
> ```
> 
> Como ainda não foi executado um `git push`, essa branch existirá apenas no seu computador.

Compartilhando a branch

==Quando desejar disponibilizar a branch para a equipe, basta enviá-la para o repositório remoto.==

```
git push -u origin nova-feature
```

Após esse comando, os outros desenvolvedores poderão visualizar e utilizar essa branch.

Observação importante

⚠️ **O Git não possui um comando específico chamado "private branch". Uma branch é considerada privada simplesmente porque ainda não foi publicada no repositório remoto.**

Quando utilizar

- Desenvolver funcionalidades em andamento.
- Realizar testes sem afetar a equipe.
- Trabalhar em correções antes de compartilhá-las.
- Evitar publicar código incompleto.

==Na prática, uma Private Branch é apenas uma branch local que ainda não foi enviada ao servidor. Ela permite que o desenvolvedor trabalhe de forma isolada até que esteja pronto para compartilhar suas alterações com a equipe.==