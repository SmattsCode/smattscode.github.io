---
{"dg-publish":true,"permalink":"/tech/bigquery-creating-time-from-summed-parts/","tags":["CodeSnippet","Databases","BigQuery"],"updated":"2026-04-22T10:41:38.973+01:00","dg-note-properties":{"tags":["CodeSnippet","Databases","BigQuery"]}}
---

# BigQuery - Creating Time From Summed Parts
Sometimes duration is split out into it's component parts and you want the duration of several rows output as HH:MM:SS rather than it's parts..

e.g.
Convert 1 Hour, 79 Minutes and 65 Seconds to 02:20:05

```SQL
SELECT
  CAST(CONCAT(
    SAFE_CAST(SUM(DurationHours) AS INT64)
    +
    DIV(
      SAFE_CAST(sum(DurationMinutes) AS INT64)
      +
      DIV(SAFE_CAST(SUM(DurationSeconds) AS INT64), 60)
      ,60
    )
    ,":",
    MOD(
      SAFE_CAST(SUM(DurationMinutes) AS INT64)
      +
      DIV(SAFE_CAST(SUM(DurationSeconds) AS INT64), 60)
      ,60
    )
    ,":",
    MOD(SAFE_CAST(SUM(DurationSeconds) AS INT64), 60)
  ) AS TIME) AS UsageDurationAsATime
FROM
  `<database>.<scheme>.<table>`
```