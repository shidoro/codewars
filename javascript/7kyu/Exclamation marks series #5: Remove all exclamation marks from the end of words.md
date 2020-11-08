# Description

Remove all exclamation marks from the end of words. Words are separated by spaces in the sentence.

**Examples**

```js
remove("Hi!") === "Hi";
remove("Hi!!!") === "Hi";
remove("!Hi") === "!Hi";
remove("!Hi!") === "!Hi";
remove("Hi! Hi!") === "Hi Hi";
remove("!!!Hi !!hi!!! !hi") === "!!!Hi !!hi !hi";
```

---

## Solution

```js
const remove = (s) => s.replace(/(?=\b)!*/g, "");
```
