# Chapter 8 - Review Questions

Use the following tables for the examples below:

**RegularUser**

| Email         | Year | Sex  |
| ------------- | ---- | ---- |
| user1@gt.edu  | 1985 | M    |
| user10@gt.edu | 1986 | M    |
| user3@gt.edu  | 1967 | M    |
| user8@gt.edu  | 1968 | M    |

**Major60sEvents**

| Year | Event                          |
| ---- | ------------------------------ |
| 1963 | March on Washington            |
| 1963 | Ich bin ein Berliner speech    |
| 1963 | JFK Assassination              |
| 1962 | Cuban Missle Crisis            |
| 1961 | Berlin Wall comes up           |
| 1968 | Tet Offensive                  |
| 1968 | Bloody Sunday                  |
| 1968 | MLK Assassination              |
| 1969 | Moon Landing                   |
| 1967 | The Doors: Alabama Song        |
| 1966 | Rolling Stones: Paint it Black |

**UserInterests**

| Email        | Interest | SinceAge |
| ------------ | -------- | -------- |
| user1@gt.edu | Music    | 10       |
| user1@gt.edu | Reading  | 5        |
| user1@gt.edu | Tennis   | 14       |
| user2@gt.edu | Swimming | 1        |
| user2@gt.edu | Tennis   | 12       |
| user3@gt.edu | Swimming | 15       |
| user3@gt.edu | Tennis   | 9        |
| user3@gt.edu | Music    | 11       |
| user3@gt.edu | Reading  | 6        |
| user4@gt.edu | DIY      | 18       |
| user4@gt.edu | Music    | 18       |
| user4@gt.edu | Reading  | 18       |

**8.1.** List the operations of relational algebra and the purpose of each.

The operations of relational algebra, and purpose, are:

* **SELECT**: Used to choose a subset of tuples from a relation. In other words, **SELECT** grabs the rows from a table.

* **PROJECT**: Used to choose a subset of attributes, or columns, from a subset.

* **RENAME**: Used to change the names of relations or attributes

* **UNION**: Denoted by R ⋃ S, is used to get all tuples that exist in R, or S, or both.

* **INTERSECTION**: Denoted by R ⋂ S, this gets all tuples are in **both** R and S.

* **SET DIFFERENCE** or **MINUS**: Denoted by R - S, this include all tuples that are in R, but not in S.

* **CROSS (CARTESIAN) PRODUCT**: Denoted by R x S, this combines all tuples from both relations into one. Useful for combining data.

* **NATURAL JOIN**: Denoted by R ***** S, joins two relations for attributes that are the same, and only those. It keeps only one copy of the join attribute, and is also called in "inner" join.

* **THETA JOIN**: Denoted by R ⨝ S (e.g., RegularUser ⨝ <sub>BirthYear < EventYear</sub> Major60sEvents), theta join is similar to the natural join, but you can compare different attributes, and both join attributes will appear in the result. This is useful for a comparison expression.

* **LEFT OUTER JOIN**: Denoted by R ⟕ S (e.g., RegularUser ⟕ Major60sEvents), left outer join is used when you want to preserve data if there is not a match. For example, **"Find Email, Year, Sex, and event for RegularUser when (Birth)Year matches (Event)Year. Preserve RegularUser data even if they don't match an event."** This is a special case of the THETA JOIN.

* **DIVIDE BY**: Denoted by R ÷ S, this is used for finding attributes of S that have *at least* the attributes of R. Example: **Find Email of all users with at least the interests of User1** would result in:

| Email        |
| ------------ |
| user1@gt.edu |
| user3@gt.edu |

**8.2.** What is union compatibility? Why do the UNION, INTERSECTION, and DIFFERENCE operations require that the relations on which they are applied be union compatible?

**Union compatibility** states that two relations that you want to apply the UNION, INTERSECTION, or DIFFERENCE operators on must have the same type of tuples. These operations require union compatibility because these are set operations, which are binary. 

**8.3.** Discuss some types of queries for which renaming of attributes is necessary in order to specify the query unambiguously.

**8.4.** Discuss the various types of inner join operations. Why is theta join required?

Theta joins are required for doing comparisons, and for when a natural join is needed on tables with no common attribute.

**8.5.** What role does the concept of foreign key play when specifying the most common types of meaningful join operations?



8.6. What is the FUNCTION operation? For what is it used?

8.7. How are the OUTER JOIN operations different from the INNER JOIN operations? How is the OUTER UNION operation different from UNION?

8.8. In what sense does relational calculus differ from relational algebra, and in what sense are they similar?

8.9. How does tuple relational calculus differ from domain relational calculus?

8.10. Discuss the meanings of the existential quantifier (∃) and the universal quantifier (∀).

8.11. Define the following terms with respect to the tuple calculus: tuple variable, range relation, atom, formula, and expression.

8.12. Define the following terms with respect to the domain calculus: domain variable, range relation, atom, formula, and expression.

8.13. What is meant by a safe expression in relational calculus?

8.14. When is a query language called relationally complete?