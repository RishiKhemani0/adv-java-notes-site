---
{"dg-publish":true,"permalink":"/constructor-chaining/","dg-note-properties":{}}
---

## Definition
Constructor Chaining is where the constructor of a given class calls another constructor of the same class or a parent class.
## Syntax
```java
	ClassName(args) {
		  	this(args);
	      super(args)
	      // Body
	  }
```  
## Application
Constructor Chaining is Generally used to Maintain Backward Compatibility or call private constructor in some other manner
## Example
  ```java
      public Person(String name, int age) {
          this.name = name;
          this.age = age;
      }
      
      public Person(String name) {
          this(name, 30); // Calling the constructor with two parameters
      }
      
      public Person() {
          this("Unknown"); // Calling the constructor with one parameter
      }
  ```