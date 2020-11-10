# Description

You are given an array of documents (strings), a term (string), and two booleans finetuning your indexing operation. Return an array containing the document IDs (1-based indices of documents in the array), where the term occurs, sorted in ascending order.

Booleans:

1.  CaseSensitive: `test` matches `test`, but not `Test`

    Not CaseSensitive: `test` matches both `test` and `Test`

2.  Exact Match: `test` matches `test` and `.test!`, but not `attest` or `test42`

    Not Exact Match: test matches both `test` and `attest`

**Example**:

```js
buildInvertedIndex(
  ["Sign", "sign", "Signature", "Sign-ature"],
  "Sign",
  true,
  true
);

return [1, 4];
```

---

## Solution

```js
const buildInvertedIndex = (
  coll,
  term,
  cS,
  eM,
  reg = [
    new RegExp(term, "i"),
    new RegExp(term),
    new RegExp(`\\b${term}\\b`, "i"),
    new RegExp(`\\b${term}\\b`),
  ][1 * cS + 2 * eM]
) => coll.reduce((acc, v, i) => (v.match(reg) ? acc.push(++i) : acc, acc), []);
```
