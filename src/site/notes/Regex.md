---
{"dg-publish":true,"permalink":"/regex/","dg-note-properties":{}}
---

### Regex Notations
* . :  Matches with everything  
 * ^ : Starts With
 * $ : Ends With 
 * [] : Matches with anything inside
 * ^ inside [] : not matches with anything inside
 * - inside []: denotes range
 * (?) : flags
 * (?i): insenitive case flag
 * \s : space charachters (entire tab as 1 char)
 * \S: all non spaces
 * \w: [A-Za-z0-9]
 * \W: [^A-Za-z0-9]
 * \b: selects start and end of word, not valid for charachters ex: XHelloX
 * \B: selects inside word and around each char ex: HXeXlXlXo also valid for chars and tabs
 * char{start, end}: both are optional
 * + : at least 1
 * * : optional character 
 * ? : Used in [[Greedy Matching\|Greedy Matching]]
### groups:
Groups in regex are created using (), a pair of this denotes a group, 
Ex : `(<h2>)(.*)(</h2>)`
Here group 0 is the entire pattern and the opening tag is group 1 and so on
Groups are used with [[Patterns\|Patterns]] and the group function