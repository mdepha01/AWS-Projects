**READ ME:**

- Before loading data Redshift empty tables need to be created first.
- Tables.sql is the query used to create the database schema for data loading.

**LOADING DATA:**

- **Loading data from S3 to Redshift.** You will use this process for loading 7 tables out of 8 tables created in above step.
- **Loading data from desktop file to Redshift.** You will use this process for loading 1 table out of 8 created in above step i.e. nation table.
- Loading Data to Redshift from S3 is used in this lab.

**Loading Data from S3:**

**COPY** command  loads large amounts of data effectively from Amazon S3 into Amazon Redshift. A single COPY command can load from multiple files into one table. It automatically loads the data in parallel from all the files present in the S3 location you provide.

Copy command, loads data into an empty table:

- Run the FromS3.sql file in the Redshift query editor.
