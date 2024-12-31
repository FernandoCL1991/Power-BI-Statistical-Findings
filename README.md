# Power-BI-Statistical-Findings

# Data Analysis Project: Target Contributions by Class and Year

## Link to Project: https://app.powerbi.com/groups/me/reports/095baa62-26b7-4498-99af-bbbfc5fddab7/7543321a26c965164723?experience=power-bi

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

### 1. Data Preparation

- A **Date Table** was created in Power BI with columns for Year, Month, and other date-specific fields.
- A new **Year** column was derived for easier aggregation.
- Relationships were established between the Date Table and the Training Table.

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
Image Classes Bins: Animals, Innanimate Objects, Nature, Person, Vehicles

- Image classes contributed similarly accross time (month and years) towards the Target variable.
- Since the data spans from March 2016 to February 2019, a consistent trend couldn't be seen. The years of 2016 and 2019 need to have more data for a deeper analysis. For those 'complete' years with data accross all months, an overall similar trend accross all continuous variables could be seen.
- As seen in the Correlation Heatmap, there were no positively correlated variables towards the Target variable. The correlation coefficient ranged from -0.05 (HRT) to 0.06 (XGT). This prevented a robust feature selection to be made for further modeling.
- The clustered column chart for the binary variables BAZ, FYT, and LGH, show also a consistent count of instances for all Image Classes Bins accross all years.
Trends can be seen as:

a. A slight upward trend on Animals, Nature, and Vehicles classes.

b. A somewhat steeper upward trend for the class Innanimate Object.

c. Person class has the fewer instances accross the dataset compared to the other classes: the instance average is of 10 (log scaled) and accross all years, all the different classes show figures ranging from 3 to 9, with only two exceptions: 2017 BAZ with 13 and 2018 FYT with 11. In 2019 there were no instances.

An upward trend can be seen for the Innanimate Object and 

- Certain image classes contributed significantly to yearly targets, while others had negligible impact.
- Correlation analysis revealed weak relationships between variables, especially towards the Target variable. 




## Future Work

- Incorporate machine learning models to predict class contributions for upcoming years.
- Perform deeper time-series analysis to understand trends over months and seasons.
- Expand the project to include external data for richer insights.

## Repository Structure

- **Python Scripts**: Includes Python scripts used for heatmap generation and correlation analysis.
- **Power BI Files**: Contains the `.pbix` file with all dashboards and visualizations.
- **Data**: Cleaned datasets used in the analysis.
- **README.md**: This documentation file.

## How to Use This Repository

1. Clone the repository:
   ```bash
   git clone <repository_url>
   ```
2. Open the Power BI file (`.pbix`) to explore dashboards.
3. Review Python scripts for additional analysis and heatmap generation.

## Acknowledgments

Special thanks to Insulet for providing the opportunity to perform this analysis and to the data analysis community for valuable insights and resources.

## Contact

For questions or collaboration opportunities, please reach out at [Your Contact Email/LinkedIn Profile].

