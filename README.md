<img src="Visualizations%20and%20photos/WHR%20logo.png" alt="WHR Logo" width="200"/>

# World-Happiness-Report-Analysis
This analysis provides an overview of world happiness scores for each country, aiming to identify correlations and trends. This project was completed as part of the curriculum from the CareerFoundry bootcamp.



## Introduction
### The World Happiness Report has been published annually since 2012. It is produced by the United Nations Sustainable Development Solutions Network in partnership with the Ernesto Illy Foundation and is based on data collected by the Gallup World Poll. This report aims to measure and understand happiness and well-being around the globe, providing valuable insights for policymakers and researchers. By surveying people worldwide and asking them to rate their lives on a scale of 0 to 10, the report identifies the happiest countries and examines the factors contributing to happiness, such as economy, family or social support, health, freedom, generosity and trust (absence of corruption). 

##  Purpose and Key Questions

**The aim of this analysis is to highlight which countries have the highest and lowest happiness levels, identify the factors driving happiness, and determine any strong correlations between these factors. The analysis covers the years 2015 to 2019, encompassing a total of 140 countries.** 

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

### Exploratory analysis

#### _1. How does happiness vary from one country to another? Are there specific regions that are happier than others?_

  To answer this question, I utilized the Folium library in Python to create a choropleth map, visualizing the worldwide happiness scores. The map showcases the average happiness scores from 2015 to 2019. Additionally, a JSON file was imported to extract and map the country names accurately.  

![image](https://github.com/user-attachments/assets/8265612d-2618-4bf0-aabe-5c7915e752ec)

![image](https://github.com/user-attachments/assets/5cb12c9a-1800-4d91-a4e2-02dba6fdae18)


#### _2. To what extent do the main six factors impact the happiness score? What is the relationship or correlation between these factors?_
By using a correlation heatmap using matplotlib, the visualization shows the factors that correlates the most between each other. 

**Correlation between Economy and Health**: 0.96 This strong positive correlation suggests that wealthier countries tend to have higher life expectancy and better health outcomes. This makes sense as higher income levels generally provide better access to healthcare services, contributing to improved overall health.

**Correlation between Economy and Family**: 0.77 This moderate positive correlation implies that countries with stronger economies often have better family dynamics and social support systems. A robust economy can enhance family well-being by providing more resources and stability.

**Correlation between Generosity and Economy**: -0.94 This strong negative correlation indicates that higher economic wealth in a country is associated with lower levels of generosity. This might suggest that wealthier nations may not necessarily have higher rates of charitable giving or altruistic behavior, potentially due to varying social and cultural factors.

**Happiness score and the Main Factors Overall**: there is a stronger correlation between the economy, health, and family with the happiness score. However, when we look at the freedom, generosity, and trust factors, the correlation seems to be rather weak or even negative. We can conclude that the first three factors weigh more heavily in the happiness score than the latter three.

![image](https://github.com/user-attachments/assets/60701175-be61-4285-b76c-e0dfc17484d7)


<img src="https://github.com/user-attachments/assets/4c2b291c-2670-4091-a6f2-ceccbd2916b5" alt="image" width="500">





**These visualizations created in Tableau display the correlations between various factors and their relationship to the happiness scores. Additionally, other variables such as population, region, and country are also presented.**



<p align="center">
  <img src="https://github.com/user-attachments/assets/7b2c9036-91f8-418a-b2a3-e93cc89ccd57" alt="Image 1" width="45%">
  <img src="https://github.com/user-attachments/assets/abe664e7-5dca-4fe3-a540-11cb8dcf92e2" alt="Image 2" width="45%">
</p>


### Statistical Analysis


#### _Supervised Machine Learning: Regression_

As demonstrated in the exploratory analysis, the economic factor significantly impacts the happiness score. To further understand this relationship, a regression analysis was conducted to test the hypothesis: "If the economy of a country is strong, then the happiness score is higher."

![image](https://github.com/user-attachments/assets/28947625-b519-44ff-b64f-cfc59a9eff0f)



- The positive slope in both the test set and training set indicate a positive relationship between the economy and the happiness score. A stronger economy is associated with higher happiness level.

- The R²score on the training set performed a bit better (0,68 for 0,63 in the test) and indicates that the relatively close values indicate that the moddel generalizes well to the new data. The model explains then a significant portion of the variance in happiness scores (68%). There is however 32% of the variance that is unexplained by the model. This makes sense as the happiness score is not only build on the economy factors.

- To conclude, the relatively positive performance metrics suggest that the model is reliable. However, the small amount of data here (only 140 countries or data points) could not be reliable to implement that on other new data. Indeed, this could lead to inacurracy and/or biased results.


#### _Unsupervised Machine Learning: K-means Clustering

With K-means clustering, we can effectively group similar data points together into clusters. This method allows us to identify and categorize data points that share common characteristics. (see script 6.5)

![image](https://github.com/user-attachments/assets/0ab91254-b6d1-4291-89fe-9d8ffb8f19c1)


![image](https://github.com/user-attachments/assets/d3e6b316-a5b5-4a22-8159-9e2dcc8d7a83)


**The K-means algorithm identified three distinct clusters within the dataset. These clusters provide meaningful insights, particularly highlighting the relationship between economic factors and happiness scores. For instance, countries in the pink cluster, which have better economic conditions, tend to have higher happiness scores. However, the data also reveals that countries with similar economic conditions can have significantly different happiness scores. This observation underscores the multifaceted nature of happiness, suggesting that while the economy is a major driver, it is not the sole factor influencing happiness.**



## Limitation of the datasets


#### _1) Data Collection Method_
- The World Happiness Report data is based on responses to the main life evaluation question. Respondents are asked to rate their current life on a scale from 0 (worst) to 10 (best) by imagining a ladder. 

- Only a sample of the population in each country is selected, totaling over 100,000 respondents. While the data comes from a reliable source, the subjectivity of the polls and the sample size need consideration during analysis. 

- Cultural biases may affect responses, as happiness perceptions vary from one culture to another (e.g., some people might earn less but feel happier). 


#### _2) Happiness Score Composition_

The Happiness Score is a sum of several factors (variables in the dataset), which may not be reliable for direct use in predictive models. It is crucial to examine the interactions and relationships between these factors rather than treating them independently. 


#### _3) Data Recency and Consistency

- The World Happiness Report is relatively recent, limiting the availability of long-term data for building reliable predictive models. 

- Factors recorded for 2018 and 2019 differ, lacking the Dystopia Residual used to account for unexplained external factors impacting happiness. 

- The "family" factor was renamed to "social support" in recent reports. For consistency, this variable has been named "family and social support" in the analysis. 

#### _4) Missing Data
Some countries were not selected each year, and for consistency, countries with missing data from certain years were excluded from the analysis, resulting in 140 countries being analyzed. 

