# Hive Tables And File Formats

### **Hive Tables**

**Internal Table**
![Screenshot 2022-11-19 at 2.05.28 PM.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1668846986873/A4-1ClCYH.png align="left")
- internal data managed by hive
- external data stored in warehouse

**External Table**

![Screenshot 2022-11-19 at 2.11.42 PM.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1668847347313/QuprV8F29.png align="left")
- internal data managed by hive
- external data is point to source'

### **File Formats**

**Parquet File**

[Parquet](https://www.databricks.com/glossary/what-is-parquet) is an open source, column-oriented data file format designed for efficient data storage and retrieval. It provides efficient data compression and encoding schemes with enhanced performance to handle complex data in bulk

**ORC File**

[The Optimized Row Columnar (ORC)](https://cwiki.apache.org/confluence/display/hive/languagemanual+orc#:~:text=The%20Optimized%20Row%20Columnar%20(ORC,%2C%20writing%2C%20and%20processing%20data.) file format provides a highly efficient way to store Hive data. It was designed to overcome limitations of the other Hive file formats. Using ORC files improves performance when Hive is reading, writing, and processing data

**Avro File**

[Avro](https://www.ibm.com/in-en/topics/avro#:~:text=Avro%20files%20include%20markers%20that,it%20ideal%20for%20scripting%20languages.) files include markers that can be used to split large data sets into subsets suitable for Apache MapReduce processing. Some data exchange services use a code generator to interpret the data definition and produce code to access the data. Avro doesn't require this step, making it ideal for scripting languages

**CSV File**

[A CSV (comma-separated values)](https://support.google.com/google-ads/answer/9004364?hl=en) file is a text file that has a specific format which allows data to be saved in a table structured format

### **Comparision between Parquet, Orc, Avro**

![1_0Frhzu__LfgEX99Ergb-Hg.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1668848836522/M7RKnOS-u.png align="left")

![Nexla-File-Format.webp](https://cdn.hashnode.com/res/hashnode/image/upload/v1668848727547/rIDlc-Phw.webp align="left")

