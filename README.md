## Case Técnico iFood

#### Introdução
Este é o projeto para demonstração de análise e modelagem de dados. Como recomendado, o projeto foi gerado utilizando DataBricks, dispensando a criação de um requirements.txt. 
Neste projeto foi usada a arquitetura de dados medalhão e desenvolvidos scripts de validação para análise exploratória, consistência e acurácia dos dados disponibilizados para consumo final. Foram aplicados conceitos de CTE e windows functions no SQL e exibição gráfica com pyspark.

#### Instruções de Execução:
Para executar o projeto, primeiro faça o download do database de referência.

Em seguida, faça o git clone deste projeto, para em seguida importar utilizando o DataBricks, pela aba Workspace. Em seguida, faça o upload das tabelas de referência e na aba de Jobs & Pipelines, crie um novo pipeline para executar o projeto.

###### Clonando o projeto:

`git clone https://github.com/LinMorais/ifood_case.git`

Em seguida, comprima o arquivo como ZIP, para importar pelo DataBricks.

###### No DataBricks:

1. Clique na aba `Workspace` e navegue até a pasta que deseja importar o projeto.
2. Clique com o botão direito do mouse na pasta desejada e selecione a opção `Import`. Selecione o ZIP do projeto para ser importado.
3. Clique na aba `Catalog`, onde deve ser criado um novo catálogo de tipo `Standard` com o mesmo nome do projeto importado (`ifood_case`).
4. Entre no catálogo criado e clique no botão `New` para fazer o upload da base de dados de referência.
5. Faça o upload das tabelas, uma de cada vez e uma para cada mês. Em `Schema`, crie um esquema de nome `nytaxi`. Em `Table name`, dê o nome 'RawYellowMes' junto do número de cada mês ('yellow_tripdata_2023_01' se torna 'RawYellowMes01'), e assim sucessivamente.
6. Clique na aba `Jobs & Pipelines` e depois no botão `Create` e selecione `ETL Pipeline`.
7. Adicione o root folder e source code path do projeto importado, confirmando com o botão `Add`. Clique no botão `Run pipeline` para executar o projeto.

###### Análise exploratória:

Validações realizadas sobre campos da tabela original:
1. improvement_surcharge   ->   taxa de melhoria deve ser positiva e obrigatória;
2. mta_tax                 ->   imposto MTA deve ser positivo e obrigatória;
3. passenger_count         ->   ao menos 1 passageiro quando há cobranças;
4. payment_type            ->   são 6 os tipos válidos e verificados;
5. PULocationID/DOLocationID  -> locais de embraque/desembarque diferentes;
6. store_and_fwd_flag      ->   se os dados são armazenados no carro ou transmitidos a um servidor remoto;
7. total_amount            ->    valor do pagamento total positivo;
8. total_amount            ->   verifica se o total pago é igual a soma das taxas;
9. trip_distance           ->   distância percorrida positiva;
10. vendorid               ->   somente vendors permitidos;

Validações de consistência com campos criados ao longo do processo:
1. Duracao_Viagem          ->   duração precisa ser maior do que zero indicando que houve deslocamento;
2. Hora_Inicio_Viagem      ->   valida intervalo de horas do inicio da viagem;
3. Hora_Fim_Viagem         ->   valida intervalo de horas do fim da viagem;
4. Dia_Inicio_Viagem       ->   valida intervalo de dias do mês do inicio da viagem;
5. Dia_Fim_Viagem          ->   valida intervalo de dias do mês do fim da viagem;

Além de outras validações inseridas na lógica dos scripts.

####  Instruções de Uso
Após executar o projeto, é possível ver as bases de dados geradas utilizando a aba Catalog do DataBricks.
