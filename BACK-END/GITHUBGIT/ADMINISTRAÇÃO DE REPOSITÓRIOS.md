## BOAS PRÁTICAS

==Seguir **boas práticas no Git** é fundamental para manter o histórico do projeto organizado, facilitar o trabalho em equipe e evitar perda de código.==

As boas práticas ajudam a tornar o desenvolvimento mais seguro e tornam a colaboração entre desenvolvedores muito mais eficiente.

Principais boas práticas

- Realize commits pequenos e frequentes.
- Escreva mensagens de commit claras e objetivas.
- Crie uma branch para cada nova funcionalidade ou correção.
- Atualize sua branch com `git pull` antes de enviar alterações.
- Revise suas modificações com `git diff` antes de realizar um commit.
- Utilize `.gitignore` para arquivos temporários e configurações locais.
- Evite trabalhar diretamente na branch principal (`main` ou `master`).
- Faça merge apenas de funcionalidades testadas.

Fluxo recomendado

Um fluxo bastante utilizado no dia a dia é:

```
git pullgit switch -c nova-featuregit add .git commit -m "Implementa nova funcionalidade"git push origin nova-feature
```

Após a revisão e os testes, a branch pode ser integrada à principal através de um merge.

> [!example]  
> Exemplo prático
> 
> Você precisa adicionar uma tela de cadastro ao sistema.
> 
> Em vez de alterar diretamente a `main`, crie uma branch:
> 
> ```
> git switch -c cadastro-usuarios
> ```
> 
> Desenvolva a funcionalidade, realize commits periódicos e envie a branch:
> 
> ```
> git push origin cadastro-usuarios
> ```
> 
> Após a validação, faça o merge para a branch principal.

Mensagens de commit

==Uma boa mensagem de commit deve descrever claramente o que foi alterado.==

Exemplos:

```
Implementa sistema de loginCorrige validação de senhaAdiciona tela de cadastro de usuários
```

Evite mensagens genéricas como:

```
testealteraçõescorrigido
```

Cuidados importantes

⚠️ **Antes de executar comandos destrutivos como `git reset --hard` ou `git clean -f`, verifique se não existe nenhum trabalho importante que ainda não foi salvo.**

Se necessário, utilize:

```
git stash
```

para armazenar temporariamente suas alterações.

Organização do projeto

Também é recomendado:

- Utilizar tags para marcar versões importantes.
- Manter o `.gitignore` atualizado.
- Excluir branches locais que não serão mais utilizadas.
- Sincronizar frequentemente o repositório local com o remoto.

==No desenvolvimento profissional, boas práticas no Git são essenciais para manter um histórico limpo, facilitar a manutenção do projeto e reduzir conflitos entre os membros da equipe.==

==Pequenos commits, branches organizadas, mensagens claras e atualizações frequentes do repositório são hábitos que tornam o fluxo de trabalho muito mais eficiente e seguro.==
## GIT CLEAN

==O comando **`git clean`** é utilizado para **remover arquivos que não estão sendo monitorados (untracked) pelo Git**.==

Esses arquivos são aqueles que ainda não foram adicionados ao controle de versão com o comando `git add`.

⚠️ **Atenção:** os arquivos removidos pelo `git clean` não podem ser recuperados pelo Git, pois nunca fizeram parte do repositório.

O que o `git clean` faz?

- Remove arquivos não rastreados (untracked).
- Limpa arquivos temporários ou gerados automaticamente.
- Ajuda a manter o diretório de trabalho organizado.
- Não remove arquivos que já estão sendo monitorados pelo Git.

Como utilizar

Visualizar quais arquivos serão removidos

```
git clean -n
```

ou

```
git clean --dry-run
```

Esse comando apenas exibe os arquivos que seriam apagados, sem removê-los.

Exemplo de saída:

```
Would remove arquivo.tmpWould remove teste.log
```

Remover os arquivos não rastreados

```
git clean -f
```

A opção `-f` (**force**) é obrigatória para confirmar a remoção.

> [!example]  
> Exemplo prático
> 
> Ao executar:
> 
> ```
> git status
> ```
> 
> O Git retorna:
> 
> ```
> Untracked files:    teste.txt    log.tmp
> ```
> 
> Para verificar o que será apagado:
> 
> ```
> git clean -n
> ```
> 
> Se estiver tudo correto, execute:
> 
> ```
> git clean -f
> ```
> 
> Os arquivos `teste.txt` e `log.tmp` serão removidos do diretório.

Removendo diretórios não rastreados

Caso existam pastas untracked, utilize a opção `-d`:

```
git clean -fd
```

Esse comando remove tanto arquivos quanto diretórios que não estejam sendo monitorados.

Quando utilizar

- Remover arquivos temporários.
- Apagar arquivos gerados automaticamente.
- Limpar o ambiente de desenvolvimento.
- Eliminar arquivos que atrapalham a visualização do `git status`.

==O `git clean` é muito útil para manter o projeto organizado, principalmente quando ferramentas ou compiladores geram diversos arquivos que não precisam ser versionados.==

==Ele atua apenas sobre arquivos untracked, ou seja, aqueles que ainda não foram adicionados ao Git através do comando `git add`.==

## GIT GC

==O comando **`git gc`** (Garbage Collector) é utilizado para **realizar a manutenção e otimização do repositório Git**.==

Ele reorganiza os arquivos internos do Git e remove dados desnecessários, melhorando o desempenho e reduzindo o espaço utilizado.

O que o `git gc` faz?

- Remove objetos que não são mais necessários.
- Compacta o histórico do repositório.
- Reorganiza os arquivos internos do Git.
- Otimiza o desempenho das operações do repositório.
- Reduz o espaço em disco utilizado pelo banco de dados do Git.

Como utilizar

Executar a limpeza e otimização do repositório

```
git gc
```

Ao executar esse comando, o Git analisará automaticamente o repositório e realizará os processos de manutenção necessários.

> [!example]  
> Exemplo prático
> 
> Após muitos commits, merges, branches e exclusões, o repositório pode acumular diversos objetos internos que não são mais utilizados.
> 
> Para realizar a manutenção, basta executar:
> 
> ```
> git gc
> ```
> 
> O Git reorganizará esses dados e otimizará a estrutura do repositório.

Observação importante

⚠️ **Na maioria das situações, não é necessário executar o `git gc` manualmente. O próprio Git realiza essa otimização automaticamente em determinados momentos.**

O comando é mais utilizado quando:

- O repositório está muito grande.
- Foram criadas e removidas muitas branches.
- Houve grande quantidade de commits e merges.
- Deseja-se realizar uma manutenção manual.

Garbage Collector

==O termo "Garbage Collector" significa "coletor de lixo". Sua função é identificar objetos que não possuem mais referências válidas e eliminá-los com segurança.==

Esse processo não remove commits válidos nem altera o histórico normal do projeto, apenas limpa dados internos que deixaram de ser necessários.

Quando utilizar

- Realizar manutenção do repositório.
- Melhorar a performance das operações do Git.
- Compactar objetos internos.
- Reduzir o espaço ocupado pelo banco de dados do Git.

==O `git gc` é uma ferramenta de otimização e manutenção interna do Git. Ele identifica arquivos e objetos que não são mais necessários, removendo-os e reorganizando a estrutura do repositório.==

==Esse processo contribui para um melhor desempenho, especialmente em projetos grandes ou com um longo histórico de desenvolvimento.==

## GIT FSCK

==O comando **`git fsck`** (**File System Check**) é utilizado para **verificar a integridade do banco de dados interno do Git**.==

Ele analisa os objetos armazenados no repositório e verifica se existem arquivos corrompidos ou referências inválidas.

O que o `git fsck` faz?

- Verifica a integridade dos objetos do Git.
- Analisa a conectividade entre commits, árvores (trees) e blobs.
- Identifica objetos corrompidos ou ausentes.
- Auxilia na manutenção e diagnóstico do repositório.

Como utilizar

Executar a verificação do repositório

```
git fsck
```

Se tudo estiver correto, normalmente o comando não exibirá erros ou mostrará apenas algumas mensagens informativas.

> [!example]  
> Exemplo prático
> 
> Após realizar diversas operações no repositório, como merges, criação de branches e alterações de histórico, você deseja verificar se não houve nenhum problema interno.
> 
> Basta executar:
> 
> ```
> git fsck
> ```
> 
> O Git analisará todos os objetos armazenados e verificará se a estrutura do repositório está íntegra.

Possíveis resultados

Se algum problema for encontrado, o Git poderá exibir mensagens semelhantes a:

```
missing blob 8f4c2d1...dangling commit 5b7a9e3...
```

- **missing blob** → um objeto esperado não foi encontrado.
- **dangling commit** → um commit existe, mas não está referenciado por nenhuma branch ou tag.

⚠️ **Nem toda mensagem exibida pelo `git fsck` representa um erro grave. Objetos "dangling", por exemplo, podem surgir naturalmente após operações como `git rebase` ou `git stash`.**

Quando utilizar

- Verificar a saúde do repositório.
- Diagnosticar possíveis corrupções.
- Validar a integridade dos objetos do Git.
- Realizar manutenção preventiva.

Diferença entre `git gc` e `git fsck`

```
git gc   → Otimiza e limpa o repositório.git fsck → Verifica a integridade e a consistência dos arquivos internos.
```

==O `git fsck` é uma ferramenta de diagnóstico que verifica se todos os objetos do repositório estão corretos e conectados adequadamente, ajudando a identificar possíveis corrupções ou inconsistências.==

==Por esse motivo, é considerado um comando de manutenção, utilizado periodicamente para garantir que o repositório esteja funcionando corretamente.==
## GIT REFLOG

==O comando **`git reflog`** é utilizado para **registrar todas as movimentações realizadas no repositório local**, incluindo mudanças de branch, commits, merges, resets e outras operações do Git.==

Diferentemente do `git log`, o reflog registra praticamente todas as ações executadas pelo usuário, funcionando como um histórico das operações locais.

O que o `git reflog` faz?

- Registra mudanças de branch.
- Armazena commits, merges, resets e checkouts.
- Permite recuperar referências perdidas.
- Auxilia na restauração de estados anteriores do repositório.
- Mantém um histórico das ações realizadas localmente.

Como utilizar

Exibir o reflog

```
git reflog
```

Exemplo de saída:

```
8f4c2d1 HEAD@{0}: commit: Corrige validação de senha5b7a9e3 HEAD@{1}: checkout: moving from main to feature-login2d8f4a1 HEAD@{2}: commit: Implementa sistema de login
```

Cada entrada representa uma operação realizada no repositório local.

> [!example]  
> Exemplo prático
> 
> Você estava trabalhando na branch `main` e mudou para a branch `feature-login`:
> 
> ```
> git switch feature-login
> ```
> 
> Mais tarde, ao executar:
> 
> ```
> git reflog
> ```
> 
> O Git exibirá essa mudança de branch juntamente com outras operações realizadas.

Diferença entre `git reflog` e `git log`

==Embora ambos exibam histórico, seus objetivos são diferentes.==

```
git log    → Mostra apenas os commits de uma branch.git reflog → Mostra todas as movimentações realizadas localmente.
```

Por exemplo, um `git checkout`, `git reset` ou `git stash` aparecerá no reflog, mas não necessariamente no log de commits.

Recuperando estados anteriores

Uma das principais utilidades do reflog é recuperar referências perdidas.

Exemplo:

```
git reset --hard HEAD@{2}
```

Esse comando faz o repositório voltar para o estado registrado na posição `HEAD@{2}`.

⚠️ **O uso de `git reset --hard` pode descartar alterações locais. Utilize esse comando com cuidado.**

Expiração do reflog

==As entradas do reflog não são armazenadas para sempre. Por padrão, elas permanecem disponíveis por aproximadamente 30 dias antes de serem removidas pelo processo de limpeza do Git.==

Quando utilizar

- Recuperar commits ou referências perdidas.
- Consultar mudanças de branch.
- Verificar operações realizadas no repositório.
- Restaurar estados anteriores após um reset ou checkout.

==O `git reflog` funciona como um histórico detalhado das ações locais do Git, registrando praticamente todos os passos realizados durante o desenvolvimento.==

==Enquanto o `git log` exibe apenas os commits de uma branch, o `git reflog` registra operações como mudanças de branch, merges, resets e checkouts, sendo uma ferramenta extremamente útil para recuperação de trabalho perdido.==

==O **`git reflog`** pode ser utilizado para **recuperar estados anteriores do repositório**, permitindo avançar ou retroceder para qualquer referência registrada no histórico local.==

Para isso, normalmente utiliza-se o comando `git reset --hard`.

⚠️ **Atenção:** o `git reset --hard` descarta todas as alterações locais não salvas. Se houver algum trabalho importante, utilize `git stash` antes de executar esse comando.

O que o `git reset --hard` faz?

- Move a branch atual para um commit específico.
- Atualiza os arquivos do projeto para aquele estado.
- Remove alterações locais que não foram commitadas.
- Permite recuperar commits ou referências encontradas no reflog.

Como utilizar

Primeiro, visualize o reflog:

```
git reflog
```

Exemplo de saída:

```
8f4c2d1 HEAD@{0}: commit: Corrige validação de senha5b7a9e3 HEAD@{1}: checkout: moving from main to feature-login2d8f4a1 HEAD@{2}: commit: Implementa sistema de login
```

Em seguida, escolha a referência desejada e execute:

```
git reset --hard <hash>
```

Exemplo:

```
git reset --hard 2d8f4a1
```

Também é possível utilizar a referência do próprio reflog:

```
git reset --hard HEAD@{2}
```

> [!example]  
> Exemplo prático
> 
> Você executou um `git reset --hard` por engano e perdeu um commit recente.
> 
> Ao consultar o reflog:
> 
> ```
> git reflog
> ```
> 
> Encontra a seguinte entrada:
> 
> ```
> 8f4c2d1 HEAD@{1}: commit: Corrige validação de senha
> ```
> 
> Para recuperar esse estado:
> 
> ```
> git reset --hard 8f4c2d1
> ```
> 
> O projeto voltará exatamente para o momento daquele commit.

Salvando alterações antes do reset

==Se existir algum trabalho que ainda não foi commitado e você deseja preservá-lo, utilize o `git stash` antes do reset.==

```
git stashgit reset --hard HEAD@{2}
```

Posteriormente, as alterações podem ser recuperadas com:

```
git stash pop
```

Observação importante

⚠️ **O reflog é um histórico local e temporário. Por padrão, suas entradas expiram após aproximadamente 30 dias, podendo ser removidas durante a manutenção do Git.**

Por isso, se precisar recuperar alguma referência antiga, é recomendável fazê-lo antes da expiração.

Quando utilizar

- Recuperar commits perdidos.
- Desfazer um `git reset` executado por engano.
- Restaurar estados anteriores do projeto.
- Navegar pelo histórico registrado no reflog.

==O reflog é uma poderosa ferramenta de recuperação do Git. Utilizando `git reset --hard <hash>`, é possível avançar ou retroceder para qualquer estado registrado no histórico local.==

==Entretanto, como o reflog possui um tempo de expiração e o `reset --hard` descarta alterações locais, é recomendável utilizar `git stash` para salvar trabalhos importantes antes de realizar essa operação.==

## GIT ARCHIVE

==O comando **`git archive`** é utilizado para **gerar um arquivo compactado a partir de uma branch, tag ou commit do repositório**.==

Ele permite criar uma cópia do projeto para distribuição ou backup, sem incluir a pasta oculta `.git` e seu histórico de versões.

O que o `git archive` faz?

- Cria um arquivo compactado do projeto.
- Pode gerar arquivos nos formatos `.zip` ou `.tar`.
- Exporta apenas os arquivos do projeto, sem o histórico do Git.
- Permite criar pacotes de versões específicas através de branches ou tags.

Como utilizar

Gerar um arquivo ZIP da branch `master`

```
git archive --format zip --output master_files.zip master
```

Nesse comando:

- `--format zip` → define o formato do arquivo compactado.
- `--output master_files.zip` → define o nome do arquivo gerado.
- `master` → indica a branch que será exportada.

> [!example]  
> Exemplo prático
> 
> Você deseja compartilhar a versão atual da branch principal do projeto sem enviar o histórico do Git.
> 
> Execute:
> 
> ```
> git archive --format zip --output master_files.zip master
> ```
> 
> Ao final, será criado o arquivo:
> 
> ```
> master_files.zip
> ```
> 
> Esse arquivo conterá todos os arquivos da branch `master`, mas não incluirá a pasta `.git`.

Exportando outra branch

Também é possível criar um arquivo compactado de qualquer outra branch:

```
git archive --format zip --output login.zip feature-login
```

Nesse caso, será exportado o conteúdo da branch `feature-login`.

Exportando uma tag

==O comando também pode ser utilizado para gerar um pacote de uma versão marcada por uma tag.==

```
git archive --format zip --output versao1.zip v1.0
```

Isso é bastante comum para distribuir versões oficiais do software.

Observação importante

⚠️ **O arquivo gerado pelo `git archive` não contém o histórico de commits, branches ou tags. Apenas os arquivos presentes na referência escolhida são exportados.**

Por isso, ele é ideal para:

- Distribuir versões finais do projeto.
- Criar backups do código-fonte.
- Compartilhar o sistema com usuários que não precisam do histórico Git.

Quando utilizar

- Gerar uma versão compactada do projeto.
- Distribuir uma release para clientes.
- Criar backups do código-fonte.
- Exportar uma branch ou tag específica.

==O `git archive` é uma ferramenta utilizada para transformar o conteúdo de uma branch, tag ou commit em um arquivo compactado, facilitando a distribuição e o armazenamento do projeto.==

==Por exemplo, ao executar:==

```
git archive --format zip --output master_files.zip master
```

==todo o conteúdo da branch `master` será compactado no arquivo `master_files.zip`, sem incluir os dados internos do Git.==

## GIT REBASE

==O comando **`git rebase`** é utilizado para **reaplicar os commits de uma branch sobre outra**, criando um histórico mais linear e organizado.==

Diferentemente do `git merge`, o `rebase` move os commits de uma branch para o topo de outra, evitando a criação de commits de merge.

O que o `git rebase` faz?

- Reaplica commits sobre outra branch.
- Mantém o histórico do projeto mais limpo e linear.
- Atualiza uma branch com as alterações mais recentes.
- Evita commits extras de merge em muitos cenários.

Como utilizar

Primeiro, acesse a branch que deseja atualizar:

```
git switch feature-login
```

Em seguida, execute o rebase utilizando a branch de destino:

```
git rebase main
```

Nesse exemplo, todos os commits da `feature-login` serão reaplicados sobre a versão mais recente da `main`.

> [!example]  
> Exemplo prático
> 
> Imagine o seguinte cenário:
> 
> ```
> main:          A --- B --- C                        \feature-login:           D --- E
> ```
> 
> Enquanto você desenvolvia a funcionalidade, a branch `main` recebeu novas alterações.
> 
> Ao executar:
> 
> ```
> git switch feature-logingit rebase main
> ```
> 
> O histórico ficará semelhante a:
> 
> ```
> main:          A --- B --- C                              \feature-login:                 D' --- E'
> ```
> 
> Os commits são recriados sobre a versão mais atual da `main`.

Diferença entre `git merge` e `git rebase`

==Embora ambos sirvam para integrar alterações, eles funcionam de maneiras diferentes.==

```
git merge  → Une os históricos das branches.git rebase → Reorganiza o histórico reaplicando os commits.
```

Exemplo visual:

```
Merge:A --- B --- C -------- M      \              /       D ---------- ERebase:A --- B --- C --- D' --- E'
```

Conflitos durante o rebase

⚠️ **Caso existam alterações conflitantes, o Git interromperá o processo e solicitará a resolução manual dos conflitos.**

Após corrigir os arquivos, execute:

```
git add .git rebase --continue
```

Caso queira cancelar toda a operação:

```
git rebase --abort
```

Boas práticas

==O `git rebase` é muito utilizado para atualizar uma branch de desenvolvimento antes de realizar um merge na branch principal.==

Entretanto, existe uma recomendação importante:

⚠️ **Evite utilizar `git rebase` em branches compartilhadas com outros desenvolvedores, pois ele reescreve o histórico dos commits e pode causar conflitos no trabalho da equipe.**

Quando utilizar

- Atualizar uma branch com a versão mais recente da `main`.
- Manter o histórico do projeto linear.
- Preparar uma branch antes de um merge.
- Organizar o histórico de commits.

==O `git rebase` é uma poderosa ferramenta para reorganizar o histórico do Git, reaplicando commits sobre uma base mais recente e deixando o fluxo de desenvolvimento mais limpo.==

==Em projetos profissionais, é comum utilizar `git rebase` para atualizar branches de funcionalidade antes da integração com a branch principal, sempre tomando cuidado para não reescrever o histórico de branches compartilhadas.==