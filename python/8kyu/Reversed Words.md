# Description

Complete the solution so that it reverses all of the words within the string passed in.

Example:

```py
reverseWords('The greatest victory is that which requires no battle');
// should return "battle no requires which that is victory greatest The"
```

---

## Solution

```py
def reverseWords(s):
    return ' '.join(s.split()[::-1])
```
