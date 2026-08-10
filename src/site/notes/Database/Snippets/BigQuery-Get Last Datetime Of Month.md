---
{"dg-publish":true,"permalink":"/database/snippets/big-query-get-last-datetime-of-month/","tags":["Type/CodeSnippet","Tech","Tech/Databases","Tech/Databases/BigQuery"],"updated":"2026-04-29T16:01:42.689+01:00","dg-note-properties":{"tags":["Type/CodeSnippet","Tech","Tech/Databases","Tech/Databases/BigQuery"]}}
---

# BigQuery - Get Last Date time Of Month
Get the last date time to the second of the month to the second for the current date.

e.g.
For the date '2026-04-22' it would return '2026-04-30 23:59:59'

```SQL
SELECT
  DATETIME_ADD(DATETIME(LAST_DAY(CURRENT_DATE(), MONTH)), INTERVAL 86399 SECOND)
```

See Also:
[[Database/Snippets/BigQuery-Get Last Day Of Month\|Big Query Get Last Day of The Month]]
[[Database/Snippets/BigQuery-Get First Day Of Month\|Big Query Get First Day of The Month]]