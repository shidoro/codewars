# Description

In this kata you have to create all permutations of an input string and remove duplicates, if present. This means, you have to shuffle all letters from the input in all possible orders.

Examples:

```js
permutations('a'); # ['a']
permutations('ab'); # ['ab', 'ba']
permutations('aabb'); # ['aabb', 'abab', 'abba', 'baab', 'baba', 'bbaa']
```

The order of the permutations doesn't matter.

---

## Solution

```js
function permutations(string) {
  if (string.length < 2) return [string];

  const perms = [];

  for (let i = 0; i < string.length; i++) {
    const ch = string[i];

    if (string.indexOf(ch) !== i) continue;

    const rest = string.slice(0, i) + string.slice(i + 1, string.length);

    for (let perm of permutations(rest)) perms.push(ch + perm);
  }

  return perms;
}
```
