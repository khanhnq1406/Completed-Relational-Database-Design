# Entity Relationship Models

In this assignment, you will be asked to create ERDs or interpret ERDs.

For creating ERDs, make sure you are using Crow’s foot notation for ERDs, and including key components: Entities, Attributes (if provided), Identifiers (if provided), Relationships (with correct cardinality and participation multiplicities).

For interpreting ERDs, make sure you are including Entities, the explicit terms for cardinality and participation for the relationships, such as must, may, can, one and only one, one or more, many, etc.

## Question 1: Create an ERD

Read the following statements and draw the Entity Relationship Diagram using Crow’s Foot Notation.

### **Answer**

<img src="./images/Assignments-Question_1_%20Create_an_ERD.png">

# Question 2: Interpret an ERD

Read and understand the ERD below, and answer the questions:
<img src = "https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/GY2E_YeGQUyNhP2HhrFMiw_5025eab6ec7c47cab30ad018d52a42f1_Screen-Shot-2022-02-21-at-10.45.40-AM.png?expiry=1667692800000&hmac=_GwMGsigpURDvHWA2pW0SPJZhOttrhRIjwjAHTHRX9g">
A: What are the entities in the ERD?

B: Translate this ERD to a list of statements. Make sure you address the cardinality and participation using correct terms may, must, one and only one, one or more, etc.

### **Anwers**

A: The entities in the ERD are Drivers, Supervisors, Dependents, DetailProfile, Division, Cars

B: Translate this ERD to a list of statements

- A driver may have one or more dependents, a dependent must belong to one and only one driver.
- A driver must have one and only one detail profile, a detail profile may belong to one and only one driver.
- A driver must belong to one and only one division, each division may have one or more drivers.
- A driver may operate one or more cars, a car may be operated by one or more drivers.
- A supervisor must supervise one or more drivers, a driver must be supervised by one and only one supervisor.

# Question 3: Create an ERD

Read the following statements about a Database for Art Galleries and collections of drawings. Draw the Entity-Relationship Attribute Diagram with Crow’s Foot Notation. No credit will be granted for other notations. Make sure you have all entities, all attributes (and identifiers), all relationships, and proper multiplicities.

## **Answer**

<img src="https://drive.google.com/uc?id=1-F0naJk3kQWX8SIxteZzyuNwl7pmWMbj">
