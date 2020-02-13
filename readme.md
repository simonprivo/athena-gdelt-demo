# GDELT DEMO

## Seed data

Copy data from gdelt main to demonstration bucket (the real bucket is GIGANTIC, would cost a lot to trove the entire set of data)

Source Bucket: s3://gdelt-open-data/events/
Destination Bucket: s3://simon-gdelt-data/

### Copy data from the source bucket to our destination
aws s3 cp s3://gdelt-open-data/events/20190918.export.csv s3://simon-gdelt-data/ --profile cath

### Summarize how much data is available
aws s3 ls s3://simon-gdelt-data/ --summarize --human-readable --profile cath

### Create a lookup table

Establish a table using AWS Glue to crawl the S3 bucket for data.

### Query number of entries
SELECT COUNT(*) as nb_events FROM "gdelt"."demosimon_gdelt_data";

### 

https://github.com/simonprivo/athena-gdelt-demo.git