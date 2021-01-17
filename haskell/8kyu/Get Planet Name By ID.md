# Description

The function is not returning the correct values. Can you figure out why?

```hs
getPlanetName 3 -- should return "Earth"
```

---

## Solution

```hs
module Planets where

getPlanetName :: Int -> String
getPlanetName = (!!) ["", "Mercury", "Venus", "Earth", "Mars", "Jupiter", "Saturn", "Uranus", "Neptune"]
```
