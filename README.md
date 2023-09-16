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
* Online Transactional Processing (OLTP): OLTP refers to the real-time processing of transaction-based applications, typically associated with relational databases and business applications. OLTP systems prioritize fast, reliable, and consistent transactions and support a large number of short on-line transactions such as INSERT, UPDATE, DELETE. Examples include order entry, retail sales, and financial transaction systems. Learn more [Online transaction processing (OLTP) - Microsoft](https://learn.microsoft.com/en-us/azure/architecture/data-guide/relational-data/online-transaction-processing)
* Online Analytical Processing (OLAP): OLAP, on the other hand, refers to complex analysis of data, often originating from various sources. OLAP systems are optimized for read-heavy scenarios and facilitate multi-dimensional analytical queries (like aggregation and drill-down), enabling users to analyze data from multiple dimensions. These systems are typically used in business intelligence and data warehousing scenarios. Learn more [Online analytical processing (OLAP) - Microsoft](https://learn.microsoft.com/en-us/azure/architecture/data-guide/relational-data/online-analytical-processing)

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
* Delta Load: Delta load refers to the process of loading only the changed data (new data or updates to existing data) into a data warehouse or database. This can be more efficient than loading all data, as it minimizes data transfer and processing. Learn more [Perform delta data loads to data lakes using AWS DMS](https://aws.amazon.com/blogs/database/perform-delta-data-loads-to-data-lakes-using-aws-dms/)
* Application Programming Interfaces (APIs): APIs are sets of rules and protocols for how software applications should interact with each other. They allow different software systems to communicate and share data and functionality, making it easier to build and integrate software applications.
#### Data collection methods
* Web Scraping: This is a method used to extract data from websites. It involves making HTTP requests to the URLs you want to scrape, and then parsing the HTML response to retrieve the data you're interested in.
* Public Databases: These are databases that are openly available for anyone to access and use. They can contain a wide variety of data, from demographic information to scientific data.
* Application Programming Interface (API)/Web Services: APIs are a set of rules and protocols for how software applications should interact with each other. Web services are a type of API, typically operating over HTTP, that allow different software systems to communicate with each other over the internet.
* Survey: A method of collecting data directly from individuals. This usually involves asking a series of questions and recording the responses. Surveys can be conducted in various ways, including online, over the phone, or in person.
* Sampling: This is a statistical method that involves selecting a subset of individuals from a larger population, in order to estimate characteristics of the whole population. Learn more [Sampling Methods | Types, Techniques & Examples](https://www.scribbr.com/methodology/sampling-methods/)
* Observation: This is a method of collecting data by watching and recording behaviors or events. It can be done in natural settings or in more controlled conditions, and may involve no interaction with the subjects being observed, or active participation by the observer. 

### 2.2 Identify common reasons for cleansing and profiling datasets
* Missing Values
   *  [Concepts of MCAR, MAR and MNAR](https://stefvanbuuren.name/fimd/sec-MCAR.html) - stefvanbuuren.name
   * In statistics and data science, replacing missing values with the mean value of the remaining data in the variable is a form of **imputation**, which is a general term for techniques used to estimate and replace missing data with substituted values. 
   * [Flexible Imputation of Missing Data](https://stefvanbuuren.name/fimd/sec-historic.html) 🌟 - stefvanbuuren.name
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
* [Data Blending](https://www.alteryx.com/glossary/data-blending): Data blending is the process of combining data from multiple sources to create an actionable analytic dataset for business decision-making or for driving a specific business process. This process allows organizations to obtain value from a variety of sources and create deeper analyses. 
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

* Documentation Elements: These are various pieces of information included in a report or other document to provide additional context, details, or explanations.
   * Version Number: This indicates the iteration or revision of the document. It's important for tracking updates and changes over time.
   * Reference Data Sources: This refers to the original sources from which data was collected or obtained. It's important for transparency, accountability, and for those who may wish to conduct further research.
   * Reference Dates: These are key dates related to the report or data.
     * Report Run Date: This is the date on which the report was generated or created.
     * Data Refresh Date: This is the date when the data used in the report was last updated or refreshed.
     * Frequently Asked Questions (FAQs): These are common questions (and their answers) about the report or data. Including FAQs can help address reader's queries or potential confusions proactively.
     * Appendix: An appendix is a section at the end of a report that provides supplementary information. This can include detailed data, methodological notes, or any additional material that supports the content of the report but might be too detailed or tangential to include in the main body of the report.

### 4.3 Given a scenario, use appropriate methods for dashboard development
* Dashboard Considerations: These are various factors that must be taken into account when designing a data dashboard. They can influence the layout, functionality, and overall effectiveness of the dashboard.
   * Data Sources and Attributes: These are the origins of the data and the characteristics of that data, which must be understood to create an effective dashboard.
     * Field Definitions: These are explanations of what each data field or column in a dataset represents.
     * Dimensions: In a dataset, dimensions are categories or characteristics that can be used to organize or slice the data (like geographic region, time period, or product type).
     * Measures: These are the quantifiable data points that are being observed or measured (like sales volume, revenue, or number of customers).
   * Continuous/Live Data Feed vs. Static Data: A continuous or live data feed updates in real time or near real time, while static data does not change once it is loaded into the dashboard. The choice between these depends on the needs of the dashboard's users and the availability of data.
   * Consumer Types: These are the categories of people who will be using the dashboard. Different consumer types may have different needs or levels of expertise, influencing the design of the dashboard.
     * C-level Executives: High-level corporate officers (like a CEO or CFO) who need to see key performance indicators and summary data.
     * Management: Mid-level managers who may need both summary data and more detailed data on specific areas of operations.
     * External Vendors/Stakeholders: People outside the organization who have a vested interest in its performance, and who may need specific data related to their relationship with the organization.
     * General Public: Members of the public, who may require high-level data presented in a straightforward, easy-to-understand manner.
     * Technical Experts: These are people with expertise in a specific field or area, who may need detailed, specialized data.

* Development Process: This refers to the steps involved in creating a data dashboard, or any other digital product. It typically involves stages of planning, designing, developing, testing, and deploying.
   * Mockup/Wireframe: This is a basic visual guide used to suggest the layout and placement of elements in a dashboard. It serves as the blueprint for the design.
     * Layout/Presentation: This refers to the arrangement of elements on the dashboard, including where charts, tables, and other data visualizations will be placed.
     * Flow/Navigation: This refers to how a user moves through the dashboard, including how they interact with the data and switch between different views or screens.
     * Data Story Planning: This involves deciding how data will be presented and interpreted to tell a coherent and meaningful story.
   * Approval Granted: This is the stage at which stakeholders or decision-makers give their consent to proceed with the development of the dashboard as per the agreed design.
   * Develop Dashboard: This is the stage where the actual creation of the dashboard takes place. It involves coding, setting up data connections, and integrating all the elements as per the design.
   * Deploy to Production: This is the final stage, where the completed dashboard is made live or released into the operational environment for end users to interact with. This step may also involve user training and the creation of supporting documentation.

* Delivery Considerations: These refer to how the data dashboard or report is made available to its end users. This can affect how easily users can access and interact with the data.
   * Subscription: This is a method of delivery where users receive updates or new data automatically on a set schedule, often via email.
   * Scheduled Delivery: This refers to delivering reports or data updates at pre-determined times. This can be useful for ensuring users always have the most recent data.
   * Interactive (drill down/roll up): Interactive dashboards allow users to click on elements to see more detail (drill down) or less detail (roll up).
     * Saved Searches: This feature allows users to save specific queries or filters for future use.
     * Filtering: This is a feature that lets users narrow down the data they're viewing based on certain criteria.
     * Static: This refers to a dashboard or report that doesn't change or update. Static reports are often used for official documents or records.
     * Web Interface: This is a way of accessing the dashboard through a web browser, making it accessible from any device with internet access.
     * Dashboard Optimization: This involves improving the performance and usability of a dashboard. It can involve reducing load times, improving data visualization, or simplifying navigation.
     * Access Permissions: These determine who can view or interact with the dashboard. This is important for maintaining data security and ensuring that users only see the data they need.
### 4.4 Given a scenario, apply the appropriate type of visualization
* Line Chart
   * Description: A line chart displays information as a series of data points connected by straight line segments. It is often used to visualize a trend in data over intervals of time.
   * Pros: Good for showing trends over time and comparing multiple datasets.
   * Cons: Not suitable for showing individual data points or categories.
* Pie Chart
   * Description: A pie chart is a circular graph that displays parts-of-a-whole.
   * Pros: Simple to understand and can clearly show proportions.
   * Cons: Can be misleading or difficult to interpret with many sections or similar proportions.
* Bubble Chart
   * Description: A bubble chart is a variation of a scatter plot, in which data points are replaced with bubbles, with the size of the bubble representing a third variable.
   * Pros: Can represent three or four dimensions of data.
   * Cons: Can become confusing with too many bubbles or overlapping bubbles.
* Scatter Plot
   * Description: A scatter plot uses dots to represent values for two different numeric variables.
   * Pros: Great for showing relationships between two variables and identifying correlation.
   * Cons: Can be difficult to interpret without a clear trend or with many data points.
* Bar Chart
   * Description: A bar chart presents categorical data with rectangular bars with heights or lengths proportional to the values they represent.
   * Pros: Simple, easy to read, and good for comparing multiple categories.
   * Cons: Not suitable for showing trends over time.
* Histogram
   * Description: A histogram is a graphical display of data using bars of different heights to show the frequency of data points in a specified range.
   * Pros: Good for showing the distribution of a dataset and identifying skewness.
   * Cons: Requires interval data, can't represent categorical data.
* Waterfall Chart
   * Description: A waterfall chart is a form of data visualization that helps in determining the cumulative effect of sequentially introduced positive or negative values.
   * Pros: Excellent for visualizing how an initial value is affected by a series of intermediate positive or negative values.
   * Cons: Can become confusing with too many categories or stages.
* Heat Map
   * Description: A heat map is a two-dimensional representation of data where values are represented by colors.
   * Pros: Great for showing patterns and correlations.
   * Cons: Color choices can greatly affect readability and interpretation.
* Geographic Map
   * Description: A geographic map displays data related to geographic areas.
   * Pros: Intuitive for location-based data and can show spatial trends or distributions.
   * Cons: May require additional software or tools and can become cluttered with many data points.
* Tree Map
   * Description: A tree map displays hierarchical data as a set of nested rectangles, with size and color representing two dimensions of information.
   * Pros: Good for showing part-to-whole relationships within a hierarchy.
   * Cons: Can become hard to read with too many categories or levels.
* Stacked Chart
   * Description: A stacked chart is a variant of the bar chart or area chart where segments are placed on top of each other to show the cumulative effect.
   * Pros: Useful for showing part-to-whole relationships over time or across categories.
   * Cons: Can become difficult to interpret with many categories.
* Infographic
   * Description: An infographic combines charts, graphics, text, and images to present information in a visually engaging way.
   * Pros: Can be highly engaging and shareable, great for storytelling.
   * Cons: Can require more effort to create and may not be suitable
* Word Cloud
   * Description: A word cloud is a visual representation of text data where the size of each word indicates its frequency or importance.
   * Pros: It's a visually engaging way to quickly understand most prominent terms in a set of text data.
   * Cons: It lacks precision and context, and doesn't provide insights on the relationships between words.
### 4.5 Compare and contrast types of reports
* Static vs. Dynamic Reports: Static reports are fixed, displaying data that was captured at a particular point in time and does not change after the report is generated.
Dynamic reports can change in real time as data updates. They often allow interactive exploration of the data.
   * Point-in-Time: A point-in-time report reflects the state of the data at a particular moment in time.
   * Real-Time: A real-time report is updated instantaneously as the underlying data changes.
* Ad-Hoc/One-Time Report: An ad-hoc report is created to answer a specific business question or for a specific purpose. It may not be repeated or updated after it's generated.
* Self-Service/On-Demand: Self-service or on-demand reports allow users to generate reports as they need them, often using a user interface that allows them to select what data they want to include.
* Recurring Reports: These are reports that are generated on a regular basis, such as daily, weekly, monthly, etc. They often monitor consistent metrics or KPIs over time.
   * Compliance Reports: These are reports often mandated by laws or regulations, such as financial audits or health and safety inspections. They demonstrate that an organization is adhering to required standards.
   * Risk and Regulatory Reports: These reports are used to monitor risks faced by the organization and to ensure the organization is complying with industry regulations.
   * Operational Reports: These reports monitor the day-to-day operations of an organization. They can track performance metrics, key performance indicators (KPIs), and other measures of operational efficiency or effectiveness.
* Tactical/Research Report: A tactical or research report is often used to inform strategic decision-making. It might involve in-depth analysis of data, examination of trends, or research into a specific issue or question.

-----
## 5.0 Data Governance, Quality, and Controls
### 5.1 Summarize important data governance concepts
`Data encryption | Data transmission | De-identify data/data masking`
* Access Requirements: These are rules or conditions that determine who can access certain data or systems. They are often used to ensure data security and privacy.
   * Role-Based: In role-based access control, permissions are assigned based on the user's role within an organization. For instance, a manager might have access to more data or systems than an entry-level employee.
   * User Group-Based: User group-based access involves assigning permissions to groups of users. For instance, the marketing team might have access to different systems or data than the engineering team.
   * Data Use Agreements: These are agreements that specify how data can be used, who can use it, and for what purpose. They often include requirements for protecting the privacy and security of the data.
   * Release Approvals: These are processes or steps that must be completed before data or a system can be released or made accessible. They often involve reviews or checks to ensure data accuracy, security, and compliance with regulations or standards.

* Security Requirements: These are measures taken to protect data from unauthorized access, alteration, or destruction. They are critical to maintaining data integrity, privacy, and compliance with regulations.
   * Data Encryption: This is the process of converting data into a code to prevent unauthorized access. Encrypted data can only be accessed or decrypted with the correct encryption key.
   * Data Transmission: This refers to the methods and protocols used to transfer data from one location to another. Secure data transmission often involves encryption to protect the data while it's in transit.
   * De-Identify Data/Data Masking: De-identifying data involves removing or obscuring personally identifiable information (PII) to protect individual privacy. Data masking is a method of de-identification that replaces real data with fictional or scrambled data, while maintaining the data's usefulness for analysis or testing.
   * [Guidelines for Media Sanitization](https://csrc.nist.gov/publications/detail/sp/800-88/rev-1/final) - nist.gov
   * [Security Breach Notification Laws](https://www.ncsl.org/technology-and-communication/security-breach-notification-laws) - ncsl.org

* Storage Environment Requirements: These are considerations and conditions that determine where and how data is stored. They often involve a balance between accessibility, security, cost, and data volume.
   * Shared Drive: A shared drive is a server that allows multiple users to store and access files. It's often used in networked office environments to enable collaboration.
   * Cloud-Based Storage: This refers to storing data on remotely located servers accessed via the internet, which are maintained by a third-party provider. It's scalable, accessible from anywhere, and offers various levels of security.
   * Local Storage: This refers to storing data directly on the device being used to access it, such as the hard drive of a computer. It offers quick access and control but can be limited in space and is subject to the physical security of the device.

* Use Requirements: These are guidelines and rules that define how data can be used, manipulated, and managed within an organization or system. They help ensure data integrity, security, and compliance with laws or regulations.
   * Acceptable Use Policy: This is a policy that sets out what is considered acceptable behavior by users of a network or system. It often includes rules regarding data security, privacy, and misuse of resources.
   * Data Processing: This refers to the actions and methods applied to data to convert it from raw data into meaningful information. It can include collecting, organizing, transforming, and analyzing data.
   * Data Deletion: This is the process of permanently removing data from a storage medium. It is often done to save space, protect privacy, or comply with data retention policies or regulations.
   * Data Retention: This refers to policies or practices that determine how long data is kept before it is deleted or archived. It is often guided by legal requirements, business needs, or data management practices.

* Entity Relationship Requirements: These are rules and conditions that govern how different entities (such as tables in a database) relate to one another. They often involve identifiers, constraints, and relationships between entities.
   * Record Link Restrictions: These are rules or conditions that govern how and when records can be linked or related to one another. They may be used to ensure data integrity and consistency.
   * Data Constraints: These are rules that restrict the type, range, or format of data that can be entered into a database. For instance, a constraint might require that a field contain only numbers, or that a field must always be filled in.
   * The [cardinality](https://www.thedataschool.co.uk/eamonn-woodham/high-cardinality-vs-low-cardinality/) of a column refers to the number of distinct values that the column can take on. A column with high cardinality has a large number of distinct values, while a column with low cardinality has a small number of distinct values.

* Data Classification: This is the process of categorizing data based on its level of sensitivity, value, and criticality. This helps in efficient use and protection of data.
   *  Personally Identifiable Information (PII): This is any information that can be used to identify an individual. Examples of PII include names, social security numbers, and addresses. It's often subject to strict privacy laws and regulations.
   *  Personal Health Information (PHI): This refers to any information about health status, provision of health care, or payment for health care that can be linked to a specific individual. It's protected under privacy laws such as the Health Insurance Portability and Accountability Act (HIPAA) in the U.S.
   *  Payment Card Industry (PCI): This refers to the regulatory standards established by the Payment Card Industry Security Standards Council to protect credit cardholder data.
   *  Data classification samples
      *  Business Classification: Public, Internal, Sensitive, Highly Sensitive
      *  Military Classifiation: Unclassified, Classified, Secret, Top Secret
* Jurisdiction Requirements: These are legal obligations that vary depending on the location where data is held, processed, or transferred. They can be shaped by industry and governmental regulations.
   *  Impact of Industry and Governmental Regulations: These are the effects that laws, rules, and regulations can have on how data must be handled. This can influence data storage, transfer, and privacy measures.
* Data Breach Reporting: This is the process of informing appropriate authorities, such as regulatory bodies, about a data breach. Reporting requirements can vary by jurisdiction, but often include a description of the breach, the types of data involved, and the response to the breach.
   *  Escalate to Appropriate Authority: In the event of a data breach, escalation involves notifying the relevant individuals or teams within an organization who are responsible for responding to the breach. This can include IT teams, management, and legal departments.

### 5.2 Given a scenario, apply data quality control concepts
* Circumstances to check for quality
   * Data Acquisition/Data Source: Refers to the process and origins of collecting data. Quality checks here ensure the source is credible, reliable, and that the data is complete, accurate, and relevant.
   * Data Transformation/Intrahops:
     * Pass-through: A scenario where data is transferred from one system to another without any modifications. Quality checks ensure the integrity and accuracy of the data during this process.
     * Conversion: A process in which data is changed from one form to another, such as from one format to another or one unit to another. Quality checks here ensure that the conversion process doesn't distort the data's original meaning or value.
   * Data Manipulation: This refers to the process of adjusting data to make it suitable for further analysis or processing. Quality checks involve ensuring data has been manipulated correctly and appropriately, maintaining its integrity and relevance.
   * Final Product (Report/Dashboard, etc.): This refers to the end result of data processing and analysis, often presented in a visual format for ease of understanding. Quality checks here ensure that the final product is accurate, clear, relevant, and provides valuable insights.
* Automated Validation:
   * Data Field to Data Type Validation: This involves checking that each data field contains the expected type of data (i.e., text, number, date), ensuring consistency and reducing the chances of processing errors.
   * Number of Data Points: This refers to the total count of individual pieces of information collected in a dataset. An automated validation here would confirm the expected number of data points has been received or processed, helping to identify any missing or extra data.
* Data Quality Dimensions
   * Data Consistency: This dimension measures whether data is uniformly represented across the entire dataset. Consistent data adheres to a uniform format, making it easier to compare and analyze.
   * Data Accuracy: This dimension gauges how closely the data in the dataset matches the true or real-world values. Accuracy is vital for analysis, as inaccurate data can lead to misleading conclusions.
   * Data Completeness: This checks whether all necessary data is present in the dataset. Incomplete data can cause bias in the analysis and may lead to incorrect conclusions.
   * Data Integrity: This refers to the overall correctness, coherence, and wholeness of data. It assesses if data is unaltered from its source and has not been corrupted during storage, retrieval, or processing.
   * Data Attribute Limitations: This refers to the constraints or restrictions placed on the values that specific data attributes can take.
* Data Quality Rule and Metrics
   * Conformity: This metric measures the level to which data adheres to the defined business rules or standards, helping ensure it is fit for use.
   * Non-Conformity: This metric identifies instances where data fails to adhere to the predefined standards or rules, indicating potential data quality issues.
   * Rows Passed: This is a count of the number of data records that have passed all the defined quality checks, meeting the required standards.
   * Rows Failed: This counts the number of data records that have not passed the defined quality checks, indicating a potential problem with the data.
* Methods to Validate Quality
   * Cross-Validation: This is a statistical method for assessing how the results of a statistical analysis will generalize to an independent data set, often used in machine learning to validate models.
   * Sample/Spot Check: This method involves checking a random sample of data to ensure it meets quality standards, providing a quick, high-level assessment of data quality.
   * Reasonable Expectations: This method uses domain knowledge to predict what the data should look like. It then verifies whether the actual data aligns with these predictions.
   * Data Profiling: This is the process of examining data from an existing source and summarizing it using statistical analysis and data visualization techniques to check its quality and condition.
   * Data Audits: This involves a comprehensive review of a dataset to assess its quality and accuracy, identify any issues, and propose solutions to correct these issues. It's a more thorough approach to validating data quality.

### 5.3 Explain master data management (MDM) concepts
* Processes
   * Consolidation of Multiple Data Fields: This process involves merging or combining several data fields into a single field to reduce redundancy and improve data management efficiency. This can simplify data analysis and ensure more consistent interpretations.
   * Standardization of Data Field Names: This process involves applying consistent naming conventions to data field names across a dataset or organization. Standardization makes it easier to understand, locate, and use data effectively. **"Standardization of data field names"** is a data management practice that involves creating a consistent format for naming data fields across a database or a collection of datasets. It ensures that the same type of information is always referred to by the same name and format. For example, one dataset might use "DOB" as a field name to indicate a person's date of birth, while another dataset might use "BirthDate". Standardizing these field names across all datasets might involve deciding to always use "DateOfBirth" for this information. This makes it immediately clear what information is contained in that field, regardless of which dataset you're looking at.
   * Data Dictionary: A data dictionary is a centralized repository of information about data, such as its meaning, relationships to other data, origin, usage, and format. It serves as a guide for understanding and managing specific datasets. A **data dictionary** is a centralized repository of information about data, such as its meaning, relationships to other data, origin, usage, and format. It serves as a catalog or a guide to understanding what data is in a system, how it is organized, and how it is used.

* Circumstances for MDM (Master Data Management)
   * Mergers and Acquisitions: In these scenarios, MDM is critical to consolidate and manage data from both organizations, enabling a single source of truth and avoiding potential conflicts or duplication in data.
   * Compliance with Policies and Regulations: MDM can help ensure consistent, accurate data across an organization, which is key to meeting regulatory compliance requirements and internal policies.
   * Streamline Data Access: MDM is used to provide a unified, consistent view of core business data, improving data accessibility and usability, which aids in decision-making and data-driven operations.


-----

## Acronyms
* ANOVA: Analysis of Variance
* API: Application Programming Interface
* AWS: Amazon Web Services
* BI: Business Intelligence
* CRM: Customer Relationship Management
* CSV: Comma-separated Values
* ELT: Extract, Load, Transform
* ETL: Extract, Transform, Load
* FAQs: Frequently Asked Questions
* GDPR: General Data Protection Regulation
* HTML: Hypertext Markup Language
* JSON: JavaScript Object Notation
* KPI: Key Performance Indicator
* MDM: Master Data Management
* NoSQL: Not Only Structured Query Language
* OLAP: Online Analytical Processing
* OLTP: Online Transaction Processing
* P&L: Profit and Loss
* PCI: Payment Card Industry
* PDF: Portable Document Format
* PHI: Personal Health Information
* PII: Personally Identifiable Information
* RDBMS: Relational Database Management System
* SDLC: Software Development Life Cycle
* SQL: Structured Query Language
* XML: Extensible Markup Language

_Extra_
* AI: Artificial Intelligence
* ML: Machine Learning
* DL: Deep Learning
* NLP: Natural Language Processing
* IoT: Internet of Things
* EDA: Exploratory Data Analysis
* SaaS: Software as a Service
* PaaS: Platform as a Service
* IaaS: Infrastructure as a Service
* DBMS: Database Management System
* HDFS: Hadoop Distributed File System
* FTP: File Transfer Protocol
* GUI: Graphical User Interface
* UX: User Experience
* UI: User Interface
* HTTPS: Hypertext Transfer Protocol Secure
* CSV: Comma-Separated Values
* GB: Gigabyte
* TB: Terabyte
