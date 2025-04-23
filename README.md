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
 - Firstly I started cleaning the shark attack dataset because there were some missing values in Year category, which is the most important category for this project.
 - I visiualized the year and shark attack count at that year
 - ## Yearly Shark attacks
 - [![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/bekircan4721/Bekircan_arac-/blob/main/shark_year.ipynb)
 - I filtered both the shark attacks dataset and temperature dataset, then I merged them.
 - After I merged these datasets, I explored the data by plotting scatterplot distribution of yearly shark_attacks  vs ocean temperature
 - Then I calculated the correlation.
 - ## Shark attack vs Temperature
 - [![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/bekircan4721/Bekircan_arac-/blob/main/shark_year.ipynb)

![image](https://github.com/user-attachments/assets/fb8216bb-578c-48a6-8827-37173cfd1605)

![image](https://github.com/user-attachments/assets/63e748f6-9d49-4bce-a389-37811eb34a7a)

![image](https://github.com/user-attachments/assets/b3c7d4c1-9361-40bd-95e5-a74e09ed6aed)

![image](https://github.com/user-attachments/assets/7596f842-4cf7-436a-bd76-d0b19e8e5fc8)
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
## Projeyi Google Colab Üzerinde Çalıştır

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1M7SLQ2iKRxZwDdhksx-xweh42c_FPsWO?authuser=0#scrollTo=lumaOt79L19q)

  




