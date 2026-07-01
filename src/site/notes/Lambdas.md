---
{"dg-publish":true,"permalink":"/lambdas/","dg-note-properties":{}}
---

## Definition
- A Lamda Is an Anonymous function
- It is used with functional interfaces
- It directly overrides the method present in the [[Functional Interfaces\|Functional Interfaces]]
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
Runnable run = () -> System.out.println("Hello World");
```
- The Object run here is still a object, it cannot be called directly
- Since, in the end it a lambda is still an anonymous inner class
- It only works here because Runnable has a single method.
## Static Methods in Interface
- An interface can have static methods
- These methods have a body
- Such methods cannot be overridden
- **Static Methods are Never Inherited**