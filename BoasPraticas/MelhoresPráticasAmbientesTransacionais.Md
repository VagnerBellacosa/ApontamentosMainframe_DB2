# Melhores Práticas para Ambientes Transacionais

Atualizado pela última vez: 2022-11-28

Os papéis de melhor prática descritos nesta seção fornecem diretrizes e técnicas práticas para ajudá-lo a usar o software Db2® de forma eficiente em ambientes transacionais.

Ambientes de processamento de transações online (OLTP), ou ambientes transacionais, são sistemas de gerenciamento de bancos de dados geralmente projetados para otimizar o processamento de transações curtas e em tempo real em que os dados são alterados constantemente. Embora os cenários descritos nos documentos de melhores práticas referidos nesta seção sejam voltados aos ambientes OLTP, muitos também podem ser aplicados a outros tipos de ambientes.

## Segurança do servidor de dados IBM

A proteção de dados requer uma abordagem holística e em camadas que considere uma ampla variedade de ameaças. Isso é comumente referido como defesa em camada e requer uma abordagem de segurança por design. Esta abordagem adota a segurança como parte do design principal dos ambientes de bancos de dados, as infraestruturas de suporte e as práticas de negócios existentes nesses ambientes. Diversas camadas de segurança trabalham juntas para atender os três objetivos finais de segurança, comumente conhecidos como a tríade CIDconfidencialidade, integridade e disponibilidade.

A IBM compreende as ameaças de segurança de dados e projeta recursos de segurança em suas famílias Db2 e Informix® de servidores de dados. Ambas as famílias de servidores de dados são projetadas com uma ampla variedade de recursos de segurança e auditoria para ajudá-lo a proteger os dados mais críticos.

No papel de melhor prática IBM segurança do servidor de dados , descubra ameaças comuns aos bancos de dados, e aprenda como proteger servidores de dados contra as ameaças comuns de segurança de dados e algumas ameaças incomuns. Além disso, aprenda contramedidas úteis para essas ameaças. Você pode baixar este papel de melhor prática a partir do site IBM® Hybrid Data Management Community: [IBM data server security](https://community.ibm.com/community/user/hybriddatamanagement/viewdocument/ibm-data-server-security?CommunityKey=ea909850-39ea-4ac4-9512-8e2eb37ea09a&tab=librarydocuments&LibraryFolderKey=03d75973-3232-4631-b848-d6fc6743f8ad&DefaultView=folder).

## Proteção de Dados na Nuvem

A computação em nuvem pública é uma tecnologia que usa a Internet e os servidores remotos centrais para hospedar dados e aplicativos. Por meio da computação em nuvem, os consumidores e as empresas podem usar aplicativos sem instalá-los localmente e acessar informações a partir de qualquer computador com acesso à Internet. A computação em nuvem permite uma computação muito mais eficiente usando armazenamento, memória e processamento centralizado. Os benefícios da computação em nuvem são claros, como também a necessidade de desenvolver uma segurança apropriada para implementações em nuvem.

A confiança de Gain sobre segurança de dados na nuvem papel é importante para você se você estiver configurando ou gerenciando bancos de dados em um ambiente de nuvem pública. Os detalhes e as melhores práticas neste documento ajudarão a proteger você e sua organização contra vazamentos e exposições de segurança aplicando uma política padrão de segurança de alta qualidade em todos os bancos de dados hospedados em uma nuvem pública. Você pode baixar este papel de melhor prática do site da Comunidade IBM Hybrid Data Management : [Gain confidence sobre segurança de dados na nuvem](https://community.ibm.com/community/user/hybriddatamanagement/viewdocument/gain-confidence-about-data-security?CommunityKey=ea909850-39ea-4ac4-9512-8e2eb37ea09a&tab=librarydocuments&LibraryFolderKey=03d75973-3232-4631-b848-d6fc6743f8ad&DefaultView=folder) .

## Segurança de Dados: Um Guia Prático para Bancos de Dados Restritivos

Ainda que bancos de dados restritivos forneçam melhor conformidade de segurança pronta para usar do que bancos de dados não restritivos, seu uso foi limitado porque os administradores não sabiam quais privilégios conceder a seus usuários finais para torná-los mais utilizáveis. Por exemplo, os administradores podem não entender porque precisam conceder privilégio EXECUTE em alguns pacotes CLP que, na superfície, não tem nada a ver com a instrução emitida por seus usuários. Esse documento fornece todas as informações necessárias para tornar o uso de bancos de dados restritivos mais efetivos.

Você pode baixar este papel de melhor prática a partir do site da Comunidade IBM Hybrid Data Management : [Um guia prático para bancos de dados restritivos](https://community.ibm.com/community/user/hybriddatamanagement/viewdocument/a-practical-guide-to-restrictive-da?CommunityKey=ea909850-39ea-4ac4-9512-8e2eb37ea09a&tab=librarydocuments&LibraryFolderKey=03d75973-3232-4631-b848-d6fc6743f8ad&DefaultView=folder).

## Segurança de Dados: Um Guia Prático para Implementar o Row and Column Access Control

Esse documento revisa os métodos tradicionais de tratamento de problemas do row and column access control e introduz os novos conceitos de permissão de linha e máscara de coluna como uma alternativa elegante e mais efetiva para os métodos tradicionais.

Obtenha uma introdução às novas dependências de permissão e máscara em Db2 Versão 10, juntamente com funções seguras e acionamentos seguros. Um cenário de uso ilustra como usar permissões de linha e máscaras de coluna para atender aos controles de acesso necessários. O documento Um Guia Prático para Implementar o Row and Column Access Control fornece um conjunto de melhores práticas que devem ser seguidas ao usar permissões de linha e máscaras de coluna.

Você pode baixar este papel de melhor prática a partir do site da Comunidade IBM Hybrid Data Management : [Um guia prático para implementar controle de acesso de linha e coluna](https://community.ibm.com/community/user/hybriddatamanagement/viewdocument/a-practical-guide-to-implementing-r?CommunityKey=ea909850-39ea-4ac4-9512-8e2eb37ea09a&tab=librarydocuments&LibraryFolderKey=03d75973-3232-4631-b848-d6fc6743f8ad&DefaultView=folder).

## Armazenamento do Banco de Dados

Descubra as melhores práticas para armazenamento do banco de dados, incluindo diretrizes e recomendações para discos físicos e números de unidades lógicas (LUNs), faixa e striping, logs e dados de transações, sistemas de arquivos versus dispositivos brutos, dispositivos Redundant Array of Independent Disks (RAID), variável de registro e definições de parâmetros de configuração e armazenamento automático.

Você pode baixar este papel de melhor prática a partir do site da Comunidade IBM Hybrid Data Management : [Melhores práticas para armazenamento de banco de dados](https://community.ibm.com/community/user/hybriddatamanagement/viewdocument/best-practices-for-database-storage?CommunityKey=ea909850-39ea-4ac4-9512-8e2eb37ea09a&tab=librarydocuments&LibraryFolderKey=03d75973-3232-4631-b848-d6fc6743f8ad&DefaultView=folder).

## Bancos de dados Db2 e o IBM General Parallel File System

Reduza os custos de gerenciamento, inclua flexibilidade e simplifique o gerenciamento de armazenamento usando o software IBM General Parallel File System (GPFS). O software GPFS é uma solução de gerenciamento de arquivos de disco compartilhado de alto desempenho que fornece acesso rápido e confiável a um conjunto comum de dados de arquivo. Os dados podem ser compartilhados entre dois computadores ou várias centenas de sistemas. Um sistema de arquivos GPFS reúne servidor misto e componentes de armazenamento para fornecer uma visão comum dos dados do arquivo corporativo. Os sistemas de arquivos GPFS e os bancos de dados Db2 criam uma plataforma poderosa para seus sistemas de banco de dados de alto desempenho.

Use os bancos de dados Db2 e o papel IBM General Parallel File System para aprender sobre os benefícios estratégicos do software GPFS e as melhores práticas para implementá-lo com o software Db2 . Você pode baixar este papel de melhor prática a partir do site da Comunidade IBM Hybrid Data Management : [Db2 bancos de dados e o IBM General Parallel File System](https://community.ibm.com/community/user/hybriddatamanagement/viewdocument/db2-databases-and-the-ibm-general-p?CommunityKey=ea909850-39ea-4ac4-9512-8e2eb37ea09a&tab=librarydocuments&LibraryFolderKey=03d75973-3232-4631-b848-d6fc6743f8ad&DefaultView=folder).

## Análise de desempenho detalhada com o InfoSphere Optim Performance Manager V5.3

Este webcast Db2 fornece um tutorial aprofundado para ajudá-lo a usar IBM InfoSphere Optim Performance Manager V5.3 (OPM) para diagnosticar, analisar e corrigir potenciais problemas de desempenho com os seus sistemas Db2 . O webcast também fornece uma visão geral dos novos recursos incluídos no OPM V5.3.

Você pode visualizar este webcast a partir do site IBM Hybrid Data Management Community: [Análise de desempenho de mergulho profundo com InfoSphere Optim Performance Manager V5.3](https://community.ibm.com/community/user/hybriddatamanagement/viewdocument/db2bp-performance-analysis-opm-v53?CommunityKey=ea909850-39ea-4ac4-9512-8e2eb37ea09a&tab=librarydocuments&LibraryFolderKey=f938e3c7-d8ec-4ed6-826a-c1f6e80b9610&DefaultView=folder).

## Implementação de IBM Db2 Express-C com PHP em Ubuntu Linux

Combinando o poder do software IBM Db2 Express-C com o servidor HTTP Apache e a linguagem de programação PHP em um sistema rodando o sistema operacional Ubuntu Linux® , fornece uma plataforma de desenvolvimento de aplicativos poderosa, flexível e confiável. Esta plataforma é ideal para pequenas empresas, desenvolvedores, instrutores e estudantes porque os componentes de software são gratuitos para download e uso.

O Implementar IBM Db2 Exexpress-C com PHP no Ubuntu Linux best practice paper fornece uma abordagem passo-a-passo para instalar e configurar tal sistema. Depois de concluir as etapas neste paper, você terá um servidor de aplicações web PHP em funcionamento que utiliza o software Db2 Express-C como servidor de dados back-end. Você pode baixar este papel de melhor prática do site da Comunidade IBM Hybrid Data Management : [Implementando IBM Db2 Express-C com o PHP em Ubuntu Linux](https://community.ibm.com/community/user/hybriddatamanagement/viewdocument/deploying-ibm-db2-express-c-with-ph?CommunityKey=ea909850-39ea-4ac4-9512-8e2eb37ea09a&tab=librarydocuments&LibraryFolderKey=03d75973-3232-4631-b848-d6fc6743f8ad&DefaultView=folder).

## Implementação do Optim Gerente de Desempenho em ambientes de grande escala

Geralmente, os ambientes de grande escala possuem considerações especiais em relação ao gerenciamento de desempenho. Em tais ambientes, é muito importante ter uma abordagem abrangente e proativa no gerenciamento de desempenho. IBM InfoSphere® Optim™ Performance Manager oferece tal abordagem.

Use o paper Deploying Optim Performance Manager em ambientes de grande escala para aprender sobre melhores práticas para implementar o software InfoSphere Optim Performance Manager Extended Edition em ambientes de grande escala. Você pode baixar este papel de melhor prática a partir do site da Comunidade IBM Hybrid Data Management : [Implementando o Optim Performance Manager em ambientes de grande escala](https://community.ibm.com/community/user/hybriddatamanagement/viewdocument/deploying-optim-performance-manager?CommunityKey=ea909850-39ea-4ac4-9512-8e2eb37ea09a&tab=librarydocuments&LibraryFolderKey=03d75973-3232-4631-b848-d6fc6743f8ad&DefaultView=folder).

## DB2 High Availability Disaster Recovery

Use o papel Db2 high availability disaster recovery para aprender sobre as melhores práticas para configuração e manutenção de um ambiente de recuperação de desastre de alta disponibilidade (HADR) do Db2 em formas que equiliam a proteção que o HADR proporciona com desempenho e custo. Este documento de melhor prática explica a otimização para failovers rápidos, parâmetros de ajustes para desempenho de rede e criação de logs e compreensão dos métodos de reorganização de tabelas e operações de carregamento em um ambiente HADR.

Você pode baixar este papel de melhor prática do site da Comunidade IBM Hybrid Data Management : [Db2 recuperação de desastres de alta disponibilidade](https://community.ibm.com/community/user/hybriddatamanagement/viewdocument/db2-high-availability-disaster-reco?CommunityKey=ea909850-39ea-4ac4-9512-8e2eb37ea09a&tab=librarydocuments&LibraryFolderKey=03d75973-3232-4631-b848-d6fc6743f8ad&DefaultView=folder).

## Gerenciando Crescimento de Dados

Devido às necessidades de negócios para retenção de dados e conformidade regulamentar, as empresas precisam gerenciar bancos de dados cada vez maiores que variam de centenas de gigabytes a muitos terabytes, ou mesmo petabytes, em tamanho. Como os dados continuam a crescer numa taxa exponencial, os profissionais de DBAs e TI dessas organizações enfrentam desafios profissionais desanimadores ao projetarem e operarem bancos de dados grandes assim. Os dados devem ser bem organizados para efetivamente acompanharem o crescimento dos dados e para atenderem aos requisitos do serviço. Este documento comunica as melhores práticas para o gerenciamento do crescimento de dados usando o rico conjunto de recursos no software IBM Db2 .

Você pode baixar este papel de melhor prática a partir do site da Comunidade IBM Hybrid Data Management : [Managing data growth](https://community.ibm.com/community/user/hybriddatamanagement/viewdocument/managing-data-growth?CommunityKey=ea909850-39ea-4ac4-9512-8e2eb37ea09a&tab=librarydocuments&LibraryFolderKey=03d75973-3232-4631-b848-d6fc6743f8ad&DefaultView=folder).

## Gerenciamento Dados XML

Use o papel Managing XML data para aprender sobre princípios e diretrizes para usar o software Db2 pureXML ® Feature para resolver problemas de negócios de forma eficaz e para obter alto desempenho ao gerenciar dados XML em aplicativos corporativos. Os exemplos que ilustram as melhores práticas têm como base um cenário de aplicativo financeiro do mundo real e demonstra como implementar as diretrizes. É possível adaptar facilmente os exemplos a outros tipos de aplicativos XML. Você pode baixar este papel de melhor prática a partir do site da Comunidade IBM Hybrid Data Management : [Gerenciando dados XML](https://community.ibm.com/community/user/hybriddatamanagement/viewdocument/managing-xml-data?CommunityKey=ea909850-39ea-4ac4-9512-8e2eb37ea09a&tab=librarydocuments&LibraryFolderKey=03d75973-3232-4631-b848-d6fc6743f8ad&DefaultView=folder).

## Otimização de cargas de trabalho analíticas usando o Db2 10.5 com o BLU Acceleration

O BLU Acceleration é uma nova coleção de tecnologias para consultas analíticas, introduzidas no Db2 Versão 10.5. Essencialmente, o BLU Acceleration deve fornecer respostas mais rápidas para mais perguntas e analisar mais dados com um menor custo. O Db2 com o BLU Acceleration fornece benefícios incríveis no desempenho, na economia de armazenamento e no time to value.

Esse documento fornece uma visão geral dessas tecnologias, recomendações sobre seleção de hardware e software, diretrizes para identificação das cargas de trabalho ideais para o BLU Acceleration e informações sobre planejamento de capacidade, memória e E/S.

Uma seção sobre a configuração do sistema mostra como o foco da IBM na simplicidade permite que você configure o Db2 para que ele faça automaticamente escolhas de configuração ideais para cargas de trabalho analíticas. Outras seções descrevem como implementar e usar o Db2 com o BLU Acceleration. Ao contrário de outras melhores práticas que mostram várias opções, este documento se concentra em como o BLU Acceleration funciona e o que ele não pode mostrar. Isso realmente lhe dará uma visão da simplicidade construída no BLU Acceleration e mostrará como ele realmente entrega uma “Super Analítica, Super Fácil”.

Você pode fazer o download do Otimizando as cargas de trabalho analíticas usando Db2 10,5 com BLU Acceleration papel de melhor prática do site da Comunidade IBM Hybrid Data Management : [Otimizando cargas de trabalho analíticas usando Db2 10,5 com BLU Acceleration](https://community.ibm.com/community/user/hybriddatamanagement/viewdocument/optimizing-analytics-workloads-usin?CommunityKey=ea909850-39ea-4ac4-9512-8e2eb37ea09a&tab=librarydocuments&LibraryFolderKey=03d75973-3232-4631-b848-d6fc6743f8ad&DefaultView=folder).

## Design do banco de dados físico para ambientes OLTP

O design de banco de dados físico pode ser o único fator mais importante que afeta o desempenho do banco de dados. O design do banco de dados físico abrange todos os aspectos de design relacionados à estrutura física do banco de dados. Esses aspectos incluem a seleção do tipo de dados, normalização e desnormalização de tabelas, índices, visualizações materializadas, armazenamento de dados em cluster, armazenamento de dados multidimensionais em cluster, particionamento de tabelas (intervalos) e particionamento de bancos de dados (hash). Um bom design de banco de dados físico reduz a utilização de recursos de hardware (utilização de E/S, CPU e rede) e melhora sua eficiência administrativa.

Você pode fazer o download do Design de banco de dados de Física para ambientes OLTP de melhor prática a partir do site da Comunidade IBM Hybrid Data Management :[Design de banco de dados físico para ambientes OLTP](https://community.ibm.com/community/user/hybriddatamanagement/viewdocument/physical-database-design-for-online?CommunityKey=ea909850-39ea-4ac4-9512-8e2eb37ea09a&tab=librarydocuments&LibraryFolderKey=03d75973-3232-4631-b848-d6fc6743f8ad&DefaultView=folder).

## Instalação e desinstalação silenciosas do Db2 V10

Este documento aborda os Parceiros de Negócios IBM e os clientes que planejam uma integração completa do software Db2 em suas soluções. Integração completa significa que nenhum administrador de banco de dados está envolvido e que toda a administração é feita programaticamente. Este documento descreve os processos de instalação e de desinstalação silenciosas do Db2, de atualizações silenciosas de fix pack do Db2 e de upgrades silenciosos para versões e liberações mais recentes do Db2. É possível utilizar instalação e desinstalação silenciosas do Db2 para instalar e desinstalar produtos ou componentes do Db2 sem qualquer interação com o usuário. A instalação silenciosa é útil para implementações de grande escala de edições do produto Db2. Como um Parceiro de Negócios IBM ou um cliente IBM, também é possível usar a instalação ou a desinstalação silenciosa para integrar os processos de instalação e de desinstalação do Db2 nos procedimentos para suas soluções. Além de explicar e de fornecer as melhores práticas para os processos de instalação e de desinstalação silenciosas do Db2, de atualizações silenciosas de fix pack e de upgrades silenciosos de versões e de liberações, este documento também inclui cenários práticos para ilustrar a instalação e a desinstalação silenciosas simples e complexas de um produto Db2.

Você pode baixar este papel de melhor prática a partir do site da Comunidade IBM Hybrid Data Management : [Db2 V10 instalação silenciosa e desinstalação](https://community.ibm.com/community/user/hybriddatamanagement/viewdocument/db2-v101-silent-installation-and-u?CommunityKey=ea909850-39ea-4ac4-9512-8e2eb37ea09a&tab=librarydocuments&LibraryFolderKey=03d75973-3232-4631-b848-d6fc6743f8ad&DefaultView=folder).

## Otimização do Armazenamento com Compactação Completa

Este paper comunica as melhores práticas para o uso do Recurso de Otimização de Armazenamento Db2 com o produto Db2 . Você pode usar o Recurso de Otimização de Armazenamento Db2 para aplicar a compactação em vários tipos de dados e dados temporários persistentemente armazenados.

Você pode baixar este papel de melhor prática a partir do site da Comunidade IBM Hybrid Data Management : [otimização de armazenamento com compressão profunda](https://community.ibm.com/community/user/hybriddatamanagement/viewdocument/storage-optimization-with-deep-comp?CommunityKey=ea909850-39ea-4ac4-9512-8e2eb37ea09a&tab=librarydocuments&LibraryFolderKey=03d75973-3232-4631-b848-d6fc6743f8ad&DefaultView=folder).

## Gerenciamento de dados temporais com Db2 V10

Os recursos temporais no produto IBM Db2 Versão 10 fornecem funcionalidades ricas para gerenciamento de dados baseado em tempo. Por exemplo, é possível optar por registrar o histórico completo de mudanças de dados de uma tabela de banco de dados para que seja possível "voltar no tempo" e consultar qualquer estado anterior dos dados. Também é possível indicar a validade de negócios de dados designando um par de valores de data ou de registro de data e hora para uma linha para indicar quando as informações são consideradas válidas no mundo real. Usando a sintaxe SQL nova e padronizada, é possível inserir, atualizar, excluir e consultar facilmente dados no passado, no presente ou no futuro.

Você pode baixar este papel de melhor prática a partir do site da Comunidade IBM Hybrid Data Management : [Gerenciamento de dados temporais com Db2 V10](https://community.ibm.com/community/user/hybriddatamanagement/viewdocument/temporal-data-management-with-db2?CommunityKey=ea909850-39ea-4ac4-9512-8e2eb37ea09a&tab=librarydocuments&LibraryFolderKey=03d75973-3232-4631-b848-d6fc6743f8ad&DefaultView=folder).

## Resolução de problemas de servidores Db2

Mesmo em um mundo perfeitamente engendrado, as coisas podem quebrar. O hardware que não é redundante pode falhar, ou software pode encontrar uma condição que requer intervenção. É possível automatizar parte dessa intervenção. Por exemplo, você pode ativar o seu servidor Db2 para coletar automaticamente dados de diagnóstico quando ele encontrar um problema significativo. No entanto, uma pessoa deve verificar os dados para diagnosticar e resolver o problema. Quando a necessidade surge, você pode usar várias ferramentas de solução de problemas Db2 que fornecem acesso altamente granular a dados de diagnóstico. As informações e cenários neste paper mostram como você pode usar as ferramentas de solução de problemas Db2 para diagnosticar problemas em seu servidor.

Em ambientes de banco de dados grandes, a coleção de dados de diagnóstico pode causar um impacto indesejado no sistema. Este documento mostra como é possível minimizar esse impacto customizando os valores de alguns parâmetros básicos de configuração de resolução de problemas, como diagpath, DUMPDIR e FODCPATH e coletando dados mais seletivamente. O resultado? Quando as coisas realmente quebrarem, você estará bem preparado para resolver os problemas o mais rápido e fácil possível.

Os cenários de resolução de problemas do Db2 a seguir são cobertos neste documento:

- Resolução de problemas de alto aumento de uso do processador
- Resolução de problemas de estouros de classificação
- Resolução de problemas de bloqueio

Para cada cenário, este documento mostra como identificar os sintomas do problema, como coletar os dados de diagnóstico com impacto mínimo para seu ambiente de banco de dados e como diagnosticar a causa do problema.

Você pode baixar este papel de melhor prática a partir do site da Comunidade IBM Hybrid Data Management : [Troubleshooting Db2 servers](https://community.ibm.com/community/user/hybriddatamanagement/viewdocument/troubleshooting-db2-servers?CommunityKey=ea909850-39ea-4ac4-9512-8e2eb37ea09a&tab=librarydocuments&LibraryFolderKey=03d75973-3232-4631-b848-d6fc6743f8ad&DefaultView=folder).

## Ajustando e Monitorando o Desempenho do Sistema de Banco de Dados

A maioria dos sistemas Db2 passa por algum tipo de uma evolução de desempenho. Primeiro você deve configurar o software e o hardware do sistema. Em muitas formas, a configuração define o sistema temporário para verificar como o sistema se comportará quando ele estiver em operação. Em seguida, após implementar o sistema, é importante monitorar o desempenho do sistema para detectar quaisquer problemas que possam surgir. Se tais problemas surgirem, você atinge a próxima fase: resolução de problemas. Cada fase atual depende das fases anteriores, por isso, sem a preparação correta nas fases anteriores, é mais provável que você tenha problemas difíceis para solucionar na fase atual.

Use o papel Ajuste e monitorando o desempenho do sistema de banco de dados para aprender sobre as melhores práticas para a evolução do desempenho de um servidor de dados Db2 . Os tópicos abrangem, desde importantes princípios de configuração inicial de hardware e de software até técnicas de monitoramento que ajudam a compreender o desempenho do sistema sob as condições operacional e resolução de problemas. Este documento fornece uma abordagem metódica passo a passo para a resolução de um problema de desempenho. Você pode baixar este papel de melhor prática a partir do site da Comunidade IBM Hybrid Data Management : [Ajuste e monitorando o desempenho do sistema de banco de dados](https://community.ibm.com/community/user/hybriddatamanagement/viewdocument/tuning-and-monitoring-database-syst-1?CommunityKey=ea909850-39ea-4ac4-9512-8e2eb37ea09a&tab=librarydocuments&LibraryFolderKey=03d75973-3232-4631-b848-d6fc6743f8ad&DefaultView=folder).

## Integrando o IBM PureData System for Transactions em uma rede de datacenter

O IBM PureData System for Transactions é um sistema habilmente integrado para ajudar a implementar bancos de dados otimizados e essenciais continuamente disponíveis. Este documento cobre os requisitos de rede para integrar o PureData System for Transactions em um ambiente de datacenter e fornece topologias de rede de amostra populares. Usando as interfaces gráficas no sistema, é possível configurar facilmente as comutações de rede para integrar a uma rede corporativa.

Você pode fazer o download do Integrando IBM PureData System for Transactions em um papel de boas práticas de rede de dados a partir do site da Comunidade IBM Hybrid Data Management : [Integrando IBM PureData System for Transactions em uma rede de data center](https://community.ibm.com/community/user/hybriddatamanagement/viewdocument/integrating-ibm-puredata-system-for?CommunityKey=ea909850-39ea-4ac4-9512-8e2eb37ea09a&tab=librarydocuments&LibraryFolderKey=03d75973-3232-4631-b848-d6fc6743f8ad&DefaultView=folder).

**Tópico Pai:**

[Db2 melhores práticas](https://www.ibm.com/docs/pt-br/SSEPGG_11.1.0/com.ibm.db2.luw.common.doc/doc/c0060073.html)

## Informações relacionadas

- [Práticas comprovadas de Business analytics](http://www.ibm.com/developerworks/analytics/practices.html)