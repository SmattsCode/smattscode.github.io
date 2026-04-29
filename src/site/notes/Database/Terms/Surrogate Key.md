---
{"dg-publish":true,"permalink":"/database/terms/surrogate-key/","tags":["Type/Term","Tech","Tech/Databases"],"updated":"2026-04-29T17:13:11.435+01:00","dg-note-properties":{"tags":["Type/Term","Tech","Tech/Databases"]}}
---

# Surrogate Key
An artificially generated identifier with no business meaning. It exists solely to uniquely identify a [[Database/Terms/Tuple\|Tuple]] within a [[Database/Terms/Relation\|Relation]] such as UserId.

Example:

| ==UserId== | UserName | Email                | Password |
| ---------- | -------- | -------------------- | -------- |
| 1          | AJones   | alex.jones@abc.com   | ######## |
| 2          | BSmith   | bob.smith@def.com    | ######## |
| 3          | CBloggs  | chris.bloggs@xyz.com | ######## |

In the table above `UserId` could be used as a unique identifier as all entries are unique, however it has no real world meaning.