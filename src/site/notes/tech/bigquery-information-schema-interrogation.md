---
{"dg-publish":true,"permalink":"/tech/bigquery-information-schema-interrogation/","tags":["CodeSnippet","Databases","BigQuery"],"updated":"2026-04-23T15:34:16.625+01:00","dg-note-properties":{"tags":["CodeSnippet","Databases","BigQuery"]}}
---

# BigQuery - Information Schema Interogation

```SQL
SELECT
  CONCAT(table_catalog, ".", table_schema, ".", table_name) AS TableName,
  column_name AS ColumnName,
  data_type AS DataType,
  is_nullable AS Nullable,
  IF(column_default = "NULL", "", column_default) AS DefaultValue,
  is_partitioning_column as PartitioningColumn,
  IF(clustering_ordinal_position > 0, "YES", "NO") AS ClusteringColumn,
  COALESCE(CAST(clustering_ordinal_position AS STRING), "") AS ClusteringOrdinal
FROM
  `<database>.<scheme>.INFORMATION_SCHEMA.COLUMNS`
ORDER BY
  table_schema,
  table_name,
  ordinal_position
```
