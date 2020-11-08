# Description

**Leaderboard climbers**

In this kata you will be given a leaderboard of unique names for example:

```py
["John", "Brian", "Jim", "Dave", "Fred"];
```

Then you will be given a list of strings for example:

```py
["Dave +1", "Fred +4", "Brian -1"];
```

Then you sort the leaderboard.

The steps for our example would be:

```py
# Dave up 1
['John',
 'Brian',
 'Dave',
 'Jim',
 'Fred']
```

```py
# Fred up 4
['Fred',
'John',
'Brian',
'Dave',
'Jim']
```

```py
# Brian down 1
['Fred',
 'John',
 'Dave',
 'Brian',
 'Jim']
```

Then once you have done this you need to return the leaderboard.

All inputs will be valid. All strings in the second list will never ask to move a name up higher or lower than possible eg. `"John +3"` could not be added to the end of the second input list in the example above.

The strings in the second list will always be something in the leaderboard followed by a space and a `+` or `-` sign followed by a number.

---

## Solution

```py
def leaderboard_sort(leaderboard, changes):
    board = leaderboard[:]

    for climber, pos in map(str.split, changes):
        pos, idx = int(pos), board.index(climber)
        board.insert(idx - pos, board.pop(idx))

    return board
```
