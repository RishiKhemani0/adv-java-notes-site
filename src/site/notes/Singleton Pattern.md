---
{"dg-publish":true,"permalink":"/singleton-pattern/","dg-note-properties":{}}
---

## Definition
- It is class design pattern that internally ensures that only a single object of the singleton class is created
- It reuses that object across the application
- Every constructor is private
- It stores a static reference to a object named `instance`, which is of the same class as itself
- It provides a factory method name `getInstance` which returns the `instance` object
- It will make sure only a single object of the class is create, this object remains static and `getInstance` returns that same reference every time.

## Application
Creating a Class `DBConnection`, that will be used everywhere to connect to the database; 

## Synchronization
- When multiple threads are present, they will check if it the object is null and may initialize it multiple times
- Hence it needs to be synchronized in some way
```java
// The method is not synchronized because, even if the instance is initialized, each thread will have to wait everyime, reducing performance.
public static DBConnection getInstance() throws SQLException {
		// Only Initialize Object when it is null
        if(instance == null) {
	        
	        // Multiple threads may detect object as null in the start, so they may initialize the object multiple times
	        // Since instance is null we cannot use it as lock object, hence we use the class string as lock, just for dummy puprpose
            synchronized (DBConnection.class) {
                if(instance == null) {
                    instance = new DBConnection();
                }
            }
        }
        
        // No need to wait for synchronized block if instance is not null
        return instance;
    }
```
## Example
```java
public class DBConnection {
	// Static instance object
    private static DBConnection instance = null;
    
    // Static Connection object to be used
    private Connection connection = null;
    
    // Connection Details
    private static final String DB_NAME = "expense_tracker";
    private static final String CONNECTION_URL = "jdbc:mysql://localhost:3306/" + DB_NAME;
    private static final String userName = "root";
    private static final String password = "rishi";
    
    // All Constructors should be rpivate
    private DBConnection() throws SQLException {
        connection = DriverManager.getConnection(CONNECTION_URL, userName, password);
    }
    
    // The getInstance Method
    public static DBConnection getInstance() throws SQLException {
        if(instance == null) {
            synchronized (DBConnection.class) {
                if(instance == null) {
                    instance = new DBConnection();
                }
            }
        }
        
        return instance;
    }
}

```