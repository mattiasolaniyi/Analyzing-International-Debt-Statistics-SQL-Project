https://www.datacamp.com/datalab/w/b6c61f52-a4e8-41e9-a75c-b00cbe9cd253/edit

# Analyzing International Debt Statistics & DataLab: AI-powered Data Notebook

# Project Overview
This project involves two main components:

Analyzing International Debt Statistics: This part of the project analyzes international debt data from The World Bank. The dataset contains information about the amount of debt (in USD) owed by developing countries across several categories.

DataLab: AI-powered Data Notebook: This component introduces DataLab, an AI-powered data notebook designed for users of all skill levels to analyze and visualize data efficiently.
Analyzing International Debt Statistics
Dataset Description
The dataset consists of the following columns:

country_name: Name of the country
country_code: Code representing the country
indicator_name: Description of the debt indicator
indicator_code: Code representing the debt indicator
debt: Value of the debt indicator for the given country (in current US dollars)
Table Structure
The dataset is stored in a table named international_debt with the following sample rows:

country_name	country_code	indicator_name	indicator_code	debt
Afghanistan	AFG	Disbursements on external debt, long-term	DT.DIS.DLXF.CD	...
Albania	ALB	Interest payments on external debt, long-term	DT.INT.DLXF.CD	...
China	CHN	Total debt	...	...
Timor-Leste	TLS	Principal repayments on external debt, long-term	...	...
Analysis Instructions
You will execute SQL queries to answer the following questions:

Number of Distinct Countries: Determine the total number of distinct countries present in the database.
Country with Highest Debt: Identify the country with the highest amount of debt.
Country with Lowest Repayments: Find the country with the lowest amount of repayments.
Example Queries
Here are some example SQL queries to help you get started:

-- Query to find the number of distinct countries
SELECT COUNT(DISTINCT country_name) AS total_distinct_countries FROM international_debt;

-- Query to find the country with the highest amount of debt
SELECT country_name, SUM(debt) AS total_debt FROM international_debt GROUP BY country_name ORDER BY total_debt DESC LIMIT 1;

-- Query to find the country with the lowest amount of repayments
SELECT country_name, indicator_name, SUM(debt) AS lowest_repayment FROM international_debt WHERE indicator_code = 'DT.AMT.DLXF.CD' GROUP BY country_name, indicator_name ORDER BY lowest_repayment ASC LIMIT 1;
DataLab: AI-powered Data Notebook
Overview
DataLab is an AI-powered data notebook designed to cater to users of all skill levels. It provides a platform for analyzing and visualizing data efficiently, leveraging AI capabilities to enhance the user experience.

Features
User-Friendly Interface: DataLab offers an intuitive interface that makes it easy for users to navigate and perform data analysis.
AI Integration: The notebook integrates AI tools to assist users in data cleaning, analysis, and visualization.
Versatility: Suitable for both beginners and advanced users, DataLab supports a wide range of data analysis tasks.
Getting Started
To get started with DataLab, follow these steps:

Install DataLab: Ensure you have the necessary software installed to run DataLab.
Load Your Data: Import your dataset into DataLab.
Analyze and Visualize: Use the AI-powered tools to clean, analyze, and visualize your data.
Example Usage
Here is an example of how you can use DataLab to analyze the international debt dataset:

import datalab

# Load the dataset
data = datalab.load_data('international_debt.csv')

# Perform analysis
total_countries = data.query('SELECT COUNT(DISTINCT country_name) AS total_distinct_countries')
highest_debt = data.query('SELECT country_name, SUM(debt) AS total_debt FROM international_debt GROUP BY country_name ORDER BY total_debt DESC LIMIT 1')
lowest_repayments = data.query('SELECT country_name, indicator_name, SUM(debt) AS lowest_repayment FROM international_debt WHERE indicator_code = "DT.AMT.DLXF.CD" GROUP BY country_name, indicator_name ORDER BY lowest_repayment ASC LIMIT 1')

# Visualize results
datalab.visualize(total_countries)
datalab.visualize(highest_debt)
datalab.visualize(lowest_repayments)
Conclusion
This project combines the analysis of international debt statistics with the powerful features of DataLab, providing a comprehensive approach to data analysis. By leveraging AI tools, users can gain valuable insights into the debt statistics of developing countries and enhance their data analysis skills.
