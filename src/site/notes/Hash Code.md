---
{"dg-publish":true,"permalink":"/hash-code/","dg-note-properties":{}}
---


1. `hashCode`() is a method present Object class
2. `hashCode` returns an integer value that can be same for multiple objects
3. This `hashCode` is used to generate a hash value that is used to decide the bucket it will be placed in.
4. The hash value might be same and hence collision handling is required
5. The hash code is independent, however hash is dependent on the size of the HashMap
6. Key Class provides `hashCode` -> Java generates hash value using the hash code -> bucket is selected