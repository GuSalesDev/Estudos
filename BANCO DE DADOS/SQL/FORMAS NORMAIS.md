
## FORMAS NORMAIS (1°,2°,3°)

Até aqui, desenhamos o mapa conceitual e o traduzimos em estruturas relacionais concretas, estruturando os processos subjacentes para que o sistema comece a ganhar forma, as tabelas surgem, as chaves se encaixam e a arquitetura relacional começa a se materializar. No entanto, uma etapa muito importante ainda nos aguarda, pois, estruturar não significa, automaticamente, organizar de forma eficiente. Dentro das tabelas recém-criadas podem habitar armadilhas ocultas: ==redundâncias disfarçadas, inconsistências latentes e vínculos frágeis entre dados que, com o tempo, podem comprometer a integridade, _performance_ e o desempenho do sistema.==

Nesse ponto, entra um dos processos mais sofisticados do projeto de banco de dados: a normalização. Veremos que a normalização deve ser vista como um exercício refinado de análise lógica que exige olhar atento para as dependências funcionais existentes entre os atributos. Cada dependência carrega um significado estrutural profundo, uma vez que revela como os dados se relacionam dentro de uma mesma entidade e como eles se condicionam mutuamente. ==Ignorar essas relações significa expor o sistema a duplicações, inconsistências e anomalias nas operações cotidianas.==

Agora, avançaremos pelas três primeiras formas normais - 1ª, 2ª e 3ª - e examinaremos como, passo a passo, essas camadas de normalização ajudam a construir bases sólidas para um banco de dados funcional, estável e preparado para o crescimento sustentável. A cada etapa, desfragmentaremos estruturas malformadas e reorganizaremos os dados em padrões coesos, equilibrados e seguros. Será uma travessia lógica, onde cada decisão carrega impacto direto sobre o comportamento futuro do sistema. Pronto para identificar as raízes da ordem dentro do caos? É hora de adentrarmos na essência da normalização.

Há uma ilusão recorrente, frequentemente alimentada pelo apelo superficial da eficiência imediata, de que um banco de dados se basta quando seus dados encontram algum lugar onde repousar. Engana-se, porém, quem supõe que o simples ato de armazenar já resolve os dilemas mais intrincados da estrutura informacional, pois, como vimos, o projeto de um banco de dados, sobretudo sob a égide do modelo relacional, exige o registro dos fatos através de uma arquitetura deliberada, onde a organização dos dados não degenere em confusão, conflito ou ruína progressiva. É nesse terreno sistemático que emerge a normalização.

Em sua formulação prática, ==a normalização opera como uma espécie de depuração conceitual, um exercício de busca estrutural que visa impedir a mistura de temas heterogêneos dentro de uma mesma tabela==. Ao identificar e, em seguida, dissolver as sobreposições indevidas entre atributos, o processo estabelece um caminho ==onde a redundância desnecessária se torna exceção, não regra==. Nesse percurso, a aplicação sucessiva das formas normais funciona como um filtro lógico, cada qual examinando o grau de coerência estrutural do modelo, fragmentando tabelas quando necessário, subdividindo-as em entidades mais especializadas, e reconfigurando suas interdependências de modo a preservar a estabilidade da arquitetura informacional.

Embora existam cinco formas normais conceitualmente estabelecidas, a prática corrente costuma se apoiar nas três primeiras, cujo alcance já conduz a uma estabilização suficiente para a maioria dos sistemas de produção. Para Alves (2021), ao final desse percurso, o que se obtém não é um modelo inchado, mas antes uma tessitura de relações mais precisas, compactas e resilientes, onde a integridade e a manutenção fluem com maior previsibilidade e segurança. Antes de prosseguir, confira a tabela a seguir.


![[Pasted image 20260706134008.png]]


Ao analisar a tabela, percebe-se que ela reúne muitas informações diferentes em um único lugar, como dados de clientes, produtos, vendedores e pedidos, sem passar por um processo adequado de normalização. Apesar de inicialmente parecer algo prático e simples de acessar, essa estrutura acaba gerando redundância de dados, já que informações como endereço e limite de crédito de um mesmo cliente são repetidas várias vezes.

Isso traz problemas importantes, ==como as anomalias de atualização, inserção e exclusão. Por exemplo, se o endereço de um cliente mudar, eu precisaria atualizar todas as linhas em que ele aparece, o que aumenta o risco de erro==. ==Da mesma forma, ao excluir um pedido, posso acabar removendo também informações do cliente, caso elas não estejam registradas em outro lugar.== Além disso, esse modelo exige mais processamento, já que o sistema precisa ficar comparando dados repetidos.

Isso mostra que há uma falha na modelagem do banco de dados, pois diferentes entidades foram misturadas em uma única tabela. É justamente nesse ponto que entra a normalização, como uma forma de organizar melhor os dados, separando-os em tabelas específicas e relacionadas, reduzindo a redundância e garantindo mais consistência ao sistema.

## PRIMEIRA FORMA NORMAL (1FN)

==A 1FN estabelece a exigência básica de que os dados estejam organizados em estruturas tabulares bem definidas, onde cada campo contém um único valor atômico e indivisível, cada linha seja distinta e cada coluna represente um único atributo do domínio== (Machado, 2014). Se observamos, essa exigência rejeita repetições internas em campos, listas de valores múltiplos em uma única célula ou agrupamentos embutidos dentro de atributos. O modelo relacional, ao exigir atomicidade, busca evitar que informações coexistam de forma aninhada dentro do mesmo campo, o que dificultaria consultas, atualizações e verificações de integridade.

Ao observarmos a tabela anteriormente analisada, notamos que ela já atende parcialmente aos critérios da 1FN. ==Cada célula contém apenas um valor e não há agrupamentos ou listas múltiplas dentro de um mesmo campo==. O nome do produto, o número do pedido, o nome do cliente, o endereço, o limite de crédito, a data e o nome do vendedor ocupam espaços separados e não sobrecarregados por múltiplos dados combinados. Mesmo atendendo formalmente à atomicidade, a tabela ainda exibe um problema estrutural: ==a mistura de assuntos. Dados de produtos, clientes e vendedores aparecem justapostos na mesma estrutura, sem segmentação adequada entre entidades conceituais distintas==. Assim, essa justaposição será precisamente o que levará, nas formas normais seguintes, à decomposição necessária.

> [!example]
> Considere, por exemplo, a coluna Nome Cliente. Embora o campo contenha um único nome por célula, o fato de que o mesmo cliente aparece diversas vezes revela a repetição dos dados pessoais junto com os pedidos. O mesmo ocorre com o Endereço Cliente e o Limite de Crédito. Como vimos, toda vez que Davi Bachmann realiza um novo pedido, seu endereço e limite são replicados. Apesar de a tabela respeitar a atomicidade, ela ainda carece de um refinamento estrutural que distinga com precisão as entidades envolvidas, por isso todo o refinamento será obtido com a aplicação das próximas formas normais, que buscarão isolar dependências, eliminar redundâncias e organizar as relações segundo os princípios de integridade e coesão.

No entanto, a tabela original já apresenta dados atômicos em cada célula. Não há listas, agrupamentos internos ou campos compostos. Todos os atributos estão separados: nome do produto, número do pedido, cliente, endereço, limite de crédito, data e vendedor. Portanto, em termos puramente formais, a estrutura atual já satisfaz o critério básico da 1FN: atomicidade dos dados. Contudo, como estamos em um processo pedagógico, é importante realizar um pequeno ajuste conceitual, pois aplicar a 1FN não significa apenas constatar a atomicidade, mas garantir rigor estrutural logo desde o início da normalização. Para esse exercício, vamos reescrever a tabela no formato 1FN, apenas reafirmando os atributos bem definidos e explicitando que não há multivalores:


| **Pedido Número** | **Nome Produto**  | **Nome Cliente**  | **Endereço Cliente** | **Limite de Crédito** | **Data** | **Nome Vendedor** |
| ----------------- | ----------------- | ----------------- | -------------------- | --------------------- | -------- | ----------------- |
| 1458              | Limpadora a Vácuo | Davi Bachmann     | Rio de Janeiro       | US$ 5,000             | 05/05/00 | Carlos Book       |
| 2730              | Computador        | Helena Daudt      | Vancouver            | US$ 2,000             | 05/06/00 | João Hans         |
| 2461              | Refrigerador      | José Stolaruck    | Chicago              | US$ 2,500             | 07/03/00 | Silvio Pherguns   |
| 456               | Televisão         | Pedro Albuquerque | São Paulo            | US$ 4,500             | 09/05/00 | Frederico Raposo  |
| 1986              | Rádio             | Carlos Antonelli  | Porto Alegre         | US$ 3,000             | 18/09/00 | Rui Ments         |
| 1815              | CD Player         | Davi Bachmann     | Rio de Janeiro       | US$ 5,000             | 13/04/00 | Silvio Pherguns   |
| 1963              | Limpadora a Vácuo | C.V. Ravishandar  | Bombaim              | US$ 7,000             | 03/01/00 | Carlos Book       |
| 1855              | Limpadora a Vácuo | Carlos Antonelli  | Porto Alegre         | US$ 3,000             | 12/03/00 | João Hans         |
| 1943              | Refrigerador      | Davi Bachmann     | Rio de Janeiro       | US$ 5,000             | 19/06/00 | Silvio Pherguns   |
| 2315              | CD Player         | Davi Bachmann     | Rio de Janeiro       | US$ 5,000             | 15/07/00 | João Hans         |
Explicitamos o fato de que cada célula ==contém apenas um valor==; inclusive, como vimos, o formato geral da tabela já satisfazia a 1FN; ==o exercício aqui serviu para fixar o conceito central da primeira forma normal: não pode haver multivalores ou repetições internas dentro de um único campo==. Por que ainda não estamos satisfeitos? Apesar de estar em 1FN, a tabela continua abrigando redundâncias estruturais e mistura de assuntos, o que será o foco da Segunda Forma Normal (2FN), quando passaremos a analisar as dependências funcionais e começaremos a decompor a tabela em estruturas mais coesas.

Ao longo deste exercício, percorremos com precisão as três primeiras etapas da normalização, tomando como ponto de partida uma única tabela inicial, onde informações de natureza distinta coexistiam de forma amalgamada. A partir dela, desdobramos o modelo em estruturas mais coesas, respeitando a lógica interna das entidades envolvidas.

==Na Primeira Forma Normal (1FN), asseguramos a base estrutural elementar: os campos passaram a conter dados atômicos, indivisíveis, sem listas de valores ou agrupamentos internos==. Garantimos que cada célula comportasse apenas uma unidade de informação, de modo que consultas e operações não fossem comprometidas por irregularidades internas nos registros.

Em seguida, aplicamos a Segunda Forma Normal (2FN), que nos obrigou a reconhecer as diferentes entidades que estavam representadas de maneira embaralhada na estrutura inicial. ==Compreendemos que informações de pedidos, clientes, produtos e vendedores, embora relacionadas, pertencem a entidades distintas, cada uma portadora de sua própria identidade lógica==. A partir dessa constatação, as tabelas passaram a ser segmentadas, preservando o princípio de que cada atributo deve depender integralmente da chave primária de sua respectiva tabela.

Avançando para a Terceira Forma Normal (3FN), identificamos as dependências transitivas residuais que ainda habitavam o modelo. ==No caso específico, observamos que o endereço do cliente não é uma propriedade diretamente inseparável da identidade do cliente enquanto chave, e sim uma informação associada que pode ser organizada como uma estrutura própria==. A decomposição final purificou as tabelas, estabelecendo a completa separação conceitual entre as propriedades essenciais de cada entidade.

O percurso das formas normais revela, portanto, a verdadeira essência da modelagem relacional: não basta armazenar dados, é preciso organizar a complexidade com rigor estrutural. Cada etapa remove gradualmente as imperfeições iniciais, restabelecendo a clareza das dependências lógicas e a integridade do sistema como um todo. A normalização, ao final, representa uma forma de proteger o projeto de banco de dados, conduzindo o projetista a um domínio mais disciplinado, resiliente e coerente do seu próprio sistema de informações.
## SEGUNDA FORMA NORMAL (2FN)

Superado o primeiro filtro da atomicidade, a normalização exige um segundo nível de análise, mais profundo, onde se passa a interrogar como os dados estão registrados, além de analisar como eles se relacionam logicamente dentro da estrutura da tabela. É nesse ponto que atua a Segunda Forma Normal (2FN). Enquanto a 1FN se preocupa com a granularidade dos campos, a 2FN desloca o foco para as dependências funcionais parciais, investigando se todos os atributos não chave dependem integralmente da chave primária (Machado, 2014).

==Em termos conceituais, uma tabela está na 2FN quando, além de atender à 1FN, ela não apresenta nenhum atributo que dependa apenas de uma parte da chave primária, no caso de chaves compostas. Sempre que uma tabela possui chave primária simples (um único atributo como identificador), a transição da 1FN para a 2FN costuma ser direta==. O problema surge, geralmente, quando a chave primária é composta por dois ou mais atributos. Nessas situações, é comum que certos campos dependam de apenas uma parte da chave, caracterizando o que se denomina dependência parcial (Alves, 2021).

==A 2FN exige, portanto, a eliminação dessas dependências parciais, movendo os atributos dependentes para outras tabelas onde sua associação lógica com a chave seja plena e indivisível==. O objetivo é estabelecer uma relação de coesão entre a identidade da linha (a chave primária) e as informações que nela residem, pois uma estrutura em 2FN promove maior estabilidade para o modelo de dados, facilita a manutenção e evita anomalias ligadas à redundância parcial de informações.

A aplicação da 2FN torna-se indispensável em situações em que uma tabela está, na prática, acumulando assuntos múltiplos encapsulados na mesma estrutura, que tende a gerar fragilidades que se manifestam durante operações de atualização, inserção e exclusão, pois determinadas informações não pertencem diretamente ao contexto de todas as colunas. ==A 2FN atua justamente como um filtro lógico que separa, organiza e restabelece as fronteiras conceituais das entidades em jogo.==

Nossa tabela original, já ajustada para a 1FN, não há multivalores nem agrupamentos internos, portanto a 1FN foi satisfeita. Agora o que buscamos é isolar dependências parciais, caso existam. Na estrutura atual, ==o campo Pedido Número é suficiente para identificar de forma única cada registro. Logo, temos uma chave primária simples==. Quando há chave simples, não há dependência parcial por definição, pois não existe subdivisão na chave.

Contudo, mesmo sem dependência parcial, a tabela ainda apresenta dependências não essenciais ao Pedido, o que chamamos de mistura de assuntos. Existem dados que não pertencem conceitualmente à entidade Pedido, como:

- Informações do Cliente (Nome Cliente, Endereço Cliente, Limite de Crédito);
- Informações do Produto (Nome Produto);
- Informações do Vendedor (Nome Vendedor).

Cada pedido contém referências a clientes, produtos e vendedores, mas as características desses elementos não são propriedades diretas do pedido, e sim ==propriedades de entidades separadas.== Portanto, mesmo que tecnicamente não haja dependência parcial no sentido clássico (chave composta), existe uma necessidade conceitual de decomposição, pois atributos distintos de entidades distintas estão juntos no mesmo conjunto de dados. É essa decomposição que aplicamos agora. ==A aplicação da 2FN nos leva à separação lógica das entidades envolvidas, o que nos leva a modificar a nossa tabela para permanecer apenas os atributos diretamente relacionados ao ato da compra, por exemplo:==



| **PEDIDO NUMERO (PK)** | **DATA**     | **NOME DO PRODUTO (FK)** | **NOME DO CLIENTE (FK)** | **NOME VENDEDOR (FK)** |
| ------------------ | -------- | -------------------- | -------------------- | ------------------ |
| 1458               | 05/05/00 | Limpadora a Vácuo    | Davi Bachmann        | Carlos Book        |
Agora, centralizamos as informações do cliente em uma única tabela, eliminando as repetições e a necessidade de múltiplas atualizações em vários registros.

### TABELA CLIENTE:


| NOME DO CLIENTE   | ENDEREÇO CLIENTE | LIMITE DE CRÉDITO |
| ----------------- | ---------------- | ----------------- |
| Davi Bachmann     | Rio de Janeiro   | US$ 5,000         |
| Helena Daudt      | Vancouver        | US$ 2,000         |
| José Stolaruck    | Chicago          | US$ 2,500         |
| Pedro Albuquerque | São Paulo        | US$ 4,500         |
| Carlos Antonelli  | Porto Alegre     | US$ 3,000         |
| C.V. Ravishandar  | Bombaim          | US$ 7,000         |
Organizamos aqui os produtos. Neste exemplo, como não há outros atributos de produto além do nome, a tabela é minimalista. No mundo real, atributos como preço, descrição ou categoria seriam adicionados.

### TABELA PRODUTO


| Nome Produto (PK) |
| ----------------- |
| Limpadora a Vácuo |
| Computador        |
| Refrigerador      |
| Televisão         |
| Rádio             |
| CD Player         |
Agora os dados dos vendedores não se repetem a cada venda:


| Nome Vendedor (PK) |
| ------------------ |
| Carlos Book        |
| João Hans          |
| Silvio Pherguns    |
| Frederico Raposo   |
| Rui Ments          |
A organização do banco de dados avançou à medida que cada entidade conceitual foi devidamente isolada em sua própria tabela, ==possibilitando uma separação lógica e, ainda sim, precisa dos dados==. Com essa separação, as repetições de informações foram eliminadas, o que reduz significativamente o risco de inconsistências, erros e desperdício de espaço de armazenamento em um refinamento estrutural que impacta diretamente nas operações cotidianas: processos de atualização, inserção e exclusão passam a ser realizados de forma mais segura e coesa, uma vez que cada modificação incide apenas sobre os registros pertinentes, sem afetar dados redundantes. Como resultado desse processo de organização, a estabilidade estrutural do banco de dados começa a se consolidar, proporcionando uma base sólida para futuras expansões, que, na prática, assegura maior integridade das informações
## TERCEIRA FORMA NORMAL (3FN)



Até aqui, asseguramos a atomicidade na 1FN e eliminamos as dependências parciais na 2FN, todavia, o processo de normalização exige um nível mais rigoroso de depuração lógica. A Terceira Forma Normal (3FN) surge nesse ponto como um mecanismo para assegurar a completa ==independência dos atributos em relação à chave primária== (Machado, 2014). Em outras palavras, a 3FN atua sobre as chamadas dependências transitivas.

Uma tabela atinge a 3FN quando, além de estar na 2FN, não existem atributos não chave que dependam de outro atributo não chave. Em termos lógicos, ==cada atributo não chave deve depender exclusivamente da chave primária, nunca de outro atributo intermediário==. Quando essa condição não é respeitada, cria-se um encadeamento indesejável de dependências dentro da própria tabela, configurando relações transitivas que fragilizam a estrutura.

> [!example]
> Para compreender melhor, considere um exemplo simples. Suponha uma tabela de clientes onde, além do endereço, registra-se também o bairro e a cidade. É evidente que o bairro depende do endereço e, por sua vez, o endereço depende do cliente. Logo, temos uma dependência transitiva: bairro depende de endereço, que depende do cliente. A 3FN atua precisamente para interromper essas cadeias, deslocando os atributos dependentes para tabelas específicas, estabelecendo assim um modelo onde cada coluna expressa uma propriedade diretamente vinculada à identidade representada pela chave primária da tabela.

> [!important]
> A aplicação da 3FN torna-se importante em sistemas que visam estabilidade estrutural a longo prazo, pois sua ausência expõe o banco de dados a anomalias sutis, de difícil detecção e dispendiosas de corrigir posteriormente. Modelos que não alcançam a 3FN tendem a gerar inconsistências quando atributos intermediários são alterados sem o devido reflexo em todos os registros relacionados, comprometendo a integridade lógica da base como um todo (Machado, 2014).

Quando aplicar a 3FN? Sempre que, ao analisar uma tabela, for possível identificar atributos não chave que dependem de outros atributos não chave, caracterizando dependência transitiva, mesmo que a tabela já esteja na 2FN. A 3FN não tem como objetivo multiplicar tabelas desnecessariamente, mas garantir que cada atributo dependa diretamente da chave primária, tornando o modelo mais consistente e evitando problemas de atualização.

No exemplo apresentado, temos a tabela Cliente que já está em 3FN:

| NOME DO CLIENTE   | ENDEREÇO CLIENTE | LIMITE DE CRÉDITO |
| ----------------- | ---------------- | ----------------- |
| Davi Bachmann     | Rio de Janeiro   | US$ 5,000         |
| Helena Daudt      | Vancouver        | US$ 2,000         |
| José Stolaruck    | Chicago          | US$ 2,500         |
| Pedro Albuquerque | São Paulo        | US$ 4,500         |
| Carlos Antonelli  | Porto Alegre     | US$ 3,000         |
| C.V. Ravishandar  | Bombaim          | US$ 7,000         |
==Observa-se que tanto o endereço quanto o limite de crédito dependem diretamente do cliente, não havendo dependência transitiva entre os atributos. Portanto, do ponto de vista da 3FN, a tabela já se encontra adequada.==

Agora vamos botar a tabela pedidos em 3FN:

| Pedido Número (PK) | Data     | Nome Cliente (FK) | Nome Produto (FK) | Nome Vendedor (FK) |
| ------------------ | -------- | ----------------- | ----------------- | ------------------ |
| 1458               | 05/05/00 | Davi Bachmann     | Limpadora a Vácuo | Carlos Book        |
| 2730               | 05/06/00 | Helena Daudt      | Computador        | João Hans          |
| 2461               | 07/03/00 | José Stolaruck    | Refrigerador      | Silvio Pherguns    |
| 456                | 09/05/00 | Pedro Albuquerque | Televisão         | Frederico Raposo   |
| 1986               | 18/09/00 | Carlos Antonelli  | Rádio             | Rui Ments          |
| 1815               | 13/04/00 | Davi Bachmann     | CD Player         | Silvio Pherguns    |
| 1963               | 03/01/00 | C.V. Ravishandar  | Limpadora a Vácuo | Carlos Book        |
| 1855               | 12/03/00 | Carlos Antonelli  | Limpadora a Vácuo | João Hans          |
| 1943               | 19/06/00 | Davi Bachmann     | Refrigerador      |                    |
| 2315               | 15/07/00 | Davi Bachmann     | CD Player         | João Hans          |
Todos os atributos não-chave dependem exclusivamente da chave primária, tudo depende exclusivamente do Pedido Número (PK), sem dependências transitivas ou parciais. Contudo, caso existam regras de negócio adicionais, como a exclusividade de produto por vendedor, o modelo precisaria ser ajustado, pois surgiriam dependências entre atributos não-chave, violando a 3FN.

### TABELA PEDIDO



No entanto, ao considerar a possibilidade de um cliente possuir mais de um endereço, surge a necessidade de reorganizar a estrutura. Nesse caso, a separação não ocorre por exigência da 3FN, mas sim por uma questão de modelagem, a fim de representar corretamente o relacionamento entre cliente e endereço.

Dessa forma, a estrutura pode ser reorganizada nas seguintes tabelas:
### TABELA CLIENTE 

| **NOME CLIENTE (PK)** | **LIMITE DE CRÉDITO** |
| --------------------- | --------------------- |
| Davi Bachmann         | US$ 5,000             |
| Helena Daudt          | US$ 2,000             |
| José Stolaruck        | US$ 2,500             |
| Pedro Albuquerque     | US$ 4,500             |
| Carlos Antonelli      | US$ 3,000             |
| C.V. Ravishandar      | US$ 7,000             |
### TABELA ENDEREÇO CLIENTE

| **NOME CLIENTE (PK/FK)** | ENDEREÇO       |
| ------------------------ | -------------- |
| Davi Bachmann            | Rio de Janeiro |
| Helena Daudt             | Vancouver      |
| José Stolaruck           | Chicago        |
| Pedro Albuquerque        | São Paulo      |
| Carlos Antonelli         | Porto Alegre   |
| C.V. Ravishandar         | Bombaim        |




A estrutura das tabelas melhora quando cada uma passa a ter apenas atributos que dependem diretamente da sua chave primária. Com isso, elimina-se a redundância e evita-se que um dado dependa indiretamente de outro. Esse processo torna as operações de atualização mais seguras, já que as mudanças passam a acontecer de forma direta e sem risco de inconsistências. Dessa forma, o banco de dados deixa de ter informações duplicadas e passa a representar melhor a realidade do sistema, de forma mais organizada e confiável.