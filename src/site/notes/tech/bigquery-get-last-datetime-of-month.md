---
{"dg-publish":true,"permalink":"/tech/bigquery-get-last-datetime-of-month/","tags":["CodeSnippet","Databases","BigQuery"],"updated":"2026-04-22T12:58:21.599+01:00","dg-note-properties":{"tags":["CodeSnippet","Databases","BigQuery"]}}
---

# BigQuery - Last Date time Of Month
Get the last date time to the second of the month to the second for the current date.

e.g.
For the date '2026-04-22' it would return '2026-04-30 23:59:59'

```SQL
SELECT DATETIME_ADD(DATETIME(LAST_DAY(CURRENT_DATE(), MONTH)), INTERVAL 86399 SECOND)
```

See Also:
[[tech/bigquery-get-last-day-of-month\|Big Query Get Last Day of The Month]]
[[tech/bigquery-get-first-day-of-month\|Big Query Get First Day of The Month]]