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
Runnable run = () -> System.out.println("Hello World");
```
- The Object run here is still a object, it cannot be called directly
- Since, in the end it a lambda is still an anonymous inner class
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
## Standard Functional Interfaces
The name of the methods here are irrelevant, since they will be used with lambdas :
1. `Consumer<T>`:
	- `void accept(T t)`
	- Used when a certain function needs to be performed over a collection
	- This is used when only something is to be done, no value will be produced
	- Ex: `forEach`
2. `Function<T, V>`:
	- `T apply(V v)`
	- This is like map in JS
	- it takes a value and returns a value
3. `Predicate<T>`:
	- `boolean test(T t)`
	- Returns a Boolean based on the object
	- Used in cases like filter form JS
4. `Supply<T>`
	- This is like Producer
	- It does not take a object by supplies one