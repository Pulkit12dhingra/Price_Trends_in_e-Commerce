# Dynamic Pricing Trends in E-Commerce

This project analyzes dynamic pricing trends in e-commerce using datasets from Kaggle and eBay. The analysis includes data cleaning, validation, and advanced analysis using Apache Spark.

## Project Structure

- `dynamic_query_delta_report_suggestion.sql`: SQL queries for delta report suggestions.
- `dynamic_pricing_query_5.sql`: SQL queries for dynamic pricing analysis.
- `dynamic_pricing_query_4.sql`: SQL queries for dynamic pricing analysis.
- `dynamic_pricing_model.sql`: SQL model for dynamic pricing.
- `data_warehouse_validation.sql`: SQL queries for data warehouse validation.
- `data_warehouse_schema.sql`: SQL schema for the data warehouse.
- `data_table_check.sql`: SQL queries for data table checks.
- `Data_cleaning_code.ipynb`: Jupyter notebook for data cleaning.
- `Data_check.ipynb`: Jupyter notebook for data checking.
- `apache_spark.ipynb`: Jupyter notebook for Apache Spark analysis.

## Setup Instructions

1. Clone the repository:
    ```sh
    git clone https://github.com/yourusername/Dynamic-Pricing-Trends-in-E-Commerce.git
    cd Dynamic-Pricing-Trends-in-E-Commerce
    ```

2. Install the required Python packages:
    ```sh
    pip install -r requirements.txt
    ```

3. Set up Apache Spark:
    ```sh
    pip install pyspark
    pip install findspark
    ```

4. Initialize Spark in your Jupyter notebook:
    ```python
    import findspark
    findspark.init()
    ```

## Usage

### Data Cleaning

Run the `Data_cleaning_code.ipynb` notebook to clean the datasets.

### Data Validation

Run the `data_warehouse_validation.sql` script to validate the data warehouse.

### Dynamic Pricing Analysis

Run the `dynamic_pricing_query_4.sql` and `dynamic_pricing_query_5.sql` scripts for dynamic pricing analysis.

### Apache Spark Analysis

Run the `apache_spark.ipynb` notebook for advanced analysis using Apache Spark.

### Save Results for Tableau

Save the results to CSV files for further analysis in Tableau:
```python
# Save to CSV for Tableau
joined_df.write.csv("output/joined_analysis", header=True, mode="overwrite")

# Save aggregated revenue analysis
joined_df.groupBy("brand").agg(
    sum(joined_df["ebay_price"]).alias("total_ebay_revenue"),
    sum(joined_df["kaggle_price"]).alias("total_kaggle_revenue")
).write.csv("output/revenue_analysis", header=True, mode="overwrite")
```

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
