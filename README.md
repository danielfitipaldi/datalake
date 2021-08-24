# datalake
datalake_aws

arquitetura de data lake da aws

A maior parte das tecnologias escolhidas para o desenvolvimento deste data lake foi da AWS, da Amazon. Também foi utilizado o google analytcs, o Salesforce, o databricks e os dados transacionais da Oracle.

O modelo consiste em ter o google analytcs, os dados transacionais da oracle, o salesforce e um arquivo csv conectados ao AWS DataPipeline, serviço da Amazon que é utilizado para automatizar a movimentação e a transformação de dados.

Os dados do google analytcs serão coletados em horário determinado diariamente, assim como os dados específicos dos produtos (os que estão armazenados na pasta receita, que é uma subpasta do detalhamento de cada produto selecionado) que estão sublocados na Oracle. Enquanto isso, a oracle vai alimentar o aws data pipeline também com os dados do histórico de transações dos clientes em tempo real. Por sua vez, o saleforce irá verificar qual a taxa de propensão a churn, ou seja, a cancelamento de compras e, através do Salesforce Einstein, irá fazer uma previsão de compras por parte dos clientes.

Esses dados irão para um arquivo csv, que aqui denominei propensao_churn_previsao_compras.csv.

Do data pipeline, esses dados irão para o armazenamento na poderosa ferramenta da Amazon, o S3( que armazena dados como objetos dentro de buckets) aonde ficarão armazenados em quatro pastas correspondentes.

O Databricks, plataforma do Apache, é uma solução que possui um workspace interativo de Software como Serviço (SaaS) que permite a colaboração entre cientistas e engenheiros de dados e também com os analistas do negócio. Ela foi escolhida para integrar, tratar e consolidar os dados nesta importante etapa.

O nosso banco de dados relacional ficará armazenado no Amazon RDS, pela facilidade de configuração de vários bancos de dados na nuvem, com uma fácil transição e migração até de serviços concorrentes como o SQL Server da Microsoft, mas especialmente pela performance, já que é um serviço redimensionável e que automatiza tarefas administrativas, como backups e aplicação de patches.

Por fim, a ferramenta QuickSight foi a escolhida para a visualização de dados. É um serviço de Business Inteligence que vem crescendo a cada ano e se tornando a solução preferida de muitos engenheiros e cientistas de dados pela grande quantidade de ferramentas à disposição. O quicksight é serveless, ou seja, não possui servidor, e permite a publicação de painéis interativos com os dados de maneira bastante simples. Torna-se interessante para este data lake também oferecer a opção de pagamento por sessão, onde é pago apenas quando os usuários acessam painéis ou relatórios, o que se torna uma boa opção de custo benefício.
