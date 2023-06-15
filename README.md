# PySpark

<h3 align="left">What is PySpark?</h3>
PySpark is a Python library for Apache Spark, a powerful open-source distributed computing system that is used for big data processing and analysis. Spark allows developers to process large amounts of data quickly and efficiently by distributing the data and processing tasks across multiple computers.

PySpark is a Python API that enables developers to write Spark applications using Python. It provides an interface for working with Spark through Python, allowing developers to leverage the power of Spark while writing code in a language they are familiar with.

Using PySpark, developers can perform data processing, machine learning, and other tasks on large datasets. It includes many built-in libraries for data manipulation, SQL, machine learning, and graph processing. PySpark also provides an interactive shell that allows developers to explore and experiment with data.

Overall, PySpark is a powerful tool for processing and analyzing large datasets using Python, and it's an essential tool for data scientists and data engineers.

<h3 align="left">Spark RDDs</h3>
RDD (Resilient Distributed Dataset) is the fundamental data structure of Apache Spark, which represents an immutable, fault-tolerant collection of elements that can be processed in parallel. RDDs are designed to handle large-scale datasets in a distributed computing environment, and they can be partitioned across a cluster of computers.

RDDs can be created from various data sources such as Hadoop Distributed File System (HDFS), local file system, or other storage systems, or they can be transformed from other RDDs using various transformations such as map, filter, reduceByKey, etc. RDDs can also be cached in memory to speed up subsequent computations.


Some common transformations in RDDs include:

map: applies a function to each element of an RDD and returns a new RDD<br>
filter: returns a new RDD with only the elements that satisfy a given condition<br>
flatMap: applies a function to each element of an RDD and returns a flattened collection of the results<br>
reduceByKey: groups the elements of an RDD by key and applies a reduction function to each group<br>


Some common actions in RDDs include:

count: returns the number of elements in an RDD<br>
collect: returns all the elements of an RDD as an array to the driver program<br>
saveAsTextFile: writes the elements of an RDD to a text file in the HDFS or a local file system<br>


Overall, RDDs are a powerful and flexible data structure that allows developers to perform complex distributed data processing tasks in a fault-tolerant and efficient manner using Apache Spark.<br>

<h3 align="left">Spark DFs</h3>
Spark DataFrame is a distributed collection of data organized into named columns, which are similar to a table in a relational database. Spark DataFrame provides a high-level API for distributed data processing, and it allows developers to work with structured and semi-structured data in a distributed computing environment.

Spark DataFrames are built on top of RDDs and they provide a more optimized API for working with structured data. They also provide optimizations such as query optimization, predicate pushdown, and column pruning, which can lead to significant performance improvements.

Spark DataFrames can be created from various data sources such as CSV files, Parquet files, JSON files, Hive tables, or other data sources. They can also be created from RDDs, Python Pandas dataframes, or Spark SQL queries.

 Some common transformations include:

select: returns a new DataFrame with selected columns<br>
filter: returns a new DataFrame with rows that satisfy a given condition<br>
groupBy: groups the rows of a DataFrame based on one or more columns<br>
join: joins two DataFrames based on a given column or set of columns<br>
agg: performs aggregation functions on the columns of a DataFrame<br>

Some common actions include:

show: prints the first n rows of a DataFrame to the console<br>
count: returns the number of rows in a DataFrame<br>
collect: returns all the rows of a DataFrame as an array to the driver program<br>
write: writes the contents of a DataFrame to a file or database<br>

Overall, Spark DataFrames provide a powerful and flexible API for working with structured and semi-structured data in a distributed computing environment, and they are an essential tool for data scientists and big data engineers.<br>

<h4 align="left">People who want to learn PySpark and AWS on Udemy</h4><a href="https://www.udemy.com/course/pyspark-aws-master-big-data-with-pyspark-and-aws">Click here</a>

<h4 align="left">PySpark Document</h4><a href="https://spark.apache.org/docs/latest/api/python/getting_started/index.html">Click here</a>

<h3 align="left">HOW TO CREATE A DATAFRAME FOR VARIABLE NUMBER OF COLUMNS</h3>

suppose file is like this

Rohit ,24
Ravi,25,abc@gmail.com
Rahul,23,123@gmail.com,Delhi
Rohan

note - there is no header in this file and we are unaware of how many maximum columns are there in file.

=> step1 - read file as text so u can get all data in one column

note - if u read file as CSV it will only take minimum no. of columns .

=> step 2 - Use split and withcolumn to create a list of all items in another column and then drop the column created in step 1.

=> step3 - Now get the maximum no. of columns using max and size.

note - use collect()[0][0] to get the value as int.

=> step4 - Extend the code in step 3 ,using for loop outside that .

note - loop will go till the max. columns

In loop we will use withcolumn to give column name to each column

the rows which does not have any value will have null value
