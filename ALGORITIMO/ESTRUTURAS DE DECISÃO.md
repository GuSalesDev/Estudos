## CONCEITO

Estruturas de decisão são os mecanismos que permitem ao algoritmo ou programa escolher um caminho com base em uma condição.
Sem estrutura de decisão, o programa executaria tudo sempre do mesmo jeito.  
Com ela, ele passa a “pensar” em termos de:

- se isso acontecer, faça isso
- senão, faça outra coisa
- se for esse caso específico, execute tal bloco

Em outras palavras, estrutura de decisão é o que dá controle de fluxo ao programa.

Uma estrutura de decisão analisa uma **condição lógica** e, a partir do resultado dessa condição, define qual trecho do código será executado.

A condição sempre resulta em:

- **verdadeiro**
- **falso**

> [!example]
> Exemplo simples do dia a dia:
> 
> - Se estiver chovendo, levo guarda-chuva.
> - Senão, saio sem guarda-chuva.

Na programação, a lógica é a mesma:

```
if (estaChovendo){
	System.out.println("levar o Guada-Chuva")
	}else{
	Sysyem.out.println("Não Levar o Guarda-Chuva")}
```

Elas são essenciais porque praticamente todo programa precisa tomar decisões.

> [!example]
> Exemplos reais:
> 
> - verificar se login e senha estão corretos
> - saber se o usuário é maior de idade
> - decidir se um produto tem desconto
> - validar se um campo foi preenchido
> - mostrar mensagens diferentes dependendo da nota do aluno
> - liberar ou bloquear acesso a uma área do sistema
> 
> Sem decisão, o programa seria apenas uma sequência fixa de comandos.

```
if (idade >= 18) {
    System.out.println("Maior de idade");
}
```

Aqui:

- `idade >= 18` é a condição
- se for verdadeira, o bloco executa
- se for falsa, ele ignora esse bloco
## Estruturas


| Estrutura        | Exemplo                                                                                                                                                                                                                                                                                                                               | Uso                                                                                            |
| ---------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- |
| if (se)          | int idade = 20;<br><br>if (idade >= 18) {<br>    System.out.println("Você é maior de idade.");<br>}                                                                                                                                                                                                                                   | se a condição for verdadeira, execute este bloco.                                              |
| if else (se não) | int idade = 16;<br><br>if (idade >= 18) {<br>    System.out.println("Maior de idade");<br>} else {<br>    System.out.println("Menor de idade");<br>}                                                                                                                                                                                  | se a condição for verdadeira, faça uma coisa; senão, faça outra.                               |
| if else if else  | int nota = 8;<br><br>if (nota >= 9) {<br>    System.out.println("Excelente");<br>} else if (nota >= 7) {<br>    System.out.println("Bom");<br>} else if (nota >= 5) {<br>    System.out.println("Regular");<br>} else {<br>    System.out.println("Insuficiente");<br>}                                                               | Essa é usada quando existem várias possibilidades.                                             |
| switch case      | int dia = 3;<br><br>switch (dia) {<br>    case 1:<br>        System.out.println("Domingo");<br>        break;<br>    case 2:<br>        System.out.println("Segunda");<br>        break;<br>    case 3:<br>        System.out.println("Terça");<br>        break;<br>    default:<br>        System.out.println("Dia inválido");<br>} | O switch é usado quando você quer comparar uma variável com **vários valores fixos possíveis** |
#### if

Sintaxe: 

```

if (condicao) {
    // bloco de código
}

```

Exemplo:

```
int idade = 20;

if (idade >= 18) {
    System.out.println("Você é maior de idade.");
}
```


como funciona:

- o programa avalia `idade >= 18`
- como 20 é maior que 18, o resultado é `true`
- o bloco dentro do `if` é executado

Se a idade fosse 15, nada seria exibido.

==O `if` sozinho executa algo **apenas quando a condição é verdadeira**.==  
==Se a condição for falsa, ele simplesmente segue o fluxo normal do programa.==
#### if else

Sintaxe:

```
if (condicao) {
    // bloco verdadeiro
} else {
    // bloco falso
}
```

Exemplo:

```
int idade = 16;

if (idade >= 18) {
    System.out.println("Maior de idade");
} else {
    System.out.println("Menor de idade");
}
```

Como funciona:

- se `idade >= 18` for verdadeira, executa o `if`
- se for falsa, executa o `else`

> [!important]
> No `if else`, **apenas um dos blocos será executado**.
> 
> Ou:
> 
> - executa o `if`
> - ou executa o `else`
> 
> Nunca os dois ao mesmo tempo.

#### if else if else

Sintaxe:

```
if (condicao1) {
    // bloco 1
} else if (condicao2) {
    // bloco 2
} else if (condicao3) {
    // bloco 3
} else {
    // bloco final
}

```

Exemplo:

```
int nota = 8;

if (nota >= 9) {
    System.out.println("Excelente");
} else if (nota >= 7) {
    System.out.println("Bom");
} else if (nota >= 5) {
    System.out.println("Regular");
} else {
    System.out.println("Insuficiente");
}
```

Como funciona:

Ele verifica **de cima para baixo**:

-  `nota >= 9`  
    não é verdadeiro
-  `nota >= 7`  
    é verdadeiro
- então ele executa `"Bom"` e **para de verificar o resto**

No `if else if else`, a ordem das condições importa muito.
#### switch case

Sintaxe:

```
switch (variavel) {
    case valor1:
        // código
        break;
    case valor2:
        // código
        break;
    default:
        // código padrão
}
```

Exemplo:

```
int dia = 3;

switch (dia) {
    case 1:
        System.out.println("Domingo");
        break;
    case 2:
        System.out.println("Segunda");
        break;
    case 3:
        System.out.println("Terça");
        break;
    default:
        System.out.println("Dia inválido");
}

```
Como funciona:

O `switch` pega o valor da variável e compara com cada `case`.

- se encontrar um caso correspondente, executa aquele bloco
- se não encontrar nenhum, executa o `default`

O `break` serve para **encerrar o switch** depois que um caso foi executado.

Sem ele, o programa continua executando os próximos `case`, mesmo que não correspondam.

 Exemplo sem `break`:

```
int opcao = 1;

switch (opcao) {
    case 1:
        System.out.println("Cadastrar");
    case 2:
        System.out.println("Editar");
    case 3:
        System.out.println("Excluir");
}

Saída:
Cadastrar
Editar
Excluir
```

O `default` é como se fosse o `else` do `switch`.
Ele executa quando nenhum `case` corresponde ao valor.

#### Quando usar

Use `if` quando:

- a condição envolve comparações lógicas
    
- você usa operadores como `>`, `<`, `>=`, `<=`
    
- a decisão depende de intervalos
    
- há expressões compostas com `&&`, `||`

Exemplo:

```
if (idade >= 18 && idade <= 65) {
    System.out.println("Faixa etária permitida");
}
```

Use `switch` quando:

- você quer comparar uma variável com valores fixos
    
- existem vários casos exatos
    
- o código fica mais organizado com opções fechadas

Exemplo:

```
switch (nivel) {
    case "admin":
    case "gerente":
    case "usuario":
}
```

#### Estrutura encadeada

Você também pode colocar uma decisão dentro da outra. Isso é chamado de **decisão aninhada** ou **encadeada**.

Exemplo:
```
int idade = 20;
boolean temCarteira = true;

if (idade >= 18) {
    if (temCarteira) {
        System.out.println("Pode dirigir");
    } else {
        System.out.println("É maior, mas não pode dirigir sem carteira");
    }
} else {
    System.out.println("Menor de idade");
}
```

O que está acontecendo aqui:

Primeiro o programa verifica se a pessoa é maior de idade.  
Depois, dentro desse cenário, verifica se ela possui carteira.

Isso mostra que uma decisão pode depender de outra.

> [!important]
> Cuidado
> 
> Estruturas muito aninhadas podem deixar o código confuso e difícil de manter.

#### Exemplo utilizando tudo:

```
int idade = 22;
String categoria = "premium";
boolean pagamentoEmDia = true;

if (idade < 18) {
    System.out.println("Acesso negado: menor de idade");
} else if (!pagamentoEmDia) {
    System.out.println("Acesso negado: pagamento pendente");
} else {
    switch (categoria) {
        case "premium":
            System.out.println("Acesso completo liberado");
            break;
        case "basico":
            System.out.println("Acesso parcial liberado");
            break;
        default:
            System.out.println("Categoria inválida");
    }
}
```

Aqui temos:

- `if` para verificar idade
- `else if` para verificar pagamento
- `switch` para decidir o tipo de acesso conforme a categoria

Ou seja, várias estruturas de decisão podem trabalhar juntas.