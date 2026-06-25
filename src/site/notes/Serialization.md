---
{"dg-publish":true,"permalink":"/serialization/","dg-note-properties":{}}
---

- Serialization is the process of converting a java object in a String
- This string is not in human readable format, but allows for transfer of java objects
* The class needs to implement interface Serializable 
 * The process of converting JS object to JSON was also serialization
 * An `ObjectOutputStream` is used to write and an `ObjectInputStream` is used to read\

## Applications
* Used to store objects in a file 
* Used to send object outside of Java
 * It converts any object into a string and send it to a file/network etc.
 * 
### Unique Identifier
 * Every class has an Unique Identifier
 * It is assigned to each class file created
 * This UID is used during serialization, every object stores this serialization ID
 * When loading a serialized object it compares the ID of the Object being loaded with the UID of the class
 * Only if they match, the object is loaded
 * **If they don't match, a `InvalidClassExpection` is thrown** 
 * Usually This version ID is created automatically using the variables present in the class, however we can override this ID by creating a constant in the class
 * This allows to ensure backwards compatibility when needed

### Example
```java
class Student implements Serializable {
	private static final long serialVersionUID = 1L;
    String name;
    int age;
    String course;
    String email;
	
	// Class Body
}

public class SerializationDemo {
	static public final String FILE_NAME = "students.ser";

	public static void main(String[] args) {
		Student orignal = new Student("SL", 21, "Advance Java");
		System.out.println("Before: " + orignal);

		try {
		// Serializing an object
			ObjectOutputStream oos = new ObjectOutputStream(new FileOutputStream(FILE_NAME));
			oos.writeObject(orignal);
			System.out.println("Object Written to " + FILE_NAME);
			oos.close();
		} catch (IOException e) {
			e.printStackTrace();
		}

		try {
		// De-Serializing an Object
			ObjectInputStream ois = new ObjectInputStream(new FileInputStream(FILE_NAME));
			Student loaded;
			while((loaded = (Student) ois.readObject()) != null) {
				System.out.println("Loaded: " + loaded);
			}
		//  ClassNotFound expection occurs if the class file for the obejcts class cannot be found
		// IOException mig
		} catch (ClassNotFoundException | IOException e) {
			e.printStackTrace();
		}
	}
}

```