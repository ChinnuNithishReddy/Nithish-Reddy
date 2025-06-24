CREATE TABLE Customers (
    CustomerID INT PRIMARY KEY,
    FirstName VARCHAR(50),
    LastName VARCHAR(50),
    Email VARCHAR(100) UNIQUE,
    PhoneNumber VARCHAR(15),
    City VARCHAR(50),
    State VARCHAR(50),
    ZipCode VARCHAR(10),
    CreatedAt TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
SQL> INSERT INTO Customers (
  2      CustomerID,FirstName, LastName, Email, PhoneNumber, City, State, ZipCode
  3  ) VALUES
  4  (6,'Kiran', 'Kumar', 'kiran.kumar@gmail.com', '5432109876', 'Bengaluru', 'Karnataka', '560001');
  CREATE TABLE Orders (
    OrderID INT PRIMARY KEY,
    CustomerID INT,
    OrderDate DATE,
    TotalAmount DECIMAL(10, 2),
    Status VARCHAR(50),
    FOREIGN KEY (CustomerID) REFERENCES Customers(CustomerID)
);
SQL> INSERT INTO Orders (OrderID, CustomerID, OrderDate, TotalAmount, Status)
  2  VALUES (105, 4, DATE '2025-06-21', 4099.99, 'Cancelled');
  
