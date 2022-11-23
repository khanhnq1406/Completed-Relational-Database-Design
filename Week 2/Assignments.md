# Question 1: Understand A Relation

<img src="https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/NDZyTieNQlO2ck4njdJTyA_319318fcc43f4b66bce097e4030789f1_Screen-Shot-2022-02-21-at-10.35.43-AM.png?expiry=1667952000000&hmac=l-39rv3OqwoE0Fl-s7CyS69v7cAc_pcPyFJDKPeG6h4">

What is the name of this relation: MotorVehicleCollisions

What is the degree of this relation: 11

What is the cardinality of this relation: 9

What might be the primary key of this relation: Collision_ID

What is the domain of ZIP CODE: 5 digits

What is the domain of CRASH DATE: Date

# Question 2: Interpret an ERD

<img src="https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/RJIqFmwgTReSKhZsIA0X6w_da139a45ad3c4b2ea4a5f19c65566df1_Screen-Shot-2022-02-21-at-10.36.57-AM.png?expiry=1667952000000&hmac=NopOXUtyHrTxeKwDUqcIkdD75eDzTdZuwO_u1dN9Bc8">

Drivers(Name, <u>EmployeeID</u>, SSN, DoB, Phone, MentorID(fk), DivisionName(fk))

Drivers_Drivers(<u>EmployeeID(fk)</u>, <u>FriendsEmployeeID(fk)</u>)

Dependents(<u>DependentsID</u>, Name, Gender, DoB, EmployeeID(fk))

Division(<u>DivisionName</u>, Location, Phone, Email)

Cars(<u>CarID</u>, Manufactor, Model, Year)

Cars_Drivers(<u>CarID(fk)</u>, <u>EmployeeID(fk)</u>)
