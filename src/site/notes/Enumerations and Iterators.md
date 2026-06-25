---
{"dg-publish":true,"permalink":"/enumerations-and-iterators/","dg-note-properties":{}}
---

## Definition
## `Enumeration`
 * Creates a series of elements in order, and gives each element at a time; 
* It provides read-only access and is used in legacy collections like `Vector` and `Hashtable`
* Can be used to grant read-only access to outside users
 * We can return an Enumeration of a collection to give one time access to element, without ability to add
#### Methods
 * `nextElement();`
 * `hasMoreElements();`

## `Iterator`
- The Iterator works will all `Collection` objects
- It only allows unidirectional traversal
- It allows modification like adding at current element and removing the current element
- Can throw `ConcurrentModificationException`
#### Methods
- `next()`
- `hasNext()`

## `ListIterator`
- It allows bidirectional traversal
- It allows to add, **replace** and remove elements
- It also allows to access indexes
#### Methods
- `next()`
- `hasNext()`
- `previous()`
- `hasPrevious()`

