# Description

Your task is to remove all **consecutive duplicate** words from string, leaving only first words entries. For example:

```
"alpha beta beta gamma gamma gamma delta alpha beta beta gamma gamma gamma delta"

--> "alpha beta gamma delta alpha beta gamma delta"
```

---

## Solution

```js
const removeConsecutiveDuplicates = (s) =>
  s.replace(/\b(\w+)(\s(\1\b))+/g, "$1");
```
