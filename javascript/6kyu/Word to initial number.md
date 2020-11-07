# Description

**Intro**:

I was doing a coding challenge. It was one of those multi-step challenges. I don't know if my approach was good or bad, but in one of these steps I was writing a function to convert word to numbers. I did it.. eventually, but... I didn't like how it was written. So I thought why not create kata and check how other people do it :) So:

**Task**:

Your task is to write the word to number converter. Digits in the number should match letters in the word. Plus generated number should be the smallest possible number you can get.

- Words will contain of maximum 10 distinct letters, but word can be any length, even longer than 10 characters long.
- Number can NOT start with 0
- Same letters share the same digit regardless of case
- For empty string return 0

**Examples**:

_"`"A"` -> `1` - OK"_

_"`"ABA"` -> `353` - WRONG ( number is OK, but it's not the smallest number )"_

_"`"ABA"` -> `333` - WRONG ( different letters map to same digits )"_

_"`"ABA"` -> `357` - WRONG ( same letters map to different digits )"_

---

## Solution

```js
const convert = (s) =>
  +s
    .toLowerCase()
    .split("")
    .reduce(
      ([result, tmp], v) => (
        ((tmp += tmp.includes(v) ? "" : v),
        (result +=
          tmp.indexOf(v) === 0
            ? 1
            : tmp.indexOf(v) === 1
            ? 0
            : tmp.indexOf(v))),
        [result, tmp]
      ),
      ["", ""]
    )[0];
```
