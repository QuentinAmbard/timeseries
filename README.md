# Timeseries forecasting with Spark ML 

  - Download https://zeppelin.apache.org, Spark > 2.0 and load the notebook.
  - The timeseries can be loaded from .csv file instead of the C* table:
```scala
val df: DataFrame = spark.read
  .format("csv")
  .option("header", "true")
  .option("dateFormat", "M/d/YYYY")
  .schema(StructType(Array(StructField("time", DateType, true), StructField("amount", FloatType, true))))
  .csv("/home/quentin/projects/spark-ml/ml/src/main/resources/sale_timeserie2.csv")

df.createOrReplaceTempView("sales") 
```
  - This project is a very basic demo for an introduction to timeseries and spark ML
