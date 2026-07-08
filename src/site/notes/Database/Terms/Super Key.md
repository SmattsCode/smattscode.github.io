---
{"dg-publish":true,"permalink":"/database/terms/super-key/","tags":["Type/Term","Tech","Tech/Databases"],"updated":"2026-04-29T17:13:11.434+01:00","dg-note-properties":{"tags":["Type/Term","Tech","Tech/Databases"]}}
---

## Super Key
A set of one or more [[Database/Terms/Attributes\|Attributes]], which may include extra, unnecessary [[Database/Terms/Attributes\|Attributes]] that together mean each [[Database/Terms/Tuple\|Tuple]] in a [[Database/Terms/Relation\|Relation]] is unique.  If you were to include all columns in a table this should be a Super Key as you should not have the same rows duplicated.

Example:

| UserId | UserName | Email                | Password |
| ------ | -------- | -------------------- | -------- |
| 1      | AJones   | alex.jones@abc.com   | ######## |
| 2      | BSmith   | bob.smith@def.com    | ######## |
| 3      | CBloggs  | chris.bloggs@xyz.com | ######## |

Possible Super Keys:
(UserId, UserName, Email, Password)
(UserId, UserName, Email)
(UserId, UserName, Password)
(UserId, Email, Password)
(UserId, UserName)
(UserId, Email)
(UserId, Password)
(UserId)
(UserName)
(Email)

(Password) cannot be used as you could have more than one user with the same password.
