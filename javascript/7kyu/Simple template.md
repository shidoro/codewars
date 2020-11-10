# Description

Implement function createTemplate which takes string with tags wrapped in {{brackets}} as input and returns closure, which can fill string with data (flat object, where keys are tag names).

```js
let personTmpl = createTemplate("{{name}} likes {{animalType}}");
personTmpl({ name: "John", animalType: "dogs" }); // John likes dogs
```

When key doesn't exist in the map, put there empty string.

---

## Solution

```js
const createTemplate = (template) => (x) =>
  template
    .replace(/(?<=\{\{).*?(?=\})/g, (c) => (x[c] ? x[c] : ""))
    .replace(/[{}]/g, "");
```
