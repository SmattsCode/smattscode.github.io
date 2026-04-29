---
{"dg-publish":true,"permalink":"/database/snippets/big-query-fill-in-dates/","tags":["Type/CodeSnippet","Tech","Tech/Databases","Tech/Databases/BigQuery"],"updated":"2026-04-29T16:01:36.237+01:00","dg-note-properties":{"tags":["Type/CodeSnippet","Tech","Tech/Databases","Tech/Databases/BigQuery"]}}
---

# BigQuery - Fill in Dates Between a Start and End Date
This script will produce different date lists based on the start date of each asset and ending at the end of last month.

e.g.
AssetId 1 starts on 2026-01-01 and AssetId 2 starts on 2026-03-01 and today's date is 2026-04-22.  The output would be

| AssetId | MonthStartDate | MonthEndDate |
|---------|----------------|--------------|
| 1       | 2026-01-01     | 2026-01-31   |
| 1       | 2026-02-01     | 2026-02-28   |
| 1       | 2026-03-01     | 2026-03-31   |
| 2       | 2026-03-01     | 2026-03-31   |

```SQL
SELECT
 AssetId,
 ArrayDate AS MonthStartDate,
 DATE_ADD(DATE_ADD(ArrayDate, INTERVAL 1 MONTH), INTERVAL -1 DAY) AS MonthEndDate
FROM (
  SELECT DISTINCT
    AssetId,
    ContractStartDate,
    DATE_ADD(DATE_ADD(CurrentUsageMonthEndDate, INTERVAL -1 MONTH), INTERVAL 1 DAY) AS NextDate
  from
    `<database>.<schema>.<table>`
  ),
  UNNEST(GENERATE_DATE_ARRAY(ContractStartDate, NextDate, INTERVAL 1 MONTH)) ArrayDate
ORDER BY
  AssetId,
  ArrayDate
```