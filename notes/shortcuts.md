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

## Working with JSON
| ID | json_data        |
|----|------------------|
| 1  | "{'a':{'b':10}}" |

The followinf query will return `10`
```sql
select json_data:a.b from my_table
```
The `:` tells Databricks to parse string as a JSON format. From Databricks' documentation "Extracts content from a JSON string using a JSON path expression."  
A JSON path expression is a set of expressions used to navigate through nested JSON structures.








