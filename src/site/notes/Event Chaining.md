---
{"dg-publish":true,"permalink":"/event-chaining/","dg-note-properties":{}}
---

## Definition
1. When events are created, like `KeyEvents`
2. The same object is passed through a line of events ex. `keyPressed` -> `keyTyped` -> `keyReleased`
3. So to prevent an object from going ahead in the chain we can use consume

### Consuming an Event
Event Object has a methods consume() which consumes the event object and prevents it from continuing the chain(the events ahead are not generated);

## Example
```java
public void keyPressed(KeyEvent ke) {
        String pressedChar = String.valueOf(ke.getKeyChar());
        if(!pressedChar.matches(regex) && ke.getKeyCode() != KeyEvent.VK_BACK_SPACE) {
            ke.consume();
        }
    }
```
The above depicts a custom validation logic that only allows certain characters to move ahead, hence only allowing certain characters to be typed on a `TextField` based on regex