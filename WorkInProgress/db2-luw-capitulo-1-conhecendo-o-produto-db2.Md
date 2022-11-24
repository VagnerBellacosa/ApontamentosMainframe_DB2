# [DB2 LUW] CAPÍTULO 1 – CONHECENDO O PRODUTO DB2

Postado por [Colaborador](http://certificacaobd.com.br/author/colaborador/) | set 3, 2013 | [DB2](http://certificacaobd.com.br/category/geral/certificacoes/db2-2/), [DB2](http://certificacaobd.com.br/category/geral/dbarea/db2-dbarea/) | [6 ](http://certificacaobd.com.br/2013/09/03/db2-luw-capitulo-1-conhecendo-o-produto-db2/#comments) |   

![[DB2 LUW] Capítulo 1 – Conhecendo o produto DB2](http://certificacaobd.com.br/wp-content/uploads/2012/05/db2_dest.png)

[![db2](http://certificacaobd.com.br/wp-content/uploads/2013/09/db2.png)](http://certificacaobd.com.br/wp-content/uploads/2013/09/db2.png)



 

Olá pessoal!

Apenas explicando sobre esse post e os demais que virão, essa série de artigos tem intuito de mostrar pra vocês um pouco mais sobre o DB2 LUW. A ideia é começar desde a instalação, criação de uma instância, banco de dados, tipos de tablespaces, estratégias de backup e restore, conceitos de log, HADR e etc.

No capítulo 1 vou mostrar um pouco de cada distribuição do DB2, como licenciar um DB2, verificar o ciclo de vida de suporte e etc.

## **1)**  **ENTENDENDO O TIPO DE DISTRIBUIÇÃO**

Basicamente o DB2 se divide em 5 distribuições: Express-c, Express, Workgroup, Enterprise Server e Advanced Enterprise Server.

 

 

[![DB2Versions](http://certificacaobd.com.br/wp-content/uploads/2013/09/DB2Versions.png)](http://certificacaobd.com.br/wp-content/uploads/2013/09/DB2Versions.png)

 

 

 

 

 

 

**O DB2 10.5.0 Express-c** é a versão gratuita. Ele te limita em 4 GB de RAM e em 2 processadores. O interessante é que mesmo a versão gratuita do DB2 não tem limite de tamanho das bases de dados, além de você poder aproveitar de algumas features interessantes como as manutenções automáticas, como reorg, runstats, backup automático e etc.

**O DB2 Express** é a versão paga de entrada do DB2. Ele te limita em 8 GB de RAM e 4 processadores. Tem todas as features da versão anterior, e o mais interessante é o suporte IBM para o produto, o suporte para o HADR (High Availability Disaster Recovery) e o TSA. Operações de reorg online agora são possíveis além de compressão de backup e serviços de replicação.

“Subindo” um pouco temos **o** **DB2 Workgroup**. Uma versão que suporta 64 GB de RAM e 16 processadores. O mais interessante é que a partir dessa versão já temos como utilizar o Pure Scale. O Pure Scale te garante escalabilidade e crescimento horizontal, podendo acrescentar uma vasta gama de servidores ao seu cluster. Vale lembrar que se você instalar um cluster Pure Scale em uma versão Workgroup, seu cluster fica limitado a 64 GB de RAM e 16 processadores, ou seja, se você tiver um cluster com 8 servidores, cada servidor terá 8 GB de memória e 2 processadores.

As versões “top de linha” são **a Enterprise e Advanced Enterprise Server** que não te limitam em memória nem processador.

Abaixo uma ilustração do “cluster” Pure Scale:

 

[![purescale](http://certificacaobd.com.br/wp-content/uploads/2013/09/purescale.jpg)](http://certificacaobd.com.br/wp-content/uploads/2013/09/purescale.jpg)

 

 

 

 

 

 

Abaixo segue um link interessante sobre as distribuições do DB2:

[http://www.ibm.com/developerworks/data/library/techarticle/dm-1204whicheditiondb2/](https://www.ibm.com/developerworks/data/library/techarticle/dm-1204whicheditiondb2/)

 

## **2)**  **LICENCIANDO O PRODUTO**

Depois de conhecer as distribuições do DB2, precisamos saber qual o tipo de licenciamento que cada “distro” suporta.

**Express-c:** Versão gratuita do DB2 e não precisa ser licenciada.

**Express:**

-  **Processor Unit License Valor (PVU):** Licenciamento por processador.
- **Authorized User Single Install License (AUSI):**  Licenciamento por usuário.
- **Fixed Term Server License (FTL):**  Licenciamento por locação de um ano.
- **Perpetual Server License (SERVER):**  Licenciamento perpétuo do DB2.

 

**Workgroup:**

- **Processor Unit License Valor (PVU):** Licenciamento por processador.
- **Authorized User Single Install License (AUSI):**  Licenciamento por usuário.
- **Socket:**  Licenciamento por “pastilha”.

 

**Enterprise e Advanced Enterprise:**

- **Processor Unit License Valor (PVU):** Licenciamento por processador.
- **Authorized User Single Install License (AUSI):**  Licenciamento por usuário.

 

## **3)**  **EDIÇÕES DO PRODUTO**

Pessoal, abaixo vou colocar uma figura interessante que retirei do site da IBM que mostra as edições dos produtos com seus respectivos fix pack’s.

[![fixpacks](http://certificacaobd.com.br/wp-content/uploads/2013/09/fixpacks.png)](http://certificacaobd.com.br/wp-content/uploads/2013/09/fixpacks.png)

 

 

## **4)**  **O CICLO DE VIDA DO SUPORTE**

 

Para você saber qual a data limite de suporte de um produto de DB2, basta acessar o link: [http://www-01.ibm.com/software/support/lifecycleapp/PLCSearch.wss?q=DB2&scope=F523070D12499J17-I645032G36539U31-K317640T42411B13-O610988L12375W12-W703098F12306M33-X105958Q73400Q82&ibm-search.x=14&ibm-search.y=17&ibm-search=Search&sort=P](https://www-01.ibm.com/software/support/lifecycleapp/PLCSearch.wss?q=DB2&scope=F523070D12499J17-I645032G36539U31-K317640T42411B13-O610988L12375W12-W703098F12306M33-X105958Q73400Q82&ibm-search.x=14&ibm-search.y=17&ibm-search=Search&sort=P)

Acessando o link acima você consegue fazer uma busca do produto, veja abaixo:

 

[![lifecycle](http://certificacaobd.com.br/wp-content/uploads/2013/09/lifecycle.png)](http://certificacaobd.com.br/wp-content/uploads/2013/09/lifecycle.png)

 

[![db2suport](http://certificacaobd.com.br/wp-content/uploads/2013/09/db2suport.png)](http://certificacaobd.com.br/wp-content/uploads/2013/09/db2suport.png)

 