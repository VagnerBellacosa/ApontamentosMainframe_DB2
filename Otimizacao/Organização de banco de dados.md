[IBM Security Directory Suite](https://www.ibm.com/docs/pt-br/sdsu)[8.0](https://www.ibm.com/docs/pt-br/sdsu/8.0)

[Feedback](mailto:ibmdocs@us.ibm.com?Subject=Feedback to IBM Documentation&body=URL: https%3A%2F%2Fwww.ibm.com%2Fdocs%2Fpt-br%2Fsdsu%2F8.0%3Ftopic%3Ddatabase-organization-reorgchk-reorg)[Lista de produtos](https://www.ibm.com/docs/pt-br/products)

# Organização de banco de dados (**reorgchk** e **reorg**)

Atualizado pela última vez: 2021-03-05

É possível ajustar a organização dos dados em um banco de dados do DB2 para melhorar o desempenho do banco de dados e para economizar espaço em disco.

Para ajustar a organização dos dados no banco de dados do DB2, é possível usar os comandos **reorgchk** e **reorg**. É possível reorganizar espaços de tabelas para melhorar o desempenho de acesso e reorganizar índices para que sejam mais eficientes em cluster.

O comando **reorgchk** faz as operações a seguir:

- Atualiza o otimizador do DB2 com as estatísticas do banco de dados para melhorar o desempenho do banco de dados.
- Reporta estatísticas na organização das tabelas de banco de dados.

Com base nas estatísticas que são geradas pelo comando **reorgchk**, deve-se executar o comando **reorg** para atualizar a organização da tabela de banco de dados. Os comandos **reorgchk** e **reorg** podem melhorar o desempenho das operações de procura e atualização.

O comando **reorg** do DB2 reorganiza a tabela e seus índices, reconstruindo os dados de índice em áreas desfragmentadas e contíguas no disco. Esta operação requer bloquear os dados para movimento. Se houver aplicativos que acessam esses dados, o desempenho do aplicativo poderá ser comprometido. Não se deve executar o comando **reorg** do DB2 enquanto o Directory Server e o banco de dados do DB2 estão em fase de produção. Deve-se executar o comando **reorg** em relação ao Directory Server e o banco de dados do DB2 durante a fase de manutenção.

Depois de concluir a operação de organização de banco de dados, você pode requerer a reinicialização do Directory Server se não observar benefícios de desempenho. Se as instruções SQL forem armazenadas em cache pelo DB2 e instância do Directory Server, você pode requere a limpeza do cache de pacotes e a reinicialização do servidor.

Deve-se executar o comando **reorgchk** periodicamente. Por exemplo, deve-se executar **reorgchk** após atualizar uma instância do Directory Server com entradas. O desempenho do banco de dados deve ser monitorado e deve-se executar **reorgchk** se o desempenho do servidor começar a se comprometer.

Em um ambiente de replicação, deve-se executar o comando **reorgchk** em todos os servidores de réplicas, pois cada réplica usa um banco de dados separado. Se o banco de dados estiver otimizado em um servidor principal, o processo de replicação não propagará otimizações de banco de dados para servidores de réplica.

## Diretrizes para reorganização

Deve-se considerar as seguintes diretrizes antes de executar a reorganização do banco de dados do DB2:

- É possível ignorar a reorganização de uma tabela ou índice se você atender às seguintes condições:

  - Uma tentativa de reorganização já está concluída.
  - O número na coluna que contém um asterisco é próximo do valor sugerido que é descrito no cabeçalho de cada seção.

- No índice LDAP_ENTRY_TRUNC e no índice SYSIBM.SQL na tabela LDAPDB2.LDAP_ENTRY, a preferência deve ser fornecida para o índice SYSIBM.SQL.

- Quando um comprimento de atributo for definido com menos de ou igual a 240 bytes, a tabela de atributos contém três colunas:

   

  EID

  , atributo e atributo invertido. Neste caso, o índice de avanço é criado, usando o

   

  EID

   

  e as colunas de atributo como chaves do índice. Por exemplo, o atributo

   

  SN

   

  é definido com o comprimento máximo, que é menor que ou igual a 240 bytes. A tabela de atributos contém as colunas

   

  EID

  ,

   

  SN

   

  e

   

  RSN

   

  e os índices a seguir são criados para a tabela de atributos:

  ```plaintext-ibm
  LDAPDB2.RSN <------A reverse index whose defined index keys are the EID 
  	and RSN columns. 
  LDAPDB2.SN<------A forward index whose defined index keys are the EID 
  	and SN columns. 
  LDAPDB2.SNI <------An update index whose defined index key is the EID column. 
  ```

  

- Reorganize todas as tabelas de atributos que você deseja usar em procuras. Na maioria dos casos, você pode desejar reorganizar para o índice de avanço. Para procuras que iniciam com * (curinga), reorganize para o índice reverso.

- Quando um comprimento de atributo é definido com comprimento maior que 240 bytes, a tabela de atributos conterá quatro colunas:

   

  EID

  , atributo, atributo truncado e atributo truncado reverso. Neste caso, o índice de avanço é criado usando o

   

  EID

   

  e as colunas de atributo truncado como chaves de índice. Por exemplo, o atributo

   

  CN

   

  é definido com o comprimento máximo, que é menor que 240 bytes. A tabela de atributos contém as colunas

   

  EID

  ,

   

  CN

  ,

   

  CN_T

   

  e

   

  RCN_T

   

  e os índices a seguir são criados para a tabela de atributos:

  ```plaintext-ibm
  LDAPDB2.RCN <------A reverse index whose defined index keys are the EID 
  	and RCN_T columns. 
  LDAPDB2.CN<------A forward index whose defined index keys are the EID 
  	and CN_T columns. 
  LDAPDB2.CNI <------An update index whose defined index key is the EID column.
  ```

  

Uma saída de exemplo com índice reverso, de avanço e de atualização:

```plaintext-ibm
Table: LDAPDB2.SECUUID
LDAPDB2 RSECUUID <— This is a reverse index
LDAPDB2 SECUUIDI <— This is an update index
LDAPDB2 SECUUID <— This is a forward index
```



- **[Executando reorgchk em um banco de dados do DB2](https://www.ibm.com/docs/pt-br/SS3Q78_8.0.0/com.ibm.IBMDS.doc_8.0.0/t_tg_db2_reorgchk.html)**
  É possível recuperar estatísticas do banco de dados e usar os valores para determinar se as tabelas, índices ou ambos devem ser reorganizados.
- **[Executando reorg em um banco de dados DB2](https://www.ibm.com/docs/pt-br/SS3Q78_8.0.0/com.ibm.IBMDS.doc_8.0.0/t_tg_db2_reorg.html)**
  É possível reorganizar os índices em uma tabela, reconstruindo os dados de índice em páginas desfragmentadas, fisicamente contínuas. A reorganização de índices e tabelas reduz o tempo que será necessário para resolver uma consulta e recuperar dados que correspondem ao filtro de consulta.

**Tópico pai:**

[Otimização e organização de banco de dados](https://www.ibm.com/docs/pt-br/SS3Q78_8.0.0/com.ibm.IBMDS.doc_8.0.0/c_tg_db2_optimize_organize.html)



Este tópico foi útil?