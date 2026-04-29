---
{"dg-publish":true,"permalink":"/database/snippets/sql-server-email-on-transaction-failure/","tags":["Type/CodeSnippet","Tech","Tech/Databases","Tech/Databases/SQLServer"],"updated":"2026-04-29T16:02:00.895+01:00","dg-note-properties":{"tags":["Type/CodeSnippet","Tech","Tech/Databases","Tech/Databases/SQLServer"]}}
---

# SQL Server Email On Transaction Failure
Once email has been setup on the server this snippet shows how to send emails when a transaction fails.  Should only be used when the query runs automatically without manual intervention otherwise you would see the failure.

```SQL
BEGIN
  BEGIN TRY
    BEGIN TRANSACTION;
      TRUNCATE TABLE [database].[schema].[tableA];

      INSERT INTO [database].[schema].[tableA] (
        [columnA],
        [columnB],
        [columnC]
      )
      SELECT
        [column1],
        [column2],
        [column3]
      FROM
        [database].[schema].[tableB];
  
      COMMIT;
  END TRY
  BEGIN CATCH
    ROLLBACK;

    EXEC msdb.dbo.sp_send_dbmail
      @profile_name = 'Company Email',
      @recipients = 'name@company.co.uk',
      @subject = 'Transaction Failed',
      @body = 'SQL Server Transaction FAILED when refreshing table [database].[schema].[tableA]',
      @importance = 'High'
  END CATCH;
END;
```