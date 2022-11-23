# Convert the ERD to the Relational Model

Customers (<u>CustomerID</u>, FirstName, LastName, Address, Email, Phone, DoB, PaymentInfo, JoinDate, ReferredByCustomerID(fk)).

Pets (<u>CustomerID(fk), Pet#</u>, NickName, Address, Email, Phone, Category, Species/Breed, Species/Breed Description, Gender, DoB, Notes).

Staff (<u>EmployeeID</u>, FirstName, LastName, SSN, Address, Email, Phone, DoB, SupervisorID(fk)).

Visit (<u>VisitID</u>, Date, Time, CustomerID(fk), Pet(fk), ServiceID, ServiceName, ServicePrice, ServiceDescription, EmployeeID(fk), Bill, Paid).

Pets_Staff(<u>CustomerID(fk), Pet#(fk),EmployeeID(fk)</u>)
