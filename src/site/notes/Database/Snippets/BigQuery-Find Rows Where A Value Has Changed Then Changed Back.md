---
{"dg-publish":true,"permalink":"/database/snippets/big-query-find-rows-where-a-value-has-changed-then-changed-back/","tags":["Type/CodeSnippet","Tech","Tech/Databases","Tech/Databases/BigQuery"],"updated":"2026-04-29T16:01:38.323+01:00","dg-note-properties":{"tags":["Type/CodeSnippet","Tech","Tech/Databases","Tech/Databases/BigQuery"]}}
---

# BigQuery - Find Rows Where A Value Has Changed Then Changed Back
Find AssetIds in a table where a value has changed and then changed back again.

```SQL
SELECT
  *
FROM (
  SELECT
    FromDateTime,
    AssetId,
    Value,
    LAG(Value)  OVER(PARTITION BY AssetId ORDER BY FromDateTime) AS Prev_Value,
    LEAD(Value) OVER(PARTITION BY AssetId ORDER BY FromDateTime) AS Next_Value
  FROM
    `<database>.<schema>.<table>`
) t
WHERE
  Value <> Prev_Value AND
  Value <> Next_Value AND
  Prev_Value = Next_Value
ORDER BY
  AssetId,
  FromDateTime
```