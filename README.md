# Relational Database Design

This is my learning process with course "Relational Database Design" by University of Colorado Boulder which I will take notes here 📝

Go to my image folder , [click here!!!](https://drive.google.com/drive/folders/14TFwUlCkA2Ysew4xs2-Wza537WEsmkJS?usp=share_link)

## Table of Contents

- [Relational Database Design](#relational-database-design)
  - [Table of Contents](#table-of-contents)
- [Module 1: Entity Relationship Models](#module-1-entity-relationship-models)
  - [Introduction to DBMS](#introduction-to-dbms)
    - [Data, Information, Knowledge, and Intelligence](#data-information-knowledge-and-intelligence)
    - [Solutions for Data Management](#solutions-for-data-management)
      - [Database](#database)
      - [Database Management Systems](#database-management-systems)
      - [Advantage/Disadvantage of DBMS](#advantagedisadvantage-of-dbms)
    - [Data Stored in DBMS](#data-stored-in-dbms)
      - [User Data](#user-data)
      - [Metadata](#metadata)
      - [Indexes](#indexes)
      - [Applications Metadata](#applications-metadata)
  - [Entities and Their Relationships](#entities-and-their-relationships)
    - [What are Entities and Attributes (Identifiers)?](#what-are-entities-and-attributes-identifiers)
      - [Entity Relationship Model](#entity-relationship-model)
    - [What are Relationships? Degree, Cardinality and Participation of Relationships](#what-are-relationships-degree-cardinality-and-participation-of-relationships)
      - [Relationships](#relationships)
      - [Relationships - Degree](#relationships---degree)
      - [Relationship - Cardinality](#relationship---cardinality)
      - [Relationship - Participation](#relationship---participation)
      - [Example](#example)
  - [Entity Relationship Diagram and Notations](#entity-relationship-diagram-and-notations)
    - [Entity Relationship Model Representation](#entity-relationship-model-representation)
    - [Crow's foot notation](#crows-foot-notation)
      - [**Entity**](#entity)
      - [**Attribute**](#attribute)
      - [**Relationship**](#relationship)
      - [Example](#example-1)
- [Module 2: Relational Models](#module-2-relational-models)
  - [Relation and Keys](#relation-and-keys)
    - [What are Relations?](#what-are-relations)
      - [Why are Relational Models?](#why-are-relational-models)
      - [Terminologies](#terminologies)
    - [What are key?](#what-are-key)
      - [Relational Keys](#relational-keys)
  - [Relational Schema](#relational-schema)
    - [What are the Relational Schemas?](#what-are-the-relational-schemas)
      - [Database Relations](#database-relations)
      - [Properies of Relations](#properies-of-relations)
  - [Convert ERD to Relational Schemas](#convert-erd-to-relational-schemas)
    - [How to Convert ERDs to Relational Models](#how-to-convert-erds-to-relational-models)
      - [Converting ERADs to Relational Models](#converting-erads-to-relational-models)
    - [Practice](#practice)
- [Module 3: Normalization](#module-3-normalization)
  - [Why we care about Normalization?](#why-we-care-about-normalization)
    - [Data Redundancy and Normalization](#data-redundancy-and-normalization)
      - [Data Redundancy](#data-redundancy)
      - [Normalization](#normalization)
      - [Benefit of Normalization](#benefit-of-normalization)
    - [Functional Dependency](#functional-dependency)
  - [Functional Dependencies and Normalization Forms](#functional-dependencies-and-normalization-forms)
    - [Full, Partial, and Transitive Functional Dependencies](#full-partial-and-transitive-functional-dependencies)
      - [Full/Partial FDs](#fullpartial-fds)
      - [Transitive FDs](#transitive-fds)
  - [Normalization Process to 3NF](#normalization-process-to-3nf)
    - [Normal Forms and Normalization Process](#normal-forms-and-normalization-process)
      - [Normalization Process](#normalization-process)
      - [First Normal Form (1NF)](#first-normal-form-1nf)
      - [Second Normal Form (2NF)](#second-normal-form-2nf)
      - [Third Normal Form (3NF)](#third-normal-form-3nf)
- [Link](#link)

# Module 1: Entity Relationship Models

## Introduction to DBMS

### Data, Information, Knowledge, and Intelligence

- Data: is a collection of facts in a raw or unorganized form such as numbers or characters. For example, 12012012 is just a sequence of numbers without apparent importance.
- Information: This is data that has been “cleaned” of errors and further processed in a way that makes it easier to measure, visualize and analyze for a specific purpose.
- Knowledge: When we don’t just view information as a description of collected facts, but also understand how to apply it to achieve our goals, we turn it into knowledge. This knowledge is often the edge that enterprises have over their competitors. As we uncover relationships that are not explicitly stated as information, we get deeper insights that take us higher up the DIKW pyramid.
- Wisdom (intelligence): Wisdom is the top of the DIKW hierarchy and to get there, we must answer questions such as ‘why do something’ and ‘what is best’. In other words, wisdom is knowledge applied in action.

<img src="https://ecolabsblog.files.wordpress.com/2010/11/data_info_knowledge_wisdom-scaled1000.png"></img>

### Solutions for Data Management

#### Database

- A structure that contains data
- Organize Data through:
  - Entities
  - Attributes
  - Relationships

#### Database Management Systems

- A program or a collection of programs through which users interact with a database.
- Popular DBMS:
  - Microsoft Access
  - MySQL
  - PostgreSQL
  - MongoDB (NoSQL)

#### Advantage/Disadvantage of DBMS

| Advantage of DBMS                                      | Disadvantage of DBMS       |
| ------------------------------------------------------ | -------------------------- |
| Getting more information from the same amount of data. | Increased complexity.      |
| Sharing data.                                          | Greater impact of failure. |
| Balancing conflicting requirements.                    | More diffcult recovery.    |
| Controlling redundancy.                                | Larger file size.          |
| Facilitating consistency.                              |                            |
| Referential integrity.                                 |                            |
| Expanding security.                                    |                            |
| Increasing productivity.                               |                            |
| Providing data independence.                           |                            |

### Data Stored in DBMS

- A Database contains: User Data, Metadata, Indexes, Application metadata.

#### User Data

- Data users work with directly by entering, updating and viewing.
- For our purpose, data will be generally stored in tables with some relationships between tables.
- Each table has one or more columns. A set of columns forms a database record.

#### Metadata

- Data about data.
- Data that describe how user data are stored in terms of table name, column name, data type, length, primary keys, etc.
- Metadata are typically stored in System tables on System Catalog and are typically only directly accessible by the DBMS or by the system administrator.

#### Indexes

- In keeping with our desire to provide users with several different views of data, indexes provide an alternate means of accessing user data. Sorting and Searching.
- Indexes allow the database to access a record without having to search through the entire table.
- Updating data requires an extra step: The index must also be updated.

#### Applications Metadata

- Many DBMS have storage facilities for forms, reports, queries and other application components.

- Applications Metadata is accessed via the database development programs.

## Entities and Their Relationships

### What are Entities and Attributes (Identifiers)?

To design a Relational Database, we start with an Entity Relationship Model (ER Model):

- Describes what are the entities the database is going to record
- Describes what are the attributes (and identifiers) of the entities
- Describes how the relationships among these entities
- To represent the Entity Relational Model in an explicit way, we the Entity Relationship Diagram.

#### Entity Relationship Model

An Entity Relationship model (or ER model) describes interrelated things of interest in a specific domain of knowledge.

<br>Concepts:

- Entity:
  The identifiable abstract object of interest (in Programming, we call Class). Examples: Students, Employees, Companies, Products, Transactions,...
- Attribute: characteristics of an entity of interest. Examples:
  - Students: FirstName, StudentID, Major,...
  - Employees: ID, SSN, ContactInfo, Department, Supervisor,...
  - Companies: LegalName, Location, Category, Rank,...
  - Products: SKU#, Category, InStockPrice, InStockQuantity,...
  - Transactions: CustomerID, StoreID, ProductID, ProductDescription, Price, Quanity, Tax, Total, Time,...
- Instance: a record/member of an entity of interest (with actual value of attributes). Examples:
  - A Student: FirstName = "Joe", StudentID = "DB001", Major = "Data Science"
  - A Employee: ID = "E0099", SSN = "123-45-6789", ContactInfo = "N/A", Department = "Education", Supervisor = "Smith"
- Identifier: A special attribute used to identify a specific instance of an entity. Examples:
  - Student: FirstName, **StudentID**, Major
  - Employees: **ID**, **SSN**, ContactInfo, Department, Supervisor,...
  - Companies: **LegalName**, Location, Category, Rank,...
  - Products: **SKU#**, Category, InStockPrice, InStockQuantity,...
- Relationship

### What are Relationships? Degree, Cardinality and Participation of Relationships

#### Relationships

- An association between two (or more) entities.
- More specifically, how the members of two (or more) entities are connected. Normally, we name a relationship with a verb.

#### Relationships - Degree

- A relationship can include one ore more entities.
- The degree of a relationship is the number of Entities that participate in the relationship.
- Relationships of degree 1 are called Unary relationships (also called Recursive).
- Relationships of degree 1 are called Binary relationships. Most relationships in databases are Binary

#### Relationship - Cardinality

Cardunality refers to the number of instances of the entity involved in the relationship. Also called max cardinality / multiplicity of a relationship.

There are three types:

- 1:N (also called One to Many)
- N:1 (also called Many to One)
- N:M (also called Many to Many)

#### Relationship - Participation

Participation of instances in a relationship may be mandatory or optional. Also called optionality, minimal cardinality of a relationship.

There are two types:

- Mandatory
- Optional

#### Example

**Entities and Attributes**

- Instructors have info: Name, \*EmpID, SSN, DoB, Email, Salary
- Courses have info: Title, \*Course#, Time, Location, Description
- Programs have info: \*Title, Chair, Office#, Contact, Description
- Students have info: Name, \*StuID, DOB, Email

**Relationship**

- An instructor **may** teach **mutiple** (0 or N) courses; and a course **might** be taught by **multiple** (0 or N) instructors.
- Each course **must** belong to **one and only one** (1 or 1) online-program, and each program **must** have **one or more** (1 or N) courses.
- A student **may** take **mutiple** (0 or N) courses; and a course **must** have **one or more** (1 or N) students.
- A student **must** belong to **exacty one** (1 or 1) program; and a program **may** have **one or more** (0 or N) students.
- A student **may** be friend of other students (0 or N).
- A student **must** have **exactly one** instructor (1 or 1) as advisor; and one instructor **may** advise **one or more** (0 or N) students.

## Entity Relationship Diagram and Notations

### Entity Relationship Model Representation

We represent Entity Relationship Models using ERD (Entiry Relationship Diagram)

- Represent Enitities (and attributes/identifiers)
- Represent Relationships (and cardinality/participation)
- Provide a high level picture of what the database is organized

There are several notations used for ERD:

- UML (Unified Modeling Language)
- Chen
- Crow's Foot (be used for this course) (using Lucid.app to draw ERDs)

### Crow's foot notation

#### **Entity**

<img src="https://vertabelo.com/blog/crow-s-foot-notation/crows-foot-notation-entity.png">

#### **Attribute**

<img src="https://vertabelo.com/blog/crow-s-foot-notation/crows-foot-notation-attributes.png">

#### **Relationship**

<img src="https://www.testingdocs.com/wp-content/uploads/Cardinality-Symbols-Database.png">

<img src="https://sites.google.com/site/tenjinsite/_/rsrc/1472680622751/reference/oracle/crows-foot/crow2.bmp">

#### Example

<img src="https://drive.google.com/uc?id=1hmDPA5wAMNUBNtu1JcLj49_LNPhFMwM8">

# Module 2: Relational Models

## Relation and Keys

### What are Relations?

#### Why are Relational Models?

- Relational Model organizes data in two-dimensional tables: columns and rows.
- Relational Model includes: Relations, Tuples, Attributes, keys and foreign keys.
- Relational Models are represented by set of Relational Schemas.

#### Terminologies

- A relation is a table with columns and rows.
  - Attribute is a named column of a relation.
  - Domain is the set of allowable values for one or more attributes.
  - Tuple is a row of a relation.
  - Degree is the number of attributes in a relation.
  - Cardinality is the number of tuples in a relation.
- Relational Database is a collection of normalized relations with distinct relation names.

<img src="https://binaryterms.com/wp-content/uploads/2019/11/Student-Relational-Model-diagram.jpg">

### What are key?

#### Relational Keys

**Superkey**

- An attribute, or a set of attributes, that uniquely identifies a tuple within a relation.

**Candidate Key**

- Superkey (K) such that no proper subset is a superkey within the relation.
  - In each tuple of R, values of K uniquely identify that tuple (uniqueness).
  - No proper subset of K has the uniqueness property (irreducibility).

**Primary Key**

- Candidate key selected to identify tuples uniquely within relation.

**Alternate Keys**

- Candidate keys that are not selected to be primary key.

**Foreign Key**

- Attribute, or set of attributes, within one relation that matches candidate key of some (possibly same) relation.

## Relational Schema

### What are the Relational Schemas?

#### Database Relations

- Relation schema: defines a relation by a set of attributes (and their domain).
- Relational database schema: set of relation schemas, each with distinct name.
- General format:
  - Name(<span style="color:red"><u>Attribute</u><sub>1</sub></span>, Attribute<sub>2</sub>, ..., <span style="color:red"><u>Attribute</u><sub>x</sub>(fk)</span>, Attribute<sub>N</sub>)
  - The attribute(s) with underline as key
  - The attribute(s) with (fk) as foreign key(s)

#### Properies of Relations

- Each tuple is distinct; there are no duplicate tuples.
- Order of attributes has no significance.
- Order of tuples has no significance, theoretically.
- Each cell of relation contains exactly one value.
- Each attribute has a distinct name.
- Values of an attribute are all from the same domain.
- Relation name is distinct from all other relation names in a Relational Model.

## Convert ERD to Relational Schemas

### How to Convert ERDs to Relational Models

#### Converting ERADs to Relational Models

General steps:

- Each entity will be converted directly to a relation.
- The attributes of the entity become the attributes of the relation.
- The Identifier of the Entity becomes a Key of the relation.
- Relationships will be mapped as foreign keys.

### Practice

<img src="https://drive.google.com/uc?id=1hmDPA5wAMNUBNtu1JcLj49_LNPhFMwM8">

Instructors(Name, <u>EmployID</u>, SSN, DoB, Email, Salary)

Courses(Title, <u>Course#</u>, Time, Location, Description, Title(fk))

Intructors_Course(<u>EmployID(fk)</u>, <u>Course#(fk)</u>)

Program(<u>Title</u>, Chair, Office#, Contact, Description)

Student(Name, <u>StuID</u>, DoB, Email, EmployID(fk))

Courses_Students (<u>Course#(fk)</u>, <u>StuID(fk)</u>)

Students_Students(<u>StuID</u>, <u>FriendID</u>)

# Module 3: Normalization

## Why we care about Normalization?

### Data Redundancy and Normalization

#### Data Redundancy

- Data redundancy is a condition created within a database or data storage technology in which the same piece of data is held in two separate places.

- This can mean two different fields within a single database, or two different spots in multiple software environments or platforms. Whenever data is repeated, it basically constitutes data redundancy.

- Data redundancy can occur by accident but is also done deliberately for backup and recovery purposes.

- Major aim of relational database design is to group attributes into relations to minimize data redundancy.

#### Normalization

Normalization is a technique for producing a set of suitable relations that support the data requirements of an enterprise.

Characteristics of suitable relations are:

- The mininal number of attributes necessary to support the data requirements of the enterprise
- Minimal redundancy with each attribute represented only once with the important exception of attributes that form all or part of foreign keys.
- Attributes with a close logical relationship are found in the same relation.

#### Benefit of Normalization

- Remove prolems caused by data redundancy
- Easier for users to access and maintain data

### Functional Dependency

Functional Dependency (FD) is a constraint that determines the relation of one attribute to another attribute in a Database Management System (DBMS). Functional Dependency helps to maintain the quality of data in the database. It plays a vital role to find the difference between good and bad database design.

A functional dependency is denoted by an arrow “→”. The functional dependency of X on Y is represented by X → Y.

## Functional Dependencies and Normalization Forms

### Full, Partial, and Transitive Functional Dependencies

#### Full/Partial FDs

In one relation, if a set of attributes A: (a<sub>1</sub>, a<sub>2</sub>,..., a<sub>n</sub>) determines attribute B:

- A: (a<sub>1</sub>, a<sub>2</sub>,..., a<sub>n</sub>) &rarr; B
- If there is no proper subset of A also determines B, then A: (a<sub>1</sub>, a<sub>2</sub>,..., a<sub>n</sub>) &rarr; B is a Full functional dependency. It is full because we need all attributes in A to determine B.
- If there is a proper subset of A also determines B, then A: (a<sub>1</sub>, a<sub>2</sub>,..., a<sub>n</sub>) &rarr; B is a Partial functional dependency.
- To achieve Full FD, we need to minimize A by removing unnecessary attributes.

#### Transitive FDs

In one relation, if an attribute A determines attribute B, and B determines attribute C (C is not A):

- FD1: A &rarr; B
- FD2: B &rarr; C
- We can have A &rarr; C because the FD1 and FD2 form a Transitive Functional Dependency.

## Normalization Process to 3NF

### Normal Forms and Normalization Process

#### Normalization Process

Normalization Process is converting a relation from less restricted form to more restricted form.

#### First Normal Form (1NF)

- A relaion in which the intersection of each row and column contains **one and only one value**.
- This is the requirement of a relation: each cell of relation contains exactly one value.

#### Second Normal Form (2NF)

A relation is in 2NF if:

- It is in 1NF
- Every non-primary-key attribute is **fully functionally dependent** on the primary key.
- In other words, if there is any non-primary-key attribute is partially functionally dependent on the primary key, a relation not in 2NF.

> 1NF to 2NF
>
> - We need to eliminate the partial FDs.
> - Since in relation R, FD2 and FD3 lead to partial FDs, we need to move them out to new relations.
> - Determinants will be primary keys in new relations, and will bes foreign keys in original relations.

#### Third Normal Form (3NF)

A relation is in 2NF if:

- It is in 2NF
- **No non-primary-key attribute is transitively** dependent on the primary key
- In other words, if there is any non-primary-key attribute is transitively dependent on the primary key, a relation is not in 3 NF.

> 2NF to 3NF
>
> - We need to eliminate the transitive FDs.
> - Since in relation R, FD2 lead to transitive FDs, we need to move them out to new relations.
> - Determinants will be primary keys in new relations, and will bes foreign keys in original relations.

# Link

[Crow's Foot Notation – Relationship Symbols And How to Read Diagrams](https://www.freecodecamp.org/news/crows-foot-notation-relationship-symbols-and-how-to-read-diagrams/)
[Data Redundancy](https://www.techopedia.com/definition/18707/data-redundancy)
