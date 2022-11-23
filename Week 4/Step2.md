# Build the Entity Relationship Model

Congratulations! Thanks to the efficient communication between Claire and you, now you understand the details of the business, and you are ready to write down narrative statements for your Entity Relationship Model.

You should lay out your own assumptions and your own ER Model.

## Answer

### Entities

The entities in the ER Model: Customers, Pets, Staffs, Visits

Customers: CustomerID, FirstName, LastName, Address, Email, Phone, DoB, PaymentInfo, JoinDate. CustomerID is the identifier.

Pets: CustomerID, Pet#, NickName, Address, Email, Phone, Category, Species/Breed, Species/Breed Description, Gender, DoB, Notes. CustomerID and Pet# together as the identifier.

Staff: EmployeeID, FirstName, LastName, SSN, Address, Email, Phone, DoB. EmployeeID is the identifier.

Visit: VisitID, Date, Time, Customer, Pet, ServiceID, ServiceName, ServicePrice, ServiceDescription, Staff, Bill, Paid. VisitID is the identifier.

### Relationships:

A customer may have one or more (zero or more) pets; A pet must belong to one and only one (exactly one) customer.

A staff may treat one or more pets (zero or more); and A pet may be familiar with one or more (zero or more) staff.

A customer may have one or more (zero or more) visits; and each visit must be done by one and only one (exactly one) customer.

A pet may have one or more (zero or more) visits; and each visit may involve one (zero or one) pet.

A staff must be in charge of one or more (one or more) visits; and a visit must be charged by one and only one (exactly one) staff.

A customer may be referred by one (zero or one) customer; and a customer may refer one or more (one or more) customers.

A staff must have one and only one (exactly one) supervisor; A staff may supervise one or more (zero or more) staff.
