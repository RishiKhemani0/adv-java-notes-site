---
{"dg-publish":true,"permalink":"/wildcards/","dg-note-properties":{}}
---

## Definition
A wildcard is a special syntax used when the type of the generic does not matter or is not used
- It cannot be used when declaring classes or interfaces
- It is generally used in classes


## PECS Rule
Producer Extends Consumer Super

`List<Integer>` and `List<Number>` are un-related types in Java = You cannot pass `List<Integer>` to the method asking for List`<Number>.` Hence Limiting the scope of a method. Multiple declarations need to be made for different types.

### Rules : 
1. `List<?>` Unknown Type. You can read from it as `Object`, you cannot add anything except `null`
2. ` List<? extends Number>` upper bound wildcard. T is a Number or Subtype. Read as `Number` (don't know the exact sub-class)
3. . `List<? super Integer>` lower bound wildcard. T is Integer or supertype of Integer i.e. Number, Object. Read as `Object`(since it cannot be sure of type) 
 
 * PECS Rule  - The Rule to remember which to use when you create custom methods or class :
 * 1. If the collection PRODUCES(acts as the source of the values) values and you READ from the collection - `use ? extends`(Since type T can refer to child classes)
 * 2. If the collection CONSUMES(stores values) values you WRITE into it - use `? super`(since super can hold references to children class)
 * 3. If you do both - use the exact type, no wildcard!

## Example
```java
/**
* This method PRODUES a value
* It asks for a list and then based on the values in that list it will Produce somehing
* Hence it asks for a list of the subtypes or the Number itself, as it can operate on them using the methods present in the Number itself.
* It leaves all the values unchanged
*/
static double sumWildCard(List<? extends Number> list) {
	double total = 0;

	for(Number n: list) total += n.doubleValue(); // Method present in Number class

	return total;
}
List<Integer> numbers = Arrays.asList(1, 30, 4.5);
sumWildCard(numbers)

/**
* This method consumes a List provided to it
* Here the destination list is asked as any class that is a super type of T
* Becasue such a class can store references to Type T or its subclasses
* Hence the src list is any class that is Type T itself or its subclasses
* So, When the argument CONSUMES some values, it can use the supertype for such cases
*/
static <T> void copyInto(List<? super T> dest, List<? extends T> src) {
	for(T item: src) {
		dest.add(item);
	}
}
List<Integer> source = Arrays.asList(10, 20, 30);
List<Number> dest = new ArrayList<>();

copyInto(dest, source);
```