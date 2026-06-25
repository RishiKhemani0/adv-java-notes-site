---
{"dg-publish":true,"permalink":"/amortized-analysis/","dg-note-properties":{}}
---

## Definition
1. The Amortized analysis is a method to analyze the Time Complexity of a particular operation.
2. Instead of focusing on the worst or the best case, it counts the average cost of the operation over a number of operations
3. This helps to identify the performance of the given operation over a sequence rather than focusing on it in a isolated way
## Example
- A `ArrayList` is a dynamic collection, hence it increases its size whenever the number of elements surpass the capacity
- When performing `add()` operation 
	1. **Best Case** :  `O(1)` 
	2.  **Worst case** : `O(n)` 
	3. **Average case** :  `O(n)`

However the amortized analysis works as following : 
- Assuming the size and capacity of the `ArrayList` are currently 10, hence total 10 operations are performed at `O(1)`
- When the 11th element is added the capacity needs be to incresed
- A new array is created will a increased capacity, and all the existing elements are copied to new array : `O(n)`
- Hence Amortized Case will be :
	- = Total Time Required / Number of Operations
	- = `O(n)` + 10 * O(1) / 11
	- = 10 + 10 / 11
	- = 1.8
	- = `O(1)`

Hence When considering the time required by the given operation over a period is constant, so the `ArrayList` add operation runs in amortized constant time. 