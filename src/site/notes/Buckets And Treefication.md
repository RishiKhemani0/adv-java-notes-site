---
{"dg-publish":true,"permalink":"/buckets-and-treefication/","dg-note-properties":{}}
---

## Buckets
 - A Bucket is Collection of Elements
 - When the capacity of a map is 16, it has 16 buckets
 - Each bucket can hold multiple elements
 - The capacity is increased on the basis of [[Maps#`loadFactor` | loadFactor]]

## `Treefication`

1. Each bucket is a  linked list till 8 elements are present in that bucket.
2. When it passes the 8 element threshold, it converts it into a BST like, Balanced(Height Balanced) Tree, where element can be found by comparing if it is greater or smaller, **and equals is not a case since if it will be equal it will be replaced.**
3. **This Process is know as `Treefication`** 
4. Has an Inner Node Class used for both
### Self Balancing Tree
 * Balances its height automatically
 * Java uses Red/Black tree for `Treeification`
 * Balancing helps to reduce the times required, it helps to perform all operations on O(log n)
 * It internally uses a BST like tree which adjusts its height using rotations