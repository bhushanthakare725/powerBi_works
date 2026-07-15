# Azure Data Engineer - Power BI End-to-End Project

## 🏗️ Project Architecture
This project demonstrates data warehousing concepts within Power BI Desktop by implementing a **Star Schema** data model.

## 📊 Data Model & Relationships
- **Sales_Fact (Fact Table):** Contains transactional data (OrderID, ProductID, Quantity, OrderDate).
- **Product_Dim (Dimension Table):** Contains master data (ProductID, ProductName, Category, Price).
- **Relationship:** Established a **One-to-Many (1:*)** relationship between `Product_Dim[ProductID]` and `Sales_Fact[ProductID]` with a **Single** cross-filter direction.

## 🧮 Implemented DAX Concepts
- **Total Revenue (Measure):** Implemented row-by-row iteration using `SUMX` and `RELATED`.
- **Laptop Revenue (Measure):** Used `CALCULATE` to apply specific column-level filters.
- **Filter Overriding:** Learned the behavior of `CALCULATE` combined with `ALL()` for absolute locking.

## 🚀 Production Deployment Approach
- Handled version control capabilities suitable for CI/CD deployment pipelines using Azure DevOps / GitHub Actions.
