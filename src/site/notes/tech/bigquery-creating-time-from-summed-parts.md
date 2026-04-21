---
{"dg-publish":true,"permalink":"/tech/bigquery-creating-time-from-summed-parts/","tags":["CodeSnippet","Databases","BigQuery"],"updated":"2026-04-21T18:58:00.888+01:00","dg-note-properties":{"tags":["CodeSnippet","Databases","BigQuery"]}}
---

# BigQuery - Creating Time From Summed Parts
Sometimes duration is split out into it's component parts and you want the duration of several rows output as HH:MM:SS rather than it's parts..

e.g.
Convert 1 Hour, 79 Minutes and 65 Seconds to 02:20:05

```SQL
select
  cast(concat(
    safe_cast(sum(DurationHours) as int64)
    +
    div(
      safe_cast(sum(DurationMinutes) as int64)
      +
      div(safe_cast(sum(DurationSeconds) as int64), 60)
      ,60
    )
    ,":",
    mod(
      safe_cast(sum(DurationMinutes) as int64)
      +
      div(safe_cast(sum(DurationSeconds) as int64), 60)
      ,60
    )
    ,":",
    mod(safe_cast(sum(DurationSeconds) as int64), 60)
  ) as time) as UsageDurationAsATime
from
  `database.scheme.table`
```