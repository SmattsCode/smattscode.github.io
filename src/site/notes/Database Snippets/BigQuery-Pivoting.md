---
{"dg-publish":true,"permalink":"/database-snippets/big-query-pivoting/","tags":["CodeSnippet","Databases","BigQuery"],"updated":"2026-04-24T09:52:55.420+01:00","dg-note-properties":{"tags":["CodeSnippet","Databases","BigQuery"]}}
---

# BigQuery - Pivoting
Produce table at the start looks like:

| product | sales | quarter | year |
|---------|-------|---------|------|
| Kale    | 51    | Q1      | 2020 |
| Kale    | 23    | Q2      | 2020 |
| Kale    | 45    | Q3      | 2020 |
| Kale    |  3    | Q4      | 2020 |
| Kale    | 70    | Q1      | 2021 |
| Kale    | 85    | Q2      | 2021 |
| Apple   | 77    | Q1      | 2020 |
| Apple   |  0    | Q2      | 2020 |
| Apple   |  1    | Q1      | 2021 |

## Full Data Pivot
```SQL
SELECT
  *
FROM
  Produce
PIVOT(SUM(sales) FOR quarter IN ('Q1', 'Q2', 'Q3', 'Q4'))
```

Finish pivot table looks like:

| product | year | Q1 | Q2   | Q3   | Q4   |
|---------|------|----|------|------|------|
| Apple   | 2020 | 77 | 0    | NULL | NULL |
| Apple   | 2021 | 1  | NULL | NULL | NULL |
| Kale    | 2020 | 51 | 23   | 45   | 3    |
| Kale    | 2021 | 70 | 85   | NULL | NULL |

## Summarised Data Pivot (Quarters Only)
```SQL
SELECT
  *
FROM (
  SELECT
    product,
    sales,
    quarter
  FROM Produce
)
PIVOT(SUM(sales) FOR quarter IN ('Q1', 'Q2', 'Q3', 'Q4'))
```

Finish pivot table looks like:

| product | Q1  | Q2  | Q3   | Q4   |
|---------|-----|-----|------|------|
| Apple   | 78  | 0   | NULL | NULL |
| Kale    | 121 | 108 | 45   | 3    |

## Summarised Data Pivot (First 2 Quarters Only)
```SQL
/*Alternative to just return sales figures by first 2 quarters...*/
SELECT
  *
FROM (
  SELECT
    sales,
    quarter
  FROM
    Produce
)
PIVOT(SUM(sales) FOR quarter IN ('Q1', 'Q2'))
```

Finish pivot table looks like:

| product | Q1  | Q2  |
|---------|-----|-----|
| Apple   | 78  | 0   |
| Kale    | 121 | 108 |
