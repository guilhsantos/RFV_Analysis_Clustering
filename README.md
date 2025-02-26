# Análise de Métricas RFV

## Descrição do Projeto

Este projeto tem como objetivo realizar uma análise detalhada das métricas RFV (Recência, Frequência e Valor) para segmentação de clientes e compreensão de seus padrões de compra. A abordagem utiliza técnicas de análise exploratória, limpeza de dados e clusterização para identificar grupos de clientes com comportamentos semelhantes.

## Dataset Utilizado

O dataset contém informações transacionais de clientes de um e-commerce, incluindo:

- Customer_ID: Identificação única do cliente.

- Invoice_Date: Data da compra.

- Invoice_No: Número da fatura.

- Quantity: Quantidade de itens comprados.

- Unit_Price: Preço unitário do item.

- Total_Sales: Valor total da compra (Quantity * Unit_Price).

## Passos Realizados

### 1. Análise Exploratória dos Dados

- Carregamento do dataset com a biblioteca Pandas.

- Verificação de valores nulos e tratamento dos dados ausentes.

- Análise estatística descritiva das transações.

- Visualização da distribuição das compras ao longo do tempo.

### 2. Cálculo das Métricas RFV

- Recência (R): Tempo desde a última compra de cada cliente.

- Frequência (F): Quantidade de compras realizadas pelo cliente.

- Valor Monetário (V): Valor total gasto pelo cliente.

- Normalização das métricas para padronização dos dados.

### 3. Clusterização de Clientes

- Utilização do algoritmo K-Means para segmentação.

- Definição do número ideal de clusters através do método do cotovelo.

- Análise dos perfis dos clientes em cada cluster.

### 4. Interpretação dos Resultados

Identificação dos segmentos de clientes, como:

- Clientes VIP: Alta frequência e alto valor gasto.

- Clientes regulares: Compras frequentes com valores moderados.

- Clientes inativos: Longo período sem compras.

- Visualização dos clusters através de gráficos de dispersão.

### Tecnologias Utilizadas

- Python

- Pandas e NumPy para manipulação dos dados

- Matplotlib e Seaborn para visualizações

- Scikit-Learn para modelagem e clusterização

## Conclusão

A análise RFV é uma ferramenta poderosa para segmentação de clientes e tomada de decisão estratégica. O modelo desenvolvido permite identificar padrões de comportamento e categorizar os clientes conforme sua importância para o e-commerce, auxiliando em ações de marketing direcionadas.
