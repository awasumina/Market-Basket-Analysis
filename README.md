# Market Basket Analysis

This repository contains a Python script for performing market basket analysis using the Apriori algorithm and generating association rules. The analysis is applied to an online retail dataset to identify frequent itemsets and association rules.
   

## Dataset

The script uses an Excel file named `Online Retail.xlsx`, which should be uploaded to Google Colab for processing. This dataset contains transaction records from an online retail store.
    
## Code Description

1. **Data Loading:**
   - The script loads the `Online Retail.xlsx` file into a pandas DataFrame.
   
2. **Data Cleaning:**
   - Extra spaces in the `Description` column are removed.
   - Rows with missing `InvoiceNo` values are dropped.
   - `InvoiceNo` values are ensured to be strings.
   - Transactions that were canceled (indicated by `InvoiceNo` containing 'C') are excluded.

3. **Data Transformation:**
   - A `basket` DataFrame is created to show the quantity of each item bought in each transaction in France. The rows represent transactions (`InvoiceNo`), and columns represent items (`Description`). If an item was not bought in a transaction, its quantity is set to `0`.
   
   - The `basket` DataFrame is converted to a binary matrix where `1` indicates a purchase and `0` indicates no purchase. The `POSTAGE` column is removed from the matrix.

4. **Market Basket Analysis:**
   - Frequent itemsets are identified using the Apriori algorithm with a minimum support threshold of `0.07`.
   - Association rules are generated based on the lift metric with a minimum threshold of `1`.
   - The rules are filtered to find strong associations where the lift is at least `6` and the confidence is at least `0.8`.


## Example Output

The output of the script includes:

- A DataFrame showing frequent itemsets with their support.
- A DataFrame of association rules with metrics like lift and confidence.
- A filtered DataFrame displaying rules where the lift is at least `6` and the confidence is at least `0.8`.


## Conclusion
The market basket analysis provides valuable insights into customer purchasing behavior by identifying frequently bought items together and revealing strong association rules. These insights can be used to enhance marketing strategies, optimize product placements, and improve customer satisfaction. By understanding which products are commonly purchased together, retailers can make data-driven decisions to boost sales and tailor their offerings to meet customer preferences.

