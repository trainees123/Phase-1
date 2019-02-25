# DATA WAREHOUSING
**Data warehousing** is a technique for collecting and mananging data from varied sources to provide meaningful business insights.
It is a combination of techniques and components to ensure strategic use of data. 

**Data warehouse** is an information system that contains historical and commutative data from single or multiple sources. 
+ It is maintained separately from the organisation's operational database.
+ It is not a product but an environment.
+ It is an architectural construct of an information system which provides users with current and historical decision support information 
  which is difficult to access or present in the traditional operational data store.
+ It is built for data analysis and reporting.

## DATA WAREHOUSE COMPONENTS
Data warehouse is based on RDBMS server which is a central information repository, surrounded by some key components to make the entire 
environment functional, manageable and accessible.

There are mainly five components of data warehouse:

+ **Data Warehouse Database:**
The central database is the foundation of the data warehousing environment.

+ **Sourcing, Acquistion, Clean-up and Transformation tools (ETL):**
The data sourcing, transformation, and migration tools are used for performing all the conversions, summarizations, and all the changes needed to transform data into a unified format in the datawarehouse. They are also called Extract, Transform and Load (ETL) Tools.

+ **Metadata:**
Metadata is data about data which defines the data warehouse. It is used for building, maintaining and managing the data warehouse.
It plays an important role as it specifies the source, usage, values, and features of data warehouse data. It also defines how data can be changed and processed. It is closely connected to the data warehouse.
*Meta Data are essential ingredients in the transformation of data into knowledge.*

+ **Query Tools:**
One of the primary objects of data warehousing is to provide information to businesses to make strategic decisions. Query tools allow users to interact with the data warehouse system.
These tools fall into four different categories:
  - Query and reporting tools
  - Application Development tools
  - Data mining tools
  - OLAP tools

+ **Data warehouse Bus Architecture:**
It determines the flow of data in your warehouse.  The data flow in a data warehouse can be categorised as Inflow, Upflow, Downflow, Ooutflow and Metaflow.
While designing a Data Bus, the shared dimensions and facts across data marts need to be considered. A *data mart* is an access layer which is used to get data out to the users. 
It is presented as an option for large size data warehouse as it takes less time and money to build.  

In other words, *a data mart is a subsidiary of a data warehouse which is used for partitioning of data created for the specific group of users.*

It can be created in the same databases as the Data warehouse or a physically separate database.
