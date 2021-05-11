# Ethan's Webpage

## Project:
I am interested in looking at how family dynamics impact student alcohol consumption.  Our dataset has information about the family, including the education and job experience of both parents.

Additionally, I am interested in learning more about how the use of alcohol affects an individual and the various aspects of their lives.  I expect there to be a negative effect of alcohol use on various academic outputs, as alcohol is generally considered to be bad for productivity.
### Datasets:
* [Student Alcohol Consumption](https://www.kaggle.com/uciml/student-alcohol-consumption)
-- This Dataset has information about student alcohol consumption in Portugal, and contains information about the family environments of the students
* [Global Alcohol Consumption](https://data.world/fivethirtyeight/alcohol-consumption)
-- This Dataset from the World Health Organization contains information about the average annual per capita alcohol consumption of different countries in the world, separated by type of alcoholic beverage.

### Data Issues:
- The dataset from the world health organization uses the names of countries, instead of the country codes which plotly accepts.  To get around this problem, I used a python library called [Country Converter](https://pypi.org/project/country-converter/).  This library takes a vector input of country names, and you can specify the desired output format.  I outputted to ISO 3 letter format, and then saved that to a new column on the dataframe.  I saved to a pickle file, and then read that pickle file into my Jupyter Notebook.  I had to use the library in a local python environment, since I could not get anaconda to install it in the Jupyter notebook.
-  While I said I wanted to find a dataset that connected family history and alcoholism data, so I had to refocus on looking at how Alcohol use varies across the world, as this was the only data that I was able to find.

## Visualizations:

### Parental Separation Vs. Cohabitation.
This histogram compares the relative weekly alcohol consumption of students whose parents live together and apart.
{% include_relative Visualizations/plot.html %}

### Effect on School Attendance
This bar chart shows the number of absences by each group of alcohol use.  Somewhat surprisingly, there are more absences in the 4/5 alcohol group than the 5/5 alcohol group, which could be a fact of there simply being more people that can be classified as 4/5 than 5/5.  There are 51 students in the 4/5 category, while there are only 28 in the 5/5 group.
{% include_relative Visualizations/absences.html %}

### Effect on Future Goals
This histogram, for each group, shows the relative percentages of those in that category who do wish to pursue higher learning, and those who do not.  I expected to see a decrease in higher learning aspirations as alcohol consumption increased, and I was not surprised to see this relationship reflected in the data.
{% include_relative Visualizations/higher.html %}

### Global Alcohol Consumption
This is an interactive Choropleth that shows the annual average per capita alcohol consumption of different countries around the world.  This is interesting, as we see that Portugal, the country from the other dataset, consumes 2.3 more liters of pure alcohol per year than the United States.  This suggests that while in the United States we may have similar effects as the data from Portugal show, but likely to a lesser extent as we consume less alcohol on average.
{% include_relative Visualizations/world.html%}


## Coming Soon:
In the final week of class, I want to find another data set that provides more information connecting the role of the parents on child alcohol use.  I am also curious about family history for alcoholism, and how that may affect the academic outcomes of their children.  For example, it appears that as high school students use alcohol more, they are less likely to want to go to college.  Going further, I am curious if those students who are using alcohol at higher rates have a family history of alcoholism, or if there are other factors that led to their situation.

## Jupyter Notebooks
I used a different notebook for each dataset that I used:
* [Student Alcohol Consumption](Visualizations/notebook.html)
* [Global Alcohol Consumption](Visualizations/notebook2.html)


## Other Research
This visualization from [Marripedia](http://marripedia.org/effects.of.divorce.on.children.s.behavior) shows that children whose parents are separated have higher behavioral problem scores.

![Visual](Visualizations/childbehavioral.jpeg)

This [article](https://www.verywellmind.com/the-effects-of-parental-alcoholism-on-children-67233) talks about the many impacts that parental alcoholism can have on children.
![Picture](Visualizations/parent_alc.png)

This research relates to my next question, as there are clear psychological effects of alcoholism in the family.  In addition to a distorted attitude towards alcohol, other psychological issues created by alcoholism may potentially lead children to worse academic outcomes, even if they are not drinking at high levels.

This [Study](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC4872611/) by NCBI discusses the role of culture in alcohol use.  It finds that cultural attitudes are strong predictors of level of drinking, which provides some insight as to why the global alcohol consumption differs so much from country to country, even when they are neighboring.  For example, France drinks the most wine, but does not drink the most alcohol.  France is also famous for its wine, so this makes sense.

This [Study](https://www.jstor.org/stable/588726?seq=1) by the British Journal of Sociology has similar findings, suggesting that social factors have a very strong impact on rates of alcohol use.

This [Book](https://www.peele.net/lib/sociocul.html) Discusses the cultural roles of alcoholism.  The author writes, "Individual drinkers tend to model and modify each others' drinking and, hence,...there is a strong interdependence between the drinking habits of individuals who interact....Potentially, each individual is linked, directly or indirectly, to all members of his or her culture".  I think that this quote is interesting as it applies sociological concepts to how we look at alcohol use, as opposed to just psychology, or just data analysis.

Ultimately, alcohol use is very complicated and embedded in society in a number of ways.  It is curious to see how across one culture levels of use may vary, as we see in the Portuguese youth.  It is even more interesting to see how some countries abstain, while others imbibe in the extreme.  The data indicate that where you are born, and your family have a large impact on how you will grow up to use (or abstain from) alcohol.
