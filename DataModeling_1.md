Data Modeling Notes
1. Way to structure the data so it fit sour need in the best possible way
2. needs can be differnt based on what system we are modeiling.
3. OLTP (online transaction processing)  --> database
4. OLAP (online Analytical processing ) ---> datawarehouse
5. how to model OLTP  --> relatioanl modeling
6. priamry goal for designing OLTP, --> minimize redundancy
7. Normalization --> techinque to devide one big table to into multiple small table with an intent to reduce the redundancy.
8. 1NF --> a single row hold more than one value (atomicity) ,  there must be a PK for identification,no duplicate rows or column
9. 2 NF---> 1NF, non pk attribute should depent on complete key
10. 3NF ---> 2NF, no transitive dependency 
11. reporting??  otlp system not ment for reporting, it will overload the syestem because of lot of joins.
12. OLAP (DWH) is best fit for reporting purpose
13.Database  (OLTP)  ,APP/flat file-->   satging layer -->transformation -->DWH -->Data marts             (ETL)
14.what is dataware house ?   --> make analytical read query faster --> dimentional modeling
15. dimentional modeling--> design tequnique for databases intended to support end user queries in DWH.
16.transaction db---> performance --> fast maintenance of data, inserting and updating is quick, small set of data is reterived in a query,data consistency is critical,laws of normalization ,focus is on customer who are entering the data
17.Reporting db --> copy of transactional data (not exactly the same way) as we are not worried about the maintence of data,the resulting model reflects the kind of question business want to ask rather than the functions of  underlying operational system, Descripitive data,larger dataset, insert and update speed is not relevant
18. feature of  dimentional modeling---> data maintence performation is secondary,data denormalized to support reporting
19. Fact ---> a mesure, mesurable metric
20. dimension??  ---> enhances the fact data, 95% of the  columns
21. there is no connection between two dimensions,dimenstion is denormalised
22.fact table will be high volume table
23.surrogate key ---> artificail key for joins
14. dimenstion --> fixed, slowely changing  (slowely  changing dimension   SCD)
15. facts never change
16. surrogate key --> requires to implement history of scd
17.avoid conflict among backend application keys
18.insulates the DWH from backend application changes
19.snowflake schema --> normalised dimensions
20.SCD -0 never chnages
21 SCD-1 overwrite, easy to implement , loses history
22. SCD -2 maintain full history
23. scd-3 limited history, keep column to store previous value, little easy to implement, limited history
34. frequently changing dimenstions---> tkae snapshots
35. one big table --> advantages and disdavantages
36.SCD implementation in pysark
