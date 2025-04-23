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
 - I filtered both the shark attacks dataset and temperature dataset, then I merged them.
 - After I merged these datasets, I calculated the correlation score.
 - Then I calculated the correlation.
 - I visiualized the merged dataset with multiple techniques like scatterplot, histogram, boxplot.
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
- [Uploaimport pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
import numpy as np
from scipy.stats import pearsonr, ttest_ind, spearmanr,t
pd.set_option('display.max_rows', None)
pd.set_option('display.max_columns', None)

# reading datasets
data_shark = pd.read_csv("attacks.csv", encoding="unicode_escape")  # veya "ISO-8859-1"
data_temperature = pd.read_table("https://www.ncei.noaa.gov/data/oceans/woa/DATA_ANALYSIS/3M_HEAT_CONTENT/DATA/basin/pentad/pent_h22-w0-2000m.dat", delim_whitespace=True)

# filtering by year
data_shark = data_shark[data_shark["Year"].notnull()]
print(data_shark.info())

# yearly ocean temperatures
temperature_by_year = data_temperature[["YEAR", "WO"]].copy()
temperature_by_year.columns = ["Year", "Ocean_Temperature"]
temperature_by_year["Year"] = temperature_by_year["Year"].round().astype(int)

# Get shark attacks by year
shark_by_year = data_shark.groupby("Year").size().reset_index(name="Attack_Count")

# Merge datasets based on Year
merged = pd.merge(shark_by_year, temperature_by_year, on="Year", how="left")

# Drop rows with missing ocean temperature data // evet artıyor genelde
merged = merged.dropna(subset=["Ocean_Temperature"])

print(merged.isna().sum())

# correlation
correlation = merged["Ocean_Temperature"].corr(merged["Attack_Count"])
print(f"correlation between Ocean temperature and shark attacks: {correlation:.3f}")

# Scatter plot for Ocean Temperature vs Shark Attack Count
plt.figure(figsize=(10, 6))
sns.scatterplot(x='Ocean_Temperature', y='Attack_Count', data=merged, color='blue')

plt.title('Shark attacks and the Ocean Temperature', fontsize=16)
plt.xlabel('Ocean Temperature (°C)', fontsize=12)
plt.ylabel('Shark Attack Count', fontsize=12)

plt.tight_layout()
plt.show()

# Bin ocean temperature for grouping (for better readability on x-axis) with 0.5°C intervals
standart_variaton = merged["Ocean_Temperature"].std()
merged['Temperature_Binned'] = pd.cut(merged['Ocean_Temperature'], bins=np.arange(merged['Ocean_Temperature'].min(), merged['Ocean_Temperature'].max() +0.1,standart_variaton*0.18), right=False)

# Group by binned temperature and sum attack counts
binned_data = merged.groupby('Temperature_Binned')['Attack_Count'].sum().reset_index()

# Bar plot for Shark Attack Count vs Ocean Temperature
plt.figure(figsize=(12, 6))
sns.barplot(x='Temperature_Binned', y='Attack_Count', data=binned_data, color='green')

plt.title('Shark Attack Count by Ocean Temperature', fontsize=16)
plt.xlabel('Ocean Temperature (°C)', fontsize=12)
plt.ylabel('Shark Attack Count', fontsize=12)

plt.xticks(rotation=90)  # Rotate x-axis labels for better visibility
plt.tight_layout()
plt.show()


# Boxplot for Ocean Temperature vs Shark Attack Count
# Boxplot for Ocean Temperature vs Shark Attack Count
plt.figure(figsize=(12, 6))

# Bin ocean temperature for grouping with the desired interval
merged['Temperature_Binned'] = pd.cut(merged['Ocean_Temperature'], bins=np.arange(merged['Ocean_Temperature'].min(), merged['Ocean_Temperature'].max() + 0.1, standart_variaton*0.4), right=False)

# Boxplot to show the distribution of attack counts for each temperature bin
sns.boxplot(x='Temperature_Binned', y='Attack_Count', data=merged, palette='Set2')

# Grafik başlığı ve etiketler
plt.title('Ocean Temperature and Shark Attacks', fontsize=16)
plt.xlabel('Ocean Temperature (°C)', fontsize=12)
plt.ylabel('Shark Attack Count', fontsize=12)

plt.xticks(rotation=90)  # X ekseni etiketlerini döndürme
plt.tight_layout()
plt.show()


 #Pearson korelasyonunu al
r, _ = pearsonr(merged['Ocean_Temperature'], merged['Attack_Count'])

# Gözlem sayısı
n = len(merged)

# Serbestlik derecesi
df = n - 2

# t-değeri
t_stat = r * np.sqrt(df) / np.sqrt(1 - r**2)

# İki kuyruklu p-değeri
p_value = 2 * t.sf(np.abs(t_stat), df)

print(f"Pearson Correlation (r): {r:.3f}")
print(f"t-value: {t_stat:.3f}")
print(f"degrees of freedom (df): {df}")
print(f"p-value: {p_value:.4f}")
ding proje.jpynb…]()





  




