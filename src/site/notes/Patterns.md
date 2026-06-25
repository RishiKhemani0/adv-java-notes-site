---
{"dg-publish":true,"permalink":"/patterns/","dg-note-properties":{}}
---

## Definition
Pattern is a class present in `java.util.regex` package, and is used to create a regex `Matcher`. which allows to find a certain pattern in a String.
Check Also: [[Greedy Matching\|Greedy Matching]]
## Syntax
```java
	Pattern pattern = Pattern.compile(pattern);
	Matcher matcher = pattern.matcher(sourceToSearch);
```

### Matcher
* matches() of Matcher class is same as `macthes()` of String class that is it tries to match the whole string to the given pattern
* Matcher class has another instance method named as find() which finds the pattern in the given text. If it finds it returns true otherwise false.
 * Now there are two more methods in Matcher class, they are start() and end()
 * These methods are useful when our Matcher finds the Pattern, as they give start and end indexed of the occurrences that has matched
 * Matcher stops after finding a match when using the find() method
 * when calling the find() method again, it remembers its state
### Example
```java
while(matcher.find()) {
		System.out.println("Occurence: " + matcher.start() + " to " + matcher.end());
}
```
 