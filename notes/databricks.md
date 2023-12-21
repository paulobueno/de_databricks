# Workspace
## Control Plane
### Unit Catalog
### Databricks UI
#### Cluster Manager
#### Jobs
#### Notebooks
#### Personas
 - SQL
 - Engineering
 - Machine Learning
## Data Plane
#### Workspace Clusters
#### SQL Warehouse
## Cloud Storage
# Compute Resources
## Cluster Types
### All-purpose
 - Designed to be provide iteractive, being usefull to explore data and build new pipelines.
 - Can be started/terminated on the go by the user
 - Can be create in the UI and using Databricks' APIs.  
 - Cluster's configurations are retained up to 70 clusters for up to 30 days.  
### Jobs
 - Designed to process automated operations
 - Clusters are created when an schedule job starts
 - On job termination, cluster is deleted and can't be restarted
 - Cluster's configuration are retained for up to 30 most recently terminated clusters
## Cluster Mode
### Single Node
 - Single node clusters only has 1 node, being the driver
 - Useful to reduce cost when testing new pipelines with reduced amount of data
### Standard (Multi Node)
 - Standard mode clusters have 1 driver node and 1+ worker nodes
 - Can be configured to autoscale
 - Useful to deal with large amount of data, distributing workload through workers
