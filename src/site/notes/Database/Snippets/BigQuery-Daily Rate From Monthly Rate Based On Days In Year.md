---
{"dg-publish":true,"permalink":"/database/snippets/big-query-daily-rate-from-monthly-rate-based-on-days-in-year/","tags":["Type/CodeSnippet","Tech","Tech/Databases","Tech/Databases/BigQuery"],"updated":"2026-04-29T16:01:33.769+01:00","dg-note-properties":{"tags":["Type/CodeSnippet","Tech","Tech/Databases","Tech/Databases/BigQuery"]}}
---

# BigQuery - Daily Rate From Monthly Rate Based on Days In Year
Using the given `MonthlyAmount` and a date `MonthDate` inside the year you want to calculate for, get the daily rate based on the number of days in the year.

e.g.
A "normal" year and a leap year will give different results

```SQL
SELECT
  <MonthlyAmount> * (SELECT 12 / SAFE_CAST(FORMAT_DATE('%j', LAST_DAY(<MonthDate>, YEAR)) AS INT64))
```