# Business-Performance-Analytics-Power-BI
Dimensional data modeling project converting a flat sales dataset into a Star Schema to improve filter propagation, context transition handling, and time intelligence calculations in Power BI.

Here is your **final polished README.md**.
You can copy-paste this directly into your GitHub repository on GitHub.

📊 Business Performance Dashboard – Star Schema Implementation

🔹 Business Objective

To analyze sales performance across products, customers, stores, and time in order to identify revenue drivers, improve scalability, and enable efficient analytical reporting.

🔹 Initial Problem Statement

The dataset was originally structured as a **single flat table** containing columns from A to T (48 attributes).

Issues with the Flat Dataset:

* Large amount of **categorical data repeated across rows**
* High **data redundancy**
* Difficult to scale for analytical expansion
* No separation between transactional and descriptive attributes
* Slower DAX evaluation due to single-table design
* Inefficient filter propagation

Because all fields existed in one table, the model lacked proper dimensional separation, which negatively impacted performance, scalability, and maintainability.

🔹 Data Modeling Approach

1️⃣ Grain Definition

Before restructuring the model, the grain was clearly defined as:

> One row per sales transaction**

Defining the grain ensured:

* Accurate aggregation
* No double counting
* Proper fact–dimension relationships

2️⃣ Star Schema Design

The flat dataset was transformed into a **Star Schema** model.

🟢 Fact Table

* **Fact_Sales** (Transactional data at transaction level)

🔵 Dimension Tables

* **Dim_Product**
* **Dim_Customer**
* **Dim_Store**
* **Dim_Date (Calendar Table)**


3️⃣ Relationship Design

* Established **One-to-Many (1:*) relationships**
* Dimension tables connected to Fact_Sales via primary–foreign keys
* Implemented **single-direction filter flow**
* Ensured structured filter propagation from dimensions to fact table

This modeling approach aligns with dimensional modeling best practices used in BI systems.

---

 🔹 Benefits of Star Schema Implementation

| Aspect             | Flat Model  | Star Schema            |
| ------------------ | ----------- | ---------------------- |
| Data Redundancy    | High        | Reduced                |
| Scalability        | Limited     | High                   |
| DAX Performance    | Slower      | Optimized              |
| Filter Propagation | Inefficient | Structured & Efficient |
| Time Intelligence  | Difficult   | Fully Supported        |

 Key Improvements:

* Reduced redundancy by separating descriptive attributes
* Improved DAX calculation efficiency
* Optimized context transition handling
* Enabled efficient time intelligence functions
* Improved model readability and maintainability



 🔹 DAX & Analytical Techniques Implemented

 ✔ Context Transition

* `CALCULATE()`
* `FILTER()`

✔ Time Intelligence Functions

* `SAMEPERIODLASTYEAR()`
* `TOTALYTD()`
* `DATEADD()`

 ✔ Filter Manipulation

* `ALL()`
* `ALLEXCEPT()`
* `KEEPFILTERS()`

These were used to build dynamic KPIs and comparative performance metrics.

🔹 Key KPIs Developed

* Total Revenue
* Profit Margin %
* Year-over-Year Growth %
* Store-wise Performance Analysis
* Product Contribution Analysis


 🔹 Model Comparison

 📌 Initial Flat Model

[Flat Model](Images/flat_model_view.png)

📌 Conceptual Star Schema Design

[Conceptual Model](Images/star_schema_architecture_diagram.png)

📌 Implemented Star Schema in Power BI

[Star Schema Model](Images/star_schema_model.png)


🔹 Conclusion

By transforming a flat dataset into a structured Star Schema model, this project demonstrates:

* Strong understanding of dimensional modeling principles
* Performance optimization through proper schema design
* Efficient context-aware DAX calculations
* Scalable and maintainable business intelligence architecture

This project highlights the critical role of data modeling in building high-performing analytical solutions in Power BI.

