---
{"dg-publish":true,"permalink":"/vectors-and-array-list/","dg-note-properties":{}}
---


| Vector                                                                                                                                                                                                   | ArrayList                                                                             | LinkedList                                                                   |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------- |
| IIt is a legacy collection, which was introduced in Java 1.0                                                                                                                                             | It is a newer collection which was introduced as part of the **Collection Framework** | It is also a newer collection and was introduced in **Collection Framework** |
| It is synchronized                                                                                                                                                                                       | It is not synchronized                                                                | It is not synchronized                                                       |
| It performs much slower when performing concurrent reads, hence making it less suitable for applications requiring concurrent reads but no writes. Performance difference increases as Threads increases | It performs faster when performing concurrent reads                                   | It also performs slower reads as a read operation in LinkedList is O(n)      |
| t is suitable for applications requiring writes without data loss or race condition                                                                                                                      | It can cause data loss in concurrent writes                                           | It is more faster for write operations, specially head insertions            |
|                                                                                                                                                                                                          |                                                                                       |                                                                              |

### Speed Comparison for Read Operations `ArrayList` and `Vector` 
 * 10 Threads: ~4
 * 10 Threads: ~16
 * 1000 Threads: ~27 to ~33
*`ArrayList` is faster*

### Applications
  * When creating a music album, once created it wont be changed, thus no expensive insert operations are required, `ArrayList` is used
  * When creating a playlist, it may change overtime hence, LinkedList is used
  * We can create a collection as LinkedList when adding elements, and then can convert back to `ArrayList` when writing is done and reading is required