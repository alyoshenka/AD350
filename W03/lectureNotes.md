# Lecture Notes, 1/18/2022

## Normalization

more an art than a science

have to understand the data to normalize the data

### Why do I care?

stops integrity issues

contradictory information = integrity issue

rules to stop all that bad stuff

### ACID -> Good

Atomic: transactions all or nothing

Consistent: only valid data

Isolation

Durability

achieved through normalization

---

anomaly: deviates from normal/standard

-> a situation in a database where the database contracicts itself

### Database Change Anomaly

#### Insert: new object requires NULL value to allow entry

Certain attrivutes cannot be inserted into the database withot the presence of other attributes

#### Update: same info on multiple rows

data inconsistency that results from data redundancy and a partial update

#### Delete: deletion of a record results in loss of data

deletion of a record that contains an attribute that shouldn't be deleted

Not as easy as it seems to figure out!

### Normal Forms

#### 1NF

unique key.

every record can be identified uniquely

each field is atomid

no duplicate columns or rows

all columns must be unique

compound key: 2+ fields required for unique identification

#### 2NF

elimination of **partial dependencies**

ex. The *name* and *description of my recipe are depencent on the recipe id. Only this recipe will have this name and description. This name and description will appear nowhere else.

#### 3NF

elimination of **transitive dependencies** (dependendy on non key field)

#### BCNF

no **non-trivial functional dependencies** of attributes on anything other than a superkey of a candidate key

candidate key: column (or set of columns) that can uniquely identify any database record

candidate key != primary key (but same characteristics)

superkey: no two distinct tuples that have the same values for the attributes in this set

BCNF *can* be violated when the table contains more than one candidate key

tuple: record where all parts can be different

#### 4NF

no non-trivial **multivalued dependencies** other than a candidate key

#### 5NF

every non-trivial join dependency is implied by the candidate keys

### What level is "good enough"?

scale and complexity need to be considered

1. good keys
    - directly associated with entity
    - real world detachments
        - VIN # vs license plate #
    - take real world into consideration
1. no uneccesary key attributes
    - if one field makes records unique, don't use 2
1. non-key dependent on key
1. if there can be 2, do not configure for 1
    - pet1, pet2, pet3...
1. if it should be a key, make it so
    - do not use properties of another entity as a property of the target entity
1. key column in one table should not be non-key in another
    - most often broken
        - ERD shows many entities clustered around central entity
        - central entity has several one to many relationships with the surrounding entities
        - surrounding entities have no relationships with any other entity

### Non Normalized Design Drawbacks

- many-to-many issue
- manual steps for DBA
- future database revisions subject to redesign

## General Database Terms

Users: user, designer, administrator, programmer

stored procedures 
- statement optimization
- reduced network traffic
- application independence
- database metrics and resource utilization

### Dealing with Referential Integrity

referential integrity -> no dangling pointers

- add cleanup to app software
- nightly maintenance
- enforce SQL rules
- FK approach  -> DBMS deletes marooned records

Don't use table aliases

