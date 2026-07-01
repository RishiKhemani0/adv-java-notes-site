---
{"dg-publish":true,"permalink":"/functional-interfaces/","dg-note-properties":{}}
---

## Definition
- Functional Interfaces are interfaces that only have one method
- Such an interface can also have other methods, that are `default`
- Functional Interfaces have a special Annotation `@FunctionalInterface`
- It looks like we have passed a function when using them with lambdas
- Ex: Runnable
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