```
CREATE OR REPLACE EXTERNAL TABLE `key-tangent-486221-h7.zoomcamp.yellow_tripdata_hw3`
OPTIONS (
  format = 'PARQUET',
  uris = ['gs://dezoomcamp_hw3_2025_calina/yellow_tripdata_2024-*.parquet']
);

CREATE TABLE `key-tangent-486221-h7.zoomcamp.yellow_tripdata_hw3_materialised` AS SELECT * FROM `key-tangent-486221-h7.zoomcamp.yellow_tripdata_hw3`;

CREATE OR REPLACE TABLE `key-tangent-486221-h7.zoomcamp.yellow_tripdata_hw3_partitioned_clustered`
PARTITION BY DATE(tpep_dropoff_datetime)
CLUSTER BY VendorID AS
SELECT * FROM `key-tangent-486221-h7.zoomcamp.yellow_tripdata_hw3`;
```

