# Description

Create a function mispelled(word1, word2):

```js
mispelled("versed", "xersed"); // returns true
mispelled("versed", "applb"); // returns false
mispelled("versed", "v5rsed"); // returns true
mispelled("1versed", "versed"); // returns true
```

It checks if the word2 differs from word1 by only one character.

This can include an extra char at the end or the beginning of either of words.

In the tests that expect `true`, the mispelled word will always differ only by one character.

---

## Solution

```js
const mispelled = (word1, word2) =>
  ((len) =>
    len
      ? len === 1
        ? word2.includes(word1) || word1.includes(word2)
        : false
      : [...word1].reduce((acc, v, i) => acc + (word2[i] === v), 0) ===
        word2.length - 1
      ? true
      : false)(Math.abs(word1.length - word2.length));
```
