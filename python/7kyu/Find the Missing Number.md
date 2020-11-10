# Description

The following was a question that I received during a technical interview for an entry level software developer position. I thought I'd post it here so that everyone could give it a go:

You are given an unsorted array containing all the integers from 0 to 100 inclusively. However, one number is missing. Write a function to find and return this number. What are the time and space complexities of your solution?

---

## Solution

_using maths_

```py
def missing_no(nums):
    return len(nums) * (len(nums) + 1) // 2 - sum(nums)
```

_don't dispare if you don't know maths_

```py
def missing_no(nums):
    if not len(nums): return 1
    nums = sorted(nums, key = int)
    x = set(nums)
    y = set(range(0, nums[-1] + 1))

    return len(nums) if x == y else list(x ^ y)[0]
```
