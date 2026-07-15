# 🎯 Azure Data Engineer - Power BI Interview Quick Revision

## 1. Storage Modes (Industry Reality)
- **Import Mode (80-90% Use):** Data is loaded directly into Power BI's in-memory cache. It offers the best query performance. With Premium Capacity, you can import datasets up to 400 GB.
- **DirectQuery Mode:** Data remains in the source system (e.g., Azure Synapse Analytics). It is used for massive datasets containing billions of rows, but it can slow down report responsiveness because every single user interaction triggers a live SQL query to the background source.
- **Composite/Dual Mode:** The massive Fact table is kept on DirectQuery, while the smaller Dimension tables are set to Import mode. This is the optimal approach to balance query performance and large data volumes.

## 2. Calculated Column vs Measure
- **Calculated Column (📊):** Consumes actual storage space inside the data model (uses RAM). It computes values row-by-row and evaluates only during data refresh.
- **Measure (🧮):** A virtual formula that does not occupy database storage space. It calculates dynamically "on the fly" when a user interacts with a report visual. This is heavily preferred in production environments to maximize performance.

## 3. Advanced DAX Golden Rules
- `SUMX()`: An iterator function that steps through a table row-by-row to evaluate an expression (like a multiplication) and then sums up the final results.
- `RELATED()`: Used to pull data from a Dimension table into a Fact table by leveraging an existing One-to-Many (1:*) relationship.
- `CALCULATE()`: The most powerful function in DAX; it modifies the active filter context and overrides default user selections to lock specific filters onto a visual.
- `ALL()`: Clears or blocks all active filters from a column or an entire table. It is most commonly paired with `CALCULATE` to compute absolute, fixed baseline metrics.
