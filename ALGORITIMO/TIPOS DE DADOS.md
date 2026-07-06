Tipo de dado = **define o que uma variável pode armazenar**

> [!example]
> Exemplo:
> - Número?
> - Texto?
> - Verdadeiro ou falso?

## TIPOS PRIMITIVOS

São os mais básicos e mais rápidos.

#### **Número Inteiros:**

| Tipo  | Tamanho              | Exemplo                       | Uso                           |
| ----- | -------------------- | ----------------------------- | ----------------------------- |
| byte  | 8 bits (ou 1 byte)   | byte idade = 25;              | Números pequenos (-128 a 127) |
| short | 16 bits (ou 2 bytes) | short ano = 2026;             | Números inteiros menores      |
| int   | 32 bits (ou 4 bytes) | int contador = 1000;          | Números inteiros padrão       |
| long  | 64 bits (ou 8 bytes) | long populacao = 8000000000L; | Números inteiros grandes      |



Exemplo em Java:

```
int idade = 22;
long populacao = 8000000000L;
```

==O  L é obrigatório no long grande.==

#### **Números decimais:**

| Tipo   | Tamanho | Exemplo                   | Uso                       |
| ------ | ------- | ------------------------- | ------------------------- |
| float  | 4 bytes | float peso = 70.5f;       | Números decimais pequenos |
| double | 8 bytes | double salario = 2500.99; | Números decimais padrão   |
Exemplo:

```
float preco = 10.5f;  
double salario = 2500.75;
```

f é obrigatório no float.

Sempre use double, quase ninguém usa float.

#### **Texto:**

| Tipo | Tamanho | Exemplo           | Uso                   |
| ---- | ------- | ----------------- | --------------------- |
| char | 2 bytes | char letra = 'A'; | Armazena um caractere |

#### **BOOLEAN:**

Apenas dois valores, Verdadeiro ou Falso. 
Muito usado em validações, condições, sistemas.

```
true  // verdadeiro
false // falso
```


| Tipo    | Tamanho | Exemplo               | Uso                   |
| ------- | ------- | --------------------- | --------------------- |
| boolean | 1 bit   | boolean ativo = true; | boolean ativo = true; |


Na prática em Java:

```
boolean temSaldo = true;

if (temSaldo) {
    System.out.println("Compra realizada");
}
```

> [!tip]
> **Dica:**
> 
> - Use `int` para números inteiros na maioria dos casos.
> - Use `double` para números com vírgula (ponto flutuante).
> - Lembre-se de usar **ponto (`.`)** e não **vírgula (`,`)** em números decimais.

## TIPOS NÃO PRIMITIVOS

#### **String:**

| Tipo   | Exemplo                  | Uso                                   |
| ------ | ------------------------ | ------------------------------------- |
| String | String nome = "Gustavo"; | Armazena uma sequência de caracteres. |

> [!important]
> String é um objeto
> 
> Isso muda tudo:
> 
> - Tem métodos
> - Tem comportamento
> - Usa memória diferente

String pool

Java otimiza strings iguais.

```
String a = "Java";
String b = "Java";
```

Eles apontam pro MESMO lugar na memória.

```
String a = new String("Java");
String b = new String("Java");

```

Agora são objetos diferentes.

Alguns métodos de String.

**Tamanho:**

`String nome = "Gustavo";`
`nome.length(); // 7`

**Pegar caractere:**

`nome.charAt(0); // G`

**Converter:**

`nome.toUpperCase(); // GUSTAVO`
`nome.toLowerCase(); // gustavo`

**Buscar:**

```
nome.contains("ta"); // true
nome.startsWith("Gu"); // true
nome.endsWith("vo"); // true
```

**Substring:**

`nome.substring(0, 3); // Gus`

**Substituir:**

`nome.replace("Gus", "Luis");`

**Remover espaços:**

`"  oi  ".trim(); // "oi"`

Exemplo real:

```
String email = "gustavo@email.com";

if (email.contains("@") && email.contains(".")) {
    System.out.println("Email válido");
} else {
    System.out.println("Email inválido");
}
```

#### **Array:**

| Tipo  | Exemplo                     | Uso                                                         |
| ----- | --------------------------- | ----------------------------------------------------------- |
| Array | int[] numeros = new int[5]; | criar listas, este comando criou 5 espaços: [0][1][2][3][4] |
**Inicializando direto:**

`int[] numeros = {10, 20, 30, 40, 50};`

**Acessando:**

`System.out.println(numeros[0]); // 10`

O índice começa a partir da posição 0

**Percorrendo array:**

```
for (int i = 0; i < numeros.length; i++) {
    System.out.println(numeros[i]);
}
```

> [!tip]
> Quando usar array?
> 
> - Quando você sabe o tamanho
> - Performance importa
> - Estruturas simples

#### **LIST (ArrrayList)**:

Uma lista dinâmica (cresce e diminui automaticamente)

| Tipo      | Exemplo                                           | Uso                      |
| --------- | ------------------------------------------------- | ------------------------ |
| ArrayList | ArrayList< Integer > numeros = new ArrayList<>(); | cria uma lista dinâmica. |
**Import:

`import java.util.ArrayList;`

**Criando:

`ArrayList< Integer > numeros = new ArrayList<>();`

**Adicionando:

`numeros.add(10);`
`numeros.add(20);`

**Acessando:

`System.out.println(numeros.get(0));`

**Removendo:

Tamanho: 

`numeros.size();`

**Percorrendo:**

```
for (int num : numeros) {
    System.out.println(num);
}
```

