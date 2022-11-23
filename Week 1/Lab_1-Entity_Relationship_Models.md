# Case 1: PizzaHot

## Entities

Stores, Employees, Vendors, Products

## Attributes/Identifiers

- Stores: \*StoreID, StoreName, Location, ContactInformation.
- Employees: \*EmployeeID, SSN, EmployeeName, Gender, DoB, Position, Salary, AffiliateStore.
- Vendors: \*VendorName, Address, ContactPerson
- Products: \*ProductName, Vendor, price, quantity

## Relationships

- A store may have one or more employees, an employees must belong to exactly one store.
- A vendor may supply one or more products, a product must be supplied by one vendor.
- A store may have multiply products, a products may be in multiple store.
- <sup>**From solution**</sup> An employee must be supervised by another employee, and an employee may supervise many other employees.

# TrueTrade

## Entities

Stocks, Customers, Portfolio, Logs, Transactions

## Attributes/Identifiers

- Stocks: \*stock#, companyName, ExchangeMarket, Description
- Customers: \*CustomerID, Name, Contact
- Portfolio: CustomerName, currentValue
- Logs: \*stock#, \*date, openPrice, closePrice
- Transactions: \*TransactionID <sup>From solutions</sup>, CustomerID, Portfolio, stock, quantity, price, date, time.

## Relationships

- One customer may have multiply tranctions, a transactions must belong one customer.
- A stock can have many logs, a log must belong to one and only one stocks.
- A customer can have many portfolio, a portfolio only belong to a customer.
- <sup>**From solution**</sup>A​ portfolio may have one or more stocks, and a stock may belong to one or more portfolios.
- <sup>**From solution**</sup>A​ portfolio may be in one or more transactions, and each transaction must include one and only one portfolio
- <sup>**From solution**</sup>A​ transaction must have a stock, and a stock may be in one or more transactions.

# MiniLibrary

## Entities

Books, BookCases, Users, Log

## Attributes/Identifiers

- Books: \*ISBN#, COPY#, Title, Author1, Author2, Year, Publisher.
- BookCases: \*Case#, Street, County
- Users: \*UserID, Name, Address, Contact
- Log: \*BookInfo, UserInfo, BookCaseInfo, TimeStamp, Borrow/Return

## Relationship

- A user can borrow/return multiple book, a books can be borrowed/returned by one user in a time.
- A bookcase can have many books, a book may be on one or more bookcase.
- A log can log one or more book, each book can be logged by more log.
