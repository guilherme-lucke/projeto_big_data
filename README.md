# Desenvolvimento e Avaliação de uma Arquitetura Distribuída para o Cadastro Ambiental Rural

## Descrição do Projeto
Este projeto tem como objetivo explorar as capacidades de arquiteturas de bancos de dados distribuídos para lidar com conjuntos de dados grandes, especificamente o Cadastro Ambiental Rural (CAR). A arquitetura proposta utiliza Databricks e Amazon S3 para armazenar, processar e analisar os dados de maneira eficiente.

## Estrutura do Repositório
- `notebooks/`
    - `projeto_big_data`: Notebook principal contendo todas as etapas de configuração, processamento e consultas.
- `README.md`: Este arquivo, com a descrição do projeto, instruções de configuração e uso.

## Tecnologias Utilizadas
- Databricks: Para processamento e análise distribuída dos dados utilizando Apache Spark.
- Amazon S3: Para armazenamento dos dados brutos e processados.
- Python: Para scripting e processamento de dados.
- PySpark: Interface do Apache Spark para Python.
- Boto3: Biblioteca para interação com serviços AWS.

## Pré-requisitos

- Conta AWS com permissões para usar S3.
- Databricks Workspace configurado.
- Python 3.x instalado.
- Bibliotecas `boto3` e `requests` instaladas.
- Credenciais AWS configuradas no Databricks ou localmente.

## Configuração

### 1. Clonar o Repositório
```bash
git clone https://github.com/seu_usuario/car-databricks-aws.git
cd car-databricks-aws
```
### 2. Configurar Credenciais AWS
No Databricks, você pode configurar as credenciais AWS na seção de configurações ou usar variáveis de ambiente.
```python
aws_access_key_id = 'YOUR_AWS_ACCESS_KEY_ID'
aws_secret_access_key = 'YOUR_AWS_SECRET_ACCESS_KEY'
```
### 3. Configurar Databricks
Importe o notebook disponível na pasta notebooks para o seu workspace do Databricks.

## Execução
### 1. Executar o Notebook no Databricks
Abra o notebook notebooks/CadastroAmbientalRural.ipynb no Databricks e siga as instruções para executar cada célula. O notebook está dividido em várias seções:
1. Configuração Inicial
2. Baixar e Carregar o Arquivo no S3
3. Configuração da Sessão Spark
4. Leitura e Processamento dos Dados
5. Limpeza dos Dados
6. Particionamento dos Dados
7. Salvando os Dados no Formato Parquet no S3
8. Realização de Consultas
### 2. Resultados Esperados
- O arquivo temas_ambientais.csv será baixado e carregado no bucket S3 especificado.
- Os dados serão lidos, processados e limpos utilizando Spark.
- O DataFrame processado será salvo em formato Parquet no S3.
- Consultas diversas serão realizadas no DataFrame, mostrando insights valiosos sobre os dados do CAR.

## Consultas Realizadas
**Consulta 1:** Soma da área para MS e MT, ordenada em ordem decrescente.
**Consulta 2:** Filtro para propriedades na região sudeste.
**Consulta 3:** Contagem de propriedades cadastradas por ano, ordenadas cronologicamente.
**Consulta 4:** Percentual médio de área remanescente de vegetação nativa.
**Consulta 5:** Contagem de propriedades rurais por estado.
**Consulta 6:** Média de área por propriedade e contagem de propriedades acima da média por estado.