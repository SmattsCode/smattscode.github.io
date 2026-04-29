---
{"dg-publish":true,"permalink":"/database/terms/candidate-key/","tags":["Type/Term","Tech","Tech/Databases"],"updated":"2026-04-29T17:13:11.429+01:00","dg-note-properties":{"tags":["Type/Term","Tech","Tech/Databases"]}}
---

# Candidate Key
A set of one or more [[Database/Terms/Attributes\|Attributes]] that can be considered for use as a [[Database/Terms/Primary Key\|Primary Key]] and therefore means each [[Database/Terms/Tuple\|Tuple]] in a [[Database/Terms/Relation\|Relation]] is unique.  Unlike [[Database/Terms/Super Key\|Super Keys]] all [[Database/Terms/Attributes\|Attributes]] in a Candidate Key must be required to create uniqueness. It is normal for there to be more than one Candidate key.  From a list of Candidate Keys one is chosen to be the [[Database/Terms/Primary Key\|Primary Key]] and the rest are considered [[Database/Terms/Alternate Key\|Alternate Keys]].

Example:

| UserId | UserName | Email                | Password |
| ------ | -------- | -------------------- | -------- |
| 1      | AJones   | alex.jones@abc.com   | ######## |
| 2      | BSmith   | bob.smith@def.com    | ######## |
| 3      | CBloggs  | chris.bloggs@xyz.com | ######## |


For the table above the list of possible Candidate Keys are:
- (UserId, UserName, Email)
- (UserId, UserName)
- (UserId, Email)
- ==(UserId)==
- (UserName)
- (Email)

In the table above UserId would be chosen as the [[Database/Terms/Primary Key\|Primary Key]] and the rest would be considered [[Database/Terms/Alternate Key\|Alternate Keys]].