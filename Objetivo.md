Descrição do Problema:
O conjunto de dados contém informações comportamentais de clientes, com o objetivo de realizar uma análise de agrupamento de clientes. Essa análise pode ajudar a entender padrões de consumo e segmentar clientes de forma eficiente, de modo que a empresa possa oferecer promoções ou campanhas direcionadas. Além disso, o dataset pode ser utilizado tanto para aprendizado supervisionado quanto para aprendizado não supervisionado. No aprendizado supervisionado, o objetivo pode ser prever se um cliente vai ou não aceitar uma oferta específica, enquanto no não supervisionado, busca-se clusterizar os clientes para identificar padrões de comportamento e consumo.

Tipo de Problema:
Este é um problema que pode ser abordado de duas formas:

Aprendizado supervisionado: Previsão de aceitação de ofertas com base em características do cliente.
Aprendizado não supervisionado: Clusterização de clientes para descobrir padrões ocultos em seus comportamentos.
Premissas e Hipóteses:

Clientes mais velhos ou com maior nível educacional podem ter um ticket médio de compras maior.
Famílias com mais crianças tendem a gastar mais em doces ou produtos voltados para o público infantil.
Clientes que reclamaram nos últimos dois anos podem ter um comportamento de compra diferenciado.
Restrições ou Condições de Seleção: Não foram impostas restrições para a seleção dos dados. O dataset abrange um conjunto variado de informações sobre comportamento de clientes.

Atributos do Dataset:
People (Informações do Cliente):

ID: Identificador único do cliente.
Year_Birth: Ano de nascimento do cliente.
Education: Nível educacional do cliente.
Marital_Status: Estado civil do cliente.
Income: Renda anual familiar do cliente.
Kidhome: Número de crianças na casa do cliente.
Teenhome: Número de adolescentes na casa do cliente.
Dt_Customer: Data de cadastro do cliente na empresa.
Recency: Número de dias desde a última compra do cliente.
Complain: 1 se o cliente fez uma reclamação nos últimos 2 anos, 0 caso contrário.
Products (Gastos em Produtos):

MntWines: Valor gasto em vinhos nos últimos 2 anos.
MntFruits: Valor gasto em frutas nos últimos 2 anos.
MntMeatProducts: Valor gasto em carne nos últimos 2 anos.
MntFishProducts: Valor gasto em peixe nos últimos 2 anos.
MntSweetProducts: Valor gasto em doces nos últimos 2 anos.
MntGoldProds: Valor gasto em produtos de ouro nos últimos 2 anos.
Promotion (Participação em Campanhas de Marketing):

NumDealsPurchases: Número de compras feitas com desconto.
AcceptedCmp1: 1 se o cliente aceitou a oferta na 1ª campanha, 0 caso contrário.
AcceptedCmp2: 1 se o cliente aceitou a oferta na 2ª campanha, 0 caso contrário.
AcceptedCmp3: 1 se o cliente aceitou a oferta na 3ª campanha, 0 caso contrário.
AcceptedCmp4: 1 se o cliente aceitou a oferta na 4ª campanha, 0 caso contrário.
AcceptedCmp5: 1 se o cliente aceitou a oferta na 5ª campanha, 0 caso contrário.
Response: 1 se o cliente aceitou a oferta na última campanha, 0 caso contrário.
Place (Canais de Compra):

NumWebPurchases: Número de compras feitas através do site.
NumCatalogPurchases: Número de compras feitas através de catálogos.
NumStorePurchases: Número de compras feitas diretamente nas lojas.
NumWebVisitsMonth: Número de visitas ao site da empresa no último mês.
#**Análise de dados **

**Objetivo: entender a informação disponível. **


**Estatísticas descritivas: **


**Quantos atributos e instâncias existem?** **Quais são os tipos de dados dos atributos?**

RangeIndex: 2240 entries, 0 to 2239
Data columns (total 29 columns):
 #   Column               Non-Null Count  Dtype  
---  ------               --------------  -----  
 0   ID                   2240 non-null   int64  
 1   Year_Birth           2240 non-null   int64  
 2   Education            2240 non-null   object 
 3   Marital_Status       2240 non-null   object 
 4   Income               2216 non-null   float64
 5   Kidhome              2240 non-null   int64  
 6   Teenhome             2240 non-null   int64  
 7   Dt_Customer          2240 non-null   object 
 8   Recency              2240 non-null   int64  
 9   MntWines             2240 non-null   int64  
 10  MntFruits            2240 non-null   int64  
 11  MntMeatProducts      2240 non-null   int64  
 12  MntFishProducts      2240 non-null   int64  
 13  MntSweetProducts     2240 non-null   int64  
 14  MntGoldProds         2240 non-null   int64  
 15  NumDealsPurchases    2240 non-null   int64  
 16  NumWebPurchases      2240 non-null   int64  
 17  NumCatalogPurchases  2240 non-null   int64  
 18  NumStorePurchases    2240 non-null   int64  
 19  NumWebVisitsMonth    2240 non-null   int64  
 20  AcceptedCmp3         2240 non-null   int64  
 21  AcceptedCmp4         2240 non-null   int64  
 22  AcceptedCmp5         2240 non-null   int64  
 23  AcceptedCmp1         2240 non-null   int64  
 24  AcceptedCmp2         2240 non-null   int64  
 25  Complain             2240 non-null   int64  
 26  Z_CostContact        2240 non-null   int64  
 27  Z_Revenue            2240 non-null   int64  
 28  Response             2240 non-null   int64  

**Verifique as primeiras linhas do dataset. Algo chama a atenção?**

**Há valores faltantes, discrepantes ou inconsistentes?**

Sim , dentro da analise foi possivel observar dados outliers , dados faltantes mas não inconsistentes

Faça um resumo estatístico dos atributos com valor numérico (mínimo, máximo, mediana, moda, média, desvio-padrão e número de valores ausentes).

** O que você percebe?**
Sem a tratativa dos dados é possivel observar que temos algumas informações discrepantes , principalmente as voltadas para volores financeiros. A exemplo disso temos dados como 'Income' que apresenta um valor maximo de 666666 mas a media é 52247.25 ,  consumo de frutas com media 26.30 e valor maximo 199.00 . Dentre outros valores 

#**Visualizações: **


Verifique a distribuição de cada atributo. O que você percebe? Dica: esta etapa pode dar ideias sobre a necessidade de transformações na etapa de preparação de dados (por exemplo, converter atributos de um tipo para outro, realizar operações de discretização, normalização, padronização, etc.).

Maior parte dos clientes da pesquisa possuem 2-3 pessoas na familia;

Maior parte dos clientes possuem valores Zerados em campos de produtos de consumo , isso pode acabar gerando algumas distorções nas analises;

Numero de frequencia de visitas ao site é maior do que a frequencia de compra, o que pode sinalizar que alguns clientes estão aguardando promoções para concluir as compras;

-Se for um problema de classificação, verifique a distribuição de frequência das classes. O que você percebe? Dica: esta etapa pode indicar a possível necessidade futura de balanceamento de classes.

Total de cada categoria para status civil:
 Marital_Status
Married     864
Together    580
Single      480
Divorced    232
Widow        77
Alone         3
Absurd        2
YOLO          2
Name: count, dtype: int64 

Total de cada categoria para Nivel educacional:
 Education
Graduation    1127
PhD            486
Master         370
2n Cycle       203
Basic           54

Old_Customer       1103
New_Custumer        551
Recent_Customer     548

Dados foram agrupados durante o codigo


-Analise os atributos individualmente ou de forma combinada, usando os gráficos mais apropriados.




**Pré-processamento de dados: **

**Objetivo:** realizar operações de limpeza, tratamento e preparação dos dados.


-Verifique quais operações de pré-processamento podem ser interessantes para o seu problema e salve visões diferentes do seu dataset (por exemplo, normalização, padronização, discretização e one-hot-encoding).

Foram utilizados processos de normalização , label enconding e feature engineering

Trate (removendo ou substituindo) os valores faltantes (se existentes).
Foram removidos

