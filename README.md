# **Dimensional-Modelling-Snowflake**

## **Project Overview**
This project demonstrates how to build a cloud-based dimensional data warehouse using **Snowflake**, with data stored in an **Amazon S3 bucket**. The objective is to transform raw datasets into an efficient star schema for analytical querying and generate actionable business insights. By leveraging Snowflake's capabilities such as staging areas and dimensional modeling, this project provides a scalable and structured approach to managing large datasets.

---

## **Key Components**

### **1. Amazon S3 Connection**
The raw data files are stored in an **Amazon S3 bucket**, which serves as the external source for Snowflake. The connection to S3 is established using Snowflake's `STAGE` feature, enabling secure and efficient data transfer.

### **2. Stage Area Usage**
The **stage area** in Snowflake acts as an intermediary between the S3 bucket and the Snowflake tables. This area is used to manage and preview data before loading it into the data warehouse.

#### Advantages:
- **Reusable Configuration**: A single stage can be used to load multiple datasets from the same S3 bucket.
- **File Management**: The stage allows you to preview available files and ensure data consistency.
- **Improved Security**: Credentials and access permissions are managed securely, minimizing risks during data ingestion.

### **3. Dimensional Modeling**
The data warehouse is structured into a **star schema**, which separates business facts from descriptive attributes, ensuring efficient and intuitive querying. 

#### Components of the Star Schema:
- **Fact Table**: Captures transactional data, such as product orders, user actions, and purchase details.
- **Dimension Tables**: Provide descriptive context to the fact table, such as product details, user information, order metadata, and hierarchical attributes like departments and aisles.

#### Benefits of Dimensional Modeling:
- **Optimized Query Performance**: The star schema simplifies complex joins and enhances query performance.
- **User-Friendly Design**: Data is organized in an intuitive way, making it easier for business analysts to navigate and query.
- **Scalability**: The schema can be extended by adding new dimensions or facts without disrupting existing queries.

---

## **Project Workflow**

1. **Data Integration**:
   - Data files are stored in an Amazon S3 bucket.
   - A Snowflake stage is created to connect to the S3 bucket and facilitate data loading.

2. **Data Loading**:
   - Data is ingested from the stage area into raw staging tables in Snowflake.
   - Each dataset is carefully processed to ensure data integrity and consistency.

3. **Dimensional Modeling**:
   - Raw data is transformed into a **star schema** consisting of one fact table and several dimension tables.
   - Dimension tables provide descriptive attributes, while the fact table captures transactional details.

4. **Data Analysis**:
   - Analytical queries are executed on the dimensional model to derive insights such as reorder patterns, product demand, and user purchase behavior.

---

# **Insights from Analytical Queries**

This document summarizes the key insights derived from the results of four analytical queries executed on the dimensional model in Snowflake.

---

## **1. Total Products Ordered per Department**
### Results Overview:
- **Top Departments**:
  - **Snacks**: 3,006,412 products ordered.
  - **International**: 2,811,155 products ordered.
  - **Produce**: 9,888,378 products ordered.
  - **Beverages**: 2,804,175 products ordered.

### Insights:
- The **Produce** department has the highest number of products ordered, showcasing its essential role in the customer shopping experience.
- The **Snacks** department ranks highly, reflecting a strong demand for quick, ready-to-eat items.
- **International** and **Beverages** departments also see significant activity, indicating diverse customer preferences.

---

## **2. Top 5 Aisles with the Highest Reordered Products**
### Results Overview:
- **Top Aisles**:
  - **Fresh Fruits**: 2,726,251 reorders.
  - **Fresh Vegetables**: 2,123,540 reorders.
  - **Packaged Vegetables/Fruits**: 1,178,700 reorders.
  - **Yogurt**: 1,034,957 reorders.
  - **Milk**: 722,128 reorders.

### Insights:
- **Fresh produce (fruits and vegetables)** dominates reorder activity, highlighting their staple nature in customer orders.
- **Dairy products** like **yogurt** and **milk** are frequently reordered, reflecting regular consumption patterns.
- The high reorder counts for **packaged vegetables/fruits** suggest customer reliance on convenience-oriented produce options.

---

## **3. Average Number of Products Added to Cart by Day of the Week**
### Results Overview:
- **Highest Average**: Day 5 (Friday) with 8.76 products per order.
- **Lowest Average**: Day 3 (Wednesday) with 7.93 products per order.
- Other days fall between these averages, indicating relatively consistent shopping behavior across the week.

### Insights:
- **Friday (Day 5)** sees the highest average number of products added to carts, possibly due to pre-weekend shopping habits.
- **Midweek shopping (Wednesday, Day 3)** exhibits the lowest averages, suggesting less frequent or smaller shopping trips during this period.
- Shopping activity remains relatively consistent across other days, with slight variations based on customer behavior patterns.

---

## **4. Top 10 Users with the Most Unique Products Ordered**
### Results Overview:
- **Top User**: User ID **182401** with 728 unique products ordered.
- Other users with high diversity include:
  - User ID **75304**: 704 unique products.
  - User ID **151994**: 643 unique products.
  - User ID **152144**: 616 unique products.

### Insights:
- The top users show a preference for a diverse range of products, possibly reflecting:
  - Large household needs.
  - Experimentation with different products.
  - A broader range of dietary requirements or preferences.
- These users represent valuable customers with high shopping activity and varied purchasing patterns, making them ideal for targeted marketing campaigns.

---

## **Summary of Insights**
- **Produce** is the most dominant department, with a heavy emphasis on **fresh fruits and vegetables** in reorder patterns.
- Shopping peaks in terms of average cart size are seen on **Fridays**, aligning with end-of-week trends.
- The top customers exhibit diverse shopping behaviors, making them crucial for personalized engagement strategies.
- The findings emphasize the importance of maintaining strong inventory levels in the **produce and dairy aisles**, particularly for frequently reordered items.

These insights provide a foundation for optimizing inventory, enhancing marketing strategies, and improving customer satisfaction.

---

## **Conclusion**
This project illustrates the power of combining Snowflake and Amazon S3 for building a scalable and efficient dimensional data warehouse. By using best practices in data integration, staging, and dimensional modeling, the project transforms raw datasets into actionable insights, enabling better decision-making and business intelligence. Whether you are analyzing reorder patterns or exploring customer behavior, this solution is designed to handle large-scale datasets with ease and efficiency.
