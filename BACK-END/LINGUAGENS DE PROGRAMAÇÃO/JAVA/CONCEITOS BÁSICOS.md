# ☕ Frameworks Java

> [!info] Informações
> **Área:** Java
> **Data:** 23/09
> **Status:** [X]

---

## 🎯 Objetivo

Entender o que são frameworks em Java, por que são utilizados e como eles ajudam no desenvolvimento de aplicações.

---

## 🧠 Conceito

### O que é?

Um **framework** é uma estrutura de desenvolvimento que fornece ferramentas, padrões e recursos prontos para facilitar a criação de aplicações.

Em vez de desenvolver toda a estrutura da aplicação do zero, o framework fornece uma base sobre a qual o desenvolvedor constrói seu sistema.

Um framework normalmente define uma maneira específica de organizar e desenvolver a aplicação.

### Como funciona?

O framework fornece uma estrutura pré-definida e o desenvolvedor utiliza essa estrutura para implementar as regras específicas da aplicação.

Uma característica importante é a **inversão de controle**: em muitos frameworks, é o próprio framework que controla o fluxo da aplicação e chama o código do desenvolvedor quando necessário.

### Por que é importante?

Frameworks ajudam a:

- Reduzir código repetitivo
- Padronizar projetos
- Aumentar a produtividade
- Facilitar a manutenção
- Fornecer funcionalidades prontas
- Facilitar a integração entre diferentes tecnologias

---

## 💡 Exemplos

Alguns frameworks e ecossistemas bastante utilizados com Java:

- [[Spring Boot]]
- [[Spring Framework]]
- [[Jakarta EE]]
- [[Hibernate]]

---

## 🔑 Pontos importantes

- Framework fornece uma **estrutura** para desenvolver aplicações.
- Ele pode definir padrões de arquitetura e desenvolvimento.
- O desenvolvedor trabalha dentro da estrutura fornecida.
- Framework não é a mesma coisa que biblioteca.
- Muitos frameworks utilizam várias bibliotecas internamente.

---

## 👨‍💻 Na prática

### Framework x código próprio

Sem um framework, o desenvolvedor precisa construir grande parte da infraestrutura da aplicação.

Com um framework como o Spring Boot, diversas configurações e componentes já são fornecidos.

Por exemplo:

```java
@RestController
public class UsuarioController {

    @GetMapping("/usuarios")
    public String usuarios() {
        return "Lista de usuários";
    }
}
```

O Spring interpreta as anotações e fornece a infraestrutura necessária para transformar esse método em um endpoint HTTP.

### Quando usar?

Frameworks são especialmente úteis em projetos maiores, nos quais organização, padronização e produtividade são importantes.

### Quando NÃO usar?

Para programas extremamente simples, utilizar um framework pode adicionar complexidade desnecessária.


## ⚠️ Erros e cuidados

- Não confundir framework com biblioteca.
- Não utilizar um framework apenas porque ele é popular.
- Entender os conceitos fundamentais antes de depender completamente do framework.

---

## 🔗 Relação com outros conceitos

- [[Java]]
- [[Bibliotecas]]
- [[API]]
- [[Spring Framework]]
- [[Spring Boot]]
- [[Arquitetura de Software]]

---

## 🧠 O que eu preciso lembrar?

1. Framework fornece uma estrutura para desenvolver software.
2. Ele reduz a necessidade de criar tudo do zero.
3. Frameworks podem controlar o fluxo da aplicação.
4. Framework e biblioteca não são a mesma coisa.
5. Spring é um dos principais ecossistemas de Java.

---

## 📝 Resumo

Frameworks são estruturas que fornecem recursos, padrões e infraestrutura para facilitar o desenvolvimento de aplicações. Eles ajudam a reduzir código repetitivo e padronizar a construção dos sistemas.

## 🔄 Revisão

### Revisão 1

- [x]  Consigo explicar o que é um framework
- [x]  Sei por que frameworks são utilizados
- [x]  Sei diferenciar framework de biblioteca
- [x]  Consigo citar exemplos de frameworks Java


---

# 2. API

# 🔌 API

> [!info] Informações
> **Área:** Java  
**Data:** 23/09  
**Status:** [X]

---

## 🎯 Objetivo

Entender o conceito de API e como diferentes sistemas utilizam APIs para se comunicar.

---

## 🧠 Conceito

### O que é?

**API** significa **Application Programming Interface**, ou Interface de Programação de Aplicações.

Uma API é uma interface que define como um software pode interagir com outro software ou com determinada funcionalidade.

Ela estabelece regras sobre como solicitar informações ou executar determinadas operações.

### Como funciona?

Imagine que uma aplicação precisa buscar informações de usuários em outro sistema.

Em vez de acessar diretamente o banco de dados do outro sistema, ela pode utilizar uma API.

Exemplo:

```text
Aplicação
    ↓
    requisição
    ↓
API
    ↓
Sistema
    ↓
resposta
    ↓
Aplicação
```

## 💡 Exemplo

Uma API REST poderia possuir:

```
GET /usuarios
```


A API poderia responder:

```
[
    {
        "id": 1,
        "nome": "Gustavo"
    }
]
```

## 🔑 Pontos importantes

- API é uma **interface de comunicação**.
- Ela define como determinado recurso pode ser utilizado.
- APIs podem ser utilizadas entre aplicações diferentes.
- Uma API não precisa necessariamente ser uma API web.
- REST é um estilo arquitetural muito utilizado para APIs web.

## 👨‍💻 Na prática

### Exemplo com Java e Spring Boot

```
@RestController
@RequestMapping("/usuarios")
public class UsuarioController {

    @GetMapping
    public String listarUsuarios() {
        return "Lista de usuários";
    }
}
```

Nesse caso:

```
GET /usuarios
```

é um endpoint da API.

### Quando usar?

Quando diferentes partes de um sistema precisam se comunicar ou quando queremos disponibilizar funcionalidades para outros sistemas.

---

## ⚠️ Erros e cuidados

API não significa necessariamente "API REST".

Existem diferentes tipos de APIs e diferentes formas de comunicação.

---

## 🔗 Relação com outros conceitos

- [[Frameworks Java]]
- [[Spring Boot]]
- [[REST]]
- [[HTTP]]
- [[JSON]]
- [[Bibliotecas]]

---

## 🧠 O que eu preciso lembrar?

1. API significa Application Programming Interface.
2. API define uma forma de interação entre softwares.
3. APIs podem receber requisições e retornar respostas.
4. REST é uma forma comum de construir APIs web.
5. Um endpoint é um ponto de acesso disponibilizado por uma API.

---

## 📝 Resumo

Uma API é uma interface que permite que softwares interajam seguindo regras previamente definidas. Em aplicações web, APIs REST são muito utilizadas para permitir a comunicação entre frontend, backend e outros sistemas.

---

## 🔄 Revisão

- [x]  Sei o que significa API
- [x]  Consigo explicar API com minhas próprias palavras
- [x]  Sei o que é um endpoint
- [x]  Sei diferenciar API de REST

---

# 3. Bibliotecas

# 📚 Bibliotecas

> [!info] Informações
> **Área:** Java  
**Data:** 23/09  
**Status:** [X]

---

## 🎯 Objetivo

Entender o que são bibliotecas, por que são utilizadas e qual a diferença entre biblioteca e framework.

---

## 🧠 Conceito

### O que é?

Uma **biblioteca** é um conjunto de códigos prontos que fornece funcionalidades que podem ser utilizadas por uma aplicação.

Em vez de desenvolver determinada funcionalidade do zero, o programador pode utilizar uma biblioteca existente.

### Como funciona?

O desenvolvedor chama as funcionalidades da biblioteca quando precisa delas.

Isso é uma diferença importante em relação aos frameworks.

**Biblioteca:**

Seu código → chama a biblioteca

**Framework:**

Framework → chama o seu código


---

## 💡 Exemplo

O Java possui diversas bibliotecas na própria plataforma.

Por exemplo:

```
import java.util.ArrayList;
import java.util.List;
```

Podemos utilizar:

```
List<String> nomes = new ArrayList<>();

nomes.add("Gustavo");
nomes.add("Maria");
```

Também existem bibliotecas externas, como:

- Jackson
- Lombok
- JUnit
- Mockito
- Apache Commons

---

## 🔑 Pontos importantes

- Biblioteca fornece código reutilizável.
- O programador decide quando utilizar a biblioteca.
- Bibliotecas evitam a necessidade de implementar tudo do zero.
- Uma aplicação pode utilizar várias bibliotecas.
- Frameworks podem utilizar bibliotecas internamente.

---

## 👨‍💻 Na prática

### Exemplo

Sem uma biblioteca específica, determinada funcionalidade poderia precisar ser implementada manualmente.

Com uma biblioteca:

```
ObjectMapper mapper = new ObjectMapper();

String json = mapper.writeValueAsString(usuario);
```

A biblioteca Jackson fornece recursos para trabalhar com JSON.

### Quando usar?

Quando uma biblioteca já fornece uma solução adequada para uma necessidade do projeto.

### Quando NÃO usar?

Evite adicionar bibliotecas sem necessidade. Cada dependência adicionada aumenta a quantidade de código externo que o projeto precisa manter.

---

## 🔄 Biblioteca x Framework

|Característica|Biblioteca|Framework|
|---|---|---|
|Quem controla o fluxo?|Seu código|Framework|
|Objetivo|Fornecer funcionalidades|Fornecer estrutura|
|Uso|Você chama quando precisa|Framework integra seu código|
|Exemplo|Jackson|Spring Boot|

---

## 🔗 Relação com outros conceitos

- [[Frameworks Java]]
- [[Maven]]
- [[Dependências]]
- [[API]]
- [[POO]]

---

## 🧠 O que eu preciso lembrar?

1. Biblioteca é código reutilizável.
2. Seu código normalmente chama a biblioteca.
3. Framework fornece uma estrutura maior.
4. Frameworks podem utilizar bibliotecas.
5. Dependências externas geralmente são adicionadas através de ferramentas como Maven.

---

## 📝 Resumo

Bibliotecas são conjuntos de códigos reutilizáveis que fornecem funcionalidades prontas para uma aplicação. Elas permitem que o desenvolvedor aproveite soluções existentes em vez de implementar tudo do zero.

---

## 🔄 Revisão

- [x]  Sei explicar o que é uma biblioteca
- [x]  Sei diferenciar biblioteca de framework
- [x]  Sei citar exemplos de bibliotecas Java
- [x]  Entendo o papel das dependências



---

# 4. Módulos em Java


# 📦 Módulos em Java

> [!info] Informações
> **Área:** Java  
**Data:** 23/09  
**Status:** [X]

---

## 🎯 Objetivo

Entender o conceito de módulos em Java e como eles ajudam a organizar e controlar aplicações.

---

## 🧠 Conceito

### O que é?

Um **módulo** é uma forma de organizar um conjunto de pacotes relacionados e controlar quais partes desse código ficam disponíveis para outros módulos.

O sistema de módulos foi introduzido no **Java 9** através do **Java Platform Module System (JPMS)**.

---

## 💡 Exemplo

Um módulo possui um arquivo:

module-info.java


Exemplo:

```
module minha.aplicacao {
    exports com.exemplo.usuario;
}
```

Nesse caso, o módulo está declarando que o pacote:

```
com.exemplo.usuario
```

pode ser utilizado por outros módulos.

---

## 🔑 Principais palavras-chave

### `module`

Define um módulo.

```
module minha.aplicacao {
}
```

### `requires`

Declara uma dependência de outro módulo.

```
module minha.aplicacao {
    requires outro.modulo;
}
```

### `exports`

Define quais pacotes podem ser acessados por outros módulos.

```
module minha.aplicacao {
    exports com.exemplo.usuario;
}
```

---

## 👨‍💻 Na prática

Uma estrutura poderia ser:

```
meu-projeto/
├── src/
│   └── com.exemplo/
│       ├── module-info.java
│       └── com/
│           └── exemplo/
│               └── Usuario.java
```

O arquivo:

```
module-info.java
```

define as regras do módulo.

---

## ⚠️ Erros e cuidados

- Módulo não é simplesmente sinônimo de pacote.
- Um módulo pode conter vários pacotes.
- Nem todo projeto Java precisa obrigatoriamente utilizar módulos explícitos.
- O sistema de módulos é diferente do sistema tradicional de pacotes.

---

## 🔗 Relação com outros conceitos

- [[Java]]
- [[Pacotes Java]]
- [[Bibliotecas]]
- [[Dependências]]
- [[Maven]]

---

## 🧠 O que eu preciso lembrar?

1. Módulos foram introduzidos no Java 9.
2. O arquivo principal de configuração é `module-info.java`.
3. `requires` declara dependências.
4. `exports` disponibiliza pacotes para outros módulos.
5. Um módulo pode conter vários pacotes.

---

## 📝 Resumo

O sistema de módulos do Java permite organizar aplicações em módulos independentes e controlar quais partes do código são expostas ou dependem de outros módulos.

---

## 🔄 Revisão

- [x]  Sei o que é um módulo
- [x]  Sei quando o sistema de módulos foi introduzido
- [x]  Sei para que serve `module-info.java`
- [x]  Sei explicar `requires`
- [x]  Sei explicar `exports`



---

# 5. Case Sensitivity

# 🔤 Case Sensitivity

> [!info] Informações
>**Área:** Java  
**Data:** 23/09  
**Status:** [X]

---

## 🎯 Objetivo

Entender o conceito de case sensitivity e como ele afeta a escrita de código Java.

---

## 🧠 Conceito

### O que é?

**Case sensitivity** significa que letras maiúsculas e minúsculas são consideradas diferentes.

Java é uma linguagem **case-sensitive**.

Isso significa que:

```text
nome
Nome
NOME
````

podem representar identificadores diferentes.

---

## 💡 Exemplo

```
String nome = "Gustavo";
String Nome = "João";
```

Nesse caso, `nome` e `Nome` são duas variáveis diferentes.

Outro exemplo:

```
System.out.println();
```

O correto é:

```
System
```

e não:

```
system
```

---

## 🔑 Pontos importantes

Java diferencia:

- `A` de `a`
- `Nome` de `nome`
- `String` de `string`
- `System` de `system`

Além disso, Java possui convenções de nomenclatura que ajudam a manter o código organizado.

---

## 👨‍💻 Na prática

### Classes

Normalmente utilizamos **PascalCase**:

```
public class UsuarioService {
}
```

### Variáveis e métodos

Normalmente utilizamos **camelCase**:

```
String nomeUsuario;

public void cadastrarUsuario() {
}
```

### Constantes

Normalmente utilizamos **UPPER_SNAKE_CASE**:

```
final int MAX_USUARIOS = 100;
```

---

## ⚠️ Erros e cuidados

Um erro comum:

```
String nome = "Gustavo";

System.out.println(Nome);
```

Isso gera erro porque `nome` e `Nome` são identificadores diferentes.

---

## 🔗 Relação com outros conceitos

- [[Java]]
- [[Variáveis]]
- [[Métodos]]
- [[Classes]]
- [[Convenções de nomenclatura]]

---

## 🧠 O que eu preciso lembrar?

1. Java é case-sensitive.
2. Maiúsculas e minúsculas fazem diferença.
3. `nome` e `Nome` são identificadores diferentes.
4. Convenções de nomenclatura ajudam a evitar confusão.
5. Classes normalmente utilizam PascalCase e variáveis/métodos camelCase.

---

## 📝 Resumo

Case sensitivity significa que letras maiúsculas e minúsculas são tratadas como diferentes. Como Java é case-sensitive, é necessário respeitar exatamente a capitalização dos identificadores e das palavras utilizadas na linguagem.

---

## 🔄 Revisão

- [x]  Sei o que significa case-sensitive
- [x]  Sei que Java é case-sensitive
- [x]  Sei diferenciar PascalCase de camelCase
- [x]  Consigo identificar erros de capitalização

---
# ☕ JVM (Java Virtual Machine)

> [!info] Informações
> **Área:** Java  
**Data:** 23/09  
**Status:** [X]

---

## 🎯 Objetivo

Entender o que é a JVM, como ela executa programas Java e qual é sua relação com o código-fonte, bytecode e o sistema operacional.

---

## 🧠 Conceito

### O que é?

**JVM** significa **Java Virtual Machine**, ou **Máquina Virtual Java**.

Ela é responsável por executar o **bytecode** produzido pelo compilador Java.

A JVM funciona como uma camada entre o programa Java e o sistema operacional.

```text
Código Java
    ↓
Compilador Java
    ↓
Bytecode (.class)
    ↓
JVM
    ↓
Sistema Operacional
    ↓
Hardware
````

---

## 💡 Por que a JVM é importante?

Uma das principais características do Java é:

> **"Write Once, Run Anywhere"**

A ideia é que o mesmo bytecode possa ser executado em diferentes sistemas operacionais desde que exista uma JVM compatível.

Por exemplo:

```
             Bytecode
                │
        ┌───────┼───────┐
        ↓       ↓       ↓
      JVM     JVM     JVM
    Windows   Linux   macOS
```

O código Java não precisa ser recompilado especificamente para cada sistema operacional na maioria dos casos.

---

## ⚙️ Como funciona?

### 1. Código-fonte

O programador escreve um arquivo `.java`.

```
public class Main {

    public static void main(String[] args) {
        System.out.println("Olá, mundo!");
    }
}
```

---

### 2. Compilação

O compilador Java, normalmente o `javac`, transforma o código-fonte em **bytecode**.

```
Main.java
   ↓
javac
   ↓
Main.class
```

O arquivo `.class` contém o bytecode.

---

### 3. Execução

A JVM carrega e executa o bytecode.

```
Main.class
    ↓
   JVM
    ↓
Programa executado
```

---

## 🧩 Principais componentes da JVM

A JVM possui diversos componentes responsáveis pela execução do programa.

### Class Loader

Responsável por carregar classes e outros dados necessários para a execução na JVM.

```
.class
  ↓
Class Loader
  ↓
JVM
```

---

### Runtime Data Areas

São áreas de memória utilizadas pela JVM durante a execução.

Entre elas estão:

- Heap
- Stack
- Method Area
- PC Register
- Native Method Stack

---

### Execution Engine

É responsável pela execução do bytecode.

Ela pode utilizar mecanismos como:

- Interpretador
- JIT Compiler

---

### Garbage Collector

A JVM possui gerenciamento automático de memória.

O **Garbage Collector (GC)** identifica objetos que não são mais utilizados e pode liberar a memória associada a eles.

Exemplo:

```
Usuario usuario = new Usuario();

usuario = null;
```

Se o objeto anteriormente criado não possuir mais referências acessíveis, ele poderá posteriormente ser identificado pelo Garbage Collector como elegível para coleta.

> O Garbage Collector não significa que a memória é liberada imediatamente após `usuario = null`.

---

## 🚀 JIT Compiler

**JIT** significa **Just-In-Time Compiler**.

Durante a execução, a JVM pode identificar partes do código que são executadas frequentemente e compilá-las para código de máquina, buscando melhorar o desempenho.

De forma simplificada:

```
Bytecode
   ↓
JVM
   ↓
JIT
   ↓
Código de máquina
   ↓
CPU
```

---

## 👨‍💻 Na prática

Podemos observar a diferença entre Java e a execução diretamente pelo sistema operacional.

Quando fazemos:

```
javac Main.java
```

obtemos:

```
Main.class
```

Depois:

```
java Main
```

a JVM é iniciada para executar a aplicação.

---

## 🔄 Java → Bytecode → JVM

O fluxo completo pode ser representado assim:

```
┌─────────────────┐
│ Código-fonte     │
│ Main.java        │
└────────┬────────┘
         │
         ↓
┌─────────────────┐
│ Compilador       │
│ javac            │
└────────┬────────┘
         │
         ↓
┌─────────────────┐
│ Bytecode         │
│ Main.class       │
└────────┬────────┘
         │
         ↓
┌─────────────────┐
│ JVM              │
│                  │
│ Class Loader     │
│ Memory           │
│ Execution Engine │
│ Garbage Collector│
└────────┬────────┘
         │
         ↓
┌─────────────────┐
│ Sistema Operacional│
└─────────────────┘
```

---

## ⚠️ Erros e cuidados

### JVM não é Java

Java é a linguagem e também o ecossistema/plataforma.

A JVM é o ambiente responsável por executar o bytecode Java.

---

### JVM não é JDK

São componentes diferentes.

```
JDK
├── Ferramentas de desenvolvimento
├── Compilador
└── JVM
```

---

### JVM não é JRE

Historicamente, a JRE era o ambiente necessário para executar aplicações Java e incluía a JVM e bibliotecas da plataforma.

Nas distribuições modernas do Java, especialmente desde a modularização iniciada no Java 9, a distinção prática entre JDK e uma JRE separada ficou diferente do modelo tradicional.

---

## 🔗 Relação com outros conceitos

- [[Java]]
- [[JDK]]
- [[JRE]]
- [[Bytecode]]
- [[Compilador]]
- [[Garbage Collector]]
- [[JIT Compiler]]
- [[Memória Heap]]
- [[Stack]]
- [[Módulos em Java]]

---

## 🧠 O que eu preciso lembrar?

1. JVM significa **Java Virtual Machine**.
2. A JVM executa o **bytecode** Java.
3. O código `.java` é compilado para `.class`.
4. A JVM permite executar o mesmo bytecode em diferentes sistemas com JVMs compatíveis.
5. A JVM possui gerenciamento automático de memória através do Garbage Collector.
6. O JIT pode compilar partes do bytecode para melhorar o desempenho.
7. **JVM ≠ JDK ≠ JRE**.

---

## 📝 Resumo

A JVM é a máquina virtual responsável por executar o bytecode Java. O código-fonte `.java` é compilado pelo `javac` para bytecode `.class`, que posteriormente é carregado e executado pela JVM. Ela fornece uma camada de abstração sobre o sistema operacional e possui recursos como gerenciamento de memória, Garbage Collector e compilação JIT.

---

## 🧪 Prática

### Exercício 1

Explique com suas próprias palavras o caminho percorrido por um programa Java desde o arquivo `.java` até sua execução.

### Exercício 2

Qual é a diferença entre:

```
JVM

JVM é o que possibilita o código java rodar em qualquer ambiente.

JRE

JRE era o ambiente necessário para executar aplicações Java

JDK

JDK é o kit de desenvolvimeento para java oferecido pela Oracle.
```

### Exercício 3

Execute:

```
javac Main.java
```

e observe o arquivo:

```
Main.class
```

Depois execute:

```
java Main
```

Observe que o comando `java` executa a classe através da JVM.

---

## 🔄 Revisão

### Revisão 1

- [x]  Sei explicar o que é a JVM
- [x]  Sei explicar o que é bytecode
- [x]  Sei explicar o papel do `javac`
- [x]  Sei explicar o papel do Garbage Collector
- [x]  Sei explicar o que é JIT
- [x]  Sei diferenciar JVM, JRE e JDK

### Revisão 2

**Sem consultar a nota:**

> Explique o fluxo `Main.java → Main.class → JVM → Sistema Operacional`.

### Revisão 3

- [x]  Consigo explicar a JVM para outra pessoa
- [x]  Consigo explicar por que Java é multiplataforma
- [x]  Consigo diferenciar compilação de execução

---
# 🔢 Bytecode

> [!info] Informações
> **Área:** Java  
**Data:** 23/09  
**Status:** [X]

---
## 🎯 Objetivo

Entender o que é bytecode, como ele é gerado e qual é sua relação com o compilador Java e a JVM.

---

## 🧠 Conceito

### O que é?

**Bytecode** é o código intermediário gerado pelo compilador Java a partir do código-fonte.

Ele não é diretamente o código de máquina do computador. É um formato que a [[JVM]] consegue interpretar e executar.

Normalmente, o bytecode fica armazenado em arquivos `.class`.

---

## ⚙️ Como funciona?

O processo pode ser representado assim:

```text
Código-fonte
Main.java
    ↓
Compilador javac
    ↓
Bytecode
Main.class
    ↓
JVM
    ↓
Execução
````

O objetivo é separar o código Java do código específico de cada sistema operacional.

---

## 💡 Exemplo

Código Java:

```
public class Main {

    public static void main(String[] args) {
        System.out.println("Olá!");
    }
}
```

Ao executar:

```
javac Main.java
```

o compilador gera:

```
Main.class
```

Esse arquivo contém o bytecode.

---

## 👨‍💻 Na prática

Podemos visualizar o bytecode de uma classe utilizando:

```
javap -c Main
```

O resultado não será o código Java original, mas instruções da JVM.

---

## 🔑 Pontos importantes

- Bytecode é gerado pelo compilador Java.
- Normalmente fica em arquivos `.class`.
- É executado pela JVM.
- Não é o mesmo que código de máquina.
- É uma das bases da portabilidade do Java.

---

## ⚠️ Erros e cuidados

Não confunda:

```
.java  → código-fonte
.class → bytecode
```

O arquivo `.class` não contém simplesmente o código Java escrito originalmente.

---

## 🔗 Relação com outros conceitos

- [[Java]]
- [[JVM]]
- [[JDK]]
- [[Compilador]]
- [[Código de Máquina]]

---

## 🧠 O que eu preciso lembrar?

1. Bytecode é um código intermediário.
2. É gerado pelo compilador Java.
3. Normalmente fica em arquivos `.class`.
4. A JVM executa o bytecode.
5. Bytecode ajuda o Java a ser multiplataforma.

---

## 📝 Resumo

Bytecode é o código intermediário produzido pelo compilador Java. Ele é armazenado normalmente em arquivos `.class` e posteriormente carregado e executado pela JVM.

---

## 🔄 Revisão

- [x]  Sei explicar o que é bytecode
- [x]  Sei diferenciar `.java` de `.class`
- [x]  Sei explicar o papel da JVM
- [x]  Sei explicar por que o bytecode ajuda na portabilidade

---

# 🗑️ Garbage Collector

> [!info] Informações
> **Área:** Java  
**Data:** 23/09  
**Status:** [X]

---

## 🎯 Objetivo

Entender o que é o Garbage Collector, por que ele existe e como ele gerencia objetos que não são mais utilizados.

---

## 🧠 Conceito

### O que é?

O **Garbage Collector (GC)** é o mecanismo da [[JVM]] responsável por gerenciar automaticamente parte da memória utilizada pelos objetos.

Ele identifica objetos que não podem mais ser alcançados pela aplicação e os torna elegíveis para coleta.

Isso reduz a necessidade de o programador liberar manualmente a memória dos objetos.

---

## ⚙️ Como funciona?

Imagine:

```java
Usuario usuario = new Usuario();
````

Um objeto `Usuario` é criado na memória.

Enquanto existir uma referência acessível para esse objeto, ele pode continuar sendo utilizado.

Agora:

```
usuario = null;
```

Se não existir nenhuma outra referência alcançável para aquele objeto, ele poderá se tornar **elegível para coleta**.

```
Objeto criado
     ↓
Possui referência
     ↓
Pode ser utilizado
     ↓
Perde todas as referências alcançáveis
     ↓
Elegível para Garbage Collection
     ↓
GC pode recuperar a memória
```

---

## 💡 Exemplo

```
public class Main {

    public static void main(String[] args) {

        Usuario usuario = new Usuario();

        usuario = null;
    }
}
```

Depois de `usuario = null`, o objeto anteriormente referenciado pode se tornar elegível para coleta, caso não exista outra referência alcançável para ele.

---

## ⚠️ Importante

O Garbage Collector **não necessariamente executa imediatamente** quando um objeto fica sem referências.

Também não devemos assumir que:

```
System.gc();
```

obrigará a JVM a executar o Garbage Collector naquele momento.

Essa chamada é apenas uma solicitação/sugestão para a JVM.

---

## 👨‍💻 Na prática

O desenvolvedor Java normalmente não precisa fazer:

```
liberar memória do objeto
```

manualmente.

A JVM possui mecanismos automáticos de gerenciamento de memória.

Isso é diferente de linguagens nas quais o programador pode precisar liberar explicitamente determinados recursos de memória.

---

## 🔑 Pontos importantes

- GC significa Garbage Collector.
- Faz parte da JVM.
- Gerencia automaticamente a memória de objetos.
- Objetos sem referências alcançáveis podem se tornar elegíveis para coleta.
- A coleta não ocorre necessariamente imediatamente.
- O programador não controla exatamente quando cada objeto será coletado.

---

## ⚠️ Erros e cuidados

### "O objeto foi coletado assim que ficou sem referência."

Não necessariamente.

O correto é dizer:

> O objeto ficou elegível para coleta.

### "Java não possui problemas de memória."

Possui.

É possível criar problemas como:

- `OutOfMemoryError`
- excesso de objetos
- referências mantidas desnecessariamente
- uso excessivo de memória

O Garbage Collector não elimina automaticamente todos os problemas de gerenciamento de memória.

---

## 🔗 Relação com outros conceitos

- [[JVM]]
- [[Heap]]
- [[Stack]]
- [[Objetos]]
- [[Referências]]
- [[Memória]]

---

## 🧠 O que eu preciso lembrar?

1. O Garbage Collector faz parte da JVM.
2. Ele gerencia automaticamente a memória de objetos.
3. Objetos sem referências alcançáveis podem ser coletados.
4. Ficar sem referência não significa coleta imediata.
5. `System.gc()` não garante uma coleta imediata.

---

## 📝 Resumo

O Garbage Collector é o mecanismo de gerenciamento automático de memória da JVM. Ele identifica objetos que não podem mais ser alcançados pela aplicação e pode recuperar a memória associada a eles.

---

## 🔄 Revisão

- [x]  Sei explicar o que é Garbage Collector
- [x]  Sei o que significa um objeto estar elegível para coleta
- [x]  Sei por que `System.gc()` não garante uma coleta imediata
- [x]  Sei explicar a relação entre GC e JVM

---

# 3. JRE

# ☕ JRE (Java Runtime Environment)

> [!info] Informações
**Área:** Java  
**Data:** 23/09  
**Status:** [X]

---

## 🎯 Objetivo

Entender o que é a JRE, para que ela servia no ecossistema Java e qual é sua relação com a JVM e o JDK.

---

## 🧠 Conceito

### O que é?

**JRE** significa **Java Runtime Environment**.

Tradicionalmente, a JRE representava o ambiente necessário para **executar aplicações Java**, incluindo a [[JVM]] e as bibliotecas necessárias para execução.

De forma simplificada:

```text
JRE
├── JVM
└── Bibliotecas necessárias para execução
````

---

## ⚙️ Como funciona?

A ideia tradicional era:

```
Aplicação Java
      ↓
     JRE
      ↓
     JVM
      ↓
Sistema Operacional
```

A JRE fornecia o ambiente de execução, enquanto a JVM era responsável pela execução do bytecode.

---

## 🔑 JRE x JVM

Não são a mesma coisa.

### JVM

É a máquina virtual responsável por executar o bytecode.

### JRE

É o ambiente de execução que tradicionalmente incluía:

- JVM
- Bibliotecas da plataforma Java
- Componentes necessários para executar aplicações

```
JRE
 └── JVM
```

---

## ⚠️ Importante sobre versões modernas do Java

A distinção entre JDK e JRE mudou com as versões modernas do Java.

A partir do **Java 11**, a Oracle deixou de distribuir uma JRE separada como produto tradicional.

Além disso, o Java possui o sistema de módulos, introduzido no Java 9, que permite criar runtimes menores e personalizados.

Por isso, atualmente é mais importante entender:

```
JDK → ambiente utilizado para desenvolvimento
JVM → máquina virtual que executa bytecode
```

do que procurar necessariamente por uma instalação separada chamada "JRE".

---

## 🔗 Relação com outros conceitos

- [[JVM]]
- [[JDK]]
- [[Bytecode]]
- [[Java]]
- [[Módulos em Java]]

---

## 🧠 O que eu preciso lembrar?

1. JRE significa Java Runtime Environment.
2. Tradicionalmente, era o ambiente para executar aplicações Java.
3. Incluía a JVM e bibliotecas da plataforma.
4. JVM e JRE não são a mesma coisa.
5. Nas versões modernas do Java, a JRE separada deixou de ser distribuída como antigamente.

---

## 📝 Resumo

A JRE era tradicionalmente o ambiente utilizado para executar aplicações Java, incluindo a JVM e as bibliotecas necessárias. Atualmente, a distribuição do Java é normalmente feita através do JDK, e a antiga distinção entre instalar JDK para desenvolver e JRE separada para executar não funciona mais da mesma maneira.

---

## 🔄 Revisão

- [x]  Sei o que significa JRE
- [x]  Sei diferenciar JRE de JVM
- [x]  Sei explicar por que a JRE é um conceito mais histórico nas versões modernas

---
# 🛠️ JDK (Java Development Kit)

> [!info] Informações
> **Área:** Java  
> **Data:** 23/09  
> **Status:** [X]

---

## 🎯 Objetivo

Entender o que é o JDK, quais ferramentas ele fornece e por que ele é necessário para desenvolver aplicações Java.

---

## 🧠 Conceito

### O que é?

**JDK** significa **Java Development Kit**.

É o conjunto de ferramentas utilizado para **desenvolver aplicações Java**.

Ele inclui a JVM, as bibliotecas da plataforma Java e ferramentas de desenvolvimento.

De forma simplificada:

```text
JDK
├── JVM
├── Bibliotecas Java
└── Ferramentas de desenvolvimento
````

---

## ⚙️ Principais ferramentas

### `javac`

Compilador Java.

Transforma:

```
.java
```

em:

```
.class
```

Exemplo:

```
javac Main.java
```

---

### `java`

Utilizado para iniciar uma aplicação Java.

Exemplo:

```
java Main
```

---

### `jshell`

Permite executar código Java de forma interativa.

```
jshell
```

---

### `javadoc`

Gera documentação a partir de comentários/documentação no código Java.

---

### `javap`

Permite inspecionar informações sobre classes compiladas, incluindo bytecode.

Exemplo:

```
javap -c Main
```

---

## 💡 Exemplo completo

Imagine:

```
Main.java
```

Você executa:

```
javac Main.java
```

O JDK utiliza o compilador para gerar:

```
Main.class
```

Depois:

```
java Main
```

A aplicação é executada pela JVM.

```
              JDK
               │
       ┌───────┴────────┐
       ↓                ↓
   javac              java
       ↓                ↓
 Main.class → JVM → execução
```

---

## 👨‍💻 Na prática

Quando você instala um JDK como o **Eclipse Temurin JDK 21**, você possui um ambiente para desenvolver e executar aplicações Java.

Para verificar a versão do Java:

```
java -version
```

Para verificar a versão do compilador:

```
javac -version
```

---

## 🔄 JDK x JRE x JVM

|Conceito|Função principal|
|---|---|
|**JVM**|Executa bytecode|
|**JRE**|Ambiente de execução tradicional|
|**JDK**|Desenvolvimento de aplicações|

Uma forma simplificada de visualizar:

```
JDK
│
├── Ferramentas de desenvolvimento
│
├── Bibliotecas
│
└── JVM
```

---

## ⚠️ Erros e cuidados

### "JDK é apenas a JVM."

Não.

A JVM é apenas uma parte do ambiente Java utilizado pelo JDK.

### "JRE e JDK são sempre instalações separadas."

Isso corresponde principalmente ao modelo histórico do Java.

Nas versões modernas, normalmente você instala um JDK para desenvolver e executar suas aplicações.

---

## 🔗 Relação com outros conceitos

- [[JVM]]
- [[JRE]]
- [[Bytecode]]
- [[Compilador]]
- [[Garbage Collector]]
- [[Java]]
- [[Maven]]

---

## 🧠 O que eu preciso lembrar?

1. JDK significa Java Development Kit.
2. É utilizado para desenvolver aplicações Java.
3. Possui ferramentas como `javac`, `java`, `jshell`, `javadoc` e `javap`.
4. O JDK inclui a JVM.
5. `javac` compila código `.java` para bytecode `.class`.
6. A JVM executa o bytecode.

---

## 📝 Resumo

O JDK é o conjunto de ferramentas necessário para desenvolver aplicações Java. Ele fornece o compilador, ferramentas de desenvolvimento, bibliotecas da plataforma e a JVM necessária para executar o código.

---

## 🧪 Prática

### Exercício 1

Execute:

```
java -version
```

Depois:

```
javac -version
```

Observe as versões instaladas.

### Exercício 2

Crie:

```
public class Main {

    public static void main(String[] args) {
        System.out.println("Java!");
    }
}
```

Compile:

```
javac Main.java
```

Observe o arquivo:

```
Main.class
```

Depois execute:

```
java Main
```

---

## 🔄 Revisão

### Revisão 1

- [x]  Sei o que significa JDK
- [x]  Sei para que serve o `javac`
- [x]  Sei para que serve o comando `java`
- [x]  Sei diferenciar JDK, JRE e JVM
- [x]  Sei explicar o caminho `.java → .class → JVM`

### Revisão 2

- [x]  Consigo explicar o funcionamento do ambiente Java
- [x]  Consigo compilar uma aplicação manualmente
- [x]  Consigo executar uma classe Java pelo terminal

````

### 🔗 A conexão que você deve guardar

Esses quatro conceitos ficam muito mais fáceis quando você pensa no **fluxo completo**:

```text
             JDK
              │
              │ javac
              ↓
         Main.java
              │
              ↓
         Main.class
          Bytecode
              │
              ↓
             JVM
              │
      ┌───────┴────────┐
      ↓                ↓
   Garbage           JIT
  Collector        Compiler
      │                │
      └───────┬────────┘
              ↓
          Execução
````

E a distinção fundamental para sua base de Java é:

**JDK = ferramentas para desenvolver**  
**JVM = máquina que executa o bytecode**  
**JRE = conceito tradicional do ambiente de execução**  
**Bytecode = código intermediário `.class`**  
**Garbage Collector = gerenciamento automático de memória da JVM**

