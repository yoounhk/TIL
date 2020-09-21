# Create_Table_In_MySQL

## Example Source Code

```mysql
CREATE TABLE topic(
    id INT(11) NOT NULL AUTO_INCREMENT,
    title VARCHAR(100) NOT NULL,
    description TEXT NOT NULL,
    date DATETIME NOT NULL,
    author VARCHAR(30) NULL,
    profile VARCHAR(100) NULL,
    PRIMARY KEY(id)
    );
```

---

## Data Types
### String Datatypes

| Data Type Syntax   | Maximum Size                                     | Explanation                                                  |
| :----------------- | :----------------------------------------------- | :----------------------------------------------------------- |
| VARCHAR(*size*)    | Maximum size of 255 characters.                  | Where ***size\*** is the number of characters to store. Variable-length string. |
| TEXT(*size*)       | Maximum size of 65,535 characters.               | Where ***size*** is the number of characters to store.       |

### Numeric Datatypes

| Data Type Syntax | Maximum Size                                                 | Explanation     |
| :--------------- | :----------------------------------------------------------- | :-------------- |
| INT(*m*)         | Standard integer value. Signed values range from -2147483648 to 2147483647. Unsigned values range from 0 to 4294967295. | m: total digits |

### Date/Time Datatypes

| Data Type Syntax | Maximum Size                                                 | Explanation                         |
| :--------------- | :----------------------------------------------------------- | :---------------------------------- |
| DATETIME         | Values range from '1000-01-01 00:00:00' to '9999-12-31 23:59:59'. | Displayed as 'YYYY-MM-DD HH:MM:SS'. |

---

## Create Table

| Command                                                      | Description         |
| :----------------------------------------------------------- | :------------------ |
| CREATE TABLE TableName (fieldname dataType [optional parameters]) | Create table syntax |

---
## Keyword

* The `NOT NULL` constraint is a column constraint that ensures values stored in a column are not NULL.

* The `AUTO_INCREMENT`  attribute is a function that operates on numeric data types. It automatically generates sequential numeric values every time that a record is inserted into a table for a field defined as auto increment.

* A `PRIMARY KEY` is a single field or combination of fields that uniquely defines a record. None of the fields that are part of the primary key can contain a NULL value. A table can have only one primary key.

---

## **References**
* [Source Code](https://opentutorials.org/course/3161/19537)
* [Datatype](https://www.techonthenet.com/mysql/datatypes.php)
* [Create Table](https://www.guru99.com/sql-cheat-sheet.html)
* [`NOT NULL` Constraint](https://www.guru99.com/null.html)
* [`AUTO_INCREMENT`](https://www.guru99.com/auto-increment.html)
* [`PRIMARY KEY`](https://www.techonthenet.com/mysql/primary_keys.php)

