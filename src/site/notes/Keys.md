---
{"dg-publish":true,"permalink":"/keys/","dg-note-properties":{}}
---

## Rules for Keys
1. Should be [[Immutable Class\|Immutable Class]]
2. Should override method `hashCode()`
3. Should override method `equals()`

## Key Immutability
In `Hashamp`, Key Can only be a Immutable Class Like String because if the key changes the hash code will change, thus causing problems.
Ex: In an Airplane booking system the key(ticket), is a object encapsulating the seat, flightno and time