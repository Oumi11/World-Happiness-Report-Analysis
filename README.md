<img src="Visualizations%20and%20photos/WHR%20logo.png" alt="WHR Logo" width="200"/>

# World-Happiness-Report-Analysis
This analysis provides an overview of world happiness scores for each country, aiming to identify correlations and trends. This project was completed as part of the curriculum from the CareerFoundry bootcamp.



## Introduction
### The World Happiness Report has been published annually since 2012. It is produced by the United Nations Sustainable Development Solutions Network in partnership with the Ernesto Illy Foundation and is based on data collected by the Gallup World Poll. This report aims to measure and understand happiness and well-being around the globe, providing valuable insights for policymakers and researchers. By surveying people worldwide and asking them to rate their lives on a scale of 0 to 10, the report identifies the happiest countries and examines the factors contributing to happiness, such as economy, family or social support, health, freedom, generosity and trust (absence of corruption). 

##  Purpose and Key Questions

The aim of this analysis is to highlight which countries have the highest and lowest happiness levels, identify the factors driving happiness, and determine any strong correlations between these factors. The analysis covers the years 2015 to 2019, encompassing a total of 140 countries. 

The main questions we aim to answer through this analysis are: 

1. How does happiness vary from one country to another? Are there specific regions that are happier than others? 

2. To what extent do the main six factors impact the happiness score? What is the relationship or correlation between these factors? How have these factors evolved? 

3. Are there any patterns in the data that could suggest what can be done to improve the happiness score?


## Data & Tools
### 1)	Datasets
<a href="https://www.kaggle.com/datasets/unsdsn/world-happiness/data">World Happiness Report 2015/2016/2017/2018/2019</a> (Kaddle)

<a href="https://data.worldbank.org/indicator/SP.POP.TOTL?end=2019&start=2015">World Population</a> (World Bank Group)

### 2)	Python libraries
- Pandas
- Numpy
- Seaborn
- Matplotlib
- matplotlib.pyplot
- folium
- JSON
- sklearn
- pylab


## Findings

#### _1. How does happiness vary from one country to another? Are there specific regions that are happier than others?_

   To answer this question, I used folium on Python to create a choropleth map to visualize the happiness scoring worldwide (here an averaged of the happiness scoring between 2015 and 2019 has been used to showcase the results). A JSON file has been also imported to extract the country names.  

![image](https://github.com/user-attachments/assets/8265612d-2618-4bf0-aabe-5c7915e752ec)

<a href="file:///C:/Users/salmi/Desktop/achievement%206/Scripts/happiness_score_worldwide_2015_2019.html">The map is avalaible here.</a>

#### _2. To what extent do the main six factors impact the happiness score? What is the relationship or correlation between these factors?
By using a correlation heatmap using matplotlib, the visualization shows the factors that correlates the most between each other. 

Correlation between Economy and AHealth: 0.96 This strong positive correlation suggests that wealthier countries tend to have higher life expectancy and better health outcomes. This makes sense as higher income levels generally provide better access to healthcare services, contributing to improved overall health.

Correlation between Economy and Family: 0.77 This moderate positive correlation implies that countries with stronger economies often have better family dynamics and social support systems. A robust economy can enhance family well-being by providing more resources and stability.

Correlation between Generosity and Economy: -0.94 This strong negative correlation indicates that higher economic wealth in a country is associated with lower levels of generosity. This might suggest that wealthier nations may not necessarily have higher rates of charitable giving or altruistic behavior, potentially due to varying social and cultural factors.

Happiness score and the Main Factors Overall: there is a stronger correlation between the economy, health, and family with the happiness score. However, when we look at the freedom, generosity, and trust factors, the correlation seems to be rather weak or even negative. We can conclude that the first three factors weigh more heavily in the happiness score than the latter three.

![image](https://github.com/user-attachments/assets/60701175-be61-4285-b76c-e0dfc17484d7)


![image](https://github.com/user-attachments/assets/4c2b291c-2670-4091-a6f2-ceccbd2916b5)




