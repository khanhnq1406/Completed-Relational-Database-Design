# Relation 1

| ID  | Name     | Major      | Quiz1 | Quiz2 | Quiz3 | Quiz4 | Total | Grade |
| --- | -------- | ---------- | ----- | ----- | ----- | ----- | ----- | ----- |
| 001 | Harry    | Magic      | 90    | 90    | 80    | 100   | 360   | A-    |
| 002 | Hermione | Magic      | 100   | 100   | 100   | 100   | 400   | A     |
| 007 | Ron      | Magic      | 80    | 100   | 70    | 100   | 350   | B+    |
| 301 | Dobby    | Service    | 95    | 95    | 95    | 95    | 380   | A     |
| 302 | Severus  | Education  | 90    | 90    | 99    | 100   | 379   | A     |
| 399 | Albus    | Management | 100   | 100   | 99    | 100   | 399   | A     |

## All possible functional dependencies:

- ID &rarr; Name, Major, Quiz1, Quiz2, Quiz3, Quiz4, Total, Grade
- Quiz1 + Quiz2 + Quiz3 + Quiz4 &rarr; Total, ~~Grade~~
- Total &rarr; Grade

# Relation 2

| SKU   | Name     | VendorID | Price | Date       | Quantity | Location | Description  |
| ----- | -------- | -------- | ----- | ---------- | -------- | -------- | ------------ |
| KB320 | MouseMat | V1230    | 13.32 | 01/01/2019 | 3000     | A3       | Discontinued |
| YZ783 | MouseMat | V3002    | 10.00 | 03/01/2019 | 1000     | A3       | Discontinued |
| IU990 | Mouse    | V3333    | 19.00 | 12/01/2019 | 700      | A1       |              |
| IU370 | Mouse    | V3333    | 15.00 | 01/01/2020 | 500      | A1       |              |
| YZ783 | MouseMat | V3012    | 9.90  | 05/01/2020 | 1000     | A3       |              |
| YZ783 | MouseMat | V3012    | 8.90  | 05/01/2021 | 1000     | A3       |              |

## All possible functional dependencies:

- SKU &rarr; Name
- SKU, VendorID, Date &rarr; Price, Quantity, Location, Description
