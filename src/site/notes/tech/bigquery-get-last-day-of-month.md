---
{"dg-publish":true,"permalink":"/tech/bigquery-get-last-day-of-month/","tags":["CodeSnippet","Databases","BigQuery"],"updated":"2026-04-23T14:06:06.136+01:00","dg-note-properties":{"tags":["CodeSnippet","Databases","BigQuery"]}}
---

# BigQuery - Last Day Of Month
Get the last day of the month for the current date.

```SQL
SELECT
  LAST_DAY(CURRENT_DATE(), MONTH)
```

See Also:
[[tech/bigquery-get-last-datetime-of-month\|Big Query Get Last DateTime of The Month]]
[[tech/bigquery-get-first-day-of-month\|Big Query Get First Day of The Month]]