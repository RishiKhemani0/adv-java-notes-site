---
{"dg-publish":true,"permalink":"/closable-interface/","dg-note-properties":{}}
---

- It is a interface implemented by many classes
- It is responsible for providing by close method
- Ex `BufferedReader`, `FileReader`.

## Try With Resource
- It is a special syntax introduced in Java 8
- It is used with Closable Interface
- It automatically closes the closable
- It asks for resources in a () bracket
- These are the resources on which the entire block is dependent
- Internally, It automatically creates a finally that closes the resource