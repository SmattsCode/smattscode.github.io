---
{"dg-publish":true,"permalink":"/database/snippets/big-query-daily-rate-from-monthly-rate-based-on-days-in-month/","tags":["Type/CodeSnippet","Tech","Tech/Databases","Tech/Databases/BigQuery"],"updated":"2026-04-29T16:01:31.450+01:00","dg-note-properties":{"tags":["Type/CodeSnippet","Tech","Tech/Databases","Tech/Databases/BigQuery"]}}
---

# BigQuery - Daily Rate From Monthly Rate Based on Days In Month
Using the given `MonthlyAmount` and a date `MonthDate` inside the month you want to calculate for, get the daily rate based on the number of days in the month.

e.g.
January and February will give different results

```SQL
SELECT
  <MonthlyAmount> / EXTRACT(DAY FROM LAST_DAY(<MonthDate>, MONTH))
```
