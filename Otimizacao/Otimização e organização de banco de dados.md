[IBM Security Directory Suite](https://www.ibm.com/docs/pt-br/sdsu)[8.0](https://www.ibm.com/docs/pt-br/sdsu/8.0)

[Feedback](mailto:ibmdocs@us.ibm.com?Subject=Feedback to IBM Documentation&body=URL: https%3A%2F%2Fwww.ibm.com%2Fdocs%2Fpt-br%2Fsdsu%2F8.0%3Ftopic%3Dcaches-optimization-organization-database)[Lista de produtos](https://www.ibm.com/docs/pt-br/products)

# Otimização e organização de banco de dados

Atualizado pela última vez: 2021-03-05

É possível otimizar e organizar o banco de dados do DB2 com os comandos do DB2 para reduzir o tempo de acesso a dados e o tempo de recuperação.

O DB2 utiliza um conjunto de algoritmos sofisticados para otimizar o acesso a dados armazenados em um banco de dados. Esses algoritmos dependem de muitos fatores, incluindo a organização dos dados no banco de dados e a distribuição desses dados em cada tabela. O gerenciador de banco de dados mantém um conjunto de estatísticas para representar os dados distribuídos.

Um Directory Server cria vários índices para tabelas no banco de dados. Esses índices minimizam o tempo que é requerido para acessar dados e localizar uma determinada linha em uma tabela.

Em um ambiente somente leitura, a distribuição dos dados não altera muito. Com atualizações e inclusões no banco de dados, não é incomum que a distribuição dos dados seja alterada significativamente. De modo semelhante, é possível que os dados em tabelas sejam ordenados de forma ineficiente.

Para resolver esses problemas, o DB2 fornece ferramentas para otimizar o acesso a dados, atualizando as estatísticas. O DB2 também fornece ferramentas para reorganizar os dados nas tabelas do banco de dados.

- **[Otimização](https://www.ibm.com/docs/pt-br/SS3Q78_8.0.0/com.ibm.IBMDS.doc_8.0.0/c_tg_db2_optimize.html)**
  Deve-se otimizar o banco de dados e atualizar as estatísticas da tabela para melhorar o desempenho da consulta e para reduzir o tempo de recuperação de dados.
- **[Visualizando as configurações das estatísticas do sistema DB2](https://www.ibm.com/docs/pt-br/SS3Q78_8.0.0/com.ibm.IBMDS.doc_8.0.0/t_tg_db2_systen_stat_setting.html)**
  É possível visualizar os relatórios de todas as configurações das estatísticas do sistema em um banco de dados. É possível usar as estatísticas do banco de dados para comparar com qualquer outro banco de dados que possui melhor desempenho e para valores de atualizações com base no uso do banco de dados.
- **[Organização de banco de dados (reorgchk e reorg)](https://www.ibm.com/docs/pt-br/SS3Q78_8.0.0/com.ibm.IBMDS.doc_8.0.0/c_tg_db2_organize.html)**
  É possível ajustar a organização dos dados em um banco de dados do DB2 para melhorar o desempenho do banco de dados e para economizar espaço em disco.

**Tópico pai:**

[Ajuste dos caches DB2 e LDAP](https://www.ibm.com/docs/pt-br/SS3Q78_8.0.0/com.ibm.IBMDS.doc_8.0.0/c_tg_tune_db2_ldap_cache.html)