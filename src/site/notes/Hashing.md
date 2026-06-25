---
{"dg-publish":true,"permalink":"/hashing/","dg-note-properties":{}}
---

**Passwords are stored in hash**
- Hash is a fix length code
- This ensures that the password cannot be seen by developers
- Hash is Irreversible
- SHA-1 has been breached, but it is still impractical to breach it. 
## How to Generate hash in Java
- Java provides `java.security` class, that provides various hashing algorithm
- It has a `MessageDigest` class , which is singleton class
- It requires the name of the class in the `getInstance` method
- `digest` method on the instance which requires a byte array
- The digest method returns a byte array, if we directly convert it to String using the constructor, it will converted to a string of `unicode` characters
- However, some DBMS and terminals do not understand `unicode`, hence it first each byte needs to converted to hex which will be converted to string
- ### Code
```java
public static String hash(String plainText) {
        try {
            MessageDigest md = MessageDigest.getInstance("SHA-256");
            byte[] bytes = md.digest(plainText.getBytes());
            
            StringBuilder hex = new StringBuilder(64);
            
            for(byte b: bytes) {
                hex.append(String.format("%x", b));
            }
            
            return hex.toString();
            
        } catch(NoSuchAlgorithmException e) {
            throw new RuntimeException("SHA-256 is Not Available");
        }
    }
```
