## CONCEITO

Loop (ou laço de repetição) é quando você quer **executar um bloco de código várias vezes** sem repetir código manualmente.

Em vez de fazer isso:

```
System.out.println("Oi");
System.out.println("Oi");
System.out.println("Oi");
```

Você faz:

```
for (int i = 0; i < 3; i++) {
    System.out.println("Oi");
}
```

Você precisa dominar 3:

- `for`
- `while`
- `do while`

## ESTRUTURAS DE LOOP


| Estrtura     | Exemplo                                                                          | Uso                                     |
| ------------ | -------------------------------------------------------------------------------- | --------------------------------------- |
| for/for-each | for (int i = 0; i < 5; i++) {<br>    System.out.println(i);<br>}                 | Quando você sabe quantas vezes repetir. |
| while        | int i = 0;<br><br>while (i < 5) {<br>    System.out.println(i);<br>    i++;<br>} | Quando depende de condição              |
| do while     |                                                                                  | Quando precisa rodar pelo menos 1 vez   |

#### FOR (o mais usado)

Sintaxe:


```
for (inicialização; condição; incremento) {
    // código
}

```


Exemplo:


```
for (int i = 0; i < 5; i++) {
    System.out.println(i);
}
```



O que acontece:
Int i (variável usada como indice) = 0 Começa em zero.

i < 5 Roda enquanto i for verdadeiro (menor que 5)

i++ (soma 1 a cada volta, se não tivesse i++ rodaria infinitamente)

```
Saída:

0
1
2
3
4

```

Quando usar?

Quando você sabe quantas vezes repetir.
- percorrer lista.
- contar números.
- repetir X vezes. 

#### WHILE 

Sintaxe:

```
while (condição) {
    // código
}

```

Exemplo: 


```
int i = 0;

while (i < 5) {
    System.out.println(i);
    i++;
}
```


```
Saída:

0
1
2
3
4

```

Quando usar:

Quando você NÃO sabe quantas vezes vai repetir.

- esperar input do usuário
- loop até condição ser atendida
- sistemas interativos

#### DO WHILE

Sintaxe:


```
do {
    // código
} while (condição);
```


Exemplo: 


```
int i = 0;

do {
    System.out.println(i);
    i++;
} while (i < 5);

```


```
Saída:

0
1
2
3
4

```

O do while executa pelo menos 1 vez, mesmo se a condição for falsa.

Por exemplo:


```
int i = 10;

do {
    System.out.println("Executou");
} while (i < 5);
```


Vai executar mesmo assim.

## Controle de loops

- Break para parar o Loop


```
for (int i = 0; i < 10; i++) {
    if (i == 5) {
        break;
    }
    System.out.println(i);
}
```



Para quando chega em 5.

- Continue pula uma volta.


```
for (int i = 0; i < 5; i++) {
    if (i == 2) {
        continue;
    }
    System.out.println(i);
}

```


Pula o 2.

- Loop infinito


```
while (true) {
    System.out.println("Nunca para");
}
```


Muito usado em:
servidores
jogos
sistemas rodando continuamente

- Loops com array (o mais importante) 


```
int[] numeros = {10, 20, 30};

for (int i = 0; i < numeros.length; i++) {
    System.out.println(numeros[i]);
}
```

## FOR-EACH (FOR MELHORADO)

O for-each é uma forma simplificada de percorrer **coleções de dados** (arrays, listas, etc).

Sintaxe:

```
for (Tipo variavel : colecao) {
    // uso da variável
}
```

Exemplo:

```
int[] numeros = {10, 20, 30};

for (int num : numeros) {
    System.out.println(num);
}
```

- `numeros` → coleção
- `num` → cada elemento da coleção

```
for (int num : numeros)
```

É equivalente a:

```
for (int i = 0; i < numeros.length; i++) {
    int num = numeros[i];
}
```

- Ele percorre automaticamente
- Sem você controlar índice

#### Funciona com o quê?

- Arrays
  
```
  int[] arr = {1, 2, 3};
```

-  ArrayList

```
   List< String > nomes = new ArrayList<>();
```

- Set

```
  Set< Integer > numeros = new HashSet<>();
```

#### Exemplo real

```
for (Usuario u : usuarios) {
    System.out.println(u.getNome());
}
```

Percorrer lista de usuários.


Use quando:

- Só quer **ler dados**
- Não precisa do índice
- Não vai alterar a coleção

 Não use:
- Precisa do índice → use `for`
- Precisa remover elementos → use `Iterator`
- Precisa alterar valores → use `for` tradicional
