# Hive Concepts (SerDe,Partitions and Sort by vs Order by)

### **🗂️ Hive SerDe**

```JSON
SerDe is short for Serializer/Deserializer. Hive uses the SerDe 
interface for IO. The interface handles both serialization and 
deserialization and also interpreting the results of serialization 
as individual fields for processing.

A SerDe allows Hive to read in data from a table, and write it 
back out to HDFS in any custom format. Anyone can write their 
own SerDe for their own data formats
```

**Serialization**
```SQL
Process of converting an object in memory into bytes that can be stored in a file or transmitted over a network
``` 


**Deserialization**
```SQL
Process of converting the bytes back into an object in memory
``` 

**Built-in SerDes**
1. Avro 
2. ORC 
3. RegEx
4. Thrift
5. Parquet 
6. CSV 
7. JsonSerDe

### **📝 Hive Partitions**

**Static Partition**

In Static Partitioning, we have to manually decide how many partitions tables will have and also value for those partitions

**Dynamic Partition**

Dynamic partitions provide us with flexibility and create partitions automatically depending on the data that we are inserting into the table

![h66.webp](https://cdn.hashnode.com/res/hashnode/image/upload/v1668880514062/m6WmMRG1y.webp align="left")

### **✅ Hive Sort by vs Order by**

**Sort by**

1. Uses multiple reducers to produce final output
2. It Only guarantees ordering of rows within a reducer

**Order by**

1. Uses only single reducer to produce final output
2. LIMIT can be used to minimize sort time

