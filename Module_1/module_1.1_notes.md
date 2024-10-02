Here is the content formatted as plain text:

```
# Joining Tables

## Aliases
Aliases are used to give a table, or a column in a table, a temporary name. An alias only exists for the duration of that query. Also, an alias is created with the `AS` keyword.

### Example Query:
```sql
SELECT CustomerID AS ID
FROM Customers;
```

This translates to: "Select `CustomerID` (column) `AS` (keyword) `ID` (new name) from `Customers` (table)."

---

## Joining Tables
There are 4 types of joins in SQL. A `JOIN` in a database links records of data between one or multiple tables based on a common column between them.

### 1. INNER JOIN
The `INNER JOIN` returns records of data that have matching values in the joined tables.

#### Example Query:
For example, assume that you want to return the full name and booking ID of customers who made bookings. You can use the `INNER JOIN` clause to extract records of data from the `Customers` and `Bookings` tables based on the matching customer ID.

```sql
SELECT Customers.FullName, Bookings.BookingID 
FROM Customers 
INNER JOIN Bookings ON Customers.CustomerID = Bookings.CustomerID; 
```

---

### 2. LEFT JOIN
You can use the `LEFT JOIN` clause to extract the full names and the booking IDs from the `Customers` and `Bookings` tables. It will return all queried records from the left table, and the matching records from the right table. If there are no matching records in the right table, the value is shown as `NULL`.

#### Example Query:
```sql
SELECT Customers.FullName, Bookings.BookingID 
FROM Customers 
LEFT JOIN Bookings ON Customers.CustomerID = Bookings.CustomerID; 
```

---

### 3. RIGHT JOIN
The `RIGHT JOIN` is similar to the `LEFT JOIN`, but it will return all queried records from the right table and the matching records from the left table. If there are no matching values in the left table, `NULL` is assigned.

#### Example Query:
```sql
SELECT Customers.FullName, Bookings.BookingID 
FROM Customers 
RIGHT JOIN Bookings ON Customers.CustomerID = Bookings.CustomerID;
```

---

### 4. SELF JOIN
A special case where you join the same table with itself to get specific information existing in the same table.

---

## UNION Operator
The `UNION` operator creates a union between two `SELECT` statements. Every `SELECT` statement must have the same number of columns. All related columns should have similar data types, and the same order must be maintained in every `SELECT` statement.

To get all data, including duplicate records, use `UNION ALL`.

### Example Query:
```sql
SELECT FullName, Location FROM CurrentClients
UNION
SELECT FullName, Location FROM LegacyClients;
```
```

You can copy and paste this plain text version into your editor of choice!