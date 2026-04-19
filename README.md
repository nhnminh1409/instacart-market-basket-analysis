# instacart-market-basket-analysis
This project analyzes shopping behavior and predicts which products customers will repurchase on Instacart (Machine Learning - Data Science).

1. Data Cleaning & Preprocessing

As the Data Engineer for this project, I focused on building a robust and memory-efficient pipeline to handle the Instacart dataset. My workflow included the following key steps:

Memory Optimization: Given the massive scale of the dataset, I implemented Downcasting techniques (converting int64 to int16/int8 and float64 to float32). This optimization significantly reduced RAM consumption and improved processing speed.

Data Integration: I integrated fragmented data by performing Merging and Joining operations on orders.csv, products.csv, aisles.csv, and departments.csv. This was achieved by identifying and connecting common columns (Primary and Foreign Keys).

Missing Value Handling: I addressed data gaps, specifically in the days_since_prior_order column. I utilized Imputation to fill NaN values with 0, representing the customer's initial order.

Data Splitting (Pipeline): To ensure a clean transition to the modeling phase, I automated the data partition into Train, Validation, and Test sets. This was based on the internal eval_set labels to maintain consistency during model evaluation.

Data Integrity: I performed rigorous checks to remove duplicates and standardize data types (e.g., ensuring IDs are integers and metrics are floats) to prevent "noise" in the analytical results.
