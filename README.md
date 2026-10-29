                       MUTUAL FUND INDUSTRY ANALYSIS 

ABSTRACT
This project, titled Mutual Fund Industry Analysis Using Python, focuses on analysing mutual fund industry data to understand scheme characteristics, investor participation, fund flows, assets under management, and financial trends over time. The dataset contains 3,115 records and 14 features covering mutual fund schemes, scheme types, scheme categories, investor folios, fund mobilization, repurchase/redemption, net inflow/outflow, and Net Assets Under Management (AUM).
The project begins with data cleaning and preprocessing, including data type conversion, missing-value investigation, duplicate checking, text consistency checks, and identification of unusual financial records. Potential outliers are examined using the Interquartile Range (IQR) method. Financial anomaly detection is also performed to identify records containing unusual negative fund mobilization or repurchase/redemption values.
Exploratory Data Analysis (EDA) is performed using descriptive statistics, categorical analysis, distribution analysis, category-wise comparisons, correlation analysis, and visualizations. A monthly time-series dataset is then prepared to analyse changes in AUM, investor folios, and net inflow/outflow from April 2019 to July 2024.
The analysis provides insights into investor participation, scheme-level financial activity, AUM growth, net fund flows, volatility, and relationships between major mutual fund indicators.

1. INTRODUCTION
The Mutual Fund Industry Analysis project focuses on exploring and analysing mutual fund financial data using Python-based data analytics techniques.
The dataset contains information about mutual fund schemes, scheme types, scheme categories, number of schemes, investor folios, fund mobilization, repurchase/redemption, net inflow/outflow, and Net AUM. These variables provide an overview of fund activity, investor participation, and asset growth.
The project begins with data loading and preprocessing. The data is examined for missing values, duplicate records, inconsistent text values, incorrect data types, unusual numerical values, and potential financial anomalies. The IQR method is used to identify potential outliers without automatically treating them as errors.
Exploratory Data Analysis is then performed to understand the distribution of mutual fund schemes, investor participation, financial flows, and AUM across different scheme types and categories.
A time-series analysis is also performed by aggregating the data into monthly observations. This makes it possible to study the development of AUM, investor folios, fund flows, and their month-to-month changes over time.
The overall purpose of the project is to transform raw mutual fund data into meaningful financial insights using data cleaning, statistical analysis, visualization, and time-series techniques.

2. PROBLEM STATEMENT
The mutual fund industry generates large amounts of financial data related to investor participation, fund mobilization, repurchases and redemptions, net inflows and outflows, and assets under management (AUM). However, analyzing these variables over time can be challenging without proper data cleaning, statistical analysis, and visualization techniques.
The main problem addressed by this project is to identify meaningful trends, patterns, fluctuations, and relationships within mutual fund industry data from April 2019 to July 2024. The analysis aims to understand how AUM and investor folios have changed over time, identify periods of significant net inflows and outflows, examine variations across scheme types and categories, and detect unusual financial observations that may require further investigation.
By applying Python-based data analysis and time-series techniques, this project seeks to transform raw financial data into meaningful insights that support a clearer understanding of mutual fund industry performance and its changes over the study period.

3. PROJECT OBJECTIVES
The main objectives of this project are:
•	To clean and preprocess the mutual fund dataset.
•	To convert variables into appropriate data types for analysis.
•	To identify and investigate missing values and duplicate records.
•	To identify inconsistent text values and unnecessary whitespace.
•	To examine numerical variables using descriptive statistics.
•	To analyse mutual fund scheme types and scheme categories.
•	To study investor participation using the number of folios.
•	To analyse fund mobilization, repurchase/redemption, and net inflow/outflow.
•	To identify potential outliers using the IQR method.
•	To detect unusual financial records using anomaly detection.
•	To examine relationships between important financial variables using correlation analysis.
•	To perform monthly time-series analysis of AUM, folios, and net fund flows.
•	To visualize important patterns and trends using Python.
•	To generate meaningful insights from the mutual fund industry data.

4. DATASET DESCRIPTION
The dataset used in this project contains 3,115 records and 14 original columns related to mutual fund schemes.
The dataset source mentioned in the project notebook is the Indian Data Portal, based on an AMFI monthly report.
Indian Data Portal – AMFI Monthly Report
Important columns in the dataset
                   Column	                Description
id	Unique identifier for each record
scheme_name	Name of the mutual fund scheme
date	Date of the observation
scheme_type	Type of mutual fund scheme
scheme_category	Category of the mutual fund scheme
no_of_schemes	Number of schemes represented
no_of_folios	Number of investor folios
fund_mobilized	Amount of funds mobilized
repurchase_redemption	Amount of repurchase/redemption
net_inflow_outflow	Net inflow or outflow of funds
net_aum	Net Assets Under Management
avg_net_aum	Average Net AUM
no_of_segregated_portfolios	Number of segregated portfolios
net_aum_in_segregated_portfolios	Net AUM in segregated portfolios

The dataset contains 55 unique scheme names, 3 scheme types, and 5 scheme categories.

The three scheme types are:
•	Open ended Schemes
•	Close Ended Schemes
•	Interval Schemes

The five scheme categories are:
•	Income/Debt Oriented Schemes
•	Growth/Equity Oriented Schemes
•	Other Schemes
•	Hybrid Schemes
•	Solution Oriented Schemes

Derived Analytical Variables
Additional variables were created during analysis to examine changes over time:
•	AUM Change: Measures the month-to-month change in net AUM.
•	AUM Percentage Change: Calculates the percentage change in AUM between consecutive months.
•	Folio Growth: Measures changes in investor folios over time.
•	AUM Growth: Tracks the growth of assets under management.
•	Financial Anomaly Flag: Identifies unusual financial observations that require further investigation.
These variables support exploratory data analysis, correlation analysis, trend identification, time-series analysis, and anomaly detection.



5. TOOLS AND TECHNOLOGIES USED
The following tools and Python libraries were used in the project.

5.1 Google Colab
Google Colab was used as the development environment for writing and executing Python code, performing data analysis, and creating visualizations.

5.2 Python
Python was used as the main programming language for data cleaning, preprocessing, statistical analysis, and visualization.

5.3 Pandas
Pandas was used for:
•	Loading the dataset
•	Data cleaning
•	Handling missing values
•	Data type conversion
•	Grouping and aggregation
•	Time-series preparation
•	Statistical analysis

5.4 NumPy
NumPy was used for numerical calculations and working with numerical data.

5.5 Matplotlib
Matplotlib was used to create charts and graphs for visualizing financial trends and analytical results.



5.6 Seaborn
Seaborn was used for statistical visualizations such as:
•	Distribution plots
•	Box plots
•	Correlation heatmaps

6. DATA CLEANING AND PREPROCESSING
Data cleaning was performed before the main analysis to improve the quality and consistency of the dataset.

6.1 Data Type Conversion
The date column was initially treated as an object and was converted into a proper datetime format using Pandas. This enabled monthly and yearly time-series analysis.

6.2 Duplicate Checking
The dataset was checked for duplicate records.
The analysis showed:
•	Total records: 3,115
•	Unique IDs: 3,115
•	Duplicate IDs: 0
Therefore, no duplicate records based on the ID were identified.

6.3 Text Consistency
Categorical columns were examined for inconsistent text and unnecessary whitespace.
The final number of unique values was:
•	scheme_name: 55
•	scheme_type: 3
•	scheme_category: 5
Whitespace was removed from text fields to improve consistency.


6.4 Missing Value Analysis
Most important financial variables contained no missing values.
Missing values were found only in:
•	no_of_segregated_portfolios: 1,008
•	net_aum_in_segregated_portfolios: 1,008
The missing values in these two columns occurred simultaneously. They were retained as NaN rather than automatically replacing them with zero because replacing them would introduce an assumption about whether the missing values actually represented zero segregated portfolios.

6.5 Negative Value Investigation
Negative values were examined because some financial variables would normally be expected to have non-negative values.
The analysis identified:
•	fund_mobilized: 3 negative values
•	repurchase_redemption: 2 negative values
•	net_inflow_outflow: 1,157 negative values
Negative net inflow/outflow values can legitimately represent net outflows, so they were not treated as errors.

6.6 Net Flow Validation
The project verified the relationship:
Net Inflow/Outflow ≈ Fund Mobilized − Repurchase/Redemption
The calculated differences were extremely small, confirming that the net flow values were consistent with the underlying fund mobilization and redemption values.

6.7 Financial Anomaly Detection
A financial anomaly flag was created to identify records with negative fund mobilization or negative repurchase/redemption values.
The result was:
•	Normal records: 3,112
•	Potential financial anomalies: 3
These records were not automatically deleted because unusual financial values may require validation against the original source data.

6.8 Outlier Detection Using IQR
The IQR method was used to identify unusually high or low numerical observations.
The number of potential outliers included:
Variable	Potential Outliers
no_of_schemes	256
no_of_folios	318
fund_mobilized	409
repurchase_redemption	420
net_inflow_outflow	643
net_aum	161
avg_net_aum	150
no_of_segregated_portfolios	306
net_aum_in_segregated_portfolios	198
These observations were retained because an IQR outlier does not necessarily represent an error. Large mutual fund schemes can naturally have much higher AUM, folios, or fund flows than smaller schemes.

7. EXPLORATORY DATA ANALYSIS AND VISUALIZATION
Exploratory Data Analysis was performed to understand the structure, distribution, and financial characteristics of the mutual fund dataset.

7.1 Summary Statistics
The describe() function was used to examine:
•	Count
•	Mean
•	Standard deviation
•	Minimum
•	Maximum
•	Quartiles
The analysis showed that several financial variables were highly dispersed, particularly investor folios, AUM, and fund flows.

7.2 Scheme Type Analysis
The distribution of scheme types showed:
•	Open ended Schemes: 2,475
•	Close Ended Schemes: 448
•	Interval Schemes: 192
Open-ended schemes clearly dominate the dataset.
 
<img width="467" height="292" alt="image" src="https://github.com/user-attachments/assets/1a206753-165b-44bf-ac90-b65f205ca5f1" />




7.3 Scheme Category Analysis
The distribution of scheme categories was:
•	Income/Debt Oriented: 1,344
•	Growth/Equity Oriented: 875
•	Other: 384
•	Hybrid: 384
•	Solution Oriented: 128
 
<img width="485" height="321" alt="image" src="https://github.com/user-attachments/assets/893da11e-70fb-4733-b265-709e5db1d139" />


Income/Debt Oriented Schemes had the largest number of observations, while Solution Oriented Schemes had the smallest.





7.4 Number of Schemes Analysis
The number of schemes was strongly right-skewed.
The mean was approximately 32.90, while the median was 22. The maximum value reached 800.

 <img width="459" height="291" alt="image" src="https://github.com/user-attachments/assets/639e2091-efbf-49f5-9c16-e7b17ed97be1" />


This indicates that most observations contain relatively smaller numbers of schemes, while a smaller number of observations contain substantially higher values.

7.5 Investor Participation Analysis
The number of investor folios was also strongly right-skewed.
The median was approximately 521,606, while the mean was approximately 2.52 million.
 
<img width="469" height="298" alt="image" src="https://github.com/user-attachments/assets/3fa6ab2c-3a88-4587-b5df-edbba8b065dc" />

This difference indicates that a relatively small number of observations have exceptionally high investor participation.

7.6 Investor Participation by Scheme Category
Growth/Equity Oriented Schemes recorded the highest total investor folios at approximately 5.40 billion in the dataset.

<img width="461" height="260" alt="image" src="https://github.com/user-attachments/assets/a659167e-a22d-46bf-8d49-f15d4c395c02" />

This indicates that the Growth/Equity category had the largest recorded investor participation among the categories analysed.

7.7 Net AUM by Scheme Category
Income/Debt Oriented Schemes recorded the highest total Net AUM at approximately 87.78 million, followed closely by Growth/Equity Oriented Schemes at approximately 85.87 million.
 
<img width="485" height="274" alt="image" src="https://github.com/user-attachments/assets/9076e098-b173-479d-ac0b-518ed2a90ed8" />

An interesting observation is that Growth/Equity schemes had substantially more recorded folios, while Income/Debt schemes had slightly higher total AUM.

7.8 Net Inflow/Outflow Analysis
Net inflow/outflow showed considerable variation.
The dataset-level statistics included:
•	Mean: 473.37
•	Median: 26.85
•	Minimum: −157,970.38
•	Maximum: 102,751.50
 
<img width="458" height="299" alt="image" src="https://github.com/user-attachments/assets/fb57ba3b-40d4-4d2e-98c0-36b869c01f49" />

The wide difference between the mean and median indicates that extreme financial movements influence the distribution.

7.9 Net Inflow/Outflow by Category
Growth/Equity Oriented Schemes recorded the highest total net inflow at approximately 653,403, followed by Other Schemes at approximately 540,091.
 
<img width="473" height="270" alt="image" src="https://github.com/user-attachments/assets/2c701f3d-455a-4a37-86bd-c2ddc03c282e" />

Hybrid Schemes also recorded positive net inflows, while Income/Debt and Solution Oriented Schemes recorded comparatively smaller positive net inflows.

7.10 Fund Mobilization vs Repurchase/Redemption
Income/Debt Oriented Schemes recorded the highest fund mobilization at approximately 58.72 million, closely followed by repurchase/redemption at approximately 58.71 million.
 
<img width="467" height="251" alt="image" src="https://github.com/user-attachments/assets/6b6473ff-dc3b-43e1-b4df-c6da2f64cbcb" />

Overall, fund mobilization and repurchase/redemption were relatively close within the categories, showing that a substantial portion of mobilized funds was offset by redemptions.

7.11 Distribution Analysis
Histograms and box plots were used to analyse Net AUM and investor folios.
 
 <img width="474" height="345" alt="image" src="https://github.com/user-attachments/assets/9250c034-31e8-497f-802a-53cd56f91613" />


Both variables showed strong right-skewed distributions, with long upper tails.
<img width="467" height="173" alt="image" src="https://github.com/user-attachments/assets/3f7b7d11-b65c-4050-a396-b3d8d0d3dbec" />
 

The log-transformed visualizations helped make smaller observations easier to compare with very large observations. However, the transformation was used only for visualization and did not remove or modify the original outliers.

7.12 Correlation Analysis
Correlation analysis was used to examine relationships between important financial variables.
In the monthly dataset:
•	AUM and folios: 0.973
•	AUM and net inflow/outflow: 0.237
•	Folios and net inflow/outflow: 0.167
 
<img width="463" height="322" alt="image" src="https://github.com/user-attachments/assets/9cf869cf-8c55-46d4-a08a-d92bde191129" />

The very strong relationship between AUM and folios indicates that both generally increased together over the analysed period.
The relationship between total AUM/folios and net flow was comparatively weak.


8. TIME SERIES ANALYSIS
Time-series analysis was performed by aggregating the data into monthly observations.
The final monthly dataset contained:
•	64 monthly observations
•	Date range: April 2019 to July 2024
•	No duplicate dates

The analysis focused on AUM, investor folios, fund flows, monthly changes, annual growth, and volatility.

8.1 Monthly AUM Trend
The monthly analysis showed an overall upward movement in Net AUM, although the trend included several periods of decline.
The first monthly AUM was approximately 2,478,756.91, while the latest value was approximately 6,496,653.14.
The overall increase was 162.09%.
 <img width="481" height="201" alt="image" src="https://github.com/user-attachments/assets/981f2ad9-62db-40f8-9b1e-8989a591c633" />


8.2 Monthly AUM Growth
The largest monthly AUM decline occurred in March 2020, when AUM decreased by approximately 18.24%.
The highest monthly percentage increase occurred in April 2020, at approximately 7.51%.
The largest absolute monthly AUM decrease was March 2020: −496,734.47
The largest increase was April 2024: +385,703.32
 
<img width="472" height="196" alt="image" src="https://github.com/user-attachments/assets/9b36af0d-7a51-4a5a-a801-3892cda12d55" />


8.3 Annual AUM Growth
The year-end AUM values showed consistent long-term growth:
Year	Year-End AUM	AUM Growth
2019	2,654,074.81	—
2020	3,102,475.48	16.89%
2021	3,772,696.31	21.60%
2022	3,988,735.40	5.73%
2023	5,077,900.35	27.31%
2024*	6,496,653.14	27.94%
*2024 contains data only through July.
The highest annual AUM growth was observed in 2024 at 27.94%, while the lowest was 2022 at 5.73%.

 <img width="468" height="232" alt="image" src="https://github.com/user-attachments/assets/3c9f791f-8073-4ab1-b2fc-82c3ca35bae1" />



8.4 Investor Folio Trend
Investor participation also increased considerably.
The number of folios increased from:
82,736,339 → 198,406,294
This represents an overall growth of 139.81%.
The highest monthly folio increase occurred in July 2024, with an increase of approximately 
7.36 million folios.
The lowest monthly folio growth occurred in November 2020, with a small decline of approximately 0.04%.
 <img width="455" height="193" alt="image" src="https://github.com/user-attachments/assets/d0ef95b8-82b8-4e48-948d-bb22ac40f3bb" />


8.5 Annual Folio Growth
The highest annual folio growth occurred in 2021 at 27.42%.
The lowest annual growth occurred in 2020 at 8.27%.
Overall, the number of investor folios increased substantially throughout the study period.

8.6 Monthly Net Inflow/Outflow Trend
Across the 64 months:
•	42 months recorded net inflows.
•	22 months recorded net outflows.
•	No month recorded exactly zero net flow.
Therefore:
•	Positive-flow months: 65.62%
•	Negative-flow months: 34.38%
This indicates that positive net fund flows occurred more frequently than negative flows.

8.7 Highest and Lowest Monthly Net Flows
The highest monthly net inflow occurred in April 2024: +239,232.85
The lowest monthly net flow occurred in March 2020: −212,737.09
These represent the two most extreme monthly fund-flow movements in the time-series analysis.

8.8 Calendar Month Analysis
Average net flow by calendar month showed considerable variation.
The strongest average net flow was recorded in April: +112,146.68
The weakest average net flow was recorded in March: −98,203.44
This pattern suggests that certain calendar months experienced stronger or weaker average flows within the available historical data. However, the result should not be interpreted as a universal seasonal pattern without a longer and more complete dataset.
 <img width="463" height="201" alt="image" src="https://github.com/user-attachments/assets/a5ac32e9-4b89-49ef-8402-eba1043e682e" />


8.9 Net Flow Volatility
The average monthly net flow was approximately 23,039.76, while the standard deviation was approximately 81,540.08.
The coefficient of variation was approximately 353.91%.
This indicates substantial month-to-month variation in net fund flows. The coefficient of variation should be interpreted cautiously because net flow can take both positive and negative values.
The distribution also showed:
•	Mean: 23,039.76
•	Median: 19,462.60
•	Skewness: −0.3483
•	Kurtosis: 0.9870
The negative skewness indicates a slightly longer negative tail, while the positive kurtosis indicates heavier tails than a normal distribution.

8.10 AUM Change vs Net Inflow/Outflow
The correlation between monthly AUM change and net inflow/outflow was 0.784.
This represents a strong positive relationship.
It indicates that months with higher net inflows generally tended to experience larger increases in AUM. However, the relationship is not perfect because AUM can also be affected by other factors such as changes in asset values.
 <img width="467" height="294" alt="image" src="https://github.com/user-attachments/assets/b975dd26-6eb0-45ef-a683-6f4e11cb82dc" />


Monthly AUM changes and net inflow/outflow generally moved in the same direction, with a strong positive correlation of 0.784. This indicates that months with higher net inflows tended to experience larger increases in AUM, although the two measures did not move identically in every month.

8.11 Folio Growth vs Net Flow
The correlation between monthly folio growth and net inflow/outflow was 0.2096.
This indicates a weak positive relationship.
Therefore, increases in investor folios were somewhat associated with higher net flows, but the relationship was not strong and does not establish causation.







8.12 AUM Growth vs Folio Growth
The correlation between monthly AUM growth and folio growth was 0.3097.
This represents a weak positive relationship.
 
 The result suggests that months with larger increases in investor folios tended to coincide somewhat with increases in AUM, but the relationship was not strong.

<img width="331" height="331" alt="image" src="https://github.com/user-attachments/assets/633f80df-88b0-4e0e-9c99-b67fdde04577" />




9. KEY FINDINGS AND INSIGHTS
The major findings from the project are:
1. Strong overall AUM growth
Net AUM increased by 162.09% between April 2019 and July 2024, showing substantial long-term growth in assets under management.
2. Significant growth in investor participation
The number of investor folios increased by 139.81%, from approximately 82.74 million to 198.41 million.
3. Open-ended schemes dominate
Open-ended schemes accounted for 2,475 of the 3,115 observations, making them the dominant scheme type in the dataset.
4. Income/Debt schemes have the largest representation
Income/Debt Oriented Schemes recorded 1,344 observations, the highest among the five scheme categories.
5. Growth/Equity has the highest recorded investor participation
Growth/Equity Oriented Schemes recorded the highest total investor folios, approximately 5.40 billion.
6. Income/Debt has slightly higher total AUM
Income/Debt Oriented Schemes recorded approximately 87.78 million in total AUM, slightly higher than Growth/Equity Oriented Schemes at approximately 85.87 million.
7. Positive-flow months were more frequent
Out of 64 months, 42 months had positive net flows, compared with 22 months having negative net flows.
8. March 2020 showed a major decline
March 2020 recorded both the lowest monthly net flow, −212,737.09, and the largest monthly AUM decline, −496,734.47.
9. April 2024 recorded the strongest monthly net inflow
The highest monthly net inflow was 239,232.85 in April 2024.
10. AUM and net flow have a strong relationship
Monthly AUM change and net inflow/outflow had a correlation of 0.784, indicating that net fund flows were strongly associated with changes in AUM.
11. Investor growth and financial flows have weaker relationships
Folio growth and net flow had a correlation of 0.2096, while AUM growth and folio growth had a correlation of 0.3097.
12. Financial data contains substantial variation
Net flows, AUM, and folios showed significant variation and right-skewed distributions, highlighting differences between smaller and larger mutual fund observations.

10. CONCLUSION
The Mutual Fund Industry Analysis Using Python project was carried out to understand mutual fund scheme characteristics, investor participation, fund flows, AUM, and their changes over time.
The dataset was cleaned and analysed using Python, Pandas, NumPy, Matplotlib, and Seaborn. The analysis included missing-value investigation, duplicate checking, data consistency checks, outlier detection, financial anomaly detection, descriptive statistics, categorical analysis, correlation analysis, and time-series analysis.
The results show that the mutual fund industry represented in the dataset experienced substantial growth between April 2019 and July 2024. Net AUM increased by 162.09%, while investor folios increased by 139.81%.
Open-ended schemes dominated the dataset, while Income/Debt Oriented Schemes had the largest number of observations. Growth/Equity Oriented Schemes recorded the highest total investor participation, whereas Income/Debt Oriented Schemes recorded slightly higher total AUM.
The time-series analysis showed that positive net-flow months were more frequent than negative months. However, substantial volatility was observed in monthly fund flows and AUM. March 2020 represented the strongest negative movement, while April 2024 represented the strongest positive monthly net flow.
The strong correlation between monthly AUM change and net inflow/outflow indicates that fund flows are an important factor associated with changes in AUM. At the same time, the weaker relationships between folio growth and net flows suggest that investor count alone does not fully explain changes in fund flows or AUM.
Overall, the project provided practical experience in data cleaning, exploratory data analysis, statistical analysis, anomaly detection, visualization, and time-series analysis using Python.



11. LIMITATIONS
The project has the following limitations:
•	Data availability: The analysis is limited to the records available in the dataset.
•	Time coverage: The time-series analysis covers April 2019 to July 2024, with 2024 containing only January–July observations in the monthly analysis.
•	Missing values: The two segregated portfolio variables contain missing values that were retained because their meaning could not be confirmed from the dataset alone.
•	Potential anomalies: Three financial records were identified as potential anomalies, but they were not removed because their validity could not be established without source verification.
•	Outliers: Several variables contain IQR-based outliers. These were retained because extreme values may represent genuine differences in scheme size or financial activity.
•	Correlation limitations: Correlation identifies association between variables but does not establish causation.
•	Limited external factors: The dataset does not contain sufficient information about external factors such as market conditions, economic events, investor sentiment, interest rates, or policy changes that could influence mutual fund performance.
•	Partial-year comparison: 2024 results should be interpreted carefully because the available monthly analysis covers only part of the year.

12. FUTURE SCOPE
The project can be extended in the following ways:
•	Live data integration: Connect the analysis to regularly updated mutual fund data to monitor current industry trends.
•	Predictive analysis: Apply machine learning or time-series forecasting techniques to predict future AUM and fund flows.
•	Advanced dashboards: Develop an interactive dashboard using Power BI or another visualization platform.
•	Scheme-level forecasting: Forecast AUM, folio growth, and net flows for individual scheme categories.
•	Seasonality analysis: Investigate whether the observed monthly patterns continue across a longer historical period.
•	External factor analysis: Combine mutual fund data with market indices, interest rates, inflation, or other economic indicators.
•	Advanced anomaly detection: Apply statistical or machine-learning methods to identify unusual financial observations more systematically.
•	Category-level trend analysis: Compare long-term performance and growth patterns across equity, debt, hybrid, and other scheme categories.
•	Risk analysis: Introduce additional financial indicators to evaluate volatility and risk across different scheme categories.
•	Automated reporting: Create an automated analytical pipeline that regularly updates the dataset and generates reports.

13. REFERENCES
Dataset Source: Indian Data Portal – AMFI Monthly Report
Indian Data Portal – AMFI Monthly Report
Google Colab: Used as the Python development and analysis environment.
Pandas: Used for data loading, cleaning, preprocessing, aggregation, and analysis.
NumPy: Used for numerical operations and calculations.
Matplotlib: Used for creating charts and time-series visualizations.
Seaborn: Used for statistical visualizations, box plots, and correlation heatmaps.
 
