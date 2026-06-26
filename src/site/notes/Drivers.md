---
{"dg-publish":true,"permalink":"/drivers/","dg-note-properties":{}}
---

## Need for Driver
- It is a .jar file
- Since the above problem, a driver for each specific DBMS
- It is provided by the DBMS
- It is responsible for parsing all the objects provided by JDBC
- It converts java requests in to SQL, and converts the response into Java objects
- It contains classes implementing the interfaces like `ResultSet`, `Statement`, etc.
- Drivers are responsible for providing implementation of the interfaces present in the JDBC API
- The interfaces remain the same throughout all drivers by different vendors only the implementation changes
- Modern drivers automatically register via `META-INF/services` of the .jar file, so `DriverManager` finds the automatically.

#### `DriverManager`
- The `DriverManager` asks for the URL and finds the suitable driver
## JAR
- Java Archives
- Contains Meta Information, about all classes
- Including Entry Point, Version
- It is a collection (archive) of multiple classes
## Types
As the Types progress, they move towards pure java and remove external dependencies
The Starting types Require Config on every box whereas type 4 only needs a single line of dependency

1. **JDBC-ODBC Bridge:** 
	- It is no longer used
	- Java App -> JDBC-ODBC Bridge -> ODBC Driver -> Database.
	- ODBC was provided by Microsoft
	- It required a DSN(Data Source Name) file to connect to ODBC
	- Connect with the bridge URL pointing at the DSN.
	- It required the user of the software to create the file
	- Does not allow auto config
	- It was used earlier ODBC drivers were provided by Database, when java native drivers were not present for that Database
	

2. **Native- API Driver:**
	- It uses Native Client Library provided by The vendor of the DB
	- Java App -> Type 2 Driver -> Native Client Library -> Vendor DB
	- It uses JNI(Java Native Invocation) to communicate with Native Libraries
	- It is platform dependent
	- It is minimally used today
	- It is the fastest type
	- It requires the following :
		1. Install the Vendors Native Client on every machine 
		2. Point the OS to those binaries via PATH/LD_LIBRARY_PATH
		3. Use the OCI Flavored Ex: URL`(note:oci:@//host:1521/ORCL)`
	- Ex. Oracle OCI
	
3. **Network Protocol Driver:**
	- It is mainly used in Product Based Companies
	- Used when a product needs to connect to multiple databases and `DBMSes`
	- It requires high technical knowledge
	- Used internally in products, since it is extremely difficult to maintain multiple databases at once
	- Uses a special middleware and uses a generic internet protocol for communication with this middleware
	- This middleware is responsible for receiving requests from the java side and automatically handle which database it matches to
	- Server runs the middleware which routes to the DB
	- The URL at the application point towards the middleware
	- It is used in niche applications and is extremely complex and expensive
	- The Client is 100% java, it is a single jar file, only one driver at client for multiple DBs
	- Moves the DB-specific logic out of the client and to the server
		![Pasted image 20260626173427.png\|625](/img/user/Pasted%20image%2020260626173427.png)
	
4. **Thin Driver**
	- It is Pure Java
	- It is the easiest to use
	- It uses TCP socket to ensure communication between the java application and DBMS
	- Extremely Fast
	- Most Used
	- **Requires a different JAR per database vendor**
	- **Protocol logic lives **
	- Only One JAR is needed, direct connection with host port :
		 `Connection conn = DriverManager.getConnection(jdbc:mysql://localhost:3306);`
	- ![Pasted image 20260626174710.png](/img/user/Pasted%20image%2020260626174710.png)


| Type         | How it talks to DB       | Pure Java ?       | Portable | Speed   | Status Today                     |
| ------------ | ------------------------ | ----------------- | -------- | ------- | -------------------------------- |
| JDBC - ODBC  | Via ODBC + native driver | No                | No       | Slowest | Dead - Removed in Java 8         |
| Native - API | Via vendor native C libs | Partly            | No       | Fast    | Niche - Special Performant Cases |
| Net-Protocol | Via Middleware Server    | Yes (client-side) | Yes      | Medium  | Rare - Multi DB Gateways         |
| Thin         | Direct Native Protocol   | Yes               | Yes      | Fastest | Default                          |
