## GIT SHOW

==O comando **`git show`** é utilizado para **exibir informações detalhadas sobre commits, branches, tags e outros objetos do Git**.==

Ele permite visualizar o histórico de alterações e as modificações realizadas em cada commit.

O que o `git show` faz?

- Exibe informações do commit atual.
- Mostra autor, data e mensagem do commit.
- Apresenta as alterações realizadas nos arquivos.
- Permite visualizar detalhes de uma tag específica.
- Auxilia na análise do histórico do projeto.

Como utilizar

Exibir informações do commit atual

```
git show
```

O Git exibirá informações semelhantes a:

```
commit 8f4c2d1...Author: Gustavo SalesDate: ...Implementa sistema de login
```

Além dessas informações, o comando também mostra as linhas adicionadas e removidas em cada arquivo.

> [!example]  
> Exemplo prático
> 
> Após realizar um commit:
> 
> ```
> git commit -m "Corrige validação de senha"
> ```
> 
> Execute:
> 
> ```
> git show
> ```
> 
> O Git exibirá:
> 
> - O identificador do commit.
> - O autor da alteração.
> - A data do commit.
> - A mensagem informada.
> - As modificações feitas nos arquivos.

Visualizar um commit específico

Também é possível informar o identificador do commit:

```
git show <hash-do-commit>
```

Exemplo:

```
git show 8f4c2d1
```

Exibindo informações de uma tag

==O comando também pode ser utilizado para visualizar detalhes de uma tag.==

```
git show <nome-da-tag>
```

Exemplo:

```
git show v1.0
```

Nesse caso, o Git exibirá a mensagem da tag, o commit associado e todas as alterações referentes àquele checkpoint.

Quando utilizar

- Consultar informações de um commit.
- Visualizar alterações realizadas em arquivos.
- Analisar o histórico do projeto.
- Verificar detalhes de uma versão marcada por uma tag.

==O `git show` é uma ferramenta muito útil para inspecionar o estado atual do projeto e entender exatamente o que foi alterado em cada commit.==

==Além de exibir informações do branch atual e suas modificações, ele também permite consultar detalhes de tags utilizando o comando `git show <nome-da-tag>`.==

## GIT DIFF

==O comando **`git diff`** é utilizado para **exibir as diferenças entre versões de arquivos, commits ou branches**.==

Ele permite visualizar exatamente quais linhas foram adicionadas, removidas ou modificadas antes de realizar um commit ou um merge.

O que o `git diff` faz?

- Mostra alterações que ainda não foram commitadas.
- Compara diferentes versões de arquivos.
- Permite analisar diferenças entre branches e commits.
- Auxilia na revisão do código antes de enviá-lo ao repositório.

Como utilizar

Exibir as alterações atuais

```
git diff
```

Esse comando mostra as diferenças entre os arquivos modificados e a última versão salva no Git.

> [!example]  
> Exemplo prático
> 
> Você alterou o arquivo:
> 
> ```
> Login.java
> ```
> 
> Antes do commit, execute:
> 
> ```
> git diff
> ```
> 
> O Git exibirá algo semelhante a:
> 
> ```
> - String senha = "";+ String senha = "123";
> ```
> 
> O símbolo `-` representa uma linha removida e o símbolo `+` representa uma linha adicionada.

Comparando arquivos específicos

Também é possível comparar dois arquivos:

```
git diff <arquivo_a> <arquivo_b>
```

Exemplo:

```
git diff Login.java LoginBackup.java
```

O Git mostrará todas as diferenças existentes entre os dois arquivos.

Comparando branches

==O comando também pode ser utilizado para verificar diferenças entre branches.==

```
git diff main feature-login
```

Nesse caso, serão exibidas todas as alterações existentes entre a branch `main` e a branch `feature-login`.

Observação importante

⚠️ **O `git diff` apenas exibe as diferenças. Ele não altera nenhum arquivo do projeto.**

Além disso, em muitos materiais é dito que ele mostra as diferenças entre a branch local e a remota. Embora isso seja possível, normalmente utiliza-se uma sintaxe mais específica, por exemplo:

```
git diff main origin/main
```

Quando utilizar

- Revisar alterações antes de um commit.
- Comparar duas versões de um arquivo.
- Analisar diferenças entre branches.
- Verificar modificações antes de realizar um merge.

==O `git diff` é uma das ferramentas mais importantes do Git para revisão de código, pois permite visualizar exatamente o que foi alterado antes de compartilhar ou integrar as mudanças ao projeto.==

==Além de comparar o estado atual do projeto, ele também pode ser utilizado para verificar diferenças entre arquivos, commits e branches, facilitando a análise do histórico de desenvolvimento.==

## GIT SHORTLOG

==O comando **`git shortlog`** é utilizado para **exibir um resumo do histórico de commits do projeto, agrupando-os por autor**.==

Ele é muito útil para visualizar rapidamente quem contribuiu para o projeto e quantos commits cada desenvolvedor realizou.

O que o `git shortlog` faz?

- Exibe um resumo dos commits do repositório.
- Agrupa os commits pelo nome do autor.
- Facilita a identificação das contribuições de cada desenvolvedor.
- Auxilia na análise do histórico do projeto.

Como utilizar

Exibir o log resumido

```
git shortlog
```

Exemplo de saída:

```
Gustavo Sales (3):      Implementa sistema de login      Corrige validação de senha      Adiciona tela de cadastroMaria Silva (2):      Ajusta layout da aplicação      Corrige bug no relatório
```

Nesse exemplo, é possível identificar quantos commits cada autor realizou e suas respectivas mensagens.

> [!example]  
> Exemplo prático
> 
> Em um projeto desenvolvido por vários integrantes, execute:
> 
> ```
> git shortlog
> ```
> 
> O Git agrupará automaticamente os commits por autor, permitindo visualizar rapidamente as contribuições de cada membro da equipe.

Exibindo a quantidade de commits

==Para obter uma visão ainda mais resumida, utilize a opção `-s` (summary):==

```
git shortlog -s
```

Exemplo de saída:

```
     15  Gustavo Sales      8  Maria Silva      5  João Pereira
```

Também é comum utilizar a opção `-sn` para ordenar pela quantidade de commits:

```
git shortlog -sn
```

Quando utilizar

- Verificar quem contribuiu para o projeto.
- Identificar a quantidade de commits por desenvolvedor.
- Gerar um resumo rápido do histórico do repositório.
- Analisar a participação dos membros da equipe.

==O `git shortlog` é uma ferramenta bastante útil em projetos colaborativos, pois organiza os commits por autor e permite identificar facilmente quem realizou cada alteração no código.==

==Dessa forma, é possível saber quais commits foram enviados ao projeto e por quem, sem precisar analisar todo o histórico detalhado do `git log`.==

## GIT DESCRIBE

==O comando **`git describe`** é utilizado para **identificar um commit com base na tag mais próxima do histórico do projeto**.==

Quando utilizado com a opção `--tags`, ele permite visualizar as tags relacionadas ao estado atual do repositório.

O que o `git describe` faz?

- Localiza a tag mais próxima de um commit.
- Exibe uma descrição baseada nas tags do projeto.
- Facilita a identificação de versões durante o desenvolvimento.
- Auxilia na localização de checkpoints importantes.

Como utilizar

Exibir a descrição baseada nas tags

```
git describe --tags
```

Exemplo de saída:

```
v1.0-3-g8f4c2d1
```

Nesse resultado:

- `v1.0` → última tag encontrada.
- `3` → quantidade de commits após essa tag.
- `g8f4c2d1` → identificador abreviado do commit atual.

> [!example]  
> Exemplo prático
> 
> Imagine que a última versão oficial do projeto seja:
> 
> ```
> v2.0
> ```
> 
> Após três novos commits, ao executar:
> 
> ```
> git describe --tags
> ```
> 
> O Git poderá retornar:
> 
> ```
> v2.0-3-g5b7a9e3
> ```
> 
> Isso indica que você está três commits à frente da tag `v2.0`.

Exibindo todas as referências

==Utilizando a opção `--all`, o comando também considera outras referências do Git, como branches e tags.==

```
git describe --all
```

Exemplo de saída:

```
heads/main
```

ou

```
tags/v2.0
```

Essa opção fornece uma descrição mais completa da posição atual do projeto no histórico.

Observação importante

⚠️ **Embora muitos materiais didáticos descrevam `git describe --tags` como um comando para listar todas as tags, sua principal função é descrever um commit usando a tag mais próxima.**

Para listar todas as tags existentes, normalmente utiliza-se:

```
git tag
```

Quando utilizar

- Identificar rapidamente a versão atual do projeto.
- Verificar a tag mais próxima de um commit.
- Auxiliar em processos de versionamento.
- Obter referências de branches e tags com a opção `--all`.

==O `git describe` é bastante utilizado em projetos que adotam versionamento por tags, permitindo identificar facilmente em qual estágio do desenvolvimento o código atual se encontra.==

==Com a opção `--tags`, o comando utiliza as tags como referência, enquanto a opção `--all` também considera branches e outras referências existentes no repositório.==

