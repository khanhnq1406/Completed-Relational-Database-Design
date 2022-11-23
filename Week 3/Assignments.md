# Question 1: Normal Forms

## Question

1A: What normal form is the following relation in (key is underlined), and Why? Make sure you provide both Answer and Reasoning:

STORE_ITEM (SKU, EventID, Vendor, Style, Price, Warranty)

FD1: SKU, EventID → Vendor, Style, Price

FD2: SKU → Vendor, Style, Warranty

FD3: Vendor → Warranty

1B: What normal form is the following relation in (key is underlined), and Why? Make sure you provide both Answer and Reasoning:

SKU (SKU, Vendor, Style, Warranty)

FD1: SKU → Vendor, Style, Warranty

FD2: Vendor → Warranty

1C: What normal form is the following relation in (key is underlined), and Why? Make sure you provide both Answer and Reasoning:

SKU (SKU, Vendor, Style, Warranty)

FD1: SKU → Vendor, Style, Warranty

FD2: Vendor, Style → Warranty

## Answers

### 1A

It is in 1NF, since it is a relation.

It is not in 2NF, since there are partial FDs: SKU is part of (SKU, EventID) -> Vendor, Style, Price

### 1B

It is in 1NF, since it is a relation.

It is in 2NF too, since there is no partial FD.

It is not in 3NF, since there is a transitive FD: SKU → Vendor, Style, Warranty, and Vendor → Warranty.

### 1C

It is in 1NF, since it is a relation.

It is in 2NF too, since there is no partial FD.

It is not in 3NF, since there is a transitive FD: SKU → Vendor, Style, Warranty and Vendor, Style → Warranty

# Question 2: Normalization Process

## Question

We have a relational model represented as a relational schema and its functional dependencies given as below:

    TRANSCRIPT (ID, fName, lName, major, majorDescription, courseID, courseDescription, courseGrade)

    FD1: ID, courseID -> fName, lName, major, majorDescription, courseDescription, courseGrade

    FD2: ID -> fName, lName, major, majorDescription

    FD3: courseID - > curseDescription

    FD4: major -> majorDescription

2A: Normalize it to 2NF

2B: Check all the relations you got from 2A. Are they in 3NF? If not, normalize them to 3NF.

## Answers

### 2A

> TRANSCRIPT (<u>ID(fk)</u>, <u>courseID(fk)</u>, courseDescription, courseGrade) <br>
> FD1: ID, courseID -> courseDescription, courseGrade

> ID (<u>ID</u>fName, lName, major, majorDescription)<br>
> FD1: ID -> fName, lName, major, majorDescription
> FD2: major -> majorDescription

> CourseID(<u>courseID</u>, curseDescription) <br>
> FD3: courseID - > curseDescription

### 2B

All is in 2NF, since there is no partial FD.

ID is not in 3NF, since there is a transitive FD: ID -> fName, lName, major, majorDescription and major -> majorDescription

> ID (<u>ID</u>fName, lName, major(fk))<br>
> FD1: ID -> fName, lName, major

> Major(<u>major</u>, majorDescription)<br>
> FD1: major -> majorDescription

# Question 3: Normalization Process

## Question

You are given the following Relational Model represented as a relational schema and its functional dependencies.

    Exam1(A, B, C, D, E, F, G, H, I)

    fd1: A, B, C -> D, E, F, G, H, I

    fd2: B -> E

    fd3: C -> F, G, H, I

    fd4: F, G -> H, I

3A: Normalize it to 2NF

3B: Check all the relations you got from 3A. Are they in 3NF? If not, normalize them to 3NF.

## Answers

### 3A

> Exam1(<u>A, B(fk), C(fk)</u>, D)<br>
> fd1: A, B, C -> D<br>

> Relation1(<u>B</u>, E) <br>
> fd1: B -> E

> Relation2(<u>C</u>, F, G, H, I) <br>
> fd1: C -> F, G, H, I
> fd2: F, G → H, I

### 3B

> Relation2(<u>C</u>, F(fk), G(fk))<br>
> Fd1: C → F, G

> Relation3(<u>F, G,</u> H, I)<br>
> Fd1: F, G → H, I
