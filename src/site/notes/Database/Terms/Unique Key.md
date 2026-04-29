---
{"dg-publish":true,"permalink":"/database/terms/unique-key/","tags":["Type/Term","Tech","Tech/Databases"],"updated":"2026-04-29T17:13:11.435+01:00","dg-note-properties":{"tags":["Type/Term","Tech","Tech/Databases"]}}
---

# Unique Key
Ensures all [[Database/Terms/Attribute Value\|Attribute Values]] across one or more [[Database/Terms/Attributes\|Attributes]] are distinct for every [[Database/Terms/Tuple\|Tuple]] in a [[Database/Terms/Relation\|Relation]].

A Unique Key is actually a [[Database/Terms/Constraints\|Constraints]] rather than being an actual Key.

Example:

| UserId | ==UserName== | Email                | Password |
| ------ | ------------ | -------------------- | -------- |
| 1      | AJones       | alex.jones@abc.com   | ######## |
| 2      | BSmith       | bob.smith@def.com    | ######## |
| 3      | CBloggs      | chris.bloggs@xyz.com | ######## |

In the table above you would use `UserName` as the unique key because you would want all your users to have a unique name.

| ==UserId== | ==ProjectCodeName== | JoinedProjectOn |
| ---------- | ------------------- | ----------------|
| 1          | Halo                | 2026-02-19      |
| 1          | Crucible            | 2024-05-04      |
| 3          | Halo                | 2025-08-31      |

In this table however you would need to use both `UserId` and `ProjectCodeName` to ensure uniqueness.