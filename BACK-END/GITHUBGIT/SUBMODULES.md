## GIT SUBMODULE

==O recurso de **Submódulos (Submodules)** permite **adicionar um repositório Git dentro de outro repositório**, mantendo ambos independentes.==

Essa funcionalidade é muito útil quando um projeto depende de outro, mas cada um deve possuir seu próprio histórico de versões.

O que um Submódulo faz?

- Permite trabalhar com dois ou mais projetos em um único repositório.
- Mantém cada projeto com seu próprio histórico Git.
- Facilita o compartilhamento de bibliotecas ou componentes comuns.
- Evita a duplicação de código entre projetos.

Como utilizar

Adicionar um submódulo

```
git submodule add <repositorio>
```

Exemplo:

```
git submodule add https://github.com/usuario/biblioteca-java.git
```

==Após a execução, o Git adicionará o repositório como uma pasta dentro do projeto atual e criará um arquivo chamado:==

```
.gitmodules
```

Esse arquivo armazena as informações dos submódulos utilizados pelo projeto.

> [!example]  
> Exemplo prático
> 
> Imagine que você possui um sistema principal chamado:
> 
> ```
> sistema-vendas
> ```
> 
> E deseja reutilizar uma biblioteca desenvolvida em outro projeto:
> 
> ```
> biblioteca-relatorios
> ```
> 
> Em vez de copiar os arquivos manualmente, basta executar:
> 
> ```
> git submodule add https://github.com/usuario/biblioteca-relatorios.git
> ```
> 
> Agora, a biblioteca fará parte do projeto, mas continuará sendo um repositório independente.

Visualizando os submódulos

Para listar todos os submódulos adicionados ao projeto:

```
git submodule
```

Exemplo de saída:

```
8f4c2d1 biblioteca-relatorios (heads/main)
```

Esse comando exibe o commit atual e o caminho do submódulo.

Observação importante

⚠️ **Um submódulo não é uma cópia do projeto. Ele apenas referencia um commit específico de outro repositório.**

Por isso, quando outro desenvolvedor clona o projeto, geralmente é necessário inicializar os submódulos com:

```
git submodule update --init --recursive
```

Quando utilizar

- Compartilhar bibliotecas entre vários projetos.
- Utilizar componentes desenvolvidos por outra equipe.
- Organizar projetos grandes em módulos independentes.
- Reaproveitar código sem duplicá-lo.

==No desenvolvimento profissional, os submódulos são utilizados quando um projeto depende de outro repositório, mas ambos precisam continuar com suas estruturas e históricos separados.==

==Os comandos mais importantes são `git submodule add <repo>` para adicionar um submódulo e `git submodule` para listar todos os submódulos existentes no projeto.==

## ATUALIZANDO SUBMÓDULOS

==Quando trabalhamos com **Submódulos**, as alterações realizadas neles precisam ser commitadas e enviadas para o repositório do próprio submódulo.==

Para facilitar esse processo, o Git oferece a opção `--recurse-submodules=on-demand`, que envia automaticamente as alterações necessárias dos submódulos.

O que o `git push --recurse-submodules=on-demand` faz?

- Verifica se existem alterações commitadas em submódulos.
- Envia essas alterações para o repositório remoto do submódulo.
- Evita que o repositório principal aponte para um commit inexistente no servidor.
- Atualiza apenas os submódulos que realmente precisam ser enviados.

Como utilizar

Primeiro, realize o commit das alterações dentro do submódulo:

```
git add .git commit -m "Atualização do submódulo"
```

Depois, a partir do repositório principal, execute:

```
git push --recurse-submodules=on-demand
```

Esse comando enviará automaticamente os commits pendentes dos submódulos antes de concluir o push do projeto principal.

> [!example]  
> Exemplo prático
> 
> Imagine que seu projeto possui o seguinte submódulo:
> 
> ```
> biblioteca-relatorios
> ```
> 
> Você realizou algumas alterações nessa biblioteca e fez um commit:
> 
> ```
> git add .git commit -m "Corrige geração de PDF"
> ```
> 
> Ao voltar para o projeto principal, execute:
> 
> ```
> git push --recurse-submodules=on-demand
> ```
> 
> O Git verificará se o submódulo possui commits não enviados e fará o push automaticamente antes de concluir a atualização do projeto principal.

Observação importante

⚠️ **Esse comando só enviará os submódulos que possuírem alterações commitadas. Caso não exista nenhum commit pendente, ele funcionará como um `git push` comum.**

Além disso, é importante lembrar que:

- Primeiro faz-se o commit no submódulo.
- Depois atualiza-se a referência do submódulo no projeto principal.
- Por fim, realiza-se o `git push`.

Quando utilizar

- Ao modificar um submódulo existente.
- Ao compartilhar atualizações de bibliotecas reutilizáveis.
- Para garantir que o repositório principal referencie commits já disponíveis no servidor.
- Em projetos que utilizam múltiplos repositórios integrados.

==No desenvolvimento com submódulos, é fundamental que as alterações sejam commitadas antes do envio. O comando `git push --recurse-submodules=on-demand` automatiza esse processo, enviando apenas os submódulos que realmente precisam ser atualizados.==

==Esse fluxo garante que outros desenvolvedores consigam acessar corretamente a versão mais recente dos submódulos ao atualizar o projeto.==