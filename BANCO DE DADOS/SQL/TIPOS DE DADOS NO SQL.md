## TIPOS DE DADOS NO SQL

==Os **Tipos de Dados (Data Types)** definem o tipo de informação que pode ser armazenada em uma coluna de uma tabela.==

A escolha correta do tipo de dado influencia:

- Espaço de armazenamento.
- Desempenho.
- Integridade dos dados.
- Facilidade de manutenção.

Os tipos de dados podem ser divididos em:

- Numéricos.
- Texto.
- Data e Hora.
- Booleanos.
- Binários.
- Outros tipos especiais.

---

## TIPOS NUMÉRICOS

## TINYINT

==Armazena números inteiros muito pequenos.==

Exemplo:

```
Idade TINYINT
```

Muito utilizado para:

- Idades.
- Quantidades pequenas.
- Valores booleanos em alguns bancos.

---

## SMALLINT

==Armazena números inteiros pequenos.==

Exemplo:

```
Ano SMALLINT
```

---

## MEDIUMINT (MySQL)

==Armazena números inteiros de tamanho intermediário.==

Exemplo:

```
Codigo MEDIUMINT
```

---

## INT

==Armazena números inteiros.==

Exemplo:

```
ID_Cliente INT
```

É o tipo inteiro mais utilizado.

---

## BIGINT

==Armazena números inteiros muito grandes.==

Exemplo:

```
NumeroTransacao BIGINT
```

---

## DECIMAL

==Armazena números decimais com precisão exata.==

Exemplo:

```
Preco DECIMAL(10,2)
```

Ideal para:

- Dinheiro.
- Salários.
- Valores financeiros.

---

## NUMERIC

==Similar ao DECIMAL.==

Exemplo:

```
Salario NUMERIC(10,2)
```

Muito utilizado no PostgreSQL.

---

## FLOAT

==Armazena números decimais aproximados.==

Exemplo:

```
Temperatura FLOAT
```

---

## DOUBLE

==Armazena números decimais com maior precisão que FLOAT.==

Exemplo:

```
Latitude DOUBLE
```

---

## REAL

==Tipo decimal utilizado em alguns bancos de dados.==

Exemplo:

```
Valor REAL
```

---

## TIPOS DE TEXTO

## CHAR

==Armazena texto de tamanho fixo.==

Exemplo:

```
UF CHAR(2)
```

Valores:

```
RJ SP MG
```

---

## VARCHAR

==Armazena texto de tamanho variável.==

Exemplo:

```
Nome VARCHAR(100)
```

É o tipo textual mais utilizado.

---

## TEXT

==Armazena grandes quantidades de texto.==

Exemplo:

```
Descricao TEXT
```

---

## TINYTEXT (MySQL)

==Versão reduzida do TEXT.==

Exemplo:

```
Observacao TINYTEXT
```

---

## MEDIUMTEXT (MySQL)

==Versão intermediária do TEXT.==

Exemplo:

```
Artigo MEDIUMTEXT
```

---

## LONGTEXT (MySQL)

==Permite armazenar textos extremamente grandes.==

Exemplo:

```
Conteudo LONGTEXT
```

---

## TIPOS DE DATA E HORA

## DATE

==Armazena apenas datas.==

Formato:

```
AAAA-MM-DD
```

Exemplo:

```
DataNascimento DATE
```

---

## TIME

==Armazena apenas horários.==

Formato:

```
HH:MM:SS
```

Exemplo:

```
HoraEntrada TIME
```

---

## DATETIME

==Armazena data e hora.==

Formato:

```
AAAA-MM-DD HH:MM:SS
```

Exemplo:

```
DataCadastro DATETIME
```

---

## TIMESTAMP

==Armazena data e hora podendo ser atualizado automaticamente.==

Exemplo:

```
UltimaAtualizacao TIMESTAMP
```

---

## YEAR (MySQL)

==Armazena apenas o ano.==

Exemplo:

```
AnoFabricacao YEAR
```

---

## INTERVAL (PostgreSQL)

==Armazena intervalos de tempo.==

Exemplo:

```
Duracao INTERVAL
```

Valores:

```
2 days3 months5 hours
```

---

## TIPOS BOOLEANOS

## BOOLEAN

==Armazena verdadeiro ou falso.==

Exemplo:

```
Ativo BOOLEAN
```

Valores:

```
TRUEFALSE
```

---

## BOOL

==Abreviação de BOOLEAN em alguns bancos.==

Exemplo:

```
Disponivel BOOL
```

---

## TIPOS BINÁRIOS

## BINARY

==Armazena dados binários com tamanho fixo.==

Exemplo:

```
Hash BINARY(16)
```

---

## VARBINARY

==Armazena dados binários com tamanho variável.==

Exemplo:

```
Arquivo VARBINARY(255)
```

---

## BLOB

==Armazena arquivos binários.==

Exemplos:

- Imagens.
- PDFs.
- Vídeos.

```
Foto BLOB
```

---

## TINYBLOB (MySQL)

```
MiniArquivo TINYBLOB
```

---

## MEDIUMBLOB (MySQL)

```
Arquivo MEDIUMBLOB
```

---

## LONGBLOB (MySQL)

```
ArquivoGrande LONGBLOB
```

---

## TIPOS ESPECIAIS (POSTGRESQL)

## UUID

==Armazena identificadores únicos universais.==

Exemplo:

```
ID UUID
```

Valor:

```
550e8400-e29b-41d4-a716-446655440000
```

---

## JSON

==Armazena documentos JSON.==

Exemplo:

```
Dados JSON
```

---

## JSONB (PostgreSQL)

==Versão otimizada do JSON.==

Exemplo:

```
Dados JSONB
```

Possui melhor desempenho em consultas.

---

## XML

==Armazena dados XML.==

Exemplo:

```
Documento XML
```

---

## ARRAY (PostgreSQL)

==Permite armazenar listas de valores.==

Exemplo:

```
Telefones TEXT[]
```

---

## TIPOS GEOGRÁFICOS (POSTGRESQL + POSTGIS)

## POINT

==Representa um ponto em coordenadas.==

Exemplo:

```
Localizacao POINT
```

---

## LINE

==Representa uma linha geométrica.==

Exemplo:

```
Rota LINE
```

---

## POLYGON

==Representa um polígono.==

Exemplo:

```
Area POLYGON
```

---

## EXEMPLO COMPLETO

```
CREATE TABLE Clientes (    
ID UUID PRIMARY KEY,    
Nome VARCHAR(100),    
Email VARCHAR(150),    
Salario DECIMAL(10,2),    
DataNascimento DATE,    
DataCadastro TIMESTAMP,    
Ativo BOOLEAN,    
Foto BLOB,    
Dados JSON
);
```

---

## RESUMO DOS PRINCIPAIS TIPOS

| Tipo      | Utilização                             |
| --------- | -------------------------------------- |
| TINYINT   | Inteiros pequenos                      |
| SMALLINT  | Inteiros pequenos                      |
| INT       | Inteiros                               |
| BIGINT    | Inteiros grandes                       |
| DECIMAL   | Valores financeiros                    |
| FLOAT     | Valores aproximados                    |
| DOUBLE    | Valores aproximados com maior precisão |
| CHAR      | Texto fixo                             |
| VARCHAR   | Texto variável                         |
| TEXT      | Texto grande                           |
| DATE      | Data                                   |
| TIME      | Hora                                   |
| DATETIME  | Data e hora                            |
| TIMESTAMP | Data e hora automática                 |
| BOOLEAN   | Verdadeiro/Falso                       |
| BLOB      | Arquivos binários                      |
| UUID      | Identificador único                    |
| JSON      | Documentos JSON                        |
| JSONB     | JSON otimizado (PostgreSQL)            |
| XML       | Dados XML                              |
| ARRAY     | Vetores/Listas (PostgreSQL)            |