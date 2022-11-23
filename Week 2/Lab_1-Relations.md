# Relation 1

**GradeBook**

| **ID** | **Name** | **Major**  | **Quiz1** | **Quiz2** | **Quiz3** | **Quiz4** |
| ------ | -------- | ---------- | --------- | --------- | --------- | --------- |
| 001    | Harry    | Magic      | 90        | 90        | 80        | 100       |
| 002    | Hermione | Magic      | 100       | 100       | 100       | 100       |
| 007    | Ron      | Magic      | 80        | 100       | 70        | 100       |
| 301    | Dobby    | Service    | 95        | 95        | 95        | 95        |
| 302    | Severus  | Education  | 90        | 90        | 99        | 100       |
| 399    | Albus    | Management | 100       | 100       | 99        | 100       |

The name of the relation: GradeBook

The attributes of the relation: ID, Name, Major, Quiz1, Quiz2, Quiz3, Quiz4

What are the tuples of the relation (pick one): | 001 | Harry | Magic | 90 | 90 | 80 | 100 |

Degree of the relation: 7

Cardinality of the relation: 6

The possible domain of attribute ID: 3 digits

The possible domain of attribute Name: length of Char is 10

The possible domain of attribute Major: a list of all majors [Magic, Service, Education, Management]

The possible domain of attribute Quiz1 - 4: 0 <= Number <= 100

**Choose some super keys for this relation:**

_If there is no duplicate name of people:_

Candidate keys may be: ID, Name

Primary key: ID

Alternate key: Name

_If there is no duplicate name of people in the same major, what might be candidate keys?_

Candidate keys may be: ID, Name, Major

The primary key: ID

The alternate key: Name, Major

_If there are duplicate names of people in the system, what might be candidate keys?_

Candidate keys: ID

Primary key: ID

Alternate key: None

# Relation 2

**ProductDetails**

| **SKU** | **Name** | **VendorID** | **Price** | **Date**   | **Quantity** | **Location** | **Description** |
| ------- | -------- | ------------ | --------- | ---------- | ------------ | ------------ | --------------- |
| KB320   | MouseMat | V1230        | 13.32     | 01/01/2019 | 3000         | A3           | Discontinued    |
| YZ783   | MouseMat | V3002        | 10.00     | 03/01/2019 | 1000         | A3           | Discontinued    |
| IU990   | Mouse    | V3333        | 19.00     | 12/01/2019 | 700          | A1           |                 |
| IU370   | Mouse    | V3333        | 15.00     | 01/01/2020 | 500          | A1           |                 |
| YZ783   | MouseMat | V3012        | 9.90      | 05/01/2020 | 1000         | A3           |                 |
| YZ783   | MouseMat | V3012        | 8.90      | 05/01/2021 | 1000         | A3           |                 |

The name of the relation: ProductDetails

The attributes of the relation: SKU, Name, VendorID, Price, Date, Quantity, Location, Description

The tuples of the relation (pick one): | KB320 | MouseMat | V1230 | 13.32 | 01/01/2019 | 3000 | A3 | Discontinued |

The degree of the relation: 8

The cardinality of the relation: 6

The possible domain of attribute SKU: 2 chars + 3 digits

The possible domain of attribute Name: chars

The possible domain of attribute VendorID: 1 char + 4 digits

The possible domain of attribute Price: float number

The possible domain of attribute Date: DD/MM/YYYY (Date)

The possible domain of attribute Quantity: Possitive integers

The possible domain of attribute Location: 1 char + 1 digit

The possible domain of attribute Description: chars

_Choose some super keys for this relation:_ SKU+Name+VendorID+Price+Date+Quantity+Location+Description; SKU+Name+VendorID+Date <sup>From solution</sup>

Candidate keys: SKU+VendorID+Price, SKU+VendorID+Date

The primary key: SKU+VendorID+Date

The alternate key: SKU+VendorID+Price
