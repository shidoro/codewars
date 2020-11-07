# Description

In this lesson we learn three methods of Math: `max()`, `min()` and `abs()`.

Their definitions and detailed information:

- [Math.max()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/max)
- [Math.min()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/min)
- [Math.abs()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/abs)

Their usage is very simple: for the given parameters, return the maximum value, minimum value and absolute value. Here we use some examples to understand their usage:

```js
var a = 1,
  b = 2,
  c = -1;
console.log(Math.max(a, b)); //output: 2
console.log(Math.min(a, b)); //output: 1
console.log(Math.abs(c)); //output: 1
```

`abs()` can has only one parameter, `max()` and `min()` can has more than one parameters. See example:

```js
var a = 1,
  b = 2,
  c = -1;
console.log(Math.max(a)); //output: 1
console.log(Math.max(a, b, c)); //output: 2
console.log(Math.min(a)); //output: 1
console.log(Math.min(a, b, c)); //output: -1
console.log(Math.abs(a)); //output: 1
console.log(Math.abs(a, b, c)); //output: 1
console.log(Math.abs(b, a, c)); //output: 2
console.log(Math.abs(c, b, a)); //output: 1
```

We can see: For `max()` and `min()`. If it has only one parameter, method returns the parameter itself; If it has many parameters, method will return the maximum / minimum values; For `abs()`. No matter how many parameters, it returns only the absolute value of the first parameter.

`max()` and `min()` can accept an array as a parameter by using `spread operator (...)`. The following example is a classic usage, to calculate the maximum/minimum values of the array:

```js
var arr = [1, 2, 3, 4, 5];
console.log(Math.max(...arr)); //output: 5
console.log(Math.min(...arr)); //output: 1
```

Ok, lesson is over. let's us do some task.

## Task

Coding in function `maxMin`. function accept 2 parameter `arr1` and `arr2`. They are two number array and have the same number of elements.

First, calculate the difference of the same index of the `arr1` and `arr2`. Like this:

```js
[1,3,5]
 | | |   --->  8, 5, 2
[9,8,7]
```

Please note that the difference is positive. Such as the above 1 and 9, the difference should be 8, not -8. I think `abs()` can help you get the correct result ;-)

Then find the maximum and minimum values of them, and return the results in the form of an array. Like this:

```js
maxvalue, minvalue[(8, 2)];
```

Examples

```js
maxMin([1,3,5],[9,8,7])               should return [8,2]
maxMin([1,10,100,1000],[0,0,0,0])     should return [1000,1]
maxMin([10,20,30,40],[111,11,1,-111]) should return [151,9]
```

---

## Solution

```js
const maxMin = (arr1, arr2) =>
  ((nums) => [Math.max(...nums), Math.min(...nums)])(
    arr1.map((n, i) => Math.abs(n - arr2[i]))
  );
```

```js
const maxMin = (arr1, arr2) =>
  arr1.reduce(
    ([max, min], v, i) => (
      [
        (max = Math.max(Math.abs(v - arr2[i]), max)),
        (min = Math.min(Math.abs(v - arr2[i]), min)),
      ],
      [max, min]
    ),
    [0, Infinity]
  );
```
