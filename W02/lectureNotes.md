# Remembering your SQL Class 1/11/2022

Peter Chen -> database model (ealy ERD)

## Elements of a Database

- data entity: an instance of an object (basically)

- entity set: collection of similar entities or objects

- relationship: association between 2+ entity sets

- cardinality: how many entities at each end of the relationship

- attribute: property about the entity

- key attribute: unique identifier

**Make sure to test your statements**

**Make sure queries are audited**

Humans understand things in heirarchies, so we tend to represent things in that format

## Good Database Design

- many competing design approaches, constantly evolving

- don't build databases in isolation, make sure they can be used in the way they are needed

- *design before you build*

- think about your environment: global web/localized internal; stay small/scale larger; sensitive/safe data; many/few users

- make a plan for interacting with supporting services

- where will your database exist?

commands -> not case sensitive

data -> case sensitive

"If you trust the default, then de fault is yours"