---
{"dg-publish":true,"permalink":"/tech/bigquery-daily-rate-from-monthly-rate-based-on-days-in-month/","tags":["CodeSnippet","Databases","BigQuery"],"updated":"2026-04-23T14:05:27.455+01:00","dg-note-properties":{"tags":["CodeSnippet","Databases","BigQuery"]}}
---

# BigQuery - Daily Rate From Monthly Rate Based on Days In Month
Using the given `MonthlyAmount` and a date `MonthDate` inside the month you want to calculate for, get the daily rate based on the number of days in the month.

e.g.
January and February will give different results

```SQL
SELECT
  <MonthlyAmount> / EXTRACT(DAY FROM LAST_DAY(<MonthDate>, MONTH))
```
