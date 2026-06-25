---
{"dg-publish":true,"permalink":"/auto-boxing/","dg-note-properties":{}}
---

## Definition
Auto Boxing is a feature in java, when using [[Generics\|Generics]] we can only use objects as types for the Generics. Hence when using a primitive type with it, it needs to be wrapped in a wrapper class
- Auto-Boxing automatically converts a primitive data type in a wrapper class when it is passed as the corresponding Wrapper Class.

### Auto-Unboxing
When fetching the elements from such collections, they are also unwrapped to store into primitive type

## Example
`add(1) => add(new Integer(1))`