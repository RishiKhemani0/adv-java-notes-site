---
{"dg-publish":true,"permalink":"/lambdas/","dg-note-properties":{}}
---

## Definition
- A Lamda Is an Anonymous function
- It is used with functional interfaces
- It directly overrides the method present in the function interface
- It cannot work without functional interfaces
- It is like a anonymous inner class
- It has Implicit return similar to JS
  ```java
   new Thread(new Runnable() {
		@Override
		public void run() {
			System.out.println("Hello World");
		}
	}).start();
  ```
Converts to : 
```java
new Thread(() -> System.out.println("Hello World")).start();
```
- It only works here because Runnable has a single method.
## Functional Interfaces
- Functional Interfaces are interfaces that only have one method
- Such an interface can also have other methods, that are `default`
- Functional Interfaces have a special Annotation `@FunctionalInterface`
- It looks like we have passed a function when using them with lambdas
- Ex: Runnable
## Static Methods in Interface
- An interface can have static methods
- These methods have a body
- Such methods cannot be overridden
- **Static Methods are Never Inherited**