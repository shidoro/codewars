# Description

Given: an array containing hashes of names

Return: a string formatted as a list of names separated by commas except for the last two names, which should be separated by an ampersand.

Example:

```py
namelist([ {'name': 'Bart'}, {'name': 'Lisa'}, {'name': 'Maggie'} ])
# returns 'Bart, Lisa & Maggie'

namelist([ {'name': 'Bart'}, {'name': 'Lisa'} ])
# returns 'Bart & Lisa'

namelist([ {'name': 'Bart'} ])
# returns 'Bart'

namelist([])
# returns ''
```

Note: all the hashes are pre-validated and will only contain A-Z, a-z, '-' and '.'.

---

## Solution

```py
from re import sub

namelist = lambda names: sub(r"(.*), (.*)$", r"\1 & \2", ', '.join([x.get('name') for x in names]))
```
