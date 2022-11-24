
Artigo[Invista em você! Saiba como a DevMedia pode ajudar sua carreira.](https://www.devmedia.com.br/guia-de-sobrevivencia-db2-parte-i/152#modulo-mvp)

# Guia de Sobrevivência DB2 - Parte I

## Você é um interessado, estudante ou profissional do mundo DB2? Então esta série de artigos é para você. Leandro Delamare inicia o Guia de Sobrevivência DB2, com dicas e truques do dia-a-dia.

- SUPORTE AO ALUNO
- ANOTAÇÕES
- FAVORITAR
- CONCLUÍDO
- **4**GOSTEI
- 

- **4**
- 
- 

<iframe class="ad-medium" src="https://www.devmedia.com.br/marketing/banners/banner_160x600/" frameborder="0" style="outline: none; -webkit-tap-highlight-color: transparent; max-width: 100%; margin: auto; display: block; height: 600px;"></iframe>

Por que eu devo ler este artigo: Este é um pequeno guia para realizar operações simples no DB2, podendo ser utilizado tanto por estudantes quanto por profissionais, e no qual apresentaremos funções comuns utilizadas no dia-a-dia.

A idéia deste artigo também é apresentar o DB2, mostrando que embora ainda desconhecido por muitos, este poderoso Banco de Dados não é nenhum “bicho de 7 cabeças”, possuindo muitas características semelhantes a de outros sistemas de bancos de dados como o Oracle, por exemplo.

Este guia foi desenvolvido baseado nas versões 6.x e 7.x do DB2, sendo que muitos dos comandos são totalmente compatíveis com as versões mais novas como 8.x, nas plataformas Windows ou MainFrame.

Ver mais

Suporte ao alunoAnotarMarcar como concluído

[Artigos](https://www.devmedia.com.br/artigos/)[Banco de Dados](https://www.devmedia.com.br/artigos/banco-de-dados)Guia de Sobrevivência DB2 - Parte I

- Criando um Banco de Dados

  Existem várias formas de se criar um Banco de Dados no DB2. Apresentamos aqui uma forma utilizando o “Command Line Processor”. A mesma operação também pode ser feita utilizando o “Command Center”

  No prompt:

  ```
  db2 => create database
  
  db2 => quit
  ```

  Exemplo:

  ```
  create table TabelaClientes ( integer, char(50) , primary key (codigo) )
  ```

- Conectando a um Banco de Dados

  Este é um exemplo de como conectar a um Banco de Dados DB2. Utilizaremos o “DB2 Command Center”

  ```
  db2=> connect to user using
  ```

  Exemplo:

  ```
  connect to SQLMAGAZINE user db2admin using db2senha
  ```

- Exibindo a estrutura de uma Tabela

  Neste exemplo exibiremos a estrutura de uma tabela, ainda empregando o “DB2 Command Center”:

  Primeiramente, conecte-se ao banco de dados como descrito acima e então execute o seguinte comando para exibir a estrutura:

  ```
  db2=> describe table
  ```

  Exemplo:

  ```
  describe table leandro.TabelaClientes
  ```

  Note que a tabela TabelaClientes está sendo referenciada pelo nome do SCHEMA (nome do usuário que a criou)

- Listando as tabelas do seu banco de dados

  Para listar as tabelas do banco de dados, o procedimento é muito simples. Contudo, existem alguns detalhes interessantes sobre o SCHEMA.

  Novamente, é necessário a conexão com o banco de dados como foi mostrado nos exemplos anteriores.

  Conforme vimos neste artigo, uma vez logado no DB2, o SGBD assume o SCHEMA com o seu nome de usuário (no nosso exemplo: “leandro”). Isso afetará a listagem das tabelas conforme veremos a seguir.

  Quando um banco é criado pelo DB2, várias tabelas auxiliares são criadas pelo sistema em outros SCHEMAS. Desta forma, somente as tabelas criadas pelo usuário, ou seja, cujo nome do usuário estiver associado ao SCHEMA, serão aquelas listadas por default.

  ```
  db2=> list tables
  ```

  Para exibir todas as tabelas de outros SCHEMAS, digite:

  ```
  db2=> list tables for all
  ```

  **Nota 1**. Percebe-se então que apesar de existirem tabelas em SCHEMAS diferentes, isso não impede que o usuário tenha acesso a elas.

  **Nota 2**. No Unix, por exemplo, nem sempre existem os ícones dos módulos do DB2, como o “Command Line Editor” ou “Command Center” criado por Default. Com isso, será necessário digitar no terminal o comando para abrir os respectivos módulos.

- Conclusão

  Esperamos ter contribuído para a criação de um guia de operações básicas. Guarde este guia para juntar com os próximos artigos, e mantenha-o sempre à mesa, seja você leitor um DBA ou mesmo um estudante DB2. Até o próximo artigo.