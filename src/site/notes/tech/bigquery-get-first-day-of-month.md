---
{"dg-publish":true,"permalink":"/tech/bigquery-get-first-day-of-month/","tags":["CodeSnippet","Databases","BigQuery"],"updated":"2026-04-23T14:05:56.840+01:00","dg-note-properties":{"tags":["CodeSnippet","Databases","BigQuery"]}}
---

# BigQuery - Get First Day Of Month
Get the first day of the month for the current date.

```SQL
SELECT
  DATE_TRUNC(CURRENT_DATE(), MONTH)
```

See Also:
[[tech/bigquery-get-last-day-of-month\|Big Query Get Last Day of The Month]]
[[tech/bigquery-get-last-datetime-of-month\|Big Query Get Last DateTime of The Month]]