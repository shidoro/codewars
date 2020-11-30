# Description

There are a series of 10 bombs about to go off! Defuse them all! Simple, right?

Note: This is not an ordinary Kata, but more of a series of puzzles. The point is to figure out what you are supposed to do, then how to do it. Instructions are intentionally left vague.

---

## Solution

```js
// 10 - 9
[42, 42, 42, 42, 42, 42].forEach((key) => Bomb.diffuse(key));

// 8
Bomb.diffuse(BombKey);

// 7
Bomb.diffuse((diffuseTheBomb = () => 1));

// 6
Bomb.diffuse(3.14159);

// 5
Bomb.diffuse(new Date(new Date().setFullYear(new Date().getFullYear() - 4)));

// 4
Bomb.diffuse(Object.freeze({ key: 43 }));

// 3
Bomb.diffuse({ valueOf: () => (this.flag ? 11 : ((this.flag = true), 9)) });

// 2
Math.random = function () {
  return { valueOf: () => (this.flag ? 1 : ((this.flag = true), 0.5)) };
};
Bomb.diffuse(42);

// 1
Array.prototype.valueOf = function () {
  return this.reduce((acc, v) => acc + v, 0);
};
Bomb.diffuse(new Buffer("yes"));
```
