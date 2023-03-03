# Amazon Review - Big Data ETL
In this project, I have used PySpark in the Google Collab environment to download Amazon review data. After parsing the data into relational tables, I uploaded the transformed dataset into an AWS Postgres cloud server.

## About the Data
This project is based on Amazon review data for [video games]("https://s3.amazonaws.com/amazon-reviews-pds/tsv/amazon_reviews_us_Video_Games_v1_00.tsv.gz"), with a dataset that includes 1,785,997 records.

## Libraries and Tools
* Python
* Pyspark
* OS
* Findspark
* Google Collab
* AWS - RDS & S3 Buckets
* PgAdmin/Postgres SQL

## Results
First, the raw datset was read into a Spark Dataframe, with 1,785,997 records. The first 20 are shown here:

![df](Images/df.png)

Next, four subset dataframes were created. The review_id_df, products_df, and vine_df were each created by selecting desired columns for the table.
![review](Images/review-df.png)

![products](Images/product-df.png)

![vine](Images/vine-df.png)

The customer_df dataframe was created by counting the number of records grouped by customer_id to get the total number of records by customer. I presented the results in descending order of record counts.

![customer](Images/customer-df.png)

Lastly, all four dataframes were loaded to the cloud Postgres server on AWS. The upload was confirmed by querying the tables for records in PgAdmin.

![review table](Images/review-table.png)

![products table](Images/products-table.png)

![customer table](Images/customer-table.png)

![vine table](Images/vine-table.png)