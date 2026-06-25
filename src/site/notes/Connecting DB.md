---
{"dg-publish":true,"permalink":"/connecting-db/","dg-note-properties":{}}
---

## SQLite
- It is a lightweight DB
- It stores the entire Database in a single file
- Used in Local Storage and used By Android
## Running with DB
- When running with a Connection
- It requires a `classpath`
- It is provided using options : -cp, -`classpath`
- It is provided in the following format: `java -cp ".;path" ClassName`
## Executing Statements
- `execute` : returns int for number of rows affected
- `executeQuery`: Returns a `ResultSet`, used for Select Queries
- `get[Types]()`: All data will be received in string or as raw bytes, hence java needs to convert into the asked type, hence different functions are provided that parse to that type and return.
- `executeUpdate`: Runs DML queries like Insert, Delete, Update in **`PreparedStatement`**
- `preparedStatementObject.getGeneratedKeys()`: Each Connection with a DBMS maintains the last Id inserted, this is because, in a multi threaded environment, multiple rows might be inserted at once,
	1. **It will return a `ResultSet `of all the keys generated in a row, these columns with the keys don not have a name and can be only accessed using the Column Number **
	2. If we want to access these keys we need to specify it during the creation by passing `PreapredStatement.RETURN_GENERATED_KEYS` in the constructor

