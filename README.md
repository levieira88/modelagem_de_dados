# Modelagem de Dados
Limpeza e organização de dados (data cleaning &amp; data wrangling) para estruturar uma base de dados para modelagem. 

## **Contexto**

Uma empresa do ramo de e-commerce contratou você para levantar os indicadores de recência, frequência e ticket médio (RFM) dos seus clientes.

A saber RFM:

- R (Recency): Tempo que o cliente realizou a última compra (em dias)
- F (Frequency): Quantidade de compras realizadas pelo cliente
- M (Monetary): Valor do ticket médio gasto pelo cliente

onde ticket médio = média do total gasto por pedido para cada cliente.

Para isso, vocês receberam uma base de dados (arquivo csv) e devem construir um código em Python que gera um output também csv, porém contendo apenas a identificação do cliente e métricas RFM.

## Sobre os dados

A tabela contém informações de compras de um e-commerce em 37 países. Contém a identificação do cliente e os dados da compra.

# 🎯 Etapas de Desenvolvimento

Para te ajudar nesse processo, detalhar o processo

## **Etapa 01) Leia o arquivo e inspecione os dados**

Pesquisar o mercado apontando os produtos que já existem hoje e seus diferenciais. É importante apresentar de forma clara os concorrentes diretos e indiretos, e destacar seus diferenciais e pontos fortes.

1. Leia o dataset
2. Utilize o describe para verificar a distribuição dos dados
3. Analise o tipo dos dados

<aside>
💡 **Dica:**

1. Leia o dataset
2. Utilize o describe para verificar a distribuição dos dados
3. Analise o tipo dos dados
</aside>

## **Etapa 02) Valores faltantes na identificação do cliente**

<aside>
💡 **Dica: Se sim, remova estas observações.**

1. Verifique os valores nulos com o isna e utilize a função sum para a somar a quantidade de nulos
2. Utilize a função dropna para remover os nulos
</aside>

## **Etapa 03) Preços unitários e quantidade de produtos iguais ou inferior a 0**

<aside>
💡 **Dica:** Se sim, remova estas observações.

1. Realize um filtro para verificar se existem dados nulos ou menor que zero na coluna de preços
2. Filtre o dataset apenas para conter preços acima de zero
3. Realize um filtro para verificar se existem dados nulos ou menor que zero na coluna de quantidade
4. Filtre o dataset apenas para conter quantidade acima de zero
</aside>

## **Etapa 04) Verifique se existem linhas duplicadas**

<aside>
💡 **Dica:** Se sim, remova estas observações (pois não faz sentido uma mesma compra para o mesmo cliente no mesmo horário, com mesmos valores etc.)

1. Verifique se tem linhas duplicadas com a função duplicated
2. Drope as linhas duplicadas
</aside>

## **Etapa 05) Tipos de dados da coluna**

<aside>
💡 **Dica:**

1. Corrija o tipo de dado do CustomerID
2. Corrija o tipo de dado da InvoiceDate
</aside>

## **Etapa 06) Tratando os outliers**

<aside>
💡 **Dica:** Vamos considerar estes valores como erro. 
  **Visualize os outliers e remova os outliers extremos em que a quantidade do item na compra é superior a 10.000, e o preço unitário é maior que 5.000.**

</aside>

## **Etapa 07) Crie uma coluna adicional**

<aside>
💡 **Dica:** Utilize as colunas Quantity e UnitPrice.  
  **Crie uma coluna adicional com o preço total da compra**

</aside>

## **Etapa 08) Última data**

<aside>
💡 **Dica:** Utilize a função max(). 
  **Calcule a data da última compra no dataset como um todo, pois vamos utilizar este valor como data de comparação para cálculo da recência.**

</aside>

## **Etapa 09) Plotando gráficos**

- **Top 10 países com maior valor em vendas**
- **Top 10 produtos mais vendidos**
- **Valor de venda total por mês**
- **Valor de venda total por mês e por país (considere apenas os top 10)**

## **Etapa 10) Cálculo do RFM**

<aside>
💡 **Dica:** Agrupe os dados por cliente e pedido/compra (InvoiceNo) e obtenha a data e o preço total do pedido.
Com isso, agrupe novamente apenas por cliente e calcule o RFM, onde:

- R é a recência, diferença em dias da última compra do cliente e da última compra disponível no conjunto de dados, que calcularam previamente.
- F é a frequência, ou seja, a quantidade de compras feitas pelo cliente;
- M é o ticket médio, ou seja, a média das compras feitas pelo cliente.

</aside>
