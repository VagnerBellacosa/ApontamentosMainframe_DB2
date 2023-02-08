![img](https://ivansanchesblog.files.wordpress.com/2016/07/db2.jpg?w=940)

[8 08+00:00 JULHO 08+00:00 2016](https://ivansanchesblog.wordpress.com/2016/07/08/db2-queries-uteis-do-dia-a-dia/) [IVANSANCHESDEV](https://ivansanchesblog.wordpress.com/author/ivansanchesblog/) [DB2](https://ivansanchesblog.wordpress.com/category/db2/)

# DB2 – Queries úteis do dia-a-dia



![img](https://i0.wp.com/files.escola-de-programadores.webnode.com/200000017-7ab587baf5/DB2.png)

\001) Como você descobre o número total de linhas em uma tabela DB2?

Use SELECT COUNT(*) … na query do db2

\002) Como voce elimina valores duplicados em um SELECT no DB2?

Use SELECT DISTINCT … na query do db2

\003) Como voce seleciona uma linha usando os índices no DB2?

Especifica as colunas que são íncides na clausúla WHERE na query do db2

\004) Como voce acha o valor máximo de uma coluna no db2?

Use SELECT MAX(…) .. na query do do db2

\005) Como voce seleciona os primeiros 5(cinco) characteres da coluna IOPER_EMPTM_FINAN no DB2 da tabela TOPER_EMPTM_FINAN ?



Anúncios

<iframe src="https://c0.pubmine.com/sf/0.0.7/html/safeframe.html" referrerpolicy="unsafe-url" id="safeframe-sf-inline-ad-0" frameborder="no" scrolling="no" allowtranparency="true" hidefocus="true" tabindex="-1" marginwidth="0" marginheight="0" style="box-sizing: inherit; max-width: 100%; border: none; display: block; height: 250px; left: 0px; margin: 0px; position: absolute; top: 0px; visibility: inherit; width: 300px; z-index: 0;"></iframe>

DENUNCIAR ESTE ANÚNCIO



SELECT SUBSTR(IOPER_EMPTM_FINAN, 1, 8) FROM DB2PRD.TOPER_EMPTM_FINAN;

\006) O são funções agregadas?

São funções matemáticas para serem usadas na clausúla SELECT

\007) Pode voce usar a função MAX em uma coluna CHAR?

Sim

\008) Meu comando SQL  SELECT AVG(VVERBA_RSORI_CSIGN) FROM DB2PRD.TRETOR_CONVE_CSIGN está trazendo um resultado errado. Porque?

Porque a coluna VVERBA_RSORI_CSIGN foi declarada como NULLs e algumas linhas cuja coluna que possuem valores NULLs também são contadas.

\009) Como você concatena o CUSUAR_INCL e CUSUAR_MANUT da tabela DB2PRD.TLCTO_OPER_EMPTM a fim de obter os nomes dos usuários?

SELECT CUSUAR_INCL || ‘ ‘ || CUSUAR_MANUT FROM DB2PRD.TLCTO_OPER_EMPTM;

\010) Como é usado a função VALUE?



Anúncios

<iframe src="https://c0.pubmine.com/sf/0.0.7/html/safeframe.html" referrerpolicy="unsafe-url" id="safeframe-sf-inline-ad-1" frameborder="no" scrolling="no" allowtranparency="true" hidefocus="true" tabindex="-1" marginwidth="0" marginheight="0" style="box-sizing: inherit; max-width: 100%; border: none; display: block; height: 250px; left: 0px; margin: 0px; position: absolute; top: 0px; visibility: inherit; width: 300px; z-index: 0;"></iframe>

DENUNCIAR ESTE ANÚNCIO



\1. Avoid -ve SQLCODEs by handling nulls and zeroes in computations

\2. Substitui por um valor válido qualquer NULLS usado na query.

\011) O que é UNION,UNION ALL?

UNION : elimina duplicatas

UNION ALL: retém duplicatas

Ambos são usados para combinar os resultados de comandos SELECT diferentes.

Suponha que eu tenho cinco comandos SELECT conectados por UNION/UNION ALL, quantas vezes eu deveria especificar UNION para eliminar as linhas duplicadas?

Uma vez.

\012) Quais as restrições do uso do UNION embutido no SQL?

Tem que estar em um CURSOR.

\013) Na cláusula WHERE o que é BETWEEN e IN?

BETWEEN traz uma gama de valores enquanto o IN traz uma lista de valores.



Anúncios

<iframe src="https://c0.pubmine.com/sf/0.0.7/html/safeframe.html" referrerpolicy="unsafe-url" id="safeframe-sf-inline-ad-2" frameborder="no" scrolling="no" allowtranparency="true" hidefocus="true" tabindex="-1" marginwidth="0" marginheight="0" style="box-sizing: inherit; max-width: 100%; border: none; display: block; height: 250px; left: 0px; margin: 0px; position: absolute; top: 0px; visibility: inherit; width: 300px; z-index: 0;"></iframe>

DENUNCIAR ESTE ANÚNCIO



\014) O BETWEEN contempla os valores extremos especificados?

Sim.

\015) O que é ‘ LIKE’ usado dentro da cláusula WHERE? O que são os caracteres de wildcard?

LIKE é usado para partidas de STRING parciais. ‘%’ ( para uma string de muitos caracteres ) e ‘_’ (para qualquer caráter único ) são os dois caracteres wildcard.

\016) Quando você deve usar o comando LIKE?

Para dar partida a uma pesquisa e.g. para pesquisar o empregado por nome, você não necessita especificar o nome completo; usando LIKE, você pode pesquisar for parte do nome, por exemplo.

\017) O que é o significado de sublinha (‘_ ‘) na declaração LIKE ?

Para pesquisa de qualquer caracter único.

\018) O que voce realiza com GROUP BY … e a cláusula HAVING?

GROUP BY as linhas selecionadas com valores distintos da coluna pela qual sera agrupada.



Anúncios

<iframe src="https://c0.pubmine.com/sf/0.0.7/html/safeframe.html" referrerpolicy="unsafe-url" id="safeframe-sf-inline-ad-3" frameborder="no" scrolling="no" allowtranparency="true" hidefocus="true" tabindex="-1" marginwidth="0" marginheight="0" style="box-sizing: inherit; max-width: 100%; border: none; display: block; height: 250px; left: 0px; margin: 0px; position: absolute; top: 0px; visibility: inherit; width: 300px; z-index: 0;"></iframe>

DENUNCIAR ESTE ANÚNCIO



HAVING seleciona grupos que tenham os critérios especificados

\019) Considere que a coluna CCONDC_ECONC da tabela de lançamentos e empréstimos financeiros é NULL. Como voce seleciona uma coluna com NULL?

SELECT CLCTO_EMPTM_FINAN

FROM  DB2PRD.TLCTO_EMPTM_FINAN

WHERE CCONDC_ECONC IS NULL

\020) Qual é o resultado desta query se nenhuma linha for selecionada:

SELECT SUM(VPRINC_ORIGN_PCELA)

FROM  DB2PRD.TSMULA_FLUXO_FINCR

WHERE QDIA_UTIL_VCTO > 0 OR

QDIA_UTIL_VCTO IS NULL

\021) Por que o SELECT * não é preferido em programas com SQL embutido?

Por três razões:



Anúncios

<iframe src="https://c0.pubmine.com/sf/0.0.7/html/safeframe.html" referrerpolicy="unsafe-url" id="safeframe-sf-inline-ad-4" frameborder="no" scrolling="no" allowtranparency="true" hidefocus="true" tabindex="-1" marginwidth="0" marginheight="0" style="box-sizing: inherit; max-width: 100%; border: none; display: block; height: 250px; left: 0px; margin: 0px; position: absolute; top: 0px; visibility: inherit; width: 300px; z-index: 0;"></iframe>

DENUNCIAR ESTE ANÚNCIO



Se a estrutura da tabela for modificada (um campo é somado), o programa terá que ser modificado.

Porque o programa irá recuperar colunas que podem não serem usadas no programa, sobrecarregando a area de I/O.

A chance de um index único será perdido.

O que é subqueries correlatas?

A subquery in which the inner (nested) query efers back to the table in the outer query. Correlated subqueries must be evaluated for each qualified row of the outer query that is referred to.

\022) O que é um CURSOR? Porque deverá ser usado?

Cursor é um dispositivo de programação que permite o SELECT achar varias linhas de uma tabela mas lhe devolve de cada vez uma de cada vez.

Cursor deverá ser usado porque a host language pode tratar só uma linha de cada vez.

\023) Como você recuperaria linhas de uma tabela do DB2 em SQL embutido?

Usando o comando SELECT, ou usando o CURSOR.



Anúncios

<iframe src="https://c0.pubmine.com/sf/0.0.7/html/safeframe.html" referrerpolicy="unsafe-url" id="safeframe-sf-inline-ad-5" frameborder="no" scrolling="no" allowtranparency="true" hidefocus="true" tabindex="-1" marginwidth="0" marginheight="0" style="box-sizing: inherit; max-width: 100%; border: none; display: block; height: 50px; left: 0px; margin: 0px; position: absolute; top: 0px; visibility: inherit; width: 320px; z-index: 0;"></iframe>

DENUNCIAR ESTE ANÚNCIO



Sem o uso do cursor, que outros modos estão disponíveis a você recuperar uma linha de uma tabela em SQL embutido?

Usando o comando SELECT.

\024) Onde você especificaria o comando DECLARE CURSOR?

Veja outras perguntas a respeito dessa questão.

\025) Como você especifica e usa um cursor em um programa de COBOL?

Use o comando DECLARE CURSOR statement na WORKING-STORAGE ou na PROCEDURE DIVISION (antes do OPEN CURSOR), para especificar o comando SELECT. Então use o OPEN, FETCH para leitura das linhas e finalmente o CLOSE.

\026) O que acontece no comando OPEN CURSOR?

Se houver uma cláusula ORDER BY, linhas são selecionadas, são ordenadas e disponibilizadas no comando FETCH. Outro modo simplesmente o cursor é colocado na primeira linha.

\027) A DECLARE CURSOR é executável?

Não.



Anúncios

<iframe src="https://c0.pubmine.com/sf/0.0.7/html/safeframe.html" referrerpolicy="unsafe-url" id="safeframe-sf-inline-ad-6" frameborder="no" scrolling="no" allowtranparency="true" hidefocus="true" tabindex="-1" marginwidth="0" marginheight="0" style="box-sizing: inherit; max-width: 100%; border: none; display: block; height: 250px; left: 0px; margin: 0px; position: absolute; top: 0px; visibility: inherit; width: 300px; z-index: 0;"></iframe>

DENUNCIAR ESTE ANÚNCIO



\028) Você pode ter mais de um CURSOR aberto ao mesmo tempo no programa?

Sim.

\029) When you COMMIT, is the cursor closed?

Sim.

\030) Como você deixa o cursor aberto após a emissão de um COMMIT? (para 2,3 DB2 ou acima somente)

Use a opção WITH HOLD na instrução DECLARE CURSOR. Mas, não tem efeito em programas CICS pseudo-conversacionais.

\031) Dê a definição do COBOL de um campo VARCHAR.

Uma coluna VARCHAR, com o nome de WS-VARCHAR, é definida da seguinte forma:

10 WS-VARCHAR.

49 WS-VARCHAR-LEN     PIC S9(4) USAGE COMP.

49 WS-VARCHAR-TEXT    PIC X(1920).

\032) Qual é o tamanho de armazenamento físico de cada um dos tipos de dados do DB2: DATE, TIME, TIMESTAMP?



Anúncios

<iframe id="inline-ad-7_iframe" frameborder="0" scrolling="no" src="about:blank" class="ata-frame" style="box-sizing: inherit; max-width: 100%; border: none; height: 50px; margin: 0px; overflow: hidden; width: 320px;"></iframe>

DENUNCIAR ESTE ANÚNCIO



DATE:          4 bytes

TIME:          3 bytes

TIMESTAMP:    10 bytes

\033) Qual é a PICTURE no COBOL dos seguintes tipo de dados do DB2: DATE, TIME, TIMESTAMP?

DATE:        PIC X(10)

TIME         PIC X(08)

TIMESTAMP:   PIC X(26)

\034) Qual é a PICTURE no COBOL para a coluna definida no DB2 como DECIMAL(11,2)?

PIC S9(9)V99 COMP-3.

\035) O que é DCLGEN?

DeCLarations GENerator: Usado para criar as variáveis HOST (copy books) para as definições das tabelas. Também cria o DECLARE das tabelas.



Anúncios

<iframe id="inline-ad-8_iframe" frameborder="0" scrolling="no" src="about:blank" class="ata-frame" style="box-sizing: inherit; max-width: 100%; border: none; height: 50px; margin: 0px; overflow: hidden; width: 320px;"></iframe>

DENUNCIAR ESTE ANÚNCIO



\036) Quais são os conteúdos da DCLGEN?

\1. Comando EXEC SQL DECLARE TABLE que dá o plano da tabela/view em termos de datatypes do DB2.

\2. Uma linguagem hospedeira que dá as definições das variáveis para os nomes de coluna.

\037) É obrigatório o uso de DCLGEN? Se não, por que você deve usá-lo ?

Não é obrigatório o uso de DCLGEN.

Usando DCLGEN, ajuda a detectar erros em Select (nomes de coluna) durante a fase de pré-compilação (por causa do DECLARE TABLE).

DCLGEN gera definições precisas de variáveis para a tabela reduzindo as chances de erro.

 

\038) Como é executado um pgm batch DB2 ?

\1. Use o utilitário DSN para executar um programa batch a partir do DB2 TSO nativo. ex:



Anúncios

<iframe id="inline-ad-9_iframe" frameborder="0" scrolling="no" src="about:blank" class="ata-frame" style="box-sizing: inherit; max-width: 100%; border: none; height: 50px; margin: 0px; overflow: hidden; width: 300px;"></iframe>

DENUNCIAR ESTE ANÚNCIO



DSN SYSTEM(DSP3)

RUN PROGRAM(EDD470BD) PLAN(EDD470BD) LIB(‘ED 01T.OBJ.LOADLIB’)

END

\2. Use o programa utilitário IKJEFT01 para executar o comando acima DSN em JCL.

Assumindo que o padrão de um site é o nome pgm = nome do plano, qual é a maneira mais fácil de descobrir quais PGMs são afetados pela mudança na estrutura de uma tabela?

Consulta as tabelas do catálogo SYSPLANDEP e SYSPACKDEP.

 

\039) Alguns nomes de campos da SQLCA.

SQLCODE, SQLERRM, SQLERRD

\040) Como você poderia facilmente encontrar a quantidade de linhas atualizadas após um comando update ?

Check the value stored in SQLERRD(3).



Anúncios

<iframe id="inline-ad-10_iframe" frameborder="0" scrolling="no" src="about:blank" class="ata-frame" style="box-sizing: inherit; max-width: 100%; border: none; height: 250px; margin: 0px; overflow: hidden; width: 300px;"></iframe>

DENUNCIAR ESTE ANÚNCIO



\041) O que é EXPLAIN?

EXPLAIN é usado para exibir o caminho de acesso determinado pelo otimizador do comando SQL. Pode ser usado no SPUFI ou no step de BIND.

\042) O que é necessário usar antes de fazer EXPLAIN?

Assegurar que a tabela utilizada no EXPLAIN foi criada sob o AUTHID na PLAN_TABLE.

\043) Onde a saída do EXPLAIN é armazenada?

No userid.PLAN_TABLE

\044) EXPLAIN tem saída com MATCHCOLS = 0. O que isto significa?

Não fez scan no indíce, se ACCESSTYPE = I.

\045) Como é executado o EXPLAIN de um comando dinâmico SQL ?

\1. Use SPUFI ou QMF para o EXPLAIN de um comando dinâmico SQL

\2. Inclua a cláusula EXPLAIN no comando dinâmico SQL

\046) Quais são os possíveis níveis de isolation ?



Anúncios

<iframe id="inline-ad-11_iframe" frameborder="0" scrolling="no" src="about:blank" class="ata-frame" style="box-sizing: inherit; max-width: 100%; border: none; height: 50px; margin: 0px; overflow: hidden; width: 300px;"></iframe>

DENUNCIAR ESTE ANÚNCIO



CS: Cursor Stability

RR: Repeatable Read

\047) Qual é a diferença entre CS and RR ?

CS: Libera o lock de uma página após o uso

RR: Retem todos os locks adquiridos até o fim da transação

\048) Onde você especifica os níveis de isolation ?

ISOLATION LEVEL é um parâmetro especificado no processo de bind.

\049) Quais são os vários níveis de locks disponíveis ?

PAGE, TABLE, TABLESPACE

\050) Como o DB2 determina qual o lock-size a ser usado?

\1. Basedo no lock-size dado na criação do tablespace

\2. Programador pode dizer diretamente ao DB2 qual lock-size usar

\3. Se o parâmetro lock-size é ANY, o DB2 usuará o lock-size PAGE



Anúncios

<iframe id="inline-ad-12_iframe" frameborder="0" scrolling="no" src="about:blank" class="ata-frame" style="box-sizing: inherit; max-width: 100%; border: none; height: 50px; margin: 0px; overflow: hidden; width: 300px;"></iframe>

DENUNCIAR ESTE ANÚNCIO



\051) Qual é a desvantagem de usar o nível de lock PAGE ?

Maiores recursos são utilizados para fazer atualizações.

\052) O que é lock escalation?

Promovendo um PAGE lock-size da tabela ou tablespace quando uma transação adquire mais locks do que o especificado no NUMLKTS.  Mais locks podem ser feitos num tablespace quando ocorrer um lock escalation.

\053) Quais são os vários locks disponíveis ?

SHARE, EXCLUSIVE, UPDATE

\054) Posso usar LOCK TABLE em uma view?

Não. Para lock de uma view, faça lock nas tabelas.

\055) O que é ALTER ?

Comando do SQL usado para alterar as definições dos objetos do DB2.

 

\056) O que é um DBRM, PLAN ?



Anúncios

<iframe id="inline-ad-13_iframe" frameborder="0" scrolling="no" src="about:blank" class="ata-frame" style="box-sizing: inherit; max-width: 100%; border: none; height: 250px; margin: 0px; overflow: hidden; width: 300px;"></iframe>

DENUNCIAR ESTE ANÚNCIO



DBRM: DataBase Request Module, tem o comando SQL extraído de uma linguagem nativa do programa pré-compilador.

PLAN: É o resultado de um processo BIND. O código é executado de um comando SQL no DBRM.

 

\057) O que é ACQUIRE/RELEASE no BIND?

Determina o ponto no qual o DB2 acquires or releases locks da tabela e tablespaces, incluindo nas intenções de locks.

\058) O que acontece se o indíce usado no PLAN é excluído ?

Plan é marcado como inválido. Na próxima vez que o plano é acessado um novo plano é recarregado.

\059) O que são PACKAGES ?

Eles contém códigos executáveis para comandos SQL no DBRM.

\060) Quais são as vantagens usando um PACKAGE?



Anúncios

<iframe id="inline-ad-14_iframe" frameborder="0" scrolling="no" src="about:blank" class="ata-frame" style="box-sizing: inherit; max-width: 100%; border: none; height: 250px; margin: 0px; overflow: hidden; width: 300px;"></iframe>

DENUNCIAR ESTE ANÚNCIO



\1. Evitar o bind de um número maior de DBRM members em um plano

\2. Evitar um custo maior de bind

\3. Evitar uma indisponibilidade de uma transação durante o bind e a carga automática do plano

\4. Minimizar a complexidade da volta no caso de falha (erro).

\061) O que é uma collection?

O usuário define o nome de um conjunto (grupo) de packages. Não é uma existência física. O usuário principal é o group packages.

\062) Como você imprime a saída de comando SQL no SPUFI?

Imprimindo o arquivo de saída.

\063) O que é um SQL dinâmico?

Um SQL dinâmico é um comando SQL criado no programa em tempo de execução

\064) Quando é determinado o acesso para um SQL dinâmico?

Em tempo de execução, quando o comando PREPARE é emitido.



Anúncios

DENUNCIAR ESTE ANÚNCIO



\065) Suponha que eu tenho um programa que utiliza um SQL dinâmico e que tenha tido um bom desempenho até agora. Acho que o desempenho piorou. O que aconteceu ?

Provavelmente RUN STATS não é feito e o programa está usando um índice errado devido a estatísticas incorretas.

Provavelmente RUN STATS é feito e otimizador escolheu um caminho de acesso errado com base nas últimas estatísticas

 

\066) Como o DB2 armazena NULL fisicamente ?

Com um prefixo extra-byte para o valor da coluna fisica, o prefixo é null Hex ’00 ‘ se o valor está presente e Hex’FF ‘ se o valor não está presente.

\067) Como você recupera dados de uma coluna nullable ?

Usando indicadores de null. Sintaxe … INTO :HOSTVAR:NULLIND

\068) Qual é a cláusula picture de uma variável indicadora de null ?

S9(4) COMP.



Anúncios

<iframe src="https://c0.pubmine.com/sf/0.0.7/html/safeframe.html" referrerpolicy="unsafe-url" id="safeframe-sf-inline-ad-16" frameborder="no" scrolling="no" allowtranparency="true" hidefocus="true" tabindex="-1" marginwidth="0" marginheight="0" style="box-sizing: inherit; max-width: 100%; border: none; display: block; height: 50px; left: 0px; margin: 0px; position: absolute; top: 0px; visibility: inherit; width: 320px; z-index: 0;"></iframe>

DENUNCIAR ESTE ANÚNCIO



\069) O que significa o indicador de null -1, 0, -2?

-1 : o campo é null

0 : o campo não é null

-2 : o valor do campo foi truncado

\070) Como você insere um registro com uma coluna nullable ?

Para inserir um NULL, move -1 para o indicador de null

Para inserir uma valor válido, move 0 para o indicador de null

\071) Que é RUNSTATS?

Um utilitário DB2 é usado para coletar estatísticas sobre os valores nas colunas da tabelas as quais podem ser usadas pelo otimizador para decidir o caminho de acesso.

Também as collects statistics podem ser usadas para gerenciar o espaço. Estas estatísticas são armazenadas nas tabelas do catálogo DB2.

\072) Quando você executará o run RUNSTATS?

Após o load, ou após mass updates, inserts, deletes, ou após REORG.



Anúncios

<iframe id="inline-ad-17_iframe" frameborder="0" scrolling="no" src="about:blank" class="ata-frame" style="box-sizing: inherit; max-width: 100%; border: none; height: 50px; margin: 0px; overflow: hidden; width: 300px;"></iframe>

DENUNCIAR ESTE ANÚNCIO



\073) Dê alguns exemplos de estatísticas coletadas durante RUNSTATS?

\# Linhas da tabela

Percentual de linhas em clustering sequence

\# valores distintos em colunas indíces

\# linhas movidas perto / longe das páginas que foram aumentadas de tamanho

\074) Que é REORG? Quando é usado ?

REORG reorganiza dados fisícos armazenados para clusterizar as linhas, posicionando o estouro de linhas na própria sequência, para adquirir espaço, para liberar o espaço livre. É usado após pesadas atividades de updates, inserts e delete.

\075) Que é IMAGECOPY ?

É um full backup de uma tabela DB2 a qual poderá ser usada para recovery.

\076) Quando utilizar o IMAGECOPY?

Fazer routinas de backup das tabelas

Após o LOAD com LOG NO



Anúncios

<iframe src="https://c0.pubmine.com/sf/0.0.7/html/safeframe.html" referrerpolicy="unsafe-url" id="safeframe-sf-inline-ad-18" frameborder="no" scrolling="no" allowtranparency="true" hidefocus="true" tabindex="-1" marginwidth="0" marginheight="0" style="box-sizing: inherit; max-width: 100%; border: none; display: block; height: 250px; left: 0px; margin: 0px; position: absolute; top: 0px; visibility: inherit; width: 300px; z-index: 0;"></iframe>

DENUNCIAR ESTE ANÚNCIO



Após REORG com LOG NO

\077) O que é o status COPY PENDING ?

Um estado no qual, um image copy de uma tabela precisa ser feito, neste status, a tabela está disponível somente para queries. Você não pode fazer update nesta tabela.

Para remover o status COPY PENDING, você faz um image copy ou use REPAIR utility.

\078) Que é CHECK PENDING ?

Quando a tabela é LOADed com opção ENFORCE NO, então a tabela é deixada em status de CHECK PENDING.

Significa que o utilitário de LOAD não executa a constraint checking.

\079) Que é QUIESCE?

A QUIESCE libera todos o buffers do DB2 no disco. Isto dá um correct snapshot (imagem consistente) do database e pode ser usado antes e após um qualquer IMAGECOPY.

\080) Que é um clustering index ?



Anúncios

<iframe id="inline-ad-19_iframe" frameborder="0" scrolling="no" src="about:blank" class="ata-frame" style="box-sizing: inherit; max-width: 100%; border: none; height: 250px; margin: 0px; overflow: hidden; width: 300px;"></iframe>

DENUNCIAR ESTE ANÚNCIO



Armazena as linhas de dados em uma sequência especificada pelo indíce.

\081) Quantos clustering indexes pode ser definido para uma tabela ?

Somente um.

\082) Qual é a diferença entre primary key & unique index?

Primary : Primary key consiste de uma ou mais colunas que identifiquem de forma única uma linha da tabela.

Unique index: um objeto físico que armazena valores únicos. Pode ter um ou mais unique indexes em uma tabela.

\083) Que é um sqlcode -922 ?

Authorization failure

\084) Que é sqlcode -811?

comando SELECT tem como resultado mais de uma linha.

\085) Se temos uma view que é um join de duas ou mais tabelas,pode esta view ser atualizada ?

Não.

\086) Quais são os 4 environments que podem acessar o DB2 ?

TSO, CICS, IMS and BATCH

\087) Que é um inner join, e um outer join ?

Inner Join: combina informações de duas ou mais tabelas pela comparação de todos os valores que são iguais no critério de pesquisa das colunas envolvidas de uma ou mais tabelas.

Outer join é aquele em que você quer tanto as linhas correspondentes e não correspondentes a serem devolvidos. DB2 não tem operador específico para as junções externas, pode ser simulada através da combinação de uma junção ou de uma subconsulta correlacionada com a UNIÃO.

 

\088) Que é FREEPAGE e PCTFREE na criação de TABLESPACE ?

PCTFREE: percentagem de cada page que será deixada livre

FREEPAGE: Número de pages para ser loaded com dados entre cada page livre

\089) Que são simple, segmented e partitioned table spaces ?

Simple Tablespace:

Pode ter uma ou mais tabelas

Linhas de múltiplas tabelas podem ser intercalada em uma página sob o controle DBAs.

Segmented Tablespace:

Pode conter ou mais tabelas

Tablespace é dividido em segmentos de 4 a 64 pages incrementadas de 4 pages. Cada segmento é dedicado para uma tabela.

Uma tabela pode ocupar múltiplos segmentos

Partitioned Tablespace:

Pode conter uma tabela

Tablespace é dividido em partes e cada parte é colocada em um VSAM dataset.

\090) Que é index cardinality?

O número de valores distintos que uma coluna pode conter.

\091) Que é synonym ?

Synonym é um nome alternativo de uma table ou de uma view. Um synonym é accessado somente pelo creator.

\092) Qual é a diferença entre SYNONYM e ALIAS?

SYNONYM: é deletado quando uma table ou tablespace é deletada. Synonym é disponibilizado somente para o creator.

ALIAS: é retido mesmo se a table or tablespace é deletada. ALIAS pode ser criada mesmo se a table não existe.

É usada principalmente em distributed environment para ocultar a localização de informações dos programas.

Alias é um global object e está disponível para todos.

\093) O que significa NOT NULL WITH DEFAULT? Quando poderá ser usado ?

Esta coluna não pode ter nulls na inserção, se nenhum valor é especificado para esta coluna, então é assumido zeroes, spaces ou date/time dependendo da picture da coluna que pode ser numérico, caracter ou date/time.

Use quando você não deseja ter nulls mas ao mesmo tempo não pode dar valores na hora de inserção da linha.

\094) Que significa NOT NULL? Quando poderá ser usado ?

A coluna não pode ter nulls. Use para colunas que fazem parte de uma key.

\095) Quando é preferível o uso do VARCHAR?

Quando a coluna contém long text, ex.: remarks e notes, pode ter mais casos com menos de 50% do tamanho máximo.

\096) Quais são as desvantagens de usar VARCHAR?

\1. Pode levar à utilização de espaço elevado se a maioria dos valores estão muito próximos do máximo.

\2. Posicionamento da coluna VARCHAR tem que ser feito com cuidado, porque tem implicações de desempenho.

\3. Remanejamento de linhas para páginas diferentes pode levar a mais IOs na recuperação.