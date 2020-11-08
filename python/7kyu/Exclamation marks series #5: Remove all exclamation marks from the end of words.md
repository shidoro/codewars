# Description

Remove all exclamation marks from the end of words. Words are separated by spaces in the sentence.

**Examples**

```py
remove("Hi!") === "Hi";
remove("Hi!!!") === "Hi";
remove("!Hi") === "!Hi";
remove("!Hi!") === "!Hi";
remove("Hi! Hi!") === "Hi Hi";
remove("!!!Hi !!hi!!! !hi") === "!!!Hi !!hi !hi";
```

---

## Solution

```py
remove = lambda s: __import__('re').sub(r"\b!+", '', s)
```
