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
 - Top 10 Shark attack location
 - ![image](https://github.com/user-attachments/assets/29cf6877-ce43-490d-89e4-9b6a3f542314)
 - Code of most 10 Shark attack location: [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/bekircan4721/Bekircan_arac-/blob/main/Shark_locations.ipynb)
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
## Projeyi Google Colab Üzerinde Çalıştır



  




