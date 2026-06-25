---
{"dg-publish":true,"permalink":"/builder-pattern/","dg-note-properties":{}}
---

## Definition
- The Builder Pattern is a Pattern where a special class is created inside a class, this class is used to construct an object of the outer class.
- The Outer Class usually only have private constructors
- A factory method usually named "build" is present in the Builder class that returns the object of the outer class
- Uses [[Inner Class\|Inner Class]]
## Application
In Scenarios where most of the fields in a object are optional, the builder pattern is especially useful
* Otherwise, we would have to create a constructor to accommodate all optional values
* In Backend, response objects have many optional fields, hence it is easier to create using Builder Pattern
## Example
  ```java
class Student {
	private String name;
	private int age;
	private String department;
	private float averagePercentage;

	// Can Access private fields as the class is inside it
	private Student(Builder obj) {
		this.age = obj.age;
		this.name = obj.name;
		this.department = obj.department;
		this.averagePercentage = obj.averagePercentage;
	}

	static class Builder {

		// Can assign default values here for optional values
		private String name; private int age; private String department;
		private float averagePercentage;

		// Methods for assigning to all variables
		Builder name(String name) {
			this.name = name;
			return this;
		}

		Builder age(int age) {
			this.age = age;
			return this;
		}

		Builder department(String department) {
			this.department = department;
			return this;
		}

		Builder averagePercentage(float averagePercentage) {
			this.averagePercentage = averagePercentage;
			return this;
		}
		
		// Factory Method
		Student build() {
			return new Student(this);
		}
	}

	@Override
	public String toString() {
		return "Student: [name: " + name + ", age: " + age + ", department: " + department + ", averagePercentage: " + averagePercentage + " ]";
	}
}

class BuilderPattern {
	public static void main(String args[]) {
		Student s = new Student.Builder()
						.name("Rishi")
						.age(18)
						.department("Comps")
						.averagePercentage(90.1F)
						.build();

		System.out.println(s);
	}
}
  ```