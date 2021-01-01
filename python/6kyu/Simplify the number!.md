# Description

**Task**
Given a positive integer as input, return the output as a string in the following format:

Each element, corresponding to a digit of the number, multiplied by a power of 10 in such a way that with the sum of these elements you can obtain the original number.

**Examples**

| Input | Output         |
| ----- | -------------- |
| 0     | ""             |
| 56    | "5\*10+6"      |
| 60    | "6\*10"        |
| 999   | "9*100+9*10+9" |
| 10004 | "1\*10000+4"   |

Note: `input >= 0`

---

## Solution

```py
def simplify(number):
    s = str(number)
    return "".join(x + (("*1" if i != len(s) - 1 else "") + "0" * (len(s) - i - 1) + "+") if x != "0" else "" for i, x in enumerate(s))[:-1]
```
