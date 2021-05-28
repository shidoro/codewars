# Description

Substitute two equal letters by the next letter of the alphabet (two letters convert to one):

```
"aa" => "b", "bb" => "c", .. "zz" => "a".
```

The equal letters do not have to be adjacent.
Repeat this operation until there are no possible substitutions left.
Return a string.

Example:

```
let str = "zzzab"
    str = "azab"
    str = "bzb"
    str = "cz"
return "cz"
```

Notes

- The order of letters in the result is not important.
- The letters `"zz"` transform into `"a"`.
- There will only be lowercase letters.

---

## Solution

```js
const next = c =>
  c.charCodeAt(c) === 122 ? 'a' : String.fromCharCode(c.charCodeAt() + 1);

const lastSurvivors = str =>
  !/(\w).*?\1/.test(str)
    ? str
    : lastSurvivors(str.replace(/(\w)(.*?)\1/g, (_, c, m) => next(c) + m));
```
