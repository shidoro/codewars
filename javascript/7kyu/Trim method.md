# Description

The `trim()` method removes whitespace from both sides of a string. [w3schools](https://www.w3schools.com/jsref/jsref_trim_string.asp)

In this kata we are going to extend the trim method to be able to remove any character(upper and lower cases) from both sides of a string.

**Task**:

Create a method called `trim` which removes the passed parameter `c`(upper and lower cases) from the leading and tailing of the `string`.

**Note**:

1- If no parameter is being passed you need to remove the leading and tailing spaces.
2- The passed parameter will only be alphabet(upper and lower cases) characters.

**Examples**:

`string = "LLLHello Worldlll"` and `c = "l"` => `"Hello World"`

`string = "Visca ElbarcaXxX"` and `c = "X"` => `"Visca Elbarca"`

---

## Solution

```js
String.prototype.trim = function (c) {
  return this.replace(
    new RegExp(`^${c ? c : " "}+|${c ? c : " "}+\$`, "gi"),
    ""
  );
};
```
