# de-zoomcamp-week2
Homework Submission for Week-02 (workflow-orchestration) containing the answers.
Have added the Kestra YAML files in the flows directory. 

Question 1: Within the execution for Yellow Taxi data for the year 2020 and month 12: what is the uncompressed file size (i.e. the output file yellow_tripdata_2020-12.csv of the extract task)?
Answer: 134.5 MiB

Question 2: What is the rendered value of the variable file when the inputs taxi is set to green, year is set to 2020, and month is set to 04 during execution?
Answer: green_tripdata_2020-04.csv


Question 3: How many rows are there for the Yellow Taxi data for all CSV files in the year 2020?
Answer: 24,648,499

SQL Query to get to that answer: 
SELECT COUNT(*)
FROM `premium-buckeye-484913-s0.kestra_homework_dataset.yellow_tripdata` 
-- WHERE TIMESTAMP_TRUNC(tpep_pickup_datetime, DAY) = TIMESTAMP("2020-02-03") LIMIT 1000;
WHERE LOWER(filename) LIKE 'yellow_tripdata_2020%'


Question 4: How many rows are there for the Green Taxi data for all CSV files in the year 2020?
Answer: 1,734,051

SQL Query to get to that answer: 
SELECT COUNT(*)
FROM `premium-buckeye-484913-s0.kestra_homework_dataset.green_tripdata` 
-- WHERE TIMESTAMP_TRUNC(tpep_pickup_datetime, DAY) = TIMESTAMP("2020-02-03") LIMIT 1000;
WHERE LOWER(filename) LIKE 'green_tripdata_2020%'


Question 5: How many rows are there for the Yellow Taxi data for the March 2021 CSV file? 
Answer: 1,925,152

SQL Query to get to that answer: 
SELECT COUNT(*)
FROM `premium-buckeye-484913-s0.kestra_homework_dataset.yellow_tripdata` 
-- WHERE TIMESTAMP_TRUNC(tpep_pickup_datetime, DAY) = TIMESTAMP("2020-02-03") LIMIT 1000;
WHERE LOWER(filename) LIKE 'yellow_tripdata_2021-03%'


Question 6: How would you configure the timezone to New York in a Schedule trigger?
Answer: Add a timezone property set to America/New_York in the Schedule trigger configuration. 