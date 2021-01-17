# Description

**_Given_** _three integers_ `a` ,`b` ,`c`, **_return_** _the ***largest number*** obtained after inserting the following operators and brackets_: `+`, `*`, `()`.

---

**Consider an Example** :

**_With the numbers are 1, 2 and 3_** , _here are some ways of placing signs and brackets_:

- `1 * (2 + 3) = 5`
- `1 * 2 * 3 = 6`
- `1 + 2 * 3 = 7`
- `(1 + 2) * 3 = 9`

So **_the maximum value_** that you can obtain is **_9_**.

---

**Notes**

- **_The numbers_** _are always_ **_positive_**.
- **_The numbers_** _are in the range_ **_(1  ≤  a, b, c  ≤  10)_**.
- _You can use the same operation_ **_more than once_**.
- **It's not necessary** _to place all the signs and brackets_.
- **_Repetition_** _n numbers may occur_ .
- You **_cannot swap the operands_**. For instance, in the given example **_you cannot get expression_\*** `(1 + 3) * 2 = 8`.

---

**Input >> Output Examples**:

```
expressionsMatter(1,2,3)  ==>  return 9
```

**_Explanation_**:

_After placing signs and brackets, the ***Maximum value*** obtained from the expression_ `(1+2) * 3 = 9`.

---

```
expressionsMatter(1,1,1)  ==>  return 3
```

**_Explanation_**:

_After placing signs, the ***Maximum value*** obtained from the expression is_ `1 + 1 + 1 = 3`.

---

```
expressionsMatter(9,1,1)  ==>  return 18
```

**_Explanation_**:

_After placing signs and brackets, the ***Maximum value*** obtained from the expression is_ `9 * (1+1) = 18`.

---

## Solution

```js
const expressionMatter = (a, b, c) =>
  Math.max(
    a * b * c,
    a + b * c,
    a * b + c,
    (a + b) * c,
    a * (b + c),
    a + b + c
  );
```
