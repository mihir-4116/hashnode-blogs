# ETL  ELT And rETL

### ETL (Extract, Transform, Load)

Extract, transform, and load (ETL) is a data pipeline used to collect data from various sources. It then transforms the data according to business rules, and it loads the data into a destination data store

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1672069335312/09d0a421-fae8-4c71-822e-248c2675c6d5.png align="center")

### ELT (Extract, Load, Transform )

Extract, load, transform (ELT) is a data integration process that moves data directly from source to destination for analysts to transform as needed

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1672069430950/5bce092e-d437-416b-aff1-d8cea53af9ea.png align="center")

### ETL VS ELT

| ETL | ELT |
| --- | --- |
| Data is extracted from a source system, transformed on a secondary processing server, and loaded into a destination system | Data is extracted from a source system, loaded into a destination system, and transformed inside the destination system |
| ETL is a time-intensive process. data is transformed before loading into a destination system | ELT is faster by comparison. data is loaded directly into a destination system and transformed in-parallel |
| data output is structured | data output can be structured, semi-structured and unstructured |

### Reverse ETL

**The reverse ETL** feature lets you use the customer data residing in your data warehouse and route it to your entire data stack, including analytics, sales, and marketing tools

![Reverse ETL: What Is It, How It Works & Recommended Tools](https://mcgaw.io/wp-content/uploads/2022/11/A-diagram-showing-the-data-flow-from-warehouse-to-operational-systems-e1669433429552.png align="left")

![](https://miro.medium.com/max/1400/1*MLkQMoy6CnJwCL4zg1-bEQ.jpeg align="left")

List of startups that support Reverse ETL

[Rudderstack](http://rudderstack.com/)

[Hightouch](http://hightouch.com/)

[Census](http://getcensus.com/)

[Grouparoo](https://www.grouparoo.com/) (open source)

[Polytomic](https://www.polytomic.com/)