# Description

An anagram is a word, a phrase, or a sentence formed from another by rearranging its letters. An example of this is "angel", which is an anagram of "glean".

Write a function that receives an array of words, and returns the total number of distinct pairs of anagramic words inside it.

Some examples:

- There are 2 anagrams in the array `["dell", "ledl", "abc", "cba"]`
- There are 7 anagrams in the array `["dell", "ledl", "abc", "cba", "bca", "bac"]`

---

## Solution

```js
const anagramCounter = (w) =>
  Object.values(
    w
      .map((w) => [...w].sort().join``)
      .reduce((a, v) => ((a[v] = ++a[v] || 0), a), {})
  ).reduce((a, v) => a + (v * (v + 1)) / 2, 0);
```
