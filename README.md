# Supermarket Sales Analysis

## 1. Introduction

This project involves performing an end-to-end analysis of supermarket transaction data to perform data cleaning, exploratory data analysis (EDA), and visualization to uncover actionable business insights. The analysis focuses on identifying top-performing products, understanding monthly sales trends, and examining customer behavior.

## 2. Objectives 🎯

### The main objectives of this analysis are to:

- Identify the top-performing product lines by revenue and transaction volume.
- Analyze sales trends over time, specifically on a monthly and daily basis.
- Understand the revenue contribution from different customer types (Members vs. Normal).

  
## 3. Dataset

- **Source File:** `Supermarket-Sales.csv`
- **Content:** The dataset contains 1006 transaction records with 16 initial columns, including Invoice ID, Branch, Customer type, Product line, Unit price, Quantity, Total, and Date/Time.

## 4. Workflow & Methodology

The analysis was conducted in a Jupyter Notebook (`Supermarket Sales_Analysis.ipynb`) and followed these key steps:

1. **Data Loading and profiling:**
- The dataset is loaded into a pandas DataFrame.
- Initial inspection is done using `.info()` and `.isnull().sum()` to understand data types and identify missing values.

2.  **Data Wrangling:**
*  **Handling Duplicates:** Checked for and removed duplicate rows.
* **Column Consolidation:** The one-hot encoded city columns (`Yangon`, `Naypyitaw`, `Mandalay`) were consolidated into a single categorical Branch column.
* **Correcting Data Types:** The `Unit price` column was cleaned of non-numeric characters (e.g., "USD") and converted from object to float. The `Date` column was converted to datetime.
* **Handling Inconsistencies:** Corrected typos and inconsistent values in categorical columns (e.g., `Memberr` to `Member`, `8 - 30 PM` to a standard time format).
* **Imputing Missing Values:** Null values in `Tax 5%` and `Total`  were recalculated and filled based on `Unit price` and `Quantity` to ensure data integrity. The final equations used were:
`Tax 5% = Unit price * Quantity * 0.05`
`Total = (Unit price * Quantity) + Tax 5%`

3.  **Exploratory Data Analysis (EDA) & Visualization:**
    * Aggregated sales data to calculate total revenue by product line, customer type, and month.
    *Several visualizations were created using matplotlib and seaborn to uncover trends and patterns, including:
        * Bar charts showing revenue, transactions, and average rating by product line.
        * A line chart displaying daily and monthly revenue trends.
        * A multi-line chart comparing the monthly revenue trends for each product line.
        * A pie chart illustrating the revenue share by customer type.

4. **Dashboard Creation:**
- A summary dashboard was created within the notebook by combining key performance indicators (KPIs) and the most important visualizations into a single, comprehensive view.

## 5. Key Insights

- **Highest Transactions:** "Fashion accessories" and "Food and beverages" are the most frequently purchased product lines.
- **Top Revenue Generators:** While frequently purchased, the highest revenue comes from "Food and beverages" (approx. $55,975) and "Sports and travel" (approx. $55,123).
- **Customer Satisfaction:** Food and beverages not only generate the most revenue but also have highe average customer rating (7.11), indicating high satisfaction with these products.
**Sales Trends**
* **Monthly Performance:** The sales data from the first quarter shows a distinct pattern: revenue peaked in January, saw a significant dip in February, and began to recover in March.
* **Drivers of Monthly Trends:** The January peak was largely driven by strong performance in the Home and lifestyle and Sports and travel product lines. Most product categories saw a dip in February.
  
- **Customer Insights**
  * The revenue is distributed across three segments, with Normal customers contributing the largest share (50.2%). This is followed closely by Member customers (46.7%) and a small, uncategorized group (3.1%).

## 6. Technical Requirements & Setup 🛠️

To run this analysis, you will need Python 3 and the following libraries:

- `pandas`
- `numpy`
- `matplotlib`
- `seaborn`

To set up the environment and run the notebook:

1.  Clone this repository.
2.  Ensure you have the required dataset `Supermarket-Sales.csv` in the same directory.
3.  Install the necessary packages:
    ```bash
    pip install pandas, numpy, matplotlib, seaborn
    ```
4.  Launch and run the Jupyter Notebook `Supermarket-Sales_Analysis.ipynb`.
5.  Run the cells sequentially to reproduce the analysis. The notebook also includes a step to export the cleaned DataFrame to a new CSV file.

## 7. File Structure

- `Supermarket-Sales_Analysis.ipynb`: The main notebook containing the Python code and analysis.
- `Supermarket-Sales.csv`: The cleaned dataset used for the analysis.
- `README.md`: This file.
