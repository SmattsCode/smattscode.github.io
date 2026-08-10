---
{"dg-publish":true,"permalink":"/database/snippets/big-query-time-travel/","tags":["Type/CodeSnippet","Tech","Tech/Databases","Tech/Databases/BigQuery"],"updated":"2026-04-29T16:01:58.300+01:00","dg-note-properties":{"tags":["Type/CodeSnippet","Tech","Tech/Databases","Tech/Databases/BigQuery"]}}
---

# BigQuery - Time Travel
Run a query against the table to get the data from the state the table was in at the given timestamp.

e.g.
This would show the data from 1 hour ago.

```SQL
SELECT
  *
FROM
  `<database>.<schema>.<table>`
  FOR SYSTEM_TIME AS OF TIMESTAMP_SUB(CURRENT_TIMESTAMP(), INTERVAL 1 HOUR);
```