#sparkconf=allow put ur conf on spark and sparkcontext=entry point/allow to read that file
from pyspark import SparkConf, SparkContext             
conf=SparkConf().setAppName("Read file")                
sc=SparkContext.getOrCreate(conf=conf)  

#provide file path using textFile or any path
text=sc.textFile("/FileStore/tables/sample.txt")        
text.collect()           

#it start processing file
