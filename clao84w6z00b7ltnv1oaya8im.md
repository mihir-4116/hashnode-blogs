# Basic Hive Commands

### **Create Database**
```SQL
create database db_name;
use db_name;
``` 

### **Create Table**
```SQL
Syntex  

create table table_name                                                                                                            
    > (                                                                                                                                       
    >col_name data_type,                                                                                                                            
    >col_name data_type)                                                                                                                                                                                                                                                
    > row format delimited                                                                                                                    
    > fields terminated by ','; 

Example 

create table department_data                                                                                                            
    > (                                                                                                                                       
    > dept_id int,                                                                                                                            
    > dept_name string,                                                                                                                       
    > manager_id int,                                                                                                                         
    > salary int)                                                                                                                             
    > row format delimited                                                                                                                    
    > fields terminated by ','; 
``` 

### **Describe Table**
```SQL
describe table_name;
describe formatted table_name;
``` 

### **Drop Table**
```SQL
Syntex

DROP TABLE [IF EXISTS] table_name;

Example

DROP TABLE IF EXISTS employee;
``` 

### **Truncate Table**
```SQL
Syntex

TRUNCATE TABLE tabe_name;

Example

TRUNCATE TABLE employee;
``` 

### **For data load from local**
```SQL
Syntex 
load data local inpath 'file path' into table table_name; 

Example 
load data local inpath 'file:///tmp/hive_class/depart_data.csv' into table department_data;
``` 

### **Load data from hdfs location**
```SQL
Syntex 
load data inpath 'hadoop file location' into table table_name;

Example  
load data inpath '/tmp/hive_data_class_2/' into table department_data_from_hdfs;
``` 

### **Display column name**
```SQL
set hive.cli.print.header = true;
``` 

### **Create external table**
```SQL
Syntex  

create external table table_name                                                                                          
    > (                                                                                                                                       
    > col_name data_type,                                                                                                                            
    > col_name data_type                                                                                                                            
    > )                                                                                                                                       
    > row format delimited                                                                                                                    
    > fields terminated by ','                                                                                                                
    > location 'source_file_location'; 

Example  

create external table department_data_external                                                                                          
    > (                                                                                                                                       
    > dept_id int,                                                                                                                            
    > dept_name string,                                                                                                                       
    > manager_id int,                                                                                                                         
    > salary int                                                                                                                              
    > )                                                                                                                                       
    > row format delimited                                                                                                                    
    > fields terminated by ','                                                                                                                
    > location '/tmp/hive_data_class_2/'; 
``` 

### **Work with Array data types**

```SQL
Example 

create table employee                                                                                                                   
    > (                                                                                                                                       
    > id int,                                                                                                                                 
    > name string,                                                                                                                            
    > skills array<string>                                                                                                                    
    > )                                                                                                                                       
    > row format delimited                                                                                                                    
    > fields terminated by ','                                                                                                                
    > collection items terminated by ':';  
``` 

### **Get element by index in hive array data type**
```SQL
Syntex  

select array[index] from table_name;

Example 

select skills[0] as prime_skill from employee;
``` 

### **Table for map data**

```SQL
Example

create table employee_map_data                                                                                                          
    > (                                                                                                                                       
    > id int,                                                                                                                                 
    > name string,                                                                                                                            
    > details map<string,string>                                                                                                              
    > )                                                                                                                                       
    > row format delimited                                                                                                                    
    > fields terminated by ','                                                                                                                
    > collection items terminated by '|'                                                                                                      
    > map keys terminated by ':'; 

Get data

 select                                                                                                                                  
    > id,                                                                                                                                     
    > name,                                                                                                                                   
    > details["gender"] as employee_gender                                                                                                    
    > from employee_map_data; 

Map functions

select                                                                                                                                  
    > id,                                                                                                                                     
    > name,                                                                                                                                   
    > details,                                                                                                                                
    > size(details) as size_of_each_map,                                                                                                      
    > map_keys(details) as distinct_map_keys,                                                                                                 
    > map_values(details) as distinct_map_values                                                                                              
    > from employee_map_data; 
``` 

### **Command to create identical table**

```SQL
Syntex

create table table_2 as select * from table_1;
``` 

### **Create table using different file formats**
```SQL
Parquet 

create table table_name                                                                                                        
    > (                                                                                                                                       
    >col_name data_type,                                                                                                                    
    > col_name data_type                                                                                                                         
    > )                                                                                                                                       
    > stored as parquet; 

Orc

 create table table_name                                                                                                        
    > (                                                                                                                                       
    >col_name data_type,                                                                                                                    
    > col_name data_type                                                                                                                         
    > )                                                                                                                                       
    > stored as orc; 

Avro

create table table_name                                                                                                        
    > (                                                                                                                                       
    >col_name data_type,                                                                                                                    
    > col_name data_type                                                                                                                         
    > )                                                                                                                                       
    > stored as avro; 

CSV File

create table table_name                                                                                                        
    > (                                                                                                                                       
    >col_name data_type,                                                                                                                    
    > col_name data_type                                                                                                                         
    > )   
    > row format serde 'org.apache.hadoop.hive.serde2.OpenCSVSerde'                                                                                                                                    
    > stored as textfile
    > tblproperties ("skip.header.line.count" = "1"); 

JSON File

create table table_name                                                                                                        
    > (                                                                                                                                       
    >col_name data_type,                                                                                                                    
    > col_name data_type                                                                                                                         
    > )   
    > row format serde 'org.apache.hive.hcatalog.data.JsonSerDe'                                                                                                                                   
    > stored as textfile; 
``` 

### **Change number of reducers**
```SQL
Syntex 

 set mapreduce.job.reduces=no of reducers;
``` 

### **Hive Partition**

**Static Partition**
```SQL
set hive.mapred.mode=strict;

create table static_table                                                                                                     
    > (                                                                                                                                       
    > col_name data_type,                                                                                                                        
    > col_name data_type                                                                                                                                                                                                                                                
    > )                                                                                                                                       
    > partitioned by (col_name data_type); 

insert overwrite table static_table partition(col_name = value) select col_name data_type, col_name data_type from table_name where col_name = value;
``` 

**Dynamic Partition**
```SQL
set hive.exec.dynamic.partition.mode=nonstrict; 

create table dynamic_table                                                                                                     
    > (                                                                                                                                       
    > col_name data_type,                                                                                                                        
    > col_name data_type                                                                                                                                                                                                                                                
    > )                                                                                                                                       
    > partitioned by (col_name data_type); 

insert overwrite table dynamic_table partition(col_name) select col_name data_type, col_name data_type from table_name where col_val = value;
``` 

**Multilevel Partition**
```SQL
create table multi_level_table                                                                                                     
    > (                                                                                                                                       
    > col_name data_type,                                                                                                                        
    > col_name data_type                                                                                                                                                                                                                                                
    > )                                                                                                                                       
    > partitioned by (col_name data_type,col_name data_type);

insert overwrite table multi_level_table partition(col1_name,col2_name) select col_name data_type, col_name data_type from table_name;
``` 

### **Add udf(user defined functions) in hive shell**

```SQL
add file file_path;
``` 

**Statement to execute python udf**
```SQL
select transform(function_params) using 'python python_file_name.py' as (receive function output) from table_name limit 5;
``` 

### **Bucketing in Hive**
```SQL
set hive.enforce.bucketing=true;

Syntex

create table buck_users                                                                                                                 
    > (                                                                                                                                       
    > col_name data_type,                                                                                                                                       
    > col_name data_type                                                                                                                                                                                                                                                     
    > )                                                                                                                                       
    > clustered by (id)                                                                                                                       
    > sorted by (id)                                                                                                                          
    > into bucket_number buckets;

Example

create table buck_users                                                                                                                 
    > (                                                                                                                                       
    > id int,                                                                                                                                 
    > name string,                                                                                                                            
    > salary int,                                                                                                                             
    > unit string                                                                                                                             
    > )                                                                                                                                       
    > clustered by (id)                                                                                                                       
    > sorted by (id)                                                                                                                          
    > into 2 buckets;
``` 

### **Hive Joins (same as [SQL Joins](https://www.geeksforgeeks.org/sql-join-set-1-inner-left-right-and-full-joins/))**

1. inner joins
2. left join
3. right join
4. full outer join

### **Hive Optimized Joins**

**Reduce-Side Join**
```SQL
SET hive.auto.convert.join=false;

Syntex 

SELECT * FROM table_1 u INNER JOIN table_2 l ON u.id = l.id;

Example

SELECT * FROM buck_users u INNER JOIN buck_locations l ON u.id = l.id;
``` 

**Map Side Join**
```SQL
SET hive.auto.convert.join=true;

Syntex 

SELECT * FROM table_1 u INNER JOIN table_2 l ON u.id = l.id;

Example

SELECT * FROM buck_users u INNER JOIN buck_locations l ON u.id = l.id;
``` 

**Bucket Map Join**
```SQL
set hive.optimize.bucketmapjoin=true;
SET hive.auto.convert.join=true;

Syntex 

SELECT * FROM table_1 u INNER JOIN table_2 l ON u.id = l.id;

Example

SELECT * FROM buck_users u INNER JOIN buck_locations l ON u.id = l.id;
``` 

**Sorted Merge Bucket Map Join**
```SQL
set hive.enforce.sortmergebucketmapjoin=false;
set hive.auto.convert.sortmerge.join=true;
set hive.optimize.bucketmapjoin = true;
set hive.optimize.bucketmapjoin.sortedmerge = true;
SET hive.auto.convert.join=false;

Syntex 

SELECT * FROM table_1 u INNER JOIN table_2 l ON u.id = l.id;

Example

SELECT * FROM buck_users u INNER JOIN buck_locations l ON u.id = l.id;
``` 































