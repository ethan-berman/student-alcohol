# Welcome to Bella's Webpage

## Statement of interest

Drinking is a controversial issue. Drinking in moderation is good for your health, but excessive drinking can harm your health. I grew up in China, and the legal age for buying alcohol in China is 18 years old, but many young people younger than 18 have tried to tart drinking. Few places will check ID.

When I came to the United States, I felt that the United States attaches great importance to the legal drinking age. Whether in restaurants or supermarkets, the date of birth on the ID will be carefully checked, which is a good way to control drinking.

My boyfriend’s uncle is a very alcoholic person, which has also become the reason for his death. He often gets drunk with friends and has headaches and vomiting symptoms. But he has no way to change his behavior because he has never been very drunk. He started drinking at a young age. Until one time, he drank too much, causing sudden alcoholism. In the end, the rescue failed and died. I believe that there are many cases of alcohol causing illness or death every year.

The event that happened around me makes me interested in the amount of alcohol purchased in the world. I will focus on the overview of the alcohol consumption situation of the world and the European region. Additionally, the relationship between the average alcohol purchase in the country and some potential variables, like the legal drinking age, national GDP per capita, and gender. Finally, I will do the reseach on how the world's death rate due to alcohol looks like.

## Datasets
I use these four datasets for my investigation:  

[**Total per capita (15+) consumption (in litres of pure alcohol) by country**](https://apps.who.int/gho/data/node.main.A1029SDG3?lang=en)

This dataset recorded alcohol consumption in liters by country of 2000, 2005, 2010, 2015, and 2018. In each year columns, it contains the alcohol consumption per capit of both sexes, male and female. 

[**Historical GDP per Capita by Country, 1960-2018**](https://apps.who.int/gho/data/node.main.A1039?lang=en)

This dataset includes data about historical GDP per capita by country form 1960 to 2018. It shows from highest per capita GDP country to the lowest one. At the most basic interpretation, per capita GDP shows how much economic production value can be attributed to each individual citizen. 

[**Recorded alcohol per capita consumption, 1960-2018**](https://apps.who.int/gho/data/node.main-euro.A1022?lang=en&showonly=GISAH)

This dataset recorded alcohol per capita consumption from 1960-1979, 1980-1999, 2000-2009, and after 2010. It contains the column of alcohol per capita consumption in liters by European countries and each beverage type. 

[**List of countries by population (United Nations)**](https://en.wikipedia.org/wiki/List_of_countries_by_population_(United_Nations))

This dataset contains a list of countries and other inhabited territories of the world by total population of 2018 and 2019, based on estimates published by the United Nations in the 2019 revision of World Population Prospects.


## Challenges with WHO Data

There are several challenges to overcome when working with his data. I summarize them here.

* In the world alcohol consumption data, there are only the full name of Country in the Country column. When we use plotly to create the Mapbox Choropleth Maps, it maps the graph using Alpha-3 code. I need to merge the data with a list of country codes by Alpha-3 code and make sure all countries in the origin dataset shoule be there after merging. 

* In the WHO wibside, the dataset from 1960-2018 are separated in to 4 individual csv file, 1960-1979, 1980-1999, 2000-2009, and after 2010. I must merge them in to one dataframe and then do the visualization.

* When I did merging, how of parameter only has 'left', 'right', 'outer', 'inner', and 'cross'. Thoes cannot satisefy my merging requriment, so finally I use pd.concat to combine these data. And I also transpose data frame without index, since the column of original data is year and row of original data is countries. It will be easier to make visualization after swap rows and columns. It took me a long time to fix. 

## Alcohol Consumption Visualization

### World alcohol consumption

Here is a plotly visualization for alcohol, total per capita(15+) consumption by country 2018.
{% include_relative Visualization/alcoholc.html %}

As the graph shows, the average per capita alcohol consumption varies widely across the world. 
There are big geographical differences: Alcohol consumption across North Africa and the Middle East is particularly low — in many countries like Pakistan and Syrian Arab Republic, close to zero. At the upper end of the scale, alcohol intake across Europe is highest at around 15 liters per person per year in the Czechia, Lithuania, and Latvia. 

Only slightly behind the Eastern European countries are Western European countries – including Germany, France, Portugal, Ireland, and Belgiumm – at around 12 to 13 liters. Outside of Europe the only other countries in this category are Nigeria and Burkina Faso.

Thoughout much of Europe, the legal drinking age is pretty low and ranges between 15 to 18, and often there isn't a legal drinking age at all. This makes their citizen starting to drink at teen. 

### European country alcohol consumption

Here is a line graph visualization for alcohol, total per capita(15+) consumption by European country from 2000 to 2018. 
{% include_relative Visualization/europe.html %}
{% include_relative Visualization/top5.html %}
{% include_relative Visualization/bottom5.html %}

The highest consumption is nearly ten times the lowest. The five countries with the highest alcohol consumption in 2018 are Czechia, Latvia, Austria, Lithuania, and Bulgaria. Their legal drinking ages are 18, 18, 18, 20, and 18. 2018 The five European countries with the lowest consumption in the year are Tajikistan, Turkey, Uzbekistan, Azerbaijan, and Israel. Their legal drinking ages are 18, 18, 20, 16, and 18. The legal drinking ages of his five countries are not higher——less than the lowest 5. I will study later whether the legal drinking age and some other factors are related to the purchase. 

### Eruopean regrion alcohol consumption over time

The time series line graph shows the alcohol consumption changes over time. 
{% include_relative Visualization/time.html %}

From 2000 to 2018, alcohol purchases in Europe experienced growth and decline. 2007 became a turning point. From 2005 to 2006, alcohol consumption increased rapidly. Later, in the year from 2008 to 2009, it experienced a rapid decline. Although alcohol consumption levels have been declining, Europe remains the region with the highest proportion of drinkers globally.
And everyone consumes the highest amount of alcohol. As well as alcohol is still the most dangerous and vital risk factor for poor health and premature death. Alcohol is The third risk factor for poor health, more important than high cholesterol and overweight.
 

### Alcohol consumption vs. GDP per capita
{% include_relative Visualization/gdp.html %}

Does alcohol consumption increase as countries get richer? I hypothesized that people in rich countries have a better standard of living and income.They will have spare money to go to bars or buy and drink alcohol to enjoy life, but poor countries still need to solve the problem of food and clothingand alcohol purchases will be relatively low. 

In the chart we see the relationship between average per capita alcohol consumption (in liters of pure alcohol of both sexes in 2018) versus gross domestic product (GDP) per capita, across countries.

We see from the chart that there is some correlation between per capita GDP and alcohol consumption, but it is not strong. People within higher income brackets tend to drink more frequently. Countries with lower per capita GDP (below 10k), although some countries have high alcohol purchases, such as Uganda, Burkina Faso, and United Republic of Tanzania , But the per capita alcohol consumption are concentrated below 5 liters. In countries with higher per capita GDP (over 10 k), most countries buy alcohol at 5-15 liters per capita. This correlation is also likely to be influenced by other lifestyle determinants and habits. the UK ONS also report that when grouped by education status, those with a university tend to drink more in total and more frequently than those of lower education status. There are also differences when grouped by profession: individuals in managerial or professional positions tend to drink more frequently than those in intermediate or manual labour roles.

### Alcohol consumption vs. legal drinking age 
{% include_relative Visualization/age.html %}

### Alcohol consumption by sex
{% include_relative Visualization/gender.html %}

This graph confirms my hypothesis about gender and alcohol consumption: Male actually buy more alcohol than Female.
The graph shows gender differences on alcohol consumption in 2018. We see that in all countries men are more likely to drink than women.

Overall, women's alcohol purchases are about four times lower than men's. This gender difference appears to be lowest in countries where the overall prevalence of drinking high. Where drinking prevalence is low-to-mid range, the prevalence of drinking in women tends to be significantly lower. 


## Other research

This visualization from [CACTC](https://www.cortlandareactc.org/post/teen-drinking-in-europe-vs-the-united-states#:~:text=While%20only%20about%2033%20out,days%20in%20Denmark%20and%20Austria.) shows that teen drinking rate in Europe Vs. the United States in past 30 days of April, 2020. 

![image](https://static.wixstatic.com/media/c07c7f_a3ffa46bee974eb8af0fcd33f7702e1d~mv2.png/v1/fill/w_1000,h_1000,al_c,q_90/c07c7f_a3ffa46bee974eb8af0fcd33f7702e1d~mv2.webp)

Compared to European countries, the US had the lowest teen drinking rate of all, except Iceland, within in the past 30 days. While only about 33% had at least one drink within the past 30 days in the U.S, European rates ranged from 42% teens drinking within the past 30 days in Norway and 80% teens having at least one drink in the past 30 days in Denmark and Austria.   

In most European country, the legal drinking age is between 16-18. Iceland is the only one that has legal drinking age of 20. It is also the only European country with lowest teen drinking rate. 

## Conclusion

## Jupyter Notebook



