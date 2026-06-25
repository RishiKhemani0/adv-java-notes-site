---
{"dg-publish":true,"permalink":"/basics/","dg-note-properties":{}}
---

## Need For JDBC
- Stands Java Database Connectivity API
- It is a standard Java API (Set of Interfaces) that lets any Java program talk to any relational database using the same code
- It is provided by Java
- Since Java only understands Objects, however DBMS does not respond in objects
- Nor does the DBMS understands Java Objects
- Hence JDBC is provided by Java, Which is responsible for communicating to the DBMS
- Communicates with the [[Drivers\|Drivers]]

Java App -> JDBC API -> Driver -> Database
## Classes Provided
- It provides `DriverManager`, `ResultSet`, `Statement`, and `Connection` all interfaces, since all the classes for different DBMS change something, and hence they are different classes
- This allows us to easily swap, between different DBs without making major changes.

## Architecture
1. Your Java Code (`Connenection`, `Statement`, `ResultSet`) Communicates with `DriverManager`
2. `DriverManager` picks the correct driver and Communicates with the actual Driver
3. The [[Drivers\|Drivers]] parse the JDBC objects and communicate with the DBMS
4. DBMS returns a Result in the form of rows (if applicable)
5. This Result is converted into a Java Objects by The Driver and is directly returned to the Java Program
**The Top layer(your java code) remains the same whereas the Drivers are pluggable, The types of [[Drivers\|Drivers]] are just a way to build such a bottom layer**