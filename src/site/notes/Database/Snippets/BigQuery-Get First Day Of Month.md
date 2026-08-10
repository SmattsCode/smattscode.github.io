---
{"dg-publish":true,"permalink":"/database/snippets/big-query-get-first-day-of-month/","tags":["Type/CodeSnippet","Tech","Tech/Databases","Tech/Databases/BigQuery"],"updated":"2026-04-29T16:01:39.583+01:00","dg-note-properties":{"tags":["Type/CodeSnippet","Tech","Tech/Databases","Tech/Databases/BigQuery"]}}
---

# BigQuery - Get First Day Of Month
Get the first day of the month for the current date.

```SQL
SELECT
  DATE_TRUNC(CURRENT_DATE(), MONTH)
```

See Also:
[[Database/Snippets/BigQuery-Get Last Day Of Month\|Big Query Get Last Day of The Month]]
[[Database/Snippets/BigQuery-Get Last Datetime Of Month\|Big Query Get Last DateTime of The Month]]