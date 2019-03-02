
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

# Relational Database
__[What are relational DB](https://computer.howstuffworks.com/question599.htm)__
+ 1970, E.F. Codd
+ Originally, databases were flat:
  - Info stored in 1 long txt file, called **tab delimited file**
  - Ea entry separated by special character, ie: '|'
  - Makes it difficult to search for info
+ Easily search for specific info
+ Allows sort based on field
+ Generate records that contain only certain fields from each record
+ Uses **tables** to store info
+ Columns - "Fields", Rows - "Records"
+ Quickly compare information because of the arrangement of data in columns

The relational database model takes advantage of this uniformity to build completely new tables out of required information from existing tables. In other words, it uses the relationship of similar data to increase the speed and versatility of the database.

The "relational" part of the name comes into play because of mathmatical relations. A typical relational database has anywhere from 10 to more than 1,000 tables. Each table contains a column or columns that other tables can key on to gather information from that table.

By storing this information in another table, the database can create a single small table with the locations that can then be used for a variety of purposes by other tables in the database. A typical large database, like the one a big Web site, such as Amazon would have, will contain hundreds or thousands of tables like this all used together to quickly find the exact information needed at any given time.

Relational databases are created using a special computer language, structured query language (SQL), that is the standard for database interoperability. SQL is the foundation for all of the popular database applications available today, from Access to Oracle.
