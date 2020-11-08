# Description

Task
In the field, two programmers A and B found some gold at the same time. They all wanted the gold, and they decided to use the following rules to distribute gold:

They divided gold into n piles and be in line. The amount of each pile and the order of piles all are randomly.

They took turns to take away a pile of gold from the far left or the far right.

In each round, the programmer will use his wisdom to choose the gold that is best for him.

Given an integer array `golds`. Please calculate the final amount of gold obtained by A and B. returns a two-element array `[amount of A, amount of B]`.

Note, we can assume that A always takes first, and each time they used the best strategy.

Example
For `golds = [10,1000,2,1]`, the output should be `[1001,12]`.

```
At 1st turn, A can take 10 or 1, 10 is greater than 1.
Should we choose 10? No, clever programmer don't think so ;-)
Because if A choose 10, next turn B can choose 1000.
So, A choose 1 is the best choice.

At 2nd turn, Whether B chooses 10 or 2, in the 3rd turn, A can always choose 1000.
So, B choose 10 is the best choice.

Final result:
A: 1 + 1000 = 1001
B: 10 + 2 = 12
```

For `golds = [10,1000,2]`, the output should be `[12,1000]`.

In this example, the choice A faces is the same as the 2nd turn in the previous example.

---

## Solution

```js
const distributionOf = (gold) =>
  ((total, result) => [result, total - result])(
    gold.reduce((acc, v) => acc + v, 0),
    bestChoice(gold)
  );

const calc = (matrix, i, j) => (i <= j ? matrix[i][j] : 0);

const bestChoice = (gold) => {
  const len = gold.length;

  if (len === 1) return gold[0];

  if (len === 2) return Math.max(gold[0], gold[1]);

  const matrix = Array(len)
    .fill()
    .map((x) => Array(len).fill(0));

  for (let k = 0; k < len; k++) {
    let i = 0;
    let j = k;
    while (j < len) {
      const start =
        gold[i] + Math.min(calc(matrix, i + 2, j), calc(matrix, i + 1, j - 1));
      const end =
        gold[j] + Math.min(calc(matrix, i + 1, j - 1), calc(matrix, i, j - 2));
      matrix[i][j] = Math.max(start, end);
      i++;
      j++;
    }
  }
  return matrix[0][len - 1];
};
```
