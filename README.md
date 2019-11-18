# Cassandra-Pyspark
Assignment done as part of a coursework

##The Dataset - supermarket.csv is loaded in cassandra and the data in csv is converted to a database table using the following code:- 

#### Creating a keyspace 'dba' with columnfamily 'sprmkts', copying the csv le into the columnfamily

```
cqlsh> CREATE KEYSPACE dba WITH replication = {'class':'SimpleStrategy', 'replication_factor' : 3};
```
```
cqlsh> USE dba;
```
```
cqlsh:dba> CREATE COLUMNFAMILY dba.sprmkts
       ... (IDCustomer INT PRIMARY KEY
       ... , Balance INT, Gender VARCHAR
       ... , EDUCATION_Level INT, Married_or_Not INT
       ... , Age INT, Pay_Month1 INT
       ... , Pay_Month2 INT, Pay_Month3 INT
       ... , Pay_month4 INT, Pay_month6 INT
       ... , Pay_month7 INT, Amount1 INT
       ... , Amount2 INT, Amount3 INT
       ... , Amount4 INT, Amount5 INT
       ... , Amount6 INT, PAY_AMT1 INT
       ... , PAY_AMT2 INT , PAY_AMT3 INT
       ... , PAY_AMT4 INT, PAY_AMT5 INT
       ... , PAY_AMT6 INT , Come INT) ;
```
```
cqlsh:dba> COPY dba.sprmkts
       ... ( IDCustomer, Balance
       ... , Gender, EDUCATION_Level
       ... , Married_or_Not, Age
       ... , Pay_Month1, Pay_Month2
       ... , Pay_Month3, Pay_month4
       ... , Pay_month6, Pay_month7
       ... , Amount1, Amount2
       ... , Amount3, Amount4
       ... , Amount5, Amount6
       ... , PAY_AMT1, PAY_AMT2
       ... , PAY_AMT3, PAY_AMT4
       ... , PAY_AMT5, PAY_AMT6
       ... , Come) FROM 'supermarket.csv' WITH HEADER=TRUE;
```
```
cqlsh:dba> SELECT * FROM dba.sprmkts;
```

Pyspark is setup in a server and is configured with jupyter and the codes in ML-DA_Pyspark-Cassandra.ipynb are executed
