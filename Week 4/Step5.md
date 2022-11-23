# Normalize the Relational Model to 3NF

fore normalization, you should ask Claire about the Functional Dependencies of the relations. Here is what you got from her:

- Customers (<u>CustomerID</u>, FirstName, LastName, Address, Email, Phone, DoB, PaymentInfo, JoinDate, ReferredByCustomerID(fk)).

  - FD1: CustomerID → FirstName, LastName, Address, Email, Phone, DoB, PaymentInfo, JoinDate, ReferredByCustomerID

- Pets (<u>CustomerID(fk), Pet#</u>, NickName, Address, Email, Phone, Category, Species/Breed, Species/Breed Description, Gender, DoB, Notes).

  - FD1: CustomerID, Pet# → NickName, Address, Email, Phone, Category, Species/Breed, Species/Breed Description, Gender, DoB, Notes.

  - FD2: CustomerID → Address, Email, Phone

  - FD3: Species/Breed → Species/Breed Description

- Staff (<u>EmployeeID</u>, FirstName, LastName, SSN, Address, Email, Phone, DoB, SupervisorID(fk)).

  - FD1: EmployeeID → FirstName, LastName, SSN, Address, Email, Phone, DoB, SupervisorID

- Visit (<u>VisitID</u>, Date, Time, CustomerID(fk), Pet(fk), ServiceID, ServiceName, ServicePrice, ServiceDescription, EmployeeID(fk), Bill, Paid).

  - FD1: VisitID → Date, Time, CustomerID, Pet, ServiceID, ServiceName, ServicePrice, ServiceDescription, EmployeeID, Bill, Paid

  - FD2: ServiceID → ServiceName, ServicePrice, ServiceDescription.

- Pets_Staff(<u>CustomerID(fk), Pet#(fk),EmployeeID(fk)</u>)
  - There is no non-primary-key attribute.

## Answers

- Customers, Staff, and Pets_Staff relations are in 3NF, because they are in 1NF; they have no partial functional dependencies so they are in 2NF; and they have no transitive functional dependencies so they are in 3NF.

- Pets relation is in 1NF. However, it is not in 2NF because FD2: CustomerID → Address, Email, Phone. CustomerID as part of the primary key, determines non-primary-key attributes. This leads to a partial functional dependency. We need to normalize Pets to 2NF:

  - Create a new relation to put CustomerID, Address, Email, Phone. Since Customer relation has these attributes, we can simply remove them from Pets, and keep CustomerID as a foreign key.

  - Pets (<u>CustomerID(fk), Pet#</u>, NickName, Category, Species/Breed, Species/Breed Description, Gender, DoB, Notes).

    - FD1: CustomerID, Pet# → NickName, Category, Species/Breed, Species/Breed Description, Gender, DoB, Notes.

    - FD2: Species/Breed → Species/Breed Description

- Pets relation now is in 2NF. However, it is not in 3NF because of FD2: Species/Breed → Species/Breed Description. (CustomerID, Pet#) →Species/Breed, and Species/Breed → Species/Breed Description is a transitive functional dependency. We need to normalize Pets to 3NF:

  - Create a new relation to put Species/Breed and Species/Breed Description and modify Pets:

  - Species (<u>Species/Breed</u>, Species/Breed Description)

    - FD1: Species/Breed → Species/Breed Description

  - Pets (<u>CustomerID(fk), Pet#</u>, NickName, Category, Species/Breed(fk), Gender, DoB, Notes).

    - FD1: CustomerID, Pet# → NickName, Category, Species/Breed, Gender, DoB, Notes.

- Now Pets relation is in 3NF.

- Visit relation is in 1NF, and 2NF. However, it is not in 3NF because of FD2: ServiceID → ServiceName, ServicePrice, ServiceDescription. VisitID → ServiceID, and ServiceID → ServiceName, ServicePrice, ServiceDescription is a transitive functional dependency. We need to normalize Visit to 3NF:

  - Create a new relation to put ServiceID, ServiceName, ServicePrice, ServiceDescription and modify visit.

  - Service (<u>ServiceID</u>, ServiceName, ServicePrice, ServiceDescription)

    - FD1: ServiceID → ServiceName, ServicePrice, ServiceDescription

  - Visit (<u>VisitID</u>, Date, Time, CustomerID(fk), Pet(fk), ServiceID(fk), EmployeeID(fk), Bill, Paid).

    - FD1: VisitID → Date, Time, CustomerID, Pet, ServiceID, EmployeeID, Bill, Paid
