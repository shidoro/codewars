# Description

You need to write a function ( `addOrChangeUrlParameter(url, keyValueParameter)` ) that can manipulate URL parameters.

It should be able to

- add a parameter to an existing URL,

but also to

- change a parameter if it already exists.

**Example:**

```js
addOrChangeUrlParameter("www.example.com", "key=value");
// -> 'www.example.com?key=value' (adds a parameter).

addOrChangeUrlParameter("www.example.com?key=value", "key2=value2");
// -> 'www.example.com?key=value&key2=value2' (adds another parameter).

addOrChangeUrlParameter("www.example.com?key=oldValue`", "key=newValue");
// ->'www.example.com?key=newValue' (changes the parameter).
```

---

## Solution

```js
const addOrChangeUrlParameter = (url, param) =>
  ((url) =>
    url.includes(param) ? url : url + (url.includes("?") ? "&" : "?") + param)(
    url.replace(new RegExp(param.split("=")[0] + "=[^&]+"), param)
  );
```
