# Description

You are given an array of documents (strings), a term (string), and two booleans finetuning your indexing operation. Return an array containing the document IDs (1-based indices of documents in the array), where the term occurs, sorted in ascending order.

Booleans:

1.  CaseSensitive: `test` matches `test`, but not `Test`

    Not CaseSensitive: `test` matches both `test` and `Test`

2.  Exact Match: `test` matches `test` and `.test!`, but not `attest` or `test42`

    Not Exact Match: test matches both `test` and `attest`

**Example**:

```py
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

```py
import re
def build_inverted_index(coll, term, cS, eM):
    return [i + 1 for i, x in enumerate(coll) if re.search(r"{0}{1}{0}".format('\\b' if eM else '', term), x, flags = not cS and re.I)]
```
