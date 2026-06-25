---
{"dg-publish":true,"permalink":"/anonymous-class/","dg-note-properties":{}}
---

## Definition
- An Anonymous class is special type of [[Inner Class\|Inner Class]], allowing only to create only one object of a class without creating an actual class definition. 
- Works similarly to [[Local Method Class\|Local Method Class]]

* **Class File Name : OuterClass$Count ex: Sample$1**

## Application
It is generally used to create objects, that are only referenced at a single place or once, hence eliminating the need to create a special class.
Ex: Creating Threads, Handling Events, etc.
## Example
  ```java
  Runnable obj = new Runnable() {
		@Override
		public void run() {
			System.out.println("Hello World");
		}
	};
  ```
```java
// Implementing ActionListener using an anonymous class 
button.addActionListener(new ActionListener() { 
	@Override 
	public void actionPerformed(ActionEvent e) { 
		System.out.println("Button was clicked!"); 
	}
});
```