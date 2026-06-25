---
{"dg-publish":true,"permalink":"/generics/","dg-note-properties":{}}
---

## Definition
- Generics are a special technique which allow to create classes without a concrete type
- When making a stack, one might need to make different stacks for int and char
- Hence to avoid this generics are used
- They were Introduced in **Java 4**
- It improves reusability
- Methods and Interfaces can be generic too
- [[Generics#Bounded Type Parameters\|#Bounded Type Parameters]]
## Example
#### Generic Class
```java
class Box<T> {
	private T box;

	Box(T value) { box = value; }

	T get() { return box; }

	@Override
	public String toString() {
		return "Box [box: " + box + "]";
	}
}

// Creating an Object
Box<Integer> ageBox = new Box<>(19);
Box<String> nameBox = new Box<>("Study Link");
Box objectBox = new Box<>(AnyObject);
```
When creating a Generic object without mentioning the type , the generic assumes type `Object` and gives an **Unsafe Operations Warning**

#### Generic Interface
```java
interface Predicate<T> {
    	boolean test(T value);
    }

static <T> boolean allMatch(List<T> list, Predicate<T> predicate) {
	for(T item: list) {
		if(!predicate.test(item)) {
			return false;
		}
	}

	return true;
}

// Calling the Method
boolean allPositive = allMatch(
		new ArrayList<Integer>(Arrays.asList(listName)), 
		new Predicate<Integer>() { // Anonymous Class
			public boolean test(Integer n) { return n >= 0; }
});
```
#### Generic Method
```java
// Might require the same method for all types
static int firstOrDefaultInt(int[] arr, int def) {
		return arr.length > 0 ? arr[0] : def;
	}

static <T> T firstOrDefault(T[] arr, T def) {
	return arr.length > 0 ? arr[0] : def;
}
```

## Bounded Type Parameters
Allows to ensure that generics extends/implement a certain class or interface
 * This allows to avoid `ClassCastExcetion` and call functions present in that interface/class
 * `<T extends Interface|Class>>`
 * `<T extends Interface & Interface>>`
 * The Keyword always remains extends
 * We can be sure that the obtained type will have a particular method and can use it safely