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

### Cluster 0 (Clientes de alto valor)
- Tamanho do cluster: 7.444 registros (relativamente pequeno em relação ao total de registros)

- Quantidade média (Quantity): 50,77 unidades. Isso sugere que os clientes desse grupo fazem compras em maior volume.

- Preço médio unitário (UnitPrice): 0,42, indicando que os produtos comprados por esses clientes têm um preço unitário relativamente baixo.

- Total gasto médio (TotalSpent): 19,17. Embora o preço unitário seja baixo, a quantidade comprada é alta, resultando em um total médio de gasto razoável.

Características principais:

- Clientes com compras grandes (quantidade) e um total gasto significativo. Mesmo que o preço por unidade não seja muito alto, o volume de compras compensa, tornando esses clientes valiosos.

- Proposta de ação: Como eles têm um gasto médio elevado, é interessante oferecer programas de fidelidade e descontos exclusivos para mantê-los como clientes frequentes e de alto valor para o negócio.

### Cluster 1 (Clientes de baixo valor)
- Tamanho do cluster: 347.586 registros (grande parte dos dados)

- Quantidade média (Quantity): 6,71 unidades. Esses clientes compram em menor quantidade, o que pode indicar que eles fazem compras menores, mais esporádicas ou de produtos mais baratos.

- Preço médio unitário (UnitPrice): 2,77. O preço médio unitário é mais alto do que o do Cluster 0, o que sugere que esses clientes compram produtos mais caros, mas em menor quantidade.

- Total gasto médio (TotalSpent): 11,43. Embora o preço por unidade seja mais alto, a quantidade comprada é menor, resultando em um total de gasto inferior ao Cluster 0.

Características principais:

- Clientes com menor volume de compras e, portanto, com um gasto total mais baixo. Apesar de comprarem produtos mais caros, a frequência e quantidade de compras são menores, tornando-os menos valiosos em termos de receita. Proposta de ação: Para incentivar esses clientes a gastar mais, você pode criar promoções direcionadas e aumentar a comunicação com eles, talvez oferecendo descontos ou benefícios que estimulem compras mais frequentes ou de maior volume.

## Conclusões gerais:
- Cluster 0 (Clientes de alto valor) são aqueles que compram mais unidades, gastam mais no total e, por isso, merecem um tratamento especial com programas de fidelidade e ofertas exclusivas. Eles são importantes para garantir a receita recorrente e aumentar a lealdade ao negócio.

- Cluster 1 (Clientes de baixo valor) têm um comportamento de compra diferente, fazendo compras menores ou em menor frequência, mas com preços unitários mais altos. Aqui, o objetivo é aumentar o engajamento e as compras desses clientes, com promoções personalizadas ou estratégias de marketing que incentivem a compra em maior volume.
