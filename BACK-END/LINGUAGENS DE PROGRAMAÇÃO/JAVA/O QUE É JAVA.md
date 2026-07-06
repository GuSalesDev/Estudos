Java é uma linguagem de programação orientada a objetos, criada pela Sun Microsystems (Hoje em dia é a Oracle).

Ela se destaca por ser uma linguagem multiplataforma graças a JVM (Java Virtual Machine), seu lema é _“Write once, run anywhere”_ (escreva uma vez, rode em qualquer lugar).

É uma das linguagens mais utilizadas no mundo, principalmente em sistemas bancários, Android, servidores, back-end, etc.

## JVM, JRE, JDK

São termos que aparecem bastante, entenda diferença entre eles:

| Sigla   | Significa                | Função                                                    |
| ------- | ------------------------ | --------------------------------------------------------- |
| **JVM** | Java Virtual Machine     | Executa o código Java (.class)                            |
| **JRE** | Java Runtime Environment | Ambiente para rodar programas Java (JVM + bibliotecas)    |
| **JDK** | Java Development Kit     | Kit para **desenvolver** (JRE + compilador + ferramentas) |
Pra programar, você instala o **JDK**.

## Sintaxe básica

Sem isso nenhum projeto em java roda.

```
public class Main {
    public static void main(String[] args) {
        System.out.println("Olá, Java!");
    }
}
```

- `class` → define uma classe
- `main()` → ponto de entrada do programa
- `System.out.println()` → imprime na tela