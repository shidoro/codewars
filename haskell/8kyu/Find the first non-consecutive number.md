# Description

Your task is to find the first element of an array that is not consecutive.

By not consecutive we mean not exactly 1 larger than the previous element of the array.

E.g. If we have an array `[1,2,3,4,6,7,8]` then `1` then `2` then `3` then `4` are all consecutive but `6` is not, so that's the first non-consecutive number.

If the whole array is consecutive then return `null`<sup>2</sup>.

The array will always have at least `2` elements<sup>1</sup> and all elements will be numbers. The numbers will also all be unique and in ascending order. The numbers could be positive or negative and the first non-consecutive could be either too!

If you like this Kata, maybe try this one next: https://www.codewars.com/kata/represent-array-of-numbers-as-ranges

<sup>1</sup> Can you write a solution that will return `null`<sup>2</sup> for both `[]` and `[ x ]` though? (This is an empty array and one with a single number and is not tested for, but you can write your own example test. )

<sup>2</sup>
Swift, Ruby and Crystal: `nil`
Haskell: `Nothing`
Python, Rust, Scala: `None`
Julia: `nothing`
Nim: `none(int)` (See [options](https://nim-lang.org/docs/options.html))

---

## Solution

```hs
module FirstNonConsecutive (firstNonConsecutive) where

firstNonConsecutive :: (Eq a, Num a) => [a] -> Maybe a
firstNonConsecutive [_] = Nothing
firstNonConsecutive (x : y : xs) | y - x == 1 = firstNonConsecutive (y : xs) | otherwise = Just y
```
