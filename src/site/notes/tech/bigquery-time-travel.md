---
{"dg-publish":true,"permalink":"/tech/bigquery-time-travel/","tags":["CodeSnippet","Databases","BigQuery"],"updated":"2026-04-23T14:35:13.546+01:00","dg-note-properties":{"tags":["CodeSnippet","Databases","BigQuery"]}}
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