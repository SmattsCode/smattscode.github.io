---
{"dg-publish":true,"permalink":"/database/snippets/big-query-get-last-day-of-month/","tags":["Type/CodeSnippet","Tech","Tech/Databases","Tech/Databases/BigQuery"],"updated":"2026-04-29T16:01:45.066+01:00","dg-note-properties":{"tags":["Type/CodeSnippet","Tech","Tech/Databases","Tech/Databases/BigQuery"]}}
---

# BigQuery - Get Last Day Of Month
Get the last day of the month for the current date.

```SQL
SELECT
  LAST_DAY(CURRENT_DATE(), MONTH)
```

See Also:
[[Database/Snippets/BigQuery-Get Last Datetime Of Month\|Big Query Get Last DateTime of The Month]]
[[Database/Snippets/BigQuery-Get First Day Of Month\|Big Query Get First Day of The Month]]