**Spark SQL Home Sales Analysis Report**


![Main Dashboard](IMAGES/Cover_image_home_sales_Small.jpg)

### 1. Overview
This report comprehensively analyzes home sales data using Apache Spark, specifically leveraging PySpark for processing and querying. The objective was to determine average home prices under various conditions, evaluate query runtimes, and assess performance optimizations. Key sections include query summaries, runtime benchmarks, and caching strategies.

### 2. Setup and Data Ingestion

- **Libraries Imported:**
  - `pyspark.sql.SparkSession`: This is used to create and manage the Spark session.
  - `pyspark.sql.functions.avg` and `pyspark.sql.functions.round`: Calculating averages and rounding results.
  - `time`: To measure the duration of query execution.

- **Spark Session Initialization:**
  - A Spark session, titled "Home Sales Analysis," was initialized to manage Spark functionalities throughout the analysis.

- **Data Ingestion:**
  - The dataset was loaded from a CSV file located at `https://2u-data-curriculum-team.s3.amazonaws.com/dataviz-classroom/v1.2/22-big-data/home_sales_revised.csv`.
  - The data was stored in a Spark DataFrame and registered as a temporary view called `home_sales`, enabling SQL-based querying.

### 3. Queries and Results

#### Query 1: **Average Price for Four-Bedroom Houses Sold Per Year**
   - **Objective:** Calculate the average price of four-bedroom homes, grouped by the year they were sold.
   - **Output:** [Results displayed]

#### Query 2: **Average Price of Homes with 3 Bedrooms and 3 Bathrooms by Year Built**
   - **Objective:** Calculate the average price for homes with three bedrooms and three bathrooms, grouped by the year built.
   - **Output:** [Results displayed]

#### Query 3: **Average Price of Homes with Specific Criteria by Year Built**
   - **Objective:** Determine the average price for homes with three bedrooms, three bathrooms, two floors, and a minimum of 2000 square feet of living space, grouped by the year built.
   - **Output:** [Results displayed]

#### Query 4: **Average Price Per View Rating for Homes Priced at $350,000 or Above**
   - **Objective:** Calculate the average home price based on view rating, only including homes priced at $350,000 or higher, grouped by view rating in descending order.
   - **Runtime (Uncached):** [Time recorded in seconds]
   - **Output:** [Results displayed]

### 4. Performance Optimization

- **Caching the `home_sales` Table**
   - **Action:** Cached the `home_sales` table to enhance query performance when accessing data multiple times.
   - **Cache Check:** Verified the table was successfully cached.
   - **Re-run Query 4 with Cached Data:**
     - **Runtime (Cached):** [Time recorded in seconds]
     - **Output:** [Results displayed]
   - **Comparison:** The runtime for the cached query was compared with the uncached runtime to determine the performance gains achieved through caching.

### 5. Data Persistence and Re-Analysis

- **Writing Data as Parquet Files**
   - **Action:** The DataFrame was partitioned by `date_built` and saved as Parquet files to allow for efficient storage and re-analysis.
   - **Path Used:** [Specify path where data was saved]

- **Re-run Query 4 on Parquet Data**
   - **Runtime (Parquet):** [Time recorded in seconds]
   - **Output:** [Results displayed]

### 6. Table Uncaching and Session Termination

- **Uncache Table:** The `home_sales` table was uncached to free up memory resources.
   - **Uncache Check:** Verified the table was successfully uncached.

- **Stop Spark Session:** The Spark session was terminated to conclude the analysis and release resources. 

This structured approach enabled the efficient analysis of home sales data, emphasizing performance optimization and scalability. The findings can serve as a model for large-scale data analysis projects using Spark and PySpark.
