## FUNÇÕES DE AGREGAÇÃO

Utilizadas para realizar cálculos sobre conjuntos de registros.

- **COUNT()** → Conta a quantidade de registros.
- **SUM()** → Soma os valores de uma coluna.
- **AVG()** → Calcula a média dos valores.
- **MAX()** → Retorna o maior valor encontrado.
- **MIN()** → Retorna o menor valor encontrado.

Exemplos:

```
SELECT COUNT(*) FROM Clientes;
SELECT SUM(Salario) FROM Funcionarios;
SELECT AVG(Preco) FROM Produtos;
SELECT MAX(Salario) FROM Funcionarios;
SELECT MIN(Preco) FROM Produtos;
```

---

## FUNÇÕES DE TEXTO

Utilizadas para manipular e formatar textos.

- **CONCAT()** → Junta dois ou mais textos em uma única string.
- **UPPER()** → Converte todo o texto para letras maiúsculas.
- **LOWER()** → Converte todo o texto para letras minúsculas.
- **LENGTH()** → Retorna a quantidade de bytes armazenados na string.
- **CHAR_LENGTH()** → Retorna a quantidade de caracteres da string.
- **TRIM()** → Remove espaços no início e no fim do texto.
- **LTRIM()** → Remove espaços apenas do lado esquerdo.
- **RTRIM()** → Remove espaços apenas do lado direito.
- **SUBSTRING()** → Extrai parte de um texto.
- **LEFT()** → Retorna os caracteres da esquerda.
- **RIGHT()** → Retorna os caracteres da direita.
- **REPLACE()** → Substitui um trecho do texto por outro.
- **REVERSE()** → Inverte a ordem dos caracteres da string.

Exemplos:

```
SELECT CONCAT('João', ' ', 'Silva');
SELECT UPPER('joao');
SELECT SUBSTRING('Gustavo', 1, 4);
```

---

## FUNÇÕES DE DATA E HORA

Utilizadas para obter ou manipular datas e horários.

- **NOW()** → Retorna a data e hora atuais.
- **CURRENT_DATE** → Retorna apenas a data atual.
- **CURRENT_TIME** → Retorna apenas o horário atual.
- **CURRENT_TIMESTAMP** → Retorna a data e hora atuais em formato timestamp.
- **YEAR()** → Extrai o ano de uma data.
- **MONTH()** → Extrai o mês de uma data.
- **DAY()** → Extrai o dia de uma data.
- **HOUR()** → Extrai a hora de um horário ou timestamp.
- **MINUTE()** → Extrai os minutos.
- **SECOND()** → Extrai os segundos.
- **DATEDIFF()** → Calcula a diferença entre duas datas.
- **DATE_ADD()** → Adiciona dias, meses ou anos a uma data.
- **DATE_SUB()** → Subtrai dias, meses ou anos de uma data.
- **AGE()** _(PostgreSQL)_ → Calcula a diferença exata entre datas.

Exemplos:

```
SELECT NOW();
SELECT YEAR(NOW());
SELECT DATE_ADD(NOW(), INTERVAL 7 DAY);
```

---

## FUNÇÕES MATEMÁTICAS

Utilizadas para realizar cálculos numéricos.

- **ROUND()** → Arredonda um número.
- **CEIL() / CEILING()** → Arredonda para cima.
- **FLOOR()** → Arredonda para baixo.
- **ABS()** → Retorna o valor absoluto (sem sinal).
- **MOD()** → Retorna o resto da divisão.
- **POWER()** → Calcula uma potência.
- **SQRT()** → Calcula a raiz quadrada.
- **RAND()** → Gera um número aleatório.
- **PI()** → Retorna o valor de π (Pi).

Exemplos:

```
SELECT ROUND(10.567, 2);
SELECT ABS(-50);
SELECT POWER(2, 3);
```

---

## FUNÇÕES DE CONTROLE

Utilizadas para criar condições e tratamentos dentro das consultas.

- **CASE** → Funciona como um IF/ELSE mais avançado.
- **IF()** _(MySQL)_ → Executa uma ação se uma condição for verdadeira e outra se for falsa.
- **IFNULL()** _(MySQL)_ → Retorna um valor alternativo se o valor for NULL.
- **COALESCE()** → Retorna o primeiro valor que não seja NULL.
- **NULLIF()** → Retorna NULL quando dois valores são iguais.

Exemplos:

```
SELECT CASE       
	WHEN Salario > 5000 THEN 'Alto'       
	ELSE 'Normal'       
	END;
```

```
SELECT COALESCE(Telefone, 'Não informado');
```

---

## FUNÇÕES DE CONVERSÃO

Utilizadas para converter dados entre diferentes tipos.

- **CAST()** → Converte explicitamente um valor para outro tipo.
- **CONVERT()** _(MySQL)_ → Converte valores para outro tipo de dado.

Exemplos:

```
SELECT CAST('100' AS INT);
SELECT CONVERT('100', SIGNED);
```

---

## FUNÇÕES PARA VALORES NULOS

Utilizadas para tratar campos com valor NULL.

- **COALESCE()** → Retorna o primeiro valor não nulo.
- **IFNULL()** _(MySQL)_ → Substitui NULL por outro valor.
- **NULLIF()** → Retorna NULL se dois valores forem iguais.

Exemplos:

```
SELECT COALESCE(Email, 'Sem Email');
SELECT IFNULL(Telefone, 'Não informado');
```

---

## FUNÇÕES DE RANKING E JANELA (WINDOW FUNCTIONS)

Utilizadas para análises avançadas e relatórios.

- **ROW_NUMBER()** → Numera cada linha sequencialmente.
- **RANK()** → Cria um ranking permitindo empates.
- **DENSE_RANK()** → Cria um ranking sem pular posições após empates.
- **LAG()** → Acessa o valor da linha anterior.
- **LEAD()** → Acessa o valor da próxima linha.
- **FIRST_VALUE()** → Retorna o primeiro valor da janela.
- **LAST_VALUE()** → Retorna o último valor da janela.

Exemplo:

```
SELECT Nome,      
	 ROW_NUMBER() OVER()
FROM Funcionarios;
```

---

## FUNÇÕES JSON

Utilizadas para trabalhar com dados armazenados em formato JSON.

- **JSON_EXTRACT()** → Extrai um valor específico do JSON.
- **JSON_OBJECT()** → Cria um objeto JSON.
- **JSON_ARRAY()** → Cria um array JSON.
- **JSON_VALUE()** → Obtém um valor escalar de um JSON.
- **JSON_QUERY()** → Obtém um objeto ou array JSON.

Exemplo:

```
SELECT JSON_EXTRACT(Dados, '$.nome');
```

---

## FUNÇÕES DE SISTEMA

Retornam informações do banco de dados ou da sessão atual.

- **DATABASE()** → Retorna o banco atualmente selecionado.
- **VERSION()** → Retorna a versão do SGBD.
- **USER()** → Retorna o usuário conectado.
- **CURRENT_USER()** → Retorna o usuário autenticado.

Exemplos:

```
SELECT DATABASE();
SELECT VERSION();
SELECT USER();
```

==Essas funções representam a maior parte das operações realizadas no dia a dia de desenvolvimento, análise de dados e administração de bancos de dados MySQL e PostgreSQL.==

==Dominar principalmente COUNT, SUM, AVG, CONCAT, UPPER, LOWER, NOW, COALESCE e CASE já cobre uma grande parcela das consultas encontradas em projetos reais e entrevistas técnicas.==