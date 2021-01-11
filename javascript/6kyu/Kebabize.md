# Description

Modify the `kebabize` function so that it converts a camel case string into a kebab case.

```js
kebabize('camelsHaveThreeHumps'); // camels-have-three-humps
kebabize('camelsHave3Humps'); // camels-have-humps
```

Notes:

- the returned string should only contain lowercase letters

---

## Solution

```js
const kebabize = (str) =>
  str
    .replace(/\d/g, '')
    .replace(/(?<!\b)([A-Z])/g, '-$1')
    .toLowerCase();
```
