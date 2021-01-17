# Description

Create a function which answers the question "Are you playing banjo?".
If your name starts with the letter "R" or lower case "r", you are playing banjo!

The function takes a name as its only argument, and returns one of the following strings:

```
name + " plays banjo"
name + " does not play banjo"
```

Names given are always valid strings.

---

## Solution

```hs
module Banjo where

areYouPlayingBanjo :: String -> String
areYouPlayingBanjo name@(x : xs) | (x == 'r' || x == 'R') = name ++ " plays banjo" | otherwise = name ++ " does not play banjo"
```
