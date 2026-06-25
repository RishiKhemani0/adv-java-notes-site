---
{"dg-publish":true,"permalink":"/switch-expressions/","dg-note-properties":{}}
---

## Definition
- Like all expressions, `switch` expressions evaluate to a single value and can be used in statements. 
- They contain "`case L ->`" labels that eliminate the need for `break` statements to prevent fall through.
- They can also combine multiple cases in a single case
- They provide better and safer usage of switch

## Example
```java
// Normal Switch Case
// May cause Fall Through if a break; statement is missed
static String getDayTypeOld(String day) {
		String type;

		switch (day) {
			case "Sunday":
			case "Saturday":
				type = "Weekend";
				break;
			case "Monday":
			case "Tuesday":
			case "Wednesday":
			case "Thursday":
			case "Friday":
				type = "Weekday";
				break;
			default:
				type = "Unknown";
		}

		return type;
	}
	// Switch Expressions
	static String getDayTypeNew(String day) {
		return switch (day) {
    		case "Saturday", "Sunday" -> "Weekend";
    		case "Monday", "Tuesday", "Wednesday", "Thursday", "Friday" -> "Weekday";
    		default -> "Unknown";
    	};
	}
```

## The yield Statement
- The yield statement in a switch expression is used to return a value from inside a block
- In the above example, the values are returned directly, without needing a block
- However, some cases may need a block
- Hence yield statements are used to return values from inside them, also acting as a `break;`
## Example of `yield;`
```java
int numLetters = switch (day) {
         case MONDAY, FRIDAY, SUNDAY -> {             
	         System.out.println(6);             
	         yield 6;         
         }         
         case TUESDAY -> {             
	         System.out.println(7);             
	         yield 7;         
         }         
         
         case THURSDAY, SATURDAY -> {             
	         System.out.println(8);             
	         yield 8;         
	    }         
	    
	    case WEDNESDAY -> {             
		    System.out.println(9);             
		    yield 9;         
		}         
		
		default -> {             
			throw new IllegalStateException("Invalid day: " + day);         
			}     
```
### Reference :
[Switch Expression Docs](https://docs.oracle.com/en/java/javase/21/language/switch-expressions-and-statements.html)