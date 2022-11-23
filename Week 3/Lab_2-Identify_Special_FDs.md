# Relation 1

## Question

Is there a partial functional dependency? Is there a transitive functional dependency?

Assignments(A, B, C, D, E, F, G, H, I, J, K, L, N, Q)

    fd1: A, B, C -> D, E, F, G, H, I, J, K, L, N, Q

## Answers

- There is no partial functional dependency
- There is no transitive functional dependency

# Relation 2

## Question

Is there a partial functional dependency? Is there a transitive functional dependency?

Assignments(A, B, C, D, E, F, G, H, I, J, K, L, N, Q)

    fd1: A, B, C -> D, E, F, G, H, I, J, K, L, N, Q

    fd2: D -> L, N, Q

    fd3: L -> N

## Answers

- There is no partial functional dependency.
- There is a transitive functional dependency:
  - A, B, C → D, and D → L
  - D → L and L → N

# Relation 3

## Question

Is there a partial functional dependency? Is there a transitive functional dependency?

Assignments(A, B, C, D, E, F, G, H, I, J, K, L, N, Q)

    fd1: A, B, C -> D, E, F, G, H, I, J, K, L, N, Q

    fd2: A -> D, E, F, L, N, Q

    fd3: B, C -> G, H

    fd4: D -> L, N, Q

    fd5: L -> N

## Answers

There are partial functional dependencys: A is part of (A B C) -> D E F L N G; also B C is part of (ABC) -> GH

There are transitive functional dependencys:

- A, B, C → D and D → L, N, Q
- D → L and L → N
- A → D and D → L

# Relation 4

## Question

Is there a partial functional dependency? Is there a transitive functional dependency?

CustomerContact (FirstName, LastName, DoB, Email, Zodiac, Street, County, City, State, Zip, Company, CompanyInfo)

    fd1: FirstName, LastName, DoB -> Email, Zodiac, Street, County, City, State, Zip, Company, CompanyInfo

    fd2: LastName, DoB → Email

    fd3: DoB → Zodiac

    fd4: Zip → City, State

    fd5: Company → CompanyInfo

## Answers

- There are partial functional dependencys: DoB is part of (Firstname, LastName, DoB) → Zodiac; Also, (LastName, DoB) is part of (Firstname, LastName, DoB) → Email
- There are transitive FDs: FirstName, LastName, DoB → Zip, and Zip → City, State. Also, FirstName, LastName, DoB → Company, and Company → CompanyInfo
