Texto traduzido no translate.google EN. - Texto em PT-BR linha 222

Text translated on translate.google EN. - Text in PT-BR line 222



***EN***


# Project

We started working with a sales database from a department store chain in Brazil, covering the period from 2016 to 2019.

We transformed the object date columns to the datetime type, which is essential for performing temporal analyses. We will generate graphs based on the following information: total sales per year, most profitable products, among other data that we observe.

First, we processed a dataframe called df_vendas_ano, which was created from a copy of the original sales dataframe. We selected only the columns of interest: date_order and sales. Then, we extracted the year from the date_order column and removed this column, keeping only the sales and years. The groupby() function was used to group the data by year and calculate the total sales for each one. With the aggregated data, a column chart was created using the Matplotlib and Seaborn libraries, where we visualized the total sales from 2016 to 2019.

The column chart was customized to present sales data in a clear and visually appealing way. The main operations performed: Adding a title, removing labels, styling the horizontal and vertical axes, and Creating a Function in the case of "grafico_vendas()".

A list of colors was created that varies between a stronger blue for the year with the highest sales and a lighter blue for the other years. This was done through a for loop that checks which year has the highest sales value. In addition, we added text to the chart to explain the variation in sales between the years 2018 and 2019, using the ax.text() function.

We processed the data by creating a new dataframe called top_lucro, where we selected the columns of interest: tipo_produto and lucrativo. Next, we aggregated the data by product type, adding up the profits and sorting them in descending order, to obtain only the 7 products with the highest profit.

A bar chart was generated using the Matplotlib and Seaborn libraries, customizing the visualization with specific colors and adjusting the graph area.

General Summary part 1: we used column and bar charts, processed and previously selected the data of interest to build a visualization, customized the title, axes, labels and color palette.


**Data Grouping**

Stacked charts will now be introduced, with bars and columns, and another categorical variable, "region", will be added, because we want to divide the value passed by the column into categories. We sometimes have the northeast region with the year 2019 in the year column, however, with different values ​​for each of the sales, so we will need to aggregate the data. Instead of using groupby(), "Cross Table" will be used. A cross table basically aggregates values ​​that are related to each other. So, we want to relate two different types of columns, taking the values ​​from the columns.
After creating a stacked chart with the "stacked" function, its formatting was done by resetting the Xlabel and Ylabel axes, and changing the parameters such as its size, color and resolution. Now the years in our chart are in the horizontal format of the chart and no longer in the vertical format, which improves the visualization. Then remove the ticks from the x and y axes, to ensure their removal.

    General Summary Part 2: Stacked column charts were created, which are useful for comparing sales data by year and region. From a copy of the sales data, where we selected the columns of interest: order_date, sales and region.
    We removed the order_date column, keeping only the relevant information. We used cross tables to aggregate sales by year and region and generated the stacked column chart.





---
---
***PT-BR***

# Projeto

Começamos a trabalhar com uma base de dados de vendas de uma rede de lojas de departamentos no Brasil, abrangendo o período de 2016 a 2019.


Transformamos as colunas de data de objeto para o tipo datetime, o que é essencial para realizar análises temporais. Vamos gerar graficos baseado nas seguintes informçaões total de vendas por ano, produtos mais lucrativos, entre outros dados que observarmos.

Primeiro, tratamos um dataframe chamado df_vendas_ano, que foi criado a partir de uma cópia do dataframe original de vendas. Selecionamos apenas as colunas de interesse: data_pedido e vendas. Em seguida, extraímos o ano da coluna data_pedido e removemos essa coluna, mantendo apenas as vendas e os anos.Foi utilizado a função groupby() para agrupar os dados por ano e calcular o total de vendas para cada um. Com os dados agregados, foi criado um gráfico de colunas utilizando as bibliotecas Matplotlib e Seaborn, onde visualizamos as vendas totais de 2016 a 2019.

 foi personalizado o gráficos de colunas para apresentar dados de vendas de forma clara e visualmente atraente. As principais operações feitas: Adição de título, remoção de rótulos, estilização do eixo horizontal e vertical e Criação de Função no caso "grafico_vendas()".

 Foi criado uma lista de cores que varia entre um azul mais forte para o ano de maior venda e um azul mais claro para os demais anos. Isso foi feito através de um laço for que verifica qual ano possui o maior valor de vendas. Além disso, adicionamos texto ao gráfico para explicar a variação de vendas entre os anos de 2018 e 2019, utilizando a função ax.text().

tratamos os dados criando um novo dataframe chamado top_lucro, onde selecionamos as colunas de interesse: tipo_produto e lucro. Em seguida, realizamos uma agregação dos dados por tipo de produto, somando os lucros e ordenando-os de forma decrescente. Para obter apenas os 7 produtos com maior lucro.

Foi gerado um gráfico de barras utilizando as bibliotecas Matplotlib e Seaborn, personalizando a visualização com cores específicas e ajustando a área do gráfico.


    Resumo Geral parte 1: usamos o gráficos de colunas e barras, fizemos o tratamento e selecionar previamente os dados de interesse para a construção de uma visualização, personalizamos título, eixos, rótulos e paleta de cores.


**Agrupamento de dados**

Vai ser introduzido agora graficos impilhados, sendo de barras e de colunas, e adicionar mais uma variavel categorica "regiao", por que quermos dividir em categorias o valor que é passado pela coluna. Temos a região nordeste algumas vezes com o ano de 2019 na coluna ano, porém, com valores diferentes para cada uma das vendas, então precisaremos fazer a agregação dos dados. Ao inves de usar o groupby(), vai ser utilizado "Cross Table" uma tabela cruzada basicamente faz a agregação de valores que tenham relação entre si. Então, queremos relacionar dois tipos diferentes de colunas, pegando os valores das colunas.
Após fazer um grafico empilhado com a função "stacked" foi feito sua formatação resetando os euxos Xlabel e Ylabel, e mudando os parametros como seu tamanho, cor e sua hotação agora os anos do nosso grafico estão no formato horizontal do grafico e nao mais na forma vertical, que melhora na hora de visualizar-mos. Em seguida removido os tickes dos eixos x e y, para que seja feito a garantia do seu remoção.

    Resumo Geral parte 2: Foi criado gráficos de colunas empilhadas, que são úteis para comparar dados de vendas por ano e região. A partir de uma cópia dos dados de vendas, onde selecionamos as colunas de interesse: data_pedido, vendas e regiao.
    Removemos a coluna data_pedido, mantendo apenas as informações relevantes. Utilizamos tabelas cruzadas (cross tables) para agregar as vendas por ano e região e geramos o gráfico de colunas empilhadas.



Estilizando o grafico de colunas ordernamos os nomes da regioes com o do grafico, criamos um laço for que chamaremos de container, adicionamos valores dentro do grafico passando uma f-string e colocando um separador com o codigo: labels = [f'R$ {valor.get_height():,.0f}'.replace(",",".")]. e foi modificado cor das informações, seu peso, tamanho e posicionamento. depois foi inserido uma linha para representar os 87% do nosso grafico com "ax.axvline" e passando seus respectivos valores.


---
---
# ***Analise 2***



