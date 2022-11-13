#### Desafio de Projeto - Explorando Dados Demográficos com Serviços de Big Data na AWS

Projeto da live coding sobre as ferramentas da AWS realizado pelo Cassiano Brexbit.

Bootcamp Geração Tech Unimed-BH Ciência de Dados da [DiO](https://www.dio.me) - vamos explorar a ferramenta [Amazon Athena](https://aws.amazon.com/pt/athena/?whats-new-cards.sort-by=item.additionalFields.postDateTime&whats-new-cards.sort-order=desc) utilizada em big data totalmente gerenciada na AWS, realizando consultas e análise de dados no [Amazon S3](https://aws.amazon.com/pt/s3/) usando SQL padrão.

#### Criar bucket no Amazon S3

- Amazon S3 console -> buckets -> create bucket -> bucket name [nome_do bucket] - create bucket
- Create folder (criar uma pasta chamada `/output` e outra com o nome do seu conjunto de dados, cujo nome irá definir o nome da tabela criada no glue)
- Upload dos arquivos de dados localizados na pasta `/data`

#### Criar glue crawler

- Amazon glue console -> crawlers -> add crawler
- Source type [data stores] -> crawl all folders
- Data store [S3] -> include path [caminho do diretório dos dados de entrada]
- Create IAM role
- Frequency [run on demand]
- Database name [seu_nome_de_db]
- Group behavior [create a single schema for each S3 path]
- Finish
- Databases -> tables -> visualizar dados das tabelas criadas

#### Criar aplicação no Amazon Athena

- Query editor -> settings -> manage settings -> query result location and encryption -> browse S3 -> selecionar o bucket  criado
- Selecionar database -> criar queries (exemplos na pasta `/src`)
- Verificar queries não salvas no bucket criado no S3
- Salavar queries -> executar novamente -> verificar no bucket criado no S3

#### Criar nova tabela

- Generate table DDL
- Copiar a query gerada
- Selecionar o DB e criar a nova tabela em uma nova query

#### Visualizar dados no Amazon QuickSight

- Signup (caso não tenha conta) -> escolher [standard]
- Datasets -> create new dataset -> athena -> name [nome do dataset] -> create
- Select database -> select table -> edit or preview -> save & visualize
- Criar visualizações selecionando colunas, criando filtros e parâmetros e selecionando visual types para gráficos.

#### Eliminar recursos

- Excluir os elementos criados

#### Serviços utilizados nessa atividade prática

- [Amazon S3](https://aws.amazon.com/pt/s3/) 
- [Amazon Glue](https://aws.amazon.com/pt/glue/)
- [Amazon Athena](https://aws.amazon.com/pt/athena/?whats-new-cards.sort-by=item.additionalFields.postDateTime&whats-new-cards.sort-order=desc) 
- [Amazon QuickSight](https://aws.amazon.com/quicksight/)