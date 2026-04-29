---
{"dg-publish":true,"permalink":"/database/terms/normalisation/","tags":["Type/Term","Tech","Tech/Databases"],"updated":"2026-04-29T17:13:11.432+01:00","dg-note-properties":{"tags":["Type/Term","Tech","Tech/Databases"]}}
---

# Database Normalisation
When delving into the realm of Database Normalisation you need to keep in mind that when it was first suggested Relational Database Management Systems such as Postgres and SQLServer didn't exist yet.  As such much of this was theoretical and so the formal definitions are maths based, use technical terms and are often written as first-order predicate logic.  Don't worry if that sounded like a foreign language, I will give the formal definitions but also try to explain them in simple terms as well. 

This is one of those topics that is going to need a lot of diagrams to help the explanation so apologies in advance if you're on your phone :)

I am acutely aware, there is a lot of opinion on how far you need to go. I will write up all phases but add notes when I believe a step is far enough for given projects.

## WHAT?
Database Normalisation is an iterative design process used to organise and structure data.  A well structured database reduces redundancy, maintains integrity and prevents inconsistencies and anomalies.  It will also ensure efficient use of storage space.  There are several rules or stages referred to as **Normal Forms** and each one builds on the work of their predecessor.

## WHO & WHEN?
British computer scientist [Edgar F. Codd](https://en.wikipedia.org/wiki/Edgar_F._Codd) first described the process as part of his theory called the [Relational Model](https://en.wikipedia.org/wiki/Relational_model) in 1969.  Since then many others have expanded on his work:
- [Raymond F. Boyce](https://en.wikipedia.org/wiki/Raymond_F._Boyce)
- [Carlo Zaniolo](https://web.cs.ucla.edu/~zaniolo/)
- [Ronald Fagin](https://en.wikipedia.org/wiki/Ronald_Fagin)
- [Chris J. Date](https://en.wikipedia.org/wiki/Christopher_J._Date)

## WHY?
The result of Database Normalisation provides many advantages:
- **Reduced Data Redundancy:** Eliminates unnecessary repetition of data, saving storage space and reducing the chances of inconsistencies.
- **Improved Data Integrity:** Ensures that data is consistent and accurate across the database.
- **Simplified Data Maintenance:** Makes it easier to update, insert, and delete data without causing anomalies.
- **Enhanced Query Performance:** Well structured tables can lead to more efficient query execution.
- **Enhanced Flexibility:** Well structured tables better allow the system to flex and incorporate future requirements.

## HOW?
The process involves splitting often large and complex tables of data into several smaller ones and creating relationships between those tables.  These relationships define how the data in the two tables are linked together.


## The Normal Forms
As previously explained the process of Normalising data is an iterative one. Each step builds on the work done in the previous step.  These steps are called Normal Forms and data is only in a Normal Form if it satisfies the criteria for the current Normal Form **AND ALL** the previous ones.

Below is the list of Normal Forms in the order they should be completed.  I have given Unnormalised Form the order value of zero because this is the point at which you start with your original data in the format you get it.

| Order | Name                                                                         | Shortened Name |
| ----- | ---------------------------------------------------------------------------- | -------------- |
| 0     | UnNormalised Form                                                            | UNF            |
| 1     | [[Database/Terms/First Normal Form\|First Normal Form]]                     | 1NF            |
| 2     | [[Database/Terms/Second Normal Form\|Second Normal Form]]                   | 2NF            |
| 3     | [[Database/Terms/Third Normal Form\|Third Normal Form]]                     | 3NF            |
| 4     | [[Database/Terms/Elementary Key Normal Form\|Elementary Key Normal Form]]   | EKNF           |
| 5     | [[Database/Terms/Boyce-Codd Normal Form\|Boyce-Codd Normal Form]]           | BCNF           |
| 6     | [[Database/Terms/Fourth Normal Form\|Fourth Normal Form]]                   | 4NF            |
| 7     | [[Database/Terms/Essential Tuple Normal Form\|Essential Tuple Normal Form]] | ETNF           |
| 8     | [[Database/Terms/Fifth Normal Form\|Fifth Normal Form]]                     | 5NF            |
| 9     | [[Database/Terms/Domain Key Normal Form\|Domain Key Normal Form]]           | DKNF           |
| 10    | [[Database/Terms/Sixth Normal Form\|Sixth Normal Form]]                     | 6NF            |