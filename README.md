# CompTIA Data+

## CompTIA
* [CompTIA Data+](https://www.comptia.org/certifications/data) - comptia.org
* [Create Your Study Plan NOW!](https://certs.comptia.org/trainingchecklist/)
* [How To Study for CompTIA Data+](https://www.comptia.org/blog/how-to-study-for-comptia-data)

# Domains
-----
## Data Concepts and Environments
### Identify basic concepts of data schemas and dimensions
#### Databases
* Relational
* Non-relational
#### Schema concepts
`Snowflake | Star`
* [Star Schema vs Snowflake Schema: Key Differences Between The Two](https://www.simplilearn.com/star-schema-vs-snowflake-schema-article) - simplilearn.com
### Compare and contrast different data types
### Compare and contrast common data structures and file formats
-----
## Data Mining
### Explain data acquisition concepts
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

### Identify common reasons for cleansing and profiling datasets
* Missing Values
   *  [Concepts of MCAR, MAR and MNAR](https://stefvanbuuren.name/fimd/sec-MCAR.html) - stefvanbuuren.name
   * In statistics and data science, replacing missing values with the mean value of the remaining data in the variable is a form of **imputation**, which is a general term for techniques used to estimate and replace missing data with substituted values. 
   * **Capping** in the context of data analysis is a method used to limit or "cap" extreme values in a dataset in order to reduce the impact of outliers. This method is also known as "winsorizing" or "truncation".
### Given a scenario, execute data manipulation techniques
### Explain common techniques for data manipulation and query optimization

-----
## Data Analysis
-----
## Visualization
-----
## Data Governance, Quality, and Controls
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
