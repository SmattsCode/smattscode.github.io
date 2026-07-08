---
{"dg-publish":true,"permalink":"/database/snippets/big-query-time-chunking/","tags":["Type/CodeSnippet","Tech","Tech/Databases","Tech/Databases/BigQuery"],"updated":"2026-04-29T16:01:55.989+01:00","dg-note-properties":{"tags":["Type/CodeSnippet","Tech","Tech/Databases","Tech/Databases/BigQuery"]}}
---

# BigQuery - Time Chunking
Show timestamps as being in their corresponding chunk of time.

e.g.
In this case show the current timestamp as the current quarter hour time chunk.
So `2026-04-22 12:43:00` would show as `2026-04-22 12:30:00`.

```SQL
SELECT
  TIMESTAMP_ADD( TIMESTAMP_TRUNC(CURRENT_TIMESTAMP(), HOUR) , INTERVAL (CAST(EXTRACT(MINUTE FROM CURRENT_TIMESTAMP()) / 15 AS INT64) * 15)  MINUTE)
```