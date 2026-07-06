
## GIT INIT

O comando **`git init`** é utilizado para **inicializar um repositório Git** em uma pasta. Ao executá-lo, o Git cria uma pasta oculta chamada **`.git`**, que armazenará todo o histórico de versões, configurações e informações necessárias para o controle de versão do projeto.

==Após a execução desse comando, o diretório passa a ser reconhecido como um repositório Git, permitindo o uso de outros comandos como `git add`, `git commit` e `git push`.==

> [!example]
>  Exemplo:
> 
> ```
> mkdir sistema-vendas
> cd sistema-vendas
> git init (Cria um repositório)
> ```
> 
> Saída:
> 
> ```
> Initialized empty Git repository in C:/sistema-vendas/.git/
> ```

A partir desse momento, o Git começará a monitorar os arquivos desse projeto, permitindo registrar alterações e criar versões do código.

## ENVIAR PARA O GITHUB

Após criar um projeto localmente com Git, podemos enviá-lo para o GitHub para armazenar o código na nuvem, compartilhar com outras pessoas e manter um backup do projeto.

O processo consiste em:

1. Criar um repositório no GitHub.
2. Inicializar o Git na pasta do projeto (`git init`).
3. Adicionar os arquivos ao controle de versão.
4. Conectar o repositório local ao remoto do GitHub.
5. Enviar os arquivos para o GitHub.

==Embora pareça um processo longo, ele é realizado com poucos comandos e normalmente só precisa ser configurado uma vez para cada projeto.==

Como utilizar

> [!example]
> 1. Inicializar o Git
> 
> ```
> git init
> ```
> 
> 2. Adicionar os arquivos
> 
> ```
> git add .
> ```
> 
> 3. Criar o primeiro commit
> 
> ```
> git commit -m "Primeiro commit"
> ```
> 
> 4. Conectar ao repositório do GitHub
> 
> ```
> git remote add origin https://github.com/usuario/repositorio.git
> ```
> 
> 5. Enviar os arquivos
> 
> ```
> git push -u origin main
> ```
> 

Tabela de comandos:

|Comando|Função|
|---|---|
|`git init`|Cria um repositório Git local|
|`git add .`|Adiciona todos os arquivos para serem versionados|
|`git commit -m "mensagem"`|Salva uma versão do projeto|
|`git remote add origin URL`|Conecta o projeto local ao GitHub|
|`git push -u origin main`|Envia os arquivos para o GitHub|

Depois dessa configuração inicial, os próximos envios normalmente exigem apenas:

```
git add .
git commit -m "Descrição da alteração"
git push
```

==Esses três comandos serão os mais utilizados no dia a dia de um desenvolvedor.==

## GIT STATUS

==O comando **`git status`** é utilizado para verificar o estado atual do repositório.== Ele mostra quais arquivos foram modificados, quais ainda não estão sendo monitorados pelo Git e quai s alterações estão prontas para serem salvas em um commit.

É um dos comandos mais usados no dia a dia, pois permite acompanhar tudo o que mudou no projeto antes de adicionar arquivos (`git add`) ou criar um commit (`git commit`).

O que o `git status` informa?

- ===**Arquivos não monitorados (Untracked Files):**== arquivos criados que o Git ainda não está controlando.
- ==**Arquivos modificados (Modified):**== arquivos que já existiam no repositório e foram alterados.
- ==**Arquivos preparados para commit (Staged Changes):**== alterações adicionadas com `git add` e prontas para serem salvas.
- ==**Branch atual:**== informa em qual branch você está trabalhando.
- ==**Situação em relação ao GitHub:**== mostra se existem commits para enviar (`push`) ou receber (`pull`).

> [!example]
>  Exemplo
> 
> Imagine que você criou um arquivo chamado `index.html` e alterou o arquivo `style.css`.
> 
> ```
> git status
> ```
> 
> Saída simplificada:
> 
> ```
> On branch mainUntracked files:  index.html
> Modified:  style.css
> ```
> 

Isso significa que:

- `index.html` foi criado e ainda não está sendo monitorado pelo Git.
- `style.css` já existia e foi modificado.

Fluxo comum de uso

```
git status      (Verifica as alterações) 
git add .       (Adiciona as alterações)
git status      (Confirma o que será salvo)
git commit -m "Atualização do projeto"
```

==Antes de executar qualquer comando importante do Git, é uma boa prática executar:==

```
git status
```


 Assim você sabe exatamente o que mudou no projeto e evita enviar arquivos errados ou
 esquecer alterações importantes.

## GIT ADD

==O comando **`git add`** é utilizado para adicionar arquivos ao controle de versão e preparar alterações para o próximo commit==. Quando um arquivo é adicionado, o Git passa a monitorá-lo e incluir suas alterações no histórico do projeto.

==Sem executar o `git add`, as mudanças realizadas nos arquivos não serão incluídas no próximo commit.==

O que o git add faz?

- Adiciona novos arquivos ao controle de versão.
- Prepara arquivos modificados para o próximo commit.
- Move as alterações da área de trabalho para a área de preparação (_Staging Area_).
- Permite escolher exatamente quais arquivos serão salvos no próximo commit.
 
 Como utilizar:

- Adicionar um arquivo específico

```
git add arquivo.txt
```

- Adicionar vários arquivos

```
git add arquivo1.txt arquivo2.txt
```

- Adicionar todos os arquivos modificados e novos

```
git add .
```

> [!example]
> Exemplo prático:
> 
> Imagine que você criou os arquivos:
> 
> ```
> index.html
> style.css
> script.js
> ```
> 
> Ao verificar o status:
> 
> ```
> git status
> ```
> 
> O Git mostrará que eles ainda não estão sendo monitorados.
> 
> Para adicioná-los:
> 
> ```
> git add .
> ```
> 
> Agora, ao executar novamente:
> 
> ```
> git status
> ```
> 

Você verá que os arquivos estão na área de preparação (_staged_) e prontos para serem salvos com um commit.

**Fluxo completo:**

```
git status
git add .
git status
git commit -m "Adiciona estrutura inicial do projeto"
```

==É recomendável executar `git add` frequentemente durante o desenvolvimento. Assim, você evita esquecer arquivos importantes e garante que todas as alterações desejadas sejam incluídas no próximo commit.==

O `git add` **não salva as alterações definitivamente**. Ele apenas prepara os arquivos para o commit.

> [!NOTE]
> Arquivo Modificado  
> 	    ↓  
> git add  
> 	 ↓  
> Área de Preparação (Staging)  
> 	 ↓  
> git commit  
> 	 ↓  
> Histórico do Projeto
> 

por isso, o comando `git add` é geralmente utilizado antes de cada `git commit`.

## GIT COMMIT

==O comando **`git commit`** é utilizado para salvar permanentemente as alterações que foram preparadas com o `git add`. ==Cada commit representa uma versão do projeto, permitindo consultar, comparar e restaurar estados anteriores do código.

Pense no commit como uma "foto" do projeto em determinado momento.

O que o `git commit` faz?

- Salva as alterações no histórico do Git.
- Cria um ponto de restauração do projeto.
- Permite acompanhar a evolução do código.
- Registra quem realizou a alteração e quando ela foi feita.

Como utilizar

- Commit com mensagem

```
git commit -m "Adiciona tela de login"
```

A flag `-m` permite adicionar uma mensagem descritiva ao commit.

- Exemplos de boas mensagens

```
git commit -m "Corrige erro de validação do formulário"
git commit -m "Adiciona funcionalidade de cadastro de usuários"
git commit -m "Atualiza layout da página inicial"
```

- Fluxo completo

==Antes de realizar um commit, os arquivos devem estar na área de preparação (_Staging Area_):==

```
git add .
git commit -m "Implementa sistema de autenticação"
```

- Utilizando a flag `-a`

==A flag `-a` adiciona automaticamente ao commit os arquivos que já estavam sendo monitorados pelo Git e foram modificados.==

```
git commit -a -m "Corrige bug no cálculo de descontos"
```

⚠️ Atenção: a flag `-a` **não adiciona arquivos novos**. Arquivos criados pela primeira vez ainda precisam passar por:

```
git add nome-do-arquivo
```

> [!example]
> Exemplo prático
> 
> Você altera o arquivo `Login.java`:
> 
> ```
> git status
> ```
> 
> Mostrará:
> 
> ```
> modified: Login.java
> ```
> 
> Então:
> 
> ```
> git add Login.javagit commit -m "Corrige validação de senha"
> ```

O Git cria uma nova versão do projeto contendo essa alteração.

**Boas práticas:**

- Faça commits pequenos e frequentes.
- Escreva mensagens claras e objetivas.
- Cada commit deve representar uma alteração específica.
- Evite mensagens genéricas como:
    - "Alterações"
    - "Update"
    - "Correções"

**Prefira:**

✅ "Adiciona tela de cadastro"

✅ "Corrige erro de autenticação"

✅ "Implementa busca de produtos"

Assim, o histórico do projeto fica muito mais organizado e fácil de entender.

## GIT PUSH

==O comando **`git push`** é utilizado para enviar os commits do repositório local para um repositório remoto==, como o GitHub. Dessa forma, as alterações realizadas no projeto ficam disponíveis no servidor e podem ser acessadas por outros desenvolvedores.

Normalmente, o `git push` é executado após finalizar uma funcionalidade, correção ou melhoria e realizar os commits correspondentes.

O que o `git push` faz?

- Envia os commits locais para o repositório remoto.
- Atualiza o código armazenado no servidor.
- Compartilha as alterações com a equipe.
- Mantém o repositório remoto sincronizado com o local.

Como utilizar:

- Enviar alterações para o GitHub

```
git push
```

- Primeiro envio de uma branch

```
git push -u origin main
```

Onde:

- `origin` → nome do repositório remoto.
- `main` → branch que será enviada.
- `-u` → define o repositório remoto padrão para os próximos pushes.

Fluxo completo

```
git add .
git commit -m "Adiciona tela de login"
git push
```

> [!example]
> Exemplo prático:
> 
> Imagine que você implementou uma nova funcionalidade:
> 
> ```
> git add .git commit -m "Implementa recuperação de senha"git push
> ```
> 
> Após o `git push`, o GitHub será atualizado com essa nova versão do projeto.

Antes de executar um `git push`, é recomendável verificar se existem alterações pendentes:

```
git status
```

==E, quando estiver trabalhando em equipe, geralmente é uma boa prática atualizar o projeto antes de enviar alterações:==

```
git pullgit push
```

Assim você reduz a chance de conflitos entre versões.

O `git commit` ==salva alterações **localmente** no seu computador==.

O `git push` ==envia essas alterações **para o repositório remoto**==, tornando-as disponíveis no GitHub e para outros membros da equipe.

## GIT PULL

==O comando **`git pull`** é utilizado para atualizar o repositório local com as alterações que estão no repositório remoto (GitHub, GitLab, Bitbucket, etc.).==

Ele é muito usado em projetos com mais de um desenvolvedor, pois permite obter as mudanças feitas por outras pessoas antes de continuar trabalhando.

O que o `git pull` faz?

- Busca as alterações do repositório remoto.
- Baixa novos commits para sua máquina.
- Integra essas alterações ao seu código local.
- Mantém seu projeto sincronizado com o servidor.

Na prática, o `git pull` equivale a:

```
git fetchgit merge
```

Primeiro ele baixa as alterações e depois as incorpora ao seu projeto.

Como utilizar

```
git pull
```

Ou especificando o remoto e a branch:

```
git pull origin main
```

> [!example]
> Exemplo prático
> 
> Imagine que um colega adicionou uma nova funcionalidade ao projeto e enviou para o GitHub.
> 
> Antes de começar a trabalhar, você executa:
> 
> ```
> git pull
> ```
> 
> O Git baixa essas alterações e atualiza sua cópia local do projeto.

**Fluxo comum em equipe

```
git pull (Pega do repositório remoto)
git status (Checa os status do projeto)
git add . (adiciona as alterações)
git commit -m "Nova funcionalidade" (Manda pro repositório local)
git push (Manda pro repositório remoto)
```

Possíveis conflitos

Às vezes você e outra pessoa alteram a mesma parte de um arquivo. Nesse caso, durante o `git pull`, o Git pode informar um **conflito de merge**.

> [!example]
> Exemplo:
> 
> ```
> CONFLICT (content): Merge conflict in Login.java
> ```
> 

Nesse cenário, você precisará escolher quais alterações manter antes de concluir a sincronização.

Antes de começar a programar em um projeto compartilhado, execute:

```
git pull
```

==Assim você garante que está trabalhando na versão mais recente do código e reduz as chances de conflitos quando fizer o `git push`.==

> [!tip]
> - **`git push`** → envia suas alterações para o servidor.
> - **`git pull`** → traz as alterações do servidor para sua máquina.
> 
> Pense assim:
> 
> ```
> Sua Máquina  ── git push ──► GitHub 
> Sua Máquina ◄── git pull ─── GitHub
> ```
> 
> O `git push` sobe código, e o `git pull` baixa código. Eles são os dois comandos de sincronização mais importantes do Git.

## GIT CLONE

==O comando **`git clone`** é utilizado para baixar uma cópia completa de um repositório remoto para sua máquina. Esse processo é chamado de **clonagem de repositório**.==

Quando você clona um projeto, o Git baixa:

- Todo o código-fonte.
- Todo o histórico de commits.
- Todas as branches e configurações do repositório.
- A conexão com o repositório remoto original.

É um comando muito utilizado quando você entra em um novo projeto ou deseja trabalhar em um projeto já existente no GitHub.

Como utilizar

```
git clone URL_DO_REPOSITORIO
```

> [!example]
> Exemplo
> 
> Suponha que você queira baixar um projeto do GitHub:
> 
> ```
> git clone https://github.com/usuario/projeto.git
> ```
> 
> O Git criará automaticamente uma pasta chamada `projeto` contendo todos os arquivos.

O que acontece após o clone?

Depois de clonar o repositório, você já pode entrar na pasta e começar a trabalhar:

```
git clone https://github.com/usuario/projeto.gitcd projeto
```

Agora você pode usar comandos como:

```
git statusgit pullgit add .git commit -m "Minha alteração"git push
```

> [!example]
> Exemplo de uso em uma empresa
> 
> Imagine que você começou um estágio e recebeu acesso ao projeto da equipe.
> 
> Em vez de criar um repositório do zero, você simplesmente executa:
> 
> ```
> git clone https://github.com/empresa/sistema.git
> ```
> 
> Pronto. Você terá exatamente a mesma versão do projeto que está no servidor.
## GIT RM

==O comando **`git rm`** é utilizado para remover arquivos do controle de versão do Git.== Após a remoção, o arquivo deixa de ser monitorado e suas alterações não serão mais consideradas nos próximos commits.

==É importante entender que o `git rm` normalmente remove o arquivo **do Git e também da pasta do projeto**.== Caso você queira apenas parar de monitorá-lo, existe uma opção específica para isso.

Como utilizar

Remover um arquivo do Git e da pasta

```
git rm arquivo.txt
```

Remover vários arquivos

```
git rm arquivo1.txt arquivo2.txt
```

> [!example]
> Exemplo
> 
> Suponha que você tenha um arquivo chamado `teste.txt`:
> 
> ```
> git rm teste.txtgit commit -m "Remove arquivo de teste"
> ```
> 
> Após o commit, o arquivo será removido do projeto e do histórico atual.

Parar de monitorar sem apagar o arquivo

Se você deseja manter o arquivo na sua máquina, mas removê-lo do controle de versão, utilize:

```
git rm --cached arquivo.txt
```

> [!example]
> Exemplo comum:
> 
> ```
> git rm --cached .env
> ```
> 
> Isso é muito utilizado para remover arquivos de configuração, senhas ou arquivos que deveriam estar no `.gitignore`.

Hoje em dia, é mais comum usar:

```
git rm --cached arquivo
```

para parar de versionar arquivos específicos, e usar o arquivo `.gitignore` para impedir que eles sejam adicionados novamente no futuro. Isso acontece bastante com:

- `.env`
- arquivos de log (`.log`)
- pastas `target/` (Java Maven)
- pastas `node_modules/`
- arquivos temporários do IDE (`.idea/`, `.vscode/`)

Para seus projetos Java com Maven, por exemplo, normalmente a pasta `target/` não deve ser enviada para o GitHub, sendo adicionada ao `.gitignore` em vez de ser versionada.

## GIT LOG

==O comando **`git log`** é utilizado para visualizar o histórico de commits de um repositório. Ele mostra todas as alterações que foram salvas ao longo do desenvolvimento do projeto.==

Com esse comando, você pode descobrir:

- Quem realizou um commit.
- Quando ele foi realizado.
- Qual foi a mensagem do commit.
- O identificador único (hash) do commit.

> [!example]
> Como utilizar
> 
> ```
> git log
> ```
> 
> Exemplo de saída
> 
> ```
> commit a1b2c3d4e5f6g7h8i9j0
> Author: Gustavo Sales
> Date: Mon Jun 2 15:30:20 2026    
> Adiciona sistema de login
> commit z9y8x7w6v5u4t3s2r1q0
> Author: Gustavo Sales
> Date: Mon Jun 1 10:15:45 2026    
> Cria estrutura inicial do projeto
> ```
> 

|Informação|Descrição|
|---|---|
|Commit|Identificador único do commit (hash)|
|Author|Autor da alteração|
|Date|Data e hora do commit|
|Mensagem|Descrição da alteração realizada|

Formato resumido

> [!example]
> Para visualizar os commits de forma mais compacta:
> 
> ```
> git log --oneline
> ```
> 
> Exemplo:
> 
> ```
> a1b2c3d Adiciona sistema de loginz9y8x7w Cria estrutura inicial do projeto
> ```
> 
> Esse formato é muito utilizado porque facilita a leitura do histórico.

Limitar a quantidade de commits

> [!example]
> Exibir apenas os últimos 5 commits:
> 
> ```
> git log -5
> ```
> 
> Ou:
> 
> ```
> git log --oneline -5
> ```
> 
> Exemplo prático
> 
> Imagine que você está trabalhando em um projeto Java e deseja saber quais alterações já foram realizadas:
> 
> ```
> git log --oneline
> ```
> 
> Resultado:
> 
> ```
> 8f4c3a2 Implementa busca de vagas
> 7d2b1f9 Corrige erro de conexão com banco
> 3a9e5c7 Cria tela principal
> ```
> 
> Assim, você consegue acompanhar a evolução do projeto e identificar rapidamente quando uma funcionalidade foi adicionada ou corrigida.

O comando mais usado no dia a dia costuma ser:

```
git log --oneline
```

Porque ele mostra o histórico de forma simples e objetiva, facilitando a consulta dos commits sem exibir informações excessivas.

## GIT MV

==O comando **`git mv`** é utilizado para **renomear** ou **mover arquivos e pastas** dentro de um repositório Git. Ao usar esse comando, o Git reconhece automaticamente a alteração, sem a necessidade de remover e adicionar o arquivo manualmente.==

O que o `git mv` faz?

- Renomeia arquivos.
- Move arquivos para outra pasta.
- Mantém o histórico do arquivo no Git.
- Marca automaticamente a alteração para o próximo commit.

Como utilizar

Renomear um arquivo

```
git mv antigo.txt novo.txt
```

Mover um arquivo para outra pasta

```
git mv arquivo.txt documentos/
```

 Renomear e mover ao mesmo tempo

```
git mv arquivo.txt src/novo_nome.txt
```

> [!example]
> Exemplo prático
> 
> Imagine que você possui um arquivo chamado:
> 
> ```
> index.html
> ```
> 
> E deseja renomeá-lo para:
> 
> ```
> home.html
> ```
> 
> Execute:
> 
> ```
> git mv index.html home.html
> ```
> 
> Depois:
> 
> ```
> git commit -m "Renomeia index.html para home.html"
> ```
> 
>  O que acontece internamente?
> 
> O comando:
> 
> ```
> git mv antigo.txt novo.txt
> ```
> 
> é equivalente a:
> 
> ```
> mv antigo.txt novo.txtgit rm antigo.txtgit add novo.txt
> ```
> 
> Mas o `git mv` faz tudo isso automaticamente.
>  Verificando a alteração
> 
> Após executar o comando:
> 
> ```
> git status
> ```
> 
> Você verá algo parecido com:
> 
> ```
> renamed: arquivo_antigo.txt -> arquivo_novo.txt
> ```

> [!tip]
>  Dica
> 
> Embora seja possível renomear arquivos diretamente pelo Explorador do Windows ou pela IDE, usar `git mv` deixa explícito para o Git que houve uma renomeação, facilitando o acompanhamento do histórico do projeto.
> 
> Para projetos Java, por exemplo, ele pode ser útil ao reorganizar pacotes, mover arquivos de configuração ou renomear classes e recursos do projeto.

## GIT CHECKOUT

==O comando **`git checkout`** pode ser utilizado para **descartar alterações em um arquivo e restaurá-lo para o último estado salvo no Git**.==

⚠️ **Atenção:** ao fazer isso, as alterações não salvas serão perdidas.

O que o `git checkout` faz?

- Restaura um arquivo para a última versão commitada.
- Remove alterações locais que ainda não foram commitadas.
- Retira o arquivo das alterações pendentes.
- Permite voltar a um estado anterior do projeto.

Como utilizar

Restaurar um arquivo

```
git checkout -- arquivo.txt
```

> [!example]
> Exemplo prático
> 
> Imagine que você modificou o arquivo:
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
> O Git mostra:
> 
> ```
> modified: Login.java
> ```
> 
> Se você decidir descartar as alterações:
> 
> ```
> git checkout -- Login.java
> ```
> 
> O arquivo voltará exatamente para a última versão salva no Git.

Atenção sobre versões mais novas do Git

==Atualmente, é mais comum utilizar:==

```
git restore arquivo.txt
```

O comando `git restore` foi criado para deixar essa operação mais clara.

Por isso:

```
git checkout -- arquivo.txt
```

e

```
git restore arquivo.txt
```

==têm praticamente o mesmo objetivo nesse contexto.==

> [!example]
> Exemplo completo
> 
> ```
> git status
> git restore Login.java
> git status
> ```
> 
> Após o `restore`, o arquivo não aparecerá mais como modificado.

==Hoje em dia, em projetos profissionais, você verá mais frequentemente os comandos `git restore` e `git switch`, que substituem parte das funções antigas do `git checkout` e tornam o Git mais fácil de entender.==

## .GITIGNORE

==O arquivo **`.gitignore`** é utilizado para informar ao Git quais arquivos ou pastas devem ser ignorados e não devem fazer parte do controle de versão.==

==Ele fica na raiz do projeto== e é muito útil para evitar que arquivos desnecessários, temporários ou sensíveis sejam enviados para o repositório.

 Por que usar o `.gitignore`?

- Evita versionar arquivos temporários.
- Impede o envio de senhas, chaves e configurações sensíveis.
- Mantém o repositório mais organizado.
- Evita conflitos com arquivos gerados automaticamente por IDEs e ferramentas.

Como criar

Crie um arquivo chamado:

```
.gitignore
```

na raiz do projeto.

Exemplo

```
# Arquivos de log*.log
# Arquivos de configuração sensíveis.env
# Pasta de compilação do Maventarget/
# Arquivos do IntelliJ IDEA.idea/
# Arquivos do VS Code.vscode/
# Arquivos compilados Java*.class
```

Significado dos padrões

|Padrão|Significado|
|---|---|
|`*.log`|Ignora todos os arquivos `.log`|
|`*.class`|Ignora todos os arquivos compilados Java|
|`target/`|Ignora a pasta `target` e seu conteúdo|
|`.env`|Ignora o arquivo `.env`|
|`.idea/`|Ignora configurações do IntelliJ|
|`.vscode/`|Ignora configurações do VS Code|

Exemplo para seus projetos Java com Maven

Como você utiliza Java e Maven, um `.gitignore` básico costuma conter:

```
target/*.class.idea/.vscode/*.log
```

Assim, apenas o código-fonte é enviado para o GitHub.

O `.gitignore` só funciona para arquivos que **ainda não estão sendo monitorados pelo Git**.

Se um arquivo já foi adicionado anteriormente, será necessário removê-lo do controle de versão:

```
git rm --cached arquivo.txt
```

Depois disso, adicione-o ao `.gitignore`.

 Exemplo prático

Imagine que seu projeto possui:

```
projeto/├── src/├── target/├── .env├── pom.xml└── .gitignore
```

Com o seguinte `.gitignore`:

```
target/.env
```

Ao executar:

```
git status
```

O Git mostrará apenas os arquivos relevantes do projeto, ignorando a pasta `target` e o arquivo `.env`.

 - **Boas práticas

- Nunca envie senhas, tokens ou chaves de API para o GitHub.
- Ignore arquivos gerados automaticamente.
- Versione apenas o que é necessário para outra pessoa executar o projeto.
- Adicione o `.gitignore` logo no início do desenvolvimento.

==O `.gitignore` é um dos arquivos mais importantes de qualquer projeto profissional, pois ajuda a manter o repositório limpo, seguro e organizado.==

## GIT RESET

==O comando **`git reset`** é utilizado para voltar o repositório a um estado anterior. Ele pode desfazer commits, remover alterações da área de staging e, dependendo da opção utilizada, até apagar alterações locais.==

==A opção mais agressiva é **`--hard`**, pois ela descarta tanto os commits quanto as alterações não salvas.==

 O que o `git reset --hard` faz?

- Remove alterações pendentes.
- Limpa a área de staging.
- Volta o projeto para um commit específico.
- Descarta modificações locais que ainda não foram commitadas.
- Pode remover commits locais recentes.

⚠️ **Atenção:** as alterações descartadas pelo `git reset --hard` geralmente não podem ser recuperadas facilmente.

Como utilizar

 Voltar para o último commit

```
git reset --hard HEAD
```

Isso descarta todas as alterações que ainda não foram commitadas.

 Voltar um commit

```
git reset --hard HEAD~1
```

Remove o commit mais recente e retorna ao estado do commit anterior.

 Voltar para um commit específico

Primeiro visualize o histórico:

```
git log --oneline
```

Exemplo:

```
a1b2c3d Adiciona tela de login
z9y8x7w Cria estrutura inicial
```

Depois:

```
git reset --hard z9y8x7w
```

O projeto voltará exatamente para esse commit.
 
 Diferença entre os tipos de reset:

| Comando             | Mantém arquivos? | Mantém staging? |
| ------------------- | ---------------- | --------------- |
| `git reset --soft`  | Sim              | Sim             |
| `git reset --mixed` | Sim              | Não             |
| `git reset --hard`  | Não              | Não             |

> [!example]
>  Exemplo prático
> 
> Imagine que você fez:
> 
> ```
> git add .git commit -m "Nova funcionalidade"
> ```
> 
> Mas percebeu que deseja voltar ao estado anterior:
> 
> ```
> git reset --hard HEAD~1
> ```
> 
> O commit será removido e o código voltará para a versão anterior.
> 

 Dica importante

Antes de usar um reset destrutivo, verifique o histórico:

```
git log --oneline
```

==E confirme que realmente deseja perder as alterações.==

Conceito-chave

- **`git restore`** → descarta alterações em arquivos específicos.
- **`git reset`** → altera o estado do repositório e do histórico.
- **`git reset --hard`** → descarta tudo que não faz parte do commit de destino.

```
Arquivo específico → git restore
Área de staging → git reset
Histórico completo → git reset --hard
```

Por isso, `git reset --hard` é considerado um comando poderoso e deve ser usado com cuidado, especialmente em projetos compartilhados.

## GIT REMOTE 

==O comando **`git remote`** é utilizado para **gerenciar os repositórios remotos associados ao seu projeto local**.==

Um repositório remoto é uma versão do projeto armazenada em um serviço como GitHub, GitLab ou Bitbucket, permitindo o compartilhamento do código com outros desenvolvedores.

O que o `git remote` faz?

- Adiciona um repositório remoto ao projeto.
- Remove repositórios remotos existentes.
- Lista os remotes configurados.
- Permite que comandos como `git push` e `git pull` saibam para onde enviar ou de onde receber alterações.

Como utilizar

Adicionar um repositório remoto

```
git remote add origin <link>
```

Exemplo:

```
git remote add origin https://github.com/usuario/meu-projeto.git
```

Nesse caso:

- `origin` é o nome dado ao repositório remoto.
- `<link>` é a URL do repositório hospedado.

> [!example]  
> Exemplo prático
> 
> Você criou um projeto localmente e também criou um repositório no GitHub.
> 
> Para conectar os dois, execute:
> 
> ```
> git remote add origin https://github.com/usuario/projeto-java.git
> ```
> 
> A partir desse momento, será possível utilizar comandos como:
> 
> ```
> git push origin main
> ```
> 
> e
> 
> ```
> git pull origin main
> ```
> 
> para enviar e receber alterações.

Visualizar os repositórios remotos

```
git remote -v
```

Exemplo de saída:

```
origin  https://github.com/usuario/projeto-java.git (fetch)origin  https://github.com/usuario/projeto-java.git (push)
```

Remover um repositório remoto

```
git remote remove origin
```

Esse comando remove apenas a conexão com o repositório remoto, sem apagar os arquivos do projeto.

Quando utilizar

- Após criar um repositório no GitHub ou GitLab.
- Para conectar um projeto local a um servidor remoto.
- Para alterar ou remover a referência de um repositório remoto.
- Para configurar o ambiente de trabalho em equipe.

==No desenvolvimento profissional, o comando `git remote` é utilizado para gerenciar as conexões entre o repositório local e os repositórios remotos, permitindo o compartilhamento e a sincronização do código entre todos os desenvolvedores.==

==Ao criar um novo repositório remoto, normalmente a primeira configuração realizada é:==

```
git remote add origin <link>
```

==Esse comando estabelece a ligação entre o projeto local e o repositório remoto, possibilitando o uso de `git push` e `git pull`.==

