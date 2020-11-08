# Description

An Arithmetic Progression is defined as one in which there is a constant difference between the consecutive terms of a given series of numbers. You are provided with consecutive elements of an Arithmetic Progression. There is however one hitch: exactly one term from the original series is missing from the set of numbers which have been given to you. The rest of the given series is the same as the original AP. Find the missing term.

You have to write a function that receives a list, list size will always be at least 3 numbers. The missing term will never be the first or last one.

**Example**

```py
find_missing([1, 3, 5, 9, 11]) == 7
```

---

## Solution

_maths_

```py
def find_missing(s):
    return (s[0] + s[-1]) * (len(s) + 1) / 2 - sum(s)
```

_don't dispare, you don't need to know maths to do it_

```py
def find_missing(s):
    s = sorted(s, key = int)
    difference = min(s[1] - s[0], s[2] - s[1], s[3] - s[2])
    x = set(s)
    y = set(range(s[0], s[-1] + 1, difference))

    return len(s) if x == y else list(x ^ y)[0]
```
