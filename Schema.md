# Schemas in Data Warehouses
 A schema is a collection of database objects, including tables, views, indexes, and synonyms.

## Types of schema
 + Third Normal Form
 + Star Schemas
## 1. Third Normal Form:
  Although this guide primarily uses star schemas in its examples, you can also use the third normal form for your data warehouse implementation.

 Third normal form modeling is a classical relational-database modeling technique that minimizes data redundancy through normalization.
 When compared to a star schema, a 3NF schema typically has a larger number of tables due to this normalization process.
 3NF schemas are typically chosen for large data warehouses, especially environments    with significant data-loading requirements that are used to feed data marts and execute  long-running queries.

 ### The main advantages of 3NF schemas are that they:
 + Provide a neutral schema design, independent of any application or data-usage considerations
 + May require less data-transformation than more normalized schemas such as star schemas

## 2. Star Schemas:
The star schema is perhaps the simplest data warehouse schema. It is called a star schema because the entity-relationship diagram of this schema resembles a star, with points radiating from a central table. The center of the star consists of a large fact table and the points of the star are the dimension tables.

A star schema is characterized by one or more very large fact tables that contain the primary information in the data warehouse, and a number of much smaller dimension tables (or lookup tables), each of which contains information about the entries for a particular attribute in the fact table.

A star query is a join between a fact table and a number of dimension tables. Each dimension table is joined to the fact table using a primary key to foreign key join, but the dimension tables are not joined to each other. The cost-based optimizer recognizes star queries and generates efficient execution plans for them.

A typical fact table contains keys and measures. For example, in the sh sample schema, the fact table, sales, contain the measures quantity_sold, amount, and cost, and the keys cust_id, time_id, prod_id, channel_id, and promo_id. The dimension tables are customers, times, products, channels, and promotions. The product dimension table, for example, contains information about each product number that appears in the fact table.

A star join is a primary key to foreign key join of the dimension tables to a fact table.

### The main advantages of star schemas are that they:

+ Provide a direct and intuitive mapping between the business entities being analyzed by end users and the schema design.
+ Provide highly optimized performance for typical star queries.
+ Are widely supported by a large number of business intelligence tools, which may anticipate or even require that the data-warehouse schema contain dimension tables
Star schemas are used for both simple data marts and very large data warehouses.

##  3.Snowflake Schemas
The snowflake schema is a more complex data warehouse model than a star schema, and is a type of star schema. It is called a snowflake schema because the diagram of the schema resembles a snowflake.

Snowflake schemas normalize dimensions to eliminate redundancy. That is, the dimension data has been grouped into multiple tables instead of one large table. For example, a product dimension table in a star schema might be normalized into a products table, a product_category table, and a product_manufacturer table in a snowflake schema. While this saves space, it increases the number of dimension tables and requires more foreign key joins. The result is more complex queries and reduced query performance.
   

