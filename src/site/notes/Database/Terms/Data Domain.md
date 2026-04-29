---
{"dg-publish":true,"permalink":"/database/terms/data-domain/","tags":["Type/Term","Tech","Tech/Databases"],"updated":"2026-04-29T16:27:45.641+01:00","dg-note-properties":{"tags":["Type/Term","Tech","Tech/Databases"]}}
---

# Data Domain
Data Domain or sometimes just Domain defines the specific rules for an [[Database/Terms/Attributes\|Attribute]].  It defines the data type used, set of allowable values, and any constraints that should be applied to the data in a column.

Different types of Data Domains:

- **Atomic Domains** - Define the specific type of data held by a single attribute, such as Description or Percentage.
- **Reference Data** - Used for mapping data to predefined lists.

For instance the Data Domain of an [[Database/Terms/Attributes\|Attribute]] called `HasChildren` would have a data type of Boolean, because it is not a mandatory attribute it can accept null values.  As such the only possible values for this column are true, false, or null.