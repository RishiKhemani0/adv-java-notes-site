---
{"dg-publish":true,"permalink":"/inner-class/","dg-note-properties":{}}
---

## Definition
- A Inner Class is a class created inside a class
- This class can be Private/Public/Protected
- An Inner class can access private variables of the outer class
- The Inner class cannot be directly accessed outside (needs an object of the outer class if the inner class is not static)
- A .class File is created for each inner class, usually named `OuterClass$InnerClass.class`
- A Inner Class can be static
## Syntax
```java
	class Outer {
		private int x;
		Outer(int x) {
			this.x = x;
		}
		class Inner {
			void display() {
				x++;
				System.out.println("Display of Inner: " + x); 
			}
		}
		 
		static class Nested {
			void display() {
				System.out.println("Display of Nested");
			}
		}
}
```
### Access
  ```java
  // Since it is static, it doesnt need an object to be declared
	Outer.Nested nested = new Outer.Nested();
	
	Outer outer = new Outer(20);
	Outer outer2 = new Outer(10);
	
	// Since it is Inside a clas, it needs the object of the outer class to create itslef
	// Hence objname.new ClassName(), binds the inner objcet to the outer object, allowing it to access the values 
	Outer.Inner inner = outer.new Inner();
	Outer.Inner inner2 = outer2.new Inner();
  ```
## Application
Inner Classes are used in patterns like [[Builder Pattern\|Builder Pattern]], but are mainly used to created classes that should not exist without the outer class, this helps to ensure proper OOP
## Example
A Class Named Seat is created inside the Theater class, since a Seat cannot exist without a Theatre