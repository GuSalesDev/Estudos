## OPERADORES ARITIMÉTICOS

**Operadores aritméticos** na programação são símbolos usados para realizar **cálculos matemáticos** entre valores (números ou variáveis).

==Eles são a base de praticamente qualquer lógica que envolva cálculo.==

Principais Operadores:

| Operador | Nome          | Exemplo       |
| -------- | ------------- | ------------- |
| +        | Soma          | 10 + 10 = 20  |
| -        | Subtração     | 10 - 5 = 5    |
| *        | Multiplicação | 10 * 10 = 100 |
| /        | Divisão       | 10 / 2 = 5    |
| %        | Resto         | 10 % 3 = 1    |

Operadores Adicionais:

| Operador | Ação                 | Exemplo |
| -------- | -------------------- | ------- |
| ++       | Incrementa +1        | a++     |
| --       | Decrementa -1        | a--     |
| +=       | Soma e atribui       | a += 5  |
| -=       | Subtrai e atribui    | a -= 2  |
| *=       | Multiplica e atribui | a *= 3  |
| /=       | Divide e atribui     | a /= 2  |

Exemplo em Java:

```
int a = 10;
int b = 3;
int c = 5;

System.out.println(a + b); // 13
System.out.println(a - b); // 7
System.out.println(a * b); // 30
System.out.println(a / b); // 3 (ATENÇÃO!)
System.out.println(a % b); // 1

c++; // x = 6  
c--; // x = 5

System.out.println(c++); // imprime 5  
System.out.println(c); // 6

System.out.println(++c); // imprime 6 direto
```

Operadores Relacionais:

| Operador | Significado |
| -------- | ----------- |
| ==       | Igual       |
| !=       | Diferente   |
| >        | Maior       |
| <        | Menor       |
| >=       | Maior Igual |
| <=       | Menor Igual |
Exemplo em Java:

```
int idade = 20;

System.out.println(idade > 18); // true
System.out.println(idade == 20); // true
System.out.println(idade != 10); // true
```

## OPERADORES LÓGICOS

Tabela:

| Operador | Nome | Exemplo                                                                           | Ação                      |
| -------- | ---- | --------------------------------------------------------------------------------- | ------------------------- |
| &&       | E    | if (idade >= 18 && temCNH) {<br>    System.out.println("Pode dirigir");<br>}      | Os dois tem que ser True. |
| \|\|     | Ou   | if (feriado \|\| fimDeSemana) {<br>    System.out.println("Pode descansar");<br>} | Basta Apenas um ser True. |
| !        | Não  | if (!logado) {<br>    System.out.println("Faça login");<br>}<br>                  | Inverte.                  |

Exemplo na prática em Java:

**E (&&)**


```
int idade = 20;
boolean temCNH = true;

if (idade >= 18 && temCNH) {
    System.out.println("Pode dirigir");
}

```

**Ou (||)**


```
boolean feriado = false;
boolean fimDeSemana = true;

if (feriado || fimDeSemana) {
    System.out.println("Pode descansar");
}

```


**Não (!)**


```
boolean logado = false;

if (!logado) {
    System.out.println("Faça login");
}
```



Tabela verdade:


| A     | B     | A&&B  | A\|\|B | !A    | !(A&&B) | !(A\|\|B) |
| ----- | ----- | ----- | ------ | ----- | ------- | --------- |
| true  | true  | true  | true   | false | false   | false     |
| true  | false | false | true   | false | true    | false     |
| false | true  | false | true   | true  | true    | false     |
| false | false | false | false  | true  | true    | true      |


Exemplo usando tudo na prática:

String nome = "Gustavo";
int idade = 22;
double salario = 2500.50;
boolean empregado = true;

System.out.println(nome);
System.out.println(idade);
System.out.println(salario);
System.out.println(empregado);