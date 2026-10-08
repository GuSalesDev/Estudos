
# 🧱 Classe e Objetos

## Informações

**Área:** Java  
**Data:** 23/09  
**Status:** [X]

---

## 🎯 Objetivo

Entender os conceitos de **classe** e **objeto**, compreender a relação entre eles e aprender como criar e utilizar objetos em Java.

---

## 🧠 Conceito

### O que é uma Classe?

Uma **classe** é uma estrutura que define as características e os comportamentos que os objetos daquele tipo poderão possuir.

Podemos pensar em uma classe como um **molde** ou uma **planta** para criar objetos.

Uma classe pode definir:

- **Atributos:** características ou dados do objeto.
- **Métodos:** comportamentos ou ações que o objeto pode executar.
- **Construtores:** formas de inicializar um objeto.

Exemplo:

```
public class Pessoa {

    String nome;
    int idade;

    void apresentar() {
        System.out.println("Olá, meu nome é " + nome);
    }
}
```

Nesse exemplo, `Pessoa` é uma classe.

Ela define que uma pessoa possui:

```
nome
idade
```

e pode realizar o comportamento:

```
apresentar()
```

---

### O que é um Objeto?

Um **objeto** é uma instância de uma classe.

Enquanto a classe define o que um objeto terá e poderá fazer, o objeto representa uma entidade concreta criada a partir dessa definição.

Por exemplo:

```
Pessoa pessoa1 = new Pessoa();
```

Aqui:

- `Pessoa` é a classe.
- `pessoa1` é uma referência para o objeto.
- `new Pessoa()` cria uma nova instância da classe.

Podemos criar vários objetos a partir da mesma classe:

```
Pessoa pessoa1 = new Pessoa();
Pessoa pessoa2 = new Pessoa();
Pessoa pessoa3 = new Pessoa();
```

Todos são objetos do tipo `Pessoa`, mas cada um pode possuir seus próprios valores.

---

## 🔄 Classe x Objeto

Uma forma simples de visualizar:

```
             CLASSE
               │
          ┌────┴────┐
          │ Pessoa  │
          │         │
          │ nome    │
          │ idade   │
          │         │
          │ apresen |
          | tar()   |
          └────┬────┘
               │
          cria objetos
        ┌──────┼──────┐
        ↓      ↓      ↓
     pessoa1 pessoa2 pessoa3
```

A **classe** é a definição.

O **objeto** é uma instância dessa definição.

---

## 💡 Exemplo

```
public class Carro {

    String modelo;
    String cor;

    void acelerar() {
        System.out.println("O carro está acelerando.");
    }
}
```

Podemos criar objetos:

```
Carro carro1 = new Carro();
Carro carro2 = new Carro();
```

E definir valores diferentes:

```
carro1.modelo = "Civic";
carro1.cor = "Preto";

carro2.modelo = "Corolla";
carro2.cor = "Branco";
```

Embora os dois objetos sejam criados a partir da mesma classe, eles possuem seus próprios estados.

---

## 👨‍💻 Na prática

### Criando uma classe

```
public class Usuario {

    String nome;
    String email;

    void exibirDados() {
        System.out.println(nome);
        System.out.println(email);
    }
}
```

### Criando um objeto

```
Usuario usuario = new Usuario();
```

### Definindo os atributos

```
usuario.nome = "Gustavo";
usuario.email = "gustavo@email.com";
```

### Chamando um método

```
usuario.exibirDados();
```

Resultado:

```
Gustavo
gustavo@email.com
```

---

## 🧩 Estado e comportamento

Uma forma importante de entender objetos é através de **estado** e **comportamento**.

### Estado

É representado pelos dados/atributos do objeto.

```
String nome;
int idade;
```

Por exemplo:

```
nome = "Gustavo"
idade = 22
```

### Comportamento

É representado pelos métodos.

```
void apresentar() {
    System.out.println("Olá!");
}
```

Portanto:

```
Objeto
├── Estado
│   ├── nome
│   └── idade
│
└── Comportamento
    └── apresentar()
```

---

## 🔑 Pontos importantes

- Uma **classe** é uma definição ou modelo.
- Um **objeto** é uma instância de uma classe.
- Uma classe pode gerar vários objetos.
- Cada objeto possui seu próprio estado.
- Atributos representam características.
- Métodos representam comportamentos.
- `new` é utilizado para criar uma nova instância de uma classe.

---

## ⚠️ Erros e cuidados

### Confundir classe com objeto

Errado pensar:

> "Pessoa é um objeto."

No exemplo:

```
Pessoa pessoa = new Pessoa();
```

`Pessoa` é a classe e `pessoa` referencia o objeto criado.

---

### Confundir referência com objeto

```
Pessoa pessoa;
```

Nesse momento, temos uma variável de referência, mas ainda não criamos um objeto `Pessoa`.

O objeto é criado com:

```
pessoa = new Pessoa();
```

---

### Criar vários objetos

```
Pessoa pessoa1 = new Pessoa();
Pessoa pessoa2 = new Pessoa();
```

São dois objetos diferentes.

Alterar:

```
pessoa1.nome = "Gustavo";
```

não altera automaticamente:

```
pessoa2.nome
```

---

## 🔗 Relação com outros conceitos

- [[POO]]
- [[Atributos]]
- [[Métodos]]
- [[Construtores]]
- [[Encapsulamento]]
- [[Herança]]
- [[Polimorfismo]]
- [[Abstração]]

---

## 🧪 Prática

### Exercício

Crie uma classe chamada `Produto` com:

- `nome`
- `preco`
- `quantidade`

Depois crie dois objetos `Produto` com valores diferentes.

Por fim, crie um método que exiba os dados do produto.

### Minha solução

```
public class Produto {

    String nome;
    double preco;
    int quantidade;

    void exibirDados() {
        System.out.println("Produto: " + nome);
        System.out.println("Preço: " + preco);
        System.out.println("Quantidade: " + quantidade);
    }
}
```

Criação dos objetos:

```
Produto produto1 = new Produto();
Produto produto2 = new Produto();

produto1.nome = "Notebook";
produto1.preco = 3500.00;
produto1.quantidade = 2;

produto2.nome = "Mouse";
produto2.preco = 100.00;
produto2.quantidade = 5;

produto1.exibirDados();
produto2.exibirDados();
```

---

## ❓ Dúvidas

- Qual é a diferença entre objeto e referência?
    Uma referencia seria como o nome do objeto criado, por exemplo eu tenho uma classe chamada de "Carro" e eu quero criar um objeto para essa classe, primeiro eu preciso criar uma referencia para esse objeto, podemos chamar de carro1 e em seguida eu crio o objeto fazendo new Carro, sendo assim carro1 a referencia que me permite acessar o objeto.
- O que acontece na memória quando utilizamos `new`?
    Criamos um novo objeto.
- Como os atributos ficam armazenados em cada objeto?
    

---

## 📝 Resumo

Em POO, uma **classe** representa uma definição que determina quais características e comportamentos seus objetos poderão possuir. Um **objeto** é uma instância dessa classe. Em Java, objetos são normalmente criados utilizando `new`, e cada objeto possui seu próprio estado, representado por seus atributos, além dos comportamentos definidos pelos métodos.

---

## 🧠 O que eu preciso lembrar?

1. **Classe = modelo/definição.**
2. **Objeto = instância da classe.**
3. Uma classe pode gerar vários objetos.
4. **Atributos representam estado.**
5. **Métodos representam comportamento.**
6. `new` cria uma nova instância.
7. Uma variável de referência não é necessariamente o objeto em si.

---

## 🔄 Revisões

### Revisão 1

- Consigo explicar o que é uma classe.
    
- Consigo explicar o que é um objeto.
    
- Sei diferenciar classe, objeto e referência.
    
- Consigo criar uma classe em Java.
    
- Consigo criar objetos usando `new`.
    

### Revisão 2

Sem consultar:

> Explique a diferença entre classe e objeto usando um exemplo do mundo real.

### Revisão 3

Sem consultar:

> Crie uma classe `Aluno` com três atributos e dois métodos e depois crie dois objetos dessa classe.

# 🏗️ Construtores, Construtor Default e Sobrecarga de Construtores

## Informações

**Área:** Java  
**Data:** 23/09  
**Status:** [X]

---

## 🎯 Objetivo

Entender o que são construtores em Java, como eles são utilizados na criação de objetos, o funcionamento do construtor default e como realizar sobrecarga de construtores.

---

## 🧠 Conceito

### O que é um construtor?

Um **construtor** é um bloco especial da classe utilizado para inicializar objetos no momento em que eles são criados.

Ele possui algumas características específicas:

- Possui o mesmo nome da classe.
- Não possui tipo de retorno, nem mesmo `void`.
- É executado quando um objeto é criado com `new`.
- Pode receber parâmetros.
- Pode existir mais de um construtor na mesma classe através da sobrecarga.

Exemplo:

```
public class Pessoa {

    String nome;
    int idade;

    Pessoa(String nome, int idade) {
        this.nome = nome;
        this.idade = idade;
    }
}
```

Ao criar o objeto:

```
Pessoa pessoa = new Pessoa("Gustavo", 22);
```

o construtor é chamado e os valores são utilizados para inicializar o objeto.

---

## 💡 Construtor x Método

Um construtor parece um método, mas existem diferenças importantes.

### Construtor

```
Pessoa(String nome) {
    this.nome = nome;
}
```

### Método

```
void apresentar() {
    System.out.println(nome);
}
```

|Característica|Construtor|Método|
|---|---|---|
|Nome|Mesmo nome da classe|Pode ter qualquer nome válido|
|Retorno|Não possui|Possui ou `void`|
|Objetivo|Inicializar objeto|Executar comportamento|
|Chamada|Durante a criação com `new`|Quando chamado pelo programa|

---

# ⚙️ Construtor Default

O termo **default constructor** possui um significado específico em Java.

Se uma classe **não declarar nenhum construtor**, o compilador fornece automaticamente um construtor sem argumentos.

Exemplo:

```
public class Pessoa {

    String nome;
    int idade;
}
```

Como nenhum construtor foi declarado, o compilador disponibiliza implicitamente algo equivalente a:

```
Pessoa() {
}
```

Assim, podemos fazer:

```
Pessoa pessoa = new Pessoa();
```

Esse é o chamado **construtor default** fornecido pelo compilador.

---

## ⚠️ Atenção

Se você declarar **qualquer construtor**, o compilador deixa de fornecer automaticamente o construtor default.

Exemplo:

```
public class Pessoa {

    String nome;

    Pessoa(String nome) {
        this.nome = nome;
    }
}
```

Agora isto funciona:

```
Pessoa pessoa = new Pessoa("Gustavo");
```

Mas isto **não funciona**:

```
Pessoa pessoa = new Pessoa();
```

Porque não existe um construtor sem argumentos.

Se quiser permitir as duas formas, precisamos declarar explicitamente:

```
public class Pessoa {

    String nome;

    Pessoa() {
    }

    Pessoa(String nome) {
        this.nome = nome;
    }
}
```

Agora:

```
Pessoa pessoa1 = new Pessoa();
Pessoa pessoa2 = new Pessoa("Gustavo");
```

funcionam.

---

# 🔢 Sobrecarga de Construtores

### O que é?

**Sobrecarga de construtores** ocorre quando uma classe possui vários construtores com diferentes listas de parâmetros.

Exemplo:

```
public class Pessoa {

    String nome;
    int idade;

    Pessoa() {
    }

    Pessoa(String nome) {
        this.nome = nome;
    }

    Pessoa(String nome, int idade) {
        this.nome = nome;
        this.idade = idade;
    }
}
```

Podemos criar objetos de diferentes maneiras:

```
Pessoa pessoa1 = new Pessoa();

Pessoa pessoa2 = new Pessoa("Gustavo");

Pessoa pessoa3 = new Pessoa("Gustavo", 22);
```

O Java identifica qual construtor utilizar de acordo com os argumentos fornecidos.

---

## 🧩 Como o Java diferencia os construtores?

A diferenciação ocorre pela **lista de parâmetros**.

```
Pessoa()
```

```
Pessoa(String nome)
```

```
Pessoa(String nome, int idade)
```

São construtores diferentes.

Apenas mudar o nome dos parâmetros não seria suficiente:

```
Pessoa(String nome)
Pessoa(String outroNome)
```

Isso seria considerado a mesma assinatura de construtor e não seria permitido.

---

## 👨‍💻 Na prática

Uma classe `Produto` pode utilizar sobrecarga para oferecer diferentes formas de criação:

```
public class Produto {

    String nome;
    double preco;
    int quantidade;

    Produto() {
    }

    Produto(String nome, double preco) {
        this.nome = nome;
        this.preco = preco;
    }

    Produto(String nome, double preco, int quantidade) {
        this.nome = nome;
        this.preco = preco;
        this.quantidade = quantidade;
    }
}
```

Podemos então utilizar:

```
Produto produto1 = new Produto();

Produto produto2 = new Produto("Mouse", 100.0);

Produto produto3 = new Produto("Teclado", 250.0, 10);
```

---

# 🔗 `this` nos construtores

A palavra-chave `this` representa a instância atual do objeto.

É muito utilizada quando o nome do parâmetro é igual ao nome do atributo:

```
public class Pessoa {

    String nome;
    int idade;

    Pessoa(String nome, int idade) {
        this.nome = nome;
        this.idade = idade;
    }
}
```

Nesse caso:

```
this.nome
```

representa o atributo do objeto.

Enquanto:

```
nome
```

representa o parâmetro recebido pelo construtor.

---

# 🔄 Chamando outro construtor com `this()`

Um construtor pode chamar outro construtor da mesma classe utilizando:

```
this()
```

Exemplo:

```
public class Pessoa {

    String nome;
    int idade;

    Pessoa() {
        this("Desconhecido", 0);
    }

    Pessoa(String nome, int idade) {
        this.nome = nome;
        this.idade = idade;
    }
}
```

Agora:

```
Pessoa pessoa = new Pessoa();
```

utiliza o construtor sem argumentos, que chama:

```
this("Desconhecido", 0);
```

Isso evita duplicação de código.

> `this()` deve ser a primeira instrução dentro do construtor.

---

## 🔑 Pontos importantes

- Construtores inicializam objetos.
- Possuem o mesmo nome da classe.
- Não possuem tipo de retorno.
- São chamados durante a criação do objeto.
- Se nenhum construtor for declarado, o compilador fornece um construtor default sem argumentos.
- Se você declarar qualquer construtor, o construtor default não é criado automaticamente.
- Podemos criar vários construtores através de sobrecarga.
- A sobrecarga depende da quantidade, ordem e tipos dos parâmetros.
- `this()` pode ser utilizado para chamar outro construtor da mesma classe.
- `this` representa a instância atual.

---

## ⚠️ Erros e cuidados

### 1. Colocar `void` no construtor

Errado:

```
void Pessoa() {
}
```

Isso não é um construtor. É um método chamado `Pessoa`.

Correto:

```
Pessoa() {
}
```

---

### 2. Achar que o construtor default sempre existe

Não existe construtor default automático se você já declarou outro construtor.

```
Pessoa(String nome) {
    this.nome = nome;
}
```

Nesse caso:

```
new Pessoa();
```

gera erro de compilação.

---

### 3. Confundir `this` com `this()`

São coisas diferentes:

```
this.nome
```

Acessa um atributo da instância atual.

Enquanto:

```
this()
```

chama outro construtor da mesma classe.

---

### 4. Confundir sobrecarga com sobrescrita

**Sobrecarga (overloading):**

```
Pessoa()
Pessoa(String nome)
Pessoa(String nome, int idade)
```

Vários construtores na mesma classe.

**Sobrescrita (overriding):**

Está relacionada à herança e ocorre quando uma subclasse redefine um método herdado.

---

## 🔗 Relação com outros conceitos

- [[Classe e Objetos]]
- [[Atributos]]
- [[Métodos]]
- [[this]]
- [[Sobrecarga]]
- [[Herança]]
- [[Encapsulamento]]
- [[Polimorfismo]]

---

## 🧪 Prática

### Exercício

Crie uma classe `Aluno` com:

- `nome`
- `idade`
- `curso`

Crie três construtores:

1. Sem argumentos.
2. Recebendo apenas `nome`.
3. Recebendo `nome`, `idade` e `curso`.

Depois crie três objetos utilizando os diferentes construtores.

### Minha solução

```
public class Aluno {

    String nome;
    int idade;
    String curso;

    Aluno() {
        this("Não informado", 0, "Não informado");
    }

    Aluno(String nome) {
        this(nome, 0, "Não informado");
    }

    Aluno(String nome, int idade, String curso) {
        this.nome = nome;
        this.idade = idade;
        this.curso = curso;
    }
}
```

Criação dos objetos:

```
Aluno aluno1 = new Aluno();

Aluno aluno2 = new Aluno("Gustavo");

Aluno aluno3 = new Aluno("Gustavo", 22, "ADS");
```

---

## ❓ Dúvidas

- Qual a diferença exata entre construtor default e construtor sem argumentos?
    
- Como `this()` evita repetição de código?
    
- O que acontece na memória durante a criação de um objeto?
    
- Como construtores se comportam em uma hierarquia de herança?
    

---

## 📝 Resumo

Construtores são utilizados para inicializar objetos durante sua criação. Eles possuem o mesmo nome da classe e não possuem tipo de retorno. Quando nenhuma declaração de construtor é feita, o compilador fornece automaticamente um construtor default sem argumentos. Porém, quando um construtor é declarado, esse construtor automático deixa de existir. Uma classe pode possuir vários construtores através da sobrecarga, permitindo diferentes formas de inicializar seus objetos. A palavra-chave `this()` pode ser utilizada para chamar outro construtor da mesma classe e evitar repetição de código.

---

## 🧠 O que eu preciso lembrar?

1. **Construtor inicializa o objeto.**
2. Construtor possui o mesmo nome da classe.
3. Construtor não possui retorno.
4. Sem construtor declarado → Java fornece um **default constructor**.
5. Declarou qualquer construtor → o default automático deixa de existir.
6. Vários construtores = **sobrecarga de construtores**.
7. `this` acessa a instância atual.
8. `this()` chama outro construtor da mesma classe.
9. `this()` deve ser a primeira instrução do construtor.

---

## 🔄 Revisões

### Revisão 1

- Sei explicar o que é um construtor.
    
- Sei diferenciar construtor de método.
    
- Sei explicar o construtor default.
    
- Sei explicar o que acontece quando declaro um construtor.
    
- Sei criar construtores sobrecarregados.
    
- Sei utilizar `this`.
    
- Sei utilizar `this()`.
    

### Revisão 2

**Sem consultar:**

> O que acontece com o construtor default quando eu crio um construtor `Pessoa(String nome)`?

### Revisão 3

**Desafio:**

Crie uma classe `ContaBancaria` com três formas diferentes de criação:

```
ContaBancaria()
ContaBancaria(String titular)
ContaBancaria(String titular, double saldo)
```

Utilize `this()` para evitar duplicação de código.

---

