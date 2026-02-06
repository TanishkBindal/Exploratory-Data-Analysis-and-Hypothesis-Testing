
# Exploratory Data Analysis (EDA) and Hypothesis Testing on Taxi Cab Payment Methods

## 📋 Project Overview
This project's main goal is to run an A/B test to examine the relationship between the total fare and the method of payment. We use Python hypothesis testing and descriptive statistics to extract useful information that can help taxi drivers generate more cash. In particular, we want to find out if there is a big difference in the fares for those who pay with credit cards versus those who pay with cash.

## Table of Contents
- [Problem Statement](#problem-statement)
- [Tools and Technologies Used](#tools-and-technologies-used)
- [ETL Process](#etl-process)
- [Data Analysis](#data-analysis)
- [Queries](#queries)
- [Conclusion](#conclusion)


## 🤔 Problem Statement
In the fast-paced taxi booking sector, making the most of revenue is essential for long-term success and driver happiness. Our goal is to use data-driven insights to maximise revenue streams for taxi drivers in order to meet this need. Our research aims to determine whether payment methods have an impact on fare pricing by focusing on the relationship between payment type and fare amount.

## 🛠️ Tools and Technologies Used
![Microsoft Excel](https://img.shields.io/badge/Microsoft_Excel-217346?style=for-the-badge&logo=microsoft-excel&logoColor=white)&nbsp;
![Jupyter Notebook](https://img.shields.io/badge/jupyter-%23FA0F00.svg?style=for-the-badge&logo=jupyter&logoColor=white)&nbsp;
![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=yellow)&nbsp;
![Pandas](https://img.shields.io/badge/pandas-%23150458.svg?style=for-the-badge&logo=pandas&logoColor=white)&nbsp;
![Matplotlib](https://img.shields.io/badge/Matplotlib-%23ffffff.svg?style=for-the-badge&logo=Matplotlib&logoColor=blue)&nbsp;
[![Seaborn](https://img.shields.io/badge/Seaborn-3776AB?style=for-the-badge&logo=seaborn&logoColor=white)](https://seaborn.pydata.org/)&nbsp;
![SciPy](https://img.shields.io/badge/SciPy-%230C55A5.svg?style=for-the-badge&logo=scipy&logoColor=%white)&nbsp;


## 📊 Steps Performed
🔹**Data Loading and Initial Exploration -**

• Imported required libraries: pandas, matplotlib, seaborn, scipy.stats, statsmodels, warnings.<br>
• Loaded the dataset: yellow_tripdata_2020-01.csv using pd.read_csv().<br>
• Displayed first and last few rows using head() and tail().<br>
• Checked the shape of the dataset to understand the number of rows and columns.

🔹**Feature Engineering -**<br>

• Converted tpep_pickup_datetime and tpep_dropoff_datetime to datetime objects.<br>
• Calculated trip duration in minutes by subtracting pickup from dropoff time.<br>
• Added this new duration column to the dataframe.<br>

🔹**Data Cleaning -**<br>

• Dropped irrelevant columns such as vendor ID, rate code, and various surcharges.<br>
• Checked and counted missing values.<br>
• Dropped rows with missing values (only ~1% of data).<br>
• Converted passenger_count and payment_type to integer types.<br>
• Remove duplicate rows from the dataset.<br>

🔹**Data Filtering -**<br>

• Kept only relevant payment_type values: 1 (Credit Card) and 2 (Cash).<br>
• Filtered passenger_count to keep records with values from 1 to 5.<br>
• Replaced numeric payment types :<br>
  → 1 → 'Card'<br>
  → 2 → 'Cash'<br>

🔹**Further Cleaning for Valid Data -**<br>

• Removed rows with non-positive values of fare_amount, trip_distance, and duration.<br>

🔹**Outlier Detection and Removal -**<br>

• Used boxplot to visually inspect outliers for fare_amount vs payment_type.<br>
• Applied IQR (Interquartile Range) method to remove outliers from :<br>
  → trip_distance<br>
  → fare_amount<br>
  → duration<br>

🔹**Exploratory Data Analysis (EDA) -**<br>

• Plotted histograms to visualize distribution of :<br>
  → fare_amount for Card and Cash<br>
  → trip_distance for Card and Cash<br>
• Used .groupby() to compute mean and standard deviation of fare and distance for each payment type.<br>
• Created a pie chart to show proportion of payment types.<br>
• Visualized passenger count distribution by payment type using a stacked horizontal bar plot with percentages.<br>

🔹**Hypothesis Testing -**<br>

• Created a Q-Q plot to check normality of fare_amount. The data was not normally distributed.<br>
• Decided to use T-Test (instead of Z-Test) as :<br>
  → Population standard deviation is unknown.<br>
  → Data is not normal.<br>
  → T-test is appropriate for large and small samples.<br>

🔹**Performing T-Test -**<br>

• Created two samples :<br>
  → credit_card = fare_amount for payment type 'Card'<br>
  → cash = fare_amount for payment type 'Cash'<br>
• Performed independent T-Test using :<br>
  stats.ttest_ind(a=credit_card, b=cash, equal_var=False)<br>
• Printed T-statistic and P-value.<br>
• Compared p-value with 0.05 :<br>
  → If p < 0.05 : Reject Null Hypothesis → Significant difference in fare based on payment type.<br>
  → Else : Accept Null Hypothesis → No significant difference.<br>

## 🔑 Key Insights<br>
• Customers paying with cards tend to have a slightly higher average trip distance and fare amount
compared to those paying with cash.<br>

• Indicates that customers prefers to pay more with cards when they have high fare amount and
long trip distance.



## 💻 Usage<br>
**To replicate the analysis, take the following Steps :**<br>

→ Clone this repository to your local machine.<br>
→ Navigate to the project directory.<br>
→ Install the required dependencies using `pip install -r requirements.txt`.<br>
→ Run the Jupyter notebooks in the `notebooks/` directory to perform data analysis and extract information.<br>
→ Review the results and conclusions drawn from the EDA and hypothesis testing.<br>

## 📝 Conclusion 
Through comprehensive EDA and hypothesis testing, it is concluded that there is a statistically significant difference in the average fare amount between customers who use credit cards and customers who use cash.
The key business insight is that encouraging customers to pay with credit cards can generate more revenue for taxi cab drivers.

<br />

<div align="left">
<h2>Connect with me <a href="https://gifyu.com/image/Zy2f"><img src="https://github.com/milaan9/milaan9/blob/main/Handshake.gif" width="50px"></a>
</h2>
<p align="left">
 
 [<img src = "https://cdn.pixabay.com/photo/2022/01/30/13/33/github-6980894_640.png" width ="55" height ="55" align = "center" style= "postion:relative">](https://github.com/TanishkBindal)&nbsp;&nbsp;&nbsp;&nbsp;
[<img src = "https://upload.wikimedia.org/wikipedia/commons/thumb/f/f8/LinkedIn_icon_circle.svg/1024px-LinkedIn_icon_circle.svg.png" width ="55" height ="85" align = "center" style= "postion:relative">](https://www.linkedin.com/in/tanishk-bindal)
[<img src = "https://static.vecteezy.com/system/resources/previews/066/118/531/non_2x/linktree-circle-logo-icon-linktree-app-editable-transparent-background-premium-social-media-design-for-digital-download-free-png.png" width ="90" height ="280" align = "center" style= "postion:relative">](https://linktr.ee/tanishkbindal)

 
 <p align="right">(<a href="#top">Back to top</a>)</p>
</p> 




































