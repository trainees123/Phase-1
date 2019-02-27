# Atomic data layer



In a data warehouse, atomic data layer is the lowest level of detail. Atomic data provides the base data for all data transformations.



>There is an old saying which states  *"You can't unscramble scrambled eggs".* Surprisingly, the same thing applies also to Data Warehouse Atomic level  says Nicolae Guse



Creating Atomic data level means adding in the fact table the finest level of granularity available in the Source application, in order to allow full tracing from the Data Warehouse back to originating data source.





# Data modeling

It is the process of documenting a complex software system design as an easily understandable diagram, using text and symbols to represent the way data needs to flow.



In other words, it is the process of creating a data model for the data to be stored in a database.

A **Data Model** is a collection of *metadata* that represents the logical organisation, shape and meaning of data.

It is a conceptual representation of

- Data objects

- The associations between different data objects

- The rules.

Data Models ensure consistency in naming conventions, default values, semantics, security while ensuring quality of the data. It emphasizes on what data is needed and how it should be organized instead of what operations need to be performed on the data.



> *Data Model is like an architect's building plan*



## Why is data modeling important?

- To ensure efficient use of data as a blueprint for the construction of new software.

- It enables the stakeholders to identify errors and make changes before any programming code has been written.

- Alternatively, models can be introduced as a part of reverse engineering efforts that extract models from existing systems.

- It is also helpful to identify missing and redundant data.

- Though the initial creation of data model is labor and time consuming, in the long run, it makes the IT infrastructure upgrade and maintenance cheaper and faster.



The two types of Data Modeling techniques are

- Entity Relationship (E-R) Model

- UML (Unified Modelling Language)



## Types of Data

| Master data | Transactional data | Look up data | Metadata |
| ---- | ---- | ---- | ---- |
| Describes an entity that is a person, place or thing | Describes the business process that happens between 2 master data entity | Describes the codes/ID/ values into which the data is abstracted | Data about the previous three types of data |
| Eg., Customer name, Hotel, Product | Eg., Purchase of a product by a customer, Check in into a hotel | Abstraction of the values of attribute eye color as: 1=Green, 2=Blue,3=Brown | Data type of column 1 = String |



## Data Model Cardinality:

It describes how the uniqueness of an entity defines it's relationship to other entities based on *data centricity*.  For example, one-one, one-many, many-many.



Data centricity is the point of view determining the modeling of primary entity.  For example, it can be customer centric model or product centric model.



## Types of Data Models:

![There are three main types of data models](https://www.guru99.com/images/1/022218_0657_WhatisDataM1.png)



### Conceptual Data Model



> This Data Model defines *what* the system contains. This model is typically created by Business stakeholders and Data Architects. The purpose is to organize, scope and define business concepts and rules.



It establishes the entities, their attributes, and their relationships. In this Data modeling level, there is hardly any detail available of the actual Database structure.

It's 3 basic tenants are

- Entity: A real-world thing

- Attribute: Characteristics or properties of an entity

- Relationship: Dependency or association between two entities





![For example:](https://www.guru99.com/images/1/022218_0657_WhatisDataM2.png)



Customer and Product are two entities. Customer number and name are attributes of the Customer entity.

Product name and price are attributes of product entity.

Sale is the relationship between the customer and product.



**Characteristics of a conceptual data model:**



- This type of Data Models are designed and developed for a business audience.



- The conceptual model is developed independently of hardware specifications like data storage capacity, location or software specifications like DBMS vendor and technology. The focus is to represent data as a user will see it in the "real world."

Conceptual data models known as Domain models create a common vocabulary for all stakeholders by establishing basic concepts and scope.



### Logical Data Model

Defines *how* the system should be implemented *regardless* of the DBMS. This model is typically created by Data Architects and Business Analysts. The purpose is to develop technical map of rules and data structures.

Logical data models add further information to the conceptual model elements.

![It defines the structure of the data elements and set the relationships between them.](https://www.guru99.com/images/1/022218_0657_WhatisDataM3.png)



The advantage of the Logical data model is to provide a foundation to form the base for the Physical model. However, the modeling structure remains generic.

At this Data Modeling level, no primary or secondary key is defined. At this Data modeling level, you need to verify and adjust the connector details that were set earlier for relationships.


**Characteristics of a Logical data model:**

- Describes data needs for a single project but could integrate with other logical data models based on the scope of the project.



- Designed and developed independently from the DBMS.



- Data attributes will have datatypes with exact precisions and length.



- Normalization processes to the model is applied typically till 3NF.



### Physical Data Model

> This Data Model describes *how* the system will be implemented using a *specific* DBMS system. This model is typically created by DBA and developers. The purpose is actual implementation of the database.

It offers an abstraction of the database and helps generate schema. This is because of the richness of meta-data offered by a Physical Data Model.

![](https://www.guru99.com/images/1/022218_0657_WhatisDataM4.png)

**Characteristics:**

- The physical data model describes data need for a single project or application though it maybe integrated with other physical data models based on project scope.

-  Data Model contains relationships between tables.

- Developed for a specific version of a DBMS, location, data storage or technology to be used in the project.

- Columns should have exact datatypes, lengths assigned and default values.

- Primary and Foreign keys, views, indexes, access profiles, and authorizations, etc. are defined.













# Data Integrity

Data integrity is the umbrella term for maintanence of data, and the assurance of accuracy and consistency of data over it's entire life cycle. It refers to the trustworthiness and reliability of data. It is a critical aspect to the design, implementation and usage of any system which stores, processes, or retrieves data.



The accuracy and consistency of stored data is indicated by an absence of any alteration in data between two updates of a data record. Data integrity is imposed within a database at its design stage through the use of standard rules and procedures, and is maintained through the use of error checking and validation routines.



## Why is it necessary to maintain data integrity?

Organizations routinely make data-driven business decisions, and with data without integrity, those decisions can have a dramatic effect on the company’s bottom line goals.  Collection of data is no longer an issue.  The responsible thing to do is to preserve data integrity such that the management can confidently make decisions that steer their company in the right direction.



## Common threats to data integrity:

+ Human error

+ Unintended transfer errors

+ Misconfigurations and security errors

+ Malware, insider threats, and cyberattacks

+ Compromised hardware



## Integrity Constraints

Data integrity is enforced in both hierarchical and relational database models. The following three integrity constraints are used in a relational database structure to achieve data integrity:

### Entity Integrity:
This is concerned with the concept of primary keys. The rule states that every table must have its own primary key and that each has to be unique and not null.

### Referential Integrity:
This is the concept of foreign keys. The rule states that the foreign key value can be in two states. The first state is that the foreign key value would refer to a primary key value of another table, or it can be null. Being null could simply mean that there are no relationships, or that the relationship is unknown.

### Domain Integrity: 
This states that all columns in a relational database are in a defined domain.



Having a single, well-defined and well-controlled data integrity system increases stability, performance, reusability and maintainability. If one of these features cannot be implemented in the database, it must be implemented through the software.





## Data Integrity checklist:

![A picture speaks a thousand words](https://blogvaronis2.wpengine.com/wp-content/uploads/2018/03/data-integrity-checklist.png)



The data integrity threats listed above also highlight an aspect of data security that can help preserve data integrity. Using the following checklist to preserve data integrity can be beneficial:

+ **Validate Input:** When data set is supplied by a known or unknown source (an end-user, another application, a malicious user, or any number of other sources) input validation must be made mandatory. That data should be verified and validated to ensure that the input is accurate.

+ **Validate Data:** It’s critical to certify that the data processes haven’t been corrupted. Specifications and key attributes that are important to the organization should be identified before the data is validated.

+ **Remove Duplicate Data:** Sensitive data from a secure database can easily find a home on a document, spreadsheet, email, or in shared folders where employees without proper access can see it. It’s prudent to clean up stray data and remove duplicates.

Smaller companies without a dedicated staff will find that these tools can assist them clean up duplicate files on a hard drive or cloud.

  + Clone Files Checker

  + Duplicate Images Finder

  + Easy Duplicate Finder

  + Duplicate Cleaner

  + Ccleaner

  + DoubleKiller

  + WinMerge



For Windows Servers: Use the Data Deduplication feature to clean up cloned files. Also try the File Server Resource Manager to remove stray files.

+ **Back up Data:** In addition to removing duplicates to ensure data security, data backups are a critical part of the process.

  + Backing up is necessary and goes a long way to prevent permanent data loss.

  + Data should be backed up as often as possible. Backups are critical when organizations get hit with ransomware attacks.

  + Backups should not be encrypted.

+ **Access Controls:** Individuals within an organization without proper access and with malicious intent can do grave harm to the data. An outsider impersonating an insider can also be detrimental. Implementing a least privilege model, where only users who need access to data get access, is a very successful form of access control. What’s often overlooked is physical access to the server. The most sensitive servers should be isolated and bolted to the floor or wall. Only individuals who need access should have an access key.

+ **Always Keep an Audit Trail:** Whenever there is a breach, it’s critical to data integrity to be able to track down the source. Often referred to as an audit trail, this provides an organization the breadcrumbs to accurately pin point the source of the problem.



