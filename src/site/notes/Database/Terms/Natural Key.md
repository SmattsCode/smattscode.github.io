---
{"dg-publish":true,"permalink":"/database/terms/natural-key/","tags":["Type/Term","Tech","Tech/Databases"],"updated":"2026-04-29T17:13:11.431+01:00","dg-note-properties":{"tags":["Type/Term","Tech","Tech/Databases"]}}
---

# Natural Key
An [[Database/Terms/Attributes\|Attribute]] that occurs in the real world and has meaning that can uniquely identify a [[Database/Terms/Tuple\|Tuple]] in a [[Database/Terms/Relation\|Relation]].  For instance Email Address in a user table could be used as a Natural Primary key.

Example:

| ==UserName== | Email                | Password |
| ------------ | -------------------- | -------- |
| AJones       | alex.jones@abc.com   | ######## |
| BSmith       | bob.smith@def.com    | ######## |
| CBloggs      | chris.bloggs@xyz.com | ######## |

In the table above `UserName` could be used as a unique identifier as all entries are unique.  It is a Natural Key because User Name has real world meaning.