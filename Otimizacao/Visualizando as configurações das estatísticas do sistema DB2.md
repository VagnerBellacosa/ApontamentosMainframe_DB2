[IBM Security Directory Suite](https://www.ibm.com/docs/pt-br/sdsu)[8.0](https://www.ibm.com/docs/pt-br/sdsu/8.0)

[Feedback](mailto:ibmdocs@us.ibm.com?Subject=Feedback to IBM Documentation&body=URL: https%3A%2F%2Fwww.ibm.com%2Fdocs%2Fpt-br%2Fsdsu%2F8.0%3Ftopic%3Ddatabase-viewing-db2-system-statistics-settings)[Lista de produtos](https://www.ibm.com/docs/pt-br/products)

# Visualizando as configurações das estatísticas do sistema DB2

Atualizado pela última vez: 2021-03-05

É possível visualizar os relatórios de todas as configurações das estatísticas do sistema em um banco de dados. É possível usar as estatísticas do banco de dados para comparar com qualquer outro banco de dados que possui melhor desempenho e para valores de atualizações com base no uso do banco de dados.

## Procedimento

1. Efetue login com as credenciais do proprietário da instância de banco de dados.

2. Execute o comando **db2look** com o parâmetro **-m** para produzir um relatório que contém os comandos do DB2 para reproduzir a configurações atuais das estatísticas do sistema.

   ```plaintext-ibm
   db2look -m -d ldapdb2 -u ldapdb2 -o output_file
   ```

   

**Tópico pai:**

[Otimização e organização de banco de dados](https://www.ibm.com/docs/pt-br/SS3Q78_8.0.0/com.ibm.IBMDS.doc_8.0.0/c_tg_db2_optimize_organize.html)