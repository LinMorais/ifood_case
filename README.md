## Case Técnico iFood
#### Introdução
Este é o projeto para demonstração de análise e modelagem de dados. Como recomendado, o projeto foi gerado utilizando DataBricks, dispensando a criação de um requirements.txt. Neste projeto usamos o Esquema Medalhão de arquitetura de dados.

#### Instruções de Execução
Para executar o projeto, primeiro faça o download do database de referência.

Em seguida, faça o git clone deste projeto, para em seguida importar utilizando o DataBricks, pela aba Workspace. Em seguida, faça o upload das tabelas de referência e na aba de Jobs & Pipelines, crie um novo pipeline para executar o projeto.

###### Clonando o projeto:

`git clone https://github.com/LinMorais/ifood_case.git`

Em seguida, comprima o arquivo como ZIP, para importar pelo DataBricks.

###### No DataBricks:

1. Clique na aba `Workspace` e navegue até a pasta que deseja importar o projeto.
2. Clique com o botão direito do mouse na pasta desejada e selecione a opção `Import`. Selecione o ZIP do projeto para ser importado.
3. Clique na aba `Catalog`, onde deve ser criado um novo catálogo de tipo `Standard` com o mesmo nome do projeto importado.
4. Entre no catálogo criado e clique no botão `New` para fazer o upload da base de dados de referência.
5. Faça o upload das tabelas uma de cada vez, para gerar tabelas diferentes para cada mês. Em `Schema`, crie um esquema de nome `nytaxi`. Em `Table name`, dê o nome 'RawYellowMes' junto do número de cada mês ('yellow_tripdata_2023_01' se torna 'RawYellowMes01'), seguindo o esquema medalhão.
6. Clique na aba `Jobs & Pipelines` e depois no botão `Create` e selecione `ETL Pipeline`.
7. Adicione o root folder e source code path do projeto importado, confirmando com o botão `Add`. Clique no botão `Run pipeline` para executar o projeto.

####  Instruções de Uso
Após executar o projeto, é possível ver as bases de dados geradas utilizando a aba Catalog do DataBricks.
