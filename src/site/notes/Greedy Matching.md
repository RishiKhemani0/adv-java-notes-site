---
{"dg-publish":true,"permalink":"/greedy-matching/","dg-note-properties":{}}
---


Greedy Matching: tries to match the max possible characters
* Reluctant Matching: Stops at the first match
 
 * **Reluctant Qualifier: ?**
 
### Example
Assume if there are two headings :
```html
<h2>Heading 1</h2>
<h2>Heading 2</h2>
```

#### Greedy Match: `(<h2>)(.*)(</h2>)`
It will collect both the h2s, because it will try to match as much as possible

#### Reluctant Match : `(<h2>)(.*?)(</h2>)`
 Will only match to first h2 in the first find