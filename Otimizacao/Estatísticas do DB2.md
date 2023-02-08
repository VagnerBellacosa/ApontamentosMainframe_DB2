[IBM Security Directory Suite](https://www.ibm.com/docs/pt-br/sdsu)[8.0](https://www.ibm.com/docs/pt-br/sdsu/8.0)

[Feedback](mailto:ibmdocs@us.ibm.com?Subject=Feedback to IBM Documentation&body=URL: https%3A%2F%2Fwww.ibm.com%2Fdocs%2Fpt-br%2Fsdsu%2F8.0%3Ftopic%3Droadmap-db2-statistics)[Lista de produtos](https://www.ibm.com/docs/pt-br/products)

# Estatísticas do DB2

Atualizado pela última vez: 2021-03-05

Ao executar operações de atualização em relação a um Directory Server, as estatísticas do DB2 do banco de dados do Directory Server são afetadas. Deve-se atualizar as estatísticas do DB2 do banco de dados do Directory Server depois de grandes atualizações no Directory Server.

Ao atualizar as estatísticas do DB2 de um banco de dados, deve-se parar o Directory Server para evitar quaisquer falhas. É possível atualizar as estatísticas do DB2 enquanto o Directory Server está em execução. No entanto, o aplicativo que está acessando o Directory Server pode atingir o tempo limite.

O otimizador do DB2 usa as estatísticas do sistema DB2 e as definições de tabela volátil para otimizar consultas do DB2. Quando as entradas LDAP são incluídas em um Directory Server, as estatísticas do DB2 nas tabelas afetadas podem se tornar desatualizadas. As estatísticas desatualizadas do sistema podem resultar em opções erradas pelo otimizador do DB2 e em baixo desempenho.

Não atualizar as estatísticas do sistema DB2 é um dos erros de ajuste de desempenho mais comuns feitos com bancos de dados do DB2. A primeira etapa na atualização das estatísticas do sistema DB2 é executar o comando DB2 **runstats** em cada tabela ou executar o comando DB2 **reorgchk**. As versões mais recentes do DB2 fornecem um método para ajustar as verificações automáticas para estatísticas desatualizadas do sistema e atualizá-las usando o comando **runstats**.

Não use a opção automática **runstats** com um Directory Server. Atualizar as estatísticas do sistema DB2 para um Directory Server também envolve a substituição das estatísticas do sistema DB2 padrão pelo comando **runstats**.

Depois de atualizar as estatísticas do sistema DB2, deve-se definir todas as tabelas como voláteis. Também é possível atualizar manualmente as estatísticas do DB2 executando o comando apropriado do DB2.

- Atualize as estatísticas do sistema com DB2 **runstats** ou **reorgchk**

  É possível atualizar as estatísticas do sistema DB2 executando um comando DB2 **runstats** em todas as tabelas no banco de dados ou executando o comando DB2 **reorgchk**. É possível obter a lista de tabelas em um banco de dados executando o seguinte comando:

  `db2 connect to ldapdb2 db2 list tables for all`

  É necessário apenas executar o comando runstats do DB2 nas tabelas que têm o esquema da instância do DB2. Por exemplo, neste documento, o esquema da instância do DB2 é ldapdb2. O comando runstats do DB2 será executado como a seguir:Para o DB2, Versão 10.5.0.3:

  `db2 runstats on table tablename with distribution and detailed indexes all  shrlevel change`

  

  Em que tablename é o nome da tabela na qual executar o comando **runstats**.Se forem oferecidas as opções shrlevel change e allow write access, o banco de dados se tornará acessível para a instância do Directory Server. Quando os comandos **runstats** estão em execução, ele pode resultar em baixo desempenho e tempos limites em operações do Directory Server.Executar o comando **runstats** em todas as tabelas pode ser cansativo se não for automatizado com um script. A alternativa é o comando DB2 **reorgchk**. Para atualizar as estatísticas do DB2, execute o comando DB2 **reorgchk**. Exemplo:

  `db2 connect to ldapdb2 db2 reorgchk update statistics on table all`

  O comando **reogchk** faz algumas verificações e relatórios adicionais na organização dos dados no banco de dados. É útil quando um aplicativo requer a leitura do banco de dados sequencialmente. Ao acessar um Directory Server para utilização comum, o banco de dados é acessado aleatoriamente.A principal vantagem do comando **runstats** do DB2 é a capacidade de selecionar quais tabelas ajustar. Ao executar o comando **runstats** do DB2, deve-se limitá-lo seletivamente para as tabelas que têm menos de 100.000 linhas. Na maioria dos casos, as tabelas com 100.000 linhas não precisam mais de ajuste. Ao limitar o comando **runstats** para as tabelas relativamente pequenas, a frequência para executar o **runstats** diminui. Por exemplo, se um milhão de usuários são incluídos em um Directory Server que já contém um milhão de usuários, é provável que as tabelas afetadas já tenham um milhão de linhas e torna-se desnecessário executar **runstats** nessa tabela.Se o segundo milhão de usuários introduzir um novo atributo LDAP que o primeiro milhão não tinha, será necessário executar **runstats** nas tabelas para os novos atributos. Mas não é necessário que essas tabelas já tenham um milhão de linhas. Em ambos os casos, o tempo para atualizar as estatísticas do sistema utilizando o comando **runstats** é menor do que seria necessário para executar a **runstats** em todas as tabelas do banco de dados de diretório.

- Atualizando estatísticas do sistema com **idsrunstats**

  É possível executar a ferramenta **idrunstats** que é fornecida com o IBM® Security Directory Suite enquanto o Directory Server está em execução. O comando **idsrunstats** coleta as estatísticas de distribuição em todas as colunas e índices das tabelas LDAP_DESC e LDAP_ENTRY.

  Para saber mais sobre **idsrunstats**, consulte [Otimização e organização (idsrunstats, reorgchk e reorg)](https://www.ibm.com/docs/pt-br/SS3Q78_8.0.0/com.ibm.IBMDS.doc_8.0.0/c_tg_db2_optimize_organize.html#c_tg_db2_optimize_organize).

- Melhorar a utilização do disco com a compactação de linhas do DB2

  Se você instalou uma versão totalmente licenciada do DB2 Enterprise Server Edition, além de uma licença do DB2 Storage Optimization Feature, será possível usar a compactação no nível da linha.É possível aprimorar a utilização do disco e o desempenho geral com o recurso de compactação de linhas do DB2. É possível selecionar as linhas que você deseja compactar utilizando a ferramenta **idsdbmaint** que é fornecida com o IBM Security Directory Suite. Para obter mais informações, consulte [DB2 compactação de linha](https://www.ibm.com/docs/pt-br/SS3Q78_8.0.0/com.ibm.IBMDS.doc_8.0.0/c_tg_db2_row_compress.html#c_tg_db2_row_compress).

- Definindo tabelas do DB2 como voláteis

  O DB2, Versão 10.5.0.3 suporta a opção para definir as tabelas como voláteis. Definir as tabelas como voláteis permite que o otimizador do DB2 use os índices que estão definidos na tabela. Se você ajustar o otimizador do DB2, o otimizador do DB2 torna a opção de otimização correta quando as estatísticas estão desatualizadas. Por exemplo, quando uma tabela aumenta de repente de tamanho antes que as estatísticas do sistema sejam atualizadas. Execute o comando a seguir para definir uma tabela como volátil:

  `db2 connect to ldapdb2 db2 alter table tablename volatile`

  Em que tablename é o nome da tabela a ser definida como volátil.

- Substituir estatísticas do sistema

  Em alguns casos, o otimizador do DB2 faz uma escolha errada na otimização de uma consulta, mesmo se as estatísticas do sistema estiverem atualizadas. Em tais casos, é necessário substituir as estatísticas do sistema DB2 para influenciar o otimizador do DB2 a fazer a escolha correta. Um Directory Server pode substituir algumas das estatísticas do sistema. Por exemplo, quando o Directory Server é iniciado como parte do comando **idsrunstats**.É possível configurar a variável de ambiente LDAP_MAXCARD para controlar as substituições das estatísticas do sistema por um Directory Server. Para obter mais informações sobre como configurar LDAP_MAXCARD e seu comportamente, consulte o website http://www-01.ibm.com/support/docview.wss?uid=swg21316267.LDAP_DESCAo configurar a variável, ela configura a coluna de cardinalidade da tabela LDAP_DESC nas tabelas de estatísticas do sistema para um valor de 9E18, que é a notação científica para um número grande. Um Directory Server também pode forçar esta substituição.Para ajustar manualmente, execute o seguinte comando:

  `db2 "update sysstat.tables set card = 9E18 where tabname = 'LDAP_DESC'"`

  Ao substituir, ele escolhe a tabela LDAP_DESC passada durante uma procura LDAP. A tabela LDAP_DESC é usada em procuras de subárvore quando o índice LDAP_DESC(AEID,DEID) está definido.Se o índice LDAP_DESC(AEID,DEID) não estiver definido, esta substituição não entrará em vigor. Esta substituição permite que procuras de pequenas subárvores sejam rápidas se forem especificadas com um filtro objectclass=*. O principal propósito dessa substituição é evitar o uso do índice LDAP_DESC(AEID,DEID) com grandes subárvores. Ele assegura que os atributos no filtro serão utilizados primeiro com uma procura LDAP, se os atributos forem especificados.LDAP_ENTRYPara procuras de nível um, os IDs de entrada são resolvidos utilizando a coluna PEID da tabela LDAP_ENTRY.Ao configurar a variável, ela configura a coluna de cardinalidade da tabela LDAP_ENTRY nas tabelas de estatísticas do sistema para um valor de 9E18, que é a notação científica para um número grande. Um Directory Server não pode forçar esta substituição.Para ajustar manualmente, execute o seguinte comando:

  `db2 "update sysstat.tables set card = 9E18 where tabname = 'LDAP_ENTRY'"`

  Em uma procura LDAP, o índice PEID da tabela LDAP_ENTRY é consultado por último devido à substituição. O índice PEID é utilizado ao executar uma procura de nível um. Ele assegura que os atributos no filtro serão utilizados primeiro com uma procura LDAP, se os atributos forem especificados.CNAo configurar a variável, ela configura a coluna de cardinalidade da tabela CN nas tabelas de estatísticas do sistema com um valor de 9E10. Um Directory Server não pode forçar esta substituição.Para ajustar manualmente, execute o seguinte comando:

  `db2 "update sysstat.tables set card = 9E10 where tabname = 'CN'"`

  A substituição escolhe a tabela CN antes dos critérios da subárvore (tabela LDAP_DESC) e de um critério de nível um (tabela LDAP_ENTRY).Esta substituição também utiliza o filtro OBJECTCLASS antes do atributo CN com uma procura LDAP.REPLCHANGEAo configurar a variável, ela configura a coluna de cardinalidade da tabela REPLCHANGE nas tabelas de estatística do sistema para um valor de 9E18, que é a notação científica para um número grande. Ela também configura as colunas colcard e high2key colunas da tabela REPLCHANGE com o colname de ID na tabela de colunas de estatísticas do sistema para 9E18 e 2147483646. Um Directory Server também pode forçar esta substituição.Para ajustar manualmente, execute os seguintes comandos:

  `db2 "update sysstat.tables set card = 9E18 where tabname = 'REPLCHANGE'" db2 "update sysstat.columns set colcard=9E18, high2key='2147483646' where colname = 'ID' and tabname = 'REPLCHANGE'"`

  O DB2 pode utilizar o índice que está definido na tabela REPLCHANGE quando a substituição está configurada. O otimizador do DB2 não usa índices em uma tabela vazia. Para DB2, Versão 10.5.0.3, se você definir a tabela como volátil, a substituição será redundante.

- comando db2look

  O comando **db2look** é útil para relatórios de todas as configurações das estatísticas do sistema do banco de dados. Use a opção imitativa **-m** para gerar um relatório que contém o comando DB2 que produz as configurações de estatísticas atuais do sistema. Exemplo:
  
  `db2look -m -d ldapdb2 -u ldapdb2 -o output_file`
  
  Em que output_file é o local do arquivo para armazenar os resultados.Antes de executar o comando **db2look**, alterne o contexto do usuário para o proprietário da instância de banco de dados.

**Tópico pai:**

[Roteiro de ajuste do Directory Server](https://www.ibm.com/docs/pt-br/SS3Q78_8.0.0/com.ibm.IBMDS.doc_8.0.0/t_tg_tds_tuning_seq_roadmap.html)