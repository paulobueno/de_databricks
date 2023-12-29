# Delta LakeHouse
## Description
- Open Source
- Created by Databricks
- Build data lakehouse on top of existing cloud storage
- Build for scalable metadata handling

## ACID
- **A - Atomic:** Operations either succeed or fail, completely
- **C - Consistency:** Guarantees over state observed by simultaneous operations
- **I - Isolation:** Guarantees over simultaneous operations over the database
- **D - Durability:** Commited changes are permanent

## Databricks
- Managed Tables
- External Tables

## Set up Delta Tables
### CTAS and CRAS
 - CTAS - Create Tables as Statements
 - CRAS - Create or Replace Table as Statements
 - Are useful when source has well defined schema, such as parquet files or tables.
 - Can't add manual schema declarations
#### Best prectices dealing non well defined data sources (eg. csv)
1. Create a temp view, declaring its schema
2. Use the temp view to create a new delta table

### CTAS - Create Tables as Statements
```sql
CREATE TABLE some_new_table AS SELECT * FROM some_table
```
### CRAS - Create or Replace Table as Statements
```sql
CREATE OR REPLACE TABLE some_new_table AS SELECT * FROM some_table
```
   
### Creating new tables
#### Managed Table
```sql
CREATE TABLE IF NOT EXSISTS new_table (col_1_NAME <TYPE>, col_2_NAME <TYPE> ...)  
USING <TYPE>
```
As a default location, it will be stored at `dbfs:/user/hive/warehouse/database_name.db/new_table`

#### External Table
```sql
CREATE TABLE IF NOT EXSISTS new_table (col_1_NAME <TYPE>, col_2_NAME <TYPE> ...)  
USING <TYPE>  
LOCATION <PATH>
```

### Managed Tables Vs External Tables
Managed tables are tables that are fully managed by Databricks, in which it can perform files deletion after `DROP TABLE` operation.  
Event though you can perform a `DROP TABLE` to an external table, it will only delete its references in your database, keeping it's logs and files.
