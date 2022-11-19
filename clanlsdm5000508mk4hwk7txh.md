# Hive Introduction And Architecture

### **What is Hive ?**
Hive is built on top of Apache Hadoop, which is an open-source framework used to efficiently store and process large datasets. As a result, Hive is closely integrated with Hadoop, and is designed to work quickly on petabytes of data. What makes Hive unique is the ability to query large datasets, leveraging MapReduce, with a SQL-like interface

## **Hive Architecture**

![Screenshot 2022-11-19 at 12.12.09 PM.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1668840189380/ec5D1use_.png align="left")


![Screenshot 2022-11-19 at 12.38.53 PM.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1668841768839/4gA_GQKHs.png align="left")

### **Hive Client**

**JDBC client**
```
A JDBC driver connects to Hive using the Thrift framework. Hive Server communicates with the Java applications using the JDBC driver
```

**ODBC client**
```
The Hive ODBC driver uses Thrift to connect to Hive. However, the ODBC driver uses the Hive Server to communicate with it instead of the Hive Server
```
**Thrift Clients**
```
The Hive server can handle requests from a client by using Apache Thrift
```

**CLI **
```
The Hive CLI (Command Line Interface) is a shell where we can execute Hive queries and commands
```

**Hive Web Interface** 
```
The Hive Web UI is just an alternative of Hive CLI. It provides a web-based GUI for executing Hive queries and commands
```

### **Driver**

1. Controller for HQL statements
2. Creates session for query
3. Maintains lifecycle of HQL 
4. Maintains metadata for execution
5. Collects output and display

### **Parsing / Compilation**

1. Syntex check
2. Execution plan 
3. Prepare different steps to get an output
4. Raise compile time errors

### **Optimizer**

1. Compares execution plans
2. Calculate cost
3. Execution plan of DAG
4. Try to place or combine transformations together

### **Execution**

Optimizer generates the logical plan in the form of DAG of map-reduce tasks and HDFS tasks. In the end, the execution engine executes the tasks

### **Metastore**

Metastore stores metadata information about tables and partitions, including column and column type information, in order to improve search engine indexing.

**Two types**

<table>
  <tr>
    <td><b>Internal Databases (Derby Database)</b></td>
    <td><b>External Database</b></td>
  </tr>
  <tr>
    <td>Can't have metadata backup</td>
    <td>Provides metadata backup</td>
  </tr>
<tr>
    <td>Only one connection at a time</td>
    <td>More multiple connnection</td>
  </tr>
<tr>
    <td>Only for internal use cases</td>
    <td>Expose to external use cases</td>
  </tr>
</table>

### **Benefits of using Hive**

1. Simple to use
2. Built on top of hadoop
3. Typical SQL kind of framework
4. Logic will be converted into map-reduce code
