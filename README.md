# Delta Lake Fundamentals Lab

## Overview
This project is a hands-on Databricks notebook demonstrating core Delta Lake functionality.

It shows how Delta Lake behaves more like a database than a traditional data lake by supporting versioning, updates, deletes, and time travel.

## Concepts Covered
- Delta table creation
- Insert, update, and delete operations
- Delta transaction history (DESCRIBE HISTORY)
- Time travel using VERSION AS OF
- Merge / upsert logic (MERGE)
- Schema evolution
- Managed vs external table concepts

## Why This Matters
Delta Lake is a core component of modern data engineering workflows in Databricks.

This project demonstrates how data engineers:
- safely update and delete data
- track historical changes
- build reliable, versioned data pipelines

## Key Features Demonstrated

### Time Travel
Query previous versions of a table:

SELECT * FROM demo_delta VERSION AS OF 1;

---

### Merge (Upsert)
Efficiently update and insert data:

MERGE INTO target  
USING source  
ON condition  
WHEN MATCHED THEN UPDATE  
WHEN NOT MATCHED THEN INSERT;

---

### Schema Evolution
Modify table structure over time:

ALTER TABLE demo_delta ADD COLUMNS (status STRING);

## Tools Used
- Databricks
- SQL
- Delta Lake

## Project Structure
- delta-lake-fundamentals-lab.py → Databricks notebook (exported)

## Key Takeaway
Delta Lake is a transaction layer on top of data lakes that enables:

- versioned data changes  
- reliable updates and deletes  
- historical tracking  
- database-like behavior on file-based storage  

## Next Steps
Future enhancements may include:
- Change Data Feed (CDF)
- External table examples with S3
- Performance optimization techniques
- Bronze → Silver pipeline extension
