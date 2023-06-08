# CompTIA Data+

## CompTIA
* [CompTIA Data+](https://www.comptia.org/certifications/data) - comptia.org
* [Create Your Study Plan NOW!](https://certs.comptia.org/trainingchecklist/)
* [How To Study for CompTIA Data+](https://www.comptia.org/blog/how-to-study-for-comptia-data)

# Domains

## 1.0 Data Concepts and Environments
### 1.1 Identify basic concepts of data schemas and dimensions
#### Databases
* Relational: Relational databases store data in a structured way with tables of rows and columns. Each table, which represents an entity type, has a key that makes each row (or record) unique. The 'relational' aspect comes from the ability to link information from different tables through the use of foreign keys, which are identifiers that establish a link between two tables. Examples of relational databases include MySQL, PostgreSQL, and Oracle Database.
* Non-relational: Non-relational databases, often called NoSQL databases, are more flexible than relational databases because they don't require a fixed schema and they scale more easily. They store data in a variety of ways: it can be column-oriented, document-oriented, graph-based or organized as a KeyValue store. This flexibility can make them a good choice for high-velocity, complex, and variable data. Examples include MongoDB (document-oriented), Cassandra (column-oriented), and Neo4j (graph-based).

#### Data mart/data warehousing/data lake
`OLTP | OLAP`
* Online Transactional Processing (OLTP): OLTP refers to the real-time processing of transaction-based applications, typically associated with relational databases and business applications. OLTP systems prioritize fast, reliable, and consistent transactions and support a large number of short on-line transactions such as INSERT, UPDATE, DELETE. Examples include order entry, retail sales, and financial transaction systems.
* Online Analytical Processing (OLAP): OLAP, on the other hand, refers to complex analysis of data, often originating from various sources. OLAP systems are optimized for read-heavy scenarios and facilitate multi-dimensional analytical queries (like aggregation and drill-down), enabling users to analyze data from multiple dimensions. These systems are typically used in business intelligence and data warehousing scenarios.

#### Schema concepts
`Snowflake | Star`
* [Star Schema vs Snowflake Schema: Key Differences Between The Two](https://www.simplilearn.com/star-schema-vs-snowflake-schema-article) - simplilearn.com
* Snowflake Schema: In a snowflake schema, dimension tables are normalized, meaning the data is organized to minimize redundancy and dependency. This leads to a structure where dimension tables are connected to other dimension tables, forming a snowflake-like shape. While this schema can save storage space and maintain data integrity, it may require more complex queries and joins to retrieve data.
* Star Schema: In a star schema, each dimension is represented by a single table, and these tables are connected to a central fact table, forming a star-like shape. This is a simple, denormalized structure that allows for faster data retrieval with simpler queries. However, due to denormalization, it might lead to more storage space being required and potential data redundancy.
#### Slowly changing dimensions
* Slowly Changing Dimensions (SCDs) are a concept in data warehousing that refers to the ways in which data in a dimension table changes over time. These dimensions don't change frequently, but when they do, there needs to be a way to manage and track these changes. For example, a customer's address might change, or a product's price might vary over time. The term "slowly changing dimension" was developed to help data warehouse designers track these historical changes in data over time. There are various strategies to handle SCDs, typically referred to as Type 0 through Type 6, each offering different methods for managing historical data changes.
There are several strategies or "types" for managing Slowly Changing Dimensions (SCDs) in a data warehouse, including:
   * Type 0 - Retain Original: In this approach, changes to data are not tracked. The original dimension attribute value is kept in the database, regardless of changes in the source system.
   * Type 1 - Overwrite: In this strategy, when changes occur in the source system, the existing records in the dimension table are updated to reflect the new information, overwriting the old data. No history is kept.
   * Type 2 - Add New Row: Here, a new record is added to the dimension table when changes occur in the source system, thus keeping a full history of data changes. This new record gets its own primary key, and the old record remains unchanged.
   * Type 3 - Add New Attribute: In this approach, a new attribute is added to the dimension table to track changes. For example, if an address changes, a "previous address" field might be added.
   * Type 4 - Add History Table: This involves creating an entirely separate "history" table to track changes. When a change occurs, a new record is added to the history table, leaving the original dimension table unchanged.
   * Type 6 - Hybrid: This is a combination of Types 1, 2, and 3. It involves overwriting some attributes (Type 1), adding a new row for others (Type 2), and adding a new attribute for yet others (Type 3).

### 1.2 Compare and contrast different data types
* Date: This type represents a date (and often a time). It's usually stored in a specific format that the database can understand.
* Numeric: Numeric data types represent number values. They can further be classified into integer, decimal, float, etc. These are all numeric data types but have different precision and size.
* Alphanumeric: This data type can contain both text and numbers. They are often used to store codes, identifiers or descriptions that may include both letters and digits.
* Currency: A data type specifically designed to store monetary values, maintaining a high level of precision to avoid rounding errors.
* Text: Text data types are used to store letters, numbers and other characters. They can hold sentences, paragraphs or even larger text.
* Discrete vs Continuous: Discrete data can only take specific values (like the number of children in a family), while continuous data can take any value within a range (like height, weight, temperature).
* Categorical/Dimension: This data type is used for values that belong to a limited set of categories or groups, often used in statistical analysis. It can be further divided into nominal (no order implied, like colors: red, blue, green) and ordinal (order matters, like rating scale: poor, average, good).
* Images, Audio, Video: These are complex data types that store multimedia data. They are typically stored in binary format, and databases often handle these by storing a reference to the location of the data rather than the data itself.

### 1.3 Compare and contrast common data structures and file formats
#### Structure
##### Structured Data
* Defined Rows/Columns: This refers to data that is organized in a tabular form, like a spreadsheet or a relational database, where each row represents a record and each column represents an attribute of that record. This is a highly structured format which is easy to query and analyze.
* Key-Value Pairs: This is a type of data model where each data item has a key that is uniquely associated with it, similar to a dictionary or a map. This is commonly used in NoSQL databases and allows for efficient data retrieval when the key is known.
##### Unstructured Data
* Undefined Fields: This refers to data that doesn't have a pre-defined data model or organization. Examples include text data like emails and word documents, as well as multimedia content such as images, audio, and video files. This type of data is more difficult to analyze and process but can contain rich and complex information.
* Machine Data: This is a form of unstructured data generated by computers or machines, often in real-time and at high volumes. Examples include log files, sensor data, or data produced by internet-connected devices. This data is typically unstructured and can be challenging to analyze but can offer significant insights when properly processed.

-----
## 2.0 Data Mining
### 2.1 Explain data acquisition concepts
#### Integration
* Extract, Transform, Load (ETL): This is a process in data warehousing. First, data is extracted from homogeneous or heterogeneous data sources. Next, it's transformed to fit operational needs (which can involve cleaning, aggregating, and organizing the data). Finally, it's loaded into the end target (database, more specifically, operational data store, data mart, or data warehouse).
* Extract, Load, Transform (ELT): This is a variant of ETL where the extracted data is loaded into the target system first, and transformations are performed after the data is loaded. This approach can leverage the high-performance capabilities of modern data warehousing environments.
* Delta Load: Delta load refers to the process of loading only the changed data (new data or updates to existing data) into a data warehouse or database. This can be more efficient than loading all data, as it minimizes data transfer and processing.
* Application Programming Interfaces (APIs): APIs are sets of rules and protocols for how software applications should interact with each other. They allow different software systems to communicate and share data and functionality, making it easier to build and integrate software applications.
#### Data collection methods
* Web Scraping: This is a method used to extract data from websites. It involves making HTTP requests to the URLs you want to scrape, and then parsing the HTML response to retrieve the data you're interested in.
* Public Databases: These are databases that are openly available for anyone to access and use. They can contain a wide variety of data, from demographic information to scientific data.
* Application Programming Interface (API)/Web Services: APIs are a set of rules and protocols for how software applications should interact with each other. Web services are a type of API, typically operating over HTTP, that allow different software systems to communicate with each other over the internet.
* Survey: A method of collecting data directly from individuals. This usually involves asking a series of questions and recording the responses. Surveys can be conducted in various ways, including online, over the phone, or in person.
* Sampling: This is a statistical method that involves selecting a subset of individuals from a larger population, in order to estimate characteristics of the whole population.
* Observation: This is a method of collecting data by watching and recording behaviors or events. It can be done in natural settings or in more controlled conditions, and may involve no interaction with the subjects being observed, or active participation by the observer.

### 2.2 Identify common reasons for cleansing and profiling datasets
* Missing Values
   *  [Concepts of MCAR, MAR and MNAR](https://stefvanbuuren.name/fimd/sec-MCAR.html) - stefvanbuuren.name
   * In statistics and data science, replacing missing values with the mean value of the remaining data in the variable is a form of **imputation**, which is a general term for techniques used to estimate and replace missing data with substituted values. 
* **Capping** in the context of data analysis is a method used to limit or "cap" extreme values in a dataset in order to reduce the impact of outliers. This method is also known as "winsorizing" or "truncation".
* Duplicate Data: This refers to data entries that are repeated in the dataset. Duplicates can occur for various reasons, such as errors during data entry or merging datasets.
* Redundant Data: This refers to data that is repeated or not needed, and doesn't provide additional information. It often results from poor database design or the lack of normalization in the database.
* Missing Values: This refers to the absence of data or data values in a dataset. Handling missing values is a major step in the data cleaning process and there are several ways to handle them, like imputation or deletion.
* Invalid Data: This is data that is incorrect, out of range, or in the wrong format. For example, a negative value for someone's age would be considered invalid.
* Non-Parametric Data: This refers to data that doesn't follow a known or specified distribution. Non-parametric statistical methods are often used when the data doesn’t meet the assumption of normality.
* Data Outliers: Outliers are data points that significantly differ from other observations in the dataset. They can arise due to variability in the data or due to errors.
* Specification Mismatch: This occurs when the actual data and expected data do not match. For example, the specification might state that a field should contain dates, but instead, it contains text.
* Data Type Validation: This is the process of checking that the values in a dataset are of the expected data type. For example, a field expecting numerical data should not contain text. This process helps in maintaining data integrity.


### 2.3 Given a scenario, execute data manipulation techniques
* Recoding Data: This involves changing or converting the values in a dataset.
   * Numeric: Converting or changing numeric values. This might involve scaling values or converting units.
   * Categorical: Converting or changing categorical values. This often involves turning categories into numeric codes or merging categories.
Derived Variables: These are new variables created from existing ones, typically through some sort of mathematical transformation or combination.
* Data Merge: This involves combining two or more datasets based on a common variable.
* Data Blending: This is a process of combining data from multiple sources, which could be structured, semi-structured or unstructured, to provide a unified view.
* Concatenation: This is a process of combining two or more strings into one.
* Data Append: This involves adding new records (rows) to a dataset from another dataset that has similar fields (columns).
* Imputation: This is a method for handling missing data by substituting missing values with estimated ones.
* Reduction/Aggregation: This is the process of transforming a dataset into a smaller one that still accurately represents the larger set. Aggregation often involves computing summary statistics such as averages or sums.
* Transpose: This involves switching the rows and columns of a dataset.
* Normalize Data: This is a process of scaling values to a standard range, often 0 to 1, to achieve better performance in machine learning algorithms.
* Parsing/String Manipulation: Parsing is the process of breaking down and interpreting strings. String manipulation involves changing, splitting, joining, or otherwise working with strings.


### 2.4 Explain common techniques for data manipulation and query optimization
#### Data manipulation
* Data Manipulation: This refers to the process of adjusting data to make it organized and easier to read. Data manipulation can involve a variety of techniques to modify, organize, or combine data.
* Filtering: This is a process of selecting a subset of data based on certain criteria. For example, you might filter a dataset to only include entries from a certain date range or with a specific value.
* Sorting: This involves arranging data in a certain order, usually either ascending or descending. For example, you might sort a list of people by their last names.
* Date Functions: These are functions that perform operations on date data types. This could involve extracting the day from a date, determining the number of days between two dates, or converting a string to a date.
* Logical Functions: These functions return a value based on a logical condition, such as IF, AND, OR in many programming languages.
* Aggregate Functions: These functions operate on a group of rows to give one result per group. Examples include SUM, AVG, MAX, MIN, and COUNT.
* System Functions: These functions perform operations related to the system, such as returning the current date and time, getting information about the user, or system settings. The availability and specifics of these functions can vary depending on the database system or programming language.

#### Query optimization

-----
## 3.0 Data Analysis
-----
## 4.0 Visualization
-----
## 5.0 Data Governance, Quality, and Controls
### Summarize important data governance concepts
#### Security requirements
`Data encryption | Data transmission | De-identify data/data masking`
* [Guidelines for Media Sanitization](https://csrc.nist.gov/publications/detail/sp/800-88/rev-1/final) - nist.gov
* [Security Breach Notification Laws](https://www.ncsl.org/technology-and-communication/security-breach-notification-laws) - ncsl.org

#### Entity relationship requirements
*  The [cardinality](https://www.thedataschool.co.uk/eamonn-woodham/high-cardinality-vs-low-cardinality/) of a column refers to the number of distinct values that the column can take on. A column with high cardinality has a large number of distinct values, while a column with low cardinality has a small number of distinct values.
*  Data classification
   *  Business Classification: Public, Internal, Sensitive, Highly Sensitive
   *  Military Classifiation: Unclassified, Classified, Secret, Top Secret

### Given a scenario, apply data quality control concepts
#### Automated Validation
* The **number of data points** is simply a count of all the measurements or observations within your data set. This is an important concept in statistical analysis, where the number of data points can affect everything from the reliability of your results to the types of analysis you can perform.

### Explain master data management (MDM) concepts
#### Processes
* A **data dictionary** is a centralized repository of information about data, such as its meaning, relationships to other data, origin, usage, and format. It serves as a catalog or a guide to understanding what data is in a system, how it is organized, and how it is used.
* **"Standardization of data field names"** is a data management practice that involves creating a consistent format for naming data fields across a database or a collection of datasets. It ensures that the same type of information is always referred to by the same name and format. For example, one dataset might use "DOB" as a field name to indicate a person's date of birth, while another dataset might use "BirthDate". Standardizing these field names across all datasets might involve deciding to always use "DateOfBirth" for this information. This makes it immediately clear what information is contained in that field, regardless of which dataset you're looking at.


-----

## Acronyms
* ANOVA Analysis of Variance
* API Application Programming Interface
* AWS Amazon Web Services
* BI Business Intelligence
* CRM Customer Relationship Management
* CSV Comma-separated Values
* ELT Extract, Load, Transform
* ETL Extract, Transform, Load
* FAQs Frequently Asked Questions
* GDPR General Data Protection Regulation
* HTML Hypertext Markup Language
* JSON JavaScript Object Notation
* KPI Key Performance Indicator
* MDM Master Data Management
* NoSQL Not Only Structured Query Language
* OLAP Online Analytical Processing
* OLTP Online Transaction Processing
* P&L Profit and Loss
* PCI Payment Card Industry
* PDF Portable Document Format
* PHI Personal Health Information
* PII Personally Identifiable Information
* RDBMS Relational Database Management System
* SDLC Software Development Life Cycle
* SQL Structured Query Language
* XML Extensible Markup Language
