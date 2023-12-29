## Magic Commands
```
%python, %r, %scala, %sql --> languages
%sh --> Shellscript commands. Only works on driver node.
%fs --> Databricks filesystem commands (dbutils)
%md --> markdown commands
%pip --> install python libraries
```

## Variable Referentiation in SQL
In SQL statements, variables create in python can be retreived using the following model

Python cell
```python
full_path = 'dbfs:/some/path'
```
SQL cell
```sql
select * from json.`${full_path}`
```
