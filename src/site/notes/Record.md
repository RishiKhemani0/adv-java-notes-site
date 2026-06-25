---
{"dg-publish":true,"permalink":"/record/","dg-note-properties":{}}
---

## Definition
A Record is A [[Immutable Class\|Immutable Class]] That is used to create POJO(Plain old Java Objects), these are usually such classes that are only used for data and have no functionality associated with them
Usually Creating such classes is tedious as it requires to create getters ,etc. **Records Were Introduced In Java 17**
Records Provide The Following by Default :
 1. Getters named as the variables, ex name()
 2.  One Constructor
 3. `toString`
4. `equals`
5. `hashCode`

A Record Cannot Inherit but can implement because, records are internally created as following
```java 
final RecordName extends java.lang.Record {};
```

## Syntax
```java
	record Student(String name, int age) implements Greet {
	public void sayHello() { // Method from Greet interface
		System.out.println("Hello World");
	}
}
```  
## Application
Records are usually used in Data Transfer like Objects Specifically created for Creating Responses in Java, since everything in Java requires concrete types.