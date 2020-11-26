# Description

**Background information**

The Hamming Code is used to correct errors, so-called bit flips, in data transmissions. Later in the description follows a detailed explanation of how it works.
In this Kata we will implement the Hamming Code with bit length 3; this has some advantages and disadvantages:

- **[ + ]** It's simple to implement
- **[ + ]** Compared to other versions of hamming code, we can correct more mistakes
- **[ - ]** The size of the input triples

**Task 1: Encode function**

Implement the encode function, using the following steps:

- convert every letter of the text to its ASCII value;
- convert ASCII values to 8-bit binary;
- triple every bit;
- concatenate the result;

For example:

```js
input: "hey"
--> 104, 101, 121                  // ASCII values
--> 01101000, 01100101, 01111001   // binary
--> 000111111000111000000000 000111111000000111000111 000111111111111000000111  // tripled
--> "000111111000111000000000000111111000000111000111000111111111111000000111"  // concatenated
```

**Task 2: Decode function:**

Check if any errors happened and correct them. Errors will be only bit flips, and not a loss of bits:

- 111 --> 101 : this can and will happen
- 111 --> 11 : this cannot happen

**Note**: the length of the input string is also always divisible by 24 so that you can convert it to an ASCII value.

Steps:

- Split the input into groups of three characters;
- Check if an error occurred: replace each group with the character that occurs most often, e.g. 010 --> 0, 110 --> 1, etc;
- Take each group of 8 characters and convert that binary number;
- Convert the binary values to decimal (ASCII);
- Convert the ASCII values to characters and concatenate the result

For example:

```js
input: "100111111000111001000010000111111000000111001111000111110110111000010111"
--> 100, 111, 111, 000, 111, 001, ...  // triples
-->  0,   1,   1,   0,   1,   0,  ...  // corrected bits
--> 01101000, 01100101, 01111001       // bytes
--> 104, 101, 121                      // ASCII values
--> "hey"
```

---

## Solution

```js
const toAscii = (text) => [...text].map((v) => v.charCodeAt(0));
const toBin = (n) =>
  n.map((n) => "0".repeat(8 - n.toString(2).length) + n.toString(2));
const triple = (bin) =>
  bin.reduce(
    (acc, v) => acc + [...v].reduce((acc, v) => acc + v.repeat(3), ""),
    ""
  );
const pipe = (...fns) =>
  fns.reduce((fn1, fn2) => (...args) => fn2(fn1(...args)));

const encode = (text) => pipe(toAscii, toBin, triple)(text);

const toTriplets = (text, l = 0) =>
  Array.from(
    { length: text.length / 3 },
    () => ((l += 3), text.slice(l - 3, l))
  );
const count = (str) =>
  Object.entries(
    [...str].reduce((acc, v) => ((acc[v] = ++acc[v] || 1), acc), {})
  ).sort((a, b) => b[1] - a[1])[0][0];
const correctBits = (arr) => arr.map((tri) => count(tri));
const toBytes = (arr, l = 0) =>
  Array.from(
    { length: arr.length / 8 },
    () => ((l += 8), arr.slice(l - 8, l).reduce((acc, v) => acc + v, ""))
  );
const readBytes = (arr) =>
  arr.reduce((acc, v) => acc + String.fromCharCode(parseInt(v, 2)), "");

const decode = (bits) =>
  pipe(toTriplets, correctBits, toBytes, readBytes)(bits);
```
