# Final Output for Implementation

- Customers (<u>CustomerID</u>, FirstName, LastName, Address, Email, Phone, DoB, PaymentInfo, JoinDate, ReferredByCustomerID(fk)).

  - FD1: CustomerID → FirstName, LastName, Address, Email, Phone, DoB, PaymentInfo, JoinDate, ReferredByCustomerID

- Pets (<u>CustomerID(fk), Pet#</u>, NickName, Category, Species/Breed(fk), Gender, DoB, Notes).

  - FD1: CustomerID, Pet# → NickName, Category, Species/Breed, Gender, DoB, Notes.

- Species (<u>Species/Breed</u>, Species/Breed Description)

  - FD1: Species/Breed → Species/Breed Description

- Staff (<u>EmployeeID</u>, FirstName, LastName, SSN, Address, Email, Phone, DoB, SupervisorID(fk)).

  - FD1: EmployeeID → FirstName, LastName, SSN, Address, Email, Phone, DoB, SupervisorID

- Visit (<u>VisitID</u>, Date, Time, CustomerID(fk), Pet(fk), ServiceID(fk), EmployeeID(fk), Bill, Paid).

  - FD1: VisitID → Date, Time, CustomerID, Pet, ServiceID, EmployeeID, Bill, Paid

- Service (<u>ServiceID</u>, ServiceName, ServicePrice, ServiceDescription)

  - FD1: ServiceID → ServiceName, ServicePrice, ServiceDescription

- Pets_Staff(<u>CustomerID(fk), Pet#(fk),EmployeeID(fk)</u>)
  - There is no non-primary-key attribute.
