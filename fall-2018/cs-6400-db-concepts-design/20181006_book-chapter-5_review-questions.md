# Chapter 5 - Review Questions

**5.1**: Define the following terms as they apply to the relational model of data: domain, attribute, n-tuple, relation schema, relation state, degree of a relation, relational database schema, and relational database state.

* **Domain**: A set of atomic values. A common method of specifying a domain is to specify a data type from which the data values forming the domain are draw.
* **Attribute**: A column header; a role or interpretation of the values in that particular column. NULL values represent attributes whose values are unknown, or do not exist (not applicable) for that tuple.
* **N-tuple**: Ordered list of values; in the relational model, each row in a table is a tuple.
* **Relation schema**: A "thing" used to describe a relation; made up of a relation name "R" and a list of attributes.
* **Relation state**: A **relation** or **relation state**, denoted by _r(R)_ is a set of n-tuples. Each n-tuple _t_ is an ordered list of _n_ values _t =<v<sub>1</sub>, v<sub>2</sub>, … , v<sub>n</sub>>,_ where each value _v<sub>i</sub>_, 1 ≤ i ≤ n, is an element of dom(A<sub>i</sub>), or is a special NULL value.
* **Degree of a relation**: Also **arity**, is the number of attributes _n_ of a relation schema.
* **Relational database schema**: A set of **relation schemas** and a set of **integrity constraints**.
* **Relational database state**: Set of **relation states** such that each r<sub>i</sub> is a state of R<sub>i</sub>, and such that the r<sub>i</sub> relation states satisfy the integrity constraints.

**5.2.** Why are tuples in a relation not ordered?

Depends on what is meant by "tuple". An _n-tuple_ is in fact an ordered list of values. However, in the alternative definition of a relation, it is not necessary to have a list of tuples to be ordered since the attribute name appears together with the values. This makes it unnecessary to order attribute name/value pairs.

**5.3.** Why are duplicate tuples not allowed in a relation?

A relation is a "set", and by definition, all elements of a set are distinct.

**5.4**. What is the difference between a key and a superkey?

The main difference between a **superkey** and a **key** is the fact that a **superkey** can have redundant attributes, whereas a **key** cannot. Here's a practical example from the book:

> A key is a superkey, but not vice versa. A superkey may be a key (if it is minimal) or may not be a key (if it is not minimal). Consider the STUDENT relation of Figure 5.1. The attribute set {Ssn} is a key of STUDENT because no two student tuples can have the same value for Ssn. Any set of attributes that includes Ssn—for example, {Ssn, Name, Age}—is a superkey. However, the superkey {Ssn, Name, Age} is not a key of STUDENT because removing Name or Age or both from the set still leaves us with a superkey. In general, any superkey formed from a single attribute is also a key. A key with multiple attributes must require all its attributes together to have the uniqueness property.

**5.5.** Why do we designate one of the candidate keys of a relation to be the primary key?

In general, keys are useful for identifying a set of tuples uniquely; we choose one of the **candidate keys** to be the **primary key** in this case when this is desired. The choice of a primary key from one of the candidate keys is arbitrary, but usually it is preferred to choose a key with a single attribute, or a smaller number of attribute to keep things simpler. The other candidate key that wasn't chosen then becomes a **unique key**.

**5.6.** Discuss the characteristics of relations that make them different from ordinary tables and files.

(Later)

**5.7.** Discuss the various reasons that lead to the occurrence of NULL values in relations.

The prevalence of a NULL values in relations usually occurs from one of the following reasons:

* The value exists in the real world, but is unknown (**Value unknown**)
* The value exists in the real world, but is not available (**Value unavailable**)
* The value is not applicable to that set of tuples (**Value does not apply**)

**5.8.** Discuss the entity integrity and referential integrity constraints. Why is each considered important?

**Entity integrity** (no primary key value can be NULL) is important because if a primary key is allowed to be NULL, the individual tuples in a relation cannot be uniquely identified. The **referential integrity constraint** ensures that a relation being referenced by another relation *must* first exist before it is referenced.

**5.9.** Define foreign key. What is this concept used for?

A foreign key is the formal name for a key that ensures referential integrity. A set of attributes FK in relation schema R<sub>1</sub>  is a foreign key of R<sub>1</sub> that references relation R<sub>2</sub> if it satisfies the following rules:

* The attributes in FK have the same domain(s) as the primary key attributes PK of R<sub>2</sub>; the attributes FK are said to **reference** or **refer** to the relation R<sub>2</sub>.
* A value of FK in a tuple t<sub>1</sub> of the current state r<sub>1</sub> (R<sub>1</sub>) either occurs as a value of PK for some tuple t<sub>2</sub> in the current state r<sub>2</sub> (R<sub>2</sub>) or is *NULL*.

**5.10.** What is a transaction? How does it differ from an Update operation?

A **transaction** is an executing program that includes some database operations, such as reading from the database, or applying insertions, deletions, or updates to the database. The chief difference between a **transaction** and an UPDATE operation is that UPDATE is a single operation (can be two if the UPDATE happens on a primary key, then it's a DELETE and INSERT) whereas a transaction can involve several statements, can be of multiple variaties (any combination of SELECT, INSERT, UPDATE, or DELETE)

