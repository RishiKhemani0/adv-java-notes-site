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

## Anatomy of a JDBC URL
`jdbc:mysql://localhost:3306/shop`
- `jdbc` = protocol
- `mysql` = subprotocol -> picks driver
- `host:port` = where
- `shop` = database name

## Steps
1. Add the Driver JAR
2. Get a Connection `DriverManager.getConnection(url, user, pass)`
3. Create Statement
4. Execute and Read `ResultSet`
5. Use Try with Resources to close everything automatically

```java
try(Connection conn = DriverManager.getConnection(connectionString)) {
    		Statement stmt = conn.createStatement();

    		String sql = "CREATE TABLE IF NOT EXISTS students(id INTEGER PRIMARY KEY AUTOINCREMENT, name TEXT, email TEXT, phone TEXT)";

    		stmt.execute(sql);

            // Insert
            stmt.execute(getInsertStatementQuery("Rishi", "r@g.com", "0000000000"));
            stmt.execute(getInsertStatementQuery("Name", "n@g.com", "0000000000"));
            stmt.execute(getInsertStatementQuery("Some", "s@g.com", "0000000000"));

            // Update
            sql = "UPDATE students SET email = 'rishi@gmail.com' WHERE id = 1;";
            stmt.execute(sql);

            // Delete
            sql = "DELETE FROM students WHERE id=2;";
            stmt.execute(sql);

            // Read
            sql = "SELECT * FROM students;";
            ResultSet rs = stmt.executeQuery(sql);

            while(rs.next()) {
                String text = """
------- Student Info -----------
ID: %d
Name: %s
Email: %s
Phone: %s
""".formatted(rs.getInt("id"), rs.getString(2), rs.getString("email"), rs.getString("phone"));

System.out.println(text);
            }

        } catch (SQLException e) {
         e.printStackTrace();
     }
}\
```
