---
{"dg-publish":true,"permalink":"/sets/","dg-note-properties":{}}
---

### Sets
 * Sets are an unordered dataset
 * It only allows unique values
 * **Does not maintain insertion order**
 * Performs operations on O(1)
 * It internally uses a `HashMap of <T, Object>` and all the Values point to a single object
 * It only uses the key part of the `HashMap`, as keys are unique
 * The value once inserted should not be mutated as it can cause undefined behavior
 *  Can perform mathematical set functions like union, etc.

## Application
 Sets are used in scenario where frequent searching is required on one element instead of pairs.
Can be used in applications where a list of unique elements is to be maintained
 
