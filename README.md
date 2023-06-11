# CompTIA Data+

{Awesome Works in Progress 📊📈}

## CompTIA
* [CompTIA Data+](https://www.comptia.org/certifications/data) - comptia.org
* [Create Your Study Plan NOW!](https://certs.comptia.org/trainingchecklist/)
* [How To Study for CompTIA Data+](https://www.comptia.org/blog/how-to-study-for-comptia-data)

# Domains
* [1.0 Data Concepts and Environments](#10-data-concepts-and-environments)
* [2.0 Data Mining](#20-data-mining)
* [3.0 Data Analysis](#30-data-analysis)
* [4.0 Visualization](#40-visualization)
* [5.0 Data Governance, Quality, and Controls](#50-data-governance-quality-and-controls)
* [Acronymns](#acronyms)
-----

## 1.0 Data Concepts and Environments
### 1.1 Identify basic concepts of data schemas and dimensions
#### Databases
`Relational | Non-relational`
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
#### Structures
`Structured Data | Unstructured Data`
##### Structured Data
* Defined Rows/Columns: This refers to data that is organized in a tabular form, like a spreadsheet or a relational database, where each row represents a record and each column represents an attribute of that record. This is a highly structured format which is easy to query and analyze.
* Key-Value Pairs: This is a type of data model where each data item has a key that is uniquely associated with it, similar to a dictionary or a map. This is commonly used in NoSQL databases and allows for efficient data retrieval when the key is known.
##### Unstructured Data
* Undefined Fields: This refers to data that doesn't have a pre-defined data model or organization. Examples include text data like emails and word documents, as well as multimedia content such as images, audio, and video files. This type of data is more difficult to analyze and process but can contain rich and complex information.
* Machine Data: This is a form of unstructured data generated by computers or machines, often in real-time and at high volumes. Examples include log files, sensor data, or data produced by internet-connected devices. This data is typically unstructured and can be challenging to analyze but can offer significant insights when properly processed.

-----
## 2.0 Data Mining
### 2.1 Explain data acquisition concepts
`ETL | ELT | Delta Load | API`
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
* Query Optimization: This is a function of the database management system where it attempts to determine the most efficient way to execute a given query by considering the different query plans.
* Parametrization: In the context of databases, it's a way of structuring a query to avoid SQL injection attacks and optimize query execution. Instead of directly embedding values, placeholders are used which are then supplied at execution time.
* Indexing: An index is a data structure that improves the speed of data retrieval operations on a database. It's similar to the index at the back of a book, allowing the database to find data without having to scan every row in a table.
* Temporary Table in the Query Set: A temporary table is a table that is used to store intermediate results. These can be useful in complex queries where you need to work with subsets of data multiple times in a single query.
* Subset of Records: This is a smaller set of data extracted from a larger dataset, usually based on certain criteria. Querying a subset of records can speed up operations by reducing the amount of data that needs to be processed.
* Execution Plan: This is the sequence of operations that the database will perform to execute a given query. Query optimizers generate different execution plans and select the one with the lowest cost based on factors like CPU usage, disk reads, and memory usage.

-----
## 3.0 Data Analysis
### 3.1 Given a scenario, apply the appropriate descriptive statistical methods
#### Measures of central tendency
* Measures of Central Tendency: These are statistical measures that identify the center of a data set. The central tendency gives a single value that represents the entire distribution of data, providing a summary of the data.
   * Mean: The mean, often called the average, is calculated by adding up all the values in a data set and then dividing by the number of values. It's a measure of the central location of data in a set.
   * Median: The median is the middle number in a sorted, ascending or descending, list of numbers. If the data set contains an even number of observations, the median is the average of the two middle numbers. It divides the data set into two equal halves.
   * Mode: The mode is the value that appears most frequently in a data set. A data set may have one mode (unimodal), two modes (bimodal), or multiple modes (multimodal). It's the only measure of central tendency that can be used with nominal data, which have purely qualitative value.
#### Measures of dispersion
* Measures of Dispersion: These are statistical measures that represent how spread out the values are in a data set. They provide an understanding of the variability or diversity of the data.
   * Range: The range is the difference between the largest (max) and smallest (min) values in a data set. It provides a basic measure of the spread of the entire data.
     * Max: The maximum or "max" is the highest value in a data set.
     * Min: The minimum or "min" is the lowest value in a data set.
   * Distribution: The distribution of a statistical data set refers to the arrangement of its values. It shows the spread and skewness of data. Common types include normal distribution, binomial distribution, and uniform distribution.
   * Variance: Variance measures how spread out the numbers in a data set are. It's calculated by taking the average of the squared differences from the mean.
   * Standard Deviation: The standard deviation is the square root of the variance. It measures the average distance between each data point and the mean. It's a popular measure of variability because it returns to the original unit of measure of the data set.
* Frequencies/Percentages: Frequencies refer to the number of times a particular value or category appears in a dataset. When expressed as a proportion of the total number of observations, this is often represented as a percentage.
* Percent Change: Percent change is a measure that expresses the change in a variable over time as a percentage of the initial value. It's often used to express growth or decline from one period to another in financial and economic data.
* Percent Difference: Percent difference is a measure of the relative difference between two quantities, expressed as a percentage. It is often used when comparing two quantities where neither is considered an initial or starting value.
* Confidence Intervals: A confidence interval is a range of values, derived from a statistical estimate, that is likely to contain an unknown population parameter. It is often expressed with a confidence level (e.g., a 95% confidence interval) to show the probability that the parameter lies within the given range.


### 3.2 Explain the purpose of inferential statistical methods
* Statistical testing concepts
   * t-tests: A t-test is a statistical hypothesis test used to determine whether there is a significant difference between the means of two groups. The test assumes that the data follows a normal distribution and that variances are equal.
   * Z-score: A Z-score is a statistical measurement that describes a value's relationship to the mean of a group of values. It's expressed in terms of standard deviations from the mean. A Z-score of 0 indicates that the data point's score is identical to the mean score.
   * p-values: In statistical testing, a p-value is the probability of obtaining a result at least as extreme as the one that was actually observed, given that the null hypothesis is true. A small p-value (typically ≤ 0.05) indicates strong evidence against the null hypothesis, so you reject the null hypothesis.
   * Chi-squared: The Chi-squared test is a statistical hypothesis test that's used to determine whether there's a significant association between two categorical variables in a sample. It compares the observed frequencies in each category of a contingency table with the frequencies that would be expected under the null hypothesis of no association.

* Hypothesis Testing: Hypothesis testing is a statistical method used to make inferences or draw conclusions about a population based on a sample of data. It involves setting up a null hypothesis (typically representing no effect or no difference), and then using data to decide whether or not to reject this null hypothesis in favor of an alternative hypothesis.
   * Type I Error: A Type I error occurs when the null hypothesis is true, but is incorrectly rejected. It's the equivalent of a false positive. For example, concluding that a medical treatment has an effect when it really doesn't.
   * Type II Error: A Type II error occurs when the null hypothesis is false, but is incorrectly accepted. It's the equivalent of a false negative. For example, concluding that a medical treatment has no effect when it actually does.
* Simple Linear Regression: Simple linear regression is a statistical method that allows us to summarize and study relationships between two continuous (quantitative) variables. One variable, denoted x, is regarded as the predictor, explanatory, or independent variable. The other variable, denoted y, is regarded as the response, outcome, or dependent variable. It assumes a linear relationship between x and y.
* Correlation: Correlation is a statistical measure that expresses the extent to which two variables are linearly related. It's a number between -1 and 1 wherein the sign determines the direction of the relationship (positive or negative) and the magnitude determines the strength of the relationship, with 1 indicating a perfect linear relationship.

### 3.3 Summarize types of analysis and key analysis techniques
####  Process to determine type of analysis
* Process to Determine Type of Analysis: This process involves identifying the most appropriate statistical or data analysis method based on the research question, the nature of the data, and the available resources.
   * Review/Refine Business Questions: The first step in any analysis process, this involves clearly defining the problem or question that needs to be answered. These questions should be specific, measurable, achievable, relevant, and time-bound.
   * Determine Data Needs and Sources to Perform Analysis: This step involves identifying the types of data needed to answer the research question, and determining where and how this data can be collected. The required data might come from a variety of sources, including databases, surveys, or external research.
   * Scoping/Gap Analysis: Scoping is the process of determining the parameters or boundaries of the analysis, such as the time period, geographical area, or specific sub-groups to be considered. Gap analysis, on the other hand, involves identifying any missing data or information that could impact the accuracy or validity of the analysis.

#### Type of analysis
• Type of Analysis: This refers to the specific method or approach used to analyze and interpret data. The type of analysis chosen depends on the nature of the data and the research question or business problem being addressed.
* Trend Analysis: This involves examining data over time to identify patterns or trends. It's often used in business to forecast future behavior.
   * Comparison of Data Over Time: This involves looking at data from different time periods to identify changes, trends, or patterns over time.
* Performance Analysis: This involves comparing actual results or outputs against planned or expected ones. It's used to understand how well a process, system, or organization is performing.
   * Tracking Measurements Against Defined Goals: This refers to regularly monitoring and evaluating progress toward specific objectives or targets.
   * Basic Projections to Achieve Goals: This involves estimating future performance based on current data and trends, to guide decision-making and planning.
* Exploratory Data Analysis: This is an approach to analyzing data sets, often large ones, to summarize their main characteristics, often using visual methods or descriptive statistics.
   * Use of Descriptive Statistics to Determine Observations: This involves using statistical methods (like measures of central tendency or dispersion) to summarize and understand the data.
* Link Analysis: This is a type of network analysis used to explore relationships (links) between objects. It's often used in fields such as information science and social network analysis.
   * Connection of Data Points or Pathway: This refers to the process of identifying relationships or connections between different data points, which can provide insight into patterns or trends.

### 3.4 Identify common data analytics tools
* Structured Query Language (SQL): A programming language used for managing and manipulating relational databases.
* Python: A high-level, interpreted programming language known for its simplicity and versatility, widely used in data science, web development, automation, and more.
* Microsoft Excel: A spreadsheet program developed by Microsoft, commonly used for data organization, analysis, and visualization.
* R: A programming language and free software environment primarily used for statistical computing and graphics.
* RapidMiner: An advanced analytics platform that provides end-to-end workflows for machine learning, including data prep, results visualization, and model validation.
* IBM Cognos: A business intelligence suite by IBM which provides reporting, analysis, dashboards, and scorecards.
* IBM SPSS Modeler: A predictive analytics platform that offers predictive modeling, data mining, and deployment capabilities.
* IBM SPSS: A software package used for interactive, or batched, statistical analysis.
* SAS: A software suite developed by SAS Institute for advanced analytics, business intelligence, data management, and predictive analytics.
* Tableau: A powerful data visualization and business intelligence tool that helps users view and understand their data.
* [Power BI](https://powerbi.microsoft.com/): A business analytics tool by Microsoft that offers interactive visualizations, unified data access, and business intelligence capabilities.
* Qlik: A platform for modern data analytics, offering interactive data visualization, reporting, and business intelligence capabilities.
* MicroStrategy: An enterprise business intelligence (BI) application software provider which offers reporting and analytics capabilities.
* BusinessObjects: A suite of front-end applications from SAP that allow business users to view, sort, and analyze business intelligence data.
* Apex: A proprietary language developed by Salesforce.com, used to write complex business and transactional logic on the Salesforce platform.
* Datorama: A cloud-based artificial intelligence (AI) powered marketing intelligence and analytics platform.
* Domo: A platform that provides business intelligence tools and data visualization for real-time business decision-making.
* AWS QuickSight: A business intelligence service from Amazon that provides data visualization and insights from AWS data sources and other on-premises databases.
* [Stata](https://www.stata.com/): A suite of applications for data management and statistical analysis.
* Minitab: A statistical package that provides a broad range of basic and advanced data analysis techniques.

-----
## 4.0 Visualization
### 4.1 Given a scenario, translate business requirements to form a report
* Data Content: This refers to the actual information or data included in an analysis or report. It's the substance of the data set that's being analyzed.
* Filtering: Filtering involves narrowing down a data set to focus on certain information. This is often done by applying specific criteria to one or more data fields.
* Views: In the context of data analysis, a view refers to a particular way of looking at data. It can be a subset or arrangement of the data set that presents information in a particular way for a specific purpose.
* Date Range: This refers to the period of time from which data is included in the analysis. The date range can greatly affect the results of an analysis.
* Frequency: In the context of a report or analysis, frequency often refers to how often data is collected or how regularly a report is generated (daily, weekly, monthly, etc).
* Audience for Report: This refers to the individuals or groups who will receive or have access to the final report or analysis. It's important to consider the audience when preparing a report, as it can influence the content, format, and level of detail included in the report.
   * Distribution List: This is a list of recipients who will receive the report or analysis. It may include individuals within an organization, external stakeholders, or even automated systems that use the report for further processing.

### 4.2 Given a scenario, use appropriate design components for reports and dashboards
* Report Cover Page: This is the first page of a report that usually contains the title, date, and author's name. It may also include the organization's name and logo, the report's purpose, and other relevant information.
   * Instructions: In the context of a report cover page, instructions may refer to guidelines for how the report should be read or used. For example, it might include notes on terminology, how to interpret charts or graphs, or instructions for providing feedback.
   * Summary: This is a brief overview of the report's main findings, conclusions, or recommendations. It's typically written for readers who may not have time to read the entire report but need to understand the key points.
     * Observations and Insights: These are the significant findings or understandings gained from the analysis of the data. Observations might point out notable patterns or trends in the data, while insights provide deeper understanding, often explaining why these patterns exist or suggesting potential actions in response to these findings.

* Design Elements: These are the components used in the creation of a report, chart, or other visual display of data. They help to ensure the output is clear, visually pleasing, and easy to understand.
   * Color Schemes: These are combinations of colors used in a design. In a report or chart, a color scheme can help differentiate data points or categories and guide the viewer's eye.
   * Layout: This refers to the arrangement of elements on a page or screen. A well-designed layout can make a report easier to read and understand.
   * Font Size and Style: These elements affect the readability of text in a design. The right font size and style can make a report look professional and can emphasize key points.
   * Key Chart Elements: These are the parts of a chart that help viewers understand the data being presented.
     * Titles: These provide a concise description of what the chart is about.
     * Labels: These are used to identify the data points, categories, or axes in a chart.
     * Legends: A legend explains the symbols, colors, or lines used in the chart.
   * Corporate Reporting Standards/Style Guide: This is a set of guidelines for how company documents should be presented. It helps ensure consistency across different reports or presentations.
     * Branding: This refers to the distinctive design elements that represent a company, such as color schemes, logos, or specific fonts.
     * Color Codes: These are specific colors associated with a company's brand.
     * Logos/Trademarks: These are distinctive symbols or designs that identify a company or brand.
     * Watermark: A watermark is a faint design made in some paper during manufacture, which is visible when held against the light and typically identifies the maker. In the context of a report, it can be a light image or text placed behind the content for branding or security purposes.
### 4.3 Given a scenario, use appropriate methods for dashboard development
### 4.4 Given a scenario, apply the appropriate type of visualization
### 4.5 Compare and contrast types of reports

-----
## 5.0 Data Governance, Quality, and Controls
### 5.1 Summarize important data governance concepts
#### Security requirements
`Data encryption | Data transmission | De-identify data/data masking`
* [Guidelines for Media Sanitization](https://csrc.nist.gov/publications/detail/sp/800-88/rev-1/final) - nist.gov
* [Security Breach Notification Laws](https://www.ncsl.org/technology-and-communication/security-breach-notification-laws) - ncsl.org

#### Entity relationship requirements
*  The [cardinality](https://www.thedataschool.co.uk/eamonn-woodham/high-cardinality-vs-low-cardinality/) of a column refers to the number of distinct values that the column can take on. A column with high cardinality has a large number of distinct values, while a column with low cardinality has a small number of distinct values.
*  Data classification
   *  Business Classification: Public, Internal, Sensitive, Highly Sensitive
   *  Military Classifiation: Unclassified, Classified, Secret, Top Secret

### 5.2 Given a scenario, apply data quality control concepts
#### Automated Validation
* The **number of data points** is simply a count of all the measurements or observations within your data set. This is an important concept in statistical analysis, where the number of data points can affect everything from the reliability of your results to the types of analysis you can perform.

### 5.3 Explain master data management (MDM) concepts
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
