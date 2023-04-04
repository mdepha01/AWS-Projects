**READ ME:**

- Before loading data Redshift empty tables need to be created first.
- Tables.sql is the query used to create the database schema for data loading.

**LOADING DATA:**

- **Loading data from S3 to Redshift.** You will use this process for loading 7 tables out of 8 tables created in above step.
- **Loading data from desktop file to Redshift.** You will use this process for loading 1 table out of 8 created in above step i.e. nation table.
- Data will be loaded from s3 and from local machine.

**Loading Data from S3:**

**COPY** command  loads large amounts of data effectively from Amazon S3 into Amazon Redshift. A single COPY command can load from multiple files into one table. It automatically loads the data in parallel from all the files present in the S3 location you provide.

Copy command, loads data into an empty table:

- Run the FromS3.sql file in the Redshift query editor.

**Loading data from local machine using Query Editor 2**

**1. setting up S3 for staging**

 - navigate to the CloudFormation stack "**RedshiftImmersionLab**".
 - copy the name of s3 bucket in this lab "**csv-file-store-4fc47a50**"
 - Navigate to Redshift console and go to **query editor 2**.
 - on the bottom left go to **settings** (settings gear icon).
 - navigate to S3 URI and put **s3://csv-file-store-4fc47a50**
 - ** The S3 URI is used for staging the file from the local machine.**

**2. loading file from loacl machine**

- From resources section, select and connect to your serverless workgroup.
- Click on **Load data**
- select **Load from local file**
- Browse and select the **Nation.csv file** downloaded earlier
- Data conversion parameters
- **Check Ignore header rows**
- **Done**
- **Target table options** select your serverless work group -- Database = dev -- Schema = public -- Table = nation -- Load data -- Notification of Loading data from a local file succeeded would be shown on top.

**Running Analyze**

To collect table statistics after loading data to a table analyze can be used however, it might impact performance.
Redshift automatiacally runs the analyze query during low peak hours. The analyze query can be seen below.

analyze table_name ; 


**Vacuum**

After running a table delete Redshift does a soft deletion i.e the rows are not actually deleted however, they are marked for deletion hence during an update
the new data is inserted into the marked rows. To reclaim space immediatelty after deletion Vacuum query can be ran.
