---
{"dg-publish":true,"permalink":"/virtual-key-codes/","dg-note-properties":{}}
---

## Definition
VKC : Virtual Key Codes, A code constant in all languages assigned to each key on the keyboard (Constants Defined in `KeyEvent` class in Java)

### `KeyPressed` 
When a key is pressed it contains the data about the ascii of the key, however modifiers might also be active
Typeable Chars : Characters that can be typed or print ex: a Generate a `keyTypedEvent`
## Methods to Obtain in Java
`getKeyChar()` : might return junk characters for non-Typeable chars
`getKeyCode()` : returns VKC, but returns VK_UNDEFINED for non-typeable code in `KeyTyped` Event
