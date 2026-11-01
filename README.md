# Segmentação de compras de e-commerce com K-Means

Clusterização de mais de 500 mil linhas de compras de um e-commerce para separar perfis de compra e propor ações de marketing para cada grupo.

[![Abrir no Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/guilhsantos/RFV_Analysis_Clustering/blob/main/RFV_Analysis_Clustering.ipynb)

## Problema

Tratar todo cliente do mesmo jeito desperdiça verba de marketing. Quem compra em volume e quem compra pouco e caro pedem abordagens diferentes.

## Solução

Agrupamento não supervisionado (K-Means) das compras por **quantidade**, **preço unitário** e **valor total gasto**, com o número de grupos escolhido por métrica, e não no olho.

## Resultado

O Silhouette Score (testado de 2 a 20 grupos) indicou **2 clusters**:

| Cluster | Registros | Qtd. média | Preço unitário médio | Gasto médio | Ação proposta |
|---|---|---|---|---|---|
| **0 · Alto volume** | 7.444 | 50,8 un. | 0,42 | 19,17 | fidelidade e descontos exclusivos |
| **1 · Baixo volume** | 347.586 | 6,7 un. | 2,77 | 11,43 | promoções para estimular compras maiores |

O achado principal é um grupo pequeno que compra muitas unidades de itens baratos e gasta mais por compra. Ele merece tratamento próprio.

## Como fiz

1. **Exploração:** 541.909 linhas, 135 mil sem cliente identificado, 5.268 duplicadas e preços e quantidades negativos (devoluções).
2. **Limpeza:** remoção de nulos, duplicados e preços zerados, e outliers de gasto removidos pelo IQR.
3. **Variáveis:** criação do gasto total (`quantidade × preço`) e padronização com `StandardScaler`.
4. **Escolha de k:** Silhouette Score de 2 a 20 grupos em uma amostra de 10%, com PCA para visualizar.
5. **Leitura dos grupos:** médias por cluster e recomendações de marketing.

## Limitações e próximos passos

- A segmentação é **por compra**, não por cliente. O passo natural é calcular a RFV de verdade por cliente (recência, frequência e valor) e clusterizar sobre ela. O cálculo de RFM por cliente está no repositório [Extracao_e_Tratamento_de_Dados_com_Python](https://github.com/guilhsantos/Extracao_e_Tratamento_de_Dados_com_Python).
- Testar mais grupos com critérios de negócio, além da métrica.

## Stack

Python · pandas · NumPy · scikit-learn (K-Means, PCA, Silhouette) · Plotly · Seaborn · Google Colab

---

Feito por [Guilherme Santos](https://portifolio-guilherme-santos.vercel.app) · [LinkedIn](https://www.linkedin.com/in/guilherme-santos-dataeng)
