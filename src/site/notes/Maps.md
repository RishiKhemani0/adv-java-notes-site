---
{"dg-publish":true,"permalink":"/maps/","dg-note-properties":{}}
---

 * It Acts at a different Class at the level of the List (Implements `Collection` Interface)
 * It Stores two different value: Key, Value
 * **Each entry is a (Map.)Entry: A interface encapsulating the Key Value Pair Stored in Map**
 * **Entry is an [[Inner Class\|Inner Class]] since, it should/could not exist without a map**

## Applications
Frequency Counting, Unique values based on keys, states etc.
## Operations
 * `put(K, V)`: returns old value and replaces with new if value is present
 * `get(K)`: return value or null if not found
 * `getOrDefault(K, defaultValue)`
 * `entrySet() `: returns Set of Entry<K, V>, used for iteration
 * `keySet()`: returns set of key, use o iteration

### `loadFactor`:
**`loadFactor` only affects map that internally use hashing, hence doesn't affect `TreeMap` or `EnumMap`**
1. The percentage of space filled before HashMap size is doubled, default: 0.75
2. Whenever the size of a HashMap is changed the hash needs to be updated, since it is dependent on the size
3. Rehashing is a very expensive operation, since hash value for each key needs to be re calculated
4. Hence, the `loadFactor` is defined on the basis of expected values to minimize rehash operations
5. Ex if the capacity is 16 and 12 elements are inserted the number of buckets is increased
6. The reason the capacity is increased because if multiple elements are present in a single bucket the performance decreases 
### `HashMap` 
 * HashMap does not preserve insert order
 * Uses Chaining with a special tree for Collision Handling
 * Starts with capacity 16 (buckets)
 * It makes use of the [[Hash Code\|Hash Code]] method
 * Uses [[Buckets And Treefication\|Buckets And Treefication]]
### `TreeMap` 
 * Requires Key to be Comparable or Requires a Comparator, since tree inserts on the basis of value 
 * It is used for sorting, ranges.
 * It is sorted in nature
 * Doesn't use Hashing
 * Uses [[Buckets And Treefication#Self Balancing Tree \| Self Balancing Tree]] (Red-Black Tree) Internally

### `LinkedHashMap` :
 * Maintains a Linked List for order
 * And also maintains a normal HashMap
 * `LinkedHashMap(capacity, loadFactor, boolean orderingMode)`
 * Ordering:
    1. false: Insertion Order
    2. true: Access-Order, changes order based on any get, add or remove;
              Used in applications like LRU
    
