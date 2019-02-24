
# OLTP - On-line Transaction Processing
__[OLTP Microsoft Azure](https://docs.microsoft.com/en-us/azure/architecture/data-guide/relational-data/online-transaction-processing)__
+ Original source of data.
+ large number of short on-line transactions (INSERT, UPDATE, DELETE). 
+ main emphasis for OLTP systems
  + put on very fast query processing
  + maintaining data integrity in multi-access environments
  + an effectiveness measured by number of transactions per second

An automated teller machine (ATM) for a bank is an example of a commercial transaction processing application.
OLTP systems record business interactions as they occur in the day-to-day operation of the organization, and support querying of this data to make inferences.
Online transaction processing applications are high throughput and insert or update-intensive in database management.
Some examples of OLTP systems include order entry, retail sales, and financial transaction systems.
In OLTP database there is detailed and current data, and schema used to store transactional databases is the entity model (usually 3NF). 
  
# OLAP - On-line Analytical Processing
+ low volume of transactions
+ Queries often complex and involve aggregations
+ Response time is used as effectiveness measure
+ data is:
  + aggregated 
  + historical data
  + stored in multi-dimensional schemas (usually star schema) 
  
  # Major differences
  |Item|OLTP System (Operational System)|OLAP System (Data Warehouse)|
  |----|--------------------------------|----------------------------|
  |Source of data|Operational data; OLTPs are the original source of the data|Consolidation data; OLAP data comes from the various OLTP Databases|
  |Purpose of data|To control and run fundamental business tasks|To help with planning, problem solving, and decision support|
  |What the data|Reveals a snapshot of ongoing business processes|Multi-dimensional views of various kinds of business activities|
  |Inserts and Updates|Short and fast inserts and updates initiated by end users|Periodic long-running batch jobs refresh the data|
  |Queries|Relatively standardized and simple queries Returning relatively few records|Often complex queries involving aggregations|
  |Processing Speed|Typically very fast|Depends on the amount of data involved; batch data refreshes and complex queries may take many hours; query speed can be improved by creating indexes|
  |Space Requirements|Can be relatively small if historical data is archived|Larger due to the existence of aggregation structures and history data; requires more indexes than OLTP|
  |Database Design|Highly normalized with many tables|Typically de-normalized with fewer tables; use of star and/or snowflake schemas|
  |Backup and Recovery|Backup religiously; operational data is critical to run the business, data loss is likely to entail significant monetary loss and legal liability|Instead of regular backups, some environments may consider simply reloading the OLTP data as a recovery method|
