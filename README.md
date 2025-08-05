# Challenge-TelecomX

# Análise de Evasão de Clientes (Churn) - TelecomX

## Introdução

Este projeto realiza uma análise exploratória profunda dos dados de clientes da TelecomX com o objetivo de identificar os principais fatores que contribuem para a evasão de clientes (Churn). A retenção de clientes é fundamental para o sucesso de empresas de telecomunicações, e a compreensão dos motivos que levam um cliente a cancelar seus serviços é o primeiro passo para a implementação de estratégias de retenção eficazes.

## Dados

O conjunto de dados utilizado para esta análise é proveniente da TelecomX e contém informações detalhadas sobre os clientes, incluindo dados demográficos, serviços utilizados, informações de cobrança e status de Churn.

## Processo de Análise (ETL & EDA)

A análise foi estruturada em fases, seguindo uma abordagem similar a ETL (Extract, Transform, Load) e Análise Exploratória de Dados (EDA):

### Extração (Extract)

Os dados foram extraídos diretamente de uma URL contendo um arquivo JSON.

### Transformação (Transform)

Nesta etapa, os dados brutos foram processados para torná-los adequados para análise:
- Colunas aninhadas ('customer', 'phone', 'internet', 'account') foram normalizadas para criar um DataFrame plano.
- Um DataFrame específico (`df_analise`) foi criado com as colunas relevantes para a análise de churn.
- Linhas com valores vazios na coluna 'Churn' foram removidas.
- A coluna 'Charges.Total' foi convertida para o tipo numérico, tratando valores não numéricos.
- Uma nova coluna, 'Contas_Diárias', foi calculada.

### Carregamento e Análise (Load & Analysis)

Os dados transformados foram preparados para análise e diversas visualizações foram geradas para explorar os padrões de churn:
- **Proporção de Churn**: Um gráfico de pizza foi utilizado para mostrar a distribuição geral de clientes que evadiram vs. clientes ativos.
- **Distribuição de Gastos Totais e Tempo de Contrato**: Boxplots foram gerados para comparar 'Charges.Total' e 'tenure' entre clientes com e sem churn.
- **Proporção de Churn por Variáveis Categóricas**: Gráficos de barras foram criados para analisar a taxa de churn em relação a 'gender', 'Contract' e 'PaymentMethod'.

## Conclusões e Insights

A análise exploratória revelou insights importantes sobre os fatores que influenciam a evasão de clientes:

*   Clientes com **menor tempo de contrato (`tenure`)** apresentam maior probabilidade de evasão.
*   **Contratos de "Month-to-month"** têm uma taxa de churn significativamente maior comparados a contratos de um ou dois anos.
*   O método de pagamento **"Electronic check"** está associado a uma proporção mais alta de churn.
*   Não houve diferença significativa na taxa de churn entre **gêneros**.
*   Clientes que evadem geralmente têm um **gasto total (`Charges.Total`) menor**, o que está alinhado com o menor tempo de contrato.

## Recomendações

Com base nos insights obtidos, as seguintes recomendações são propostas para a TelecomX:

*   Implementar **programas de onboarding aprimorados** para novos clientes, especialmente aqueles com contratos de curto prazo.
*   Oferecer **incentivos para adesão a contratos de longo prazo**.
*   Investigar e melhorar a **experiência do cliente com o método de pagamento "Electronic check"**.
*   Desenvolver um sistema para **monitorar proativamente clientes de risco** (menor tempo de contrato, método de pagamento de maior risco).
*   Incorporar a **análise de sentimento e feedback dos clientes** para identificar outros pontos de insatisfação.

Estas recomendações visam ajudar a TelecomX a reduzir sua taxa de evasão de clientes e aumentar a retenção.
