[IBM Security Directory Suite](https://www.ibm.com/docs/pt-br/sdsu)[8.0](https://www.ibm.com/docs/pt-br/sdsu/8.0)

[Feedback](mailto:ibmdocs@us.ibm.com?Subject=Feedback to IBM Documentation&body=URL: https%3A%2F%2Fwww.ibm.com%2Fdocs%2Fpt-br%2Fsdsu%2F8.0%3Ftopic%3Ddatabase-optimization)[Lista de produtos](https://www.ibm.com/docs/pt-br/products)

# Otimização

Atualizado pela última vez: 2021-03-05

Deve-se otimizar o banco de dados e atualizar as estatísticas da tabela para melhorar o desempenho da consulta e para reduzir o tempo de recuperação de dados.

Deve-se otimizar o banco de dados periodicamente ou após atualizações de banco de dados. Por exemplo, após importar entradas em uma instância do Directory Server. É possível otimizar o banco de dados usando o comando **idsrunstats** ou a partir do painel **Otimizar banco de dados** da IBM® Security Directory Suite Ferramenta de Configuração. A ferramenta chama internamente o comando **idsrunstats** para atualizar as estatísticas do banco de dados que é usado pelo otimizador de consulta para todas as tabelas LDAP.



**Nota:** Também é possívelusar o comando **reorgchk** para atualizar as estatísticas. Se você estiver planejando executar o **reorgchk**, otimizar o banco de dados é desnecessário. Para obter mais informações sobre o comando **reorgchk**, consulte [Organização de banco de dados (reorgchk e reorg)](https://www.ibm.com/docs/pt-br/SS3Q78_8.0.0/com.ibm.IBMDS.doc_8.0.0/c_tg_db2_organize.html#c_tg_db2_organize).

É possível executar o comando **idsrunstats** para atualizar as estatísticas do catálogo do sistema DB2. As estatísticas incluem as características físicas de tabelas e índices associados no banco de dados de uma instância do Directory Server. As características físicas de uma tabela incluem o número de registros, número de páginas e duração média do registro. Para coletar estatísticas do banco de dados, os seguintes parâmetros **DB2RUNSTATS_ALL_COLUMNS|DB2RUNSTATS_ALL_INDEXES** são transmitidos para a API db2Runstats. É possível executar o comando **idsrunstats** com relação a uma instância do Directory Server mesmo quando a instância está ativa e em execução.

Para otimizar o banco de dados, execute o seguinte comando:

```plaintext-ibm
idsrunstats –I instance_name 
```



A variável instance_name é o nome da instância do Directory Server e é um parâmetro opcional. Se seu computador contiver mais de uma instância, deve-se especificar o nome da instância.

Depois de concluir a otimização, é possível requerer a reinicialização do Directory Server se você não vir benefícios de desempenho após esvaziar o cache de pacotes.

Para saber mais sobre o uso do comando **idsrunstats**, consulte a seção Referência de Comando do [Documentação do IBM Security Directory Suite](http://www.ibm.com/support/knowledgecenter/SS3Q78/welcome).

**Tópico pai:**

[Otimização e organização de banco de dados](https://www.ibm.com/docs/pt-br/SS3Q78_8.0.0/com.ibm.IBMDS.doc_8.0.0/c_tg_db2_optimize_organize.html)