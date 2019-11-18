# Cassandra-Pyspark
Assignment done as part of a coursework

##Cassandra Code:
### Creating a keyspace 'dba' with columnfamily 'sprmkts', copying the csv le into the columnfamily

```
cqlsh> CREATE KEYSPACE dba WITH replication = {'class':'SimpleStrategy', 'replication_factor' : 3};
```
```
cqlsh> USE dba;
```
```
cqlsh:dba> CREATE COLUMNFAMILY dba.sprmkts
```
```
... (IDCustomer INT PRIMARY KEY
```
```
... , Balance INT, Gender VARCHAR
```
```
... , EDUCATION_Level INT, Married_or_Not INT
```
```
... , Age INT, Pay_Month1 INT
```
```
... , Pay_Month2 INT, Pay_Month3 INT
```
```
... , Pay_month4 INT, Pay_month6 INT
```
```
... , Pay_month7 INT, Amount1 INT
```
```
... , Amount2 INT, Amount3 INT
```
```
... , Amount4 INT, Amount5 INT
```
```
... , Amount6 INT, PAY_AMT1 INT
```
```
... , PAY_AMT2 INT , PAY_AMT3 INT
```
```
... , PAY_AMT4 INT, PAY_AMT5 INT
```
```
... , PAY_AMT6 INT , Come INT) ;
```
```
cqlsh:dba> COPY dba.sprmkts
```
```
... ( IDCustomer, Balance
```
```
... , Gender, EDUCATION_Level
```
```
... , Married_or_Not, Age
```
```
... , Pay_Month1, Pay_Month
```
```
... , Pay_Month3, Pay_month
```
```
... , Pay_month6, Pay_month
```
```
... , Amount1, Amount
```
```
... , Amount3, Amount
```
```
... , Amount5, Amount
```
```
... , PAY_AMT1, PAY_AMT
```
```
... , PAY_AMT3, PAY_AMT
```
```
... , PAY_AMT5, PAY_AMT
```
```
... , Come) FROM 'supermarket.csv' WITH HEADER=TRUE;
```
```
cqlsh:dba> SELECT * FROM dba.sprmkts;
```
