# Description

## The function is not returning the correct values. Can you figure out why?

---

### Problem

```py
def get_planet_name(id):
    name=""
    switch id:
        case 1: name = "Mercury"
        case 2: name = "Venus"
        case 3: name = "Earth"
        case 4: name = "Mars"
        case 5: name = "Jupiter"
        case 6: name = "Saturn"
        case 7: name = "Uranus"
        case 8: name = "Neptune"
    return name
```

### Solution

```py
def get_planet_name(id):
    planets = { 1: 'Mercury', 2: 'Venus', 3: 'Earth', 4: 'Mars', 5: 'Jupiter', 6: 'Saturn', 7: 'Uranus', 8: 'Neptune' }

    return planets.get(id, "Unknown planet")
```
