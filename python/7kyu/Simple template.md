# Description

Implement function createTemplate which takes string with tags wrapped in {{brackets}} as input and returns closure, which can fill string with data (flat object, where keys are tag names).

```py
let personTmpl = createTemplate("{{name}} likes {{animalType}}");
personTmpl({ name: "John", animalType: "dogs" }); // John likes dogs
```

When key doesn't exist in the map, put there empty string.

---

## Solution

```py
import re
def create_template(template):
    def closure(**kwargs):
        return re.sub(r"{{(\w+)}}", lambda x: kwargs.get(x.group(1)) ,template)

    return closure
```
