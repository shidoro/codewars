# Description

Jumping number is the number that All adjacent digits in it differ by 1.

**Task**

Given a number, Find if it is Jumping or not .

---

## Solution

```py
def jumping_number(number):
    lst = list(map(int, str(number)))
    return "Jumping!!" if len(lst) == 1 or { 1 } == { abs(a - b) for a, b in zip(lst, lst[1:]) } else "Not!!"
```
