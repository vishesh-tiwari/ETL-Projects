## ETL Project Description

This project is built by performing ETL on a CSV files that contains retail customers and orderd data. 


<b>Tools: MySQL, Jupyter Notebook, Python, Pandas.</b>

### Extract 

Loaded the csv file from the Resources folder using pd.read_csv.

https://www.kaggle.com/datasets/mohamedharris/supermart-grocery-sales-retail-analytics-dataset

### Transform

Removed an Irrelevant Column: Dropped the last column in the dataset since it only contained data specific to Tamil Nadu, which was not needed for further analysis.

Filtered High-Profit Customers: Filtered out customers who generated profits greater than 700. This subset of data focuses on high-value customers.

Sorted by Discount: Sorted these high-profit customers by the Discount column in ascending order to prioritize customers who required lower discounts.

Selected Top 50 Lucrative Customers: Identified the 50 most lucrative customers by selecting the top entries with the highest profits and lowest discounts.

### Load 

Database Connection: Established a connection to a PostgreSQL database using SQLAlchemy and the credentials specified in environment variables.

Create Table and Load Data: Loaded the transformed data (top 50 lucrative customers) into a PostgreSQL table named loyal_customers. This table stores customer data for further analysis of high-value customers based on profitability and discount usage.

Validation: Queried the loyal_customers table in PostgreSQL to confirm that the data was successfully loaded and is available for analysis.
