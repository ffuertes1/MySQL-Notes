+++markdown
# Filtering Data with Operators (AND, OR, NOT, IN, BETWEEN, LIKE)

## AND Operator
The `AND` operator displays a record if **all** the conditions are `TRUE`.

### Example Query:
```sql
SELECT * FROM Customers
WHERE Country = 'Germany'
  AND City = 'Berlin'
  AND PostalCode > 12000;
```

This translates as: 
"Select all records from the `Customers` table where `Country` is `'Germany'`, `City` is `'Berlin'`, and `PostalCode` is greater than `12000`. To retrieve the data, all conditions after the `WHERE` clause must be true."



## OR Operator
The `OR` operator displays a record if **any** of the conditions are `TRUE`.

### Example Query:
```sql
SELECT * FROM Customers
WHERE Country = 'Spain' 
  OR CustomerName = 'Maria';
```

In this query, we are saying: 
"Select all records from the `Customers` table where either `Country` is `'Spain'` or `CustomerName` is `'Maria'`. If one of the conditions is true, the data will be retrieved."



## NOT Operator
The `NOT` operator is used in combination with other operators to give the **opposite** result, also called the negative result.

### Example Query:
```sql
SELECT * FROM Customers
WHERE NOT Country = 'Spain';
```

This translates to:
"Select all records from the `Customers` table where `Country` is **not** `'Spain'`. This will return all data except for the rows where `Country` is `'Spain'`."

---
---
---

## IN Operator
The `IN` operator is a shorthand for multiple `OR` conditions.

### Example Query:
```sql
SELECT * FROM Buyers
WHERE Country IN ('Germany', 'France', 'UK');
```

This translates to:
"Select all records from the `Buyers` table where `Country` is either `'Germany'`, `'France'`, or `'UK'`. The query will retrieve data for any of these countries."



## BETWEEN Operator
The `BETWEEN` condition is used to retrieve values within a specific range in a `SELECT`, `INSERT`, `UPDATE`, or `DELETE` statement.

### Example Query:
```sql
SELECT *
FROM contacts
WHERE contact_id BETWEEN 100 AND 200;
```

This translates to:
"Select all records from the `contacts` table where `contact_id` is between `100` and `200`. The range includes both `100` and `200`. The `BETWEEN` operator is equivalent to using `>=` and `<=`."



## LIKE Operator
The `LIKE` operator allows for pattern matching and is used in a `WHERE` clause to search for a specified pattern in a column.

### Example Query:
```sql
SELECT * FROM Customers
WHERE CustomerName LIKE 'a%';
```

This translates to:
"Select all records from the `Customers` table where `CustomerName` starts with an `A`. The `%` is used as a wildcard that matches zero, one, or more characters. For example, using `LIKE '%a'` would match all names ending with an `A`."

### Wildcards:
- **Percent sign (%)**: Represents zero, one, or multiple characters.
- **Underscore (_)**: Represents one single character.

### Example:
- `se_` matches any string starting with `se` followed by exactly one character, such as "see" or "sea".
---