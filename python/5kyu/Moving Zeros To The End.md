# Description

Write an algorithm that takes an array and moves all of the zeros to the end, preserving the order of the other elements.

```py
move_zeros([False,1,0,1,2,0,1,3,"a"]) # returns[False,1,1,2,1,3,"a",0,0]
```

---

## Solution

```py
def move_zeros(array):
    z = []
    return [*filter(lambda x: x != 0 or type(x) == bool or z.append(x), array)] + z
```
