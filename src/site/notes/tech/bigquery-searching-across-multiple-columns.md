---
{"dg-publish":true,"permalink":"/tech/bigquery-searching-across-multiple-columns/","tags":["CodeSnippet","Databases","BigQuery"],"updated":"2026-04-24T08:33:02.951+01:00","dg-note-properties":{"tags":["CodeSnippet","Databases","BigQuery"]}}
---

# BigQuery - Multiple Column Searching
Search for the same thing across multiple columns at the same time.

```SQL
WHERE
  '08003286081' IN (Phone1, CTN, MobileNumber)
```