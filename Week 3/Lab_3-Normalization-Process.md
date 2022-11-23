# Identify Normalization Form

## Relation 1

### Question

Which normal form is the relational model below?

    Assignments(A, B, C, D, E, F, G, H, I, J, K, L, N, Q)

    fd1: A, B, C -> D, E, F, G, H, I, J, K, L, N, Q

### Answer: 3NF

## Relation 2

### Question

Which normal form is the relational model below?

    Assignments(A, B, C, D, E, F, G, H, I, J, K, L, N, Q)

    fd1: A, B, C -> D, E, F, G, H, I, J, K, L, N, Q

    fd2: D -> L, N, Q

    fd3: L -> N

### Answer: 2NF

## Relation 3

### Question

Which normal form is the relational model below?

    Assignments(A, B, C, D, E, F, G, H, I, J, K, L, N, Q)

    fd1: A, B, C -> D, E, F, G, H, I, J, K, L, N, Q

    fd2: A -> D, E, F, L, N, Q

    fd3: B, C -> G, H

    fd4: D -> L, N, Q

    fd5: L -> N

### Answer: 1NF

## Relation 4

### Question

Which normal form is the relational model below?

    CustomerContact (FirstName, LastName, DoB, Email, Zodiac, Street, County, City, State, Zip, Company, CompanyInfo)

    fd1: FirstName, LastName, DoB -> Email, Zodiac, Street, County, City, State, Zip, Company, CompanyInfo

    fd2: LastName, DoB → Email

    fd3: DoB → Zodiac

    fd4: Zip → City, State

    fd5: Company → CompanyInfo

### Answer: 1NF

# Normalization Process

## Relational Model 1

### Question

Given the relational model below, normalize it to 3NF. Make sure you list the Functional Dependencies along with each relation, and include all relations (each relation with its functional dependencies) in the summary.

    Customers (CID, FirstName, LastName, Email, Address, Company, CompanyInfo)

    FD1: CID → FirstName, LastName, Email, Address, Company, CompanyInfo

    FD2: Company → CompanyInfo

### Answer

This relation is NF2. Because every non-primary-key attribute is fully functionally dependent on the primary key.

Normalize it to 3NF:

> Customers (<u>CID(fk)</u>, FirstName, LastName, Email, Address, Company(fk)) <br>
> FD1: CID → FirstName, LastName, Email, Address, Company

> Companies(<u>Company</u>, CompanyInfo) <br>
> FD1: Company → CompanyInfo

## Relational Model 2

### Question

Given the relational model below, normalize it to 3NF. Make sure you list the Functional Dependencies along with each relation, and include all relations (each relation with its functional dependencies) in the summary.

    CustomerContact (FirstName, LastName, DoB, Email, Zodiac, Street, County, City, State, Zip, Company, CompanyInfo)

    fd1: FirstName, LastName, DoB → Email, Zodiac, Street, County, City, State, Zip, Company, CompanyInfo

    fd2: LastName, DoB → Email

    fd3: DoB → Zodiac

    fd4: Zip → City, State

    fd5: Company → CompanyInfo

### Answer

This relation is NF1.

Normalize it to 3NF:

> CustomerContact (<u>FirstName(fk), LastName(fk), DoB(fk),</u> Street, County, Zip(fk), Company(fk)) <br>
> fd1: FirstName, LastName, DoB → Street, County, Zip, Company

> Email (<u>LastName, DoB,</u> Email) <br>
> fd1: LastName, DoB → Email

> Zodiac (<u>DoB</u>, Zodiac) <br>
> fd1: DoB → Zodiac

> Zip (<u>Zip</u>, City, State)<br>
> fd1: Zip → City, State

> Companies(<u>Company</u>, CompanyInfo) <br>
> fd1: Company → CompanyInfo

## Relational Model 3

### Question

Given the relational model below, normalize it to 3NF. Make sure you list the Functional Dependencies along with each relation, and include all relations (each relation with its functional dependencies) in the summary.

    Assignments(A, B, C, D, E, F, G, H, I, J, K, L, N, Q)

    fd1: A, B, C → D, E, F, G, H, I, J, K, L, N, Q

    fd2: A → D, E, F, L, N, Q

    fd3: B, C → G, H

    fd4: D → L, N, Q

    fd5: L → N

    fd6: G → H

### Answer

> Assignments(<u>A(fk), B(fk), C(fk),</u> I, J, K) <br>
> fd1: A, B, C → I, J, K

> Relation1(<u>A</u>, D(fk), E, F)<br>
> fd1: A → D, E, F

> Relation2(<u>B, C</u>, G(fk))<br>
> fd1: B, C → G

> Relation3(<u>D</u>, L(fk), Q)<br>
> fd1: D → L, Q

> Relation4(<u>L</u>, N)<br>
> fd1: L → N

> Relation5(<u>G</u>, H)<br>
> fd1: G → H
