[WebSphere Application Server Network Deployment](https://www.ibm.com/docs/pt-br/was-nd)[8.5.5](https://www.ibm.com/docs/pt-br/was-nd/8.5.5)

[Feedback](mailto:ibmdocs@us.ibm.com?Subject=Feedback to IBM Documentation&body=URL: https%3A%2F%2Fwww.ibm.com%2Fdocs%2Fpt-br%2Fwas-nd%2F8.5.5%3Ftopic%3Dtuning-db2-parameters)[Lista de produtos](https://www.ibm.com/docs/pt-br/products)

![[AIX Solaris HP-UX Linux Windows]](https://www.ibm.com/docs/pt-br/SSAW57_8.5.5/com.ibm.websphere.nd.multiplatform.doc/images/dist.gif)![[z/OS]](https://www.ibm.com/docs/pt-br/SSAW57_8.5.5/com.ibm.websphere.nd.multiplatform.doc/images/ngzos.gif)

# Parâmetros de Ajuste do DB2

Atualizado pela última vez: 2021-10-14

Leia este tópico para obter os parâmetros que podem ser configurados para melhor desempenho do banco de dados.

Para obter informações completas sobre ajustes do DB2, consulte o documento Guia de Administração do DB2 UDB: Desempenho.

![[AIX]](https://www.ibm.com/docs/pt-br/SSAW57_8.5.5/com.ibm.websphere.nd.multiplatform.doc/images/aixlogo.gif)Para obter informações adicionais sobre como usar o AIX com o DB2, consulte o tópico Ajustando Sistemas AIX.

## Criação de Log do DB2

O DB2 tem os arquivos de log correspondentes para cada banco de dados que fornece serviços para administradores, incluindo visualização de acesso ao banco de dados e do número de conexões. Para sistemas com várias unidades de disco rígido, é possível obter grandes ganhos de desempenho configurando os arquivos de log para cada banco de dados em uma unidade de disco rígido diferente dos arquivos do banco de dados.

- Como visualizar ou configurar: Em um prompt de comandos do DB2, emita o comando: `db2 update db cfg for [database_name] using newlogpath [fully_qualified_path]`.
- Valor padrão: Os logs residem no mesmo disco que o banco de dados.
- Valor recomendado: Use uma unidade de alta velocidade separada, preferivelmente com desempenho aprimorado por meio de uma configuração de Redundant Array of Independent Disks (RAID).

## Orientador de Configuração do DB2

Localizado no Centro de Controle doDB2, este orientador calcula e exibe os valores recomendados para o tamanho do conjunto de buffers, o banco de dados e os parâmetros de configuração do gerenciador de banco de dados DB2, com a opção de aplicação desses valores. Consulte informações adicionais sobre o orientador no recurso de ajuda on-line no Centro de Controle.

## Número de conexões ao DB2 - MaxAppls e MaxAgents

Ao configurar as configurações de origem de dados para os bancos de dados, confirme que a configuração de MaxAppls do DB2 é maior do que o número máximo de conexões para a origem de dados. Se você estiver planejando estabelecer clones, defina o valor de MaxAppls como o número máximo de conexões multiplicado pelo número de clones. A mesma relação se aplica ao número de conexões do gerenciador de sessão. A definição de MaxAppls deve ser maior que ou igual ao número de conexões. Se você estiver utilizando o mesmo banco de dados para sessão e origens de dados, defina o valor de MaxAppls como a soma do número de definições de conexões para o gerenciador de sessão e as origens de dados.

Por exemplo, MaxAppls = (número de conexões definidas para a origem de dados + número de conexões no gerenciador de sessão) multiplicado pelo número de clones.

Depois de calcular as configurações de MaxAppls para o banco de dados do WebSphere Application Server e cada bancos de dados do aplicativo, verifique se a configuração de MaxAgents para o DB2 é igual ou maior à soma de todos os valores de MaxAppls. Por exemplo, MaxAgents = soma de MaxAppls para todos os bancos de dados.

## Buffpage do DB2

Melhora o desempenho do sistema de banco de dados. Buffpage é um parâmetro de configuração de banco de dados. Um conjunto de buffers é uma área de armazenamento de memória onde as páginas do banco de dados que contêm linhas da tabela ou as entradas de índices são temporariamente lidas e mudadas. Os dados são acessados muito mais rapidamente da memória que do disco.

- Como visualizar ou configurar: para visualizar o valor atual de buffpage para o banco de dados

   

  ```
  x
  ```

  , emita o comando de DB2

   

  ```
  getdb cfg for x
  ```

   

  e procure pelo valor

   

  ```
  BUFFPAGE
  ```

  . Para configurar

   

  ```
  BUFFPAGE
  ```

   

  com um valor igual a

   

  ```
  n
  ```

  ,emita o comando do DB2

   

  ```
  update db cfg for x
  ```

   

  usando

   

  ```
  BUFFPAGE n 
  ```

  econfigure

   

  ```
  NPAGES
  ```

   

  como -1, conforme a seguir:

  ```
  db2   <-- acesse o modo do comando do  DB2, caso contrário, “select” a seguir não funcionará no estado em que se encontra
      connect to x    <-- (em que x é o nome do banco de dados DB2 específico) 
      select * from syscat.bufferpools 
         (e anote o nome do padrão, talvez: IBMDEFAULTBP)
         (se NPAGES já for -1, não há necessidade de emitir o comando a seguir) 
      alter bufferpool IBMDEFAULTBP size -1
      (emita novamente o “select” acima e NPAGES agora igual a -1)
  ```

  É possível coletar um instantâneo do banco de dados enquanto o aplicativo está em execução e calcular a proporção de acertos do conjunto de buffers da seguinte maneira:

  1. Colete o instantâneo:
     1. Emita o comando update monitor switches using bufferpool on.
     2. Certifique-se de que o monitoramento do buffer pool esteja ativo emitindo o comando get monitor switches.
     3. Limpe o comando monitor counters with the reset monitor all.
  2. Execute o aplicativo.
  3. Emita o comando get snapshot for all databases antes de todos os aplicativos se desconectarem do banco de dados, caso contrário, as estatísticas serão perdidas.
  4. Emita o comando update monitor switches using bufferpool off.
  5. Calcule a proporção de acertos, examinando as seguintes estatísticas no instantâneo do banco de dados:
     - Leituras lógicas de dados do conjunto de buffers
     - Leituras físicas de dados do conjunto de buffers
     - Leituras lógicas de índices do conjunto de buffers
     - Leituras físicas do índice do conjunto de buffers

- Valor padrão: 250

- Valor recomendado: Continue aumentando o valor até a captura instantânea mostrar uma taxa de ocorrência satisfatória.

A proporção de acertos do conjunto de buffers indica a porcentagem de tempo que o gerenciador de banco de dados não precisou carregar uma página do disco para servir um pedido de página. Ou seja, a página já está no conjunto de buffers. Quanto mais alta a taxa de acerto do conjunto de buffers, mais baixa a freqüência de entrada e saída do disco. Calcule a proporção de acertos do conjunto de buffers da seguinte maneira:

- P = leituras físicas de dados do conjunto de buffers + leituras físicas de índices do conjunto de buffers
- L = leituras lógicas de dados do conjunto de buffers + leituras lógicas de índices do conjunto de buffers
- Proporção de acerto = (1-(P/L)) * 100%

## Nível de Otimização de Consulta do DB2

Configura a quantidade de trabalho e recursos que o DB2 utiliza para otimizar o plano de acesso. quando uma consulta de banco de dados é executada noDB2, vários métodos são utilizados para calcular o plano de acesso mais eficiente. O intervalo é de 0 a 9. Um nível de otimização de 9 faz com que o DB2 dedique muito tempo e todas as suas estatísticas disponíveis para otimizar o plano de acesso.

- Como visualizar ou configurar: O nível de otimização é configurado em bancos de dados individuais e pode ser configurado com a linha de comandos ou com o centro de controle do DB2. As instruções SQL estáticas utilizam o nível de otimização que é especificado nos comandos

   

  ```
  prep
  ```

   

  e

   

  ```
  bind
  ```

  . Se o nível de otimização não for especificado, o DB2 utilizará a otimização padrão conforme especificada pela configuração dft_queryopt. As instruções SQL dinâmicas utilizam a classe de otimização que é especificada pelo registro especial de otimização de consulta atual, o qual é definido utilizando a instrução Set de SQL. Por exemplo, a instrução a seguir define a classe de otimização como 1:

  ```
  Definir otimização da consulta atual = 1
  ```

  Se o registro de otimização de consulta atual não for definido, as instruções dinâmicas serão ligadas utilizando a classe de otimização de consulta padrão.

- Valor padrão: 5

- Valor recomendado: Configure o nível de otimização para as necessidades do aplicativo. Utilize níveis altos somente quando houver consultas muito complicadas.

## Rorgchk do DB2

Obtém as estatísticas atuais para dados de religação. Utilize este parâmetro porque o desempenho de instruções SQL pode deteriorar após muitas atualizações, exclusões ou inserções.

- Como visualizar ou configurar: Use o comando do DB2 reorgchk update statistics on table all para executar a operação `runstats` em todas as tabelas de usuário e de sistema para o banco de dados ao qual você está conectado atualmente. Religue os pacotes utilizando o comando `bind`. Se as estatísticas estiverem disponíveis, emita o comando db2 -v “select tbname, nleaf, nlevels, stats_time from sysibm.sysindexes” no CLP do DB2. Se não existir nenhuma atualização de estatística, nleaf e nlevels serão -1, e stats_time terá uma entrada vazia (por exemplo: “-”). Se o comando runstats foi executado anteriormente, o time stamp real da conclusão da operação runstats também é exibido sob stats_time. Se você achar que a hora mostrada para a operação runstats anterior é muito antiga, execute o comando runstats novamente.
- Valor padrão: None
- Valor recomendado: None

## Locktimeout do DB2

Especifica o número de segundos que um aplicativo aguarda para obter um bloqueio. A configuração desta propriedade ajuda a evitar conflitos globais para aplicativos.

- Como visualizar ou configurar: Para visualizar o valor atual da propriedade de tempo limite do bloqueio para o banco de dados `xxxxxx`, emita o comando DB2 `get db cfg for xxxxxx` e procure o valor, LOCKTIMEOUT. Para configurar LOCKTIMEOUT com um valor igual a `n`, emita o comando do DB2 `update db cfg for xxxxxx` usando `LOCKTIMEOUT n`, em que `xxxxxx` é o nome do banco de dados do aplicativo e `n` é um valor entre 0 e 30 000, inclusive.
- Valor padrão: -1, significando que a detecção de tempo limite do bloqueio está desativada. Nesta situação, um aplicativo aguarda por uma trava, se uma não estiver disponível no momento do pedido, até que um dos seguintes eventos ocorra:
  - A trava é concedida
  - Ocorre um conflito
- Valor recomendado: Se seu padrão de acesso ao banco de dados tender em direção à maioria das gravações, configure este valor para que ele forneça aviso antecipado quando um tempo limite ocorrer. Uma configuração de 30 segundos é adequada para esse fim. Se o padrão de acesso tender a uma maioria de leituras, aceite o valor padrão do tempo limite de trava ou defina a propriedade como um valor maior que 30 segundos.

## Maxlocks do DB2

Especifica o percentual da lista de bloqueios que é alcançado quando o gerenciador de banco de dados executa a escalação, de linha a tabela, para os bloqueios mantidos pelo aplicativo. Embora o processo de escalada não leve muito tempo, travar tabelas inteiras em comparação com as linhas individuais, diminui a simultaneidade e potencialmente diminui o desempenho global do banco de dados para tentativas subseqüentes de acessar as tabelas afetadas.

- Como visualizar ou configurar: Para visualizar o valor atual da propriedade maxlocks para o banco de dados `xxxxxx`, emita o comando do DB2 `get db cfg for xxxxxx` e procure o valor MAXLOCKS. Para configurar MAXLOCKS com um valor igual a `n`, emita o comando do DB2 `update db cfg for xxxxxx` usando `MAXLOCKS n`, em que `xxxxxx` é o nome do banco de dados do aplicativo e `n` é um valor entre 1 e 100, inclusive.
- Valor padrão: Consulte as informações do banco de dados atuais para obter os valores padrão por sistema operacional.
- Valor recomendado: Se escalações de bloqueios estiverem causando preocupações relacionadas ao desempenho, poderá ser necessário aumentar o valor deste parâmetro ou do parâmetro locklist, que está descrito no parágrafo a seguir. É possível utilizar o monitor do sistema de banco de dados para determinar se estão ocorrendo escaladas de trava.

## Locklist do DB2

Especifica a quantidade de armazenamento que é alocada na lista de bloqueios.

- Como visualizar ou configurar: Para visualizar o valor atual da propriedade locklist para o banco de dados `xxxxxx`, emita o comando do DB2 `get db cfg for xxxxxx` e procure o valor LOCKLIST. Para configurar LOCKLIST com um valor igual a `n`, emita o comando do DB2 `update db cfg for xxxxxx` usando `LOCKLIST n`, em que `xxxxxx` é o nome do banco de dados do aplicativo e `n` é um valor entre 4 e 60 000, inclusive.
- Valor padrão: Consulte as informações do banco de dados atuais para obter os valores padrão por sistema operacional.
- Valor recomendado: Se escalações de bloqueios estiverem causando preocupações relacionadas ao desempenho, poderá ser necessário aumentar o valor deste parâmetro ou do parâmetro maxlocks, que está descrito no parágrafo anterior. É possível utilizar o monitor do sistema de banco de dados para determinar se estão ocorrendo escaladas de trava. Consulte o documento Guia de Administração do DB2: Desempenho para obter detalhes adicionais.

## Tarefas relacionadas

- [Ajustando o Ambiente de Serviço do Aplicativo](https://www.ibm.com/docs/pt-br/SSAW57_8.5.5/com.ibm.websphere.nd.multiplatform.doc/ae/tprf_tuneprf.html)

## Informações relacionadas

- [Documentação DB2](https://www.ibm.com/support/knowledgecenter/SSEPGG)



Este tópico foi útil?