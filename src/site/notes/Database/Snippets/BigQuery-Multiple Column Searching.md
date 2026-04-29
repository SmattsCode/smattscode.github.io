---
{"dg-publish":true,"permalink":"/database/snippets/big-query-multiple-column-searching/","tags":["Type/CodeSnippet","Tech","Tech/Databases","Tech/Databases/BigQuery"],"updated":"2026-04-29T16:01:51.310+01:00","dg-note-properties":{"tags":["Type/CodeSnippet","Tech","Tech/Databases","Tech/Databases/BigQuery"]}}
---

# BigQuery - Multiple Column Searching
Search for the same thing across multiple columns at the same time.

```SQL
WHERE
  '08003286081' IN (Phone1, CTN, MobileNumber)
```