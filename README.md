<h1 align="center"> ETL Zap Moveis</h1>

ETL com dataset da empresa ZapMoveis utilizando Azure DataLake Gen 1 e Databricks

<h2>Nesse projeto, utilizei as seguintes tecnologias:</h2>
<ul>
    <li>Azure Data lake Gen 1</li>
    <li>Azure Databricks</li>
    <li>Delta Lake</li>
    <li>Scala</li>
</ul>

<h2>Steps do projeto:</h2>
<ol>
    <li>Criei um application registration, que vai servir para permitir que o cluster databricks tenha permissão de leitura e escrita nos arquivos do azure data lake</li>
    <li>Subi um Azure DataLake Gen1</li>
    <li>Montei a arquitetura do DataLake (com 4 camadas):</li>
          <ul>
            <li>inbound: Camada do meu datalake que vai armazenar os arquivos no seu formato original (JSON) e sem fazer transformações</li>
            <li>bronze: Camada do meu datalake que vai armazenar os arquivos em um formato otimizado, mas também não vai fazer transformações</li>
            <li>silver: Camada do meu datalake que vai ler os dados da camada bronze e vai fazer transformações e limpezas</li>
            <li>Gold: Camada do meu datalake onde os dados estão prontos para anális ou treinamentos</li>
          </ul>
</ol>

Nas camadas bronze, silver e gold trabalhei com delta tables com o objetivo de aproveitar da poderosa ferramenta Delta Lake do databricks.

<ul>
    <li>Storage de Dados compatível com Apache Spark (desenvolvida pelo databricks) projetada para lidar com grandes volumes de dados e fornecer funcionalidades avançadas para processamento de dados em big data.</li>
    <li>Trás as principais caracteristicas de um data warehouse (Transações ACID, Consistência, Isolamento, Durabilidade...)</li>
</ul>

Uma boa representação da arquitetura:
![image](https://github.com/andrebastosdata/zap-moveis-etl/assets/173493147/f533aa5d-c929-45bb-af72-95fa733f1065)
