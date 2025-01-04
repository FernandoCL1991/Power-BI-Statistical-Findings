# Power-BI-Statistical-Findings

# Data Analysis Project: Target Contributions by Class and Year

## Link to Project: [https://app.powerbi.com/groups/me/reports/095baa62-26b7-4498-99af-bbbfc5fddab7/7543321a26c965164723?experience=power-bi](https://app.powerbi.com/groups/me/reports/194933ab-58ba-40f9-9f23-917a22f8ddc6/7543321a26c965164723?experience=power-bi)

## https://app.powerbi.com/groups/me/reports/194933ab-58ba-40f9-9f23-917a22f8ddc6/7543321a26c965164723?experience=power-bi


## Project Overview

This project involves performing a detailed analysis of a dataset to understand how various image classes contribute to the yearly target. Using Power BI and Python, visualizations and calculations were created to derive insights about patterns and correlations in the data.

## Key Objectives

1. Calculate the yearly contribution of each image class to the overall target.
2. Visualize the contributions using a stacked column chart and other Power BI visuals.
3. Perform correlation and exploratory data analysis to uncover trends and relationships.

## Tools and Technologies

- **Power BI**: For interactive data visualization and dashboard creation.
- **Python**: Used within Power BI for creating heatmaps and performing correlation analysis.
- **GitHub**: Repository for storing and sharing the project.

## Steps Performed

## Pre-step

- A connection to a Microsoft Azure DB was established.
- **Training** data table was retrieved for the anaysis.

### 1. Data Preparation

- A **Date Table** was created in Power BI with columns for Year, Month, and other date-specific fields.
- A new **Year** column was derived for easier aggregation.
- Relationships were established between the Date Table and the Training Table.
- A new table was created **Aggregated Class Target** specific to how classes contributed overall towards Target and had a many-yo-many relationship to Training Table.
- A **Unique Years** table was created to enhance the performance of different visualizations with a one-to-many relationship to Aggregated Class Target table and another to the Date Table.
- **Data types** were changed correspondingly.
- **Image Classes Bins** were created to synthesize classes into more concise groups. The groups created were: Animals, Innanimate Objects, Nature, Person, and Vehicles.


### 2. Calculation of Yearly Class Contribution

- Created a new aggregated table in Power BI (**Aggregated Class Target**) using DAX to calculate yearly contributions.
- The formula ensured contributions were scaled to represent percentages (from 0% to 100%) for accurate representation.

### 3. Visualizations

#### Stacked Column Chart:

- **X-Axis**: Year (from Unique Years table)
- **Column Y-Axis**: Yearly Class Contribution (from Aggregated Class Target table)
- **Column Legend**: Image Class or Image Class Groups (from Aggregated Class Target table)

#### Correlation Heatmap:

- All variables ploted along with the Target variable
- The heatmap was created using Python's Seaborn library

#### Box and Whiskers Plots:

- Created to visually analyze outliers in the data
- Tooltips were created to hover on every data point in the plot
- Made for every single variable in the dataset
- Depending on the Year and Class filtering applied with the slicers, different outliers can be seen in each variable

#### Scatter Plots

- Created to visually see all the data points and their distribution along the specified X and Y ranges
- Created to detect patterns in the data
- Tooltips were created to hover on every data point in the plot

#### Heatmap for Binary Variables

- Created to visually see the accumulation (count) of instances accross time

#### Histogram:

- Created to analyze the distribution of binary variables over time showing the total count of instances

### 4. Advanced Insights

- Derived metrics for annualized target values and class-wise contributions.
- Incorporated filters to ensure consistent analysis across dashboards.
- Adjusted relationships and resolved duplication errors for smoother integration of new calculated tables.

## Challenges Faced

1. A lack of context behind dataset and variables impeded a more refined analysis and conclusions.
2. Inconsistent time periods where the data spans from March 2016 to February 2019. A more consisten time frame would allow for clearer trend and seasonality analysis.
3. Different types of variables were encountered: continuous variables and binary variables made analysis not as straight forward; different data modeling techniques needed to be used.
4. Log scaling: was applied to binary variables so to be able to compare them using the same order of magnitude in a single analysis (clustered column chart).
5. Establishing relationships between tables due to duplicate values in columns.
6. No incomplete data was found although partially complete years were something to account for.
7. Converting categorical values to numerical representations for analysis.
8. Handling of outliers: a decision was made to leave outliers as is given that the data is most probable to be medical related, hence the outliers can give a better understanding of rare effects on instances.

## Key Findings

- Image classes contributed similarly accross time (month and years) towards the Target variable, except for the Person class which only contributed towards Target with 5,374,823.31, while every other class contributed from a range of 10 to 14,000,000 towards Target. This has to do with how classes were distributed to each class group were 2 or more classes were added to classes, only 1 class was added to the 'Person' class.
- Scatter Plots accross all variables didn't show uniform distributions.
- Since the data spans from March 2016 to February 2019, a consistent trend or seasonality couldn't be seen. The years of 2016 and 2019 need to have more data for a deeper analysis. For those 'complete' years with data accross all months, an overall similar trend accross all continuous variables could be seen.
- As seen in the **Correlation Heatmap**, there were no positively correlated variables towards the Target variable. The correlation coefficient ranged from -0.05 (HRT) to 0.06 (XGT). This prevented a robust feature selection to be made for further modeling.
- The **clustered column chart for the binary variables BAZ, FYT, and LGH**, show also a consistent count of instances for all Image Classes Bins accross all years, with some instance imbalances: Binary variable LGH contributed with just 237 instances in the data while BAZ and FYT contributed with 328 and 320 respectively. Trends can be seen as:

a. A somewhat consisten trend on Nature and Vehicles classes with steeper variances of LGH of 2 to 9 points.

b. A somewhat upward trend for the class Innanimate Object, although showing high variability for sum of BAZ and sum of FYT. 

c. Person class has the fewer instances accross the dataset compared to the other classes: the instance average is of 10 (log scaled) and accross all years, all the different classes show figures ranging from 3 to 9, with only two exceptions: 2017 BAZ with 13 and 2018 FYT with 11. In 2019 there were no instances. FYT stayed consistent accross all years, except for 2019 the other two show high variability.

d. A somewhat consistent trend for the Animals class where all three variables stayed consistent for 2016 to 2018 with values ranging from 19 to 34.

- All classes see a diminishing instance count for year 2019, were data was only collected for the months of January and February.

- Certain image classes contributed significantly to yearly targets, while others had negligible impact.
- Correlation analysis revealed weak relationships between variables, especially towards the Target variable.

## Future Work

- Removal of Outliers: After removing outliers, the correlation heatmap could reveal stronger and more accurate relationships between variables like Target, Binary, and Continuous features. Outliers often skew results, masking underlying patterns or weakening correlations. By eliminating these points, the data becomes less variable and more representative, allowing for clearer trends and higher correlation coefficients. This adjustment ensures a more reliable basis for feature selection and modeling in subsequent analysis steps.
- Data consistency: Overall, for further analysis only the years of 2016 to 2018 should be considered and disregard year 2019. This can improve trend and seasonality analysis.
- An even split among classes should be considered for furhter analysis, this would aliviate a bias towards the analysis unintentionally set in the beginning.
- No high correlation were obseverved from any of the variables, continuous or binary ones, towards Target.
- Implement predictive modeling like time series forecasting or regression to predict future trends and values based on the historical data.
- Consider doing any of the next statistical methods to further enhance feature engineering:

**Mutual Information (MI):**
Calculate MI scores between the Target and all variables (binary and continuous) to capture both linear and non-linear dependencies. Prioritize variables with higher MI scores for further modeling, as they provide the most information about the Target. Use mutual_info_regression (Scikit-learn) to handle your continuous and binary data effectively.

**Polynomial Features:**
Create higher-degree and interaction terms for continuous variables to capture non-linear relationships with the Target. For example, squaring or combining features like counts or metrics may reveal stronger patterns. Use Scikit-learn’s PolynomialFeatures to generate these features and evaluate their impact on the Target's relationship.

## Contact

For questions or collaboration opportunities, please reach out at: https://www.linkedin.com/in/fernando-cl-data-analyst/
