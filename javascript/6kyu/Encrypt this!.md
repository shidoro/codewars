# Description

Encrypt this!

You want to create secret messages which can be deciphered by the [Decipher this!](https://www.codewars.com/kata/decipher-this) kata. Here are the conditions:

1. Your message is a string containing space separated words.
2. You need to encrypt each word in the message using the following rules:
   - The first letter needs to be converted to its ASCII code.
   - The second letter needs to be switched with the last letter
3. Keepin' it simple: There are no special characters in input.

**Examples**:

```js
encryptThis('Hello') === '72olle';
encryptThis('good') === '103doo';
encryptThis('hello world') === '104olle 119drlo';
```

---

## Solution

```js
const encryptThis = (text) =>
  text.replace(
    /\b(\w)(\w?)(\w*?)(\w?)\b/g,
    (_, a, b, c, d) => a.charCodeAt() + d + c + b
  );
```
