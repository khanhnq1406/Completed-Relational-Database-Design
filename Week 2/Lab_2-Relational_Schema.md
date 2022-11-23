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

**Relational Schema to represent the relation:**

GradeBook(<u>ID</u>, Name, Major(fk), Quiz1, Quiz2, Quiz3, Quiz4)

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

**Relational Schema to represent the relation:**

ProductDetails(<u>SKU, VendorID(fk), Date</u>, Name, Price, Quantity, Location, Description)
