\# Product Stockout Analysis



\## Introduction

This project aims to analyze product data from ASOS to identify potential lost revenue due to product stockouts and to understand brand performance in relation to pricing and stock availability. By examining product descriptions, pricing, and stock status, we can uncover insights into product management and revenue optimization.



\## Data Source

The analysis uses the `products\_asos.csv` dataset, which contains information about various products, including their URLs, names, sizes, categories, prices, colors, SKUs, descriptions, and images.



\## Analysis Steps

1\.  \*\*Data Loading and Initial Inspection\*\*: The `products\_asos.csv` file was loaded into a pandas DataFrame. Initial checks were performed to understand the data's structure and identify missing values.

2\.  \*\*Data Cleaning\*\*: Missing values were inspected, and rows with missing 'price' data were dropped. The 'price' column was converted to a numeric type, coercing errors.

3\.  \*\*Brand Extraction\*\*: Product descriptions, which often contain brand information (e.g., 'by BrandName'), were used to extract a raw brand name. A `get\_brand` function was created for this purpose. A `brand\_map` was then applied to standardize some brand names, and only brands with more than 5 products were kept for further analysis.

4\.  \*\*Stockout Calculation\*\*: A `calculate\_phantom\_revenue` function was defined to parse the 'size' string, count the number of 'Out of stock' items for each product, and calculate a stockout rate. This was used to determine the number of stockouts and the overall stockout rate per product.

5\.  \*\*Lost Revenue Calculation\*\*: The 'lost\_revenue' for each product was calculated by multiplying its 'price' by the 'Stockout\_count'.

6\.  \*\*Brand Strategy Analysis\*\*: Brands were grouped to calculate their average price, average stockout rate, total lost revenue, and product count. This aggregated data was used to create a scatter plot.



\## Key Findings

The scatter plot for Brand Strategy Analysis visualizes the relationship between average price, average stockout rate, and total lost revenue for different brands. 



\*   \*\*High-Impact Brands\*\*: Brands with an average price above 40 and an average stockout rate above 0.4 were highlighted as 'winner' brands. These brands, specifically \*\*Mango\*\*, \*\*Naked\*\*, \*\*Pull\&BearThrow\*\*, \*\*TopshopLove\*\*, and \*\*VilaAll\*\*, represent products with significant lost revenue potential due to stockouts, indicating high demand for these more expensive, frequently out-of-stock items.

\*   \*\*Opportunity for Optimization\*\*: The analysis suggests that focusing on improving inventory management for these 'winner' brands could lead to substantial revenue recovery.



\## Tools and Libraries Used

\*   `pandas` for data manipulation and analysis.

\*   `matplotlib.pyplot` for plotting.

\*   `seaborn` for enhanced data visualizations.

\*   `numpy` for numerical operations (though not explicitly used in the final plot, it's typically imported with these libraries).



