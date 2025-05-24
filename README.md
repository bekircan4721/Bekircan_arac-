# Dsa 210 project


## Main Purpose of the project

In this project, I will attempt to examine how the consequences of temperature change affect shark behavior and which areas are most likely to be affected. My main goal is to understand how sharks react to climate changes. This way, we can think about when to enter the ocean and feel safer when entering the ocean.  

## Motivation
I have been interested in sharks since my childhood,thats why researching how climate change affects these incredible animals excites me. I also think that there is a correlation between shark attacks and the changing climate.

## Project Plan:
# Collecting Datasets:
- The data for shark attacks will be collected from Kaggle, and the Earth's temperature data will be collected from Nasa
- Shark attack dataset(1): https://www.kaggle.com/datasets/felipeesc/shark-attack-dataset/data
- Land and Ocean datasets(2): https://www.ncei.noaa.gov/data/oceans/woa/DATA_ANALYSIS/3M_HEAT_CONTENT/DATA/basin/pentad/pent_h22-w0-2000m.dat
-  https://data.giss.nasa.gov/gistemp/graphs/graph_data/Global_Mean_Estimates_based_on_Land_and_Ocean_Data/graph.txt
## Data Analysis

# - Data Cleaning: 
I will clean the datasets if needed. For example if there are columns like null valued, I will determine whether fill those rows, or drop these rows.
# - Choosing Relevant Data:
- Shark attack dataset will be analyzed by categories such as country, year,Fatality,Location and attack details, and in the Temperature datasets I will focus on categories like Year, Wo(World Ocean),NH(Northern Hemisphere),SH(Southern Hemisphere).
- Shark attack dataset will be enriched with temperature datasets. As a result, we can observe how sharks react to temperature change.
- Exploring potential correlations between rising ocean temperatures and shark attacks.
- I will use my analysis for Hyphotesis testing like H0(Null hypothesis) and H1(Alternative hypothesis)
- I will use machine learning models such as decision trees, random forests, Logistic regression, so I can make a prediction about the shark attack probability.

# Data Visualization
- I will use python to visualize my analysis, and with the help of the libraries like pandas, matplotlib, seaborn, I will visualize my results.
## Report
 - The main objective of this project is observe the relationship between the temperature changes and sharks. This project aims to reveal which factors affect shark attacks and how it affects.
## Hypothesis
# - H0(Null hyphotesis)
- There is no relationship between shark attacks and temperature
# - H1(Alternative hyphotesis)
- Obviously there is a relationship between the shark attacks and temperature

## Explanatory Data Analysis
 - I analyzed attacks.csv dataset, and I choose most related categories such as "Year" , "location".
 - Firstly I started cleaning the shark attack dataset because there were some missing values in Year category, which is the most important category for this project.
 - I visiualized the year and shark attack count at that year
 - ## Yearly Shark attacks
 # Top 10 Shark attack location
 - ![image](https://github.com/user-attachments/assets/29cf6877-ce43-490d-89e4-9b6a3f542314)
 - Code of most 10 Shark attack location: [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/bekircan4721/Bekircan_arac-/blob/main/Shark_locations.ipynb)
 # Yearly Shark Attacks
 - ![image](https://github.com/user-attachments/assets/1be4b73f-9f86-44a6-a27d-b4c018251103)
 - Code of the shark attacks : [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/bekircan4721/Bekircan_arac-/blob/main/shark_year.ipynb)

 - I filtered both the shark attacks dataset and temperature dataset, then I merged them.
 - After I merged these datasets, I explored the data by plotting scatterplot distribution of yearly shark_attacks  vs ocean temperature
 - Then I calculated the correlation.
 - ## Analyzing Shark Attack vs Ocean Temperature
 - I used merged dataset to visualize Shark Attacks vs Ocean Temperature with different visualization techniques such as scatterplot, barplot, boxplot.
 - ![image](https://github.com/user-attachments/assets/c2d07cbd-ce36-4ba6-86a1-652b22e66ba2)
 - ![image](https://github.com/user-attachments/assets/12e83ada-b9b3-4d8f-99dd-4ac25bdf1f6c)
 - ![image](https://github.com/user-attachments/assets/5b68b352-4517-487a-a6c3-12fc33adf05b)
 - Code of the three visual : [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/bekircan4721/Bekircan_arac-/blob/main/explaining_data.ipynb)

- It seems like there is a clear relationship between Ocean temperature and Shark attacks when we look at the scatterplot , and boxplot distrubution. However, the difference seems like less if we look at only barplot. Therefore, sometimes distrubution charts may be speculative.
## Calculating P-value with different methods
# Spearman Correlation
- This test gives better results when there is a correlation but the correlation is not linear.
- I calculated the result of Spearman correlation test with importing scipy library.
- P value is 0.0 and Spearman correlation is 0.567 which indicates there is a non-linear correlation between shark attacks and ocean temperatures, but that correlation.
- ![image](https://github.com/user-attachments/assets/cf6654d5-bef4-4b57-8927-4d363e7bfe28)

# Pearson Correlation
- This test gives better results when there is a linear correlation.
- Again I calculated the result by importing Scipy library.
- P value is again 0.0, Pearson correlation is 0.674, t-value is 7.062, and df is 60 because the length of the merged dataframe is 62 and there are two categories (62-2).
- ![image](https://github.com/user-attachments/assets/30057e28-3a63-4c08-8d86-36c51b5e697e)
- Since both p-values are smaller than 0.05, we have to reject HO.
## Code of Correlations : [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/bekircan4721/Bekircan_arac-/blob/main/Correlations.ipynb)

## Machine Learning
# My aim is that predicting the shark attack count for future years.
# Checking if the distributions are suitable for Machine learning
- Firstly I checked my most important feature Attack_count whether it has normal distribution
- I generated a histplot, and I conducted a K-S test for Attack_count and Temperature feature.
- When I do the tests,I found that the result of the Attack_count feature's histplot and K-S test was not suitable for normal distribution.
- But Ocean Temperature feature was suitable for normal distribution.
- I fixed the distribution of the Attack_count feature. Therefore, I can conduct some Machine Learning algorithms.
- ![image](https://github.com/user-attachments/assets/614fb38c-c08d-4e25-8b26-7cb6ac2f527b)
- As we can see from the image, the graph is skewed. Not suitable for normal distribution.
- ![image](https://github.com/user-attachments/assets/d0d6dcb9-69e6-4386-8904-01d844ea0739)
- Temperature distrubution is suitable for normal distribution.
- ![image](https://github.com/user-attachments/assets/0582a7b2-ba32-402e-8daf-84f46cf1d201)
- Taking logarithm seems worked for Attack_count feature, now it has better distrubiton for Machine learning models.
- ![image](https://github.com/user-attachments/assets/79e57125-5993-4ca8-a0cd-09cfaf0a9a4b)
- Moreover, as we can see from the image, the result of the K-S test and the p value for the Attack_count was not suitable for normal distribution because p < 0.05.
- After we take logarithm of the Attack_count feature, both Attack_count, and Temperature feature's p value become higher than 0.05 , which means suitable for machine learning.
# Linear Regression
- Firstly, I conducted Linear regression model for my normally distributed data for Attack_count(logarithm), and Temperature feature.
- This model performs well if there is a linear relationship between features.
- ![image](https://github.com/user-attachments/assets/aec9e374-9b00-4ff8-9642-b722ba0ea3c6)
- As we can see the result of the model is R^^2 is 0.39, and Mean square error is 0.1186
- Result of R^^2 which is 0.39 is not satisfying, only 39% percent of the data can be explained with this model
- Even though R^^2 is not satisfying, the mean square error(MSE) rate of this model is somehow acceptable
# Bootsrap Sampling
- After training the linear regression model, I conducted Bootstrap Sampling to enhance my model performance and stability.
-![image](https://github.com/user-attachments/assets/645cf2eb-ec73-44be-8edf-7fe6781f7c36)
- The result of the all generated sample's mean is similar to the linear regression , 0.4023 with the confidence Interval CI %95 (0.2113,5969). Which means that in the worst case scenario my model can only predicts 29% accuracy, and the best case scenario 59.69% accuracy which is not good enough.
- The Mean Square Error rate (MSE) is almost same with Linear Regression 0.1142 with 95% confidence Interval.
# Random Forest
- I decided to try Random Forest machine learning algorithm to catch the relationship between Attack_count, and Temperature features if the relationship is not linear.
- ![image](https://github.com/user-attachments/assets/d4b9cbe0-349b-4657-8da5-f74e4b414ef1)
- As we can see from the picture, this model has better R^^2 and MSE scores, which also means that the relationship is more likely to non-linear.
- Even though the result is better than Linear Regression , and Bootsrap sampling model, it still can only express the 54 % of the data which is still not good enough.

## Enriching Data To Get Better Model Results
# Adding Feature
- The R^^2 values were not good enough to explain my data, so I decided to enrich my data by adding features.
- Firstly, I checked shark_attack dataset's features with Ablation technique and I decided to enrich my data with the Country feature.
- ![image](https://github.com/user-attachments/assets/0e3dc541-92d1-4b54-b212-8a94771a942e)
- As we can see, most of the time best features are related with Country feature, thats why we enriched our data with Country feature.
- I extend my dataset with features Year, Attack_count_log, Temperature with Country, and I conducted Machine Learning models again to see whether adding feature actually worked.
- However, since Country feature is discrete, I firstly transformed that feature with one-hot encoding.
# Analyzing feature added data with corellation matrix
- ![image](https://github.com/user-attachments/assets/8871a3d1-5078-404b-bb4f-ae85f978be43)
- As we can see, my correlation matrix seems perfectly matched.
- Moreover, I generated a scatter plot to visualize the performance of a linear regression model. 
- ![image](https://github.com/user-attachments/assets/af506ea1-db03-44bb-b316-f5cacb0d02ac)
- Since I took the logarithm of attack_count feature, it seems like the performance of the model is bad, but it is not bad.
- Most data points are clustered around the red line, so linear regression model has learned the trend line well.
- I will calculate R^^2 of this model.
- [Open in Colab](https://colab.research.google.com/github/bekircan4721/Bekircan_arac-/blob/main/Visualizing_machine_learning.ipynb)

# Linear Regression With Added Feature(Country)
- ![image](https://github.com/user-attachments/assets/f784bad0-ec2f-4c30-88f5-a9285c4a23c5)
- Before adding the feature, the R^^2 and MSE were respectively 0.39 and 0.1186. After adding the Country feature, the R^^2 increased to 0.7561, while the MSE slightly increased to 0.1640.
- This time my Linear Regression model can explain my data with 75.6 % accuracy which is satisfying, and much better than the one without Country feature.
- Increase in the MSE is negligible, does not affect the model performance because increase in R^^2 tolerates it.
# Bootstrap Sampling With Added Feature(Country)
- ![image](https://github.com/user-attachments/assets/60432010-c305-469f-ae18-96578fa0a37b)
- Again, when I added the Country feature, average R^^2 value increased to 0.7899, and worst case scenario R^^2 value only decreased to 0.7559 which was 0.2113 before. And Best case scenario R^^2 value increased to 0.8234 with 95% confidence level.
- These R^^2 values are significantly better than the one that before, and it can almost explain my data 75% everytime which is acceptable.
- MSE rate is almost same with before, which indicates that eventhough R^^2 is significantly increased, my model's error rate does not affected.
# Random Forest With added Feature(Country)
- As I expected, the most significant improvement still occurred in the Random Forest method after adding the feature.
- ![image](https://github.com/user-attachments/assets/f522acc1-8754-46a0-aca1-1e82da5b989c)
- The R^^2 value increased to 0.89 which means this model almost predicts my data with 90% accuracy rate.
- Moreover, while the MSE rate remains at 0.073 (which is the lowest one), indicates that this model not only outperforms the other models, but also has most accurate predictions. Therefore, I conclude that this is currently the most suitable model for my data.
# Codes For these three comparison(part1)
- 🚀 [Open in Colab](https://colab.research.google.com/github/bekircan4721/Bekircan_arac-/blob/main/Machine_learning1.ipynb)
# Decision Tree Versus Random Forest
- As I expected, Random forest model performs better than Decision Tree model most of the time because Random Forest is a structure that evaluates multiple decision three , and choosing best features that improves the model by voting mechanism
- ![image](https://github.com/user-attachments/assets/a538b2d4-e17c-4dc7-8f66-7f57c607966a)
# Gradient Boosting
- I performed Gradient Boosting method with my feature added data, And the result is satisfying.
- R^^2 value is 0.8376, and MSE rate is 0.1092 which is not bad.
- ![image](https://github.com/user-attachments/assets/8ac6e39a-bb84-43ef-97dc-3a389ef77068)
- I tried to improve my model performance with Stochastic Gradient Descent.
- And the result of SGD did not significantly changed my model performance, but it increased R^^2 to 0.8414 and MSE rate decreased to 0.1067 which is a slight improvement
- ![image](https://github.com/user-attachments/assets/ad6c6bdc-5b77-42ee-a7e7-14fd19a7d041)
# Support Vector Machines
- I performed Support Vector Machines model to my data, and the R^^2 is 0.7591 , and MSE rate is 0.1620.
- The performance of this model for my data is not bad but compared to Random Forest, it has lower accuracy and higher error rate.
- ![image](https://github.com/user-attachments/assets/82694434-4daa-4761-8a0f-39d409b2d931)
# K-means Clustering
- Firstly I performed Hard clustering, and then re-performed Random Forest model to analyze the performance difference of hard clustering.
- R^^ result is 0.8918, and MSE rate is 0.0728 for Hard clustering which is really good.
- ![image](https://github.com/user-attachments/assets/9b1f4c9a-ae60-49a6-a2db-322ef6e698a2)

- Then I performed Flat clustering, and again re-performed Random Forest model to analyze the performance difference.
- R^^2 result is 0.8869 and MSE rate is 0.0788. Flat clustering performed almost as well as Hard clustering, but there is a little decrease in R^^2 and increase in MSE.
- ![image](https://github.com/user-attachments/assets/6766c21b-b576-4376-b4a3-2afc59ea85e1)
- Lastly, I performed Soft clustering, and I obtained the worst result from that model. R^^2 is 0.8829 ,and MSE rate is 0.0761.
- ![image](https://github.com/user-attachments/assets/b7444a79-c686-4231-bfaf-bace21ae4ab6)
- Statistics of the results are below.
- ![image](https://github.com/user-attachments/assets/089bb964-6b7f-43dc-9f53-d8a1917568d8)
- codes of the kmeans graphs : [Open K-Means Graphs in Colab](https://colab.research.google.com/github/bekircan4721/Bekircan_arac-/blob/main/kmeans_graphs.ipynb)

# Codes of part2
- [Open in Colab](https://colab.research.google.com/github/bekircan4721/Bekircan_arac-/blob/main/Machine_learning_part2.ipynb)




 



 









  




