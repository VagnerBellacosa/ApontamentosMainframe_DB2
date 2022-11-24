
Artigo[Invista em você! Saiba como a DevMedia pode ajudar sua carreira.](https://www.devmedia.com.br/conhecendo-a-arquitetura-do-gerenciador-de-dados-db2/26363#modulo-mvp)

# Conhecendo a arquitetura do gerenciador de dados DB2

## Veja neste artigo como está organizada a arquitetura do gerenciador de dados DB2. Serão apresentados os objetos básicos que gerenciam e organizam as bases de dados.

- SUPORTE AO ALUNO
- ANOTAÇÕES
- FAVORITAR
- CONCLUÍDO
- **9**GOSTEI
- 

- **9**
- 
- 

<iframe class="ad-medium" src="https://www.devmedia.com.br/marketing/banners/banner_160x600/" frameborder="0" style="outline: none; -webkit-tap-highlight-color: transparent; max-width: 100%; margin: auto; display: block; height: 600px;"></iframe>

Suporte ao alunoAnotarMarcar como concluído

[Artigos](https://www.devmedia.com.br/artigos/)[Banco de Dados](https://www.devmedia.com.br/artigos/banco-de-dados)Conhecendo a arquitetura do gerenciador de dados DB2

### O que é o DB2

O DB2 é um dos Sistemas de Gestão de Bases de Dados Relacionais (SGDBR) produzido pela linha de Software de Gestão de Informação da IBM. Existem diferentes versões do DB2 que rodam desde num simples PDA, até os mais potentes mainframes, funcionando em servidores baseados em Unix, Windows, Linux e z/OS (sistema operacional para mainframes criado pela IBM).

O DB2 é vendido em diversas distribuições/licenças, com isso a IBM evita que os consumidores paguem por funcionalidades que não iriam usar. Algumas das edições disponíveis são a Express, a Workgroup e a Enterprise. Porém, as mais utilizadas para Linux/Unix/Windows é o DB2 Data Warehouse Enterprise Edition (DB2 DWE). Para o z/OS, o sistema possui algumas características exclusivas: segurança Multi-Level, tabelas de tamanhos extremamente elevados e compressão a nível de hardware. O DB2 sempre foi conhecido pela sua liderança na performance OLTP (Online Transaction Processing ou Processamento de Transações em Tempo Real), sendo usado para suportar missões críticas nas operações de negócios, incorporando nas suas ultimas versões características de Business Intelligence.

Em Janeiro de 2006, a IBM lançou uma versão do DB2 chamada DB2 9 Express-C. Foi esta a resposta da IBM à concorrência, que por essa altura começou a lançar versões gratuitas dos seus SGBDR, nomeadamente o Oracle e o Microsoft SQL Server.

### Estrutura de armazenamento no DB2

O DB2 utiliza uma estrutura chamada de DB2 data structures para organizar/gerenciar base de dados, essa estrutura é constituída por alguns objetos que são usados para manipular esses dados de forma fácil, rápida e eficaz. Alguns exemplos desses objetos como, banco de dados, Tables Spaces, Índices, chaves, entre outros, são descritos e demonstrados na figura abaixo.

![Estrutura de armazenamento de dados no DB2](http://videos.web-03.net/artigos/Rodrigo_Mendes_Dos_Santos/Introducao_DB2/Introducao_DB21.jpg)

**Figura 1:** Estrutura de armazenamento de dados no DB2

**DATABASE**: Objeto utilizado para agrupar outros objetos como, TABLES, INDEX, TABLES SPACES e STORAGE GROUP. Usualmente os DATABASE’s são criados agrupando objetos que tenha algum relacionamento em comum, por exemplo, TABLES, INDEX e STORAGE GROUP de um mesmo sistema ou de um mesmo grupo de sistemas.

**STORAGE GROUP**: É um conjunto de disco que armazenam os dados fisicamente das TABELAS e INDEX do banco de dados.

**TABLES**: No DB2 todos os dados são representados em TABLES que são organizadas em linhas e colunas, todas as linhas contem as mesmas colunas, formando assim uma matriz.

**INDEX**: O INDEX é criado para agilizar pesquisas acessando dados diretamente, é um conjunto ordenado de ponteiros para dados organizados em tabelas do DB2.

**TABLE SPACE**: Espaço reservado em disco que armazena os dados reais das TABLE e INDEX, Apesar de uma TABLE SPACE conseguir agrupar mais de um objeto, por orientação da própria IBM, é uma boa pratica colocar somente um objeto em cada TABLE SPACE.

**VIEW**: A VIEW é uma alternativa de representar dados armazenados em varias tabelas, agrupando somente as colunas e linhas desejadas.

### Sistema de Objetos

O gerenciador de dados DB2 utiliza alguns objetos para gerenciar e garantir a arquitetura dos dados, estes objetos são chamado de DB2 system objects, abaixo uma breve descrição de cada.

**DB2 CATALOG**: O catalogo é conjunto de TABLEs que contêm informações sobre todos os objetos definidos no DB2, tais como INDEX, VIEW, STORAGE GROUP, TABLE. Este conjunto de TABLE é definido no DATABASE DSNDB06, quaisquer inclusão, alteração ou deleção de um objeto, o DB2 atualiza as informações dessas tabelas automaticamente. Por exemplo, quando se cria uma nova TABLE no DB2, as informações de controle dessa nova TABLE são colocados na TABLE do catalogo chamada de SYSIBM.SYSTABLES que armazena informações do tipo, nome da TABLE, DATABASE, TABLE SPACE, OWNER, o criador da TABLE, entre outras informações. Geralmente o catalogo é usado para gerar estatísticas de TABLES, acesso a INDEX, pesquisar relacionamento entre objetos e pesquisar informações sobre privilegio de usuários.

**DB2 DIRECTORY:** O diretório contém informações que o DB2 usa em tempo de execução para realizar suas operações, por exemplo, informações de execução de querys, controle de open/close de TABLEs, informações de execuções de utilitários, controle de atualização de dados, entre outros. O diretório é composto por um conjunto de TABLEs que são armazenadas no DATABASE DSNDB01. Apesar de sua estrutura ser feita de tabelas, o diretório não pode ser acessado via SQL.

**ACTIVE and ARCHIVE LOG**: DB2 registra todas as alterações de dados e outros eventos significativos em logs, caso ocorra um evento de falha o uso dessas logs se faz necessário para recuperação de um banco de dados em um determinado ponto anterior do tempo. A gravação das logs é feita após cada evento realizado no banco e esses dados são gravados na log ativa (ACTIVE LOG), quando esta LOG estiver cheia, o DB2 descarrega esses dados em outro arquivo ou fita magnética que são chamados de ARQUIVE LOG, posteriormente este arquive LOG pode ser usado para possíveis recuperações de bases de dados.

**BOOTSTRAP DATA SET**: O bootstrap data set (BSDS) é um arquivo VSAM key-sequenced data set (KSDS - utilizado por sistemas que são utilizados em arquitetura Mainframe), este arquivo contem informações que são fundamentais para o DB2, como os nomes dos logs, pontos para reinício de processos (CHECKPOINT) e informações sobre buffer pools. O DB2 utiliza as informações do BSDS para reinicialização do sistema ou para qualquer atividade que requer ler o log.

**BUFFER POOL**: Buffer são áreas em memória no qual o DB2 armazena temporariamente páginas de TABLE SPACE ou INDEX. Quando um programa acessa uma linha de uma TABLE, o DB2 recupera a página que contém a linha e coloca em um determinado buffer, se os dados necessários já estão em um buffer, o programa não precisa esperar o DB2 recuperar o dado em disco, de modo que o tempo e custo de recuperar a página são reduzidos. O tamanho máximo de um BUFFER POOL é 1 TB.

**WORK FILE DATABASE**: São áreas de trabalho utilizadas para armazenando dados e executar determinadas tarefas dentro do DB2. Essas áreas são definidas em um DATABASE chamado DSNDB07 que é criado em tempo de instalação do DB2, o aumento de espaço do WORK FILE é feito adicionado novas TABLE SPACE dentro deste DATABASE. Geralmente instruções que realizam sorte e criação de tabelas temporárias utilizam estas áreas.

Resumindo, esses são os principais componentes para o funcionamento do [DB2](http://www.devmedia.com.br/trabalhando-com-o-sgbd-db2-revista-sql-magazine-98-parte-1/24042), o entendimento de cada um é de grande importância para vida de um administrador de dados DB2.

Bom com isso termina mais um artigo, abraços e até a próxima!