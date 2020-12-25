# Description

Every positive integer can be written as a sum of [Fibonacci numbers](https://en.wikipedia.org/wiki/Fibonacci_number). For example `10 = 8 + 2 or 5 + 3 + 2 or 3 + 3 + 2 + 2`. Apparently, this representation is not unique.

It becomes unique, if we rule out _consecutive_ Fibonacci numbers: this is [Zeckendorf's theorem](https://en.wikipedia.org/wiki/Zeckendorf%27s_theorem), first proven by Lekkerkerker in 1952. In the example above, this excludes the last two representations (containing the consecutive Fibonacci numbers `2` and `3`), and we are left with the _Zeckendorf representation_ `10 = 8 + 2`.

Complete the function that returns the Zeckendorf representation of a given integer `n` as a list of Fibonacci numbers in decreasing order. Return an empty list for `n = 0` and `None/nil` for negative `n`.

_Hint: Be greedy!_

---

## Solution

```py
def fib(n):
    a, b = 1, 1
    while b <= n: a, b = b, a + b
    return a

def Zeckendorf_rep(n):
    if n < 0: return None

    Z = []

    while n > 0:
        f = fib(n)
        Z.append(f)
        n = n - f

    return Z
```
