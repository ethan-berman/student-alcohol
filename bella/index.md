# Bella's Webpage


## Project

I am interested in the per capita consumption of alcohol for 15+ people in the world. Our data was collected of the consumption of 15-22 year-old students in two secondary schools in Portugal. I feel that the legal drinking age in Europe is relatively low, so I want to see which countries in the world have higher per capita consumption of alcohol.

## Dataset
* Here I compile the world alcohol comsumption by country data from the [WHO](https://apps.who.int/gho/data/node.main.A1039?lang=en)
The data recoreded alcohol per capita consumption from 2010 to 2018. It contains alcohol per capita consumption in litters by countries and each beverage types. 

* Here I compile the European region alcohol consumption by country data from the [WHO](https://apps.who.int/gho/data/node.main-euro.A1022?lang=en&showonly=GISAH)
The data recorded alcohol per capita consimption from 1960-1979, 1980-1999, 2000-2009, and after 2010. It caontains the column of alcohol per capita consumption in litters by European countries abd each beverage types. 

## Challenges with WHO Data

There are several challenges to overcome when working with his data. I summarize them here.

* In the world alcohol consumption data, there are only the full name of Country in the Country column. When we use plotly to create the Mapbox Choropleth Maps, it maps the graph using Alpha-3 code. I need to merge the data with a list of country codes by Alpha-3 code and make sure all countries in the origin dataset shoule be there after merging. 

* In the WHO wibside, the dataset from 1960-2018 are separated in to 4 individual csv file, 1960-1979, 1980-1999, 2000-2009, and after 2010. I must merge them in to one dataframe and then do the visualization.

* When I did merging, how of parameter only has 'left', 'right', 'outer', 'inner', and 'cross'. Thoes cannot satisefy my merging requriment, so finally I use pd.concat to combine these data. And I also transpose data frame without index, since the column of original data is year and row of original data is countries. It will be easier to make visualization after swap rows and columns. It took me a long time to fix. 

## Visualization

### World alcohol consumption.

Here is a plotly visualization for alcohol, total per capita(15+) consumption by country 2018.
{% include_relative Visualization/alcohol.html %}

### European country alcohol consumption.

Here is a line graph visualization for alcohol, total per capita(15+) consumption by European country from 2000 to 2018. 
{% include_relative Visualization/europe.html %}

### Time series of Eruopean regrion alcohol consumption. 

{% include_relative Visualization/time.html %}

## Other research

This visualization from [CACTC](https://www.cortlandareactc.org/post/teen-drinking-in-europe-vs-the-united-states#:~:text=While%20only%20about%2033%20out,days%20in%20Denmark%20and%20Austria.) shows that teen drinking rate in Europe Vs. the United States in past 30 days of April, 2020. 

![image](https://static.wixstatic.com/media/c07c7f_a3ffa46bee974eb8af0fcd33f7702e1d~mv2.png/v1/fill/w_1000,h_1000,al_c,q_90/c07c7f_a3ffa46bee974eb8af0fcd33f7702e1d~mv2.webp)

Compared to European countries, the US had the lowest teen drinking rate of all, except Iceland, within in the past 30 days. While only about 33% had at least one drink within the past 30 days in the U.S, European rates ranged from 42% teens drinking within the past 30 days in Norway and 80% teens having at least one drink in the past 30 days in Denmark and Austria.   

In most European country, the legal drinking age is between 16-18. Iceland is the only one that has legal drinking age of 20. It is also the only European country with lowest teen drinking rate. 

