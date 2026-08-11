Superstore Sales Data Analysis and Visualization

Project Title
Superstore Sales Data Analysis Using Python

Project Overview
This project focuses on analyzing the Superstore sales dataset using Python. The main objective is to understand sales, profit, discounts, categories, and other important business factors through data analysis and visualization.

Python libraries such as Pandas, NumPy, Matplotlib, and Seaborn are used to clean, analyze, and visualize the dataset.

The project helps identify important patterns such as which category generates higher sales and profit, how profit varies across categories, the effect of discounts on profit, and the relationship between numerical variables.

Objectives To load and understand the Superstore dataset. To inspect the structure and statistical summary of the data. To identify and handle missing values. To convert date columns into proper date format. To calculate delivery duration. To analyze sales by category. To compare profit across different categories. To study the distribution of sales and profit. To identify outliers using box plots. To analyze the relationship between discount and profit. To find correlations between numerical variables. To represent important findings using visualizations.
Dataset
The project uses the Superstore dataset stored in the file:

samplesuperstore.csv

The dataset contains information related to customer orders, products, sales, profit, discounts, categories, regions, and order/shipping dates.

Important Columns Order Date – Date on which the order was placed. Ship Date – Date on which the order was shipped. Category – Product category. Sales – Sales amount. Profit – Profit generated from the order. Discount – Discount offered on the product. Region – Geographical region of the order. 5. Technologies Used Programming Language Python Libraries Pandas – Data loading, cleaning, and manipulation. NumPy – Numerical operations. Matplotlib – Data visualization. Seaborn – Statistical visualization. Development Environment Google Colab / Jupyter Notebook Python 3.x 6. Data Loading

The dataset is loaded using Pandas.

import pandas as pd import numpy as np import matplotlib.pyplot as plt import seaborn as sns

df = pd.read_csv("/content/samplesuperstore.csv")

The head(), info(), and describe() functions are used to understand the dataset.

Data Preprocessing
Data preprocessing is performed before visualization and analysis.

Date Conversion

The Order Date and Ship Date columns are converted into datetime format.

df['Order Date'] = pd.to_datetime(df['Order Date']) df['Ship Date'] = pd.to_datetime(df['Ship Date']) Delivery Days Calculation

The number of days between order and shipping is calculated.

df['Delivery Days'] = (df['Ship Date'] - df['Order Date']).dt.days

This helps analyze the delivery duration of orders.

Missing Value Checking

Missing values are checked using:

df.isnull().sum() 8. Exploratory Data Analysis

Exploratory Data Analysis (EDA) is performed to understand the important characteristics and patterns in the dataset.

The following functions are used:

df.head() df.info() df.describe() df['Category'].unique() df.isnull().sum()

These functions provide information about the dataset's records, columns, data types, statistical values, unique categories, and missing values.

Sales Analysis by Category
The total sales for each category are calculated using groupby().

category_sales = df.groupby('Category')['Sales'].sum() category_sales

A bar plot is created to visually compare the sales of different categories.

category_sales.plot(kind='bar', figsize=(8,5)) plt.title("Sales by Category") plt.ylabel("Total Sales") plt.show() Purpose

This visualization helps determine which product category generates the highest total sales.

Sales Distribution
A histogram is used to understand the distribution of sales values.

sns.histplot(df['Sales'], bins=30) plt.title("Sales Distribution") plt.show() Purpose

The histogram shows how frequently different sales values occur in the dataset.

Profit Analysis by Category
A bar plot is used to compare profit across product categories.

sns.barplot( data=df, x="Category", y="Profit" )

plt.title("Profit by Category") plt.show() Purpose

This analysis helps identify which category generates higher profit.

Sales Distribution by Category
Sales are also visualized using a Seaborn bar plot.

sns.barplot( data=df, x="Category", y="Sales" )

plt.title("Sales Distribution by Category") plt.show()

This provides a visual comparison of sales performance across categories.

Profit Distribution Using Box Plot
A box plot is used to understand the distribution of profit.

sns.boxplot( data=df, y="Profit" )

plt.title("Profit Distribution") plt.show() Box Plot Shows Median Data distribution Variation Outliers 14. Profit Variation Across Categories

A category-wise box plot is created to compare profit distributions.

sns.boxplot( data=df, x="Category", y="Profit" )

plt.title("Profit Variation Across Categories") plt.show()

This helps identify differences in profit variation and possible outliers among categories.

Discount vs Profit Analysis
The relationship between discount and profit is analyzed using a scatter plot.

First, the available discount values are identified:

df["Discount"].unique()

Then a scatter plot is created:

sns.scatterplot( data=df, x="Discount", y="Profit" )

plt.title("Impact of Discount on Profit") plt.show() Purpose

The analysis helps understand whether increasing discounts have a positive or negative effect on profit.

It can help answer the question:

"At what discount level does profit start decreasing?"

Correlation Analysis
Correlation is used to understand the relationship between numerical variables.

First, numerical columns are selected:

numeric_df = df.select_dtypes(include="number")

The correlation matrix is then calculated:

corr = numeric_df.corr() corr 17. Correlation Heatmap

A heatmap is used to visualize the correlation between numerical variables.

sns.heatmap( corr, annot=True )

plt.title("Correlation Heatmap") plt.show() Purpose

The heatmap makes it easier to identify positive and negative relationships between variables such as:

Sales Profit Discount Quantity Delivery Days 18. Project Workflow Superstore Dataset ↓ Load Dataset ↓ Explore Dataset ↓ Data Preprocessing ↓ Convert Date Columns ↓ Calculate Delivery Days ↓ Exploratory Data Analysis ↓ Data Visualization ↓ ┌────────────┼─────────────┐ ↓ ↓ ↓ Bar Plots Box Plots Scatter Plots │ │ │ └────────────┼─────────────┘ ↓ Correlation Analysis ↓ Heatmap Visualization ↓ Final Insights 19. Key Visualizations

The project includes the following visualizations:

Sales by Category – Bar Plot Sales Distribution – Histogram Profit by Category – Bar Plot Sales Distribution by Category – Bar Plot Profit Distribution – Box Plot Profit Variation Across Categories – Box Plot Discount vs Profit – Scatter Plot Correlation Heatmap 20. Expected Results

The analysis provides insights into:

The category with the highest sales. The category with better profit performance. The distribution of sales values. Profit variation and outliers. The relationship between discount and profit. Relationships among numerical variables. Delivery duration based on order and ship dates. 21. Advantages Easy to understand and implement. Provides visual representation of business data. Helps identify sales and profit patterns. Helps understand the effect of discounts. Makes large datasets easier to analyze. Supports data-driven business decisions. 22. Limitations The analysis depends on the quality of the dataset. Historical data may not represent current business conditions. Correlation does not necessarily indicate causation. The project mainly focuses on descriptive analysis and visualization. 23. Future Enhancements

The project can be improved by adding:

Sales prediction using Machine Learning. Profit prediction. Customer segmentation. Product recommendation. Regional sales analysis. Monthly and yearly sales trends. Interactive dashboards using Power BI or Tableau. Automated business reports. Machine learning-based demand forecasting. 24. Conclusion

The Superstore Sales Data Analysis and Visualization project demonstrates how Python can be used to analyze real-world business data. Pandas is used for data processing, while Matplotlib and Seaborn are used to create meaningful visualizations.

Through bar plots, box plots, histograms, scatter plots, and correlation heatmaps, the project provides a better understanding of sales, profit, discounts, and other business-related factors.

Overall, the project demonstrates the importance of Exploratory Data Analysis (EDA) and data visualization in discovering useful patterns and supporting better business decisions.

How to Run the Project Step 1: Install Required Libraries pip install pandas numpy matplotlib seaborn Step 2: Add the Dataset
Place the samplesuperstore.csv file in the appropriate project folder.

Step 3: Open the Notebook

Open the project using:

Google Colab Jupyter Notebook VS Code Step 4: Run the Code

Run the Python cells sequentially to perform data preprocessing, analysis, and visualization.

Project Structure Superstore-Sales-Analysis/ │ ├── samplesuperstore.csv ├── Superstore_Sales_Analysis.ipynb ├── README.md └── visualizations/ ├── sales_by_category.png ├── profit_by_category.png ├── profit_distribution.png ├── discount_vs_profit.png └── correlation_heatmap.png
