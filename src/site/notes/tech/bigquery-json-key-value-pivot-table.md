---
{"dg-publish":true,"permalink":"/tech/bigquery-json-key-value-pivot-table/","tags":["CodeSnippet","Databases","BigQuery"],"updated":"2026-04-23T14:48:02.607+01:00","dg-note-properties":{"tags":["CodeSnippet","Databases","BigQuery"]}}
---

# BigQuery - JSON Key : Value Pivot Table
Pivot from JSON data stored as a string column into a Key, Value structure.

```SQL
WITH basedata AS (
SELECT
  ARRAY(
    SELECT AS STRUCT 
      ChangeDateTime,
      AssetId,
      REVERSE(TRIM(SPLIT(REVERSE(kv), ':')[OFFSET(1)])) AS JSON_Key,
      ARRAY(SELECT AS STRUCT [REVERSE(TRIM(SPLIT(REVERSE(kv), ':')[OFFSET(0)]))]) AS JSON_Value
    FROM
      t.kv kv
    WHERE
      REVERSE(TRIM(SPLIT(REVERSE(kv), ':')[OFFSET(1)])) IN (<comma separated list of all required JSONKey(s)>)
  ) AS key_values
FROM
  `<database>.<schema>.<table>`,
  UNNEST([STRUCT(SPLIT(TRANSLATE(TO_JSON_STRING(JSONData_Column), '{}[]"\\', '')) AS kv)]) t
)
SELECT
  base.ChangeDateTime,
  base.AssetId,
  base.JSON_Key,
  base.JSON_Value
FROM
  basedata,
  unnest(basedata.key_value) AS base
ORDER BY
  AssetId,
  ChangeDateTime,
  JSON_Key
```