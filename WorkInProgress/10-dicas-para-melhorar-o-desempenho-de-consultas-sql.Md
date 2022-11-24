<iframe id="wp-custom-header-video" frameborder="0" allowfullscreen="1" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" title="YouTube video player" width="1920" height="800" src="https://cdn.hu-manity.co/empty.html" sandbox="allow-same-origin allow-scripts allow-forms allow-popups allow-popups-to-escape-sandbox" data-hu-category="2" data-src="https://www.youtube.com/embed/3iXYciBTQ0c?autoplay=1&amp;controls=0&amp;disablekb=1&amp;fs=0&amp;iv_load_policy=3&amp;loop=1&amp;modestbranding=1&amp;playsinline=1&amp;rel=0&amp;showinfo=0&amp;enablejsapi=1&amp;origin=https%3A%2F%2Fwww.blogadvpl.com&amp;widgetid=1" class="hu-blocked" style="box-sizing: border-box; margin: 0px; padding: 0px; border: 0px; font-size: 17px; vertical-align: baseline; object-fit: cover; position: absolute; opacity: 0; width: 1349px; transition: opacity 0.4s cubic-bezier(0.44, 0.94, 0.25, 0.34) 0s;"></iframe>

Content blocked. Click Unblock to set your consent level for this website and view the content.

Unblock

# 10 DICAS PARA MELHORAR O DESEMPENHO DE CONSULTAS SQL

Blog Advpl - Share knowledge

## 10 dicas para melhorar o desempenho de consultas SQL

![sql](https://i0.wp.com/blogadvpl.com/wp-content/uploads/2015/12/sql.png?resize=720%2C300)Melhora o desempenho da consulta SQL é um tema muito instigante entre desenvolvedores e da comunidade de usuários. Usuários sempre querem uma resposta rápida sobre a sua ação de recuperação de dados e desenvolvedores de colocar diante de seus melhores esforços para fornecer os dados no menor tempo possível, no entanto, não há nenhuma maneira simples de definir o que é o melhor desempenho. 

Você pode escolher várias maneiras de melhorar o desempenho de consulta SQL, que cai sob diversas categorias como reescrever a consulta SQL, criação e utilização de índices, manejo adequado de estatísticas, etc.

1. **Evite várias associações em uma única consulta**

Tente evitar escrever uma consulta SQL usando várias associações que inclui associações externas, aplicar cruzamentos, sub consultas complexas e outros. Em algum momento, o otimizador é forçado a usar loop aninhado, independentemente das consequências de desempenho para consultas com excessivos cruzamentos complexos ou sub consultas.

1. **Eliminar cursores a partir da consulta**

Tente remover cursores da consulta e usar consulta baseada em conjunto; consulta baseada em conjunto é mais eficiente do que à base de cursor. Se existe uma necessidade de utilizar cursor de evitar cursores dinâmicos uma vez que tende a limitar a escolha de plantas disponíveis para o otimizador de consulta. Por exemplo, cursor dinâmico limita o otimizador para usar loop aninhado.

1. **Evitar o uso de** **sub consultas**

Você pode reescrever sua consulta para remover uma sub consulta não correlacionados como uma consulta separada, em vez de parte da consulta principal e armazenar a saída em uma variável, que pode ser referido na consulta principal ou parte posterior do lote. Isto lhe dará melhores opções para otimizar.

1. **Criação e uso de índices**

Estamos conscientes do fato de que Index pode magicamente reduzir o tempo de recuperação de dados, mas tem um efeito inverso sobre as operações DML, o que pode degradar o desempenho da consulta. Com este fato, indexação é uma tarefa desafiadora, mas pode ajudar a melhorar o desempenho da consulta SQL e dar-lhe melhor tempo de resposta de consulta.

1. **Compreender a dados**

Compreender os dados de suas consultas permite tomar qualquer decisão de criar um índice. Se você entender o comportamento dos dados completamente, ele irá ajudá-lo a decidir qual coluna deve ter tanto um índice de cluster ou índice não agrupado. Se um índice de cluster não está em uma coluna exclusiva, em seguida, SQL Server irá manter a exclusividade pela adição de um identificador único para cada chave duplicada, o que leva à sobrecarga. Para evitar este tipo de sobrecarga escolha a coluna corretamente ou fazer as alterações apropriadas.

1. **Criar um índice altamente seletivo**

A seletividade define o percentual de linhas de qualificação na tabela (número de linhas de qualificação / número total de linhas). Se a razão entre o número de qualificação de linhas ao número total de linhas é baixo, o índice é altamente seletivo e é mais útil. Um índice não agrupado é mais útil se a proporção é de cerca de 5% ou menos, o que significa que se pode eliminar o índice de 95% das linhas de consideração. Se o índice está retornando mais de 5% das linhas em uma tabela, ele provavelmente não vai ser usado.

1. **Posicione uma coluna em um índice**

A ordem ou a posição de uma coluna em um índice também desempenha um papel vital para melhorar o desempenho da consulta SQL. Um índice pode ajudar a melhorar o desempenho de consulta SQL. Como uma prática recomendada, colunas mais seletivas devem ser colocadas mais à esquerda na chave de um índice não agrupado.

1. **Eliminar** **índices não utilizados**

Eliminar índices não utilizados podem ajudar a acelerar a modificações de dados sem afetar a recuperação de dados. Além disso, é necessário definir uma estratégia para processos em lote que são executados com pouca frequência e utilizam determinados índices. Em tais casos, a criação de índices com antecedência de processos descontínuos e, em seguida, soltando-os quando os processos descontínuos são feitas ajuda a reduzir a sobrecarga sobre a base de dados.

1. **Criação de Estatística e Atualizações**

Você precisa cuidar da criação de estatística e atualizações regulares para colunas computadas e multi-colunas referidas na consulta; o otimizador de consulta usa informações sobre a distribuição dos valores em uma ou mais colunas de uma tabela de estatísticas para estimar a cardinalidade, ou número de linhas, no resultado da consulta. Estas estimativas de cardinalidade permitir que o otimizador de consulta crie um plano de consulta de alta qualidade.

1. **Revisitar suas definições de esquema**

Por último, mas não menos importante, rever suas definições de esquema; ficar de olho que CHAVE FORIGEN apropriado, NOT NULL e restrições CHECK estão no lugar ou não. Disponibilidade da restrição à direita no lugar certo sempre ajuda a melhorar o desempenho da consulta, como FORIGEN KEY restrição ajuda a simplificar.

1. **Fontes**

http://msdn.microsoft.com/en-us/library/ff647793.aspx
http://msdn.microsoft.com/en-us/library/ff650689.aspx
http://technet.microsoft.com/en-us/library/ms172984.aspx