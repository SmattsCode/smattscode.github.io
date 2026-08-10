---
{"dg-publish":true,"permalink":"/database/snippets/sql-server-time-chunking/","tags":["Type/CodeSnippet","Tech","Tech/Databases","Tech/Databases/SQLServer"],"updated":"2026-04-29T16:02:04.216+01:00","dg-note-properties":{"tags":["Type/CodeSnippet","Tech","Tech/Databases","Tech/Databases/SQLServer"]}}
---

# SQL Server - Time Chunking
Show timestamps as being in their corresponding chunk of time.

e.g.
In this case show the current timestamp as the current 5 minute time chunk.
So `2026-04-22 12:49:00` would show as `2026-04-22 12:45:00`.

```SQL
SELECT
  DATEADD(SECOND, (CAST((DATEPART(SECOND, CURRENT_TIMESTAMP) / 5) AS INT) * 5), CAST(DATEADD(MINUTE, DATEDIFF(MINUTE, 0, CURRENT_TIMESTAMP), 0) AS DATETIME2));
```