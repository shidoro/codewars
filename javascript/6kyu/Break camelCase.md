# Description

Complete the solution so that the function will break up camel casing, using a space between words.

**Example**

```
solution("camelCasing")  ==  "camel Casing"
```

---

## Solution

```js
const solution = (string) => string.replace(/[A-Z]/g, ' $&');
```
