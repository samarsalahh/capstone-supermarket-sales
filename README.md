# Supermarket Sales Analysis

## 1. Introduction

This project provides an analysis of supermarket sales data from the first quarter of 2019. The primary goal is to perform data cleaning, exploratory data analysis (EDA), and visualization to uncover actionable business insights. The analysis focuses on identifying top-performing products, understanding monthly sales trends, and examining customer behavior.

## 2. Objectives

- Identify the top-performing product lines by revenue and transaction volume.
- Analyze sales trends on a monthly and daily basis.
- Examine the revenue contribution of different customer types (Member vs. Normal).
- Investigate the popularity of various payment methods.

## 3. Dataset

- **Source File:** `Capstone_Supermarket Sales.csv`
- **Content:** The dataset contains 1006 transaction records with 16 initial columns, including Invoice ID, Branch, Customer type, Product line, Unit price, Quantity, Total, and Date/Time.

## 4. Workflow & Methodology

The analysis was conducted in a Jupyter Notebook (`capstone_supermarket--sales.ipynb`) and followed these key steps:

1.  **Data Wrangling:**
    * Handled missing values in `Tax 5%` and `Total` by recalculating them based on `Unit price` and `Quantity`.
    * Corrected data types for `Unit price` (from object to float) and `Date` (from object to datetime).
    * Standardized categorical data by correcting typos in `Customer type` and consolidating three one-hot encoded city columns into a single `Branch` column.
    * Cleaned inconsistent formatting in the `Time` column.

2.  **Exploratory Data Analysis (EDA) & Visualization:**
    * Aggregated sales data to calculate total revenue by product line, customer type, and month.
    * Created visualizations to illustrate key findings, including:
        * A bar chart showing revenue and transaction counts by product line.
        * A line chart displaying monthly revenue trends for each product category.
        * A pie chart illustrating the revenue share between member and normal customers.
        * A comprehensive dashboard summarizing all key metrics and charts.

## 5. Key Insights

- **Top Performers:** "Fashion accessories" and "Food and beverages" are the highest revenue-generating product lines.
- **Seasonal Trends:** Sales show a distinct peak in February, indicating seasonal purchasing behavior.
- **Customer Value:** The revenue is distributed across three segments, with Normal customers contributing the largest share (50.0%). This is followed closely by Member customers (46.9%) and a small, uncategorized group (3.1%).

## 6. Technical Requirements & Setup

To run this analysis, you will need Python 3 and the following libraries:

- `pandas`
- `numpy`
- `matplotlib`
- `seaborn`

To set up the environment and run the notebook:

1.  Clone this repository.
2.  Ensure you have the required dataset `Capstone_Supermarket Sales.csv` in the same directory.
3.  Install the necessary packages:
    ```bash
    pip install pandas numpy matplotlib seaborn
    ```
4.  Launch and run the Jupyter Notebook `capstone_supermarket--sales.ipynb`.

## 7. File Structure

- `capstone_supermarket--sales.ipynb`: The main notebook containing the Python code and analysis.
- `Capstone_Supermarket Sales.csv`: The raw dataset used for the analysis.
- `README.md`: This file.
