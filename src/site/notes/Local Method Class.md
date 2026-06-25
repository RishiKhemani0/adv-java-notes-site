---
{"dg-publish":true,"permalink":"/local-method-class/","dg-note-properties":{}}
---

## Definition
A Local Method Class is A Class Created inside a Method itself, this class can only be used inside the method and cannot be accessed outside.
**All Variables in a method containing the class should be final or effectively final, however the outer class can have normal variables**

***Not Widely Used*** 
### Why No Variables Declared in A Method with Local Class can be modified

- All the objects in java are created in the heap whereas variables of the local methods are created in the stack
- The Inner Class can easily access the variable(of the object) inside the heap
* However, when accessing the variables of the method, it is not possible, since they are on the stack
* Hence, java injects a copy of these variables inside the Inner Class
* Therefore to avoid confusion and synchronization issues, all the variables of method accessed inside the inner class must be final or effectively final (unchanged throughout the method)
* Since these variables might be used after being changed, and it will not update inside the Inner Class and can cause issues
* **Summary: Inner Class Cannot Access Stack Variables(Synchronization Issues), Hence a Copy is injected**
## Application
Creating validator class inside a method to validate before performing the action, Abstracting the process from the method
## Example
  ```java
class OuterClass {
	int x = 20;

	void display() {
		int local = 10;
		System.out.println("1st Line of Display");

		int local2 = 20;
		class Inner {
			void show() {
				x++;
				// local++; Not Allowed
				System.out.println("Show of Inner : " + x + " " + local);
			}
		}

		Inner obj = new Inner();
		obj.show();

		// Only variables used in the Inner class should be final
		local2++;
		System.out.println(local2);
		
		// local++ Not Allowed
		System.out.println("Last line of Display");
	}
}

  ```