# Description

Given: an array containing hashes of names

Return: a string formatted as a list of names separated by commas except for the last two names, which should be separated by an ampersand.

Example:

```js
list([{ name: 'Bart' }, { name: 'Lisa' }, { name: 'Maggie' }]);
// returns 'Bart, Lisa & Maggie'

list([{ name: 'Bart' }, { name: 'Lisa' }]);
// returns 'Bart & Lisa'

list([{ name: 'Bart' }]);
// returns 'Bart'

list([]);
// returns ''
```

Note: all the hashes are pre-validated and will only contain A-Z, a-z, '-' and '.'.

---

## Solution

```js
const list = names =>
  names.reduce(
    (acc, v, i) =>
      acc +
      v.name +
      (i < names.length - 2 ? ', ' : i < names.length - 1 ? ' & ' : ''),
    ''
  );
```
